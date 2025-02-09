---
description: "supportsCatalogsInPrivilegeDefinitions Method (SQLServerDatabaseMetaData)"
title: "supportsCatalogsInPrivilegeDefinitions Method | Microsoft Docs"
ms.custom: ""
ms.date: "01/19/2017"
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ""
ms.technology: connectivity
ms.topic: reference
apiname: 
  - "SQLServerDatabaseMetaData.supportsCatalogsInPrivilegeDefinitions"
apilocation: 
  - "sqljdbc.jar"
apitype: "Assembly"
ms.assetid: cc18f99e-c19f-4bd0-96ae-b9a6a0de1926
author: David-Engel
ms.author: v-davidengel
---
# supportsCatalogsInPrivilegeDefinitions Method (SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Retrieves whether a catalog name can be used in a privilege definition statement.  
  
## Syntax  
  
```  
  
public boolean supportsCatalogsInPrivilegeDefinitions()  
```  
  
## Return Value  
 **true** if supported. Otherwise, **false**.  
  
## Exceptions  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## Remarks  
 This supportsCatalogsInPrivilegeDefinitions method is specified by the supportsCatalogsInPrivilegeDefinitions method in the java.sql.DatabaseMetaData interface.  
  
## See Also  
 [SQLServerDatabaseMetaData Methods](../../../connect/jdbc/reference/sqlserverdatabasemetadata-methods.md)   
 [SQLServerDatabaseMetaData Members](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [SQLServerDatabaseMetaData Class](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  
