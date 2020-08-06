---
title: Importer une base de connaissances à partir d’un fichier .dqs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 9b9786fe-9e80-429a-afcb-dc3b3dd6f0b0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 522c5f6d8f962cef77e215c21133927e8da4d04f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701993"
---
# <a name="import-a-knowledge-base-from-a-dqs-file"></a><span data-ttu-id="8b4d6-102">Importer une base de connaissances à partir d'un fichier .dqs</span><span class="sxs-lookup"><span data-stu-id="8b4d6-102">Import a Knowledge Base from a .dqs File</span></span>
  <span data-ttu-id="8b4d6-103">Cette rubrique décrit comment importer une base de connaissances entière à partir d'un fichier de données .dqs dans [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="8b4d6-103">This topic describes how to import an entire knowledge base from a .dqs data file in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="8b4d6-104">Vous créez le fichier de données en exportant une base de connaissances existante de l’application [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] (consultez [Exporter une base de connaissances vers un fichier .dqs](../../2014/data-quality-services/export-a-knowledge-base-to-a-dqs-file.md)).</span><span class="sxs-lookup"><span data-stu-id="8b4d6-104">You create the data file by exporting an existing knowledge base from within the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] application (see [Export a Knowledge Base to a .dqs File](../../2014/data-quality-services/export-a-knowledge-base-to-a-dqs-file.md)).</span></span>  
  
 <span data-ttu-id="8b4d6-105">L'utilisation d'un fichier de données .dqs pour exporter le contenu d'une base de connaissances, puis importer le contenu dans une autre base de connaissances sur le même [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] ou un [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] différent simplifie le processus de génération de la connaissance, en permettant de gagner du temps et d'économiser les efforts.</span><span class="sxs-lookup"><span data-stu-id="8b4d6-105">Using a .dqs data file to export the contents of a knowledge base and then import the contents into another knowledge base on the same [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] or a different [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] simplifies the knowledge generation process, saving time and effort.</span></span> <span data-ttu-id="8b4d6-106">Il vous permet de partager une base de connaissances et ses connaissances avec d'autres, ce qui leur fait gagner du temps.</span><span class="sxs-lookup"><span data-stu-id="8b4d6-106">It enables you to share a knowledge base and its knowledge with others, saving them time.</span></span> <span data-ttu-id="8b4d6-107">Le fichier .dqs contient toutes les informations de la base de connaissances, y compris les domaines et la stratégie de correspondance, à l'exception des informations de données de référence jointes.</span><span class="sxs-lookup"><span data-stu-id="8b4d6-107">The .dqs file will contain all knowledge base information, including domains and the matching policy, except for the attached reference data information.</span></span> <span data-ttu-id="8b4d6-108">Les données publiées et non publiées seront importées.</span><span class="sxs-lookup"><span data-stu-id="8b4d6-108">Published and unpublished data will be imported.</span></span>  
  
 <span data-ttu-id="8b4d6-109">Un fichier de données .dqs est chiffré, et ne peut pas être affiché.</span><span class="sxs-lookup"><span data-stu-id="8b4d6-109">A .dqs data file is encrypted, so cannot be viewed.</span></span>  
  
 <span data-ttu-id="8b4d6-110">Lorsque vous importez une base de connaissances, vous pouvez utiliser le même nom, à moins que le nom de la base de connaissances existe déjà dans l'application cliente, auquel cas vous devez la renommer.</span><span class="sxs-lookup"><span data-stu-id="8b4d6-110">When you import a knowledge base, you can use the same name, unless the knowledge base name already exists in the client application, in which case you must rename it.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8b4d6-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="8b4d6-111">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="8b4d6-112">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="8b4d6-112">Prerequisites</span></span>  
 <span data-ttu-id="8b4d6-113">Pour importer une base de connaissances à partir d'un fichier .dqs, vous devez avoir déjà exporté la base de connaissances dans le fichier .dqs.</span><span class="sxs-lookup"><span data-stu-id="8b4d6-113">To import a knowledge base from a .dqs file, you must have already exported the knowledge base into the .dqs file.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8b4d6-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="8b4d6-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8b4d6-115">Autorisations</span><span class="sxs-lookup"><span data-stu-id="8b4d6-115">Permissions</span></span>  
 <span data-ttu-id="8b4d6-116">Vous devez disposer du rôle dqs_kb_editor ou dqs_administrator sur la base de données DQS_MAIN pour importer une base de connaissances à partir d'un fichier de données .dqs.</span><span class="sxs-lookup"><span data-stu-id="8b4d6-116">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to import a knowledge base from a .dqs data file.</span></span>  
  
##  <a name="import-a-knowledge-base-from-a-dqs-file"></a><a name="Import"></a><span data-ttu-id="8b4d6-117">Importer une base de connaissances à partir d’un fichier. DQS</span><span class="sxs-lookup"><span data-stu-id="8b4d6-117">Import a knowledge base from a .dqs file</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="8b4d6-118">[Exécutez l’Application Data Quality client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="8b4d6-118">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="8b4d6-119">Dans l'écran d'accueil de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , cliquez sur **Nouvelle base de connaissances**.</span><span class="sxs-lookup"><span data-stu-id="8b4d6-119">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **New knowledge base**.</span></span>  
  
3.  <span data-ttu-id="8b4d6-120">Entrez un nom pour la base de connaissances.</span><span class="sxs-lookup"><span data-stu-id="8b4d6-120">Enter a name for the knowledge base.</span></span>  
  
4.  <span data-ttu-id="8b4d6-121">Cliquez sur la flèche bas pour **Créer la base de connaissances à partir de**, puis sélectionnez **Importer à partir d'un fichier DQS**.</span><span class="sxs-lookup"><span data-stu-id="8b4d6-121">Click the down arrow for **Create knowledge base from**, and then select **Import from DQS file**.</span></span>  
  
5.  <span data-ttu-id="8b4d6-122">Pour **Sélectionnez le fichier de données**, cliquez sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="8b4d6-122">For **Select data file**, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="8b4d6-123">Dans la boîte de dialogue **Importer à partir d'un fichier de données** , accédez au dossier qui contient le fichier .dqs à importer, puis cliquez sur le nom du fichier.</span><span class="sxs-lookup"><span data-stu-id="8b4d6-123">In the **Import from Data File** dialog box, move to the folder that contains the .dqs file that you want to import, and then click the name of the file.</span></span> <span data-ttu-id="8b4d6-124">Cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="8b4d6-124">Click **Open**.</span></span>  
  
7.  <span data-ttu-id="8b4d6-125">Vérifiez que la base de connaissances et les domaines corrects sont affichés dans la liste **Domaine** .</span><span class="sxs-lookup"><span data-stu-id="8b4d6-125">Verify that the correct knowledge base and domains are displayed in the **Domain** list.</span></span>  
  
8.  <span data-ttu-id="8b4d6-126">Sélectionnez l'activité que vous souhaitez effectuer, puis cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="8b4d6-126">Select the activity that you want to perform, and then click **Create**.</span></span>  
  
9. <span data-ttu-id="8b4d6-127">Dans la boîte de dialogue **Importer la base de connaissances** , vérifiez que la ligne d'état indique que l'importation est terminée.</span><span class="sxs-lookup"><span data-stu-id="8b4d6-127">In the **Import Knowledge Base** dialog box, verify that the status line indicates that the import completed.</span></span> <span data-ttu-id="8b4d6-128">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8b4d6-128">Click **OK**.</span></span>  
  
10. <span data-ttu-id="8b4d6-129">Effectuez les tâches de découverte des connaissances, de gestion des domaines ou de stratégie de correspondance que vous devez effectuer, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="8b4d6-129">Complete the knowledge discovery, domain management, or matching policy tasks that you need to perform, and then click **Finish**.</span></span>  
  
11. <span data-ttu-id="8b4d6-130">Cliquez sur **Publier** pour publier la connaissance dans la base de connaissances ou sur **Non** dans le cas contraire.</span><span class="sxs-lookup"><span data-stu-id="8b4d6-130">Click **Publish** to publish the knowledge in the knowledge base, or **No** not to.</span></span>  
  
12. <span data-ttu-id="8b4d6-131">Si vous avez publié la base de connaissances, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8b4d6-131">If you published the knowledge base, click **OK**.</span></span>  
  
13. <span data-ttu-id="8b4d6-132">Dans la page d'accueil de Data Quality Services, vérifiez que la base de connaissances est répertoriée sous **Base de connaissances récentes**.</span><span class="sxs-lookup"><span data-stu-id="8b4d6-132">In the Data Quality Services home page, verify that the knowledge base is listed under **Recent knowledge bases**.</span></span>  
  
##  <a name="follow-up-after-importing-a-knowledge-base-from-a-dqs-file"></a><a name="FollowUp"></a> <span data-ttu-id="8b4d6-133">Suivi : Après l'importation d'une base de connaissances à partir d'un fichier .dqs</span><span class="sxs-lookup"><span data-stu-id="8b4d6-133">Follow Up: After Importing a Knowledge Base from a .dqs File</span></span>  
 <span data-ttu-id="8b4d6-134">Après avoir importé une base de connaissances à partir d'un fichier .dqs, vous pouvez ajouter la connaissance à la base de connaissances ou utiliser la base de connaissances dans un projet de nettoyage ou de correspondance, selon le contenu de la base de connaissances.</span><span class="sxs-lookup"><span data-stu-id="8b4d6-134">After you import a knowledge base from a .dqs file, you can add knowledge to the knowledge base or use the knowledge base in a cleansing or matching project, depending on the contents of the knowledge base.</span></span> <span data-ttu-id="8b4d6-135">Pour plus d’informations, consultez [Effectuer une découverte des connaissances](../../2014/data-quality-services/perform-knowledge-discovery.md), [Gestion d’un domaine](../../2014/data-quality-services/managing-a-domain.md), [Gestion d’un domaine composite](../../2014/data-quality-services/managing-a-composite-domain.md), [Créer une stratégie de correspondance](../../2014/data-quality-services/create-a-matching-policy.md), [Nettoyage des données](../../2014/data-quality-services/data-cleansing.md) ou [Correspondance de données](../../2014/data-quality-services/data-matching.md).</span><span class="sxs-lookup"><span data-stu-id="8b4d6-135">For more information, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md), [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md), [Managing a Composite Domain](../../2014/data-quality-services/managing-a-composite-domain.md), [Create a Matching Policy](../../2014/data-quality-services/create-a-matching-policy.md), [Data Cleansing](../../2014/data-quality-services/data-cleansing.md), or [Data Matching](../../2014/data-quality-services/data-matching.md).</span></span>  
  
  
