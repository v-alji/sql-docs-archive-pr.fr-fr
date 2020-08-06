---
title: Créer des déclencheurs imbriqués | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- recursive DML triggers [SQL Server]
- DML triggers, nested
- triggers [SQL Server], nested
- direct recursion [SQL Server]
- triggers [SQL Server], recursive
- DML triggers, recursive
- RECURSIVE_TRIGGERS option
- indirect recursion [SQL Server]
- nested DML triggers
ms.assetid: cd522dda-b4ab-41b8-82b0-02445bdba7af
author: rothja
ms.author: jroth
ms.openlocfilehash: c0016fc3cdd93ea78ceed56efa076a01bd85be50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613893"
---
# <a name="create-nested-triggers"></a><span data-ttu-id="7155c-102">Créer des déclencheurs imbriqués</span><span class="sxs-lookup"><span data-stu-id="7155c-102">Create Nested Triggers</span></span>
  <span data-ttu-id="7155c-103">Les déclencheurs DML et DDL sont imbriqués lorsqu'un déclencheur exécute une action qui lance un autre déclencheur.</span><span class="sxs-lookup"><span data-stu-id="7155c-103">Both DML and DDL triggers are nested when a trigger performs an action that initiates another trigger.</span></span> <span data-ttu-id="7155c-104">Ces actions peuvent lancer d'autres déclencheurs, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="7155c-104">These actions can initiate other triggers, and so on.</span></span> <span data-ttu-id="7155c-105">Les déclencheurs DML et DDL peuvent avoir jusqu'à 32 niveaux d'imbrication.</span><span class="sxs-lookup"><span data-stu-id="7155c-105">DML and DDL triggers can be nested up to 32 levels.</span></span> <span data-ttu-id="7155c-106">Vous pouvez définir si les déclencheurs AFTER peuvent être imbriqués à l’aide de l’option de configuration serveur **nested triggers** .</span><span class="sxs-lookup"><span data-stu-id="7155c-106">You can control whether AFTER triggers can be nested through the **nested triggers** server configuration option.</span></span> <span data-ttu-id="7155c-107">Les déclencheurs INSTEAD OF (seuls les déclencheurs DML peuvent être des déclencheurs INSTEAD OF) peuvent être imbriqués quelle que soit la valeur de ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="7155c-107">INSTEAD OF triggers (only DML triggers can be INSTEAD OF triggers) can be nested regardless of this setting.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7155c-108">Une référence au code managé à partir d'un déclencheur [!INCLUDE[tsql](../../includes/tsql-md.md)] compte pour un niveau quant à la limite d'imbrication de 32 niveaux.</span><span class="sxs-lookup"><span data-stu-id="7155c-108">Any reference to managed code from a [!INCLUDE[tsql](../../includes/tsql-md.md)] trigger counts as one level against the 32-level nesting limit.</span></span> <span data-ttu-id="7155c-109">Les méthodes appelées à partir du code managé ne comptent pas par rapport à cette limite.</span><span class="sxs-lookup"><span data-stu-id="7155c-109">Methods invoked from within managed code do not count against this limit.</span></span>  
  
 <span data-ttu-id="7155c-110">Si l'imbrication est permise et qu'un déclencheur de la chaîne démarre une boucle infinie, le niveau d'imbrication maximal est dépassé et le déclencheur s'arrête.</span><span class="sxs-lookup"><span data-stu-id="7155c-110">If nested triggers are allowed and a trigger in the chain starts an infinite loop, the nesting level is exceeded and the trigger terminates.</span></span>  
  
 <span data-ttu-id="7155c-111">Les déclencheurs imbriqués peuvent s'avérer utiles pour effectuer certaines fonctions de maintenance, comme stocker une copie de sauvegarde des lignes concernées par un déclencheur précédent.</span><span class="sxs-lookup"><span data-stu-id="7155c-111">You can use nested triggers to perform useful housekeeping functions such as storing a backup copy of rows affected by a previous trigger.</span></span> <span data-ttu-id="7155c-112">Par exemple, vous pouvez créer un déclencheur sur `PurchaseOrderDetail` , qui enregistre une copie de sauvegarde des lignes `PurchaseOrderDetail` qui ont été supprimées par le déclencheur `delcascadetrig` .</span><span class="sxs-lookup"><span data-stu-id="7155c-112">For example, you can create a trigger on `PurchaseOrderDetail` that saves a backup copy of the `PurchaseOrderDetail` rows that the `delcascadetrig` trigger deleted.</span></span> <span data-ttu-id="7155c-113">Lorsque le déclencheur `delcascadetrig` est actif, la suppression de `PurchaseOrderID` 1965 de `PurchaseOrderHeader` supprime la ou les lignes correspondantes de `PurchaseOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="7155c-113">With the `delcascadetrig` trigger in effect, deleting `PurchaseOrderID` 1965 from `PurchaseOrderHeader` deletes the corresponding row or rows from `PurchaseOrderDetail`.</span></span> <span data-ttu-id="7155c-114">Pour enregistrer les données, vous pouvez créer un déclencheur DELETE sur `PurchaseOrderDetail` , qui enregistre les données supprimées dans une autre table `del_save`créée séparément.</span><span class="sxs-lookup"><span data-stu-id="7155c-114">To save the data, you can create a DELETE trigger on `PurchaseOrderDetail` that saves the deleted data into another separately created table, `del_save`.</span></span> <span data-ttu-id="7155c-115">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="7155c-115">For example:</span></span>  
  
```  
CREATE TRIGGER Purchasing.savedel  
   ON Purchasing.PurchaseOrderDetail  
FOR DELETE  
AS  
   INSERT del_save;  
   SELECT * FROM deleted;  
```  
  
 <span data-ttu-id="7155c-116">Il n'est pas recommandé d'utiliser des déclencheurs imbriqués dans une séquence où l'ordre a de l'importance.</span><span class="sxs-lookup"><span data-stu-id="7155c-116">We do not recommend using nested triggers in an order-dependent sequence.</span></span> <span data-ttu-id="7155c-117">Employez des déclencheurs séparés pour effectuer des modifications de données en cascade.</span><span class="sxs-lookup"><span data-stu-id="7155c-117">Use separate triggers to cascade data modifications.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7155c-118">Comme les déclencheurs s'exécutent au sein d'une transaction, un échec à un quelconque niveau d'un ensemble de déclencheurs imbriqués annule la transaction tout entière, entraînant la restauration de toutes les modifications de données.</span><span class="sxs-lookup"><span data-stu-id="7155c-118">Because triggers execute within a transaction, a failure at any level of a set of nested triggers cancels the entire transaction, and all data modifications are rolled back.</span></span> <span data-ttu-id="7155c-119">Pour déterminer l'emplacement où l'erreur a eu lieu, incluez dans vos déclencheurs des instructions PRINT.</span><span class="sxs-lookup"><span data-stu-id="7155c-119">Include PRINT statements in your triggers so that you can determine where the failure has occurred.</span></span>  
  
## <a name="recursive-triggers"></a><span data-ttu-id="7155c-120">Déclencheurs récursifs</span><span class="sxs-lookup"><span data-stu-id="7155c-120">Recursive Triggers</span></span>  
 <span data-ttu-id="7155c-121">Un déclencheur AFTER ne s'appelle pas lui-même de manière récursive, à moins que l'option de base de données RECURSIVE_TRIGGERS ne soit définie.</span><span class="sxs-lookup"><span data-stu-id="7155c-121">An AFTER trigger does not call itself recursively unless the RECURSIVE_TRIGGERS database option is set.</span></span>  
  
 <span data-ttu-id="7155c-122">Il existe deux types d'autorisations :</span><span class="sxs-lookup"><span data-stu-id="7155c-122">There are two types of recursion:</span></span>  
  
-   <span data-ttu-id="7155c-123">Récurrence directe.</span><span class="sxs-lookup"><span data-stu-id="7155c-123">Direct recursion</span></span>  
  
     <span data-ttu-id="7155c-124">Elle se produit lorsqu'un déclencheur est activé et exécute une action qui l'active de nouveau.</span><span class="sxs-lookup"><span data-stu-id="7155c-124">This recursion occurs when a trigger fires and performs an action that causes the same trigger to fire again.</span></span> <span data-ttu-id="7155c-125">Par exemple, une application met à jour la table **T3**, ce qui active le déclencheur **Trig3** .</span><span class="sxs-lookup"><span data-stu-id="7155c-125">For example, an application updates table **T3**; this causes trigger **Trig3** to fire.</span></span> <span data-ttu-id="7155c-126">**Trig3** met à jour de nouveau la table **T3** , ce qui active encore le déclencheur **Trig3** .</span><span class="sxs-lookup"><span data-stu-id="7155c-126">**Trig3** updates table **T3** again; this causes trigger **Trig3** to fire again.</span></span>  
  
     <span data-ttu-id="7155c-127">La récurrence directe peut également se produire si le même déclencheur est rappelé, mais après l'appel d'un type différent (AFTER ou INSTEAD OF) de déclencheur.</span><span class="sxs-lookup"><span data-stu-id="7155c-127">Direct recursion can also occur when the same trigger is called again, but after a trigger of a different type (AFTER or INSTEAD OF) is called.</span></span> <span data-ttu-id="7155c-128">Autrement dit, la récurrence directe d'un déclencheur INSTEAD OF peut se produire lorsque le même déclencheur est rappelé, même si un ou plusieurs déclencheurs AFTER ont été appelés entre temps.</span><span class="sxs-lookup"><span data-stu-id="7155c-128">In other words, direct recursion of an INSTEAD OF trigger can occur when the same INSTEAD OF trigger is called for a second time, even if one or more AFTER triggers are called in between.</span></span> <span data-ttu-id="7155c-129">De même, la récurrence directe d'un déclencheur AFTER peut se produire lorsque le même déclencheur est rappelé, même si un ou plusieurs déclencheurs INSTEAD OF ont été appelés entre temps.</span><span class="sxs-lookup"><span data-stu-id="7155c-129">Likewise, direct recursion of an AFTER trigger can occur when the same AFTER trigger is called for a second time, even if one or more INSTEAD OF triggers are called in between.</span></span> <span data-ttu-id="7155c-130">Par exemple, une application met à jour la table **T4**.</span><span class="sxs-lookup"><span data-stu-id="7155c-130">For example, an application updates table **T4**.</span></span> <span data-ttu-id="7155c-131">Cette mise à jour entraîne l’activation du déclencheur INSTEAD OF **Trig4** .</span><span class="sxs-lookup"><span data-stu-id="7155c-131">This update causes INSTEAD OF trigger **Trig4** to fire.</span></span> <span data-ttu-id="7155c-132">**Trig4** met à jour la table **T5**.</span><span class="sxs-lookup"><span data-stu-id="7155c-132">**Trig4** updates table **T5**.</span></span> <span data-ttu-id="7155c-133">Cette mise à jour entraîne l’activation du déclencheur AFTER **Trig5** .</span><span class="sxs-lookup"><span data-stu-id="7155c-133">This update causes AFTER trigger **Trig5** to fire.</span></span> <span data-ttu-id="7155c-134">**Trig5** met à jour la table **T4**, et cette mise à jour entraîne de nouveau l’activation du déclencheur INSTEAD OF **Trig4** .</span><span class="sxs-lookup"><span data-stu-id="7155c-134">**Trig5** updates table **T4**, and this update causes INSTEAD OF trigger **Trig4** to fire again.</span></span> <span data-ttu-id="7155c-135">Cette chaîne d’événements est une récursion directe pour **Trig4**.</span><span class="sxs-lookup"><span data-stu-id="7155c-135">This chain of events is considered direct recursion for **Trig4**.</span></span>  
  
-   <span data-ttu-id="7155c-136">Récurrence indirecte.</span><span class="sxs-lookup"><span data-stu-id="7155c-136">Indirect recursion</span></span>  
  
     <span data-ttu-id="7155c-137">Elle se produit lorsqu'un déclencheur est activé et exécute une action qui active un autre déclencheur du même type (AFTER ou INSTEAD OF).</span><span class="sxs-lookup"><span data-stu-id="7155c-137">This recursion occurs when a trigger fires and performs an action that causes another trigger of the same type (AFTER or INSTEAD OF) to fire.</span></span> <span data-ttu-id="7155c-138">Le deuxième déclencheur exécute une action qui active de nouveau le déclencheur de départ.</span><span class="sxs-lookup"><span data-stu-id="7155c-138">This second trigger performs an action that causes the original trigger to fire again.</span></span> <span data-ttu-id="7155c-139">En d'autres termes, la récursion indirecte peut se produire lorsqu'un déclencheur INSTEAD OF est rappelé, mais pas avant l'appel d'un autre déclencheur INSTEAD OF entre temps.</span><span class="sxs-lookup"><span data-stu-id="7155c-139">In other words, indirect recursion can occur when an INSTEAD OF trigger is called for a second time, but not until another INSTEAD OF trigger is called in between.</span></span> <span data-ttu-id="7155c-140">De même, la récursion indirecte peut se produire lorsqu'un déclencheur AFTER est rappelé, mais pas avant l'appel d'un autre déclencheur AFTER entre temps.</span><span class="sxs-lookup"><span data-stu-id="7155c-140">Likewise, indirect recursion can occur when an AFTER trigger is called for a second time, but not until another AFTER trigger is called in between.</span></span> <span data-ttu-id="7155c-141">Par exemple, une application met à jour la table **T1**.</span><span class="sxs-lookup"><span data-stu-id="7155c-141">For example, an application updates table **T1**.</span></span> <span data-ttu-id="7155c-142">Cette mise à jour entraîne l’activation du déclencheur AFTER **Trig1** .</span><span class="sxs-lookup"><span data-stu-id="7155c-142">This update causes AFTER trigger **Trig1** to fire.</span></span> <span data-ttu-id="7155c-143">**Trig1** met à jour la table **T2**, ce qui active le déclencheur AFTER **Trig2** .</span><span class="sxs-lookup"><span data-stu-id="7155c-143">**Trig1** updates table **T2**, and this update causes AFTER trigger **Trig2** to fire.</span></span> <span data-ttu-id="7155c-144">**Trig2** à son tour met à jour la table **T1** , ce qui active de nouveau le déclencheur AFTER **Trig1** .</span><span class="sxs-lookup"><span data-stu-id="7155c-144">**Trig2** in turn updates table **T1** that causes AFTER trigger **Trig1** to fire again.</span></span>  
  
 <span data-ttu-id="7155c-145">Seule la récurrence directe des déclencheurs AFTER est neutralisée lorsque l'option de base de données RECURSIVE_TRIGGERS est désactivée (OFF).</span><span class="sxs-lookup"><span data-stu-id="7155c-145">Only direct recursion of AFTER triggers is prevented when the RECURSIVE_TRIGGERS database option is set to OFF.</span></span> <span data-ttu-id="7155c-146">Pour désactiver la récurrence indirecte des déclencheurs AFTER, affectez en plus la valeur **0** à l’option de serveur **nested triggers**.</span><span class="sxs-lookup"><span data-stu-id="7155c-146">To disable indirect recursion of AFTER triggers, also set the **nested triggers** server option to **0**.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="7155c-147">Exemples</span><span class="sxs-lookup"><span data-stu-id="7155c-147">Examples</span></span>  
 <span data-ttu-id="7155c-148">L'exemple suivant illustre l'utilisation des déclencheurs récursifs pour résoudre une relation faisant référence à elle-même, également appelé fermeture transitive.</span><span class="sxs-lookup"><span data-stu-id="7155c-148">The following example shows using recursive triggers to solve a self-referencing relationship (also known as transitive closure).</span></span> <span data-ttu-id="7155c-149">Par exemple, la table `emp_mgr` définit les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="7155c-149">For example, the table `emp_mgr` defines the following:</span></span>  
  
-   <span data-ttu-id="7155c-150">un salarié (`emp`) dans une entreprise ;</span><span class="sxs-lookup"><span data-stu-id="7155c-150">An employee (`emp`) in a company.</span></span>  
  
-   <span data-ttu-id="7155c-151">le responsable de chaque salarié (`mgr`) ;</span><span class="sxs-lookup"><span data-stu-id="7155c-151">The manager for each employee (`mgr`).</span></span>  
  
-   <span data-ttu-id="7155c-152">le nombre total de salariés dans l'arborescence de l'organisation rattachés à chaque salarié (`NoOfReports`).</span><span class="sxs-lookup"><span data-stu-id="7155c-152">The total number of employees in the organizational tree reporting to each employee (`NoOfReports`).</span></span>  
  
 <span data-ttu-id="7155c-153">Un déclencheur de mise à jour récursif peut être utilisé pour maintenir à jour la colonne `NoOfReports` au fur et à mesure de l'insertion de l'enregistrement de nouveaux salariés.</span><span class="sxs-lookup"><span data-stu-id="7155c-153">A recursive UPDATE trigger can be used to keep the `NoOfReports` column up-to-date as new employee records are inserted.</span></span> <span data-ttu-id="7155c-154">Le déclencheur INSERT met à jour la colonne `NoOfReports` de l'enregistrement du responsable, provoquant la mise à jour récursive de la colonne `NoOfReports` des autres enregistrements en remontant la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="7155c-154">The INSERT trigger updates the `NoOfReports` column of the manager record, which recursively updates the `NoOfReports` column of other records up the management hierarchy.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
-- Turn recursive triggers ON in the database.  
ALTER DATABASE AdventureWorks2012  
   SET RECURSIVE_TRIGGERS ON;  
GO  
CREATE TABLE dbo.emp_mgr (  
   emp char(30) PRIMARY KEY,  
    mgr char(30) NULL FOREIGN KEY REFERENCES emp_mgr(emp),  
    NoOfReports int DEFAULT 0  
);  
GO  
CREATE TRIGGER dbo.emp_mgrins ON dbo.emp_mgr  
FOR INSERT  
AS  
DECLARE @e char(30), @m char(30);  
DECLARE c1 CURSOR FOR  
   SELECT emp_mgr.emp  
   FROM   emp_mgr, inserted  
   WHERE emp_mgr.emp = inserted.mgr;  
  
OPEN c1;  
FETCH NEXT FROM c1 INTO @e;  
WHILE @@fetch_status = 0  
BEGIN  
   UPDATE dbo.emp_mgr  
   SET emp_mgr.NoOfReports = emp_mgr.NoOfReports + 1 -- Add 1 for newly  
   WHERE emp_mgr.emp = @e ;                           -- added employee.  
  
   FETCH NEXT FROM c1 INTO @e;  
END  
CLOSE c1;  
DEALLOCATE c1;  
GO  
-- This recursive UPDATE trigger works assuming:  
--   1. Only singleton updates on emp_mgr.  
--   2. No inserts in the middle of the org tree.  
CREATE TRIGGER dbo.emp_mgrupd ON dbo.emp_mgr FOR UPDATE  
AS  
IF UPDATE (mgr)  
BEGIN  
   UPDATE dbo.emp_mgr  
   SET emp_mgr.NoOfReports = emp_mgr.NoOfReports + 1 -- Increment mgr's  
   FROM inserted                            -- (no. of reports) by  
   WHERE emp_mgr.emp = inserted.mgr;         -- 1 for the new report.  
  
   UPDATE dbo.emp_mgr  
   SET emp_mgr.NoOfReports = emp_mgr.NoOfReports - 1 -- Decrement mgr's  
   FROM deleted                             -- (no. of reports) by 1  
   WHERE emp_mgr.emp = deleted.mgr;          -- for the new report.  
END  
GO  
-- Insert some test data rows.  
INSERT dbo.emp_mgr(emp, mgr) VALUES  
    ('Harry', NULL)  
    ,('Alice', 'Harry')  
    ,('Paul', 'Alice')  
    ,('Joe', 'Alice')  
    ,('Dave', 'Joe');  
GO  
SELECT emp,mgr,NoOfReports  
FROM dbo.emp_mgr;  
GO  
-- Change Dave's manager from Joe to Harry  
UPDATE dbo.emp_mgr SET mgr = 'Harry'  
WHERE emp = 'Dave';  
GO  
SELECT emp,mgr,NoOfReports FROM emp_mgr;  
  
GO  
```  
  
 <span data-ttu-id="7155c-155">Résultats avant la mise à jour :</span><span class="sxs-lookup"><span data-stu-id="7155c-155">Here are the results before the update.</span></span>  
  
```  
emp                            mgr                           NoOfReports  
------------------------------ ----------------------------- -----------  
Alice                          Harry                          2  
Dave                           Joe                            0  
Harry                          NULL                           1  
Joe                            Alice                          1  
Paul                           Alice                          0  
```  
  
 <span data-ttu-id="7155c-156">Résultats après la mise à jour :</span><span class="sxs-lookup"><span data-stu-id="7155c-156">Here are the results after the update.</span></span>  
  
```  
emp                            mgr                           NoOfReports  
------------------------------ ----------------------------- -----------  
Alice                          Harry                          2  
Dave                           Harry                          0  
Harry                          NULL                           2  
Joe                            Alice                          0  
Paul                           Alice                          0  
```  
  
 <span data-ttu-id="7155c-157">**Pour définir l'option nested triggers**</span><span class="sxs-lookup"><span data-stu-id="7155c-157">**To set the nested triggers option**</span></span>  
  
-   [<span data-ttu-id="7155c-158">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7155c-158">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
 <span data-ttu-id="7155c-159">**Pour définir l'option de base de données RECURSIVE_TRIGGERS**</span><span class="sxs-lookup"><span data-stu-id="7155c-159">**To set the RECURSIVE_TRIGGERS database option**</span></span>  
  
-   [<span data-ttu-id="7155c-160">ALTER DATABASE SET Options &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7155c-160">ALTER DATABASE SET Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-set-options)  
  
## <a name="see-also"></a><span data-ttu-id="7155c-161">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7155c-161">See Also</span></span>  
 <span data-ttu-id="7155c-162">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7155c-162">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 [<span data-ttu-id="7155c-163">Configurer l'option de configuration du serveur nested triggers</span><span class="sxs-lookup"><span data-stu-id="7155c-163">Configure the nested triggers Server Configuration Option</span></span>](../../database-engine/configure-windows/configure-the-nested-triggers-server-configuration-option.md)  
  
  
