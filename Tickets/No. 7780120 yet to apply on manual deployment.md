---
notion_id: "33c43c23-a5e2-8089-b5cd-c6ddb26738fc"
notion_last_edited: "2026-04-09T13:46:00.000Z"
tags:
resolved: "False"
problem tags:
Solved by: "ME"
Date: "2026-04-08"
---

# Issue:

Patch not get deployed on the machine even if the machine is online and in yet to apply status.

# Analysis:

There is a known issue on the customers build where refreshing the console while the deployment is created and a download is in progress.

This issue is fixed on latest builds, kindly suggest server upgrade for the customer

[https://www.manageengine.com/products/desktop-central/service-packs.html](https://www.manageengine.com/products/desktop-central/service-packs.html)

# Log traces:

```prolog
build.number=114253501

[15:06:34:233]|[04-06-2026]|[ConfigLogger]|[INFO]|[337]|[863701b7-8e71-4e3c-bd5e-15232909f733]: Configuration has been persisted with :: Collection ID : 1205 collectionName : Patch Deploy Test 06042026_002|

[15:06:37:843]|[04-06-2026]|[CollectionStatusLogger]|[INFO]|[53410]|[df635008-28fd-4202-9778-fa40a1a55c2b]: Starting Refresh for collection: 1205 at: Apr 6, 2026 03:06 PM|


[15:06:34:139]|[04-06-2026]|[ConfigLogger]|[INFO]|[337]|[863701b7-8e71-4e3c-bd5e-15232909f733]: #### Going to create collection DO ----  |
[15:06:34:139]|[04-06-2026]|[ConfigLogger]|[INFO]|[337]|[863701b7-8e71-4e3c-bd5e-15232909f733]: Into constructing ConfigDO for the configs count : 1|
[15:06:34:139]|[04-06-2026]|[ConfigLogger]|[INFO]|[337]|[863701b7-8e71-4e3c-bd5e-15232909f733]: Going to construct ConfigDO for the config id : 151|
[15:06:34:144]|[04-06-2026]|[ConfigLogger]|[INFO]|[337]|[863701b7-8e71-4e3c-bd5e-15232909f733]: handleRequest invoked with request type: 2|
[15:06:34:144]|[04-06-2026]|[ConfigLogger]|[INFO]|[337]|[863701b7-8e71-4e3c-bd5e-15232909f733]: handleRequest Properties: {retainSuspendedState=false, windowStartTime=00:00:00, isUserDefTemplate=false, windowStopTime=23:59:59, showProgress=0, isPatchUninstallConfig=false, rebootMessage=, continueDeployment=1, skipScheduleDate=, templateId=6, userID=304, ConfigPackageSize=0, isTemplateClone=false, expiryDate=, clonedConfig=false, skipShceduleTime=, isModified=false, insAfterDate=, isExpiryEnabled=false, isUSBConfig=false, action=ApplyNow, rebootValue=0, isSPConfig=false, excludeServer=1, skipCollTime=0, actionToPerform=2, isConfigApi=true, insAfterTime=, skipCollection=0, skipTillTime=-1, userName=admin2, collectionDO=<WritableDataObject>
 <Tables>
[CollectionRetry, CollnToCustomerRel, Collection, CollnActivePeriod, CollectionStatus, CollectionVersion, CollectionRWStatus, CollSchExecution] </Tables>
 <JoinsInDO>
 </JoinsInDO>
 <Operations>
  <INSERT><CollectionRetry_PK COLLECTION_ID="UVH@1553365474"/></INSERT>
  <INSERT><CollnToCustomerRel_PK COLLECTION_ID="UVH@1553365474", CUSTOMER_ID="1"/></INSERT>
  <INSERT><Collection_PK COLLECTION_ID="UVH@1553365474"/></INSERT>
  <INSERT><CollnActivePeriod_PK COLLECTION_ID="UVH@1553365474"/></INSERT>
  <INSERT><CollectionStatus_PK COLLECTION_ID="UVH@1553365474"/></INSERT>
  <INSERT><CollectionVersion_PK COLLECTION_ID="UVH@1553365474"/></INSERT>
  <INSERT><CollectionRWStatus_PK COLLECTION_ID="UVH@1553365474"/></INSERT>
  <INSERT><CollSchExecution_PK COLLECTION_ID="UVH@1553365474"/></INSERT>
 </Operations>
 <Rows>
  <CollectionRetry COLLECTION_ID="UVH@1553365474" ENABLE_RETRY="true" NO_OF_RETRIES="2" REFRESH_MIN_RETRY="1" LOGON_STARTUP_MIN_RETRY="1" />
  <CollnToCustomerRel COLLECTION_ID="UVH@1553365474" CUSTOMER_ID="1" DB_UPDATED_TIME="1775459194139" />
  <Collection COLLECTION_ID="UVH@1553365474" COLLECTION_NAME="Patch Deploy Test 06042026_002" DESCRIPTION="--" CREATION_TIME="1775459194139" MODIFIED_TIME="1775459194139" IS_SINGLE_CONFIG="true" COLLECTION_TYPE="1" APPLY_TYPE="1" IS_CONFIG_COLLECTION="true" PLATFORM_ID="1" IS_DELETED="false" COLLECTION_STATE="0" SHOW_IN_VIEW="true" DB_UPDATED_TIME="1775459194139" />
  <CollnActivePeriod COLLECTION_ID="UVH@1553365474" START_TIME="-1" END_TIME="-1" />
  <CollectionStatus COLLECTION_ID="UVH@1553365474" STATUS="13" IS_STATUS_COMPUTABLE="true" PROFILE_COLLECTION_STATUS="0" DB_UPDATED_TIME="1775459194144" />
  <CollectionVersion COLLECTION_ID="UVH@1553365474" VERSION="1775459194" TARGET_VERSION="1775459194" RESET_VERSION="1775459194" />
  <CollectionRWStatus COLLECTION_ID="UVH@1553365474" IS_REPWINDOW_ENABLED="false" />
  <CollSchExecution COLLECTION_ID="UVH@1553365474" SCHEDULE_ENABLE="1" SCHEDULE_TIME="-1" EXECUTION_OPTION="3" />
 </Rows>
</WritableDataObject>
, isTools=false, deploymentType=0, isInsAfterEnabled=false, rebootTimeOut=5, CONFIG_TYPE=computer, deadlineSettings={forceRebootOption=0, enableDeadline=false}, filterDOList=[[Ljava.lang.Object;@e12d1a2], configDOList=[[Ljava.lang.Object;@4aff10c1], expiryTime=, isPatchConfig=true, isTargetBasedConfig=false, operationType=6, forceDownload=true, IS_REPWINDOW_ENABLED=false}|
[15:06:34:144]|[04-06-2026]|[ConfigLogger]|[INFO]|[337]|[863701b7-8e71-4e3c-bd5e-15232909f733]: persistCollection: Begining a transaction for collection addition...|
[15:06:34:164]|[04-06-2026]|[ConfigLogger]|[INFO]|[337]|[863701b7-8e71-4e3c-bd5e-15232909f733]: Transaction is commited successfully for Collection with collectionID 1,205|
[15:06:34:166]|[04-06-2026]|[ConfigLogger]|[INFO]|[337]|[863701b7-8e71-4e3c-bd5e-15232909f733]: Collection staus updated as draft for configuration with collectionID :1,205|
[15:06:34:233]|[04-06-2026]|[ConfigLogger]|[INFO]|[337]|[863701b7-8e71-4e3c-bd5e-15232909f733]: Configuration has been persisted with :: Collection ID : 1205 collectionName : Patch Deploy Test 06042026_002|

```

