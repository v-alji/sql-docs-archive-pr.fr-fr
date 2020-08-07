---
title: Créer un modèle à l’aide de Gestionnaire de rapports | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report models [Reporting Services], creating
- Report Manager [Reporting Services], model creation
ms.assetid: 8e5d2bd3-48ec-45f3-afee-6d86797c8f28
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 59ce278a22ec9797b001ca37a0bde576483cf5d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703936"
---
# <a name="create-a-model-using-report-manager"></a><span data-ttu-id="73d1f-102">Créer un modèle à l'aide du Gestionnaire de rapports</span><span class="sxs-lookup"><span data-stu-id="73d1f-102">Create a Model Using Report Manager</span></span>
  <span data-ttu-id="73d1f-103">Vous pouvez générer des modèles à partir d'un cube [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , d'une base de données [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ou d'une base de données Oracle à l'aide du Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="73d1f-103">You can generate models from an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube, a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database, or an Oracle database using Report Manager.</span></span> <span data-ttu-id="73d1f-104">Les modèles de rapport sont générés à partir de sources de données partagées publiées sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="73d1f-104">Report models are generated from shared data sources that are published on the report server.</span></span> <span data-ttu-id="73d1f-105">Si vous ne possédez pas déjà une source de données partagée, vous devez en créer une.</span><span class="sxs-lookup"><span data-stu-id="73d1f-105">If you do not already have a shared data source, you must create one.</span></span>  
  
 <span data-ttu-id="73d1f-106">Le modèle de rapport que vous générez est entièrement basé sur le schéma de la source de données partagée.</span><span class="sxs-lookup"><span data-stu-id="73d1f-106">The report model that you generate is based entirely on the schema of the shared data source.</span></span> <span data-ttu-id="73d1f-107">Vous ne pouvez pas choisir les parties de la source de données à inclure dans le modèle, ni modifier les règles ou les métadonnées d'un modèle généré.</span><span class="sxs-lookup"><span data-stu-id="73d1f-107">You cannot choose which parts of the data source are included in the model, nor can you edit the rules or metadata of a generated model.</span></span> <span data-ttu-id="73d1f-108">Toutefois, vous pouvez définir des propriétés du modèle une fois celui-ci généré et définir les attributions de rôles qui limitent l'accès à l'ensemble ou une partie du modèle.</span><span class="sxs-lookup"><span data-stu-id="73d1f-108">However, you can set properties on the model after it is generated and define role assignments that restrict access to all or part of the model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73d1f-109">Un modèle basé sur Oracle, généré à l’aide de Gestionnaire de rapports ou [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2007 [!INCLUDE[SPS2010](../includes/sps2010-md.md)] , inclut des objets de base de données qui font partie du schéma du compte d’utilisateur utilisé pour se connecter à la source de données Oracle.</span><span class="sxs-lookup"><span data-stu-id="73d1f-109">An Oracle-based model generated using Report Manager or [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2007 [!INCLUDE[SPS2010](../includes/sps2010-md.md)] will include database objects that are a part of the schema for the user account used to connect to the Oracle data source.</span></span> <span data-ttu-id="73d1f-110">Le nom du compte d'utilisateur est spécifié dans les informations d'identification des propriétés de la source de données.</span><span class="sxs-lookup"><span data-stu-id="73d1f-110">The user account name is specified in the data source properties credentials.</span></span>  
  
### <a name="to-create-a-new-data-source-for-a-report-model-using-report-manager"></a><span data-ttu-id="73d1f-111">Pour créer une nouvelle source de données pour un modèle de rapport à l'aide du Gestionnaire de rapports</span><span class="sxs-lookup"><span data-stu-id="73d1f-111">To create a new data source for a report model using Report Manager</span></span>  
  
1.  <span data-ttu-id="73d1f-112">Dans le navigateur Web, tapez l'URL du serveur de rapports dans la barre d'adresses.</span><span class="sxs-lookup"><span data-stu-id="73d1f-112">In your Web browser, type the URL for your report server in the address bar.</span></span>  
  
2.  <span data-ttu-id="73d1f-113">Cliquez sur **Nouvelle source de données**.</span><span class="sxs-lookup"><span data-stu-id="73d1f-113">Click **New Data Source**.</span></span>  
  
3.  <span data-ttu-id="73d1f-114">Dans la zone **Nom** , entrez un nom pour la source de données.</span><span class="sxs-lookup"><span data-stu-id="73d1f-114">In the **Name** box, enter a name for the data source.</span></span>  
  
4.  <span data-ttu-id="73d1f-115">Si vous le souhaitez, entrez une brève description du modèle dans la zone **Description** .</span><span class="sxs-lookup"><span data-stu-id="73d1f-115">Optionally, enter a brief description of the mode in the **Description** text box.</span></span>  
  
5.  <span data-ttu-id="73d1f-116">Vérifiez que la case à cocher **Activer cette source de données** est activée.</span><span class="sxs-lookup"><span data-stu-id="73d1f-116">Verify that the **Enable this data source** check box is selected.</span></span>  
  
6.  <span data-ttu-id="73d1f-117">Dans la liste **Type de connexion** , sélectionnez le type de source de données auquel vous souhaitez vous connecter.</span><span class="sxs-lookup"><span data-stu-id="73d1f-117">In the **Connection type** list, select the data source type to which you want to connect.</span></span> <span data-ttu-id="73d1f-118">Il doit s'agir de l'un des types de connexions suivants : **Oracle**, **Microsoft SQL Server** ou **Microsoft SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="73d1f-118">The connection type must be one of the following: **Oracle**, **Microsoft SQL Server** or **Microsoft SQL Server Analysis Services**.</span></span>  
  
7.  <span data-ttu-id="73d1f-119">Dans la zone **Chaîne de connexion** , entrez la chaîne de connexion qui pointe vers la base de données.</span><span class="sxs-lookup"><span data-stu-id="73d1f-119">In the **Connection string** box, enter the connection string that points to the database.</span></span>  
  
8.  <span data-ttu-id="73d1f-120">Sélectionnez la méthode de connexion dont les utilisateurs du Générateur de rapports devront se servir pour se connecter à la base de données.</span><span class="sxs-lookup"><span data-stu-id="73d1f-120">Select the connection method that Report Builder users will need to use to connect to the database.</span></span>  
  
    -   <span data-ttu-id="73d1f-121">Authentification Windows : sélectionnez cette option si vous souhaitez que le système d'exploitation authentifie les utilisateurs [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73d1f-121">Windows Authentication: Select this option when you want the operating system to authenticate [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] users.</span></span> <span data-ttu-id="73d1f-122">Cette option permet à [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] d'utiliser les fonctionnalités de sécurité de Windows, telles que le chiffrement des mots de passe, pour authentifier les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="73d1f-122">This option allows [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to use Windows security features, such as password encryption, to authenticate users.</span></span> <span data-ttu-id="73d1f-123">Nous vous recommandons vivement de sélectionner cette option.</span><span class="sxs-lookup"><span data-stu-id="73d1f-123">It is strongly recommended that you select this option.</span></span>  
  
    -   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]<span data-ttu-id="73d1f-124">Authentification : sélectionnez cette option si vous souhaitez que les utilisateurs utilisent un [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] compte de connexion que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="73d1f-124">Authentication: Select this option when you want users to use a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login account that you created.</span></span> <span data-ttu-id="73d1f-125">Les utilisateurs doivent fournir un nom et un mot de passe de connexion [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] valides.</span><span class="sxs-lookup"><span data-stu-id="73d1f-125">Users must supply a valid [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login name and password.</span></span>  
  
        > [!CAUTION]  
        >  <span data-ttu-id="73d1f-126">Dans la mesure du possible, utilisez l’authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="73d1f-126">Whenever possible, use Windows Authentication.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
### <a name="to-create-a-report-model-using-report-manager"></a><span data-ttu-id="73d1f-127">Pour créer un modèle de rapport à l'aide du Gestionnaire de rapports</span><span class="sxs-lookup"><span data-stu-id="73d1f-127">To create a report model using Report Manager</span></span>  
  
1.  <span data-ttu-id="73d1f-128">Dans le Gestionnaire de rapports, sélectionnez la source de données à utiliser pour votre modèle.</span><span class="sxs-lookup"><span data-stu-id="73d1f-128">In Report Manager, select the data source that you want to use for your model.</span></span>  
  
     <span data-ttu-id="73d1f-129">La page Propriétés apparaît.</span><span class="sxs-lookup"><span data-stu-id="73d1f-129">The Properties page is displayed.</span></span>  
  
2.  <span data-ttu-id="73d1f-130">Vérifiez que vous souhaitez utiliser les options spécifiées pour la source de données.</span><span class="sxs-lookup"><span data-stu-id="73d1f-130">Verify that you want to use the options specified for the data source.</span></span>  
  
3.  <span data-ttu-id="73d1f-131">Cliquez sur **Générer le modèle**.</span><span class="sxs-lookup"><span data-stu-id="73d1f-131">Click **Generate Model**.</span></span>  
  
     <span data-ttu-id="73d1f-132">La page Général apparaît pour la source de données.</span><span class="sxs-lookup"><span data-stu-id="73d1f-132">The General page is displayed for the data source.</span></span>  
  
4.  <span data-ttu-id="73d1f-133">Dans la zone **Nom** , entrez un nom pour le modèle de rapport.</span><span class="sxs-lookup"><span data-stu-id="73d1f-133">In the **Name** box, enter a name for the report model.</span></span>  
  
5.  <span data-ttu-id="73d1f-134">Dans la zone **Description** , entrez une brève description du modèle.</span><span class="sxs-lookup"><span data-stu-id="73d1f-134">In the **Description** box, enter a brief description of the model.</span></span>  
  
6.  <span data-ttu-id="73d1f-135">Pour spécifier un nouvel emplacement dans lequel enregistrer le modèle de rapport, cliquez sur **Modifier l'emplacement**.</span><span class="sxs-lookup"><span data-stu-id="73d1f-135">To specify a new location to save the report model to, click **Change Location**.</span></span>  
  
     <span data-ttu-id="73d1f-136">Par défaut, le modèle de rapport est enregistré dans la page d'accueil du Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="73d1f-136">By default, the report model is saved to Report Manager Home.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="73d1f-137">Le modèle de rapport est créé et enregistré à l'emplacement que vous avez spécifié.</span><span class="sxs-lookup"><span data-stu-id="73d1f-137">The report model is created and saved to the location that you specified.</span></span> <span data-ttu-id="73d1f-138">Vous pouvez octroyer des autorisations à ce modèle à l'aide du Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="73d1f-138">You can assign permissions to this model by using Report Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73d1f-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="73d1f-139">See Also</span></span>  
 <span data-ttu-id="73d1f-140">[Octroi d'autorisations sur un serveur de rapports en mode natif](security/granting-permissions-on-a-native-mode-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="73d1f-140">[Granting Permissions on a Native Mode Report Server](security/granting-permissions-on-a-native-mode-report-server.md) </span></span>  
 <span data-ttu-id="73d1f-141">[Connexions de données, sources de données et chaînes de connexion dans Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="73d1f-141">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="73d1f-142">Page Nouvelle source de données &#40;Gestionnaire de rapports&#41;</span><span class="sxs-lookup"><span data-stu-id="73d1f-142">New Data Source Page &#40;Report Manager&#41;</span></span>](../../2014/reporting-services/new-data-source-page-report-manager.md)  
  
  
