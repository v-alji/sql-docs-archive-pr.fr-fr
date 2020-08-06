---
title: Ajouter un type de contenu de connexion de modèle sémantique BI à une bibliothèque (PowerPivot pour SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 145505ed-50bc-4528-912b-2a5cd2566011
author: minewiskan
ms.author: owend
ms.openlocfilehash: ecd40193b382aa692beeadd55ab8f9388c328620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613175"
---
# <a name="add-a-bi-semantic-model-connection-content-type-to-a-library-powerpivot-for-sharepoint"></a><span data-ttu-id="7d5a1-102">Ajouter un type de contenu de connexion de modèle sémantique BI à une bibliothèque (PowerPivot pour SharePoint)</span><span class="sxs-lookup"><span data-stu-id="7d5a1-102">Add a BI Semantic Model Connection Content Type to a Library (PowerPivot for SharePoint)</span></span>
  <span data-ttu-id="7d5a1-103">Une connexion de modèle sémantique BI est créée dans SharePoint et assure la redirection vers les données de modèle sémantique Business Intelligence situées dans un classeur PowerPivot ou une base de données model tabulaire Analysis Services sur un serveur réseau.</span><span class="sxs-lookup"><span data-stu-id="7d5a1-103">A BI semantic model connection is created in SharePoint and provides redirection to business intelligence semantic model data in a PowerPivot workbook or Analysis Services tabular model database on a network server.</span></span> <span data-ttu-id="7d5a1-104">Avant de pouvoir créer une connexion de modèle sémantique BI dans SharePoint, vous devez étendre une bibliothèque de documents pour autoriser la création d'un fichier .bism.</span><span class="sxs-lookup"><span data-stu-id="7d5a1-104">Before you can create a BI semantic model connection in SharePoint, you must extend a document library to allow the creation of a .bism file.</span></span> <span data-ttu-id="7d5a1-105">Cette étape est effectuée une seule fois pour chaque bibliothèque, mais vous devrez la répéter pour toutes les bibliothèques à partir desquelles vous souhaitez créer des fichiers .bism.</span><span class="sxs-lookup"><span data-stu-id="7d5a1-105">This step only needs to be performed once for each library, but you will need to repeat it for any library from which you want to create .bism files.</span></span> <span data-ttu-id="7d5a1-106">Les meilleures pratiques recommandent de créer une bibliothèque centralisée pour le stockage des fichiers .bism, afin que vous puissiez gérer les autorisations dans un seul emplacement.</span><span class="sxs-lookup"><span data-stu-id="7d5a1-106">Best practices recommend that you create a centralized library for storing .bism files so that you can manage permissions in one place.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7d5a1-107">Si vous utilisez déjà des bibliothèques de connexion de données SharePoint, le type de contenu Connexion de modèle sémantique BI est ajouté automatiquement à ce modèle de bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="7d5a1-107">If you already use SharePoint Data Connection Libraries, the BI Semantic Model Connection content type is automatically added to that library template.</span></span> <span data-ttu-id="7d5a1-108">Vous pouvez ignorer les étapes de cette section si vous utilisez une bibliothèque de connexions de données qui vous permet déjà de créer des documents de connexion de modèle sémantique BI.</span><span class="sxs-lookup"><span data-stu-id="7d5a1-108">You can skip the steps in this section if you use a data connection library that already lets you create new BI semantic model connection documents.</span></span>  
  
##  <a name="add-the-content-type-to-a-document-library"></a><a name="bkmk_addtype"></a> <span data-ttu-id="7d5a1-109">Ajouter le type de contenu à une bibliothèque de documents</span><span class="sxs-lookup"><span data-stu-id="7d5a1-109">Add the content type to a document library</span></span>  
 <span data-ttu-id="7d5a1-110">Pour ajouter et configurer un type de contenu, vous devez au minimum disposer d'une autorisation Gérer les listes.</span><span class="sxs-lookup"><span data-stu-id="7d5a1-110">You must have at least the Manage Lists permission to add and configure a content type.</span></span> <span data-ttu-id="7d5a1-111">Cette autorisation est intégrée au niveau d'autorisation de conception et aux niveaux supérieurs.</span><span class="sxs-lookup"><span data-stu-id="7d5a1-111">This permission is built into the Design permission level and above.</span></span>  
  
 <span data-ttu-id="7d5a1-112">Le site qui contient la bibliothèque de documents doit disposer d'une activation des fonctionnalités pour PowerPivot pour SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7d5a1-112">The site that contains the document library must have feature activation for PowerPivot for SharePoint.</span></span> <span data-ttu-id="7d5a1-113">Pour plus d’informations, consultez [activer l’intégration des fonctionnalités PowerPivot pour les collections de sites dans l’administration centrale](activate-power-pivot-integration-for-site-collections-in-ca.md).</span><span class="sxs-lookup"><span data-stu-id="7d5a1-113">For more information, see [Activate PowerPivot Feature Integration for Site Collections in Central Administration](activate-power-pivot-integration-for-site-collections-in-ca.md).</span></span>  
  
1.  <span data-ttu-id="7d5a1-114">Ouvrez la bibliothèque de documents pour laquelle activer le type de contenu Connexion de modèle sémantique BI.</span><span class="sxs-lookup"><span data-stu-id="7d5a1-114">Open the document library for which you want to enable the BI Semantic Model Connection content type.</span></span>  
  
2.  <span data-ttu-id="7d5a1-115">Sur le ruban SharePoint, dans Outils de bibliothèque, cliquez sur **Bibliothèque**.</span><span class="sxs-lookup"><span data-stu-id="7d5a1-115">On the SharePoint ribbon, in Library Tools, click **Library**.</span></span>  
  
3.  <span data-ttu-id="7d5a1-116">Cliquez sur **Paramètres de la bibliothèque**.</span><span class="sxs-lookup"><span data-stu-id="7d5a1-116">Click **Library Settings**.</span></span>  
  
4.  <span data-ttu-id="7d5a1-117">Sous Paramètres généraux, cliquez sur **Paramètres avancés**.</span><span class="sxs-lookup"><span data-stu-id="7d5a1-117">In General Settings, click **Advanced settings**.</span></span>  
  
5.  <span data-ttu-id="7d5a1-118">Dans Types de contenu, dans la section « Autoriser la gestion des types de contenu ? »,</span><span class="sxs-lookup"><span data-stu-id="7d5a1-118">In Content Types, in the "Allow management of content types?"</span></span> <span data-ttu-id="7d5a1-119">cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="7d5a1-119">section, click **Yes**.</span></span>  
  
6.  <span data-ttu-id="7d5a1-120">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7d5a1-120">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="7d5a1-121">Dans la section Types de contenu, cliquez sur **Ajouter à partir de types de contenu de site existants**.</span><span class="sxs-lookup"><span data-stu-id="7d5a1-121">In the Content Types section, click **Add from existing site content types**.</span></span> <span data-ttu-id="7d5a1-122">Si vous ne voyez pas cette page, retournez au site, cliquez sur **Bibliothèque** dans Outils de bibliothèque, puis sur **Paramètres de la bibliothèque**.</span><span class="sxs-lookup"><span data-stu-id="7d5a1-122">If you do not see this page, go back to the site, click **Library** in Library Tools, and then click **Library Settings**.</span></span>  
  
8.  <span data-ttu-id="7d5a1-123">Dans Types de contenu, cliquez sur **Ajouter à partir de types de contenu de site existants**.</span><span class="sxs-lookup"><span data-stu-id="7d5a1-123">In Content Types, click **Add from existing site content types**.</span></span>  
  
9. <span data-ttu-id="7d5a1-124">Dans Sélectionner des types de contenu dans, sélectionnez **Aide à la décision**.</span><span class="sxs-lookup"><span data-stu-id="7d5a1-124">In Select site content types from:, select **Business Intelligence**.</span></span>  
  
10. <span data-ttu-id="7d5a1-125">Dans Types de contenu de site disponibles, cliquez sur **Fichier de connexion de modèle sémantique BI**, puis sur **Ajouter** pour déplacer le type de contenu sélectionné dans la liste Types de contenu à ajouter.</span><span class="sxs-lookup"><span data-stu-id="7d5a1-125">In Available Site Content Types, click **BI Semantic Model Connection File**, and then click **Add** to move the selected content type to the Content types to add list.</span></span>  
  
11. <span data-ttu-id="7d5a1-126">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7d5a1-126">Click **OK**.</span></span>  
  
12. <span data-ttu-id="7d5a1-127">Pour vérifier que vous avez ajouté le type de contenu, revenez à la bibliothèque et cliquez sur **Nouveau document** dans la zone Documents du ruban de bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="7d5a1-127">To verify you added the content type, go back to the library and click **New Document** on the Documents area of the library ribbon.</span></span> <span data-ttu-id="7d5a1-128">Vous devez voir **Fichier de connexion de modèle sémantique BI** dans la liste des nouveaux documents.</span><span class="sxs-lookup"><span data-stu-id="7d5a1-128">You should see **BI Semantic Model Connection File** in the New Documents list.</span></span>  
  
     <span data-ttu-id="7d5a1-129">![Sous-menu Nouveau document dans une bibliothèque SharePoint](../media/ssas-bismconnection-new.gif "Sous-menu Nouveau document dans une bibliothèque SharePoint")</span><span class="sxs-lookup"><span data-stu-id="7d5a1-129">![New Document submenu in a SharePoint library](../media/ssas-bismconnection-new.gif "New Document submenu in a SharePoint library")</span></span>  
  
 <span data-ttu-id="7d5a1-130">Après avoir activé le type de contenu Connexion de modèle sémantique BI pour une bibliothèque, vous pouvez créer une connexion qui assure la redirection vers des données de modèle sémantique d'entreprise qui peuvent être utilisées par des rapports Excel ou [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7d5a1-130">After you enable the BI semantic model connection content type for a library, you can create a connection that provides redirection to business semantic model data that can be used by Excel or [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] reports.</span></span> <span data-ttu-id="7d5a1-131">Choisissez parmi les liens suivants pour en savoir plus sur cette étape suivante :</span><span class="sxs-lookup"><span data-stu-id="7d5a1-131">Choose from the following links to learn more about this next step:</span></span>  
  
 [<span data-ttu-id="7d5a1-132">Créer une connexion de modèle sémantique BI à un classeur PowerPivot</span><span class="sxs-lookup"><span data-stu-id="7d5a1-132">Create a BI Semantic Model Connection to a PowerPivot Workbook</span></span>](create-a-bi-semantic-model-connection-to-a-power-pivot-workbook.md)  
  
 [<span data-ttu-id="7d5a1-133">Créer une connexion de modèle sémantique BI à une base de données model tabulaire</span><span class="sxs-lookup"><span data-stu-id="7d5a1-133">Create a BI Semantic Model Connection to a Tabular Model Database</span></span>](create-a-bi-semantic-model-connection-to-a-tabular-model-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="7d5a1-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7d5a1-134">See Also</span></span>  
 <span data-ttu-id="7d5a1-135">[Connexion de modèle sémantique BI PowerPivot &#40;. BISM&#41;](power-pivot-bi-semantic-model-connection-bism.md) </span><span class="sxs-lookup"><span data-stu-id="7d5a1-135">[PowerPivot BI Semantic Model Connection &#40;.bism&#41;](power-pivot-bi-semantic-model-connection-bism.md) </span></span>  
 [<span data-ttu-id="7d5a1-136">Utiliser une connexion de modèle sémantique BI dans Excel ou Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7d5a1-136">Use a BI Semantic Model Connection in Excel or Reporting Services</span></span>](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md)  
  
  
