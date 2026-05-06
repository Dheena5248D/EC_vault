---
notion_id: "33e43c23-a5e2-80eb-914c-d2240bd60db5"
notion_last_edited: "2026-04-10T13:23:00.000Z"
tags:
resolved: "False"
problem tags:
Solved by: "ME"
Date: "2026-04-10"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003567661680"
---

# Issue:

error indicating that too many requests are being sent to the API 

# Analysis:

A customer can make 30 API calls for one minute. if the customer exceeds that limit a cooldown period for the api for 5 minute will trigger and the customer will get "too many requests, please try again later" error message and the user can call the api after 5 minute.

kindly refer this zask,

[https://zask.pali.io/zask/EMSTechAsk/questions/9093146170?answer=2283061290](https://zask.pali.io/zask/EMSTechAsk/questions/9093146170?answer=2283061290)

# Log traces:

