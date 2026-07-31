


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

