---
notion_id: "33443c23-a5e2-8065-9ac2-c4a77a8a6f19"
notion_last_edited: "2026-03-31T12:17:00.000Z"
tags:
  - "API"
  - "ui"
resolved: "False"
problem tags:
  - "ui rendering"
Date: "2026-03-31"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003531744570"
---

# Issue:

URL: [https://deskcentr.corp.rabota.space:8383/store](https://deskcentr.corp.rabota.space:8383/store)

The customer is trying to access the URL that is only accessible by the Agent.

The Authentication will not be completed by using the server login credentials; this is asking for the basic authentication used only by the agent for agent server communication, so that the console login credentials are not accepted

The credential that has been created by the EPC server and is only accessed by the agent.

This request will not be vulnerable from the EndpoinCentral. And that the server is not compromised.

# Analysis:

This behavior is expected across all cases. The URL in the query is for agent-to-server communication and uses basic authentication.

The authentication requested here is not related to console login credentials. Instead, it is a dedicated credential created by the server and used only by the agent for secure communication. Hence, attempting to access this URL manually via a browser will prompt for credentials, and standard server console credentials will not work.

In conclusion, this is expected product behavior, and the server is not compromised

# Log traces:



