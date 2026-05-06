---
notion_id: "35743c23-a5e2-809d-a800-d03a66af92b1"
notion_last_edited: "2026-05-05T11:41:00.000Z"
tags:
resolved: "False"
problem tags:
Date: "2026-05-05"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003640304667"
---

# Issue:

The INTERNAL\!SGrooms account is my domain administrator account. The Domain Admins group is a member of the local Administrators group on ever server we have. I ran this in CMD both as myself and as Admin and had the same error. I logged in as a local Administrator user on this machine and tried to run the batch file as directed and received the same error, just with that user’s name in the log(SDC-MEEC\suretyadmin)    

# Analysis:

 Based on the log traces, the query execution is failing due to special characters in the username. Kindly ask the customer to run the BAT file using another admin account without special characters and verify the status.

# Log traces:

Please login to the system as INTERNAL\!SGrooms and execute initPgsql.bat script with administrator privileges. If issue is not yet solved, please contact support.
java.lang.Exception: Exception while initializing DB.
at com.adventnet.persistence.PersistenceInitializer.initializeDBAndPers(PersistenceInitializer.java:466)
at com.adventnet.persistence.PersistenceInitializer.initialize(PersistenceInitializer.java:440)
at com.adventnet.persistence.StandAlonePersistence.startDB(StandAlonePersistence.java:43)
at com.adventnet.persistence.StandAlonePersistence.startServer(StandAlonePersistence.java:161)
at com.me.devicemanagement.onpremise.server.util.CommandLineQueryExecuter.startServer(CommandLineQueryExecuter.java:55)
at com.me.devicemanagement.onpremise.server.util.CommandLineQueryExecuter.main(CommandLineQueryExecuter.java:220)
Caused by: java.lang.RuntimeException: Please login to the system as INTERNAL\!SGrooms and execute initPgsql.bat script with administrator privileges. If issue is not yet solved, please contact support.
at com.adventnet.persistence.PersistenceInitializer.printErrorMsgAndHalt(PersistenceInitializer.java:1661)
at com.adventnet.persistence.PersistenceInitializer.startDB(PersistenceInitializer.java:1548)

