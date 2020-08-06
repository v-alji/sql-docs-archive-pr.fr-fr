---
title: 'Didacticiel : utilisation du type de données hierarchyid | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- tutorials [hierarchyid]
- hierarchyid [Database Engine], tutorial
ms.assetid: 5a7f7cfd-7faf-439f-8085-8fd6bf7db355
author: stevestein
ms.author: sstein
ms.openlocfilehash: a735b4c2b51e1c680c8129647733ce1efd9f9984
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603361"
---
# <a name="tutorial-using-the-hierarchyid-data-type"></a><span data-ttu-id="9c724-102">Didacticiel : utilisation du type de données hierarchyid</span><span class="sxs-lookup"><span data-stu-id="9c724-102">Tutorial: Using the hierarchyid Data Type</span></span>
  <span data-ttu-id="9c724-103">Ce didacticiel s'adresse aux utilisateurs familiers de [!INCLUDE[tsql](../../includes/tsql-md.md)], mais qui n'ont jamais utilisé le type de données `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="9c724-103">This tutorial is intended for users who are experienced with [!INCLUDE[tsql](../../includes/tsql-md.md)], but are new to the `hierarchyid` data type.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="9c724-104">Contenu du didacticiel</span><span class="sxs-lookup"><span data-stu-id="9c724-104">What You Will Learn</span></span>  
 <span data-ttu-id="9c724-105">Ce didacticiel est divisé en deux leçons :</span><span class="sxs-lookup"><span data-stu-id="9c724-105">This tutorial is divided into two lessons:</span></span>  
  
 [<span data-ttu-id="9c724-106">Leçon 1 : conversion d’une table en structure hiérarchique</span><span class="sxs-lookup"><span data-stu-id="9c724-106">Lesson 1: Converting a Table to a Hierarchical Structure</span></span>](lesson-1-converting-a-table-to-a-hierarchical-structure.md)  
 <span data-ttu-id="9c724-107">Dans cette leçon, vous prenez une table d'employés existante structurée en hiérarchie parent/enfant et vous déplacez les données dans une nouvelle table qui représente la hiérarchie en utilisant le type de données `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="9c724-107">In this lesson, you take an existing employee table that is structured as a parent/child hierarchy and move the data into a new table that represents the hierarchy by using the `hierarchyid` data type.</span></span> <span data-ttu-id="9c724-108">Cette leçon requiert l'exemple de base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9c724-108">This lesson requires the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
 [<span data-ttu-id="9c724-109">Leçon 2 : création et gestion de données dans une table hiérarchique</span><span class="sxs-lookup"><span data-stu-id="9c724-109">Lesson 2: Creating and Managing Data in a Hierarchical Table</span></span>](lesson-2-creating-and-managing-data-in-a-hierarchical-table.md)  
 <span data-ttu-id="9c724-110">Dans cette leçon, vous créez une table en utilisant le type de données `hierarchyid` pour représenter la structure de hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="9c724-110">In this lesson, you create a table by using the `hierarchyid` data type to represent the hierarchy structure.</span></span> <span data-ttu-id="9c724-111">Vous manipulez ensuite les données dans la table en utilisant les méthodes hiérarchiques.</span><span class="sxs-lookup"><span data-stu-id="9c724-111">Then, you manipulate the data in the table by using the hierarchical methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c724-112">Spécifications</span><span class="sxs-lookup"><span data-stu-id="9c724-112">Requirements</span></span>  
 <span data-ttu-id="9c724-113">Les programmes suivants doivent être installés sur votre système :</span><span class="sxs-lookup"><span data-stu-id="9c724-113">Your system must have the following installed:</span></span>  
  
-   <span data-ttu-id="9c724-114">Toute édition de [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="9c724-114">Any edition of [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or later.</span></span>  
  
-   <span data-ttu-id="9c724-115">[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] Express.</span><span class="sxs-lookup"><span data-stu-id="9c724-115">Either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] Express.</span></span>  
  
-   <span data-ttu-id="9c724-116">Internet Explorer 6 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="9c724-116">Internet Explorer 6 or a later version.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c724-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9c724-117">See Also</span></span>  
 <span data-ttu-id="9c724-118">[Didacticiel : Prise en main avec le Moteur de base de données](../tutorial-getting-started-with-the-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="9c724-118">[Tutorial: Getting Started with the Database Engine](../tutorial-getting-started-with-the-database-engine.md) </span></span>  
 <span data-ttu-id="9c724-119">[Didacticiel : écriture d’instructions Transact-SQL](../../t-sql/tutorial-writing-transact-sql-statements.md) </span><span class="sxs-lookup"><span data-stu-id="9c724-119">[Tutorial: Writing Transact-SQL Statements](../../t-sql/tutorial-writing-transact-sql-statements.md) </span></span>  
 <span data-ttu-id="9c724-120">[Référence de la méthode de type de données hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) </span><span class="sxs-lookup"><span data-stu-id="9c724-120">[hierarchyid Data Type Method Reference](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) </span></span>  
 <span data-ttu-id="9c724-121">[&#40;de données hiérarchiques SQL Server&#41;](../hierarchical-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9c724-121">[Hierarchical Data &#40;SQL Server&#41;](../hierarchical-data-sql-server.md) </span></span>  
 [<span data-ttu-id="9c724-122">hierarchyid &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9c724-122">hierarchyid &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/hierarchyid-data-type-method-reference)  
  
  
