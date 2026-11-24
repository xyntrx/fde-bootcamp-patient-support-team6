# Patient Support Agent

An Agentforce Service Agent for a global healthcare provider, built as part of the FDE Bootcamp (Team 6).

## Overview

The Patient Support Agent handles common patient inquiries via web chat, grounded on a Patient Support Knowledge Base. It covers:

- Insurance benefits & coverage
- Appointment scheduling
- Prescription refills & pharmacy services
- Patient portal & account access

When a question is outside the knowledge base, the agent asks the patient if they'd like to be transferred to a human agent, then escalates with a safety message before handing off.

## Architecture

- **Channel:** Messaging for Web (Embedded Service on Experience Cloud portal)
- **Agent type:** `AgentforceServiceAgent`
- **Subagents:** `agent_router` → `patient_faq` + `escalation`
- **Knowledge:** Patient Support Knowledge Base (RAG-grounded)
- **Compliance:** Einstein Trust Layer — Pattern Based masking (PII, HIPAA, GDPR, COPPA, CCPA)

## Org

- **Instance:** `https://orgfarm-c0e12124ec.my.salesforce.com`
- **Alias:** `fde-bootcamp`
- **Username:** `ashish.tyagi@salesforce.com.fdebootcamp`

## Setup

```bash
# Authenticate
sf org login web --alias fde-bootcamp

# Retrieve latest metadata
sf project retrieve start --metadata "AiAuthoringBundle:PatientSupportAgent" --target-org fde-bootcamp

# Deploy
sf project deploy start --metadata "AiAuthoringBundle:PatientSupportAgent" --target-org fde-bootcamp
```

## Team

FDE Bootcamp — Team 6
