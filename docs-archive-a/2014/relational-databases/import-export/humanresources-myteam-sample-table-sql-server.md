---
title: Exemple de table HumanResources.myTeam (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- myTeam sample table [SQL Server]
- bulk importing [SQL Server], examples
- bulk exporting [SQL Server], examples
ms.assetid: 27da45a0-c1f4-4bf4-ab24-6196e80d3834
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7d4e0cbbf42c2bdd25e3dd7c9577e4d0ec44549a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612337"
---
# <a name="humanresourcesmyteam-sample-table-sql-server"></a><span data-ttu-id="ac682-102">Exemple de table HumanResources.myTeam (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ac682-102">HumanResources.myTeam Sample Table (SQL Server)</span></span>
  <span data-ttu-id="ac682-103">Les exemples de code fournis au chapitre [Importation et exportation de données en bloc](bulk-import-and-export-of-data-sql-server.md) font généralement appel à une table de test spéciale nommée **myTeam**.</span><span class="sxs-lookup"><span data-stu-id="ac682-103">Many of the code examples in [Importing and Exporting Bulk Data](bulk-import-and-export-of-data-sql-server.md) require a special-purpose test table named **myTeam**.</span></span> <span data-ttu-id="ac682-104">Pour pouvoir mettre à exécution les exemples, vous devez d’abord créer la table **myTeam** dans le schéma **HumanResources** de la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ac682-104">Before you can run the examples, you must create the **myTeam** table in the **HumanResources** schema of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] <span data-ttu-id="ac682-105">est l’un des exemples de bases de données fournis dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac682-105">is one of the sample databases in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="ac682-106">La table **myTeam** contient les colonnes suivantes.</span><span class="sxs-lookup"><span data-stu-id="ac682-106">The **myTeam** table is contains the following columns.</span></span>  
  
|<span data-ttu-id="ac682-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="ac682-107">Column</span></span>|<span data-ttu-id="ac682-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="ac682-108">Data type</span></span>|<span data-ttu-id="ac682-109">Possibilité de valeurs nulles</span><span class="sxs-lookup"><span data-stu-id="ac682-109">Nullability</span></span>|<span data-ttu-id="ac682-110">Description</span><span class="sxs-lookup"><span data-stu-id="ac682-110">Description</span></span>|  
|------------|---------------|-----------------|-----------------|  
|<span data-ttu-id="ac682-111">**EmployeeID**</span><span class="sxs-lookup"><span data-stu-id="ac682-111">**EmployeeID**</span></span>|`smallint`|<span data-ttu-id="ac682-112">Non Null</span><span class="sxs-lookup"><span data-stu-id="ac682-112">Not null</span></span>|<span data-ttu-id="ac682-113">Clé primaire des lignes.</span><span class="sxs-lookup"><span data-stu-id="ac682-113">Primary key for the rows.</span></span> <span data-ttu-id="ac682-114">EmployeeID d'un membre de l'équipe.</span><span class="sxs-lookup"><span data-stu-id="ac682-114">Employee ID of a member of my team.</span></span>|  
|<span data-ttu-id="ac682-115">**Nom**</span><span class="sxs-lookup"><span data-stu-id="ac682-115">**Name**</span></span>|`nvarchar(50)`|<span data-ttu-id="ac682-116">Non Null</span><span class="sxs-lookup"><span data-stu-id="ac682-116">Not null</span></span>|<span data-ttu-id="ac682-117">Name est un membre de l'équipe.</span><span class="sxs-lookup"><span data-stu-id="ac682-117">Name of a member of my team.</span></span>|  
|<span data-ttu-id="ac682-118">**Titre**</span><span class="sxs-lookup"><span data-stu-id="ac682-118">**Title**</span></span>|`nvarchar(50)`|<span data-ttu-id="ac682-119">Nullable</span><span class="sxs-lookup"><span data-stu-id="ac682-119">Nullable</span></span>|<span data-ttu-id="ac682-120">Fonction occupée par l'employé au sein de l'équipe.</span><span class="sxs-lookup"><span data-stu-id="ac682-120">Title the employee performs on my team.</span></span>|  
|<span data-ttu-id="ac682-121">**Contexte**</span><span class="sxs-lookup"><span data-stu-id="ac682-121">**Background**</span></span>|`nvarchar(50)`|<span data-ttu-id="ac682-122">Non Null</span><span class="sxs-lookup"><span data-stu-id="ac682-122">Not null</span></span>|<span data-ttu-id="ac682-123">Date et heure de dernière mise à jour de la ligne</span><span class="sxs-lookup"><span data-stu-id="ac682-123">Date and time the row was last updated.</span></span> <span data-ttu-id="ac682-124">(Par défaut)</span><span class="sxs-lookup"><span data-stu-id="ac682-124">(Default)</span></span>|  
  
 <span data-ttu-id="ac682-125">**Pour créer HumanResources.myTeam**</span><span class="sxs-lookup"><span data-stu-id="ac682-125">**To create HumanResources.myTeam**</span></span>  
  
-   <span data-ttu-id="ac682-126">Utilisez les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] suivantes :</span><span class="sxs-lookup"><span data-stu-id="ac682-126">Use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    --Create HumanResources.MyTeam:   
    USE AdventureWorks;  
    GO  
    CREATE TABLE HumanResources.myTeam   
    (EmployeeID smallint NOT NULL,  
    Name nvarchar(50) NOT NULL,  
    Title nvarchar(50) NULL,  
    Background nvarchar(50) NOT NULL DEFAULT ''  
    );  
    GO  
    ```  
  
 <span data-ttu-id="ac682-127">**Pour remplir HumanResources.myTeam**</span><span class="sxs-lookup"><span data-stu-id="ac682-127">**To populate HumanResources.myTeam**</span></span>  
  
-   <span data-ttu-id="ac682-128">Exécutez les instructions `INSERT` suivantes pour remplir la table de deux lignes :</span><span class="sxs-lookup"><span data-stu-id="ac682-128">Execute following `INSERT` statements to populate the table with two rows:</span></span>  
  
    ```  
    USE AdventureWorks;  
    GO  
    INSERT INTO HumanResources.myTeam(EmployeeID,Name,Title,Background)  
       VALUES(77,'Mia Doppleganger','Administrative Assistant','Microsoft Office');  
    GO  
    INSERT INTO HumanResources.myTeam(EmployeeID,Name,Title,Background)  
       VALUES(49,'Hirum Mollicat','I.T. Specialist','Report Writing and Data Mining');  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="ac682-129">Ces instructions ignorent la quatrième colonne, `Background`.</span><span class="sxs-lookup"><span data-stu-id="ac682-129">These statements skip the fourth column, `Background`.</span></span> <span data-ttu-id="ac682-130">Celle-ci a une valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="ac682-130">This has a default value.</span></span> <span data-ttu-id="ac682-131">En l'ignorant, l'instruction `INSERT` laisse cette colonne vide.</span><span class="sxs-lookup"><span data-stu-id="ac682-131">Skipping this column causes this `INSERT` statement to leave this column blank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac682-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ac682-132">See Also</span></span>  
 [<span data-ttu-id="ac682-133">Importation et exportation en bloc de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ac682-133">Bulk Import and Export of Data &#40;SQL Server&#41;</span></span>](bulk-import-and-export-of-data-sql-server.md)  
  
  
