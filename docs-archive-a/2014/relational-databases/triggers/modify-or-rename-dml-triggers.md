---
title: Modifier ou renommer les déclencheurs DML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- renaming triggers
- modifying triggers
- DML triggers, modifying
ms.assetid: c7317eec-c0e9-479e-a4a7-83b6b6c58d59
author: rothja
ms.author: jroth
ms.openlocfilehash: 65bb13552b552d54b5547eadedc412977e423a57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613871"
---
# <a name="modify-or-rename-dml-triggers"></a><span data-ttu-id="2f3bb-102">Modifier ou renommer les déclencheurs DML</span><span class="sxs-lookup"><span data-stu-id="2f3bb-102">Modify or Rename DML Triggers</span></span>
  <span data-ttu-id="2f3bb-103">Cette rubrique explique comment modifier ou renommer un déclencheur DML dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f3bb-103">This topic describes how to modify or rename a DML trigger in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2f3bb-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="2f3bb-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2f3bb-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="2f3bb-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2f3bb-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="2f3bb-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="2f3bb-107">Recommandations</span><span class="sxs-lookup"><span data-stu-id="2f3bb-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="2f3bb-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2f3bb-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2f3bb-109">**Pour modifier ou renommer un déclencheur DML à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="2f3bb-109">**To modify or rename a DML trigger, using:**</span></span>  
  
     [<span data-ttu-id="2f3bb-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2f3bb-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2f3bb-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2f3bb-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2f3bb-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="2f3bb-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="2f3bb-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="2f3bb-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="2f3bb-114">Lorsque vous renommez un déclencheur, celui-ci doit se trouver dans la base de données actuelle et le nouveau nom doit respecter les règles applicables aux [identificateurs](../databases/database-identifiers.md).</span><span class="sxs-lookup"><span data-stu-id="2f3bb-114">When you rename a trigger, the trigger must be in the current database, and the new name must follow the rules for [identifiers](../databases/database-identifiers.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="2f3bb-115">Recommandations</span><span class="sxs-lookup"><span data-stu-id="2f3bb-115">Recommendations</span></span>  
  
-   <span data-ttu-id="2f3bb-116">Nous vous recommandons de ne pas utiliser la procédure stockée [sp_rename](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) pour renommer un déclencheur.</span><span class="sxs-lookup"><span data-stu-id="2f3bb-116">We recommend you do not use the [sp_rename](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) stored procedure to rename a trigger.</span></span> <span data-ttu-id="2f3bb-117">La modification d'une partie du nom de l'objet peut provoquer des problèmes dans des scripts et des procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="2f3bb-117">Changing any part of an object name can break scripts and stored procedures.</span></span> <span data-ttu-id="2f3bb-118">Le fait de renommer un déclencheur ne modifie pas le nom de l’objet correspondant dans la colonne de définition de l’affichage catalogue [sys.sql_modules](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="2f3bb-118">Renaming a trigger does not change the name of the corresponding object name in the definition column of the [sys.sql_modules](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) catalog view.</span></span> <span data-ttu-id="2f3bb-119">Nous vous recommandons plutôt de supprimer et de recréer le déclencheur.</span><span class="sxs-lookup"><span data-stu-id="2f3bb-119">We recommend that you drop and re-create the trigger instead.</span></span>  
  
-   <span data-ttu-id="2f3bb-120">Si vous changez le nom d'un objet référencé par un déclencheur DML, vous devez modifier le déclencheur pour que sa définition se réfère au nouveau nom de l'objet.</span><span class="sxs-lookup"><span data-stu-id="2f3bb-120">If you change the name of an object referenced by a DML trigger, you must modify the trigger so that its text reflects the new name.</span></span> <span data-ttu-id="2f3bb-121">Par conséquent, avant de renommer un objet, affichez les dépendances de l'objet pour savoir si des déclencheurs peuvent être concernés par la modification projetée.</span><span class="sxs-lookup"><span data-stu-id="2f3bb-121">Therefore, before you rename an object, display the dependencies of the object first to determine whether any triggers are affected by the proposed change.</span></span>  
  
-   <span data-ttu-id="2f3bb-122">Un déclencheur DML peut aussi être modifié pour en chiffrer la définition.</span><span class="sxs-lookup"><span data-stu-id="2f3bb-122">A DML trigger can also be modified to encrypt its definition.</span></span>  
  
-   <span data-ttu-id="2f3bb-123">Pour afficher les dépendances d'un déclencheur, vous pouvez utiliser [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou la fonction et les affichages catalogue suivants :</span><span class="sxs-lookup"><span data-stu-id="2f3bb-123">To view the dependencies of a trigger, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or the following function and catalog views:</span></span>  
  
    -   [<span data-ttu-id="2f3bb-124">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2f3bb-124">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)  
  
    -   [<span data-ttu-id="2f3bb-125">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2f3bb-125">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql)  
  
    -   [<span data-ttu-id="2f3bb-126">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2f3bb-126">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql)  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2f3bb-127">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2f3bb-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2f3bb-128">Autorisations</span><span class="sxs-lookup"><span data-stu-id="2f3bb-128">Permissions</span></span>  
 <span data-ttu-id="2f3bb-129">La modification d'un déclencheur DML nécessite une autorisation ALTER sur la table ou la vue sur laquelle le déclencheur est défini.</span><span class="sxs-lookup"><span data-stu-id="2f3bb-129">To alter a DML trigger requires ALTER permission on the table or view on which the trigger is defined.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2f3bb-130">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2f3bb-130">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-dml-trigger"></a><span data-ttu-id="2f3bb-131">Pour modifier un déclencheur DML</span><span class="sxs-lookup"><span data-stu-id="2f3bb-131">To modify a DML trigger</span></span>  
  
1.  <span data-ttu-id="2f3bb-132">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="2f3bb-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="2f3bb-133">Développez la base de données choisie, développez **Tables**, puis développez la table qui contient le déclencheur que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="2f3bb-133">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger that you want to modify.</span></span>  
  
3.  <span data-ttu-id="2f3bb-134">Développez **Déclencheurs**, cliquez avec le bouton droit sur le déclencheur à modifier, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="2f3bb-134">Expand **Triggers**, right-click the trigger to modify, and then click **Modify**.</span></span>  
  
4.  <span data-ttu-id="2f3bb-135">Modifiez le déclencheur, puis sélectionnez **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="2f3bb-135">Modify the trigger, and then click **Execute**.</span></span>  
  
#### <a name="to-rename-a-dml-trigger"></a><span data-ttu-id="2f3bb-136">Pour renommer un déclencheur DML</span><span class="sxs-lookup"><span data-stu-id="2f3bb-136">To rename a DML trigger</span></span>  
  
1.  <span data-ttu-id="2f3bb-137">[Supprimez le déclencheur](../triggers/dml-triggers.md) que vous souhaitez renommer.</span><span class="sxs-lookup"><span data-stu-id="2f3bb-137">[Delete the trigger](../triggers/dml-triggers.md) that you want to rename.</span></span>  
  
2.  <span data-ttu-id="2f3bb-138">[Recréez le déclencheur](../triggers/create-dml-triggers.md)en spécifiant un nouveau nom.</span><span class="sxs-lookup"><span data-stu-id="2f3bb-138">[Re-create the trigger](../triggers/create-dml-triggers.md), specifying the new name.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2f3bb-139">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2f3bb-139">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-trigger-using-alter-trigger"></a><span data-ttu-id="2f3bb-140">Pour modifier un déclencheur à l'aide de ALTER TRIGGER</span><span class="sxs-lookup"><span data-stu-id="2f3bb-140">To modify a trigger using ALTER TRIGGER</span></span>  
  
1.  <span data-ttu-id="2f3bb-141">Connectez-vous au [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f3bb-141">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2f3bb-142">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="2f3bb-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2f3bb-143">Copiez et collez les exemples suivants dans le volet de requête.</span><span class="sxs-lookup"><span data-stu-id="2f3bb-143">Copy and paste the following examples into the query.</span></span> <span data-ttu-id="2f3bb-144">Exécutez le premier exemple pour créer un déclencheur DML qui envoie un message défini par l'utilisateur au client lorsqu'un utilisateur tente d'ajouter ou de modifier les données de la table `SalesPersonQuotaHistory` .</span><span class="sxs-lookup"><span data-stu-id="2f3bb-144">Execute the first example to create a DML trigger that prints a user-defined message to the client when a user tries to add or change data in the `SalesPersonQuotaHistory` table.</span></span> <span data-ttu-id="2f3bb-145">Exécutez l'instruction [ALTER TRIGGER](/sql/t-sql/statements/alter-trigger-transact-sql) pour modifier le déclencheur afin qu'il s'active uniquement sur des activités `INSERT` .</span><span class="sxs-lookup"><span data-stu-id="2f3bb-145">Execute the [ALTER TRIGGER](/sql/t-sql/statements/alter-trigger-transact-sql) statement to modify the trigger to fire only on `INSERT` activities.</span></span> <span data-ttu-id="2f3bb-146">Ce déclencheur est utile car il rappelle à l'utilisateur qui met à jour ou insère des lignes dans cette table de notifier également le département `Compensation` .</span><span class="sxs-lookup"><span data-stu-id="2f3bb-146">This trigger is helpful because it reminds the user that updates or inserts rows into this table to also notify the `Compensation` department.</span></span>  
  
```sql  
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
USE AdventureWorks2012;  
GO  
ALTER TRIGGER Sales.bonus_reminder  
ON Sales.SalesPersonQuotaHistory  
AFTER INSERT  
AS RAISERROR ('Notify Compensation', 16, 10);  
GO  
  
```  
  
#### <a name="to-rename-a-trigger-using-drop-trigger-and-alter-trigger"></a><span data-ttu-id="2f3bb-147">Pour renommer un déclencheur à l'aide de DROP TRIGGER et ALTER TRIGGER</span><span class="sxs-lookup"><span data-stu-id="2f3bb-147">To rename a trigger using DROP TRIGGER and ALTER TRIGGER</span></span>  
  
1.  <span data-ttu-id="2f3bb-148">Connectez-vous au [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f3bb-148">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2f3bb-149">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="2f3bb-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2f3bb-150">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="2f3bb-150">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="2f3bb-151">Cet exemple utilise les instructions [DROP TRIGGER](/sql/t-sql/statements/drop-trigger-transact-sql) et [ALTER TRIGGER](/sql/t-sql/statements/alter-trigger-transact-sql) pour renommer le déclencheur `Sales.bonus_reminder` en `Sales.bonus_reminder_2`.</span><span class="sxs-lookup"><span data-stu-id="2f3bb-151">This example use the [DROP TRIGGER](/sql/t-sql/statements/drop-trigger-transact-sql) and [ALTER TRIGGER](/sql/t-sql/statements/alter-trigger-transact-sql) statements to rename the `Sales.bonus_reminder` trigger to `Sales.bonus_reminder_2`.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID(N'Sales.bonus_reminder', N'TR') IS NOT NULL  
    DROP TRIGGER Sales.bonus_reminder;  
GO  
CREATE TRIGGER Sales.bonus_reminder_2  
ON Sales.SalesPersonQuotaHistory  
WITH ENCRYPTION  
AFTER INSERT, UPDATE   
AS RAISERROR ('Notify Compensation', 16, 10);  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="2f3bb-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2f3bb-152">See Also</span></span>  
 <span data-ttu-id="2f3bb-153">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f3bb-153">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="2f3bb-154">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f3bb-154">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span></span>  
 <span data-ttu-id="2f3bb-155">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f3bb-155">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="2f3bb-156">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f3bb-156">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="2f3bb-157">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f3bb-157">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span></span>  
 <span data-ttu-id="2f3bb-158">[sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f3bb-158">[sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) </span></span>  
 <span data-ttu-id="2f3bb-159">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f3bb-159">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span></span>  
 <span data-ttu-id="2f3bb-160">[Obtenir des informations sur les déclencheurs DML](../triggers/get-information-about-dml-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="2f3bb-160">[Get Information About DML Triggers](../triggers/get-information-about-dml-triggers.md) </span></span>  
 <span data-ttu-id="2f3bb-161">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f3bb-161">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span></span>  
 <span data-ttu-id="2f3bb-162">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f3bb-162">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span></span>  
 <span data-ttu-id="2f3bb-163">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f3bb-163">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span></span>  
 <span data-ttu-id="2f3bb-164">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f3bb-164">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="2f3bb-165">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f3bb-165">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="2f3bb-166">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f3bb-166">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span></span>  
 <span data-ttu-id="2f3bb-167">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f3bb-167">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span></span>  
 <span data-ttu-id="2f3bb-168">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f3bb-168">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="2f3bb-169">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f3bb-169">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span></span>  
 [<span data-ttu-id="2f3bb-170">sys.server_assembly_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2f3bb-170">sys.server_assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql)  
  
  
