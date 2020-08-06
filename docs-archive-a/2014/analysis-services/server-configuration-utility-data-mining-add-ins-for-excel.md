---
title: Utilitaire de configuration du serveur (compléments d’exploration de données pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 28435f86-5cec-4a1e-9b7d-b2069c1ddddb
author: minewiskan
ms.author: owend
ms.openlocfilehash: f985338e44bf0f4b591fcb70a4e093901626149f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710871"
---
# <a name="server-configuration-utility-data-mining-add-ins-for-excel"></a><span data-ttu-id="e331a-102">Utilitaire de configuration du serveur (Compléments d'exploration de données pour Excel)</span><span class="sxs-lookup"><span data-stu-id="e331a-102">Server Configuration Utility (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="e331a-103">Lorsque vous installez les compléments d’exploration de données pour Excel, un utilitaire de configuration de serveur est également installé et s’exécute la première fois que vous ouvrez les compléments. Cette rubrique explique comment utiliser l’utilitaire pour vous connecter à une instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] et configurer une base de données pour travailler avec des modèles d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="e331a-103">When you install the Data Mining Add-ins for Excel, a Server Configuration Utility is also installed, and will run the first time you open the add-ins. This topic describes how to use the utility to connect to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and set up a database for working with data mining models.</span></span>  
  

  
##  <a name="step-1-connect-to-analysis-services"></a><a name="bkmk_step1"></a><span data-ttu-id="e331a-104">Étape 1 : se connecter à Analysis Services</span><span class="sxs-lookup"><span data-stu-id="e331a-104">Step 1: Connect to Analysis Services</span></span>  
 <span data-ttu-id="e331a-105">Choisissez le serveur [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] qui fournit les algorithmes d'exploration de données et stocke vos modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="e331a-105">Choose the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that provides the data mining algorithms and stores your data mining models.</span></span>  
  
 <span data-ttu-id="e331a-106">Lorsque vous créez une connexion pour l'exploration de données, vous devez choisir un serveur sur lequel travailler avec les modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="e331a-106">When you create a connection to enable data mining, you should choose a server where you can experiment with data mining models.</span></span> <span data-ttu-id="e331a-107">Nous vous recommandons de créer une nouvelle base de données sur le serveur et de la dédier à l'exploration de données, ou de demander à votre administrateur de préparer un serveur d'exploration de données à votre place.</span><span class="sxs-lookup"><span data-stu-id="e331a-107">We recommend that you create a new database on the server and dedicate the new database to data mining, or ask your administrator to prepare a data mining server for you.</span></span> <span data-ttu-id="e331a-108">Ainsi, vous pourrez créer des modèles sans affecter l'exécution d'autres services.</span><span class="sxs-lookup"><span data-stu-id="e331a-108">That way you can build models without affecting the performance of other services.</span></span>  
  
 <span data-ttu-id="e331a-109">Notez que le serveur [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que vous utilisez pour l'exploration de données ne doit pas nécessairement être sur le même serveur que vos données source.</span><span class="sxs-lookup"><span data-stu-id="e331a-109">Note that the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that you use for data mining does not need to be on the same server as your source data.</span></span>  
  
 <span data-ttu-id="e331a-110">**Nom du serveur**</span><span class="sxs-lookup"><span data-stu-id="e331a-110">**Server name**</span></span>  
 <span data-ttu-id="e331a-111">Tapez le nom du serveur qui contient l'instance [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que vous utiliserez pour l'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="e331a-111">Type the name of the server that contains the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you will use for data mining.</span></span>  
  
 <span data-ttu-id="e331a-112">**Authentification**</span><span class="sxs-lookup"><span data-stu-id="e331a-112">**Authentication**</span></span>  
 <span data-ttu-id="e331a-113">Spécifiez les méthodes d'authentification.</span><span class="sxs-lookup"><span data-stu-id="e331a-113">Specify the authentication methods.</span></span> <span data-ttu-id="e331a-114">L'Authentification Windows est requise pour les connexions à [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], sauf si votre administrateur a configuré l'accès au serveur via HTTPPump.</span><span class="sxs-lookup"><span data-stu-id="e331a-114">Windows Authentication is required for connections to [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], unless your administrator has configured access to the server via the HTTPPump.</span></span>  
  
##  <a name="step-2-allow-temporary-models"></a><a name="bkmk_step2"></a><span data-ttu-id="e331a-115">Étape 2 : autoriser les modèles temporaires</span><span class="sxs-lookup"><span data-stu-id="e331a-115">Step 2: Allow Temporary Models</span></span>  
 <span data-ttu-id="e331a-116">Avant de pouvoir utiliser les compléments, une propriété du serveur [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] doit être modifiée pour permettre la création de modèles d'exploration de données temporaires.</span><span class="sxs-lookup"><span data-stu-id="e331a-116">Before you can use the add-ins, an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server property must be changed to permit the creation of temporary mining models.</span></span>  
  
 <span data-ttu-id="e331a-117">Les modèles d’exploration de données temporaires sont également appelés *modèles de session*.</span><span class="sxs-lookup"><span data-stu-id="e331a-117">Temporary mining models are also called *session models*.</span></span> <span data-ttu-id="e331a-118">C'est parce que les modèles sont stockés uniquement tant que votre session actuelle est ouverte.</span><span class="sxs-lookup"><span data-stu-id="e331a-118">This is because the models are stored only as long as your current session is open.</span></span> <span data-ttu-id="e331a-119">Lorsque vous fermez votre connexion au serveur, la session est terminée et tous les modèles utilisés pendant la session sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="e331a-119">When you close your connection to the server, the session is ended and any models used during the session are deleted.</span></span>  
  
 <span data-ttu-id="e331a-120">L'utilisation de modèles d'exploration de données de session n'affecte pas l'espace de stockage disponible sur le serveur, mais la surcharge induite par la création de modèles d'exploration de données peut affecter les performances du serveur.</span><span class="sxs-lookup"><span data-stu-id="e331a-120">The use of session mining models does not affect storage space on the server, but the overhead involved in creating data mining models may affect the performance of the server.</span></span>  
  
 <span data-ttu-id="e331a-121">L'Assistant commence par détecter les paramètres du serveur spécifié.</span><span class="sxs-lookup"><span data-stu-id="e331a-121">The wizard first detects the settings on the server that you specified.</span></span> <span data-ttu-id="e331a-122">Si le serveur autorise déjà les modèles d’exploration de données temporaires, vous pouvez cliquer sur **suivant** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="e331a-122">If the server already allows temporary mining models, you can click **Next** to continue.</span></span> <span data-ttu-id="e331a-123">L'Assistant fournit également des instructions pour activer les modèles d'exploration de données temporaires sur le serveur [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] spécifié, ou pour en faire la demande à votre administrateur [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e331a-123">The wizard also provides instructions for how to enable temporary mining models on the specified [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server, or how to make a request to your [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] administrator.</span></span>  
  
##  <a name="step-3-create-database-for-add-in-users"></a><a name="bkmk_step3"></a><span data-ttu-id="e331a-124">Étape 3 : créer une base de données pour les utilisateurs des compléments</span><span class="sxs-lookup"><span data-stu-id="e331a-124">Step 3: Create Database for Add-in Users</span></span>  
 <span data-ttu-id="e331a-125">Dans cette page de l'Assistant Installation et configuration, vous créez une nouvelle base de données qui est dédiée à l'exploration de données, ou vous sélectionnez une base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] existante.</span><span class="sxs-lookup"><span data-stu-id="e331a-125">On this page of the setup and configuration wizard, you can create a new database that is dedicated to data mining, or select an existing [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="e331a-126">L'exploration de données nécessite une instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] exécutée en mode multidimensionnel.</span><span class="sxs-lookup"><span data-stu-id="e331a-126">Data mining requires an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that is running in multidimensional mode.</span></span> <span data-ttu-id="e331a-127">Le mode tabulaire ne prend pas en charge l'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="e331a-127">Tabular mode does not support data mining.</span></span>  
  
 <span data-ttu-id="e331a-128">Nous vous recommandons de créer une base de données distincte dédiée à l'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="e331a-128">We recommend that you create a separate database dedicated to data mining.</span></span> <span data-ttu-id="e331a-129">Vous pourrez ainsi travailler avec les modèles d'exploration de données sans affecter les autres objets de la solution.</span><span class="sxs-lookup"><span data-stu-id="e331a-129">This lets you experiment with data mining models without affecting other solution objects.</span></span>  
  
 <span data-ttu-id="e331a-130">Si vous choisissez une base de données existante sur une instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], notez qu'il est possible de remplacer les modèles existants si vous utilisez les compléments pour créer un modèle et si un modèle avec ce nom existe déjà.</span><span class="sxs-lookup"><span data-stu-id="e331a-130">If you choose an existing database on an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], note that it is possible to overwrite existing models if you use the add-ins to create a model and a model of that name already exists.</span></span>  
  
 <span data-ttu-id="e331a-131">**Create new database**</span><span class="sxs-lookup"><span data-stu-id="e331a-131">**Create new database**</span></span>  
 <span data-ttu-id="e331a-132">Sélectionnez cette option pour créer une nouvelle base de données sur le serveur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="e331a-132">Select this option to create a new database on the selected server.</span></span> <span data-ttu-id="e331a-133">Une base de données d'exploration de données stockera vos sources de données, ainsi que vos structures et vos modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="e331a-133">A data mining database will store your data sources, mining structures, and mining models.</span></span>  
  
 <span data-ttu-id="e331a-134">**Nom de la base de données**</span><span class="sxs-lookup"><span data-stu-id="e331a-134">**Database name**</span></span>  
 <span data-ttu-id="e331a-135">Tapez le nom de la nouvelle base de données.</span><span class="sxs-lookup"><span data-stu-id="e331a-135">Type the name of the new database.</span></span> <span data-ttu-id="e331a-136">Si le nom n'est pas encore utilisé, il sera créé.</span><span class="sxs-lookup"><span data-stu-id="e331a-136">If the name is not already in use, it will be created for you.</span></span>  
  
 <span data-ttu-id="e331a-137">**Utiliser une base de données existante**</span><span class="sxs-lookup"><span data-stu-id="e331a-137">**Use existing database**</span></span>  
 <span data-ttu-id="e331a-138">Sélectionnez cette option pour utiliser une base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] existante.</span><span class="sxs-lookup"><span data-stu-id="e331a-138">Select this option to use an existing [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="e331a-139">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="e331a-139">**Database**</span></span>  
 <span data-ttu-id="e331a-140">Si vous choisissez d'utiliser une base de données existante, vous devez sélectionner son nom dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e331a-140">If you chose the option to use an existing database, you must select the database name from the list.</span></span>  
  
##  <a name="step-4-give-add-in-users-appropriate-permissions"></a><a name="bkmk_step4"></a><span data-ttu-id="e331a-141">Étape 4 : attribuer les autorisations appropriées aux utilisateurs des compléments</span><span class="sxs-lookup"><span data-stu-id="e331a-141">Step 4: Give Add-in Users Appropriate Permissions</span></span>  
 <span data-ttu-id="e331a-142">Assurez-vous que vous-même (et les autres utilisateurs des compléments) bénéficiez des autorisations nécessaires pour parcourir, modifier, traiter ou créer des structures et des modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="e331a-142">You must ensure that you (and any other users of the add-ins) have the necessary permissions to browse, edit, process, or create data mining structures and models.</span></span>  
  
 <span data-ttu-id="e331a-143">Par défaut, l'Authentification Windows intégrée est un préalable de l'utilisation des compléments.</span><span class="sxs-lookup"><span data-stu-id="e331a-143">By default, integrated Windows Authentication is required to use the add-ins.</span></span>  
  
 <span data-ttu-id="e331a-144">**Donner aux utilisateurs les autorisations d'administration sur la base de données**</span><span class="sxs-lookup"><span data-stu-id="e331a-144">**Give add-in users database administration permissions**</span></span>  
 <span data-ttu-id="e331a-145">Sélectionnez cette option pour accorder l'accès à la base de données aux utilisateurs répertoriés.</span><span class="sxs-lookup"><span data-stu-id="e331a-145">Select this option to give the listed users administrative access to the database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e331a-146">Ces autorisations s’appliquent uniquement à la base de données indiquée dans la zone **nom de la base de données** .</span><span class="sxs-lookup"><span data-stu-id="e331a-146">These permissions apply only to the database listed in the **Database name** box.</span></span>  
  
 <span data-ttu-id="e331a-147">**Nom de la base de données**</span><span class="sxs-lookup"><span data-stu-id="e331a-147">**Database name**</span></span>  
 <span data-ttu-id="e331a-148">Affiche le nom de la base de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e331a-148">Displays the name of the selected database.</span></span>  
  
 <span data-ttu-id="e331a-149">**Spécifier les utilisateurs ou les groupes à ajouter**</span><span class="sxs-lookup"><span data-stu-id="e331a-149">**Specify users or groups to add**</span></span>  
 <span data-ttu-id="e331a-150">Sélectionnez les connexions qui auront accès à la base de données utilisée pour l'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="e331a-150">Select the logins that will have access to the database used for data mining.</span></span>  
  
 <span data-ttu-id="e331a-151">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="e331a-151">**Add**</span></span>  
 <span data-ttu-id="e331a-152">Cliquez pour ouvrir une boîte de dialogue et ajouter des utilisateurs ou des groupes.</span><span class="sxs-lookup"><span data-stu-id="e331a-152">Click to open a dialog box and add users or groups.</span></span>  
  
 <span data-ttu-id="e331a-153">**Remove**</span><span class="sxs-lookup"><span data-stu-id="e331a-153">**Remove**</span></span>  
 <span data-ttu-id="e331a-154">Cliquez pour supprimer l'utilisateur ou le groupe de la liste des utilisateurs dotés d'autorisations d'administration.</span><span class="sxs-lookup"><span data-stu-id="e331a-154">Click to remove the selected user or group from the list of users with administration permissions.</span></span>  
  
  
