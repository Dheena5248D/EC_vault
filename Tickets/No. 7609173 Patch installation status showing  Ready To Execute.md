---
notion_id: "32443c23-a5e2-8013-a338-d74639cbd1d7"
notion_last_edited: "2026-03-16T12:42:00.000Z"
tags:
  - "APD"
  - "patch-deployment"
resolved: "False"
problem tags:
  - "collection struck at ready to execute"
Date: "2026-03-16"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003465674552"
---

# Problem:

The cx states that the collection is struck at ready to execute even tough the dep policy to apply anytime at earliest



# Analysis:

The filter.xml is cannot be downloaded from the DS since the DS logs are rotated we can’t determine the root cause.

# Log traces:



```javascript
 26-03-05	   Refresh	    SYSTEM	10.13.235.98_PatchPushByAnsible_2026-03-0438595	88876	  05:38:51	       No Filter xml	  05:38:52
```



```javascript
  <CollectionRetry COLLECTION_ID="UVH@2100733621" ENABLE_RETRY="true" NO_OF_RETRIES="2" REFRESH_MIN_RETRY="1" LOGON_STARTUP_MIN_RETRY="1" />
  <CollnToCustomerRel COLLECTION_ID="UVH@2100733621" CUSTOMER_ID="1" DB_UPDATED_TIME="1772643963998" />
  <Collection COLLECTION_ID="UVH@2100733621" COLLECTION_NAME="10.13.235.98_PatchPushByAnsible_2026-03-0438595" DESCRIPTION="deploy patch through ansible playbook" CREATION_TIME="1772643963998" MODIFIED_TIME="1772643963998" IS_SINGLE_CONFIG="true" COLLECTION_TYPE="1" APPLY_TYPE="1" IS_CONFIG_COLLECTION="true" PLATFORM_ID="1" IS_DELETED="false" COLLECTION_STATE="0" SHOW_IN_VIEW="true" DB_UPDATED_TIME="1772643963998" />
  <CollnActivePeriod COLLECTION_ID="UVH@2100733621" START_TIME="-1" END_TIME="-1" />
  <CollectionStatus COLLECTION_ID="UVH@2100733621" STATUS="13" IS_STATUS_COMPUTABLE="true" PROFILE_COLLECTION_STATUS="0" DB_UPDATED_TIME="1772643964013" />
  <CollectionVersion COLLECTION_ID="UVH@2100733621" VERSION="1772643963" TARGET_VERSION="1772643963" RESET_VERSION="1772643963" />
  <CollectionRWStatus COLLECTION_ID="UVH@2100733621" IS_REPWINDOW_ENABLED="true" />
  <CollSchExecution COLLECTION_ID="UVH@2100733621" SCHEDULE_ENABLE="1" SCHEDULE_TIME="-1" EXECUTION_OPTION="3" />
 </Rows>
</WritableDataObject>
, forceDownload=false, skipCollection=0, isTemplateClone=false, isInsAfterEnabled=false, deploymentType=0, userName=ansible_prod, expiryTime=, CONFIG_TYPE=Computer, isPatchUninstallConfig=false, filterDOList=[[Ljava.lang.Object;@661548db], skipScheduleDate=, expiryDate=, skipCollTime=0, userID=2101, continueDeployment=1, operationType=6, isSPConfig=false, skipShceduleTime=, isModified=false, ConfigPackageSize=0, rebootMessage=, clonedConfig=false, isUSBConfig=false, isTargetBasedConfig=false, isTools=false, rebootValue=0, skipTillTime=-1, isExpiryEnabled=false, windowStartTime=00:00:00}|
[22:36:04:013]|[03-04-2026]|[ConfigLogger]|[INFO]|[25252]|[bda6fbe7-5926-4353-9356-d440d6679278]: persistCollection: Begining a transaction for collection addition...|
[22:36:05:123]|[03-04-2026]|[ConfigLogger]|[INFO]|[25252]|[bda6fbe7-5926-4353-9356-d440d6679278]: Transaction is commited successfully for Collection with collectionID 88,876|
[22:36:05:123]|[03-04-2026]|[ConfigLogger]|[INFO]|[25252]|[bda6fbe7-5926-4353-9356-d440d6679278]: Collection staus updated as draft for configuration with collectionID :88,876|
[22:36:05:154]|[03-04-2026]|[ConfigLogger]|[INFO]|[25252]|[bda6fbe7-5926-4353-9356-d440d6679278]: Configuration has been persisted with :: Collection ID : 88876 collectionName : 10.13.235.98_PatchPushByAnsible_2026-03-0438595
```

