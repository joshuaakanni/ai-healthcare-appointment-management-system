# AI Healthcare Appointment Management System

A Voice AI healthcare receptionist that helps callers manage patient records and appointments through n8n, MCP, and an EHR API.

The system can find or create patient records, check appointment availability, book appointments, retrieve appointment details, list appointments, reschedule appointments, and cancel appointments.

> **Portfolio note:** This system was built under contract for LENOGROW and is published here as a sanitized demonstration with permission. Real credentials, private infrastructure details, and patient information are not included.

> **Important:** This system does not diagnose symptoms, provide medical advice, or contact emergency services.

## Project Overview

This project is a Voice AI healthcare receptionist designed to support routine front-desk and appointment-management tasks.

A caller speaks with the Voice AI phone agent, which identifies the requested action and sends it through an MCP server to the appropriate n8n workflow. The workflow normalizes the input, generates a request nonce, communicates with the EHR API, and returns the result to the voice agent for confirmation.

## Business Problem

Healthcare organizations often spend significant staff time handling repetitive administrative calls such as checking availability, creating patient records, booking appointments, retrieving appointment details, rescheduling visits, and processing cancellations.

This system helps reduce that workload by allowing a Voice AI receptionist to complete these routine actions through connected backend workflows.

## Core Capabilities

- Look up an existing patient
- Create a new patient record
- List a patient’s appointments
- Check provider and location availability
- Create a new appointment
- Retrieve a specific appointment
- Reschedule an existing appointment
- Cancel an appointment

## System Architecture

```text
Caller
   ↓
Voice AI Phone Agent
   ↓
MCP Server
   ↓
Selected n8n Workflow
   ↓
Input Normalization
   ↓
Nonce Generation
   ↓
HTTP Request to EHR API
   ↓
Result Returned to Voice Agent
   ↓
Caller Receives Confirmation

## Included Workflows

```text
workflows/
├── mcp-server.json
├── lookup-patient.json
├── create-patient.json
├── list-patient-appointments.json
├── check-availability.json
├── create-appointment.json
├── get-appointment.json
├── reschedule-appointment.json
└── cancel-appointment.json
```

Each JSON file is a sanitized public portfolio version of the original n8n workflow.

## Tools and Technologies

- n8n
- Model Context Protocol (MCP)
- Voice AI phone agent
- JavaScript Code nodes
- HTTP Request nodes
- EHR API integration
- JSON
- Webhooks

## Setup and Import

1. Download the required JSON files from the `workflows` folder.
2. Open your n8n workspace.
3. Import each workflow into n8n.
4. Connect the eight supporting workflows to the MCP server workflow.
5. Configure your own EHR API endpoint and authentication.
6. Connect the MCP server to your Voice AI phone agent.
7. Test the system using fictional patient and appointment data.
8. Keep all workflows inactive until the configuration has been reviewed.

## Environment Configuration

The repository includes a `.env.example` file containing placeholders only:

```env
EHR_API_BASE_URL=YOUR_EHR_API_BASE_URL
EHR_API_SECRET=YOUR_EHR_API_SECRET
MCP_SERVER_PATH=YOUR_MCP_SERVER_PATH
MCP_HEADER_SECRET=YOUR_MCP_HEADER_SECRET
```

Never upload real API secrets, authentication headers, private endpoints, or patient information to GitHub.

## Testing and Project Status

**Status: Completed, tested, and published**

The system has been tested to:

- Route requests through the MCP server
- Call the correct supporting n8n workflow
- Normalize patient and appointment inputs
- Generate a unique request nonce
- Send requests to the EHR API
- Return results to the Voice AI phone agent
- Support patient lookup and creation
- Support appointment availability, booking, retrieval, rescheduling, and cancellation

This repository contains sanitized workflow files for portfolio and demonstration purposes.

## Security and Privacy

Before publication, the workflow files were reviewed and sanitized.

The following information was removed or replaced:

- LENOGROW API secrets
- Private EHR endpoints
- MCP authentication details
- Internal workflow IDs
- Webhook paths
- n8n instance identifiers
- Workflow version identifiers
- Organization-specific infrastructure details
- Hard-coded test values where appropriate

This repository does not contain real patient records, medical information, appointment data, API keys, passwords, or private authentication tokens.

The original production configuration remains private.

## Known Limitations

- The system handles administrative healthcare tasks only.
- It does not diagnose symptoms or provide medical advice.
- It does not replace trained healthcare staff.
- It does not contact emergency services.
- It depends on the connected EHR API being available.
- Appointment results depend on the accuracy of the EHR data.
- Voice recognition may require confirmation for names, dates, phone numbers, and appointment times.
- Production use requires appropriate privacy, security, access-control, and healthcare-compliance reviews.

## Possible Future Improvements

- Add multilingual voice support
- Add automated appointment reminders
- Add call summaries for authorized staff
- Add configurable appointment rules
- Add staff notifications for failed requests
- Add improved error handling and retry logic
- Add reporting and appointment analytics
- Add stronger identity-verification steps

## Project Attribution

This system was built by **Joshua Asegunloluwa Akanni** under contract for **LENOGROW**.

The project is published here as a sanitized portfolio demonstration with permission.

## Author

**Joshua Asegunloluwa Akanni**

AI Automation Specialist | n8n Workflow Developer | AI Agent Builder

Website: [blanyx.com](https://blanyx.com)

GitHub: [@joshuaakanni](https://github.com/joshuaakanni)

## License

No open-source license has been added.

This repository is shared for portfolio review and demonstration only. Ownership of the original project remains with LENOGROW.
