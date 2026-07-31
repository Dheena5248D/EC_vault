
## smtpconfiguration (only onprem only)

This table consists of mail server settings
The details from the UI admin -> mail server -> mail server settings

```table
Name               |Value                                
-------------------+-------------------------------------
servername         |sandbox.smtp.mailtrap.io             
port               |587                                  
username           |2aa37694744566                       
sender_name        |Administrator                        
sender_address     |noreply@yourdomain.com               
is_tls_enabled     |false                                
is_smtps_enabled   |false                                
previous_error_code|-1                                   
auth_type          |0                                    
use_proxy          |false                                
credential_id      |                                     
PASSWORD           |Ã     '?Ø¾rê bÒE  ¡=CÐ}Ø ¥   <á é WéC
```



# configurations
## collection
This table holds the data of configurations (manual deployment / APD)

```
Name                |Value                                      |
--------------------+-------------------------------------------+
collection_id       |1                                          |
collection_name     |Change Date Format                         |
description         |Change the system date format to yyyy-MM-dd|
creation_time       |1428654451625                              |
modified_time       |1428654451625                              |
is_single_config    |true                                       |
collection_type     |2                                          |
apply_type          |1                                          |
is_config_collection|true                                       |
platform_id         |1                                          |
is_deleted          |false                                      |
collection_state    |0                                          |
show_in_view        |false                                      |
db_updated_time     |0                                          |
```

## DCUsersCollectionMapping

this table holds the data of configuration created user and modified user 
```table
Name                 |Value        |
---------------------+-------------+
collection_id        |304          |
dc_user_id           |2            |
last_modified_user_id|2            |
db_updated_time      |1773034393364|
```


# ResourceToRebootDetails

This table holds whether a system require reboot or not 
```table
Name             |Value        |
-----------------+-------------+git
resource_id      |1202         |
reboot_req_status|false        |
reboot_req_reason|--           |
db_updated_time  |1783575913796|
```
