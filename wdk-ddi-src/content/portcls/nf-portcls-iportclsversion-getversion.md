---
UID: NF:portcls.IPortClsVersion.GetVersion
title: IPortClsVersion::GetVersion (portcls.h)
description: The GetVersion method returns the version of the Windows operating system that the driver is running on.
old-location: audio\iportclsversion_getversion.htm
tech.root: audio
ms.assetid: ce1394e5-1d45-4b59-8738-fcb2cbe7cf51
ms.date: 05/08/2018
keywords: ["IPortClsVersion::GetVersion"]
ms.keywords: GetVersion, GetVersion method [Audio Devices], GetVersion method [Audio Devices],IPortClsVersion interface, IPortClsVersion interface [Audio Devices],GetVersion method, IPortClsVersion.GetVersion, IPortClsVersion::GetVersion, audio.iportclsversion_getversion, audmp-routines_82b73b24-296b-4b31-88e4-1d1303863c6c.xml, portcls/IPortClsVersion::GetVersion
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IPortClsVersion::GetVersion
 - portcls/IPortClsVersion::GetVersion
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IPortClsVersion.GetVersion
---

# IPortClsVersion::GetVersion


## -description

The <code>GetVersion</code> method returns the version of the Windows operating system that the driver is running on.

## -returns

The <code>GetVersion</code> method returns a DWORD value that specifies the Windows version number. For more information, see the following Remarks section.

## -remarks

The <code>GetVersion</code> method returns version information that specifies the Windows release.

The possible Windows version numbers that <code>GetVersion</code> can return are shown in the following table.

| Version Number | Windows Version | Supports |
|----------------|-----------------|----------|
|**kVersionWin98**|Windows 98|no|
|**kVersionWin98SE**|Windows 98 Second Edition|no|
|**kVersionWin2K**|Windows 2000|no|
|**kVersionWin98SE_QFE2**|Windows 98 SE + Hot-Fix Package 269601.)|no|
|**kVersionWin2K_SP2**|Windows 2000 + Service Pack 2|YES|
|**kVersionWinME**|Windows Me|no|
|**kVersionWin98SE_QFE3**|Reserved for future use|YES|
|**kVersionWinME_QFE1**|Reserved for future use|YES|
|**kVersionWinXP**|Windows XP|YES|
|**kVersionWinXPSP1**|Windows XP + Service Pack 1|YES|
|**kVersionWinServer2003**|Windows Server 2003|YES|
|**kVersionWin2K_UAAQFE**|Windows 2000 + hot-fix package with IUnregister_Xxx_ support (See [Dynamic Audio Subdevices](https://docs.microsoft.com/windows-hardware/drivers/audio/dynamic-audio-subdevices).)|YES|
|**kVersionWinXP_UAAQFE**|Windows XP + hot-fix package with IUnregister_Xxx_ support (See [Dynamic Audio Subdevices](https://docs.microsoft.com/windows-hardware/drivers/audio/dynamic-audio-subdevices).)|YES|
|**kVersionWinServer2003_UAAQFE**|Windows Server 2003 + hot-fix package with IUnregister_Xxx_ support (See [Dynamic Audio Subdevices](https://docs.microsoft.com/windows-hardware/drivers/audio/dynamic-audio-subdevices).)|YES|

The version numbers in the preceding table are defined in header file portcls.h. Note that portcls.h defines version numbers both for Windows versions that do and do not support the <b>IPortClsVersion</b> interface. Both types of version number can be useful. A miniport driver typically contains a proprietary routine that determines the Windows version and can return any of the version numbers in the preceding table. When executed on a platform that does not support <b>IPortClsVersion</b>, this routine needs to use other software tests to determine the Windows version. These tests typically rely on the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioiswdmversionavailable">IoIsWdmVersionAvailable</a> function. For a code example of such a routine, see the sb16 sample audio driver in the Windows Driver Kit (WDK).

The version numbers in the preceding table are listed in roughly chronological order. Each successive Windows version in the table does not necessarily represent a feature superset of the preceding version. For example, the version that is represented by <b>kVersionWin2K</b> has more audio features than the version that is represented by <b>kVersionWin98SE_QFE2</b>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iportclsversion">IPortClsVersion</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioiswdmversionavailable">IoIsWdmVersionAvailable</a>

