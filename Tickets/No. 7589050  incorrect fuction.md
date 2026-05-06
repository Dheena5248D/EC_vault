---
notion_id: "33443c23-a5e2-80a2-8204-e3785496bb7b"
notion_last_edited: "2026-03-31T11:03:00.000Z"
tags:
resolved: "False"
problem tags:
Date: "2026-03-31"
---

# Issue:

Windows 11 feature pack deployment failing with remark "incorrect fuction"  

# Analysis:



# Log traces:

```javascript
[ 2026-03-25 13:50:02:751 ] [ 12440 ] [INFO] 	 The execution fileWithSwitch for Patch Install 112729-windows11-25H2-prereq-handler_x64_en.exe -i 112733-Win11_25H2_enx64.iso -e setup.exe -s "/auto upgrade /DynamicUpdate enable /ShowOOBE none /quiet /noreboot /compat IgnoreWarning /EULA accept /BitLocker TryKeepActive" -v 10.0.26200 -w 
[ 2026-03-25 13:50:02:751 ] [ 12440 ] [INFO] installPatch : installation directory : C:\Program Files (x86)\ManageEngine\UEMS_Agent\\patches  
[ 2026-03-25 13:50:02:751 ] [ 12440 ] [INFO] installPatch : installationFileName : 112729-windows11-25H2-prereq-handler_x64_en.exe  
[ 2026-03-25 13:50:02:751 ] [ 12440 ] [INFO] Message : The operation completed successfully.  
[ 2026-03-25 13:50:02:751 ] [ 12440 ] [INFO] GetTimeInSeconds : Time in Second : 1774426802
[ 2026-03-25 13:50:02:751 ] [ 12440 ] [INFO] executeFileEx : Current Working Directory : C:\Program Files (x86)\ManageEngine\UEMS_Agent 
[ 2026-03-25 13:50:02:751 ] [ 12440 ] [INFO] executeFileEx : Executing Application Source : 112729-windows11-25H2-prereq-handler_x64_en.exe -i 112733-Win11_25H2_enx64.iso -e setup.exe -s "/auto upgrade /DynamicUpdate enable /ShowOOBE none /quiet /noreboot /compat IgnoreWarning /EULA accept /BitLocker TryKeepActive" -v 10.0.26200 -w 
[ 2026-03-25 13:50:02:751 ] [ 12440 ] [INFO] executeFileEx : Set Working Directory : C:\Program Files (x86)\ManageEngine\UEMS_Agent\\patches 
[ 2026-03-25 13:50:02:766 ] [ 12440 ] [INFO] execute : Process successfully created for application 112729-windows11-25H2-prereq-handler_x64_en.exe -i 112733-Win11_25H2_enx64.iso -e setup.exe -s "/auto upgrade /DynamicUpdate enable /ShowOOBE none /quiet /noreboot /compat IgnoreWarning /EULA accept /BitLocker TryKeepActive" -v 10.0.26200 -w 
[ 2026-03-25 13:50:03:049 ] [ 12440 ] [ERROR] Error Code : 1 , Error Message : Incorrect function.  
[ 2026-03-25 13:50:03:049 ] [ 12440 ] [INFO] executeFileEx : Exit code for the application : 1 
[ 2026-03-25 13:50:03:049 ] [ 12440 ] [INFO] executeFileEx : Remarks from the CreateProcess is Incorrect function.  for the executable 112729-windows11-25H2-prereq-handler_x64_en.exe -i 112733-Win11_25H2_enx64.iso -e setup.exe -s "/auto upgrade /DynamicUpdate enable /ShowOOBE none /quiet /noreboot /compat IgnoreWarning /EULA accept /BitLocker TryKeepActive" -v 10.0.26200 -w 
[ 2026-03-25 13:50:03:049 ] [ 12440 ] [INFO] deleteValue:  Key found ...!: 0
[ 2026-03-25 13:50:03:049 ] [ 12440 ] [INFO] deleteValue:  Delete value DCCreateProcessStatus success! 
[ 2026-03-25 13:50:03:049 ] [ 12440 ] [INFO] productid : 1766 patchId: 112729
[ 2026-03-25 13:50:03:049 ] [ 12440 ] [INFO] productid : 1820 patchId: 112729
[ 2026-03-25 13:50:03:049 ] [ 12440 ] [INFO] productid : 1874 patchId: 112729
[ 2026-03-25 13:50:03:049 ] [ 12440 ] [INFO] productid : 1939 patchId: 112729
[ 2026-03-25 13:50:03:049 ] [ 12440 ] [INFO] productid : 2058 patchId: 112729
[ 2026-03-25 13:50:03:049 ] [ 12440 ] [INFO] Inside GetFamilyIdForPatchId Method
[ 2026-03-25 13:50:03:049 ] [ 12440 ] [INFO] [driverupdates][GET_PRD_FOR_PATCH] => More than 1 product in table. trying to get from last driver scan results
[ 2026-03-25 13:50:03:049 ] [ 12440 ] [INFO] FamilyId : 412
[ 2026-03-25 13:50:03:049 ] [ 12440 ] [INFO] *** Inside GetEPMErrorId method *** 
[ 2026-03-25 13:50:03:049 ] [ 12440 ] [INFO] FamilyId : 412
[ 2026-03-25 13:50:03:049 ] [ 12440 ] [INFO] Data Not Found With FamilyId
[ 2026-03-25 13:50:03:049 ] [ 12440 ] [INFO] Error ID : 4 and reamarks : [i18n]Incorrect Function[/i18n] from EPMErrorCodes.
[ 2026-03-25 13:50:03:064 ] [ 12440 ] [INFO] *** GetEPMErrorId returned with : 4 
[ 2026-03-25 13:50:03:064 ] [ 12440 ] [INFO] 	 Error Occured while installing the Patch 112729-windows11-25H2-prereq-handler_x64_en.exe  due to [i18n]Incorrect Function[/i18n] 
```

