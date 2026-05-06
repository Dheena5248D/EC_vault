---
ticket_id: "#7795379"
status: "Done"
date: "2026-04-13"
url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003571237948"
solved_by: "ME"
---

# Issue:
After a patch (that requires a reboot) is deployed, cx is not seeing the delayed reboot notification, even though a delay has been configured in the policy

# Analysis:
On analysing the log the patch 43586 is deployed successfully at 13:32 and the reboot prompt is shown to the user at 13:41 and at 14:07 the user clicked postpone for 15 min and the prompt is again shown on 14:22 and then the user clicked reboot now button on the prompt so the reboot has successfully performed on the system.

# Log traces:
```prolog
26-04-05	59407	Test for reboot 	43586		69007		Install Patch	13:28:45	13:32:50	REBOOT_REQUIRED	[i18n]Reboot Pending[/i18n]
```

```prolog
26-04-05	       Ondemand	  13:28:16	       13:37:04
```

```prolog
26-04-05		14:51:54		Restart		The process C:\\Program Files (x86)\\ManageEngine\\UEMS_Agent\\bin\\dcmsghandler
```

```prolog
26-04-05,1,59407,Test for reboot ,5401,1775385424,1775385425,FORCE_REBOOT,----,----,----,----,REBOOT_DONE
```

```prolog
[ 2026-04-05 13:41:18:308 ] [ 6252 ] [INFO] [got refresh interval]
[ 2026-04-05 13:41:18:308 ] [ 6252 ] [INFO] [Force reboot enabled]
[ 2026-04-05 13:41:18:308 ] [ 6252 ] [INFO] [PromptWindowCallback] => Target Force time : 1775389024, CurrTime : 1775385678
[ 2026-04-05 13:41:18:310 ] [ 6252 ] [INFO] [GetTimeAsString] -> MsgHandlerDateFmt: (null)
[ 2026-04-05 13:41:18:310 ] [ 6252 ] [INFO] MonthText : April
[ 2026-04-05 13:41:18:310 ] [ 6252 ] [INFO] [GetTimeAsString] -> MsgHandlerTimeFmt: 12
[ 2026-04-05 13:41:18:310 ] [ 6252 ] [INFO] [Force reboot enabled text] Your PC will automatically shutdown/reboot at  
[ 2026-04-05 13:41:18:310 ] [ 6252 ] [INFO] [Force reboot enabled time text] :  April 05, 2026 - 02:37 PM
[ 2026-04-05 13:41:18:310 ] [ 6252 ] [INFO] Message : The operation completed successfully.  
[ 2026-04-05 13:41:18:310 ] [ 6252 ] [INFO] [Should set postpone opts]
[ 2026-04-05 13:41:18:310 ] [ 6252 ] [INFO] Added 120 seconds as grace period. Diff for comparison : 3466
[ 2026-04-05 13:41:18:310 ] [ 6252 ] [INFO] Allowed Options based on force reboot after time : [ST] : false, [8H] : false, [6H] : false, [4H] : false, [2H] : false, [1H] : false, [15M] : true
[ 2026-04-05 13:41:18:310 ] [ 6252 ] [INFO] Allowed Options from deployment settings : [ST] : false, [8H] : false, [6H] : false, [4H] : false, [2H] : false, [1H] : true, [15M] : true
[ 2026-04-05 13:41:18:310 ] [ 6252 ] [INFO] Final allowed options : [ST] : false, [8H] : false, [6H] : false, [4H] : false, [2H] : false, [1H] : false, [15M] : true
[ 2026-04-05 13:41:18:310 ] [ 6252 ] [INFO] [SetPostponeOptions] => Param is not empty, : 1
[ 2026-04-05 13:41:18:310 ] [ 6252 ] [INFO] [ret set postpone opts]
[ 2026-04-05 13:41:18:312 ] [ 6252 ] [INFO] WebDialog::PromptWindowCallback : ExitOnForceReb

[ 2026-04-05 14:07:00:263 ] [ 6252 ] [INFO] [PromptWindow] => User Clicked ok btn
[ 2026-04-05 14:07:00:263 ] [ 6252 ] [INFO] [PromptWindow] => User choice was : POSTPONE
[ 2026-04-05 14:07:00:263 ] [ 6252 ] [INFO] [PromptWindowCallback] => JobId for this instance : 1
[ 2026-04-05 14:07:00:263 ] [ 6252 ] [INFO] [PromptWindow] => DND is to be set till :1775388120
[ 2026-04-05 14:07:00:263 ] [ 6252 ] [INFO] GetTimeInSeconds : Time in Second : 1775387220
[ 2026-04-05 14:07:00:263 ] [ 6252 ] [INFO] GetCurrentTimeInSecondsWithDayLightBias : Time in Second : 1775387220
[ 2026-04-05 14:07:00:263 ] [ 6252 ] [INFO] [PromptWindowCallback] => User has NOT configured to restart on logoff
```

```prolog
[ 2026-04-05 14:50:13:386 ] [ 18596 ] [INFO] [ForceReboot] :: User Clicked Shutdown Now button
[ 2026-04-05 14:50:13:386 ] [ 18596 ] [INFO] addorDeleteProcessIDinReg :subKey : SOFTWARE\\AdventNet\\DesktopCentral\\DCAgent\\RebootDialog\\ForceReboot\\3432 action : 2 
[ 2026-04-05 14:50:13:386 ] [ 18596 ] [INFO] deleteRegistryKey:  Key successfull deleted!: 0
[ 2026-04-05 14:50:13:390 ] [ 18596 ] [INFO] [ForceReboot] :: Rebooting the System
[ 2026-04-05 14:50:13:390 ] [ 18596 ] [INFO] 	 @@@@@@@@ Inside RebootSystem Method @@@@@@@@ 
[ 2026-04-05 14:50:13:390 ] [ 18596 ] [INFO] 	 Trying to take backup of Reboot history file for this cycle.
[ 2026-04-05 14:50:13:390 ] [ 18596 ] [INFO] 	 Reboot history backup created 
[ 2026-04-05 14:50:13:390 ] [ 18596 ] [INFO] RebootSystem : Initiated the InitiateSystemShutdown Method 
[ 2026-04-05 14:50:13:412 ] [ 18596 ] [INFO] RebootSystem : Successfully initiated the shutdown / restart .. 
[ 2026-04-05 14:50:13:412 ] [ 18596 ] [INFO] Product code is 1
[ 2026-04-05 14:50:13:421 ] [ 18596 ] [INFO] 	 @@@@@@@@ End of RebootSystem Method @@@@@@@@ 
[ 2026-04-05 14:50:13:421 ] [ 18596 ] [INFO] [WndProc] => Recieved quit message
[ 2026-04-05 14:50:13:421 ] [ 18596 ] [INFO] isAnotherInstanceRunning: subKey : SOFTWARE\\AdventNet\\DesktopCentral\\DCAgent\\RebootDialog\\ForceReboot
[ 2026-04-05 14:50:13:421 ] [ 18596 ] [INFO] isAnotherInstanceRunning: subKey : SOFTWARE\\AdventNet\\DesktopCentral\\DCAgent\\RebootDialog\\PromptReboot
[ 2026-04-05 14:50:13:421 ] [ 18596 ] [INFO] isAnotherInstanceRunning: subKey : SOFTWARE\\AdventNet\\DesktopCentral\\DCAgent\\RebootDialog\\PostponeReboot
[ 2026-04-05 14:50:13:421 ] [ 18596 ] [ERROR] isAnotherInstanceRunning: Error in opening regKeyPath : 4L
[ 2026-04-05 14:50:13:421 ] [ 18596 ] [INFO] [WndProc] => Clearing handlePending Keys
[ 2026-04-05 14:50:13:421 ] [ 18596 ] [INFO] Message : The operation completed successfully.  
[ 2026-04-05 14:50:13:421 ] [ 18596 ] [INFO] Message : The operation completed successfully.  
[ 2026-04-05 14:50:13:421 ] [ 18596 ] [INFO] [WndProc] => Clearing settings
[ 2026-04-05 14:50:13:421 ] [ 18596 ] [INFO] [WndProc] => Reboot initiated, did not write end log
[ 2026-04-05 14:50:13:423 ] [ 18596 ] [INFO] [WndProc] => END MessageHandler
```
