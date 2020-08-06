---
title: Créer un projet de qualité des données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.dqproject.newdqproject.f1
helpviewer_keywords:
- create,data quality project
- data quality project,create
ms.assetid: 19c52d2b-d28e-4449-ab59-5fe0dc326cd9
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3bab14b34123464450bcf0de7540364fc642343e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696067"
---
# <a name="create-a-data-quality-project"></a><span data-ttu-id="76c8c-102">Créer un projet de qualité des données</span><span class="sxs-lookup"><span data-stu-id="76c8c-102">Create a Data Quality Project</span></span>
  <span data-ttu-id="76c8c-103">Cette rubrique explique comment créer un projet de qualité des données à l'aide de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76c8c-103">This topic describes how to create a data quality project by using [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span></span> <span data-ttu-id="76c8c-104">Un projet de qualité des données est utilisé pour exécuter l'activité de nettoyage ou de correspondance dans [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="76c8c-104">A data quality project is used to run the cleansing or matching activity in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="76c8c-105">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="76c8c-105">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="76c8c-106">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="76c8c-106">Prerequisites</span></span>  
 <span data-ttu-id="76c8c-107">Vous devez disposer d'une base de connaissances appropriée à utiliser dans le projet de qualité des données pour l'activité de nettoyage ou de correspondance.</span><span class="sxs-lookup"><span data-stu-id="76c8c-107">You must have a relevant knowledge base to use in the data quality project for the cleansing or matching activity.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="76c8c-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="76c8c-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="76c8c-109">Autorisations</span><span class="sxs-lookup"><span data-stu-id="76c8c-109">Permissions</span></span>  
 <span data-ttu-id="76c8c-110">Vous devez disposer du rôle dqs_kb_editor ou dqs_kb_operator sur la base de données DQS_MAIN pour créer un projet de qualité des données.</span><span class="sxs-lookup"><span data-stu-id="76c8c-110">You must have the dqs_kb_editor or dqs_kb_operator role on the DQS_MAIN database to create a data quality project.</span></span>  
  
##  <a name="create-a-data-quality-project"></a><a name="Create"></a><span data-ttu-id="76c8c-111">Créer un projet de qualité des données</span><span class="sxs-lookup"><span data-stu-id="76c8c-111">Create a Data Quality Project</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="76c8c-112">[Exécutez l’Application Data Quality client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="76c8c-112">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="76c8c-113">Dans l'écran d'accueil [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , cliquez sur **Nouveau projet de qualité des données**.</span><span class="sxs-lookup"><span data-stu-id="76c8c-113">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **New data quality project**.</span></span>  
  
3.  <span data-ttu-id="76c8c-114">Dans l'écran **Nouveau projet de qualité des données** :</span><span class="sxs-lookup"><span data-stu-id="76c8c-114">In the **New Data Quality Project** screen:</span></span>  
  
    1.  <span data-ttu-id="76c8c-115">Dans la zone **Nom** , entrez un nom pour le nouveau projet de qualité des données.</span><span class="sxs-lookup"><span data-stu-id="76c8c-115">In the **Name** box, type a name for the new data quality project.</span></span>  
  
    2.  <span data-ttu-id="76c8c-116">(Facultatif) Dans la zone de **Description** , tapez une description du nouveau projet de qualité des données.</span><span class="sxs-lookup"><span data-stu-id="76c8c-116">(Optional) In the **Description** box, type a description for the new data quality project.</span></span>  
  
    3.  <span data-ttu-id="76c8c-117">Dans la liste **Utiliser la Base de connaissances** , cliquez pour sélectionner une base de connaissances à utiliser pour le projet de qualité des données.</span><span class="sxs-lookup"><span data-stu-id="76c8c-117">In the **Use Knowledge base** list, click to select a knowledge base to be used for the data quality project.</span></span> <span data-ttu-id="76c8c-118">La zone **Détails de la base de connaissances : <nom_base_de_connaissances>** sur le côté droit affiche les noms de domaine disponibles dans la base de connaissances sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="76c8c-118">The **Knowledge base details: <Knowledge_Base_Name>** area on the right side displays the domain names available in the selected knowledge base.</span></span>  
  
    4.  <span data-ttu-id="76c8c-119">Dans la zone **Sélectionner une activité** , cliquez sur l'activité que vous souhaitez exécuter à l'aide de ce projet de qualité des données :</span><span class="sxs-lookup"><span data-stu-id="76c8c-119">In the **Select Activity** area, click on an activity that you want to perform using this data quality project:</span></span>  
  
        -   <span data-ttu-id="76c8c-120">**Nettoyage**: sélectionnez cette activité pour nettoyer les données sources.</span><span class="sxs-lookup"><span data-stu-id="76c8c-120">**Cleansing**: Select this activity to cleanse the source data.</span></span>  
  
        -   <span data-ttu-id="76c8c-121">**Correspondance**: sélectionnez cette activité pour effectuer la correspondance.</span><span class="sxs-lookup"><span data-stu-id="76c8c-121">**Matching**: Select this activity to perform matching.</span></span> <span data-ttu-id="76c8c-122">Cette activité est disponible uniquement si la base de connaissances sélectionnée pour le projet de qualité des données contient une stratégie correspondante.</span><span class="sxs-lookup"><span data-stu-id="76c8c-122">This activity is available only if the knowledge base selected for the data quality project contains a matching policy.</span></span>  
  
4.  <span data-ttu-id="76c8c-123">Cliquez sur **Créer** pour créer un projet de qualité des données.</span><span class="sxs-lookup"><span data-stu-id="76c8c-123">Click **Create** to create a data quality project.</span></span>  
  
##  <a name="follow-up-after-creating-a-data-quality-project"></a><a name="FollowUp"></a> <span data-ttu-id="76c8c-124">Suivi : Après la création d'un projet de qualité des données</span><span class="sxs-lookup"><span data-stu-id="76c8c-124">Follow Up: After Creating a Data Quality Project</span></span>  
 <span data-ttu-id="76c8c-125">Après avoir créé un projet de qualité des données, un Assistant vous est proposé pour effectuer l'activité sélectionnée : nettoyage ou correspondance.</span><span class="sxs-lookup"><span data-stu-id="76c8c-125">After you create a data quality project, you are presented with a wizard that you use to perform the selected activity: cleansing or matching.</span></span> <span data-ttu-id="76c8c-126">Pour plus d’informations sur les activités de nettoyage et de correspondance, consultez [Nettoyage des données](../../2014/data-quality-services/data-cleansing.md) et [Correspondance de données](../../2014/data-quality-services/data-matching.md).</span><span class="sxs-lookup"><span data-stu-id="76c8c-126">For more information about the cleansing and matching activities, see [Data Cleansing](../../2014/data-quality-services/data-cleansing.md) and [Data Matching](../../2014/data-quality-services/data-matching.md).</span></span>  
  
  
