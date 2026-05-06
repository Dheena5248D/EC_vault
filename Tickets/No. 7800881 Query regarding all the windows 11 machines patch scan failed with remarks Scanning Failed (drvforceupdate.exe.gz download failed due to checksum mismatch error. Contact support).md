---
notion_id: "34443c23-a5e2-80f7-baea-e915743c9912"
notion_last_edited: "2026-04-16T14:27:00.000Z"
tags:
resolved: "False"
problem tags:
Solved by: "ME"
Date: "2026-04-16"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003574416384"
---

# Issue:

Query regarding all the windows 11 machines patch scan failed with remarks: Scanning Failed (drvforceupdate.exe.gz download failed due to checksum mismatch error. Contact support)



# Analysis:

On analysing the log it seems like the drvforceupdate.exe.gz file is downloaded on old schema but checksum validation return success on the server from the CRS and the file is downloaded by the agent and checksum mismatch is caught by the agent

[Chris Kavin Romero Romanus](https://medcsupport.zohodesk.com/agent/medcsupport/all/setup#setup/users-control/agents/220709002781485591) , kindly take care as discussed.

# Log traces:

```prolog
BUILD NUMBER 				 STARTED AT 					 SHUTDOWN AT 					 UP TIME 
==================================================================================================================
115260513 				 apr 15,2026 12:51:07 AM 		 -- 		 --
115260513 				 apr 15,2026 12:45:22 AM 		 -- 		 --
115260513 				 apr 04,2026 04:27:35 PM 		 -- 		 --
115260513 				 apr 04,2026 04:21:50 PM 		 apr 04,2026 04:24:17 PM 		 2 minutes
115260026 				 apr 04,2026 12:15:28 PM 		 apr 04,2026 03:43:40 PM 		 3 hours, 28 minutes
114252203 				 apr 03,2026 09:53:46 PM 		 apr 04,2026 11:27:06 AM 		 13 hours, 33 minutes



[14:07:58:659]|[04-04-2026]|[CRSLogger]|[INFO]|[386]|[SERVER-46ff21b0-b3df-47b3-8218-22cb884e87d4]: Generated Local metadata-version.xml in the path : ..\conf\CRSData\dc-crs\metadata-version.xml|
[14:07:58:659]|[04-04-2026]|[CRSLogger]|[INFO]|[386]|[SERVER-46ff21b0-b3df-47b3-8218-22cb884e87d4]: CrawlerParams:Parameter updated in DB:- param name patchDBUpdateStat and param value success: |
[14:07:58:668]|[04-04-2026]|[CRSLogger]|[INFO]|[386]|[SERVER-46ff21b0-b3df-47b3-8218-22cb884e87d4]: CrawlerParams:Parameter updated in DB:- param name patchDBStatMsg and param value Sincronizzato correttamente: |
[14:07:58:676]|[04-04-2026]|[CRSLogger]|[INFO]|[386]|[SERVER-46ff21b0-b3df-47b3-8218-22cb884e87d4]: CrawlerParams:Parameter updated in DB:- param name patchDBMsgConstant and param value 1100: |
[14:07:58:678]|[04-04-2026]|[CRSLogger]|[INFO]|[386]|[SERVER-46ff21b0-b3df-47b3-8218-22cb884e87d4]: Checking CRSUpdates for moduleKeyName : drvforceupdate|
[14:07:58:683]|[04-04-2026]|[CRSLogger]|[INFO]|[386]|[SERVER-46ff21b0-b3df-47b3-8218-22cb884e87d4]: --- Schema Check (Local schema version : 1.4 )|
[14:07:58:693]|[04-04-2026]|[CRSLogger]|[INFO]|[386]|[SERVER-46ff21b0-b3df-47b3-8218-22cb884e87d4]: Going to compare data : <WritableDataObject>
 <Tables>
[CRSMetaData] </Tables>
 <JoinsInDO>
 </JoinsInDO>
 <Operations>
  <INSERT><CRSMetaData_PK CRS_META_DATA_ID="289"/></INSERT>
 </Operations>
 <Rows>
  <CRSMetaData CRS_META_DATA_ID="289" CRS_META_DATA_KEY="drvforceupdate" CRS_META_DATA_VERSION="1761636249000" SCHEMA_VERSION="1.4" CRS_META_DATA_FILE_NAME="drvforceupdate.xml" CRS_META_DATA_FILE_PATH="dc-crs/definitiondata/1.4/" CHECKSUM="ed4ea311dd3e0794a7ccc8e6b3cbea69d85cbf719e4b40d1b5e93675f579e6cd" CHECKSUM_TYPE="SHA256" />
 </Rows>
</WritableDataObject>
|
[14:07:58:693]|[04-04-2026]|[CRSLogger]|[INFO]|[386]|[SERVER-46ff21b0-b3df-47b3-8218-22cb884e87d4]: Schema versions Local Version : 1.4 & downlaoded Version : 1.4|
[14:07:58:693]|[04-04-2026]|[CRSLogger]|[INFO]|[386]|[SERVER-46ff21b0-b3df-47b3-8218-22cb884e87d4]: Schema versions are same, continue...|
[14:07:58:693]|[04-04-2026]|[CRSLogger]|[INFO]|[386]|[SERVER-46ff21b0-b3df-47b3-8218-22cb884e87d4]: --- MetaData Check (Local metadata version : -1 )|
[14:07:58:693]|[04-04-2026]|[CRSLogger]|[INFO]|[386]|[SERVER-46ff21b0-b3df-47b3-8218-22cb884e87d4]: Metadata version changed Local Version : -1 & downlaoded Version : 1761636249000|
[14:07:58:693]|[04-04-2026]|[CRSLogger]|[INFO]|[386]|[SERVER-46ff21b0-b3df-47b3-8218-22cb884e87d4]: relLocation : dc-crs/definitiondata/1.4//drvforceupdate.xml|
[14:07:58:693]|[04-04-2026]|[CRSLogger]|[INFO]|[386]|[SERVER-46ff21b0-b3df-47b3-8218-22cb884e87d4]: --- Going to find Defenition Diff...|
[14:07:58:693]|[04-04-2026]|[CRSLogger]|[INFO]|[386]|[SERVER-46ff21b0-b3df-47b3-8218-22cb884e87d4]: file exist on the path : ..\conf\CRSData\PatchDBUpdate\dc-crs\definitiondata\1.4\\drvforceupdate.xml|
[14:07:58:693]|[04-04-2026]|[CRSLogger]|[SEVERE]|[386]|[SERVER-46ff21b0-b3df-47b3-8218-22cb884e87d4]: Validating Checksum | File: ..\conf\CRSData\PatchDBUpdate\dc-crs\definitiondata\1.4\\drvforceupdate.xml | Expected Checksum: ed4ea311dd3e0794a7ccc8e6b3cbea69d85cbf719e4b40d1b5e93675f579e6cd | Type: SHA256|
[14:07:58:701]|[04-04-2026]|[CRSLogger]|[INFO]|[386]|[SERVER-46ff21b0-b3df-47b3-8218-22cb884e87d4]: copy file status success for the path : ..\conf\CRSData\\patch-temp-data\dc-crs\definitiondata\1.4\\drvforceupdate.xml|
[14:07:58:705]|[04-04-2026]|[CRSLogger]|[INFO]|[386]|[SERVER-46ff21b0-b3df-47b3-8218-22cb884e87d4]: --- Copying Module related xmls/sqls...|
[14:07:58:707]|[04-04-2026]|[CRSLogger]|[INFO]|[386]|[SERVER-46ff21b0-b3df-47b3-8218-22cb884e87d4]: file exist on the path : ..\conf\CRSData\PatchDBUpdate\\dc-crs\definitiondata\1.4\patchdata\1.2\drvforceupdate.exe.gz|
[14:07:58:707]|[04-04-2026]|[CRSLogger]|[SEVERE]|[386]|[SERVER-46ff21b0-b3df-47b3-8218-22cb884e87d4]: Validating Checksum | File: ..\conf\CRSData\PatchDBUpdate\\dc-crs\definitiondata\1.4\patchdata\1.2\drvforceupdate.exe.gz | Expected Checksum: 76bb3afb0c8746b57f118fdc4ea24c7daa04ab6bbe364650f359de24cc31ff4c | Type: SHA256|
[14:07:58:739]|[04-04-2026]|[CRSLogger]|[INFO]|[386]|[SERVER-46ff21b0-b3df-47b3-8218-22cb884e87d4]: copy file status success for the path : ..\conf\CRSData\\patch-temp-data\\dc-crs\definitiondata\1.4\patchdata\1.2\drvforceupdate.exe.gz|
[14:07:58:741]|[04-04-2026]|[CRSLogger]|[INFO]|[386]|[SERVER-46ff21b0-b3df-47b3-8218-22cb884e87d4]: Copied file : ..\conf\CRSData\\patch-temp-data\\dc-crs\definitiondata\1.4\patchdata\1.2\drvforceupdate.exe.gz|
[14:07:58:741]|[04-04-2026]|[CRSLogger]|[INFO]|[386]|[SERVER-46ff21b0-b3df-47b3-8218-22cb884e87d4]: Checking for any file removal...|
[14:07:58:741]|[04-04-2026]|[CRSLogger]|[INFO]|[386]|[SERVER-46ff21b0-b3df-47b3-8218-22cb884e87d4]: Updating definition data : <WritableDataObject>
 <Tables>
[DefinitionMetaData] </Tables>
 <JoinsInDO>
 </JoinsInDO>
 <Operations>
  <UPDATE><DefinitionMetaData_PK DEFINITION_ID="3124"/></UPDATE>
 </Operations>
 <Rows>
  <DefinitionMetaData DEFINITION_ID="3124" DEFINITION_TYPE="78" DEFINITION_NAME="drvforceupdate" DEFINITION_VERSION="1761636249000" DEFINITION_FILE_NAME="drvforceupdate.exe.gz" DEFINITION_FILE_PATH="/dc-crs/definitiondata/1.4/patchdata/1.2" CUMULATIVE_BASE_VERSION="-1" IS_DIFF_SQL="false" CHECKSUM="76bb3afb0c8746b57f118fdc4ea24c7daa04ab6bbe364650f359de24cc31ff4c" CHECKSUM_TYPE="SHA256" />
 </Rows>
</WritableDataObject>
|
```

