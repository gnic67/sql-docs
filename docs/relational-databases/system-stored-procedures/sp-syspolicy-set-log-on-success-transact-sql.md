---
title: "sp_syspolicy_set_log_on_success (Transact-SQL)"
description: "sp_syspolicy_set_log_on_success (Transact-SQL)"
author: VanMSFT
ms.author: vanto
ms.date: "08/09/2016"
ms.service: sql
ms.subservice: system-objects
ms.topic: "reference"
f1_keywords:
  - "sp_syspolicy_set_log_on_success_TSQL"
  - "sp_syspolicy_set_log_on_success"
helpviewer_keywords:
  - "sp_syspolicy_set_log_on_success"
dev_langs:
  - "TSQL"
---
# sp_syspolicy_set_log_on_success (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Specifies whether successful policy evaluations are logged in the Policy History log for Policy-Based Management.  
  
 
 :::image type="icon" source="../../includes/media/topic-link-icon.svg" border="false"::: [Transact-SQL syntax conventions](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## Syntax  
  
```  
  
sp_syspolicy_set_log_on_success [ @value = ] value  
```  
  
## Arguments  
`[ @value = ] value`
 Determines whether successful policy evaluations are logged. *value* is **sqlvariant**, and can be one of the following values:  
  
-   0 or 'false' = Successful policy evaluations are not logged.  
  
-   1 or 'true' = Successful policy evaluations are logged.  
  
## Return Code Values  
 **0** (success) or **1** (failure)  
  
## Remarks  
 You must run sp_syspolicy_set_log_on_success in the context of the msdb system database.  
  
 When *value* is set to 0 or to 'false', only failed policy evaluations are logged.  
  
## Permissions  
 Requires membership in the PolicyAdministratorRole fixed database role.  
  
> [!IMPORTANT]  
> Possible elevation of credentials: Users in the PolicyAdministratorRole role can create server triggers and schedule policy executions that can affect the operation of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)]. For example, users in the PolicyAdministratorRole role can create a policy that can prevent most objects from being created in the [!INCLUDE[ssDE](../../includes/ssde-md.md)]. Because of this possible elevation of credentials, the PolicyAdministratorRole role should be granted only to users who are trusted with controlling the configuration of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
## Examples  
 The following example enables the logging of successful policy evaluations.  
  
```  
EXEC msdb.dbo.sp_syspolicy_set_log_on_success @value = 1;  
  
GO  
```  
  
## See Also  
 [Policy-Based Management Stored Procedures &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/policy-based-management-stored-procedures-transact-sql.md)   
 [sp_syspolicy_configure &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-syspolicy-configure-transact-sql.md)  
  
  
