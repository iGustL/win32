---
title: INetFwV6Mgr LogfilePath property
description: A read/write property that specifies the path of the file that is used to record logging information. For example, dropped packets and connection creation and teardown.
ms.assetid: 6a392133-93aa-41b2-a427-35df9afe2e52
keywords:
- LogfilePath property ICS/ICF
- LogfilePath property ICS/ICF , INetFwV6Mgr interface
- INetFwV6Mgr interface ICS/ICF , LogfilePath property
topic_type:
- apiref
api_name:
- INetFwV6Mgr.LogfilePath
- INetFwV6Mgr.get_LogfilePath
- INetFwV6Mgr.put_LogfilePath
api_location:
- Netfwv6.dll
api_type:
- COM
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# INetFwV6Mgr::LogfilePath property

\[The IPv6 Internet Connection Firewall is available for use in the operating systems specified in the Requirements section. Instead, use the [Windows Firewall API](windows-firewall-start-page.md).\]

A read/write property that specifies the path of the file that is used to record logging information. For example, dropped packets and connection creation and teardown.

This property is read/write.

## Syntax


```C++
HRESULT put_LogfilePath(
  [in]  BSTR bstrLogfilePath
);

HRESULT get_LogfilePath(
  [out] BSTR *pbstrLogfilePath
);
```



## Property value

Specifies the value to set.

## Error codes

If the method succeeds, the return value is S\_OK.

If the method fails, the return value is one of the following error codes.



| Name                                                                                      | Meaning                                                       |
|-------------------------------------------------------------------------------------------|---------------------------------------------------------------|
| <dl> <dt>E\_ABORT</dt> </dl>       | The operation was aborted.<br/>                         |
| <dl> <dt>E\_FAIL</dt> </dl>        | An unspecified error occurred.<br/>                     |
| <dl> <dt>E\_INVALIDARG</dt> </dl>  | One of the parameters is invalid.<br/>                  |
| <dl> <dt>E\_NOINTERFACE</dt> </dl> | A specified interface is not supported.<br/>            |
| <dl> <dt>E\_NOTIMPL</dt> </dl>     | A specified method is not implemented.<br/>             |
| <dl> <dt>E\_OUTOFMEMORY</dt> </dl> | The method was unable to allocate required memory.<br/> |
| <dl> <dt>E\_POINTER</dt> </dl>     | A pointer passed as a parameter is not valid.<br/>      |
| <dl> <dt>E\_UNEXPECTED</dt> </dl>  | The method failed for unknown reasons.<br/>             |



## Requirements



|                                     |                                                                                        |
|-------------------------------------|----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP with SP1 \[desktop apps only\]<br/>                                   |
| Minimum supported server<br/> | None supported<br/>                                                              |
| End of client support<br/>    | Windows XP with SP1<br/>                                                         |
| Redistributable<br/>          | Advanced Networking Pack for Windows XP<br/>                                     |
| Header<br/>                   | <dl> <dt>Netfwv6.h</dt> </dl>   |
| DLL<br/>                      | <dl> <dt>Netfwv6.dll</dt> </dl> |



## See also

<dl> <dt>

[INetFwV6Mgr](https://msdn.microsoft.com/library/windows/desktop/aa365874)
</dt> <dt>


</dt> <dt>

[**INetFwV6Mgr**](inetfwv6mgr.md)
</dt> </dl>

 

 




