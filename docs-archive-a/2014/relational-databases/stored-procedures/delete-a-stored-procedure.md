---
title: Supprimer une procédure stockée | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- removing stored procedures
- stored procedures [SQL Server], deleting
- deleting stored procedures
ms.assetid: 232dbf4d-392a-406f-af3a-579518cd8e46
author: stevestein
ms.author: sstein
ms.openlocfilehash: 418e68d4bb7c6ba6632767a554aea72e85726840
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613353"
---
# <a name="delete-a-stored-procedure"></a><span data-ttu-id="52b44-102">Supprimer une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="52b44-102">Delete a Stored Procedure</span></span>
    
##  <a name="this-topic-describes-how-to-delete-a-stored-procedure-in-sscurrent-by-using-ssmanstudiofull-or-tsql"></a><a name="Top"></a> <span data-ttu-id="52b44-103">Cette rubrique explique comment supprimer une procédure stockée dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="52b44-103">This topic describes how to delete a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="52b44-104">**Avant de commencer :**  [Limitations et restrictions](#Restrictions), [sécurité](#Security)</span><span class="sxs-lookup"><span data-stu-id="52b44-104">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="52b44-105">**Pour supprimer une procédure avec :**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="52b44-105">**To delete a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="52b44-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="52b44-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="52b44-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="52b44-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="52b44-108">La suppression d'une procédure peut entraîner l'échec des scripts et des objets dépendants quand ceux-ci n'ont pas été mis à jour pour refléter la suppresion de la procédure.</span><span class="sxs-lookup"><span data-stu-id="52b44-108">Deleting a procedure can cause dependent objects and scripts to fail when the objects and scripts are not updated to reflect the removal of the procedure.</span></span> <span data-ttu-id="52b44-109">Cependant, si vous créez une nouvelle procédure ayant le même nom et les mêmes paramètres pour remplacer celle qui a été supprimée, les autres objets qui y font référence pourront s'exécuter correctement.</span><span class="sxs-lookup"><span data-stu-id="52b44-109">However, if a new procedure of the same name and the same parameters is created to replace the one that was deleted, other objects that reference it will still process successfully.</span></span> <span data-ttu-id="52b44-110">Pour plus d’informations, consultez [Afficher les dépendances d’une procédure stockée](view-the-dependencies-of-a-stored-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="52b44-110">For more information, see [View the Dependencies of a Stored Procedure](view-the-dependencies-of-a-stored-procedure.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="52b44-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="52b44-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="52b44-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="52b44-112">Permissions</span></span>  
 <span data-ttu-id="52b44-113">Exige l'autorisation ALTER sur le schéma auquel appartient la procédure ou l'autorisation CONTROL sur la procédure.</span><span class="sxs-lookup"><span data-stu-id="52b44-113">Requires ALTER permission on the schema to which the procedure belongs, or CONTROL permission on the procedure.</span></span>  
  
##  <a name="how-to-delete-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="52b44-114">Pour supprimer une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="52b44-114">How to Delete a Stored Procedure</span></span>  
 <span data-ttu-id="52b44-115">Vous pouvez utiliser l'un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="52b44-115">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="52b44-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="52b44-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="52b44-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="52b44-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="52b44-118">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="52b44-118">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="52b44-119">**Pour supprimer une procédure dans l'Explorateur d'objets**</span><span class="sxs-lookup"><span data-stu-id="52b44-119">**To delete a procedure in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="52b44-120">Dans l'Explorateur d'objets, connectez-vous à une instance de [!INCLUDE[ssDE](../../includes/ssde-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="52b44-120">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="52b44-121">Développez **Bases de données**, développez la base de données à laquelle appartient la procédure, puis développez **Programmabilité**.</span><span class="sxs-lookup"><span data-stu-id="52b44-121">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="52b44-122">Développez **Procédures stockées**, cliquez avec le bouton droit sur la procédure à supprimer, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="52b44-122">Expand **Stored Procedures**, right-click the procedure to remove, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="52b44-123">Pour afficher les objets qui dépendent de la procédure, cliquez sur **Afficher les dépendances**.</span><span class="sxs-lookup"><span data-stu-id="52b44-123">To view objects that depend on the procedure, click **Show Dependencies**.</span></span>  
  
5.  <span data-ttu-id="52b44-124">Vérifiez que la procédure correcte est sélectionnée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="52b44-124">Confirm the correct procedure is selected, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="52b44-125">Supprimez les références à la procédure à partir de tous les objets et scripts dépendants.</span><span class="sxs-lookup"><span data-stu-id="52b44-125">Remove references to the procedure from any dependent objects and scripts.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="52b44-126">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="52b44-126">Using Transact-SQL</span></span>  
 <span data-ttu-id="52b44-127">**Pour supprimer une procédure dans l'Éditeur de requête**</span><span class="sxs-lookup"><span data-stu-id="52b44-127">**To delete a procedure in Query Editor**</span></span>  
  
1.  <span data-ttu-id="52b44-128">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="52b44-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="52b44-129">Développez **Bases de données**, développez la base de données à laquelle appartient la procédure, ou, dans la barre d'outils, sélectionnez la base de données dans la liste des bases de données disponibles.</span><span class="sxs-lookup"><span data-stu-id="52b44-129">Expand **Databases**, expand the database in which the procedure belongs, or, from the tool bar, select the database from the list of available databases.</span></span>  
  
3.  <span data-ttu-id="52b44-130">Dans le menu Fichier, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="52b44-130">On the File menu, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="52b44-131">Obtient le nom de la procédure stockée à supprimer dans la base de données active.</span><span class="sxs-lookup"><span data-stu-id="52b44-131">Obtain the name of stored procedure to remove in the current database.</span></span> <span data-ttu-id="52b44-132">Dans l'Explorateur d'objets, développez **Programmabilité** , puis **Procédures stockées**.</span><span class="sxs-lookup"><span data-stu-id="52b44-132">From Object Explorer, expand **Programmability** and then expand **Stored Procedures**.</span></span> <span data-ttu-id="52b44-133">Sinon, dans l'éditeur de requête, exécutez l'instruction suivante.</span><span class="sxs-lookup"><span data-stu-id="52b44-133">Alternatively, in the query editor, run the following statement.</span></span>  
  
    ```sql  
    SELECT name AS procedure_name   
        ,SCHEMA_NAME(schema_id) AS schema_name  
        ,type_desc  
        ,create_date  
        ,modify_date  
    FROM sys.procedures;  
    ```  
  
5.  <span data-ttu-id="52b44-134">Copiez et collez l'exemple suivant dans l'éditeur de requête et insérez un nom de procédure stockée à supprimer de la base de données active.</span><span class="sxs-lookup"><span data-stu-id="52b44-134">Copy and paste the following example into the query editor and insert a stored procedure name to delete from the current database.</span></span>  
  
    ```sql  
    DROP PROCEDURE <stored procedure name>;  
    GO  
    ```  
  
6.  <span data-ttu-id="52b44-135">Supprimez les références à la procédure à partir de tous les objets et scripts dépendants.</span><span class="sxs-lookup"><span data-stu-id="52b44-135">Remove references to the procedure from any dependent objects and scripts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52b44-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="52b44-136">See Also</span></span>  
 <span data-ttu-id="52b44-137">[Créer une procédure stockée](create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="52b44-137">[Create a Stored Procedure](create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="52b44-138">[Modifier une procédure stockée](modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="52b44-138">[Modify a Stored Procedure](modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="52b44-139">[Renommer une procédure stockée](rename-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="52b44-139">[Rename a Stored Procedure](rename-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="52b44-140">[Afficher la définition d'une procédure stockée](view-the-definition-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="52b44-140">[View the Definition of a Stored Procedure](view-the-definition-of-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="52b44-141">[Afficher les dépendances d’une procédure stockée](view-the-dependencies-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="52b44-141">[View the Dependencies of a Stored Procedure](view-the-dependencies-of-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="52b44-142">DROP PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="52b44-142">DROP PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-procedure-transact-sql)  
  
  
