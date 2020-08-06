---
title: Créer une base de connaissances | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.kb.selectkb.f1
- sql12.dqs.kb.newkb.f1
ms.assetid: 2733a284-975f-4650-abcc-cc2aad074cab
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 281fa663362cc4462cd4e32839c1eaf6908394e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601716"
---
# <a name="create-a-knowledge-base"></a><span data-ttu-id="b0ed6-102">Créer une base de connaissances</span><span class="sxs-lookup"><span data-stu-id="b0ed6-102">Create a Knowledge Base</span></span>
  <span data-ttu-id="b0ed6-103">Cette rubrique explique comment créer une base de connaissances dans [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) et la préparer pour la gestion de l'arborescence des domaines, la découverte de la connaissance ou l'ajout d'une stratégie correspondante.</span><span class="sxs-lookup"><span data-stu-id="b0ed6-103">This topic describes how to create a knowledge base in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS), and prepare it for domain management, knowledge discovery, or adding a matching policy.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b0ed6-104">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="b0ed6-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="b0ed6-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="b0ed6-105">Prerequisites</span></span>  
 <span data-ttu-id="b0ed6-106">Pour créer une base de connaissances, vous devez avoir installé [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] et [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0ed6-106">To create a knowledge base, you must have installed [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] and [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b0ed6-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b0ed6-107">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b0ed6-108">Autorisations</span><span class="sxs-lookup"><span data-stu-id="b0ed6-108">Permissions</span></span>  
 <span data-ttu-id="b0ed6-109">Vous devez disposer du rôle dqs_kb_editor ou dqs_administrator sur la base de données DQS_MAIN pour créer une base de connaissances.</span><span class="sxs-lookup"><span data-stu-id="b0ed6-109">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to create a knowledge base.</span></span>  
  
##  <a name="create-a-knowledge-base"></a><a name="Createaknowledgebase"></a><span data-ttu-id="b0ed6-110">Créer une base de connaissances</span><span class="sxs-lookup"><span data-stu-id="b0ed6-110">Create a knowledge base</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="b0ed6-111">[Exécutez l’Application Data Quality client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="b0ed6-111">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="b0ed6-112">Dans l'écran d'accueil de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , cliquez sur **Nouvelle base de connaissances**.</span><span class="sxs-lookup"><span data-stu-id="b0ed6-112">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **New knowledge base**.</span></span>  
  
3.  <span data-ttu-id="b0ed6-113">Entrez un nom et une description pour la nouvelle base de connaissances.</span><span class="sxs-lookup"><span data-stu-id="b0ed6-113">Enter a name and description for the new knowledge base.</span></span>  
  
4.  <span data-ttu-id="b0ed6-114">Dans **Créer la base de connaissances à partir de**, sélectionnez l'élément sur lequel fonder la base de connaissances :</span><span class="sxs-lookup"><span data-stu-id="b0ed6-114">In **Create knowledge base from**, select what to base the knowledge base on:</span></span>  
  
    -   <span data-ttu-id="b0ed6-115">Sélectionnez **Aucun** si vous ne souhaitez pas fonder la nouvelle base de connaissances sur une base de connaissances ou un fichier de données existants.</span><span class="sxs-lookup"><span data-stu-id="b0ed6-115">Select **None** if you do not want to base the new knowledge base on an existing knowledge base or data file.</span></span>  
  
    -   <span data-ttu-id="b0ed6-116">Sélectionnez **Base de connaissances existante** pour fonder la nouvelle base de connaissances sur une base de connaissances qui a déjà été créée sur [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)]ou sur la base de connaissances par défaut.</span><span class="sxs-lookup"><span data-stu-id="b0ed6-116">Select **Existing Knowledge Base** to base the new knowledge base on a knowledge base that has already been created on [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], or on the default knowledge base.</span></span> <span data-ttu-id="b0ed6-117">Sélectionnez la base de connaissances dans la liste déroulante **Sélectionner la Base de connaissances** ou cliquez sur **Parcourir** pour afficher la boîte de dialogue **Sélectionner une Base de connaissances** , sélectionnez une base de connaissances existante sur laquelle fonder la nouvelle base de connaissances, puis cliquez **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0ed6-117">Select the knowledge base from the **Select Knowledge Base** drop-down list, or click **Browse** to display the **Select a Knowledge Base** dialog box, select an existing knowledge base to base the new knowledge base on, and then click **OK**.</span></span> <span data-ttu-id="b0ed6-118">Lorsque vous sélectionnez une base de connaissances à partir de la Tablet PC, les domaines et les règles correspondantes de la base de connaissances seront affichés dans le volet droit de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b0ed6-118">When you select a knowledge base from the tablet, the domains and matching rules in the knowledge base will be displayed in the right-hand pane of the dialog box.</span></span> <span data-ttu-id="b0ed6-119">Vous pouvez également sélectionner la base de connaissances **Données DQS** , qui est la base de connaissances par défaut contenant les domaines courants prêts à l’emploi et les connaissances relatives aux sociétés, adresses et données externes aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="b0ed6-119">You can also select the **DQS Data** knowledge base, which is the default knowledge base that contains common out-of-the-box domains and knowledge related to U.S. company, address, and party data.</span></span>  
  
    -   <span data-ttu-id="b0ed6-120">Sélectionnez **Importer à partir d'un fichier DQS** pour fonder la nouvelle base de connaissances sur un fichier DQS de [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0ed6-120">Select **Import from DQS File** to base the new knowledge base on a DQS file on [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span> <span data-ttu-id="b0ed6-121">Cliquez **Parcourir**, sélectionnez un fichier de données de DQS avec une extension .dqs, puis cliquez **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0ed6-121">Click **Browse**, select a DQS data file with an extension of .dqs, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="b0ed6-122">Dans **Sélectionner une activité**, sélectionnez l'activité que vous souhaitez effectuer sur la nouvelle base de connaissances :</span><span class="sxs-lookup"><span data-stu-id="b0ed6-122">In **Select Activity**, select the activity that you want to perform on the new knowledge base:</span></span>  
  
    -   <span data-ttu-id="b0ed6-123">Sélectionnez **Gestion de l'arborescence du domaine** pour créer la base de connaissances et accédez aux écrans que vous utilisez pour modifier les domaines de la base de connaissances.</span><span class="sxs-lookup"><span data-stu-id="b0ed6-123">Select **Domain Management** to create the knowledge base and enter the screens that you use to modify the domains in the knowledge base.</span></span>  
  
    -   <span data-ttu-id="b0ed6-124">Sélectionnez **Découverte des connaissances** pour créer la base de connaissances et accédez à l'Assistant que vous utilisez pour analyser un échantillon de données et remplir les domaines de la base de connaissances avec les résultats.</span><span class="sxs-lookup"><span data-stu-id="b0ed6-124">Select **Knowledge Discovery** to create the knowledge base and enter the wizard that you use to analyze a data sample and populate the domains of the knowledge base with the results.</span></span>  
  
    -   <span data-ttu-id="b0ed6-125">Sélectionnez **Stratégie de correspondance** pour créer une stratégie de correspondance et l'ajouter à la base de connaissances.</span><span class="sxs-lookup"><span data-stu-id="b0ed6-125">Select **Matching Policy** to create a matching policy and add it to the knowledge base.</span></span>  
  
6.  <span data-ttu-id="b0ed6-126">Cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="b0ed6-126">Click **Create**.</span></span>  
  
##  <a name="follow-up-after-creating-a-knowledge-base"></a><a name="FollowUp"></a><span data-ttu-id="b0ed6-127">Suivi : après avoir créé une base de connaissances</span><span class="sxs-lookup"><span data-stu-id="b0ed6-127">Follow Up: After Creating a Knowledge Base</span></span>  
 <span data-ttu-id="b0ed6-128">Après avoir créé une base de connaissances, vous voyez s'afficher un Assistant qui vous permet d'effectuer la découverte des connaissances, un Assistant qui vous permet de créer une stratégie de correspondance, ou des pages pour exécuter la gestion des domaines.</span><span class="sxs-lookup"><span data-stu-id="b0ed6-128">After you create a knowledge base, you are presented with a wizard that you can use to perform knowledge discovery, a wizard to create a matching policy, or pages to perform domain management.</span></span> <span data-ttu-id="b0ed6-129">Pour plus d’informations sur la découverte des connaissances, la gestion de domaine ou la stratégie de correspondance, consultez [Effectuer une découverte des connaissances](../../2014/data-quality-services/perform-knowledge-discovery.md), [Gestion d’un domaine](../../2014/data-quality-services/managing-a-domain.md) ou [Créer une stratégie de correspondance](../../2014/data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="b0ed6-129">For more information about the knowledge discovery, domain management, or matching policy, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md), [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md), or [Create a Matching Policy](../../2014/data-quality-services/create-a-matching-policy.md).</span></span>  
  
  
