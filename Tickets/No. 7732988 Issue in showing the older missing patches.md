---
notion_id: "33a43c23-a5e2-804c-a084-efc873731d60"
notion_last_edited: "2026-04-06T06:50:00.000Z"
tags:
  - "red_hat"
  - "module_patches"
resolved: "False"
problem tags:
Solved by: "Others"
Date: "2026-04-06"
---

# Issue:

 Issue in showing the older missing patches

# Analysis:

In Redhat we have a concept of module patches, where vendor have grouped packages as module stream. For example, vendor
have released a module  "perl-DBI" vendor have released stream for the same as 1.0, 2.0, 3.0 and so on.

Update for the same modules will be released based on the packages grouped inside and also updates will be released for each stream. Initially we have not supported these module patches,.

Now we have have supported each module updates under each stream as each individual patches. i.e each update for 1.0 stream, 2.0 stream 3.0 stream for the packages are supported and released as each individual patches.



Lets consider a module (for example: perl-DBI) is installed with in a machine with the stream 2.0. Missing patches for the same should be shown for the same stream 2.0. But right now we do not have stream detection installed in the machine,

So our agent will try to compare all the patches which is released latest to the package despite of its stream.

i.e : package perl-DBI 2.0 module package is installed in the machine, our agent will detect missing patches for the same package with all the available stream higher than 2.0 stream installed in the machine. During version check agent will check for the latest patch version against the version installed in the machine.

So during detection 2.0 < 3.0 and 2.0 < 4.0.  Due to this, missing patches will be detected for the same package in all upstream modules.

**Kindly collect the fixes_id.properties file from the following directory:**

UEMS_CentralServer\conf\JarTracker, and also provide a screenshot of the server build number from the server console to proceed with the fix.

# Log traces:



