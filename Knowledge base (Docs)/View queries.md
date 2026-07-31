

# APD list view query
```sql
select
	distinct OSPLATFORMTYPE.OS_PLATFORM_NAME as "OSPLATFORMTYPE.OS_PLATFORM_NAME",
	OSPLATFORMTYPE.OS_PLATFORM_ID as "OSPLATFORMTYPE.OS_PLATFORM_ID",
	ApdTasks.TASK_ID as "ApdTasks.TASK_ID" ,
	TASKTOCOLLECTION.COLLECTION_ID as "TASKTOCOLLECTION.COLLECTION_ID",
	TaskDetails.TASKNAME as "TaskDetails.TASKNAME",
	TaskDetails.TYPE as "TaskDetails.TYPE",
	TaskDetails.CREATIONTIME as "TaskDetails.CREATIONTIME",
	TaskDetails.MODIFIEDTIME as "TaskDetails.MODIFIEDTIME",
	ScheduledTaskDetails.SCHEDULER_CLASS_ID as "ScheduledTaskDetails.SCHEDULER_CLASS_ID",
	(case
		when q1.TEMPLATE_ID1 is null then q2.TEMPLATE_ID2
		else q1.TEMPLATE_ID1
	end) as "TEMPLATE_ID",
	(case
		when q4.LABEL is null then cast(q3.COLLECTION_ID as VARCHAR(50))
		else q4.LABEL
	end) as "REMARKS",
	CREATEDUSER.FIRST_NAME as "CREATEDUSER.FIRST_NAME",
	CREATEDUSER.USER_ID as "CREATEDUSER.USER_ID",
	MODIFIEDUSER.FIRST_NAME as "MODIFIEDUSER.FIRST_NAME",
	(case
		when q6.TOTAL_TARGET1 is null then q7.TOTAL_TARGET2
		else q6.TOTAL_TARGET1
	end) as "TOTAL_TARGET",
	CollectionStatus.STATUS as "CollectionStatus.STATUS"
from
	ApdTasks
inner join TaskDetails on
	ApdTasks.TASK_ID = TaskDetails.TASK_ID
inner join OSPLATFORMTYPE on
	ApdTasks.PLATFORM_ID = OSPLATFORMTYPE.OS_PLATFORM_ID
inner join TaskToUserRel on
	ApdTasks.TASK_ID = TaskToUserRel.TASK_ID
inner join AAAUSER CREATEDUSER on
	TaskToUserRel.USER_ID = CREATEDUSER.USER_ID
inner join AAAUSER MODIFIEDUSER on
	TaskToUserRel.LAST_MODIFIED_BY = MODIFIEDUSER.USER_ID
inner join TASKTOCUSTOMERREL on
	ApdTasks.TASK_ID = TASKTOCUSTOMERREL.TASK_ID
left join TASKTOCOLLECTION on
	ApdTasks.TASK_ID = TASKTOCOLLECTION.TASK_ID
left join CollectionStatus on
	TASKTOCOLLECTION.COLLECTION_ID = CollectionStatus.COLLECTION_ID
left join ScheduledTaskDetails on
	TaskDetails.TASK_ID = ScheduledTaskDetails.TASK_ID
left join (
	select
		TASKTOCOLLECTION.TASK_ID,
		DEPLOYMENTTEMPLATES.TEMPLATE_ID as TEMPLATE_ID1
	from
		TASKTOCOLLECTION
	inner join COLLNTODEPLOYTEMPLATE on
		TASKTOCOLLECTION.COLLECTION_ID = COLLNTODEPLOYTEMPLATE.COLLECTION_ID
	inner join DEPLOYMENTTEMPLATES on
		COLLNTODEPLOYTEMPLATE.TEMPLATE_ID = DEPLOYMENTTEMPLATES.TEMPLATE_ID)q1 on
	ApdTasks.TASK_ID = q1.TASK_ID
left join (
	select
		APDTASKTODEPLOYTEMPLATE.TASK_ID,
		DEPLOYMENTTEMPLATES.TEMPLATE_ID as TEMPLATE_ID2
	from
		APDTASKTODEPLOYTEMPLATE
	inner join DEPLOYMENTTEMPLATES on
		APDTASKTODEPLOYTEMPLATE.TEMPLATE_ID = DEPLOYMENTTEMPLATES.TEMPLATE_ID)q2 on
	ApdTasks.TASK_ID = q2.TASK_ID
	and TaskDetails.TYPE in (9, 10, 16)
left join (
	select
		TASK_ID,
		COLLECTION_ID
	from
		TASKTOCOLLECTION)q3 on
	ApdTasks.TASK_ID = q3.TASK_ID
left join(select TASKEXECUTIONDETAILS.TASK_ID, CONFIGSTATUSDEFN.LABEL from TASKEXECUTIONDETAILS inner join CONFIGSTATUSDEFN on TASKEXECUTIONDETAILS.LAST_RESULT_ID = CONFIGSTATUSDEFN.STATUS_ID)q4 on
	ApdTasks.TASK_ID = q4.TASK_ID
left join (
	select
		ApdTasks.TASK_ID,
		COUNT(CollnToResources.RESOURCE_ID) TOTAL_TARGET1
	from
		ApdTasks
	inner join UpdatedTaskHistory on
		ApdTasks.TASK_ID = UpdatedTaskHistory.TASK_ID
	inner join ApdScanCollHistory on
		UpdatedTaskHistory.TASK_HISTORY_ID = ApdScanCollHistory.TASK_HISTORY_ID
	inner join COLLECTION on
		ApdScanCollHistory.SCAN_COLL_ID = Collection.COLLECTION_ID
	left join CollnToResources on
		Collection.COLLECTION_ID = CollnToResources.COLLECTION_ID
	left join ManagedComputer on
		CollntoResources.RESOURCE_ID = ManagedComputer.RESOURCE_ID
	where
		ManagedComputer.MANAGED_STATUS = 61
	group by
		ApdTasks.TASK_ID)q6 on
	ApdTasks.TASK_ID = q6.TASK_ID
left join (
	select
		ctr.COLLECTION_ID,
		COUNT(ctr.RESOURCE_ID) TOTAL_TARGET2
	from
		CollnToResources ctr
	inner join ManagedComputer on
		ctr.RESOURCE_ID = ManagedComputer.RESOURCE_ID
	where
		ManagedComputer.MANAGED_STATUS = 61
	group by
		ctr.COLLECTION_ID)q7 on
	TASKTOCOLLECTION.COLLECTION_ID = q7.COLLECTION_ID
where
	TASKTOCUSTOMERREL.CUSTOMER_ID = 1
	and (1 = 1)
	and (1 = 1)
```

# Reboot required view query
```sql
select
	ResourceDeploymentStatus.RESOURCE_ID as "ResourceDeploymentStatus.RESOURCE_ID",
	ResourceDeploymentStatus.DEPLOY_STATUS_ID as "ResourceDeploymentStatus.DEPLOY_STATUS_ID",
	Resource.RESOURCE_ID as "Resource.RESOURCE_ID",
	Resource.NAME as "Resource.NAME",
	Resource.DOMAIN_NETBIOS_NAME as "Resource.DOMAIN_NETBIOS_NAME",
	ManagedComputer.RESOURCE_ID as "ManagedComputer.RESOURCE_ID",
	ManagedComputer.AGENT_VERSION as "ManagedComputer.AGENT_VERSION",
	AgentContact.RESOURCE_ID as "AgentContact.RESOURCE_ID",
	AgentContact.LAST_CONTACT_TIME as "AgentContact.LAST_CONTACT_TIME",
	PatchMgmtOSInfo.RESOURCE_ID as "PatchMgmtOSInfo.RESOURCE_ID",
	PatchMgmtOSInfo.OS_NAME as "PatchMgmtOSInfo.OS_NAME",
	PatchMgmtOSInfo.SERVICE_PACK as "PatchMgmtOSInfo.SERVICE_PACK",
	PatchClientScanStatus.RESOURCE_ID as "PatchClientScanStatus.RESOURCE_ID",
	PatchClientScanStatus.LAST_SCAN_TIME as "PatchClientScanStatus.LAST_SCAN_TIME",
	BranchMemberResourceRel.RESOURCE_ID as "BranchMemberResourceRel.RESOURCE_ID",
	BranchMemberResourceRel.BRANCH_OFFICE_ID as "BranchMemberResourceRel.BRANCH_OFFICE_ID",
	BranchOfficeDetails.BRANCH_OFFICE_NAME as "BranchOfficeDetails.BRANCH_OFFICE_NAME",
	OSLanguage.LANGUAGEID as "OSLanguage.LANGUAGEID",
	OSLanguage.I18N as "OSLanguage.I18N",
	OSLanguage.ABBREVIATION as "OSLanguage.ABBREVIATION",
	PMResHealthStatus.RESOURCE_ID as "PMResHealthStatus.RESOURCE_ID",
	PMResHealthStatus.HEALTH_STATUS as "PMResHealthStatus.HEALTH_STATUS",
	ResourceToRebootDetails.RESOURCE_ID as "ResourceToRebootDetails.RESOURCE_ID",
	ResourceToRebootDetails.REBOOT_REQ_STATUS as "ResourceToRebootDetails.REBOOT_REQ_STATUS",
	AgentContact.LAST_BOOTUP_TIME as "AgentContact.LAST_BOOTUP_TIME",
	ResourceMACIP.IP_ADDRESS as "ResourceMACIP.IP_ADDRESS",
	AgentContact.LOGGED_ON_USERS as "AgentContact.LOGGED_ON_USERS",
	ManagedComputerExtn.OWNER as "ManagedComputerExtn.OWNER",
	ResourceLiveStatus.STATUS as "ResourceLiveStatus.STATUS",
	ResourceLiveStatus.STATUS_UPDATE_TIME as "ResourceLiveStatus.STATUS_UPDATE_TIME",
	Computer.OS_PLATFORM as "Computer.OS_PLATFORM",
	CustomerInfo.CUSTOMER_ID as "CustomerInfo.CUSTOMER_ID",
	ManagedComputer.FRIENDLY_NAME as "ManagedComputer.FRIENDLY_NAME",
	CustomerInfo.CUSTOMER_NAME as "CustomerInfo.CUSTOMER_NAME",
	ResourceToRebootDetails.REBOOT_REQ_REASON as "ResourceToRebootDetails.REBOOT_REQ_REASON",
	AgentContact.LAST_DS_CONTACT_TIME as "AgentContact.LAST_DS_CONTACT_TIME",
	ManagedComputerExtn.LOCATION as "ManagedComputerExtn.LOCATION",
	ManagedComputerExtn.SEARCH_TAG as "ManagedComputerExtn.SEARCH_TAG",
	ManagedComputerExtn.DESCRIPTION as "ManagedComputerExtn.DESCRIPTION",
	ManagedComputerExtn.OWNER_EMAIL_ID as "ManagedComputerExtn.OWNER_EMAIL_ID",
	ResourceDeploymentStatus.LAST_PATCHED_TIME as "ResourceDeploymentStatus.LAST_PATCHED_TIME",
	PatchRebootPendingInfo.COLLECTION_ID as "PatchRebootPendingInfo.COLLECTION_ID",
	PatchRebootPendingInfo.UPCOMING_FORCE_REBOOT_TIME as "PatchRebootPendingInfo.UPCOMING_FORCE_REBOOT_TIME",
	PatchRebootPendingInfo.REBOOT_PENDING_UPDATED_TIME as "PatchRebootPendingInfo.REBOOT_PENDING_UPDATED_TIME",
	PatchRebootPendingInfo.REBOOT_PENDING_REASON as "PatchRebootPendingInfo.REBOOT_PENDING_REASON",
	PatchRebootPendingInfo.TASK_TYPE as "PatchRebootPendingInfo.TASK_TYPE",
	Collection.COLLECTION_NAME as "Collection.COLLECTION_NAME",
	CollnToDeployTemplate.TEMPLATE_ID as "CollnToDeployTemplate.TEMPLATE_ID",
	DeploymentTemplates.TEMPLATE_NAME as "DeploymentTemplates.TEMPLATE_NAME",
	Computer.TIMEZONE_OFFSET as "Computer.TIMEZONE_OFFSET",
	TaskToCollection.TASK_ID as "TaskToCollection.TASK_ID",
	Collection.COLLECTION_ID as "Collection.COLLECTION_ID",
	Collection.IS_DELETED as "Collection.IS_DELETED",
	ResourceMACIP.MAC_ADDRESS as "ResourceMACIP.MAC_ADDRESS",
	ManagedComputerCustomFields.COL1 as "ManagedComputerCustomFields.COL1",
	ManagedComputerCustomFields.COL2 as "ManagedComputerCustomFields.COL2",
	ManagedComputerCustomFields.COL301 as "ManagedComputerCustomFields.COL301",
	Computer.PROCESSOR_ARCHITECTURE as "Computer.PROCESSOR_ARCHITECTURE"
from
	ResourceDeploymentStatus
inner join Resource on
	ResourceDeploymentStatus.RESOURCE_ID = Resource.RESOURCE_ID
inner join ManagedComputer on
	Resource.RESOURCE_ID = ManagedComputer.RESOURCE_ID
left join AgentContact on
	ManagedComputer.RESOURCE_ID = AgentContact.RESOURCE_ID
inner join PatchMgmtOSInfo on
	ManagedComputer.RESOURCE_ID = PatchMgmtOSInfo.RESOURCE_ID
inner join OSLanguage on
	PatchMgmtOSInfo.LANGUAGEID = OSLanguage.LANGUAGEID
left join PatchClientScanStatus on
	ManagedComputer.RESOURCE_ID = PatchClientScanStatus.RESOURCE_ID
left join BranchMemberResourceRel on
	ManagedComputer.RESOURCE_ID = BranchMemberResourceRel.RESOURCE_ID
left join BranchOfficeDetails on
	BranchMemberResourceRel.BRANCH_OFFICE_ID = BranchOfficeDetails.BRANCH_OFFICE_ID
left join PMResHealthStatus on
	ManagedComputer.RESOURCE_ID = PMResHealthStatus.RESOURCE_ID
left join ResourceMACIP on
	ManagedComputer.RESOURCE_ID = ResourceMACIP.RESOURCE_ID
left join ManagedComputerExtn on
	ManagedComputer.RESOURCE_ID = ManagedComputerExtn.RESOURCE_ID
left join PatchRebootPendingInfo on
	ManagedComputer.RESOURCE_ID = PatchRebootPendingInfo.RESOURCE_ID
left join Collection on
	PatchRebootPendingInfo.COLLECTION_ID = Collection.COLLECTION_ID
left join CollnToDeployTemplate on
	Collection.COLLECTION_ID = CollnToDeployTemplate.COLLECTION_ID
left join DeploymentTemplates on
	CollnToDeployTemplate.TEMPLATE_ID = DeploymentTemplates.TEMPLATE_ID
left join TaskToCollection on
	Collection.COLLECTION_ID = TaskToCollection.COLLECTION_ID
left join ManagedComputerCustomFields on
	ManagedComputer.RESOURCE_ID = ManagedComputerCustomFields.RESOURCE_ID
left join ResourceToRebootDetails on
	Resource.RESOURCE_ID = ResourceToRebootDetails.RESOURCE_ID
left join ResourceLiveStatus on
	Resource.RESOURCE_ID = ResourceLiveStatus.RESOURCE_ID
inner join Computer on
	Resource.RESOURCE_ID = Computer.RESOURCE_ID
inner join OSPlatformType on
	Computer.OS_PLATFORM = OSPlatformType.OS_PLATFORM_ID
inner join CustomerInfo on
	Resource.CUSTOMER_ID = CustomerInfo.CUSTOMER_ID
where
	( ( ResourceToRebootDetails.REBOOT_REQ_STATUS = true )
		and ( ManagedComputer.MANAGED_STATUS = 61 ) )
```