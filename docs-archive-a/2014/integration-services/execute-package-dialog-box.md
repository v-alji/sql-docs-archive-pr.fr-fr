---
title: Boîte de dialogue Exécuter le package | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.ispackageexecute.f1
- sql12.ssis.ssms.executepackage.f1
ms.assetid: 4f7a806d-4867-4d1f-bc65-b00c1caee7b6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1b60381054c781cd59f0a9d434710663b72d616c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610753"
---
# <a name="execute-package-dialog-box"></a><span data-ttu-id="7f984-102">Execute Package Dialog Box</span><span class="sxs-lookup"><span data-stu-id="7f984-102">Execute Package Dialog Box</span></span>
  <span data-ttu-id="7f984-103">Utilisez la boîte de dialogue **Exécuter le package** pour exécuter un package stocké sur le serveur [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7f984-103">Use the **Execute Package** dialog box to run a package that is stored on the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span>  
  
 <span data-ttu-id="7f984-104">Un package [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] peut contenir des paramètres qui référencent les valeurs stockées dans les variables d'environnement.</span><span class="sxs-lookup"><span data-stu-id="7f984-104">An [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package may contain parameters that values stored in environment variables.</span></span> <span data-ttu-id="7f984-105">Avant d'exécuter un tel package, vous devez spécifier quel environnement sera utilisé pour fournir les valeurs de variable d'environnement.</span><span class="sxs-lookup"><span data-stu-id="7f984-105">Before executing such a package, you must specify which environment will be used to provide the environment variable values.</span></span> <span data-ttu-id="7f984-106">Un projet peut contenir plusieurs environnements, mais un seul environnement peut être utilisé pour la liaison de valeurs de variable d'environnement au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="7f984-106">A project may contain multiple environments, but only one environment can be used for binding environment variable values at the time of execution.</span></span> <span data-ttu-id="7f984-107">Si aucune variable d'environnement n'est utilisée dans le package, un environnement n'est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="7f984-107">If no environment variables are used in the package, an environment is not required.</span></span>  
  
 <span data-ttu-id="7f984-108">Que voulez-vous faire ?</span><span class="sxs-lookup"><span data-stu-id="7f984-108">What do you want to do?</span></span>  
  
-   [<span data-ttu-id="7f984-109">Ouvrir la boîte de dialogue Exécuter le package</span><span class="sxs-lookup"><span data-stu-id="7f984-109">Open the Execute Package dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="7f984-110">Définir les options sur la page Général</span><span class="sxs-lookup"><span data-stu-id="7f984-110">Set the Options on the General page</span></span>](#general)  
  
-   [<span data-ttu-id="7f984-111">Définir les options de l'onglet Paramètres</span><span class="sxs-lookup"><span data-stu-id="7f984-111">Set the Options on the Parameters tab</span></span>](#parameters)  
  
-   [<span data-ttu-id="7f984-112">Définir les options de l'onglet Gestionnaires de connexions</span><span class="sxs-lookup"><span data-stu-id="7f984-112">Set the Options on the Connection Managers tab</span></span>](#connection)  
  
-   [<span data-ttu-id="7f984-113">Définir les options de l'onglet Avancé</span><span class="sxs-lookup"><span data-stu-id="7f984-113">Set the Options on the Advanced tab</span></span>](#advanced)  
  
-   [<span data-ttu-id="7f984-114">Création de script avec les options de la boîte de dialogue Exécuter le package</span><span class="sxs-lookup"><span data-stu-id="7f984-114">Scripting the Options in the Execute Package Dialog Box</span></span>](#script)  
  
##  <a name="open-the-execute-package-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="7f984-115">Ouvrir la boîte de dialogue Exécuter le package</span><span class="sxs-lookup"><span data-stu-id="7f984-115">Open the Execute Package dialog box</span></span>  
  
1.  <span data-ttu-id="7f984-116">Dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], connectez-vous au serveur [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7f984-116">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="7f984-117">Vous vous connectez à l’instance du [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] qui héberge la base de données SSISDB.</span><span class="sxs-lookup"><span data-stu-id="7f984-117">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="7f984-118">Dans l'Explorateur d'objets, développez l'arborescence pour afficher le nœud **Integration Services Catalogues** .</span><span class="sxs-lookup"><span data-stu-id="7f984-118">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="7f984-119">Développez le nœud **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="7f984-119">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="7f984-120">Développez le dossier contenant le package à exécuter.</span><span class="sxs-lookup"><span data-stu-id="7f984-120">Expand the folder that contains the package you want to run.</span></span>  
  
5.  <span data-ttu-id="7f984-121">Cliquez avec le bouton droit sur le package, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="7f984-121">Right-click the package, and then click **Execute**.</span></span>  
  
##  <a name="set-the-options-on-the-general-page"></a><a name="general"></a> <span data-ttu-id="7f984-122">Définir les options sur la page Général</span><span class="sxs-lookup"><span data-stu-id="7f984-122">Set the Options on the General page</span></span>  
 <span data-ttu-id="7f984-123">Sélectionnez **Environnement** pour spécifier l'environnement qui est appliqué avec le package.</span><span class="sxs-lookup"><span data-stu-id="7f984-123">Select **Environment** to specify the environment that is applied with the package is run.</span></span>  
  
##  <a name="set-the-options-on-the-parameters-tab"></a><a name="parameters"></a> <span data-ttu-id="7f984-124">Définir les options de l'onglet Paramètres</span><span class="sxs-lookup"><span data-stu-id="7f984-124">Set the Options on the Parameters tab</span></span>  
 <span data-ttu-id="7f984-125">Utilisez l'onglet **Paramètres** pour modifier les valeurs de paramètre utilisées lors de l'exécution du package.</span><span class="sxs-lookup"><span data-stu-id="7f984-125">Use the **Parameters** tab to modify the parameter values that are used when the package runs.</span></span>  
  
##  <a name="set-the-options-on-the-connection-managers-tab"></a><a name="connection"></a> <span data-ttu-id="7f984-126">Définir les options de l'onglet Gestionnaires de connexions</span><span class="sxs-lookup"><span data-stu-id="7f984-126">Set the Options on the Connection Managers tab</span></span>  
 <span data-ttu-id="7f984-127">Utilisez l'onglet Gestionnaires de connexions pour définir les propriétés du ou des gestionnaires de connexions du package.</span><span class="sxs-lookup"><span data-stu-id="7f984-127">Use the Connection Managers tab to set the properties of the package connection manager(s).</span></span>  
  
##  <a name="set-the-options-on-the-advanced-tab"></a><a name="advanced"></a> <span data-ttu-id="7f984-128">Définir les options de l'onglet Avancé</span><span class="sxs-lookup"><span data-stu-id="7f984-128">Set the Options on the Advanced tab</span></span>  
 <span data-ttu-id="7f984-129">Utilisez l'onglet Avancé pour gérer des propriétés et d'autres paramètres du package.</span><span class="sxs-lookup"><span data-stu-id="7f984-129">Use the Advanced tab to manage properties and other package settings.</span></span>  
  
 <span data-ttu-id="7f984-130">**Ajouter**, **Modifier**, **Supprimer**</span><span class="sxs-lookup"><span data-stu-id="7f984-130">**Add**, **Edit**, **Remove**</span></span>  
 <span data-ttu-id="7f984-131">Cliquez pour ajouter, modifier ou supprimer une propriété.</span><span class="sxs-lookup"><span data-stu-id="7f984-131">Click to add, edit, or remove a property.</span></span>  
  
 <span data-ttu-id="7f984-132">**Niveau de journalisation**</span><span class="sxs-lookup"><span data-stu-id="7f984-132">**Logging level**</span></span>  
 <span data-ttu-id="7f984-133">Sélectionnez le niveau de journalisation pour l'exécution du package.</span><span class="sxs-lookup"><span data-stu-id="7f984-133">Select the logging level for the package execution.</span></span> <span data-ttu-id="7f984-134">Pour plus d’informations, consultez [catalog.set_execution_parameter_value &#40;base de données SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="7f984-134">For more information, see [catalog.set_execution_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database).</span></span>  
  
 <span data-ttu-id="7f984-135">**Vider en cas d'erreurs**</span><span class="sxs-lookup"><span data-stu-id="7f984-135">**Dump on errors**</span></span>  
 <span data-ttu-id="7f984-136">Spécifiez si un fichier de vidage est créé lorsque des erreurs se produisent pendant l'exécution du package.</span><span class="sxs-lookup"><span data-stu-id="7f984-136">Specify whether a dump file is created when errors occur during the package execution.</span></span> <span data-ttu-id="7f984-137">Pour plus d’informations, voir [Generating Dump Files for Package Execution](troubleshooting/generating-dump-files-for-package-execution.md).</span><span class="sxs-lookup"><span data-stu-id="7f984-137">For more information, see [Generating Dump Files for Package Execution](troubleshooting/generating-dump-files-for-package-execution.md).</span></span>  
  
 <span data-ttu-id="7f984-138">**Runtime 32 bits**</span><span class="sxs-lookup"><span data-stu-id="7f984-138">**32-bit runtime**</span></span>  
 <span data-ttu-id="7f984-139">Indiquez que le package doit s'exécuter sur un système 32 bits.</span><span class="sxs-lookup"><span data-stu-id="7f984-139">Specify that the package will execute on a 32-bit system.</span></span>  
  
##  <a name="scripting-the-options-in-the-execute-package-dialog-box"></a><a name="script"></a> <span data-ttu-id="7f984-140">Création de script avec les options de la boîte de dialogue Exécuter le package</span><span class="sxs-lookup"><span data-stu-id="7f984-140">Scripting the Options in the Execute Package Dialog Box</span></span>  
 <span data-ttu-id="7f984-141">Lorsque vous vous trouvez dans la boîte de dialogue **Exécuter le package** , vous pouvez également utiliser le bouton **Script** de la barre d'outils pour écrire du code [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7f984-141">While you are in the **Execute Package** dialog box, you can also use the **Script** button on the toolbar to write [!INCLUDE[tsql](../includes/tsql-md.md)] code for you.</span></span> <span data-ttu-id="7f984-142">Le script généré appelle les procédures stockées [catalog.start_execution &#40;base de données SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database) avec les options que vous avez sélectionnées dans la boîte de dialogue **Exécuter le package**.</span><span class="sxs-lookup"><span data-stu-id="7f984-142">The generated script calls the stored procedures [catalog.start_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database) with the same options that you have selected in the **Execute Package** dialog box.</span></span> <span data-ttu-id="7f984-143">Le script s'affiche dans une nouvelle fenêtre de script dans [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f984-143">The script appears in a new script window in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
  
