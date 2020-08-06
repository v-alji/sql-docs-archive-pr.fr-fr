---
title: Générer des scripts
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 9711c617-3c68-4e5a-aea3-befc64d51524
author: rothja
ms.author: jroth
ms.openlocfilehash: 199d5e0c98d220861ee0dfb48a44a71675d8ba87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613973"
---
# <a name="generate-scripts-sql-server-management-studio"></a><span data-ttu-id="04373-102">Générer des scripts (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="04373-102">Generate Scripts (SQL Server Management Studio)</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="04373-103">fournit deux mécanismes pour générer des scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="04373-103">provides two mechanisms for generating [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts.</span></span> <span data-ttu-id="04373-104">Vous pouvez créer des scripts pour plusieurs objets à l’aide de l' **Assistant générer et publier des scripts.**</span><span class="sxs-lookup"><span data-stu-id="04373-104">You can create scripts for multiple objects by using the **Generate and Publish Scripts Wizard.**.</span></span> <span data-ttu-id="04373-105">Vous pouvez également générer un script pour des objets individuels ou plusieurs objets à l'aide du menu **Script en tant que** dans l' **Explorateur d'objets**.</span><span class="sxs-lookup"><span data-stu-id="04373-105">You can also generate a script for individual objects or multiple objects by using the **Script as** menu in **Object Explorer**.</span></span>  
  
1.  <span data-ttu-id="04373-106">**Choisissez une méthode :**  [Assistant Générer et publier des scripts](#GenPubScriptWiz), [Menu Script en tant que de l'Explorateur d'objets](#OEScriptAsMenu)</span><span class="sxs-lookup"><span data-stu-id="04373-106">**Choose a method:**  [Generate and Publish Scripts Wizard](#GenPubScriptWiz), [Object Explorer Script As Menu](#OEScriptAsMenu)</span></span>  
  
2.  <span data-ttu-id="04373-107">**Pour utiliser le menu Script en tant que :**  [Générer un script d'un objet unique](#ScriptSingleObject), [Générer un script de deux objets à l'aide de l'Explorateur d'objets](#ScriptTwoObjectsOE), [Générer un script de deux objets à l'aide de la page Détails de l'Explorateur d'objets](#ScriptTwoObjectsOED)</span><span class="sxs-lookup"><span data-stu-id="04373-107">**To use the Script As menu:**  [Script a Single Object](#ScriptSingleObject), [Script Two Objects Using Object Explorer](#ScriptTwoObjectsOE), [Script Two Objects Using Object Explorer Details](#ScriptTwoObjectsOED)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="04373-108">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="04373-108">Before You Begin</span></span>  
 <span data-ttu-id="04373-109">Choisissez le mécanisme qui correspond le mieux à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="04373-109">Choose the mechanism that best meets your requirements.</span></span>  
  
###  <a name="generate-and-publish-scripts-wizard"></a><a name="GenPubScriptWiz"></a> <span data-ttu-id="04373-110">Assistant Générer et publier des scripts</span><span class="sxs-lookup"><span data-stu-id="04373-110">Generate and Publish Scripts Wizard</span></span>  
 <span data-ttu-id="04373-111">Utilisez l' **Assistant Générer et publier des scripts** pour créer un script [!INCLUDE[tsql](../../includes/tsql-md.md)] pour plusieurs objets.</span><span class="sxs-lookup"><span data-stu-id="04373-111">Use the **Generate and Publish Scripts Wizard** to create a [!INCLUDE[tsql](../../includes/tsql-md.md)] script for many objects.</span></span> <span data-ttu-id="04373-112">L'Assistant génère un script de tous les objets d'une base de données, ou un sous-ensemble des objets que vous sélectionnez.</span><span class="sxs-lookup"><span data-stu-id="04373-112">The wizard generates a script of all the objects in a database, or a subset of the objects that you select.</span></span> <span data-ttu-id="04373-113">L'Assistant propose de nombreuses options pour vos scripts et vous permet notamment d'inclure ou non des autorisations, un classement et des contraintes.</span><span class="sxs-lookup"><span data-stu-id="04373-113">The wizard has many options for your scripts, such as whether to include permissions, collation, constraints, and so on.</span></span> <span data-ttu-id="04373-114">Pour obtenir des instructions sur l'utilisation de l'Assistant, consultez [Generate and Publish Scripts Wizard](generate-and-publish-scripts-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="04373-114">For instructions on using the wizard, see [Generate and Publish Scripts Wizard](generate-and-publish-scripts-wizard.md).</span></span>  
  
###  <a name="object-explorer-script-as-menu"></a><a name="OEScriptAsMenu"></a> <span data-ttu-id="04373-115">Menu Script en tant que de l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="04373-115">Object Explorer Script As Menu</span></span>  
 <span data-ttu-id="04373-116">Vous pouvez utiliser le menu **Script en tant que de l'Explorateur d'objets** pour générer un script d'un objet unique, de plusieurs objets ou de plusieurs instructions pour des objets uniques.</span><span class="sxs-lookup"><span data-stu-id="04373-116">You can use the **Object Explorer Script as** menu to script a single object, script multiple objects, or script multible statements for a single objects.</span></span> <span data-ttu-id="04373-117">Vous pouvez choisir un type de scripts parmi plusieurs ; par exemple pour créer, modifier ou supprimer l'objet.</span><span class="sxs-lookup"><span data-stu-id="04373-117">You can choose one of several types of scripts; for example to create, alter, or drop the object.</span></span> <span data-ttu-id="04373-118">Vous pouvez enregistrer le script dans une fenêtre Éditeur de requête, dans un fichier ou dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="04373-118">You can save the script in a Query Editor window, to a file, or to the Clipboard.</span></span> <span data-ttu-id="04373-119">Le script est créé au format Unicode.</span><span class="sxs-lookup"><span data-stu-id="04373-119">The script is created in Unicode format.</span></span>  
  
##  <a name="to-generate-a-script-of-a-single-object"></a><a name="ScriptSingleObject"></a> <span data-ttu-id="04373-120">Pour générer un script d'un objet unique</span><span class="sxs-lookup"><span data-stu-id="04373-120">To generate a script of a single object</span></span>  
 <span data-ttu-id="04373-121">**Pour générer un script d'un objet unique**</span><span class="sxs-lookup"><span data-stu-id="04373-121">**To script a single object**</span></span>  
  
1.  <span data-ttu-id="04373-122">Dans l'Explorateur d'objets, connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="04373-122">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="04373-123">Développez **Bases de données**, puis développez la base de données contenant l'objet pour lequel un script doit être généré.</span><span class="sxs-lookup"><span data-stu-id="04373-123">Expand **Databases**, and then expand the database containing the object to be scripted.</span></span>  
  
3.  <span data-ttu-id="04373-124">Développez la catégorie de l'objet.</span><span class="sxs-lookup"><span data-stu-id="04373-124">Expand the category of the object.</span></span> <span data-ttu-id="04373-125">Par exemple, développez le nœud **Tables** ou **Vues** .</span><span class="sxs-lookup"><span data-stu-id="04373-125">For example, expand the **Tables** or **Views** node.</span></span>  
  
4.  <span data-ttu-id="04373-126">Cliquez avec le bouton droit sur l’objet, pointez sur **script \<object type> sous la forme**, par exemple, pointez sur générer un script de la **table en tant que**.</span><span class="sxs-lookup"><span data-stu-id="04373-126">Right-click the object, point to **Script \<object type> as**, For example, point to **Script Table as**.</span></span>  
  
5.  <span data-ttu-id="04373-127">Pointez sur le type de script, tel que **Create to** ou **Alter to**.</span><span class="sxs-lookup"><span data-stu-id="04373-127">Point to the script type, such as **Create to** or **Alter to**.</span></span>  
  
6.  <span data-ttu-id="04373-128">Sélectionnez l'emplacement dans lequel vous voulez enregistrer le script, tel que **Nouvelle fenêtre d'éditeur de requête** ou **Presse-papiers**.</span><span class="sxs-lookup"><span data-stu-id="04373-128">Select the location to save the script, such as **New Query Editor Window** or **Clipboard**.</span></span>  
  
##  <a name="to-generate-a-script-of-two-objects-using-object-explorer"></a><a name="ScriptTwoObjectsOE"></a><span data-ttu-id="04373-129">Pour générer un script de deux objets à l’aide de l’Explorateur d’objets</span><span class="sxs-lookup"><span data-stu-id="04373-129">To generate a script of two objects using Object Explorer</span></span>  
 <span data-ttu-id="04373-130">**Pour générer un script de deux objets à l'aide de l'Explorateur d'objets**</span><span class="sxs-lookup"><span data-stu-id="04373-130">**To script two objects using Object Explorer**</span></span>  
  
 <span data-ttu-id="04373-131">Vous pouvez parfois avoir besoin d'utiliser un script avec plusieurs options permettant, par exemple, de supprimer et de créer une procédure ou bien de créer une table puis de la modifier.</span><span class="sxs-lookup"><span data-stu-id="04373-131">Sometimes you may want a script with multiple options, such as drop a procedure and then create a procedure, or create a table and then alter a table.</span></span> <span data-ttu-id="04373-132">Les processus ci-dessous de génération de scripts pour plusieurs objets fonctionnent également si vous devez créer un script qui référence différents types d'objets, tels que les tables, les vues et les procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="04373-132">The processes below for generating scripts of multiple objects also work if you need to create a script that references different types of objects, such as tables, views, and stored procedures.</span></span>  
  
1.  <span data-ttu-id="04373-133">Dans l'Explorateur d'objets, connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="04373-133">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="04373-134">Développez **Bases de données**, puis développez la base de données contenant les objets pour lequel un script doit être généré.</span><span class="sxs-lookup"><span data-stu-id="04373-134">Expand **Databases**, and then expand the database containing the objects to be scripted.</span></span>  
  
3.  <span data-ttu-id="04373-135">Cliquez avec le bouton droit sur le premier objet pour lequel vous souhaitez créer un script, pointez sur générer un **script \<object type> en tant que**et, dans les sélections **Enregistrer sous** , choisissez **nouvelle fenêtre** de l’éditeur de requête comme destination de sortie.</span><span class="sxs-lookup"><span data-stu-id="04373-135">Right-click the first object to be scripted, point to **Script \<object type> as**, and in the **Save as** selections chooses **New Query Editor Window** as the output destination.</span></span>  
  
4.  <span data-ttu-id="04373-136">Accédez au deuxième objet pour lequel vous voulez générer un script.</span><span class="sxs-lookup"><span data-stu-id="04373-136">Navigate to the second object you want to script.</span></span>  
  
5.  <span data-ttu-id="04373-137">Cliquez avec le bouton droit sur l’objet, pointez sur générer un **script \<object type> en tant que**et dans les sélections **Enregistrer sous** , choisissez **presse-papiers** comme destination de sortie.</span><span class="sxs-lookup"><span data-stu-id="04373-137">Right-click the object, point to **Script \<object type> as**, and in the **Save as** selections chooses **Clipboard** as the output destination.</span></span>  
  
6.  <span data-ttu-id="04373-138">Dans la fenêtre de l'Éditeur de requête ouverte pour le premier objet, collez le script pour le deuxième objet du presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="04373-138">In the Query Editor window opened for the first object, paste the script for the second object from the clipboard.</span></span>  
  
##  <a name="to-generate-a-script-of-two-objects-using-object-explorer-details"></a><a name="ScriptTwoObjectsOED"></a><span data-ttu-id="04373-139">Pour générer un script de deux objets à l’aide des détails de l’Explorateur d’objets</span><span class="sxs-lookup"><span data-stu-id="04373-139">To generate a script of two objects using Object Explorer Details</span></span>  
 <span data-ttu-id="04373-140">**Pour générer un script de deux objets à l'aide de la page Détails de l'Explorateur d'objets**</span><span class="sxs-lookup"><span data-stu-id="04373-140">**To script two objects using Object Explorer Details**</span></span>  
  
 <span data-ttu-id="04373-141">Vous pouvez utiliser le volet **Détails de l'Explorateur d'objets** pour générer un script pour plusieurs objets de la même catégorie.</span><span class="sxs-lookup"><span data-stu-id="04373-141">You can use the **Object Explorer Details** pane to generate a script for mutliple objects of the same category.</span></span>  
  
1.  <span data-ttu-id="04373-142">Dans l'Explorateur d'objets, connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="04373-142">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="04373-143">Développez **Bases de données**, puis développez la base de données contenant les objets pour lequel un script doit être généré.</span><span class="sxs-lookup"><span data-stu-id="04373-143">Expand **Databases**, and then expand the database containing the objects to be scripted.</span></span>  
  
3.  <span data-ttu-id="04373-144">Développez le nœud de catégorie des types d'objet pour lesquels vous voulez générer un script, tel que le nœud **Tables** .</span><span class="sxs-lookup"><span data-stu-id="04373-144">Expand the category node of the types of object you want to script, such as the **Tables** node.</span></span>  
  
4.  <span data-ttu-id="04373-145">Ouvrez le volet **Détails de l'Explorateur d'objets** en appuyant sur **F7**, ou en ouvrant le menu **Affichage** et en sélectionnant **Détails de l'Explorateur d'objets**.</span><span class="sxs-lookup"><span data-stu-id="04373-145">Open the **Object Explorer Details** pane by either selecting **F7**, or opening the **View** menu and selecting **Object Explorer Details**.</span></span>  
  
5.  <span data-ttu-id="04373-146">Cliquez avec le bouton gauche sur l'un des objets pour lesquels vous voulez générer un script.</span><span class="sxs-lookup"><span data-stu-id="04373-146">Left-click one of the objects you want to script.</span></span>  
  
6.  <span data-ttu-id="04373-147">Appuyez sur Crtl + clic gauche sur le deuxième objet pour lequel vous voulez générer un script.</span><span class="sxs-lookup"><span data-stu-id="04373-147">Crtl + left-click the second object you want to script.</span></span>  
  
7.  <span data-ttu-id="04373-148">Cliquez avec le bouton droit sur l’un des objets sélectionnés, puis sélectionnez **script \<object type> sous**.</span><span class="sxs-lookup"><span data-stu-id="04373-148">Right-click one of the selected objects, and select **Script \<object type> as**.</span></span>  
  
  
