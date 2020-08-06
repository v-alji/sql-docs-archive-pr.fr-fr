---
title: 'Leçon 1 : Création des objets de base de données | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: t-sql
ms.topic: conceptual
ms.assetid: 9fb8656b-0e4e-4ada-b404-4db4d3eea995
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 172fdbcaedc10f9c359befd48ed09ec825aea9bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704596"
---
# <a name="lesson-1-creating-database-objects"></a><span data-ttu-id="b216e-102">Leçon 1 : Création des objets de base de données</span><span class="sxs-lookup"><span data-stu-id="b216e-102">Lesson 1: Creating Database Objects</span></span>
  <span data-ttu-id="b216e-103">Cette leçon vous montre comment créer une base de données, une table dans la base de données, puis accéder aux données et les modifier dans la table.</span><span class="sxs-lookup"><span data-stu-id="b216e-103">This lesson shows you how to create a database, create a table in the database, and then access and change the data in the table.</span></span> <span data-ttu-id="b216e-104">Étant donné que cette leçon est une introduction à l’utilisation de [!INCLUDE[tsql](../includes/tsql-md.md)], elle n’utilise pas ni ne décrit les nombreuses options disponibles pour ces instructions.</span><span class="sxs-lookup"><span data-stu-id="b216e-104">Because this lesson is an introduction to using [!INCLUDE[tsql](../includes/tsql-md.md)], it does not use or describe the many options that are available for these statements.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="b216e-105">les instructions peuvent être écrites et soumises au [!INCLUDE[ssDE](../includes/ssde-md.md)] comme suit :</span><span class="sxs-lookup"><span data-stu-id="b216e-105">statements can be written and submitted to the [!INCLUDE[ssDE](../includes/ssde-md.md)] in the following ways:</span></span>  
  
-   <span data-ttu-id="b216e-106">À l'aide de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b216e-106">By using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="b216e-107">Ce didacticiel suppose que vous utilisez [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], mais vous pouvez aussi utiliser [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] Express, disponible gratuitement en téléchargement à partir du [Centre de téléchargement Microsoft](https://www.microsoft.com/download/details.aspx?id=14630).</span><span class="sxs-lookup"><span data-stu-id="b216e-107">This tutorial assumes that you are using [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], but you can also use [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] Express, which is available as a free download from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=14630).</span></span>  
  
-   <span data-ttu-id="b216e-108">À l’aide de [l’utilitaire sqlcmd](../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="b216e-108">By using the [sqlcmd utility](../tools/sqlcmd-utility.md).</span></span>  
  
-   <span data-ttu-id="b216e-109">En vous connectant à partir d'une application que vous créez.</span><span class="sxs-lookup"><span data-stu-id="b216e-109">By connecting from an application that you create.</span></span>  
  
 <span data-ttu-id="b216e-110">Le code s’exécute sur le [!INCLUDE[ssDE](../includes/ssde-md.md)] de la même façon et avec les mêmes autorisations, quelle que soit la manière dont vous soumettez les instructions de code.</span><span class="sxs-lookup"><span data-stu-id="b216e-110">The code executes on the [!INCLUDE[ssDE](../includes/ssde-md.md)] in the same way and with the same permissions, regardless of how you submit the code statements.</span></span>  
  
 <span data-ttu-id="b216e-111">Pour exécuter des instructions [!INCLUDE[tsql](../includes/tsql-md.md)] dans [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], ouvrez [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] et connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b216e-111">To run [!INCLUDE[tsql](../includes/tsql-md.md)] statements in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], open [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] and connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)].</span></span>  
  
 <span data-ttu-id="b216e-112">Cette leçon contient les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="b216e-112">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="b216e-113">Création d’une base de données &#40;Didacticiel&#41;</span><span class="sxs-lookup"><span data-stu-id="b216e-113">Creating a Database &#40;Tutorial&#41;</span></span>](lesson-1-1-creating-a-database.md)  
  
-   [<span data-ttu-id="b216e-114">Création d’une table &#40;Didacticiel&#41;</span><span class="sxs-lookup"><span data-stu-id="b216e-114">Creating a Table &#40;Tutorial&#41;</span></span>](lesson-1-2-creating-a-table.md)  
  
-   [<span data-ttu-id="b216e-115">Insertion et mise à jour des données dans une table &#40;Didacticiel&#41;</span><span class="sxs-lookup"><span data-stu-id="b216e-115">Inserting and Updating Data in a Table &#40;Tutorial&#41;</span></span>](lesson-1-3-inserting-and-updating-data-in-a-table.md)  
  
-   [<span data-ttu-id="b216e-116">Lecture des données dans une table &#40;Didacticiel&#41;</span><span class="sxs-lookup"><span data-stu-id="b216e-116">Reading the Data in a Table &#40;Tutorial&#41;</span></span>](lesson-1-4-reading-the-data-in-a-table.md)  
  
-   [<span data-ttu-id="b216e-117">Résumé : Création des objets de base de données</span><span class="sxs-lookup"><span data-stu-id="b216e-117">Summary: Creating Database Objects</span></span>](lesson-1-5-summary-creating-database-objects.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b216e-118">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="b216e-118">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b216e-119">Création d’une base de données &#40;Didacticiel&#41;</span><span class="sxs-lookup"><span data-stu-id="b216e-119">Creating a Database &#40;Tutorial&#41;</span></span>](lesson-1-1-creating-a-database.md)  
  
  
