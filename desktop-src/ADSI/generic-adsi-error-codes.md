---
title: Generic ADSI Error Codes
description: These types of error codes can be returned by any of the ADSI system providers to represent ADSI-specific error messages.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\mbaldwin
ms.assetid: 193c5808-fc39-48e6-8bb8-8338e5c980ad
ms.prod: windows-server-dev
ms.technology: active-directory-domain-services
ms.tgt_platform: multiple
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# Generic ADSI Error Codes

These types of error codes can be returned by any of the ADSI system providers to represent ADSI-specific error messages. They have the facility code 5 with severity bit set either **true** or **false**. When the severity bit is set to **true**, this results in error values of the form 0x80005xxx and error messages of the form **E\_ADS\_\***. When the severity bit is set to **false**, this results in error values of the form 0x00005xxx and the error messages are of the **S\_ADS\_\*** form.

The following table lists generic ADSI error codes defined in Adserr.h.



| Value       | Code                                  | Description                                                           | Corrective Action                                                                                                                                                                                                                                                                                          |
|-------------|---------------------------------------|-----------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 0x00005011L | **S\_ADS\_ERRORSOCCURRED**            | During a query, one or more errors occurred.                          | Verify that the search preference can be legally set and, if so, that it is properly set.                                                                                                                                                                                                                  |
| 0x00005012L | **S\_ADS\_NOMORE\_ROWS**              | The search operation has reached the last row.                        | Move on to the rest of the program.                                                                                                                                                                                                                                                                        |
| 0x00005013L | **S\_ADS\_NOMORE\_COLUMNS**           | The search operation has reached the last column for the current row. | Move on to next row.                                                                                                                                                                                                                                                                                       |
| 0x80005000L | **E\_ADS\_BAD\_PATHNAME**             | An invalid ADSI pathname was passed.                                  | Verify that the object exists on the directory server and check for typographic errors of the path.                                                                                                                                                                                                        |
| 0x80005001L | **E\_ADS\_INVALID\_DOMAIN\_OBJECT**   | An unknown ADSI domain object was requested.                          | Verify the path of the domain object.                                                                                                                                                                                                                                                                      |
| 0x80005002L | **E\_ADS\_INVALID\_USER\_OBJECT**     | An unknown ADSI user object was requested.                            | Verify the existence of the user object, check for typos of the path and the user access rights.                                                                                                                                                                                                           |
| 0x80005003L | **E\_ADS\_INVALID\_COMPUTER\_OBJECT** | An unknown ADSI computer object was requested.                        | Verify the existence of the computer object, check for typos of the path and the computer access rights.                                                                                                                                                                                                   |
| 0x80005004L | **E\_ADS\_UNKNOWN\_OBJECT**           | An unknown ADSI object was requested.                                 | Verify the name of and the access rights to the object.                                                                                                                                                                                                                                                    |
| 0x80005005L | **E\_ADS\_PROPERTY\_NOT\_SET**        | The specified ADSI property was not set.                              |                                                                                                                                                                                                                                                                                                            |
| 0x80005006L | **E\_ADS\_PROPERTY\_NOT\_SUPPORTED**  | The specified ADSI property is not supported.                         | Verify that the correct property is set.                                                                                                                                                                                                                                                                   |
| 0x80005007L | **E\_ADS\_PROPERTY\_INVALID**         | The specified ADSI property is invalid                                | Verify the parameters passed to the method call.                                                                                                                                                                                                                                                           |
| 0x80005008L | **E\_ADS\_BAD\_PARAMETER**            | One or more input parameters are invalid.                             |                                                                                                                                                                                                                                                                                                            |
| 0x80005009L | **E\_ADS\_OBJECT\_UNBOUND**           | The specified ADSI object is not bound to a remote resource.          | Call [**GetInfo**](/windows/desktop/api/Iads/nf-iads-iads-getinfo) on a newly created object after [**SetInfo**](/windows/desktop/api/Iads/nf-iads-iads-setinfo) has been called.                                                                                                                                                                                      |
| 0x8000500AL | **E\_ADS\_PROPERTY\_NOT\_MODIFIED**   | The specified ADSI object has not been modified.                      |                                                                                                                                                                                                                                                                                                            |
| 0x8000500BL | **E\_ADS\_PROPERTY\_MODIFIED**        | The specified ADSI object has been modified.                          |                                                                                                                                                                                                                                                                                                            |
| 0x8000500CL | **E\_ADS\_CANT\_CONVERT\_DATATYPE**   | The data type cannot be converted to/from a native DS data type.      | Verify that the correct data type is used and/or that there is sufficient schema data available to perform data type conversion.                                                                                                                                                                           |
| 0x8000500DL | **E\_ADS\_PROPERTY\_NOT\_FOUND**      | The property cannot be found in the cache.                            | Verify that [**GetInfo**](/windows/desktop/api/Iads/nf-iads-iads-getinfo) has been called implicitly or explicitly. If the attribute is an operational attribute, it must be explicitly retrieved with [**GetInfoEx**](/windows/desktop/api/Iads/nf-iads-iads-getinfoex) instead of **GetInfo**. If the problem persists, the property has not been set on the server. |
| 0x8000500EL | **E\_ADS\_OBJECT\_EXISTS**            | The ADSI object exists.                                               | Use a different name to create the object.                                                                                                                                                                                                                                                                 |
| 0x8000500FL | **E\_ADS\_SCHEMA\_VIOLATION**         | The attempted action violates the directory service schema rules.     |                                                                                                                                                                                                                                                                                                            |
| 0x80005010L | **E\_ADS\_COLUMN\_NOT\_SET**          | The specified column in the ADSI was not set.                         |                                                                                                                                                                                                                                                                                                            |
| 0x80005014L | **E\_ADS\_INVALID\_FILTER**           | The specified search filter is invalid.                               | Use the correct format of the filter accepted by the directory server.                                                                                                                                                                                                                                     |



 

 

 



