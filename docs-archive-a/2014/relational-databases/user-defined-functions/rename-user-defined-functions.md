---
title: Renommer des fonctions définies par l’utilisateur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: c2695a5c-9cc5-4b18-8771-53027ca9a9af
author: rothja
ms.author: jroth
ms.openlocfilehash: ec923be64cf7819c4018ebda71a472f58b29cf8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615073"
---
# <a name="rename-user-defined-functions"></a><span data-ttu-id="b93fe-102">Renommer des fonctions définies par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="b93fe-102">Rename User-defined Functions</span></span>
  <span data-ttu-id="b93fe-103">Vous pouvez renommer les fonctions définies par l'utilisateur dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b93fe-103">You can rename user-defined functions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="b93fe-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="b93fe-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b93fe-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="b93fe-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b93fe-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="b93fe-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b93fe-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b93fe-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b93fe-108">**Pour renommer des fonctions définies par l'utilisateur, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="b93fe-108">**To rename user-defined functions, using:**</span></span>  
  
     [<span data-ttu-id="b93fe-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b93fe-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b93fe-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b93fe-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b93fe-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="b93fe-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b93fe-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="b93fe-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b93fe-113">Les noms de fonction doivent respecter les règles applicables aux [identificateurs](../databases/database-identifiers.md).</span><span class="sxs-lookup"><span data-stu-id="b93fe-113">Function names must comply with the rules for [identifiers](../databases/database-identifiers.md).</span></span>  
  
-   <span data-ttu-id="b93fe-114">Le fait de renommer une fonction définie par l’utilisateur ne modifie pas le nom de l’objet correspondant dans la colonne de définition de l’affichage catalogue **sys.sql_modules** .</span><span class="sxs-lookup"><span data-stu-id="b93fe-114">Renaming a user-defined function will not change the name of the corresponding object name in the definition column of the **sys.sql_modules** catalog view.</span></span> <span data-ttu-id="b93fe-115">Par conséquent, nous vous recommandons de ne pas renommer ce type d'objet.</span><span class="sxs-lookup"><span data-stu-id="b93fe-115">Therefore, we recommend that you do not rename this object type.</span></span> <span data-ttu-id="b93fe-116">À la place, supprimez, puis recréez la procédure stockée avec son nouveau nom.</span><span class="sxs-lookup"><span data-stu-id="b93fe-116">Instead, drop and re-create the stored procedure with its new name.</span></span>  
  
-   <span data-ttu-id="b93fe-117">La modification du nom ou de la définition d'une fonction définie par l'utilisateur peut entraîner l'échec de ses objets dépendants si ceux-ci n'ont pas été mis à jour pour refléter les modifications apportées à la fonction.</span><span class="sxs-lookup"><span data-stu-id="b93fe-117">Changing the name or definition of a user-defined function can cause dependent objects to fail when the objects are not updated to reflect the changes that have been made to the function.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b93fe-118">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b93fe-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b93fe-119">Autorisations</span><span class="sxs-lookup"><span data-stu-id="b93fe-119">Permissions</span></span>  
 <span data-ttu-id="b93fe-120">Pour supprimer la fonction, un utilisateur doit disposer de l'autorisation ALTER sur le schéma auquel la fonction appartient ou de l'autorisation CONTROL sur la fonction.</span><span class="sxs-lookup"><span data-stu-id="b93fe-120">To drop the function, requires either ALTER permission on the schema to which the function belongs or CONTROL permission on the function.</span></span> <span data-ttu-id="b93fe-121">Pour recréer la fonction, un utilisateur doit disposer de l'autorisation CREATE FUNCTION dans la base de données et de l'autorisation ALTER sur le schéma dans lequel la fonction est en cours de création.</span><span class="sxs-lookup"><span data-stu-id="b93fe-121">To re-create the function, requires CREATE FUNCTION permission in the database and ALTER permission on the schema in which the function is being created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b93fe-122">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b93fe-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-user-defined-functions"></a><span data-ttu-id="b93fe-123">Pour renommer des fonctions définies par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="b93fe-123">To rename user-defined functions</span></span>  
  
1.  <span data-ttu-id="b93fe-124">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) en regard de la base de données qui contient la fonction que souhaitez renommer, puis</span><span class="sxs-lookup"><span data-stu-id="b93fe-124">In **Object Explorer**, click the plus sign next to the database that contains the function you wish to rename and then</span></span>  
  
2.  <span data-ttu-id="b93fe-125">Cliquez sur le signe plus (+) en regard du dossier **Programmabilité** .</span><span class="sxs-lookup"><span data-stu-id="b93fe-125">Click the plus sign next to the **Programmability** folder.</span></span>  
  
3.  <span data-ttu-id="b93fe-126">Cliquez sur le signe plus (+) en regard du dossier qui contient la fonction à renommer :</span><span class="sxs-lookup"><span data-stu-id="b93fe-126">Click the plus sign next to the folder that contains the function you wish to rename:</span></span>  
  
    -   <span data-ttu-id="b93fe-127">Fonction table</span><span class="sxs-lookup"><span data-stu-id="b93fe-127">Table-valued Function</span></span>  
  
    -   <span data-ttu-id="b93fe-128">Fonction scalaire</span><span class="sxs-lookup"><span data-stu-id="b93fe-128">Scalar-valued Function</span></span>  
  
    -   <span data-ttu-id="b93fe-129">Fonction d'agrégation</span><span class="sxs-lookup"><span data-stu-id="b93fe-129">Aggregate Function</span></span>  
  
4.  <span data-ttu-id="b93fe-130">Cliquez avec le bouton droit sur la fonction que vous voulez renommer et sélectionnez **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="b93fe-130">Right-click the function you wish to rename and select **Rename**.</span></span>  
  
5.  <span data-ttu-id="b93fe-131">Entrez le nouveau nom de la fonction.</span><span class="sxs-lookup"><span data-stu-id="b93fe-131">Enter the function's new name.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b93fe-132">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b93fe-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="b93fe-133">**Pour renommer des fonctions définies par l'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="b93fe-133">**To rename user-defined functions**</span></span>  
  
 <span data-ttu-id="b93fe-134">Cette tâche ne peut pas être effectuée à l'aide d'instructions Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="b93fe-134">This task cannot be performed using Transact-SQL statements.</span></span> <span data-ttu-id="b93fe-135">Pour renommer une fonction définie par l'utilisateur à l'aide de Transact-SQL, vous devez d'abord supprimer la fonction existante puis la recréer sous son nouveau nom.</span><span class="sxs-lookup"><span data-stu-id="b93fe-135">To rename a user-defined function using Transact-SQL, you must first delete the existing function and then re-create it with the new name.</span></span> <span data-ttu-id="b93fe-136">Vérifiez que l’ensemble du code et des applications qui utilisaient l’ancien nom de la fonction utilisent désormais le nouveau nom.</span><span class="sxs-lookup"><span data-stu-id="b93fe-136">Ensure that all code and applications that used the function's old name now use the new name.</span></span>  
  
 <span data-ttu-id="b93fe-137">Pour plus d’informations, consultez [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) et [DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b93fe-137">For more information, see [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) and [DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b93fe-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b93fe-138">See Also</span></span>  
 <span data-ttu-id="b93fe-139">[sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b93fe-139">[sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) </span></span>  
 [<span data-ttu-id="b93fe-140">Afficher des fonctions définies par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="b93fe-140">View User-defined Functions</span></span>](user-defined-functions.md)  
  
  
