---
title: Créer ou personnaliser une bibliothèque de flux de données (PowerPivot pour SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data feed library
- data feeds [Analysis Services with SharePoint]
ms.assetid: 699fbeb9-42ab-436b-beba-214db51ea3dd
author: minewiskan
ms.author: owend
ms.openlocfilehash: b86f63c1af094ea9e8a2a1149debeac387bccbf0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698580"
---
# <a name="create-or-customize-a-data-feed-library-powerpivot-for-sharepoint"></a><span data-ttu-id="246de-102">Créer ou personnaliser une bibliothèque de flux de données (PowerPivot pour SharePoint)</span><span class="sxs-lookup"><span data-stu-id="246de-102">Create or Customize a Data Feed Library (PowerPivot for SharePoint)</span></span>
  <span data-ttu-id="246de-103">Une *bibliothèque de flux de données* est une bibliothèque SharePoint spécifique qui permet d’enregistrer et de partager des documents de service de données Atom (.atomsvc).</span><span class="sxs-lookup"><span data-stu-id="246de-103">A *data feed library* is a special-purpose SharePoint library that enables you to register and share Atom data service documents (.atomsvc).</span></span> <span data-ttu-id="246de-104">Ces documents fournissent des flux XML aux classeurs [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] ou à d'autres applications clientes qui prennent en charge le format de flux Atom.</span><span class="sxs-lookup"><span data-stu-id="246de-104">These documents provide XML data feeds to [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] workbooks or other client applications that support the Atom data feed format.</span></span> <span data-ttu-id="246de-105">Une bibliothèque de flux de données est différente des autres bibliothèques SharePoint, car elle vous donne la possibilité :</span><span class="sxs-lookup"><span data-stu-id="246de-105">A data feed library is different from other SharePoint libraries because it gives you the ability to:</span></span>

-   <span data-ttu-id="246de-106">de créer ou modifier un *document de service de données*, utilisé pour spécifier une connexion HTTP à un flux spécifique ;</span><span class="sxs-lookup"><span data-stu-id="246de-106">Create or edit a *data service document*, used to specify an HTTP connection to a specific feed.</span></span>

-   <span data-ttu-id="246de-107">de partager et gérer des documents de service de données depuis un emplacement central ;</span><span class="sxs-lookup"><span data-stu-id="246de-107">Share and manage data service documents in a central location.</span></span>

-   <span data-ttu-id="246de-108">Identifiez visuellement des documents de service de données à l’aide d’une icône, afin de pouvoir distinguer facilement les documents de service des autres documents stockés dans la même bibliothèque : ![GMNI_IconDataFeed](../media/gmni-icondatafeed.gif "GMNI_IconDataFeed")</span><span class="sxs-lookup"><span data-stu-id="246de-108">Visually identify data service documents by an icon, so that you can easily distinguish service documents from other documents stored in the same library: ![GMNI_IconDataFeed](../media/gmni-icondatafeed.gif "GMNI_IconDataFeed")</span></span>

 <span data-ttu-id="246de-109">Une bibliothèque de flux de données contient toujours des fichiers de documents de service de données (.atomsvc), et jamais le flux de données lui-même.</span><span class="sxs-lookup"><span data-stu-id="246de-109">A data feed library always contains data service document (.atomsvc) files, and never the data feed itself.</span></span> <span data-ttu-id="246de-110">Contrairement à un flux de données, qui est constitué de données XML statiques, le document de service de données spécifie l'URL d'un service ou d'une application qui génère un flux à la demande, fournissant ainsi des informations de connexion réutilisables pour les opérations d'importation répétées.</span><span class="sxs-lookup"><span data-stu-id="246de-110">Unlike a data feed, which consists of static XML data, the data service document specifies a URL to a service or application that generates a feed upon request, providing reusable connection information for repeatable import operations.</span></span>

 <span data-ttu-id="246de-111">Cette rubrique contient les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="246de-111">This topic contains the following sections:</span></span>

 [<span data-ttu-id="246de-112">Composants requis</span><span class="sxs-lookup"><span data-stu-id="246de-112">Prerequisites</span></span>](#prereq)

 [<span data-ttu-id="246de-113">Créer une bibliothèque de flux</span><span class="sxs-lookup"><span data-stu-id="246de-113">Create a New Data Feed Library</span></span>](#createlib)

 [<span data-ttu-id="246de-114">Ajouter le type de contenu du flux à une bibliothèque</span><span class="sxs-lookup"><span data-stu-id="246de-114">Add the Data Feed Content Type to Any Library</span></span>](#addtolib)

##  <a name="prerequisites"></a><a name="prereq"></a> <span data-ttu-id="246de-115">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="246de-115">Prerequisites</span></span>
 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] <span data-ttu-id="246de-116">L’intégration de la fonctionnalité doit être activée pour les sites pour lesquels vous créez la bibliothèque de flux de données.</span><span class="sxs-lookup"><span data-stu-id="246de-116">feature integration must be activated for the sites for which you are creating the data feed library.</span></span> <span data-ttu-id="246de-117">Si le type de modèle de bibliothèque de flux n'est pas disponible, la cause en est probablement que cette condition préalable n'est pas respectée.</span><span class="sxs-lookup"><span data-stu-id="246de-117">If the data feed library template type is not available, the most likely cause is that this prerequisite has not been met.</span></span> <span data-ttu-id="246de-118">Pour plus d’informations, consultez [activer l’intégration des fonctionnalités PowerPivot pour les collections de sites dans l’administration centrale](activate-power-pivot-integration-for-site-collections-in-ca.md).</span><span class="sxs-lookup"><span data-stu-id="246de-118">For more information, see [Activate PowerPivot Feature Integration for Site Collections in Central Administration](activate-power-pivot-integration-for-site-collections-in-ca.md).</span></span>

 <span data-ttu-id="246de-119">Vous devez être propriétaire de site pour créer la bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="246de-119">You must be a site owner to create the library.</span></span>

##  <a name="create-a-new-data-feed-library"></a><a name="createlib"></a><span data-ttu-id="246de-120">Créer une nouvelle bibliothèque de flux de données</span><span class="sxs-lookup"><span data-stu-id="246de-120">Create a New Data Feed Library</span></span>
 <span data-ttu-id="246de-121">La création d’une bibliothèque de flux de données est la première étape de l’activation des flux de données pour les classeurs [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="246de-121">Creating a data feed library is the first step to enabling data feeds for [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] workbooks.</span></span> <span data-ttu-id="246de-122">Avant de pouvoir créer un document, une bibliothèque de flux doit être en place, car c'est elle qui fournit les pages d'application et de gestion de documents de service de données.</span><span class="sxs-lookup"><span data-stu-id="246de-122">Because a data feed library provides application and management pages for data service documents, you must have this library in place before you can create a new document.</span></span>

 <span data-ttu-id="246de-123">Une bibliothèque de flux de données est basée sur un modèle intégré et sur un *type de contenu de document de service de données* préconfiguré qui définit les propriétés et comportements d’un document de service de données.</span><span class="sxs-lookup"><span data-stu-id="246de-123">A data feed library is based on a built-in template and a preconfigured *data service document content type* that defines properties and behaviors for a data service document.</span></span>

1.  <span data-ttu-id="246de-124">Cliquez sur **Actions du site** dans l’angle supérieur gauche de la page.</span><span class="sxs-lookup"><span data-stu-id="246de-124">Click **Site Actions** at the top left corner of the page.</span></span>

2.  <span data-ttu-id="246de-125">Cliquez sur **plus d’options**...</span><span class="sxs-lookup"><span data-stu-id="246de-125">Click **More Options**...</span></span>

3.  <span data-ttu-id="246de-126">Sous Bibliothèques, cliquez sur **Bibliothèque de flux de données**.</span><span class="sxs-lookup"><span data-stu-id="246de-126">Under Libraries, click **Data Feed Library**.</span></span>

4.  <span data-ttu-id="246de-127">Tapez le nom et la description, ainsi que les préférences en termes de démarrage et de version.</span><span class="sxs-lookup"><span data-stu-id="246de-127">Type the name, description, launch, and version preferences.</span></span> <span data-ttu-id="246de-128">Incluez des informations descriptives pour aider les utilisateurs à identifier cette bibliothèque en tant qu'emplacement de stockage pour les documents de service de données.</span><span class="sxs-lookup"><span data-stu-id="246de-128">Include descriptive information to help users identify this library as storage for data service documents.</span></span>

5.  <span data-ttu-id="246de-129">Cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="246de-129">Click **Create**.</span></span>

 <span data-ttu-id="246de-130">Un lien vers la bibliothèque de flux s'affiche dans le volet de navigation Lancement rapide du site actuel.</span><span class="sxs-lookup"><span data-stu-id="246de-130">A link to the data feed library will appear in the navigation Quick Launch pane for the current site.</span></span>

 <span data-ttu-id="246de-131">Après avoir créé une bibliothèque, vous pouvez l'utiliser pour créer des documents de service de données.</span><span class="sxs-lookup"><span data-stu-id="246de-131">After you create a library, you can use it to create data service documents.</span></span> <span data-ttu-id="246de-132">Pour plus d’informations, consultez [utiliser des flux de données &#40;PowerPivot pour SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="246de-132">For more information, see [Use Data Feeds &#40;PowerPivot for SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md).</span></span>

##  <a name="add-the-data-feed-content-type-to-any-library"></a><a name="addtolib"></a><span data-ttu-id="246de-133">Ajouter le type de contenu de flux de données à n’importe quelle bibliothèque</span><span class="sxs-lookup"><span data-stu-id="246de-133">Add the Data Feed Content Type to Any Library</span></span>
 <span data-ttu-id="246de-134">Si vous ne souhaitez pas créer de bibliothèque de flux de données dédiée, mais souhaitez toujours créer et gérer des documents de service de données à partir d'un site SharePoint, vous pouvez ajouter et configurer manuellement le type de contenu de document de service de données pour toute bibliothèque que vous utiliserez pour partager des fichiers de documents de service de données (.atomsvc).</span><span class="sxs-lookup"><span data-stu-id="246de-134">If you do not want to create a dedicated data feed library, but you still want to create and manage data service documents from a SharePoint site, you can manually add and configure the data service document content type for any library that you will use to share data service document (.atomsvc) files.</span></span>

 <span data-ttu-id="246de-135">Pour ajouter et configurer un type de contenu, vous devez au minimum disposer d'une autorisation Gérer les listes.</span><span class="sxs-lookup"><span data-stu-id="246de-135">You must have at least the Manage Lists permission to add and configure a content type.</span></span> <span data-ttu-id="246de-136">Cette autorisation est intégrée au niveau d'autorisation de conception et aux niveaux supérieurs.</span><span class="sxs-lookup"><span data-stu-id="246de-136">This permission is built into the Design permission level and above.</span></span>

 <span data-ttu-id="246de-137">Les étapes suivantes doivent être répétées pour chaque bibliothèque dans laquelle vous souhaitez créer ou modifier des documents d'inscription de flux de données.</span><span class="sxs-lookup"><span data-stu-id="246de-137">The following steps must be repeated for each library in which you want to create or edit data feed registration documents.</span></span>

#### <a name="step-1-enable-content-type-management"></a><span data-ttu-id="246de-138">Étape 1 : activer la gestion des types de contenu</span><span class="sxs-lookup"><span data-stu-id="246de-138">Step 1: Enable Content Type Management</span></span>

1.  <span data-ttu-id="246de-139">Ouvrez la bibliothèque de documents pour laquelle activer plusieurs types de contenu.</span><span class="sxs-lookup"><span data-stu-id="246de-139">Open the document library for which you want to enable multiple content types.</span></span>

2.  <span data-ttu-id="246de-140">Sur le ruban SharePoint, dans Outils de bibliothèque, cliquez sur **Bibliothèque**.</span><span class="sxs-lookup"><span data-stu-id="246de-140">On the SharePoint ribbon, in Library Tools, click **Library**.</span></span>

3.  <span data-ttu-id="246de-141">Cliquez sur **Settings**.</span><span class="sxs-lookup"><span data-stu-id="246de-141">Click **Settings**.</span></span>

4.  <span data-ttu-id="246de-142">Cliquez sur **Paramètres de la bibliothèque**.</span><span class="sxs-lookup"><span data-stu-id="246de-142">Click **Library Settings**.</span></span>

5.  <span data-ttu-id="246de-143">Sous Paramètres généraux, cliquez sur **Paramètres avancés**.</span><span class="sxs-lookup"><span data-stu-id="246de-143">In General Settings, click **Advanced settings**.</span></span>

6.  <span data-ttu-id="246de-144">Dans Types de contenu, dans la section « Autoriser la gestion des types de contenu ? »,</span><span class="sxs-lookup"><span data-stu-id="246de-144">In Content Types, in the "Allow management of content types?"</span></span> <span data-ttu-id="246de-145">cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="246de-145">section, click **Yes**.</span></span>

7.  <span data-ttu-id="246de-146">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="246de-146">Click **OK**.</span></span>

#### <a name="step-2-add-the-data-service-document-content-type"></a><span data-ttu-id="246de-147">Étape 2 : ajouter le type de contenu du document de service de données</span><span class="sxs-lookup"><span data-stu-id="246de-147">Step 2: Add the Data Service Document Content Type</span></span>

1.  <span data-ttu-id="246de-148">Dans la section Types de contenu, cliquez sur **Ajouter à partir de types de contenu de site existants**.</span><span class="sxs-lookup"><span data-stu-id="246de-148">In the Content Types section, click **Add from existing site content types**.</span></span> <span data-ttu-id="246de-149">Si vous ne voyez pas cette page, retournez au site, cliquez sur **Bibliothèque** dans Outils de bibliothèque, puis sur **Paramètres de la bibliothèque**.</span><span class="sxs-lookup"><span data-stu-id="246de-149">If you do not see this page, go back to the site, click **Library** in Library Tools, and then click **Library Settings**.</span></span>

2.  <span data-ttu-id="246de-150">Dans Types de contenu, cliquez sur **Ajouter à partir de types de contenu de site existants**.</span><span class="sxs-lookup"><span data-stu-id="246de-150">In Content Types, click **Add from existing site content types**.</span></span>

3.  <span data-ttu-id="246de-151">Dans Sélectionner des types de contenu dans, sélectionnez **Aide à la décision**.</span><span class="sxs-lookup"><span data-stu-id="246de-151">In Select site content types from:, select **Business Intelligence**.</span></span>

4.  <span data-ttu-id="246de-152">Dans Types de contenu de site disponibles, cliquez sur **Document de service de données**, puis sur **Ajouter** pour déplacer le type de contenu sélectionné dans la liste Types de contenu à ajouter.</span><span class="sxs-lookup"><span data-stu-id="246de-152">In Available Site Content Types, click **Data Service Document**, and then click **Add** to move the selected content type to the Content types to add list.</span></span>

5.  <span data-ttu-id="246de-153">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="246de-153">Click **OK**.</span></span>

#### <a name="step-3-verify-data-service-document-configuration"></a><span data-ttu-id="246de-154">Étape 3 : vérifier la configuration des documents de service de données</span><span class="sxs-lookup"><span data-stu-id="246de-154">Step 3: Verify Data Service Document Configuration</span></span>

1.  <span data-ttu-id="246de-155">Ouvrez la page d'accueil du site.</span><span class="sxs-lookup"><span data-stu-id="246de-155">Open the site home page.</span></span>

2.  <span data-ttu-id="246de-156">Ouvrez la bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="246de-156">Open the library.</span></span>

3.  <span data-ttu-id="246de-157">Sur le ruban SharePoint, cliquez sur **Documents**.</span><span class="sxs-lookup"><span data-stu-id="246de-157">On the SharePoint ribbon, click **Documents**.</span></span>

4.  <span data-ttu-id="246de-158">Cliquez sur la flèche vers le bas de Nouveau document et sélectionnez **Document de service de données**.</span><span class="sxs-lookup"><span data-stu-id="246de-158">Click the down arrow on New Document, and select **Data Service Document**.</span></span> <span data-ttu-id="246de-159">La page Nouveau document de service de données s'affiche.</span><span class="sxs-lookup"><span data-stu-id="246de-159">The New Data Service Document page should appear.</span></span>

## <a name="see-also"></a><span data-ttu-id="246de-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="246de-160">See Also</span></span>
 <span data-ttu-id="246de-161">[Utiliser des flux de données &#40;PowerPivot pour SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md) [supprimer une bibliothèque de flux de données PowerPivot](delete-a-power-pivot-data-feed-library.md) [administration et configuration du serveur PowerPivot dans les flux de données PowerPivot de l’administration centrale](power-pivot-server-administration-and-configuration-in-central-administration.md) [PowerPivot Data Feeds](power-pivot-data-feeds.md)</span><span class="sxs-lookup"><span data-stu-id="246de-161">[Use Data Feeds &#40;PowerPivot for SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md) [Delete a PowerPivot Data Feed Library](delete-a-power-pivot-data-feed-library.md) [PowerPivot Server Administration and Configuration in Central Administration](power-pivot-server-administration-and-configuration-in-central-administration.md) [PowerPivot Data Feeds](power-pivot-data-feeds.md)</span></span>


