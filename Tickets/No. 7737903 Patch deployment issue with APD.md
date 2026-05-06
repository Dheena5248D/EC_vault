---
notion_id: "33a43c23-a5e2-8027-be38-c8b5ba826737"
notion_last_edited: "2026-04-06T07:08:00.000Z"
tags:
  - "APD"
resolved: "False"
problem tags:
Solved by: "Others"
Date: "2026-04-06"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003546973198"
---

# Issue:

The cx is facing an issue where some approved patches are not being deployed. The APD task category and severity are configured appropriately;  Upon further investigation, it was observed that the machine is not part of the APD task, even though the APD scope is targeted to the Active Directory OU to which the machine belongs.


# Analysis:

Based on the logs collected from the machine "LA-DT-15406", that the machine is not part of the APD task because the OU-based filter did not succeed.

If the APD is targeted to the OU that includes this machine, kindly ask the cx to share a screenshot confirming that "LA-DT-15406" is present within the specified OU.

# Log traces:

```sql
computer.log

[ 2026-04-01 22:29:47:249 ] [ 12452 ] [INFO] @@@@@@@@ Inside ProcessFilter Method @@@@@@@@ 
[ 2026-04-01 22:29:47:254 ] [ 12452 ] [INFO] @@@@@@@@@@@@@@@@@@@@@@@@ Inside  ProcessNewFilter method @@@@@@@@@@@@@@@@@
[ 2026-04-01 22:29:47:254 ] [ 12452 ] [INFO] ProcessFilterComponentValue : filter_class_id = Domain , comparator_id = Equals , logical_operator = OR 
[ 2026-04-01 22:29:47:254 ] [ 12452 ] [INFO] ProcessFilterComponentValue : isExcludeSubOU value = 0 
[ 2026-04-01 22:29:47:254 ] [ 12452 ] [INFO] ProcessFilterComponentValue : DomainType value = 2 
[ 2026-04-01 22:29:47:254 ] [ 12452 ] [ERROR] ChangeAnsiToUTF8Str: ansiString is empty! 
[ 2026-04-01 22:29:47:254 ] [ 12452 ] [INFO] GetValueAndCompare : Compare Value   -> cac.fd.pvt 
[ 2026-04-01 22:29:47:254 ] [ 12452 ] [INFO] GetValueAndCompare : Retrieved Server Value -> CAC.FD.PVT. Chassis value -> (null) 
[ 2026-04-01 22:29:47:254 ] [ 12452 ] [INFO] ProcessNewFilter : Main filter process succeeded 
[ 2026-04-01 22:29:47:254 ] [ 12452 ] [INFO] ProcessNewFilter: processComputerSubFilter skipped for computer config 
[ 2026-04-01 22:29:47:254 ] [ 12452 ] [INFO] ProcessFilterComponentValue : filter_class_id = OU , comparator_id = Equals , logical_operator = OR 
[ 2026-04-01 22:29:47:254 ] [ 12452 ] [INFO] ProcessFilterComponentValue : Netbiosname validation starts....
[ 2026-04-01 22:29:47:254 ] [ 12452 ] [ERROR] ChangeAnsiToUTF8Str: ansiString is empty! 
[ 2026-04-01 22:29:47:254 ] [ 12452 ] [INFO] GetValueAndCompare : Compare Value   -> CAC 
[ 2026-04-01 22:29:47:254 ] [ 12452 ] [INFO] GetValueAndCompare : Retrieved Server Value -> CAC. Chassis value -> (null) 
[ 2026-04-01 22:29:47:254 ] [ 12452 ] [INFO] ProcessFilterComponentValue : Netbiosname validation ends....
[ 2026-04-01 22:29:47:254 ] [ 12452 ] [INFO] ProcessFilterComponentValue : isExcludeSubOU value = 0 
[ 2026-04-01 22:29:47:254 ] [ 12452 ] [INFO] ProcessFilterComponentValue : DomainType value = 1 
[ 2026-04-01 22:29:47:254 ] [ 12452 ] [INFO] @@@@@@@@ Inside FilterByOU Method @@@@@@@@ 
[ 2026-04-01 22:29:47:254 ] [ 12452 ] [INFO] FilterByOU : The LDAP Path is given by LDAP://LSNGDC02/<GUID=1985767417309e4d912ecd37b44d76d9> 
[ 2026-04-01 22:29:47:254 ] [ 12452 ] [INFO] Inside ADsBindingSSL
[ 2026-04-01 22:29:47:256 ] [ 12452 ] [INFO] Going to connect through LDAP
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] LDAP Connection Success
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] Value Obtained
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] End of ADsBindingSSL
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] Filter provided for Directory Search : (&(objectCategory=computer)(name=LA-DT-15406)) 
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] @@@@@@@@ End Of FilterByOU Method @@@@@@@@ 
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] ProcessFilterComponentValue : Netbiosname validation starts....
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [ERROR] ChangeAnsiToUTF8Str: ansiString is empty! 
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] GetValueAndCompare : Compare Value   -> CAC 
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] GetValueAndCompare : Retrieved Server Value -> CAC. Chassis value -> (null) 
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] ProcessFilterComponentValue : Netbiosname validation ends....
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] ProcessFilterComponentValue : isExcludeSubOU value = 0 
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] ProcessFilterComponentValue : DomainType value = 1 
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] @@@@@@@@ Inside FilterByOU Method @@@@@@@@ 
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] FilterByOU : The LDAP Path is given by LDAP://LSNGDC02/<GUID=94656656da711143afbdb0b30cb074ca> 
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] Inside ADsBindingSSL
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] Going to connect through LDAP
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] LDAP Connection Success
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] Value Obtained
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] End of ADsBindingSSL
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] Filter provided for Directory Search : (&(objectCategory=computer)(name=LA-DT-15406)) 
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] @@@@@@@@ End Of FilterByOU Method @@@@@@@@ 
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] ProcessFilterComponentValue : Netbiosname validation starts....
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [ERROR] ChangeAnsiToUTF8Str: ansiString is empty! 
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] GetValueAndCompare : Compare Value   -> CAC 
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] GetValueAndCompare : Retrieved Server Value -> CAC. Chassis value -> (null) 
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] ProcessFilterComponentValue : Netbiosname validation ends....
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] ProcessFilterComponentValue : isExcludeSubOU value = 0 
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] ProcessFilterComponentValue : DomainType value = 1 
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] @@@@@@@@ Inside FilterByOU Method @@@@@@@@ 
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] FilterByOU : The LDAP Path is given by LDAP://LSNGDC02/<GUID=2a4fc72d25354e43963b3ce8735fc11c> 
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] Inside ADsBindingSSL
[ 2026-04-01 22:29:47:437 ] [ 12452 ] [INFO] Going to connect through LDAP
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] LDAP Connection Success
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] Value Obtained
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] End of ADsBindingSSL
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] Filter provided for Directory Search : (&(objectCategory=computer)(name=LA-DT-15406)) 
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] @@@@@@@@ End Of FilterByOU Method @@@@@@@@ 
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] ProcessFilterComponentValue : Netbiosname validation starts....
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [ERROR] ChangeAnsiToUTF8Str: ansiString is empty! 
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] GetValueAndCompare : Compare Value   -> CAC 
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] GetValueAndCompare : Retrieved Server Value -> CAC. Chassis value -> (null) 
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] ProcessFilterComponentValue : Netbiosname validation ends....
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] ProcessFilterComponentValue : isExcludeSubOU value = 0 
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] ProcessFilterComponentValue : DomainType value = 1 
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] @@@@@@@@ Inside FilterByOU Method @@@@@@@@ 
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] FilterByOU : The LDAP Path is given by LDAP://LSNGDC02/<GUID=a57283d31cb61143b70b6d7361af0e57> 
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] Inside ADsBindingSSL
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] Going to connect through LDAP
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] LDAP Connection Success
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] Value Obtained
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] End of ADsBindingSSL
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] Filter provided for Directory Search : (&(objectCategory=computer)(name=LA-DT-15406)) 
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] @@@@@@@@ End Of FilterByOU Method @@@@@@@@ 
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] ProcessFilterComponentValue : Netbiosname validation starts....
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [ERROR] ChangeAnsiToUTF8Str: ansiString is empty! 
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] GetValueAndCompare : Compare Value   -> CAC 
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] GetValueAndCompare : Retrieved Server Value -> CAC. Chassis value -> (null) 
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] ProcessFilterComponentValue : Netbiosname validation ends....
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] ProcessFilterComponentValue : isExcludeSubOU value = 0 
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] ProcessFilterComponentValue : DomainType value = 1 
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] @@@@@@@@ Inside FilterByOU Method @@@@@@@@ 
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] FilterByOU : The LDAP Path is given by LDAP://LSNGDC02/<GUID=0e4b34f29f6865439b21962ff6578185> 
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] Inside ADsBindingSSL
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] Going to connect through LDAP
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] LDAP Connection Success
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] Value Obtained
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] End of ADsBindingSSL
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] Filter provided for Directory Search : (&(objectCategory=computer)(name=LA-DT-15406)) 
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] @@@@@@@@ End Of FilterByOU Method @@@@@@@@ 
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] ProcessFilterComponentValue : Netbiosname validation starts....
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [ERROR] ChangeAnsiToUTF8Str: ansiString is empty! 
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] GetValueAndCompare : Compare Value   -> CAC 
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] GetValueAndCompare : Retrieved Server Value -> CAC. Chassis value -> (null) 
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] ProcessFilterComponentValue : Netbiosname validation ends....
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] ProcessFilterComponentValue : isExcludeSubOU value = 0 
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] ProcessFilterComponentValue : DomainType value = 1 
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] @@@@@@@@ Inside FilterByOU Method @@@@@@@@ 
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] FilterByOU : The LDAP Path is given by LDAP://LSNGDC02/<GUID=98f03532eea6b4498e3b3dc831b7b382> 
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] Inside ADsBindingSSL
[ 2026-04-01 22:29:47:452 ] [ 12452 ] [INFO] Going to connect through LDAP
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] LDAP Connection Success
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] Value Obtained
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] End of ADsBindingSSL
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] Filter provided for Directory Search : (&(objectCategory=computer)(name=LA-DT-15406)) 
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] @@@@@@@@ End Of FilterByOU Method @@@@@@@@ 
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] ProcessFilterComponentValue : Netbiosname validation starts....
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [ERROR] ChangeAnsiToUTF8Str: ansiString is empty! 
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] GetValueAndCompare : Compare Value   -> CAC 
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] GetValueAndCompare : Retrieved Server Value -> CAC. Chassis value -> (null) 
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] ProcessFilterComponentValue : Netbiosname validation ends....
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] ProcessFilterComponentValue : isExcludeSubOU value = 0 
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] ProcessFilterComponentValue : DomainType value = 1 
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] @@@@@@@@ Inside FilterByOU Method @@@@@@@@ 
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] FilterByOU : The LDAP Path is given by LDAP://LSNGDC02/<GUID=2c9201432aeec54f899821efa3f1a9eb> 
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] Inside ADsBindingSSL
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] Going to connect through LDAP
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] LDAP Connection Success
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] Value Obtained
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] End of ADsBindingSSL
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] Filter provided for Directory Search : (&(objectCategory=computer)(name=LA-DT-15406)) 
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] @@@@@@@@ End Of FilterByOU Method @@@@@@@@ 
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] ProcessFilterComponentValue : Netbiosname validation starts....
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [ERROR] ChangeAnsiToUTF8Str: ansiString is empty! 
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] GetValueAndCompare : Compare Value   -> CAC 
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] GetValueAndCompare : Retrieved Server Value -> CAC. Chassis value -> (null) 
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] ProcessFilterComponentValue : Netbiosname validation ends....
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] ProcessFilterComponentValue : isExcludeSubOU value = 0 
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] ProcessFilterComponentValue : DomainType value = 1 
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] @@@@@@@@ Inside FilterByOU Method @@@@@@@@ 
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] FilterByOU : The LDAP Path is given by LDAP://LSNGDC02/<GUID=aea41c0308a49b4caf88001fe479bb7d> 
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] Inside ADsBindingSSL
[ 2026-04-01 22:29:47:468 ] [ 12452 ] [INFO] Going to connect through LDAP
[ 2026-04-01 22:29:47:484 ] [ 12452 ] [INFO] LDAP Connection Success
[ 2026-04-01 22:29:47:484 ] [ 12452 ] [INFO] Value Obtained
[ 2026-04-01 22:29:47:484 ] [ 12452 ] [INFO] End of ADsBindingSSL
[ 2026-04-01 22:29:47:484 ] [ 12452 ] [INFO] Filter provided for Directory Search : (&(objectCategory=computer)(name=LA-DT-15406)) 
[ 2026-04-01 22:29:47:484 ] [ 12452 ] [INFO] @@@@@@@@ End Of FilterByOU Method @@@@@@@@ 
[ 2026-04-01 22:29:47:484 ] [ 12452 ] [INFO] ProcessFilterComponentValue : Netbiosname validation starts....
[ 2026-04-01 22:29:47:484 ] [ 12452 ] [ERROR] ChangeAnsiToUTF8Str: ansiString is empty! 
[ 2026-04-01 22:29:47:484 ] [ 12452 ] [INFO] GetValueAndCompare : Compare Value   -> CAC 
[ 2026-04-01 22:29:47:484 ] [ 12452 ] [INFO] GetValueAndCompare : Retrieved Server Value -> CAC. Chassis value -> (null) 
[ 2026-04-01 22:29:47:484 ] [ 12452 ] [INFO] ProcessFilterComponentValue : Netbiosname validation ends....
[ 2026-04-01 22:29:47:484 ] [ 12452 ] [INFO] ProcessFilterComponentValue : isExcludeSubOU value = 0 
[ 2026-04-01 22:29:47:484 ] [ 12452 ] [INFO] ProcessFilterComponentValue : DomainType value = 1 
[ 2026-04-01 22:29:47:484 ] [ 12452 ] [INFO] @@@@@@@@ Inside FilterByOU Method @@@@@@@@ 
[ 2026-04-01 22:29:47:484 ] [ 12452 ] [INFO] FilterByOU : The LDAP Path is given by LDAP://LSNGDC02/<GUID=11101a24e7d1e94ba9de58c75a544bf7> 
[ 2026-04-01 22:29:47:484 ] [ 12452 ] [INFO] Inside ADsBindingSSL
[ 2026-04-01 22:29:47:484 ] [ 12452 ] [INFO] Going to connect through LDAP
[ 2026-04-01 22:29:47:484 ] [ 12452 ] [INFO] LDAP Connection Success
[ 2026-04-01 22:29:47:484 ] [ 12452 ] [INFO] Value Obtained
[ 2026-04-01 22:29:47:484 ] [ 12452 ] [INFO] End of ADsBindingSSL
[ 2026-04-01 22:29:47:484 ] [ 12452 ] [INFO] Filter provided for Directory Search : (&(objectCategory=computer)(name=LA-DT-15406)) 
[ 2026-04-01 22:29:47:484 ] [ 12452 ] [INFO] @@@@@@@@ End Of FilterByOU Method @@@@@@@@ 
[ 2026-04-01 22:29:47:484 ] [ 12452 ] [INFO] @@@@@@@@@@@@@@@@@@@@@@@@ End of  ProcessNewFilter method @@@@@@@@@@@@@@@@@
[ 2026-04-01 22:29:47:484 ] [ 12452 ] [INFO] @@@@@@@@ End Of ProcessFilter Method @@@@@@@@ 
[ 2026-04-01 22:29:47:497 ] [ 12452 ] [INFO] Collection CAC Main Building  is not applicable for this target computer or target user. 
[ 2026-04-01 22:29:47:497 ] [ 12452 ] [INFO] ****************************************************************************** 
[ 2026-04-01 22:29:47:497 ] [ 12452 ] [INFO] **************************************************************************

```

