---
title: Supprimer ou désactiver des déclencheurs DML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- DML triggers, disabling
- removing DML triggers
- disabling DML triggers
- dropping DML triggers
- deleting DML triggers
- DML triggers, removing
ms.assetid: 0f97f953-33c5-4b26-afeb-db2a26ce38b4
author: rothja
ms.author: jroth
ms.openlocfilehash: 39b345ade1258987df06938791ac0024e8612365
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613888"
---
# <a name="delete-or-disable-dml-triggers"></a><span data-ttu-id="b646e-102">Supprimer ou désactiver les déclencheurs DML</span><span class="sxs-lookup"><span data-stu-id="b646e-102">Delete or Disable DML Triggers</span></span>
  <span data-ttu-id="b646e-103">Cette rubrique explique comment supprimer ou désactiver un déclencheur DML dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b646e-103">This topic describes how to delete or disable a DML trigger in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="b646e-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="b646e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b646e-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="b646e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b646e-106">Recommandations</span><span class="sxs-lookup"><span data-stu-id="b646e-106">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="b646e-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b646e-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b646e-108">**Pour supprimer ou désactiver un déclencheur DML à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="b646e-108">**To delete or disable a DML trigger, using:**</span></span>  
  
     [<span data-ttu-id="b646e-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b646e-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b646e-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b646e-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b646e-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="b646e-111">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="b646e-112">Recommandations</span><span class="sxs-lookup"><span data-stu-id="b646e-112">Recommendations</span></span>  
  
-   <span data-ttu-id="b646e-113">La suppression d'un déclencheur entraîne sa suppression définitive de la base de données actuelle.</span><span class="sxs-lookup"><span data-stu-id="b646e-113">When a trigger is deleted, it is dropped from the current database.</span></span> <span data-ttu-id="b646e-114">La table et les données sur lesquelles il est basé ne sont pas affectées.</span><span class="sxs-lookup"><span data-stu-id="b646e-114">The table and the data upon which it is based are not affected.</span></span> <span data-ttu-id="b646e-115">La suppression d'une table supprime automatiquement les déclencheurs qui lui sont associés.</span><span class="sxs-lookup"><span data-stu-id="b646e-115">Deleting a table automatically deletes any triggers on the table.</span></span>  
  
-   <span data-ttu-id="b646e-116">Un déclencheur est activé par défaut lors de sa création.</span><span class="sxs-lookup"><span data-stu-id="b646e-116">A trigger is enabled by default when it is created.</span></span>  
  
-   <span data-ttu-id="b646e-117">La désactivation d'un déclencheur ne le supprime pas.</span><span class="sxs-lookup"><span data-stu-id="b646e-117">Disabling a trigger does not drop it.</span></span> <span data-ttu-id="b646e-118">Le déclencheur existe toujours en tant qu'objet dans la base de données actuelle.</span><span class="sxs-lookup"><span data-stu-id="b646e-118">The trigger still exists as an object in the current database.</span></span> <span data-ttu-id="b646e-119">Il ne s'activera toutefois pas lors de l'exécution d'une instruction INSERT, UPDATE ou DELETE pour laquelle il avait été programmé.</span><span class="sxs-lookup"><span data-stu-id="b646e-119">However, the trigger will not fire when any INSERT, UPDATE, or DELETE statement on which it was programmed is executed.</span></span> <span data-ttu-id="b646e-120">Tout déclencheur désactivé peut être à nouveau réactivé.</span><span class="sxs-lookup"><span data-stu-id="b646e-120">Triggers that are disabled can be reenabled.</span></span> <span data-ttu-id="b646e-121">Un déclencheur n'est pas recréé par son activation.</span><span class="sxs-lookup"><span data-stu-id="b646e-121">Enabling a trigger does not re-create it.</span></span> <span data-ttu-id="b646e-122">Le déclencheur est activé de la même manière que lorsqu'il a été initialement créé.</span><span class="sxs-lookup"><span data-stu-id="b646e-122">The trigger fires in the same manner as when it was originally created.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b646e-123">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b646e-123">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b646e-124">Autorisations</span><span class="sxs-lookup"><span data-stu-id="b646e-124">Permissions</span></span>  
 <span data-ttu-id="b646e-125">La suppression d'un déclencheur DML nécessite une autorisation ALTER sur la table ou la vue sur laquelle le déclencheur est défini.</span><span class="sxs-lookup"><span data-stu-id="b646e-125">To delete a DML trigger requires ALTER permission on the table or view on which the trigger is defined.</span></span>  
  
 <span data-ttu-id="b646e-126">Pour désactiver ou activer un déclencheur DML, un utilisateur doit avoir au minimum l'autorisation ALTER pour la table ou la vue sur laquelle le déclencheur a été créé.</span><span class="sxs-lookup"><span data-stu-id="b646e-126">To disable or enable a DML trigger, at a minimum, a user must have ALTER permission on the table or view on which the trigger was created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b646e-127">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b646e-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-dml-trigger"></a><span data-ttu-id="b646e-128">Pour supprimer un déclencheur DML</span><span class="sxs-lookup"><span data-stu-id="b646e-128">To delete a DML trigger</span></span>  
  
1.  <span data-ttu-id="b646e-129">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="b646e-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="b646e-130">Développez la base de données choisie, développez **Tables**, puis développez la table qui contient le déclencheur que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="b646e-130">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger that you want to delete.</span></span>  
  
3.  <span data-ttu-id="b646e-131">Développez **Déclencheurs**, cliquez avec le bouton droit sur le déclencheur à supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b646e-131">Expand **Triggers**, right-click the trigger to delete, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="b646e-132">Dans la boîte de dialogue **Supprimer un objet** , vérifiez que le déclencheur correct est spécifié et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b646e-132">In the **Delete Object** dialog box, verify the trigger to delete, and then click **OK**.</span></span>  
  
#### <a name="to-disable-and-enable-a-dml-trigger"></a><span data-ttu-id="b646e-133">Pour désactiver et activer un déclencheur DML</span><span class="sxs-lookup"><span data-stu-id="b646e-133">To disable and enable a DML trigger</span></span>  
  
1.  <span data-ttu-id="b646e-134">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="b646e-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="b646e-135">Développez la base de données choisie, développez **Tables**, puis développez la table qui contient le déclencheur que vous souhaitez désactiver.</span><span class="sxs-lookup"><span data-stu-id="b646e-135">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger that you want to disable.</span></span>  
  
3.  <span data-ttu-id="b646e-136">Développez **Déclencheurs**, cliquez avec le bouton droit sur le déclencheur à désactiver, puis cliquez sur **Désactiver**.</span><span class="sxs-lookup"><span data-stu-id="b646e-136">Expand **Triggers**, right-click the trigger to disable, and then click **Disable**.</span></span>  
  
4.  <span data-ttu-id="b646e-137">Pour activer le déclencheur, cliquez sur **Activer**.</span><span class="sxs-lookup"><span data-stu-id="b646e-137">To enable the trigger, click **Enable**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b646e-138">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b646e-138">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-dml-trigger"></a><span data-ttu-id="b646e-139">Pour supprimer un déclencheur DML</span><span class="sxs-lookup"><span data-stu-id="b646e-139">To delete a DML trigger</span></span>  
  
1.  <span data-ttu-id="b646e-140">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b646e-140">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b646e-141">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="b646e-141">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b646e-142">Copiez et collez les exemples suivants dans la fenêtre de requête.</span><span class="sxs-lookup"><span data-stu-id="b646e-142">Copy and paste the following examples into the query window.</span></span> <span data-ttu-id="b646e-143">Exécutez l'instruction [CREATE TRIGGER](/sql/t-sql/statements/create-trigger-transact-sql) pour créer le déclencheur `Sales.bonus_reminder` .</span><span class="sxs-lookup"><span data-stu-id="b646e-143">Execute the [CREATE TRIGGER](/sql/t-sql/statements/create-trigger-transact-sql) statement to create the `Sales.bonus_reminder` trigger.</span></span> <span data-ttu-id="b646e-144">Pour supprimer le déclencheur, exécutez l'instruction [DROP TRIGGER](/sql/t-sql/statements/drop-trigger-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="b646e-144">To delete the trigger, execute the [DROP TRIGGER](/sql/t-sql/statements/drop-trigger-transact-sql) statement.</span></span>  
  
```sql  
--Create the trigger.  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID(N'Sales.bonus_reminder', N'TR') IS NOT NULL  
    DROP TRIGGER Sales.bonus_reminder;  
GO  
CREATE TRIGGER Sales.bonus_reminder  
ON Sales.SalesPersonQuotaHistory  
WITH ENCRYPTION  
AFTER INSERT, UPDATE   
AS RAISERROR ('Notify Compensation', 16, 10);  
GO  
  
```  
  
```sql  
--Delete the trigger.  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ('Sales.bonus_reminder', 'TR') IS NOT NULL  
   DROP TRIGGER Sales.bonus_reminder;  
GO  
  
```  
  
#### <a name="to-disable-and-enable-a-dml-trigger"></a><span data-ttu-id="b646e-145">Pour désactiver et activer un déclencheur DML</span><span class="sxs-lookup"><span data-stu-id="b646e-145">To disable and enable a DML trigger</span></span>  
  
1.  <span data-ttu-id="b646e-146">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b646e-146">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b646e-147">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="b646e-147">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b646e-148">Copiez et collez les exemples suivants dans la fenêtre de requête.</span><span class="sxs-lookup"><span data-stu-id="b646e-148">Copy and paste the following examples into the query window.</span></span> <span data-ttu-id="b646e-149">Exécutez l'instruction [CREATE TRIGGER](/sql/t-sql/statements/create-trigger-transact-sql) pour créer le déclencheur `Sales.bonus_reminder` .</span><span class="sxs-lookup"><span data-stu-id="b646e-149">Execute the [CREATE TRIGGER](/sql/t-sql/statements/create-trigger-transact-sql) statement to create the `Sales.bonus_reminder` trigger.</span></span> <span data-ttu-id="b646e-150">Pour désactiver et activer le déclencheur, exécutez les instructions [DISABLE TRIGGER](/sql/t-sql/statements/disable-trigger-transact-sql) et [ENABLE TRIGGER](/sql/t-sql/statements/enable-trigger-transact-sql) , respectivement.</span><span class="sxs-lookup"><span data-stu-id="b646e-150">To disable and enable the trigger, execute the [DISABLE TRIGGER](/sql/t-sql/statements/disable-trigger-transact-sql) and [ENABLE TRIGGER](/sql/t-sql/statements/enable-trigger-transact-sql) statements, respectively.</span></span>  
  
```sql  
--Create the trigger.  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID(N'Sales.bonus_reminder', N'TR') IS NOT NULL  
    DROP TRIGGER Sales.bonus_reminder;  
GO  
CREATE TRIGGER Sales.bonus_reminder  
ON Sales.SalesPersonQuotaHistory  
WITH ENCRYPTION  
AFTER INSERT, UPDATE   
AS RAISERROR ('Notify Compensation', 16, 10);  
GO  
  
```  
  
```sql  
--Disable the trigger.  
USE AdventureWorks2012;  
GO  
DISABLE TRIGGER Sales.bonus_reminder ON Sales.SalesPersonQuotaHistory;  
GO  
  
```  
  
```sql  
--Enable the trigger.  
USE AdventureWorks2012;  
GO  
ENABLE TRIGGER Sales.bonus_reminder ON Sales.SalesPersonQuotaHistory;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="b646e-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b646e-151">See Also</span></span>  
 <span data-ttu-id="b646e-152">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b646e-152">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span></span>  
 <span data-ttu-id="b646e-153">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b646e-153">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="b646e-154">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b646e-154">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span></span>  
 <span data-ttu-id="b646e-155">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b646e-155">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="b646e-156">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b646e-156">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="b646e-157">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b646e-157">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span></span>  
 <span data-ttu-id="b646e-158">[Obtenir des informations sur les déclencheurs DML](dml-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="b646e-158">[Get Information About DML Triggers](dml-triggers.md) </span></span>  
 <span data-ttu-id="b646e-159">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b646e-159">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span></span>  
 <span data-ttu-id="b646e-160">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b646e-160">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span></span>  
 <span data-ttu-id="b646e-161">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b646e-161">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span></span>  
 <span data-ttu-id="b646e-162">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b646e-162">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="b646e-163">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b646e-163">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="b646e-164">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b646e-164">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span></span>  
 <span data-ttu-id="b646e-165">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b646e-165">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span></span>  
 <span data-ttu-id="b646e-166">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b646e-166">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="b646e-167">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b646e-167">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span></span>  
 [<span data-ttu-id="b646e-168">sys.server_assembly_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b646e-168">sys.server_assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql)  
  
  
