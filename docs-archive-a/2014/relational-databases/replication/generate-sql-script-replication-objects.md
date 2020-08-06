---
title: Générer un script SQL (objets de réplication) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.generatesqlscript.f1
helpviewer_keywords:
- Generate SQL Script dialog box
ms.assetid: b7ccc34e-1c22-44b8-8eb5-f6423af3164e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 31a4b318eb3a4c0e5d9f79f43efdcf97c42957f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601337"
---
# <a name="generate-sql-script-replication-objects"></a><span data-ttu-id="70fd8-102">Générer un script SQL (objets de réplication)</span><span class="sxs-lookup"><span data-stu-id="70fd8-102">Generate SQL Script (Replication Objects)</span></span>
  <span data-ttu-id="70fd8-103">Un script de réplication contient les procédures stockées système [!INCLUDE[tsql](../../includes/tsql-md.md)] nécessaires à l'implémentation de composants de réplication en script, tels qu'une publication ou un abonnement.</span><span class="sxs-lookup"><span data-stu-id="70fd8-103">A replication script contains the [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures necessary to implement the replication components scripted, such as a publication or subscription.</span></span> <span data-ttu-id="70fd8-104">Tous les composants de réplication dans une topologie doivent faire l'objet d'un script et s'intégrer dans un plan de récupération des données en cas de sinistre ; les scripts peuvent également être utilisés pour automatiser des tâches répétitives.</span><span class="sxs-lookup"><span data-stu-id="70fd8-104">All replication components in a topology should be scripted as part of a disaster recovery plan, and scripts can also be used to automate repetitive tasks.</span></span> <span data-ttu-id="70fd8-105">La réplication propose deux boîtes de dialogue spécifiques à l'écriture de scripts mettant en œuvre des objets de réplication :</span><span class="sxs-lookup"><span data-stu-id="70fd8-105">Replication offers two dialog boxes for scripting replication objects:</span></span>  
  
-   <span data-ttu-id="70fd8-106">**Générer un script SQL**, disponible à partir du menu contextuel du dossier **Replication** ainsi que de tous les sous-dossiers de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70fd8-106">**Generate SQL Script**, which is available from the context menu of the **Replication** folder and all subfolders in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="70fd8-107">Cette boîte de dialogue vous permet de générer des scripts d’objets de réplication sur une instance de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70fd8-107">This dialog box allows you to script all replication objects on an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="70fd8-108">**Générer un script SQL \<ObjectName>** , disponible à partir du menu contextuel relatif aux publications et aux abonnements.</span><span class="sxs-lookup"><span data-stu-id="70fd8-108">**Generate SQL Script \<ObjectName>**, which is available from the context menu for publications and subscriptions.</span></span> <span data-ttu-id="70fd8-109">Cette boîte de dialogue vous permet de générer des scripts d'objets individuels.</span><span class="sxs-lookup"><span data-stu-id="70fd8-109">This dialog box allows you to script individual objects.</span></span>  
  
 <span data-ttu-id="70fd8-110">Ces boîtes de dialogue génèrent des scripts d'objets sur une instance unique de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Ils ne se connectent pas à d'autres instances pour permettre générer des scripts d'objets associés.</span><span class="sxs-lookup"><span data-stu-id="70fd8-110">These dialog boxes script objects on a single instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]; they do not connect to other instances to script related objects.</span></span>  
  
## <a name="generate-sql-script-options"></a><span data-ttu-id="70fd8-111">Options de la boîte de dialogue Générer un script SQL</span><span class="sxs-lookup"><span data-stu-id="70fd8-111">Generate SQL Script Options</span></span>  
 <span data-ttu-id="70fd8-112">**Propriétés du serveur de distribution**</span><span class="sxs-lookup"><span data-stu-id="70fd8-112">**Distributor properties**</span></span>  
 <span data-ttu-id="70fd8-113">Permet de générer des scripts de procédures stockées pour : activer ou désactiver le serveur de distribution, ajouter ou supprimer des serveurs de publication associés au serveur de distribution, et créer ou supprimer la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="70fd8-113">Select to script stored procedures to: enable or disable the Distributor; add or drop Publishers associated with the Distributor; and create or drop the distribution database.</span></span>  
  
 <span data-ttu-id="70fd8-114">**Publications dans les sources de données suivantes**</span><span class="sxs-lookup"><span data-stu-id="70fd8-114">**Publications in the following data sources**</span></span>  
 <span data-ttu-id="70fd8-115">Permet de générer des scripts de procédures stockées pour : activer ou désactiver la publication, et créer ou supprimer des publications, des articles, des abonnements par extraction et des travaux de réplication.</span><span class="sxs-lookup"><span data-stu-id="70fd8-115">Select to script stored procedures to: enable or disable publishing; and create or drop publications, articles, push subscriptions, and replication jobs.</span></span>  
  
 <span data-ttu-id="70fd8-116">**Abonnements dans les sources de données suivantes**</span><span class="sxs-lookup"><span data-stu-id="70fd8-116">**Subscriptions in the following data sources**</span></span>  
 <span data-ttu-id="70fd8-117">Permet de générer des scripts de procédures stockées afin de créer ou de supprimer des abonnements extraits et des travaux de réplication.</span><span class="sxs-lookup"><span data-stu-id="70fd8-117">Select to script stored procedures to create or drop pull subscriptions and replication jobs.</span></span>  
  
 <span data-ttu-id="70fd8-118">**Pour créer ou activer les composants** et **Pour supprimer ou désactiver les composants**</span><span class="sxs-lookup"><span data-stu-id="70fd8-118">**To create or enable the components** and **To drop or disable the components**</span></span>  
 <span data-ttu-id="70fd8-119">Permet d'indiquer si le script doit inclure des commandes de création ou de suppression d'un objet de réplication.</span><span class="sxs-lookup"><span data-stu-id="70fd8-119">Specify whether the script should include commands for creating or dropping a replication object.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="70fd8-120">recommande d'utiliser la boîte de dialogue pour créer un ensemble de scripts assurant l'activation et la désactivation de composants.</span><span class="sxs-lookup"><span data-stu-id="70fd8-120">recommends that you use the dialog box to create a set of scripts for enabling and disabling components.</span></span>  
  
 <span data-ttu-id="70fd8-121">**Travaux de réplication**</span><span class="sxs-lookup"><span data-stu-id="70fd8-121">**Replication jobs**</span></span>  
 <span data-ttu-id="70fd8-122">Permet de générer des scripts de travaux de réplication en complément des scripts d'appels de procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="70fd8-122">Select to script replication jobs in addition to stored procedure calls.</span></span> <span data-ttu-id="70fd8-123">Cette option n'est disponible que lors de la génération de scripts à partir d'un serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="70fd8-123">This option is available only when scripting from a Distributor.</span></span>  
  
 <span data-ttu-id="70fd8-124">Les procédures stockées de réplication créent les travaux nécessaires lors de leur exécution ; il n'est donc pas requis de choisir cette option.</span><span class="sxs-lookup"><span data-stu-id="70fd8-124">Replication stored procedures create the necessary jobs when they are executed, so it is not required to select this option.</span></span> <span data-ttu-id="70fd8-125">Il peut toutefois s'avérer utile d'obtenir un enregistrement des travaux créés dans le cas où un seul travail devait être recréé.</span><span class="sxs-lookup"><span data-stu-id="70fd8-125">However, it can be useful to have a record of the jobs created in case an individual job must be recreated.</span></span>  
  
## <a name="generate-sql-script-objectname-options"></a><span data-ttu-id="70fd8-126">Options de la boîte de dialogue Générer un script SQL \<ObjectName></span><span class="sxs-lookup"><span data-stu-id="70fd8-126">Generate SQL Script \<ObjectName> Options</span></span>  
 <span data-ttu-id="70fd8-127">**Pour créer ou activer les composants** et **Pour supprimer ou désactiver les composants**</span><span class="sxs-lookup"><span data-stu-id="70fd8-127">**To create or enable the components** and **To drop or disable the components**</span></span>  
 <span data-ttu-id="70fd8-128">Permet d'indiquer si le script doit inclure des commandes de création ou de suppression d'un objet de réplication.</span><span class="sxs-lookup"><span data-stu-id="70fd8-128">Specify whether the script should include commands for creating or dropping a replication object.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="70fd8-129">recommande d'utiliser la boîte de dialogue pour créer un ensemble de scripts d'activation et de désactivation de composants.</span><span class="sxs-lookup"><span data-stu-id="70fd8-129">recommends that you use the dialog box, creating a set of scripts for enabling and disabling components.</span></span>  
  
 <span data-ttu-id="70fd8-130">**Travaux de réplication**</span><span class="sxs-lookup"><span data-stu-id="70fd8-130">**Replication jobs**</span></span>  
 <span data-ttu-id="70fd8-131">Cette option n'est disponible qu'à partir de la boîte de dialogue **Générer un script SQL** .</span><span class="sxs-lookup"><span data-stu-id="70fd8-131">This option is available only from the **Generate SQL Script** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70fd8-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="70fd8-132">See Also</span></span>  
 [<span data-ttu-id="70fd8-133">Création de scripts de réplication</span><span class="sxs-lookup"><span data-stu-id="70fd8-133">Scripting Replication</span></span>](scripting-replication.md)  
  
  
