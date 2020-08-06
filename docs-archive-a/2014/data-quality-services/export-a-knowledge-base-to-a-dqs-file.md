---
title: Exporter une base de connaissances dans un fichier .dqs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: a324ead5-c8aa-4e26-abe3-ef415add00f8
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 81dfc8e7f20fae9dacd521595d101be3117a6794
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602299"
---
# <a name="export-a-knowledge-base-to-a-dqs-file"></a><span data-ttu-id="fe078-102">Exporter une base de connaissances dans un fichier .dqs</span><span class="sxs-lookup"><span data-stu-id="fe078-102">Export a Knowledge Base to a .dqs File</span></span>
  <span data-ttu-id="fe078-103">Cette rubrique décrit comment exporter une base de connaissances entière dans un fichier de données .dqs dans [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="fe078-103">This topic describes how to export an entire knowledge base to a .dqs data file in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="fe078-104">Vous pouvez exporter un domaine ou la totalité d'une base de connaissances vers un fichier de données.</span><span class="sxs-lookup"><span data-stu-id="fe078-104">You can export a domain or an entire knowledge base to a data file.</span></span> <span data-ttu-id="fe078-105">Pour plus d’informations sur l’exportation d’un domaine, consultez [Exporter un domaine vers un fichier .dqs](../../2014/data-quality-services/export-a-domain-to-a-dqs-file.md).</span><span class="sxs-lookup"><span data-stu-id="fe078-105">For information about exporting a domain, see [Export a Domain to a .dqs File](../../2014/data-quality-services/export-a-domain-to-a-dqs-file.md).</span></span>  
  
 <span data-ttu-id="fe078-106">L'exportation d'une base de connaissances vers un fichier .dqs, puis son importation en tant que base de connaissances distincte, simplifie le processus de génération de connaissances, et permet d'économiser aussi bien du temps que des efforts.</span><span class="sxs-lookup"><span data-stu-id="fe078-106">Exporting a knowledge base to a .dqs file, and then importing it as another knowledge base simplifies the knowledge generation process, saving time and effort.</span></span> <span data-ttu-id="fe078-107">Cela vous permet de partager une base de connaissances et ses contenus avec d'autres.</span><span class="sxs-lookup"><span data-stu-id="fe078-107">It enables you to share a knowledge base and its knowledge with others.</span></span> <span data-ttu-id="fe078-108">Le fichier .dqs contient toutes les informations de la base de connaissances, y compris les domaines et la stratégie de correspondance, à l'exception des informations de données de référence jointes.</span><span class="sxs-lookup"><span data-stu-id="fe078-108">The .dqs file will contain all knowledge base information, including domains and the matching policy, except for the attached reference data information.</span></span> <span data-ttu-id="fe078-109">Vous devez joindre à nouveau les domaines requis aux services de données de référence appropriés, le cas échéant, après avoir importé le fichier .dqs.</span><span class="sxs-lookup"><span data-stu-id="fe078-109">You must attach the required domains to appropriate reference data services again, if required, after importing the .dqs file.</span></span> <span data-ttu-id="fe078-110">Les données publiées et non publiées dans une base de connaissances sont exportées.</span><span class="sxs-lookup"><span data-stu-id="fe078-110">Both published and unpublished data in a knowledge base is exported.</span></span>  
  
 <span data-ttu-id="fe078-111">Le fichier de données .dqs créé par le processus d'exportation est chiffré, de sorte que le contenu ne peut pas être affiché.</span><span class="sxs-lookup"><span data-stu-id="fe078-111">The .dqs data file created by the export process is encrypted, so the contents cannot be viewed.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fe078-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="fe078-112">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="fe078-113">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="fe078-113">Prerequisites</span></span>  
 <span data-ttu-id="fe078-114">Pour exporter une base de connaissances dans un fichier de données .dqs, vous devez avoir créé et ouvert une base de connaissances.</span><span class="sxs-lookup"><span data-stu-id="fe078-114">To export a knowledge base to a .dqs data file, you must have created and opened a knowledge base.</span></span> <span data-ttu-id="fe078-115">Vous n'avez pas besoin de disposer d'un fichier .dqs vers lequel effectuer l'exportation ; il en sera créé un automatiquement.</span><span class="sxs-lookup"><span data-stu-id="fe078-115">You do not need to have a .dqs file to export into; one will be created for you.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fe078-116">Sécurité</span><span class="sxs-lookup"><span data-stu-id="fe078-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fe078-117">Autorisations</span><span class="sxs-lookup"><span data-stu-id="fe078-117">Permissions</span></span>  
 <span data-ttu-id="fe078-118">Vous devez disposer du rôle dqs_kb_editor ou dqs_administrator sur la base de données DQS_MAIN pour exporter une base de connaissances dans un fichier de données .dqs.</span><span class="sxs-lookup"><span data-stu-id="fe078-118">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to export a knowledge base to a .dqs data file.</span></span>  
  
##  <a name="export-a-knowledge-base-to-a-dqs-file"></a><a name="Export"></a><span data-ttu-id="fe078-119">Exporter une base de connaissances vers un fichier. DQS</span><span class="sxs-lookup"><span data-stu-id="fe078-119">Export a knowledge base to a .dqs file</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="fe078-120">[Exécutez l’Application Data Quality client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="fe078-120">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="fe078-121">Sur l'écran d'accueil de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , ouvrez une base de connaissances dans l'activité Gestion de l'arborescence du domaine.</span><span class="sxs-lookup"><span data-stu-id="fe078-121">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, open a knowledge base in the Domain Management activity.</span></span>  
  
3.  <span data-ttu-id="fe078-122">Dans la page Gestion de l'arborescence du domaine (tout onglet étant sélectionné), cliquez sur l'icône **Exporter des données de Base de connaissances** au-dessus de la liste des domaines, puis sur **Exporter la Base de connaissances**.</span><span class="sxs-lookup"><span data-stu-id="fe078-122">In the Domain Management page (with any tab selected), click the **Export Knowledge Base data** icon above the Domain list, and then click **Export Knowledge Base**.</span></span> <span data-ttu-id="fe078-123">Vous pouvez également cliquer avec le bouton droit dans la liste **Domaine** , pointer sur **Exporter**, puis cliquer sur **Exporter la Base de connaissances**.</span><span class="sxs-lookup"><span data-stu-id="fe078-123">Alternatively, you can also right-click in the **Domain** list, hover over **Export**, and then click **Export Knowledge Base**.</span></span>  
  
4.  <span data-ttu-id="fe078-124">Dans la boîte de dialogue **Exporter vers un fichier de données**, accédez au dossier dans lequel vous voulez enregistrer le fichier, nommez le fichier ou conservez le nom de la base de données, conservez **Fichiers de données DQS (\*.dqs**) comme **Type de fichier**, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="fe078-124">In the **Export to Data File** dialog box, move to the folder that you want to save the file in, name the file or keep the knowledge base name, keep **DQS Data Files (\*.dqs)** as the **Save as** type, and then click **Save**.</span></span>  
  
5.  <span data-ttu-id="fe078-125">Dans la boîte de dialogue **Exporter la Base de connaissances** , vérifiez que la ligne d'état indique que l'exportation est terminée.</span><span class="sxs-lookup"><span data-stu-id="fe078-125">In the **Export Knowledge Base** dialog box, verify that the status line indicates that the export completed.</span></span> <span data-ttu-id="fe078-126">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe078-126">Click **OK**.</span></span>  
  
##  <a name="follow-up-after-exporting-a-domain-to-a-dqs-file"></a><a name="FollowUp"></a><span data-ttu-id="fe078-127">Suivi : après l’exportation d’un domaine vers un fichier. DQS</span><span class="sxs-lookup"><span data-stu-id="fe078-127">Follow Up: After Exporting a Domain to a .dqs File</span></span>  
 <span data-ttu-id="fe078-128">Après avoir exporté une base de connaissances dans un fichier .dqs, vous pouvez importer la base de connaissances dans le même [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] (avec un nouveau nom) ou dans un [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)]différent.</span><span class="sxs-lookup"><span data-stu-id="fe078-128">After you export a knowledge base to a .dqs file, you can import the knowledge base into the same [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] (with a new name) or into a different [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
  
