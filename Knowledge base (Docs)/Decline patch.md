# declined patch / product to all managed computers
If a patch/ product declined to all managed computers then that specific patch will be removed from [[Tables#Affectedpatchstatus]] and will be moved to [[Tables#DeclinedAffectedpatchstatus]]

## scenarios
1. If a patch is declined while a patch scan in progress in the agent then,
	1. the patch will be declined and removed from table affectedpatchstatus
	2.  the scan results updates the affectedpatchstatus table
	3. [This scenario will be fixed in next patch scan as the agent will post the scan results to remove the patch from the affected patch status and to add in declined patch status ]
	4. ref ticket: https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003833348227
