---
title: Gérer (ouvrir, déverrouiller, renommer et supprimer) un projet de qualité des données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.dqproject.opendqproject.f1
helpviewer_keywords:
- data quality project,delete
- data quality project,rename
- data quality project,unlock
- data quality project,open
ms.assetid: de8a2b04-4673-4beb-b4cf-96a28cdf3a93
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 216c95937676954c509890b879abdee8f55b778c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613628"
---
# <a name="manage-open-unlock-rename-and-delete-a-data-quality-project"></a><span data-ttu-id="262cd-102">Gérer (ouvrir, déverrouiller, renommer et supprimer) un projet de qualité des données</span><span class="sxs-lookup"><span data-stu-id="262cd-102">Manage (Open, Unlock, Rename, and Delete) a Data Quality Project</span></span>
  <span data-ttu-id="262cd-103">Cette rubrique explique comment gérer un projet de qualité des données à l'aide de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , par exemple ouvrir, déverrouiller, renommer et supprimer un projet de qualité des données.</span><span class="sxs-lookup"><span data-stu-id="262cd-103">This topic describes how to manage a data quality project by using [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] such as open, unlock, rename, and delete a data quality project.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="262cd-104">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="262cd-104">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="262cd-105">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="262cd-105">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="262cd-106">Vous ne pouvez pas ouvrir un projet verrouillé créé par un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="262cd-106">You cannot open a locked project that is created by another user.</span></span>  
  
-   <span data-ttu-id="262cd-107">Vous ne pouvez pas déverrouiller, renommer ou supprimer un projet de qualité des données créé par un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="262cd-107">You cannot unlock, rename, or delete a data quality project that is created by another user.</span></span>  
  
-   <span data-ttu-id="262cd-108">Vous ne pouvez pas supprimer un projet de qualité des données verrouillé.</span><span class="sxs-lookup"><span data-stu-id="262cd-108">You cannot delete a locked data quality project.</span></span> <span data-ttu-id="262cd-109">Vous devez d'abord le déverrouiller.</span><span class="sxs-lookup"><span data-stu-id="262cd-109">You must first unlock it to delete.</span></span>  
  
-   <span data-ttu-id="262cd-110">Vous pouvez uniquement déverrouiller un projet de qualité des données que vous avez vous-même créé.</span><span class="sxs-lookup"><span data-stu-id="262cd-110">You can only unlock a data quality project that is created by you.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="262cd-111">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="262cd-111">Prerequisites</span></span>  
 <span data-ttu-id="262cd-112">Vous devez disposer d'au moins un projet de qualité des données à gérer.</span><span class="sxs-lookup"><span data-stu-id="262cd-112">You must have at least one data quality project to manage.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="262cd-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="262cd-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="262cd-114">Autorisations</span><span class="sxs-lookup"><span data-stu-id="262cd-114">Permissions</span></span>  
 <span data-ttu-id="262cd-115">Vous devez disposer du rôle dqs_kb_editor ou dqs_kb_operator sur la base de données DQS_MAIN pour gérer un projet de qualité des données.</span><span class="sxs-lookup"><span data-stu-id="262cd-115">You must have the dqs_kb_editor or dqs_kb_operator role on the DQS_MAIN database to manage a data quality project.</span></span>  
  
##  <a name="open-a-data-quality-project"></a><a name="Open"></a> <span data-ttu-id="262cd-116">Ouvrir un projet de qualité des données</span><span class="sxs-lookup"><span data-stu-id="262cd-116">Open a Data Quality Project</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="262cd-117">[Exécutez l’Application Data Quality client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="262cd-117">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="262cd-118">Dans l' [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] écran d’accueil, cliquez sur **ouvrir le projet de qualité des données**.</span><span class="sxs-lookup"><span data-stu-id="262cd-118">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open data quality project**.</span></span> <span data-ttu-id="262cd-119">L'écran **Ouvrir le projet** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="262cd-119">The **Open project** screen appears.</span></span>  
  
     <span data-ttu-id="262cd-120">Vous pouvez également ouvrir directement un projet de qualité des données répertorié sous la zone **Projet de qualité des données récent** en cliquant dessus.</span><span class="sxs-lookup"><span data-stu-id="262cd-120">Alternately, you can directly open a data quality project listed under **Recent data quality project** area by clicking it.</span></span>  
  
3.  <span data-ttu-id="262cd-121">Dans l'écran **Ouvrir le projet** , cliquez pour sélectionner le projet de qualité des données que vous voulez ouvrir, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="262cd-121">In the **Open project** screen, click to select the data quality project that you want to open, and click **Next**.</span></span>  
  
4.  <span data-ttu-id="262cd-122">Le projet de qualité des données s'ouvre dans le même état d'activité que celui dans lequel il se trouvait lorsqu'il a été fermé pour la dernière fois.</span><span class="sxs-lookup"><span data-stu-id="262cd-122">The data quality project opens at the same state of the activity where it was last closed.</span></span> <span data-ttu-id="262cd-123">Un projet de qualité des données peut prendre les états suivants :</span><span class="sxs-lookup"><span data-stu-id="262cd-123">A data quality project has the following states:</span></span>  
  
    -   <span data-ttu-id="262cd-124">Pour l’activité de **nettoyage** , un projet de qualité des données peut avoir les États suivants : **nettoyage-mappage**, **nettoyage-nettoyer**, **nettoyage-gérer et afficher les résultats**et **nettoyage-exportation**.</span><span class="sxs-lookup"><span data-stu-id="262cd-124">For the **Cleansing** activity, a data quality project can have the following states: **Cleansing - Map**, **Cleansing - Cleanse**, **Cleansing - Manage and View Results**, and **Cleansing - Export**.</span></span>  
  
    -   <span data-ttu-id="262cd-125">Pour l’activité de **correspondance** , un projet de qualité des données peut avoir les États suivants : correspondance **-** correspondance, correspondance **-** correspondance, correspondance **-survie**et **exportation correspondante**.</span><span class="sxs-lookup"><span data-stu-id="262cd-125">For the **Matching** activity, a data quality project can have the following states: **Matching - Map**, **Matching - Matching**, **Matching - Survivorship**, and **Matching - Export**.</span></span>  
  
##  <a name="unlock-a-data-quality-project"></a><a name="Unlock"></a> <span data-ttu-id="262cd-126">Déverrouiller un projet de qualité des données</span><span class="sxs-lookup"><span data-stu-id="262cd-126">Unlock a Data Quality Project</span></span>  
 <span data-ttu-id="262cd-127">Lorsque vous créez un projet de qualité des données, il se trouve dans un état verrouillé pour empêcher son utilisation ou sa modification par d'autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="262cd-127">When you create a data quality project, it is in a locked state to prevent usage or modification by other users.</span></span> <span data-ttu-id="262cd-128">Vous devez déverrouiller le projet de qualité des données une fois votre travail terminé si vous voulez que d'autres utilisateurs travaillent dessus.</span><span class="sxs-lookup"><span data-stu-id="262cd-128">You must unlock the data quality project after you have completed your work if you want other users to work on your data quality project.</span></span> <span data-ttu-id="262cd-129">Un symbole de verrou est affiché pour les projets verrouillés.</span><span class="sxs-lookup"><span data-stu-id="262cd-129">A lock symbol is displayed for projects that are locked.</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="262cd-130">[Exécutez l’Application Data Quality client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="262cd-130">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="262cd-131">Dans l' [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] écran d’accueil, cliquez sur **ouvrir le projet de qualité des données**.</span><span class="sxs-lookup"><span data-stu-id="262cd-131">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open data quality project**.</span></span> <span data-ttu-id="262cd-132">L'écran **Ouvrir le projet** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="262cd-132">The **Open project** screen appears.</span></span>  
  
3.  <span data-ttu-id="262cd-133">Dans l'écran **Ouvrir le projet** , cliquez avec le bouton droit sur un projet de qualité des données verrouillé que vous avez créé, puis cliquez sur **Déverrouiller** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="262cd-133">In the **Open project** screen, right-click a locked data quality project that is created by you, and then click **Unlock** in the shortcut menu.</span></span> <span data-ttu-id="262cd-134">Une coche verte s'affiche pour le projet, indiquant qu'il est déverrouillé.</span><span class="sxs-lookup"><span data-stu-id="262cd-134">A green check mark is displayed for the project indicating that it is unlocked.</span></span>  
  
##  <a name="rename-a-data-quality-project"></a><a name="Rename"></a> <span data-ttu-id="262cd-135">Renommer un projet de qualité des données</span><span class="sxs-lookup"><span data-stu-id="262cd-135">Rename a Data Quality Project</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="262cd-136">[Exécutez l’Application Data Quality client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="262cd-136">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="262cd-137">Dans l' [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] écran d’accueil, cliquez sur **ouvrir le projet de qualité des données**.</span><span class="sxs-lookup"><span data-stu-id="262cd-137">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open data quality project**.</span></span> <span data-ttu-id="262cd-138">L'écran **Ouvrir le projet** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="262cd-138">The **Open project** screen appears.</span></span>  
  
3.  <span data-ttu-id="262cd-139">Dans l'écran **Ouvrir le projet** , cliquez avec le bouton droit sur un projet de qualité des données verrouillé que vous avez créé, puis cliquez sur **Renommer** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="262cd-139">In the **Open project** screen, right-click a data quality project that is created by you, and then click **Rename** in the shortcut menu.</span></span>  
  
4.  <span data-ttu-id="262cd-140">Le nom du projet de qualité des données peut être modifié dans la colonne **Nom** .</span><span class="sxs-lookup"><span data-stu-id="262cd-140">The data quality project name becomes editable in the **Name** column.</span></span> <span data-ttu-id="262cd-141">Tapez un nouveau nom, puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="262cd-141">Type a new name, and then press Enter.</span></span>  
  
##  <a name="delete-a-data-quality-project"></a><a name="Delete"></a> <span data-ttu-id="262cd-142">Supprimer un projet de qualité des données</span><span class="sxs-lookup"><span data-stu-id="262cd-142">Delete a Data Quality Project</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="262cd-143">[Exécutez l’Application Data Quality client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="262cd-143">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="262cd-144">Dans l' [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] écran d’accueil, cliquez sur **ouvrir le projet de qualité des données**.</span><span class="sxs-lookup"><span data-stu-id="262cd-144">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open data quality project**.</span></span> <span data-ttu-id="262cd-145">L'écran **Ouvrir le projet** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="262cd-145">The **Open project** screen appears.</span></span>  
  
3.  <span data-ttu-id="262cd-146">Dans l'écran **Ouvrir le projet** , cliquez avec le bouton droit sur un projet de qualité des données déverrouillé que vous avez créé, puis cliquez sur **Supprimer** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="262cd-146">In the **Open project** screen, right-click an unlocked data quality project that is created by you, and then click **Delete** in the shortcut menu.</span></span>  
  
4.  <span data-ttu-id="262cd-147">Un message de confirmation s’affiche.</span><span class="sxs-lookup"><span data-stu-id="262cd-147">A confirmation message appears.</span></span> <span data-ttu-id="262cd-148">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="262cd-148">Click **Yes**.</span></span>  
  
  
