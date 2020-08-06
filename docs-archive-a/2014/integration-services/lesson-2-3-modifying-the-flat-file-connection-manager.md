---
title: 'Étape 3 : Modification du gestionnaire de connexions de fichiers plats | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 459e3995-2116-4f15-aaa2-32f26113869c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b897f9412a8f2978ebe4137e3e79bf1d28c97844
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601564"
---
# <a name="step-3-modifying-the-flat-file-connection-manager"></a><span data-ttu-id="b3ccd-102">Étape 3 : Modification du Gestionnaire de connexions de fichiers plats</span><span class="sxs-lookup"><span data-stu-id="b3ccd-102">Step 3: Modifying the Flat File Connection Manager</span></span>
  <span data-ttu-id="b3ccd-103">Dans cette tâche, vous allez modifier le gestionnaire de connexions de fichiers plats que vous avez créé et configuré dans la leçon 1.</span><span class="sxs-lookup"><span data-stu-id="b3ccd-103">In this task, you will modify the Flat File connection manager that you created and configured in Lesson 1.</span></span> <span data-ttu-id="b3ccd-104">Le gestionnaire de connexions de fichiers plats a été configuré au départ pour charger statiquement un seul fichier.</span><span class="sxs-lookup"><span data-stu-id="b3ccd-104">When originally created, the Flat File connection manager was configured to statically load a single file.</span></span> <span data-ttu-id="b3ccd-105">Pour faire en sorte que le Gestionnaire de connexions de fichiers plats charge les fichiers interactivement, vous devez modifier la propriété ConnectionString du Gestionnaire de connexions afin que la variable `User:varFileName`définie par l’utilisateur soit acceptée. Cette variable contient le chemin du fichier qui doit être chargé au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="b3ccd-105">To enable the Flat File connection manager to iteratively load files, you must modify the ConnectionString property of the connection manager to accept the user-defined variable `User:varFileName`, which contains the path of the file to be loaded at run time.</span></span>  
  
 <span data-ttu-id="b3ccd-106">La modification du Gestionnaire de connexions pour qu’il utilise la variable `User::varFileName`définie par l’utilisateur et qui remplit la propriété ConnectionString du Gestionnaire de connexions, permettra à ce dernier de se connecter à plusieurs fichiers plats.</span><span class="sxs-lookup"><span data-stu-id="b3ccd-106">By modifying the connection manager to use the value of the user-defined variable, `User::varFileName`, to populate the ConnectionString property of the connection manager, the connection manager will be able to connect to different flat files.</span></span> <span data-ttu-id="b3ccd-107">Au moment de l'exécution, chaque itération du conteneur de boucles Foreach mettra à jour la variable `User::varFileName` dynamiquement.</span><span class="sxs-lookup"><span data-stu-id="b3ccd-107">At run time, each iteration of the Foreach Loop container will dynamically update the `User::varFileName` variable.</span></span> <span data-ttu-id="b3ccd-108">Si la variable est à son tour mise à jour, le Gestionnaire de connexions se connecte à un autre fichier plat et la tâche de flux de données traite un autre jeu de données.</span><span class="sxs-lookup"><span data-stu-id="b3ccd-108">Updating the variable, in turn, causes the connection manager to connect to a different flat file, and the data flow task to process a different set of data.</span></span>  
  
### <a name="to-configure-the-flat-file-connection-manager-to-use-a-variable-for-the-connection-string"></a><span data-ttu-id="b3ccd-109">Pour configurer le Gestionnaire de connexions de fichiers plats afin qu'il utilise une variable pour la chaîne de connexion</span><span class="sxs-lookup"><span data-stu-id="b3ccd-109">To configure the Flat File connection manager to use a variable for the connection string</span></span>  
  
1.  <span data-ttu-id="b3ccd-110">Dans le volet **Gestionnaires de connexions** , cliquez avec le bouton droit sur **Sample Flat File Source Data**, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b3ccd-110">In the **Connection Managers** pane, right-click **Sample Flat File Source Data**, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="b3ccd-111">Dans la Fenêtre Propriétés, pour **expressions**, cliquez dans la cellule vide, puis cliquez sur le bouton de sélection **(...)**.</span><span class="sxs-lookup"><span data-stu-id="b3ccd-111">In the Properties window, for **Expressions**, click in the empty cell, and then click the ellipsis button **(...)**.</span></span>  
  
3.  <span data-ttu-id="b3ccd-112">Dans la boîte de dialogue **éditeur d’expressions** de la propriété, dans la colonne **propriété** , tapez ou sélectionnez `ConnectionString` .</span><span class="sxs-lookup"><span data-stu-id="b3ccd-112">In the **Property Expressions Editor** dialog box, in the **Property** column, type or select `ConnectionString`.</span></span>  
  
4.  <span data-ttu-id="b3ccd-113">Dans la colonne **expression** , cliquez sur le bouton de sélection **(...)** pour ouvrir la boîte de dialogue **Générateur d’expressions** .</span><span class="sxs-lookup"><span data-stu-id="b3ccd-113">In the **Expression** column, click the ellipsis button **(...)** to open the **Expression Builder** dialog box.</span></span>  
  
5.  <span data-ttu-id="b3ccd-114">Dans la boîte de dialogue **Générateur d’expression** , développez le nœud **Variables** .</span><span class="sxs-lookup"><span data-stu-id="b3ccd-114">In the **Expression Builder** dialog box, expand the **Variables** node.</span></span>  
  
6.  <span data-ttu-id="b3ccd-115">Faites glisser la variable **User :: varFileName**vers la zone **expression** .</span><span class="sxs-lookup"><span data-stu-id="b3ccd-115">Drag the variable, **User::varFileName**, into the **Expression** box.</span></span>  
  
7.  <span data-ttu-id="b3ccd-116">Cliquez sur **OK** pour fermer la boîte de dialogue **Générateur d’expression** .</span><span class="sxs-lookup"><span data-stu-id="b3ccd-116">Click **OK** to close the **Expression Builder** dialog box.</span></span>  
  
8.  <span data-ttu-id="b3ccd-117">Recliquez sur **OK** pour fermer la boîte de dialogue **Éditeur d’expressions de la propriété** .</span><span class="sxs-lookup"><span data-stu-id="b3ccd-117">Click **OK** again to close the **Property Expressions Editor** dialog box.</span></span>  
  
## <a name="next-lesson-task"></a><span data-ttu-id="b3ccd-118">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="b3ccd-118">Next Lesson Task</span></span>  
 [<span data-ttu-id="b3ccd-119">Étape 4 : Test du package du tutoriel de la leçon 2</span><span class="sxs-lookup"><span data-stu-id="b3ccd-119">Step 4: Testing the Lesson 2 Tutorial Package</span></span>](../integration-services/lesson-2-4-testing-the-lesson-2-tutorial-package.md)  
  
  
