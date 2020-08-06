---
title: Générer un script pour une table | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: ea88d736-849e-4368-b55d-06aeee097bf3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 247c839d83768756c57297d47f952401a1c8fd46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603749"
---
# <a name="script-a-table"></a><span data-ttu-id="a3a52-102">Générer un script pour une table</span><span class="sxs-lookup"><span data-stu-id="a3a52-102">Script a Table</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="a3a52-103">peut créer des scripts pour sélectionner, insérer, mettre à jour et supprimer des tables et également pour créer, modifier, supprimer ou exécuter des procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="a3a52-103">can create scripts to select, insert, update, and delete tables, and to create, alter, drop, or execute stored procedures.</span></span>  
  
 <span data-ttu-id="a3a52-104">Vous pouvez parfois avoir besoin d'utiliser un script avec plusieurs options permettant, par exemple, de supprimer et de créer une procédure ou bien de créer une table puis de la modifier.</span><span class="sxs-lookup"><span data-stu-id="a3a52-104">Sometimes you want a script with multiple options, such as drop a procedure and then create a procedure, or create a table then alter a table.</span></span> <span data-ttu-id="a3a52-105">Pour créer des scripts combinés, enregistrez le premier script dans une fenêtre de l’Éditeur de requête et le second dans le Presse-papiers afin de le copier dans la fenêtre après le premier script.</span><span class="sxs-lookup"><span data-stu-id="a3a52-105">To create combined scripts, save the first script to a Query Editor window and the second to the clipboard so you can paste it into the window after the first script.</span></span>  
  
## <a name="creating-an-update-script"></a><span data-ttu-id="a3a52-106">Création d'un script de mise à jour</span><span class="sxs-lookup"><span data-stu-id="a3a52-106">Creating an Update Script</span></span>  
  
#### <a name="to-create-the-insert-script-for-a-table"></a><span data-ttu-id="a3a52-107">Pour créer le script d'insertion pour une table</span><span class="sxs-lookup"><span data-stu-id="a3a52-107">To create the insert script for a table</span></span>  
  
1.  <span data-ttu-id="a3a52-108">Dans l’Explorateur d’objets, développez votre serveur, puis **Bases de données**, [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]et enfin, **Tables**, cliquez avec le bouton droit sur **HumanResources.Employee**, puis pointez sur **Générer un script de la table en tant que**.</span><span class="sxs-lookup"><span data-stu-id="a3a52-108">In Object Explorer, expand your server, expand **Databases**, expand [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], expand **Tables**, right-click **HumanResources.Employee**, and then point to **Script Table As**.</span></span>  
  
2.  <span data-ttu-id="a3a52-109">Le menu contextuel propose sept options de script : **CREATE To**, **DROP To**, **DROP and CREATE To**, **SELECT To**, **INSERT To**, **UPDATE To**et **DELETE To**.</span><span class="sxs-lookup"><span data-stu-id="a3a52-109">The shortcut menu has seven available scripting options: **CREATE To**, **DROP To**, **DROP and CREATE To**, **SELECT To**, **INSERT To**, **UPDATE To**, and **DELETE To**.</span></span> <span data-ttu-id="a3a52-110">Pointez sur **UPDATE To**, puis cliquez sur **Nouvelle fenêtre d’éditeur de requête**.</span><span class="sxs-lookup"><span data-stu-id="a3a52-110">Point to **UPDATE To**, and then click **New Query Editor Window**.</span></span>  
  
3.  <span data-ttu-id="a3a52-111">Une nouvelle fenêtre de l'Éditeur de requête s'ouvre et présente la connexion établie ainsi que l'instruction de mise à jour dans sa totalité.</span><span class="sxs-lookup"><span data-stu-id="a3a52-111">A new Query Editor window opens, makes a connection, and presents the entire update statement.</span></span>  
  
     <span data-ttu-id="a3a52-112">Cet exercice montre comment la fonction de création de script peut faire plus que simplement automatiser la création d'une table ou d'une procédure stockée au moyen d'un script.</span><span class="sxs-lookup"><span data-stu-id="a3a52-112">This exercise demonstrates how the scripting feature can do more than just script the creation of a table or stored procedure.</span></span> <span data-ttu-id="a3a52-113">Cette nouvelle fonctionnalité peut vous aider à ajouter rapidement des scripts de manipulation de données à votre projet et à exécuter facilement des procédures stockées au moyen d'un script.</span><span class="sxs-lookup"><span data-stu-id="a3a52-113">This new feature can help you quickly add data manipulation scripts to your project and easily script execution of stored procedures.</span></span> <span data-ttu-id="a3a52-114">Cela peut représenter un gain de temps considérable pour les tables et les procédures qui comptent une quantité importante de champs.</span><span class="sxs-lookup"><span data-stu-id="a3a52-114">This can be a big timesaver for tables and procedures with many fields.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="a3a52-115">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="a3a52-115">Next Task in Lesson</span></span>  
 [<span data-ttu-id="a3a52-116">Résumé : Écriture d'instructions Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a3a52-116">Summary: Writing Transact-SQL</span></span>](../../tutorials/summary-writing-transact-sql.md)  
  
  
