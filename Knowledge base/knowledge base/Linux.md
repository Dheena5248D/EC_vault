---
notion_id: "32443c23-a5e2-809a-8866-e7d86a427798"
notion_last_edited: "2026-03-26T12:15:00.000Z"
created date: "2026-03-16"
---

# What is Linux?

- Linux is a open source OS 
- There are various distributions and flavors in Linux
# Supported by EC

There are various Linux OS that are supported by EC they are classified by their package managers so the workflows can be followed.

## APT based

- Ubuntu
- Debian
- Pardus
## YUM based

- Redhat
- Rocky linux
- Oracle linux
- amazon linux
- Alma Linux
- Cent OS
## Zypper based

- SUSE Linux
# What is package manager tool

- A package manager tool is used to automatically install, upgrade, uninstall, roll back softwares automatically 
- package managers are responsible for dependency resolution 
# patch release

Patches are released by the vendor for each flavor in the flavour respective sites

# Vendor sites where patches released

for debian:[https://lists.debian.org/debian-security-announce/2021/threads.html](https://lists.debian.org/debian-security-announce/2021/threads.html)
for suse:[https://lists.suse.com/pipermail/sle-security-updates/](https://lists.suse.com/pipermail/sle-security-updates/)
for Redhat:[https://access.redhat.com/errata/#/](https://access.redhat.com/errata/#/)
for oracle:[https://oss.oracle.com/pipermail/el-errata/](https://oss.oracle.com/pipermail/el-errata/)
for centos:[https://lists.centos.org/pipermail/centos-announce/](https://lists.centos.org/pipermail/centos-announce/)
for ubuntu:[https://lists.ubuntu.com/archives/ubuntu-security-announce/](https://lists.ubuntu.com/archives/ubuntu-security-announce/)
for Suse 15:[https://lists.suse.com/pipermail/sle-security-updates/](https://lists.suse.com/pipermail/sle-security-updates/)



# Patches in Linux

There are two types of  patches in linux

1. Main patch
1. Dependency patch
The types of patch in linux are

1. security patch
1. non-security patch
1. 3rd-party patches
# Normal Linux workflow

## Overview:

The `sudo apt update` command is used to download and update the meta files in linux 

### what this command does

This goes to `/etc/apt/sources.list.d` and gets the url of compontents where it downloads the meta data files 

```prolog
Types: deb
URIs: http://archive.ubuntu.com/ubuntu/
Suites: noble noble-updates noble-backports
Components: main universe restricted multiverse
Signed-By: /usr/share/keyrings/ubuntu-archive-keyring.gpg
```

After this the packages are downloaded and stored in the directory `var/lib/apt/lists` 

# Workflow in endpoint central:

The ec downloads `GlobalMetaData.xml` and then it downloads offline meta data  xml file eg `ubuntu-offline-meta.xml` 

it writes the `sources-dc.list`

```prolog
2026/03/21 03:48:44.842256 | 1347 | INFO | [[Entered repolistmanagerutils.WriteDCAptSourceList]]
2026/03/21 03:48:44.842261 | 1347 | INFO | [[Running Command : lsb_release [--codename]]]
2026/03/21 03:48:44.854638 | 1347 | INFO | [[Got OS codename : noble]]
2026/03/21 03:48:44.854709 | 1347 | INFO | [[Repo content :]]
2026/03/21 03:48:44.854716 | 1347 | INFO | [[deb https://archive.ubuntu.com/ubuntu/ noble main restricted universe multiverse
deb https://archive.ubuntu.com/ubuntu/ noble-updates main restricted universe multiverse
deb https://security.ubuntu.com/ubuntu noble-security main restricted universe multiverse
]]
2026/03/21 03:48:44.854722 | 1347 | INFO | [[Removing Directory : /etc/apt/sources-dc.list]]
2026/03/21 03:48:44.856206 | 1347 | INFO | [[Trying to Write to File : /etc/apt/sources-dc.list]]
2026/03/21 03:48:44.856364 | 1347 | INFO | [[Finished Writing file : /etc/apt/sources-dc.list]]
2026/03/21 03:48:44.856382 | 1347 | INFO | [[Exiting repolistmanagerutils.WriteDCAptSourceList()]]
2026/03/21 03:48:44.856387 | 1347 | INFO | [[Exiting DcRepoListManagerMain]]
2026/03/21 03:48:44.856392 Ended logging
```

Using the offline meta xml file and the processor architecture and codename  the agent downloads the packages and store it `var/lib/apt/lists-dc`

```prolog
 HEAD Request URL : https://192.168.56.1:8383/client-data/patch-resources/linux/ubuntu/offline-meta/ubuntu_dists_noble_universe_binary-amd64_Packages.gz?ResourceID=901&uniqueValue=--
21-03-2026 03:48:44.892412 | 1196 | INFO  | Headers : CONNECTION -> close, USER-AGENT -> ECAgent/11.5.2605.01.L-1774064924
```

# Patch scan



```prolog
24-03-2026 09:20:16.237381 | 1683 | INFO  | Check ID - Type : 1599335  -  201
24-03-2026 09:20:16.237386 | 1683 | INFO  | Checking OS Name & Version
24-03-2026 09:20:16.237390 | 1683 | INFO  | Expected Architecture : 64
24-03-2026 09:20:16.237396 | 1683 | INFO  | CrtGroupId = 0 : true
24-03-2026 09:20:16.237400 | 1683 | INFO  | Product Applicable : 300225`24-03-2026 09:20:16.237441 | 1683 | INFO  | Assigning OS Product ID : 300225
```



```prolog
24-03-2026 09:20:18.828843 | 1683 | INFO  | Check ID - Type : 395864  -  202
24-03-2026 09:20:18.828849 | 1683 | INFO  | Checking Package Name Contains : gstreamer1.0-x
24-03-2026 09:20:18.828856 | 1683 | INFO  | EXEC COMMAND : dpkg -l *gstreamer1.0-x* 
24-03-2026 09:20:18.843944 | 1683 | INFO  | CrtGroupId = 85 : true
24-03-2026 09:20:18.843976 | 1683 | INFO  | Product Applicable : 300062

2281
24-03-2026 09:20:18.877742 | 1683 | INFO  | Check ID - Type : 395651  -  202
24-03-2026 09:20:18.877850 | 1683 | INFO  | Checking Package Name Contains : curl
24-03-2026 09:20:18.877862 | 1683 | INFO  | EXEC COMMAND : dpkg -l *curl* 
24-03-2026 09:20:18.891072 | 1683 | INFO  | CrtGroupId = 1 : true
24-03-2026 09:20:18.891098 | 1683 | INFO  | Product Applicable : 300056

818
24-03-2026 09:20:14.147556 | 1683 | INFO  | Check ID - Type : 1311925  -  202
24-03-2026 09:20:14.147562 | 1683 | INFO  | Checking Package Name Contains : openjdk-10-source
24-03-2026 09:20:14.147568 | 1683 | INFO  | EXEC COMMAND : dpkg -l *openjdk-10-source* ERROR : exit status 1 
24-03-2026 09:20:14.162217 | 1683 | INFO  | CrtGroupId = 8 : false
```

Loads or downloads the pr-sp files



```prolog
24-03-2026 09:20:18.919787 | 1683 | INFO  | Latest file already available. pr300022-sp300001.xml.gz
24-03-2026 09:20:18.919834 | 1683 | INFO  | Latest file already available. pr300027-sp300001.xml.gz
24-03-2026 09:20:18.919847 | 1683 | INFO  | Latest file already available. pr300020-sp300001.xml.gz
24-03-2026 09:20:18.919857 | 1683 | INFO  | Latest file already available. pr300056-sp300001.xml.gz
24-03-2026 09:20:18.919867 | 1683 | INFO  | Latest file already available. pr300092-sp300001.xml.gz
24-03-2026 09:20:18.919876 | 1683 | INFO  | Latest file already available. pr300055-sp300001.xml.gz
24-03-2026 09:20:18.919887 | 1683 | INFO  | Latest file already available. pr300040-sp300001.xml.gz
```

```javascript
 Setting up package manager script to resolve the dependencies.
 Script Based Dependency Resolution Enabled:  true
```

> [!info]  /usr/local/manageengine/uems_agent/data/patch/product-dep-300225.xml

find what this file is for 
      The 300225 is a product id of Ubuntu 24.04 LTS (x64)

```javascript
24-03-2026 09:20:22.350685 | 1683 | INFO  | Check ID - Type : 1749728  -  204
24-03-2026 09:20:22.350707 | 1683 | INFO  | Checking DEB Package Name (>= Version) : linux-modules-extra-6.8.0-1013-nvidia-lowlatency (>= 6.8.0-1013.14.1)
24-03-2026 09:20:22.350727 | 1683 | INFO  | EXEC COMMAND : dpkg -l linux-modules-extra-6.8.0-1013-nvidia-lowlatency ERROR : exit status 1 
24-03-2026 09:20:22.365406 | 1683 | INFO  | Patch Id : 2009317 Status  : 203 Current PackageVersion :  
24-03-2026 09:20:22.365472 | 1683 | INFO  | APPLICABILITY CHECKED PATCH ID     2011870      Affected Status 1   Affected ProductId 1900010      PRODUCT UNAVAILABLE CrtGroupId 3 : false
24-03-2026 09:20:22.365495 | 1683 | INFO  | APPLICABILITY CHECKED PATCH ID     2011870      Affected Status 1   Affected ProductId 1900011      PRODUCT UNAVAILABLE CrtGroupId 8 : false
24-03-2026 09:20:22.365502 | 1683 | INFO  | APPLICABILITY CHECKED PATCH ID     2011870      Affected Status 1   Affected ProductId 1900012      PRODUCT UNAVAILABLE CrtGroupId 9 : false
24-03-2026 09:20:22.365508 | 1683 | INFO  | APPLICABILITY CHECKED PATCH ID     2011870      Affected Status 1   Affected ProductId 1900013      PRODUCT UNAVAILABLE CrtGroupId 10 : false
24-03-2026 09:20:22.365732 | 1683 | INFO  | APPLICABILITY CHECKED PATCH ID     2011870      Affected Status 1   Affected ProductId 1900014      PRODUCT UNAVAILABLE CrtGroupId 11 : false
24-03-2026 09:20:22.365756 | 1683 | INFO  | APPLICABILITY CHECKED PATCH ID     2011870      Affected Status 1   Affected ProductId 300224       PRODUCT UNAVAILABLE CrtGroupId 1 : false
24-03-2026 09:20:22.365764 | 1683 | INFO  | APPLICABILITY CHECKED PATCH ID     2011870      Affected Status 1   Applicable Product 300225       PRODUCT AVAILABLE   CrtGroupId 0 : true
24-03-2026 09:20:22.365812 | 1683 | INFO  | Is PatchType Applicable :  true Patch Type:  1 Patch Details : {2011870 UNSA-2024-1387 0 1 3 1714329000  1752495 0 2865820 map[1:map[0:[300225] 1:[300224] 2:[1900009] 3:[1900010] 8:[1900011] 9:[1900012] 10:[1900013] 11:[1900014]]] [300001 300001 300001 300001 300001 300001 300001 300001]}
24-03-2026 09:20:22.365840 | 1683 | INFO  | Check ID - Type : 1752495  -  204
```

If the patch is found missing

```javascript
24-03-2026 09:27:01.644672 | 1683 | INFO  | Is PatchType Applicable :  true Patch Type:  2 Patch Details : {4120581 TU-USN-0029 0 2 3 1770057000  100170422 0 100254762 map[1:map[0:[300009]] 2:map[0:[300225]]] [300001 300001]}
24-03-2026 09:27:01.644681 | 1683 | INFO  | Check ID - Type : 100170422  -  204
24-03-2026 09:27:01.644687 | 1683 | INFO  | Checking DEB Package Name (>= Version) : python3-apt (>= 2.7.7ubuntu5.2)
24-03-2026 09:27:01.644694 | 1683 | INFO  | EXEC COMMAND : dpkg -l python3-apt 
24-03-2026 09:27:01.666278 | 1683 | INFO  | Version Comparison Result 2.7.7ubuntu5.1 < 2.7.7ubuntu5.2
24-03-2026 09:27:01.666310 | 1683 | INFO  | Patch Id : 4120581 Status  : 202 Current PackageVersion : 2.7.7ubuntu5.1 
24-03-2026 09:27:01.666323 | 1683 | INFO  | Adding the dependency details for Patch Id : 4120581
24-03-2026 09:27:01.666333 | 1683 | INFO  | EXEC COMMAND : sh -c apt-get -o Dir::Etc::SourceList=/etc/apt/sources-dc.list -o Dir::Etc::SourceParts=/tmp/nulldir -o Dir::State::Lists=/var/lib/apt/lists-dc/ -o Dir::Cache::Archives==/tmp/nulldir -o Acquire::ForceHash=sha256 --print-uris --yes install python3-apt 
24-03-2026 09:27:02.951387 | 1683 | INFO  | Checking Line for Dependencies : 'https://archive.ubuntu.com/ubuntu/pool/main/p/python-apt/python-apt-common_2.7.7ubuntu5.2_all.deb' python-apt-common_2.7.7ubuntu5.2_all.deb 20576 SHA256:f038a5741b69c53fd2fe840d98940058950f623790fc934e3ab43906ec61b3f9

24-03-2026 09:27:02.951459 | 1683 | INFO  | Detail: https://archive.ubuntu.com/ubuntu/pool/main/p/python-apt/python-apt-common_2.7.7ubuntu5.2_all.deb | StartString: '
24-03-2026 09:27:02.951560 | 1683 | INFO  | Detail: f038a5741b69c53fd2fe840d98940058950f623790fc934e3ab43906ec61b3f9 | StartString: SHA256:
24-03-2026 09:27:02.951587 | 1683 | INFO  | Adding Dependency for Patch ID ( 4120581 ) : python-apt-common_2.7.7ubuntu5.2_all.deb
24-03-2026 09:27:02.951600 | 1683 | INFO  | Checking Line for Dependencies : 'https://archive.ubuntu.com/ubuntu/pool/main/p/python-apt/python3-apt_2.7.7ubuntu5.2_amd64.deb' python3-apt_2.7.7ubuntu5.2_amd64.deb 169242 SHA256:2fc6f415b6dd0b61cda90cdf4cbfc5c386a0ccfdce40cc207ef44749822961be

24-03-2026 09:27:02.951639 | 1683 | INFO  | Detail: https://archive.ubuntu.com/ubuntu/pool/main/p/python-apt/python3-apt_2.7.7ubuntu5.2_amd64.deb | StartString: '
```



