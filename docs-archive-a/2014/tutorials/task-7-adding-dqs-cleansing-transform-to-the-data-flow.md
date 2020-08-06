---
title: 'Tâche 7 : ajout d’une transformation de nettoyage DQS au Data Flow | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 0b749c71-dfb6-493a-804f-600290d46eef
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 887bc361a51b61e9137404e054bd52e2b630ca5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601827"
---
# <a name="task-7-adding-dqs-cleansing-transform-to-the-data-flow"></a><span data-ttu-id="3b7d0-102">Tâche 7 : Ajout d’une transformation de nettoyage DQS au flux de données</span><span class="sxs-lookup"><span data-stu-id="3b7d0-102">Task 7: Adding DQS Cleansing Transform to the Data Flow</span></span>
  <span data-ttu-id="3b7d0-103">Dans cette tâche, vous allez ajouter la transformation de nettoyage DQS au flux de données pour nettoyer les données des fournisseurs d'entrée à l'aide de DQS.</span><span class="sxs-lookup"><span data-stu-id="3b7d0-103">In this task, you add DQS Cleansing Transform to the data flow to cleanse the input supplier data by using DQS.</span></span> <span data-ttu-id="3b7d0-104">Pour plus d’informations sur la transformation, consultez **[transformation de nettoyage DQS](https://msdn.microsoft.com/library/ee677619.aspx)** .</span><span class="sxs-lookup"><span data-stu-id="3b7d0-104">See **[DQS Cleansing Transform](https://msdn.microsoft.com/library/ee677619.aspx)** for more details about the transform.</span></span>  
  
1.  <span data-ttu-id="3b7d0-105">Cliquez avec le bouton droit sur **nettoyage DQS** sous l’onglet **Flow Data** , puis cliquez sur **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="3b7d0-105">Right-click **DQS Cleansing** in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="3b7d0-106">Tapez **nettoyer les données des fournisseurs**, puis appuyez sur **entrée**.</span><span class="sxs-lookup"><span data-stu-id="3b7d0-106">Type **Cleanse Supplier Data**, and press **ENTER**.</span></span>  
  
2.  <span data-ttu-id="3b7d0-107">Sélectionnez **lire les données des fournisseurs à partir d’un fichier Excel**. Faites glisser le connecteur bleu pour **nettoyer les données des fournisseurs**.</span><span class="sxs-lookup"><span data-stu-id="3b7d0-107">Select **Read Supplier Data from Excel File**; drag the blue connector to **Cleanse Supplier Data**.</span></span> <span data-ttu-id="3b7d0-108">Les composants sont maintenant connectés.</span><span class="sxs-lookup"><span data-stu-id="3b7d0-108">The components are now connected.</span></span>  
  
     <span data-ttu-id="3b7d0-109">![Lire les données du fournisseur-> nettoyer les données des fournisseurs](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-01.jpg "Lire les données des fournisseurs -> Nettoyer les données des fournisseurs")</span><span class="sxs-lookup"><span data-stu-id="3b7d0-109">![Read Supplier Data -> Cleanse Supplier Data](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-01.jpg "Read Supplier Data -> Cleanse Supplier Data")</span></span>  
  
3.  <span data-ttu-id="3b7d0-110">Double-cliquez sur **nettoyer les données des fournisseurs**.</span><span class="sxs-lookup"><span data-stu-id="3b7d0-110">Double-click **Cleanse Supplier Data**.</span></span>  
  
4.  <span data-ttu-id="3b7d0-111">Dans l **'éditeur de transformation de nettoyage DQS**, cliquez sur **nouveau** en regard de la **liste déroulante gestionnaire de connexions de qualité des données**.</span><span class="sxs-lookup"><span data-stu-id="3b7d0-111">In the **DQS Cleansing Transformation Editor**, click **New** next to the **Data Quality Connection Manager drop-down list**.</span></span>  
  
5.  <span data-ttu-id="3b7d0-112">Dans la boîte de dialogue **Gestionnaire de connexions de nettoyage DQS** , tapez **(local)** ou **point** (.) pour vous connecter au serveur local.</span><span class="sxs-lookup"><span data-stu-id="3b7d0-112">In the **DQS Cleansing Connection Manager** dialog box, type **(local)** or **period** (.) to connect to the local server.</span></span> <span data-ttu-id="3b7d0-113">Cette leçon suppose que vous avez installé DQS sur un serveur local.</span><span class="sxs-lookup"><span data-stu-id="3b7d0-113">This lesson assumes that you have DQS installed on a local server.</span></span>  
  
6.  <span data-ttu-id="3b7d0-114">Cliquez sur **tester la connexion** pour tester la connexion au serveur DQS.</span><span class="sxs-lookup"><span data-stu-id="3b7d0-114">Click **Test Connection** to test the connection to DQS server.</span></span>  
  
7.  <span data-ttu-id="3b7d0-115">Cliquez sur **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="3b7d0-115">Click **OK** to close the dialog box.</span></span>  
  
8.  <span data-ttu-id="3b7d0-116">Sélectionnez **fournisseurs** pour la **base de connaissances de qualité des données**.</span><span class="sxs-lookup"><span data-stu-id="3b7d0-116">Select **Suppliers** for the **Data Quality Knowledge Base**.</span></span>  
  
     <span data-ttu-id="3b7d0-117">![Éditeur de transformation de nettoyage DQS - Base de connaissances des fournisseurs](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-02.jpg "Éditeur de transformation de nettoyage DQS - Base de connaissances des fournisseurs")</span><span class="sxs-lookup"><span data-stu-id="3b7d0-117">![DQS Cleansing Transformation Editor - Suppliers KB](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-02.jpg "DQS Cleansing Transformation Editor - Suppliers KB")</span></span>  
  
9. <span data-ttu-id="3b7d0-118">Basculez vers l’onglet **mappage** en haut.</span><span class="sxs-lookup"><span data-stu-id="3b7d0-118">Switch to the **Mapping** tab at the top.</span></span>  
  
10. <span data-ttu-id="3b7d0-119">Dans **colonnes d’entrée disponibles**, **Sélectionnez nom du fournisseur**, **ContactEmailAddress**, **adresse**, **ville**, **État**, **pays**et **Code postal** en activant les cases à cocher.</span><span class="sxs-lookup"><span data-stu-id="3b7d0-119">From **Available Input Columns**, select **Supplier Name**, **ContactEmailAddress**, **Address Line**, **City**, **State**, **Country**, and **Zip Code** by selecting the check boxes.</span></span>  
  
     <span data-ttu-id="3b7d0-120">![Éditeur de transformation de nettoyage DQS - Mappages](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-03.jpg "Éditeur de transformation de nettoyage DQS - Mappages")</span><span class="sxs-lookup"><span data-stu-id="3b7d0-120">![DQS Cleansing Transformation Editor - Mappings](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-03.jpg "DQS Cleansing Transformation Editor - Mappings")</span></span>  
  
11. <span data-ttu-id="3b7d0-121">Dans le volet inférieur, mappez ces colonnes à l’aide des listes déroulantes de la colonne **domaine** :</span><span class="sxs-lookup"><span data-stu-id="3b7d0-121">In the bottom pane, map these columns by using drop-down lists in the **Domain** column:</span></span>  
  
    |<span data-ttu-id="3b7d0-122">Colonne</span><span class="sxs-lookup"><span data-stu-id="3b7d0-122">Column</span></span>|<span data-ttu-id="3b7d0-123">Domaine</span><span class="sxs-lookup"><span data-stu-id="3b7d0-123">Domain</span></span>|  
    |------------|------------|  
    |<span data-ttu-id="3b7d0-124">Nom du fournisseur</span><span class="sxs-lookup"><span data-stu-id="3b7d0-124">Supplier Name</span></span>|<span data-ttu-id="3b7d0-125">Nom du fournisseur</span><span class="sxs-lookup"><span data-stu-id="3b7d0-125">Supplier Name</span></span>|  
    |<span data-ttu-id="3b7d0-126">ContactEmailAddress</span><span class="sxs-lookup"><span data-stu-id="3b7d0-126">ContactEmailAddress</span></span>|<span data-ttu-id="3b7d0-127">E-mail du contact</span><span class="sxs-lookup"><span data-stu-id="3b7d0-127">Contact Email</span></span>|  
    |<span data-ttu-id="3b7d0-128">Adresse</span><span class="sxs-lookup"><span data-stu-id="3b7d0-128">Address Line</span></span>|<span data-ttu-id="3b7d0-129">Adresse</span><span class="sxs-lookup"><span data-stu-id="3b7d0-129">Address Line</span></span>|  
    |<span data-ttu-id="3b7d0-130">City</span><span class="sxs-lookup"><span data-stu-id="3b7d0-130">City</span></span>|<span data-ttu-id="3b7d0-131">City</span><span class="sxs-lookup"><span data-stu-id="3b7d0-131">City</span></span>|  
    |<span data-ttu-id="3b7d0-132">State</span><span class="sxs-lookup"><span data-stu-id="3b7d0-132">State</span></span>|<span data-ttu-id="3b7d0-133">State</span><span class="sxs-lookup"><span data-stu-id="3b7d0-133">State</span></span>|  
    |<span data-ttu-id="3b7d0-134">Pays ou région</span><span class="sxs-lookup"><span data-stu-id="3b7d0-134">Country</span></span>|<span data-ttu-id="3b7d0-135">Pays ou région</span><span class="sxs-lookup"><span data-stu-id="3b7d0-135">Country</span></span>|  
    |<span data-ttu-id="3b7d0-136">Code postal</span><span class="sxs-lookup"><span data-stu-id="3b7d0-136">Zip Code</span></span>|<span data-ttu-id="3b7d0-137">Zip</span><span class="sxs-lookup"><span data-stu-id="3b7d0-137">Zip</span></span>|  
  
12. <span data-ttu-id="3b7d0-138">Cliquez sur **OK** pour fermer la boîte de dialogue **éditeur de transformation de nettoyage DQS** .</span><span class="sxs-lookup"><span data-stu-id="3b7d0-138">Click **OK** to close the **DQS Cleansing Transformation Editor** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="3b7d0-139">étape suivante</span><span class="sxs-lookup"><span data-stu-id="3b7d0-139">Next Step</span></span>  
 [<span data-ttu-id="3b7d0-140">Tâche 8 : Ajout de la transformation de fractionnement conditionnel pour fractionner la sortie du nettoyage</span><span class="sxs-lookup"><span data-stu-id="3b7d0-140">Task 8: Adding Conditional Split Transform to Split Cleansing Output</span></span>](../../2014/tutorials/task-8-adding-conditional-split-transform-to-split-cleansing-output.md)  
  
  
