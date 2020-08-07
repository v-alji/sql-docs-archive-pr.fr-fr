---
title: Création d’une base de données (tutoriel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- tutorial creating a database
ms.assetid: e1e2c83f-dfad-4bb8-aa7a-09d3f69517ae
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 99d5439c289b5d4e71786d4c6734f158f6bba371
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611437"
---
# <a name="creating-a-database-tutorial"></a><span data-ttu-id="ed8f5-102">Création d'une base de données (Didacticiel)</span><span class="sxs-lookup"><span data-stu-id="ed8f5-102">Creating a Database (Tutorial)</span></span>
  <span data-ttu-id="ed8f5-103">Comme de nombreuses instructions [!INCLUDE[tsql](../includes/tsql-md.md)], l'instruction CREATE DATABASE nécessite un paramètre obligatoire : le nom de la base de données.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-103">Like many [!INCLUDE[tsql](../includes/tsql-md.md)] statements, the CREATE DATABASE statement has a required parameter: the name of the database.</span></span> <span data-ttu-id="ed8f5-104">L'instruction CREATE DATABASE possède aussi de nombreux paramètres facultatifs, tels que l'emplacement du disque où vous souhaitez copier les fichiers de base de données.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-104">CREATE DATABASE also has many optional parameters, such as the disk location where you want to put the database files.</span></span> <span data-ttu-id="ed8f5-105">Lorsque vous exécutez l'instruction CREATE DATABASE sans les paramètres facultatifs, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] utilise les valeurs par défaut pour un grand nombre de ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-105">When you execute CREATE DATABASE without the optional parameters, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] uses default values for many of these parameters.</span></span> <span data-ttu-id="ed8f5-106">Ce didacticiel utilise très peu de paramètres de syntaxe facultatifs.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-106">This tutorial uses very few of the optional syntax parameters.</span></span>  
  
### <a name="to-create-a-database"></a><span data-ttu-id="ed8f5-107">Pour créer une base de données</span><span class="sxs-lookup"><span data-stu-id="ed8f5-107">To create a database</span></span>  
  
1.  <span data-ttu-id="ed8f5-108">Dans une fenêtre de l'Éditeur de requête, tapez mais sans l'exécuter le code suivant :</span><span class="sxs-lookup"><span data-stu-id="ed8f5-108">In a Query Editor window, type but do not execute the following code:</span></span>  
  
    ```  
    CREATE DATABASE TestData  
    GO  
    ```  
  
2.  <span data-ttu-id="ed8f5-109">Utilisez le pointeur pour sélectionner les mots `CREATE DATABASE`, et appuyez sur la touche **F1**.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-109">Use the pointer to select the words `CREATE DATABASE`, and then press **F1**.</span></span> <span data-ttu-id="ed8f5-110">La rubrique correspondante de la documentation en ligne de SQL Server doit s'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-110">The CREATE DATABASE topic in SQL Server Books Online should open.</span></span> <span data-ttu-id="ed8f5-111">Vous pouvez faire appel à cette technique pour rechercher la syntaxe finale de CREATE DATABASE et pour les autres instructions utilisées dans ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-111">You can use this technique to find the complete syntax for CREATE DATABASE and for the other statements that are used in this tutorial.</span></span>  
  
3.  <span data-ttu-id="ed8f5-112">Dans l'Éditeur de requête, appuyez sur la touche **F5** pour exécuter l'instruction et créer une base de données nommée `TestData`.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-112">In Query Editor, press **F5** to execute the statement and create a database named `TestData`.</span></span>  
  
 <span data-ttu-id="ed8f5-113">Lorsque vous créez une base de données, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] effectue une copie de la base de données **model** et remplace le nom de la copie par le nom de la base de données.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-113">When you create a database, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] makes a copy of the **model** database, and renames the copy to the database name.</span></span> <span data-ttu-id="ed8f5-114">Cette opération ne doit prendre que quelques secondes, sauf si vous spécifiez une taille initiale importante pour la base de données comme paramètre facultatif.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-114">This operation should only take several seconds, unless you specify a large initial size of the database as an optional parameter.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ed8f5-115">Le mot clé GO sépare les instructions si plus d'une instruction est envoyée dans un même traitement.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-115">The keyword GO separates statements when more than one statement is submitted in a single batch.</span></span> <span data-ttu-id="ed8f5-116">GO est facultatif lorsque le traitement contient uniquement une seule instruction.</span><span class="sxs-lookup"><span data-stu-id="ed8f5-116">GO is optional when the batch contains only one statement.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ed8f5-117">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="ed8f5-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ed8f5-118">Création d’une table &#40;Didacticiel&#41;</span><span class="sxs-lookup"><span data-stu-id="ed8f5-118">Creating a Table &#40;Tutorial&#41;</span></span>](lesson-1-2-creating-a-table.md)  
  
## <a name="see-also"></a><span data-ttu-id="ed8f5-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ed8f5-119">See Also</span></span>  
 [<span data-ttu-id="ed8f5-120">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ed8f5-120">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
  
