---
title: Afficher ou modifier des planifications de jeu d’éléments de collecte (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dc.collectionsetprop.uploads.f1
- sql12.swb.dc.collectionsetprop.general.f1
- sql12.swb.dc.collectionsetprop.description.f1
helpviewer_keywords:
- collection sets [SQL Server], changing schedules
- schedules [SQL Server], changing collection set
- collection sets [SQL Server], viewing schedules
- schedules [SQL Server], viewing collection set
ms.assetid: 26336c98-78c5-414f-8d6a-574fc3af60c4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2eb1acf0346b3e16bd1d54829abbc070e1d9d63b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612964"
---
# <a name="view-or-change-collection-set-schedules-sql-server-management-studio"></a><span data-ttu-id="e6a78-102">Afficher ou modifier des planifications de jeu d'éléments de collecte (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="e6a78-102">View or Change Collection Set Schedules (SQL Server Management Studio)</span></span>
  <span data-ttu-id="e6a78-103">Vous pouvez afficher ou modifier des planifications de jeu d'éléments de collecte à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6a78-103">You can view or change collection set schedules by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="e6a78-104">Le mode de collecte, avec ou sans mise en cache, détermine la manière dont vous pouvez apporter des modifications à une planification.</span><span class="sxs-lookup"><span data-stu-id="e6a78-104">The collection mode, cached or non-cached, determines how you can make changes to a schedule.</span></span> <span data-ttu-id="e6a78-105">Le mode avec mise en cache utilise des planifications distinctes pour la collecte et le téléchargement.</span><span class="sxs-lookup"><span data-stu-id="e6a78-105">Cached mode uses separate schedules for collection and upload.</span></span> <span data-ttu-id="e6a78-106">Le mode sans mise en cache utilise la même planification pour la collecte et le téléchargement.</span><span class="sxs-lookup"><span data-stu-id="e6a78-106">Non-cached mode uses the same schedule for collection and upload.</span></span> <span data-ttu-id="e6a78-107">Le type de mode de collecte pour chacun des jeux d’éléments de collecte de données système est comme suit :</span><span class="sxs-lookup"><span data-stu-id="e6a78-107">The type of collection mode for each of the System Datacollection sets is as follows:</span></span>  
  
-   <span data-ttu-id="e6a78-108">**Utilisation du disque** utilise le mode de collecte sans mise en cache.</span><span class="sxs-lookup"><span data-stu-id="e6a78-108">**Disk Usage** uses non-cached collection mode.</span></span>  
  
-   <span data-ttu-id="e6a78-109">**Statistiques de requête** utilise le mode de collecte avec mise en cache.</span><span class="sxs-lookup"><span data-stu-id="e6a78-109">**Query Statistics** uses cached collection mode.</span></span>  
  
-   <span data-ttu-id="e6a78-110">**Activité du serveur** utilise le mode de collecte avec mise en cache.</span><span class="sxs-lookup"><span data-stu-id="e6a78-110">**Server Activity** uses cached collection mode.</span></span>  
  
### <a name="to-view-collection-set-schedules"></a><span data-ttu-id="e6a78-111">Pour afficher des planifications de jeu d'éléments de collecte</span><span class="sxs-lookup"><span data-stu-id="e6a78-111">To view collection set schedules</span></span>  
  
1.  <span data-ttu-id="e6a78-112">Dans l'Explorateur d'objets, développez le nœud **Gestion** et développez **Collecte de données**, puis **Jeux d'éléments de collecte de données système**.</span><span class="sxs-lookup"><span data-stu-id="e6a78-112">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="e6a78-113">Cliquez avec le bouton droit sur un nom de jeu d’éléments de collecte, puis sélectionnez **Propriétés** pour ouvrir la boîte de dialogue [Propriétés du jeu d’éléments de collecte de données](#CollectionSet) .</span><span class="sxs-lookup"><span data-stu-id="e6a78-113">Right-click a collection set name, and then click **Properties** to open the [Data Collection Set Properties](#CollectionSet) dialog box.</span></span>  
  
### <a name="to-change-the-schedules-for-a-cached-mode-collection-set"></a><span data-ttu-id="e6a78-114">Pour modifier les planifications d'un jeu d'éléments de collecte en mode avec mise en cache</span><span class="sxs-lookup"><span data-stu-id="e6a78-114">To change the schedules for a cached mode collection set</span></span>  
  
1.  <span data-ttu-id="e6a78-115">Dans l'Explorateur d'objets, développez le nœud **Gestion** et développez **Collecte de données**, puis **Jeux d'éléments de collecte de données système**.</span><span class="sxs-lookup"><span data-stu-id="e6a78-115">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="e6a78-116">Cliquez avec le bouton droit sur un jeu d’éléments de collecte qui utilise le mode avec mise en cache, tel que **Statistiques sur les requêtes**, puis sélectionnez **Propriétés** pour ouvrir la boîte de dialogue [Propriétés du jeu d’éléments de collecte de données](#CollectionSet) .</span><span class="sxs-lookup"><span data-stu-id="e6a78-116">Right-click a collection set that uses cached mode, such as **Query Statistics**, and then click **Properties** to open the [Data Collection Set Properties](#CollectionSet) dialog box.</span></span>  
  
3.  <span data-ttu-id="e6a78-117">Vous pouvez modifier la fréquence de collecte sur la page **Général** .</span><span class="sxs-lookup"><span data-stu-id="e6a78-117">You can change the collection frequency on the **General** page.</span></span> <span data-ttu-id="e6a78-118">Pour ce faire, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e6a78-118">To do this, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="e6a78-119">Dans le volet d’informations, double-cliquez sur le nombre qui s’affiche pour la colonne **Fréquence de collecte (s)** de la table **Éléments de collecte** .</span><span class="sxs-lookup"><span data-stu-id="e6a78-119">In the details pane, double-click the number that is displayed for the **Collection Frequency (sec)** column in the **Collection items** table.</span></span>  
  
    2.  <span data-ttu-id="e6a78-120">Pour augmenter ou diminuer la fréquence de collecte, tapez un nombre inférieur ou supérieur, puis appuyez sur Entrée pour stocker la nouvelle valeur.</span><span class="sxs-lookup"><span data-stu-id="e6a78-120">To increase or decrease the collection frequency, type a lower or higher number, and then press ENTER to store the new value.</span></span>  
  
4.  <span data-ttu-id="e6a78-121">Pour modifier la planification de téléchargement existante du jeu d'éléments de collecte, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e6a78-121">To change the existing upload schedule for the collection set, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="e6a78-122">Cliquez sur la page **Téléchargements** .</span><span class="sxs-lookup"><span data-stu-id="e6a78-122">Click the **Uploads** page.</span></span>  
  
    2.  <span data-ttu-id="e6a78-123">Dans le volet d'informations, cliquez sur **Choisir**.</span><span class="sxs-lookup"><span data-stu-id="e6a78-123">In the details pane, click **Pick**.</span></span>  
  
         <span data-ttu-id="e6a78-124">La boîte de dialogue **Choisir une planification pour le travail** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="e6a78-124">The **Pick Schedule for Job** dialog box opens.</span></span> <span data-ttu-id="e6a78-125">Les planifications disponibles apparaissent sous la forme d'une table.</span><span class="sxs-lookup"><span data-stu-id="e6a78-125">The available schedules appear as a table.</span></span>  
  
    3.  <span data-ttu-id="e6a78-126">Cliquez sur la ligne correspondant à la planification qui vous intéresse.</span><span class="sxs-lookup"><span data-stu-id="e6a78-126">Click the row with the schedule that you want.</span></span> <span data-ttu-id="e6a78-127">Par exemple, pour modifier la planification de façon à définir un intervalle de cinq minutes, cliquez sur la ligne où le nom de planification est **CollectorSchedule_Every_5min**.</span><span class="sxs-lookup"><span data-stu-id="e6a78-127">For example, to change the schedule to every 5 minutes, click the row where the schedule name is **CollectorSchedule_Every_5min.**</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="e6a78-128">Vous pouvez afficher et modifier les propriétés de la planification sélectionnée en cliquant sur **Propriétés** pour ouvrir la boîte de dialogue **Propriétés de la planification du travail** applicable à la planification.</span><span class="sxs-lookup"><span data-stu-id="e6a78-128">You can view and edit the properties for the selected schedule by clicking **Properties** to open the **Job Schedule Properties** dialog box for the schedule.</span></span> <span data-ttu-id="e6a78-129">Vous pouvez utiliser cette boîte de dialogue pour modifier des informations de planification telles que la fréquence.</span><span class="sxs-lookup"><span data-stu-id="e6a78-129">You can use this dialog box to change schedule information, such as the frequency.</span></span>  
        >   
        >  <span data-ttu-id="e6a78-130">En guise d'alternative à la modification d'une planification existante, vous pouvez créer une planification de téléchargement en cliquant sur **Nouveau** dans la page **Téléchargements** .</span><span class="sxs-lookup"><span data-stu-id="e6a78-130">As an alternative to modifying an existing schedule, you can create a new upload schedule by clicking **New** on the **Uploads** page.</span></span> <span data-ttu-id="e6a78-131">Cette action ouvre la boîte de dialogue **Nouvelle planification du travail** , que vous pouvez utiliser pour créer une planification personnalisée.</span><span class="sxs-lookup"><span data-stu-id="e6a78-131">This action opens the **New Job Schedule** dialog box, which you can use to create a custom schedule.</span></span>  
  
    4.  <span data-ttu-id="e6a78-132">Lorsque vous avez fini de configurer la planification, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6a78-132">When you are finished configuring the schedule, click **OK**.</span></span>  
  
         <span data-ttu-id="e6a78-133">Les modifications que vous avez apportées apparaissent sur la page **Téléchargements** .</span><span class="sxs-lookup"><span data-stu-id="e6a78-133">The changes that you made appear on the **Uploads** page.</span></span>  
  
5.  <span data-ttu-id="e6a78-134">Cliquez sur **OK** pour enregistrer les modifications de fréquence de collecte et de planification des téléchargements, ainsi que pour fermer la boîte de dialogue **Propriétés du jeu d'éléments de collecte de données** .</span><span class="sxs-lookup"><span data-stu-id="e6a78-134">Click **OK** to save the changes to the collection frequency and the upload schedule, and to close the **Data Collection Set Properties** dialog box.</span></span>  
  
### <a name="to-change-the-schedule-for-a-non-cached-mode-collection-set"></a><span data-ttu-id="e6a78-135">Pour modifier la planification pour un jeu d'éléments de collecte en mode sans mise en cache</span><span class="sxs-lookup"><span data-stu-id="e6a78-135">To change the schedule for a non-cached mode collection set</span></span>  
  
1.  <span data-ttu-id="e6a78-136">Dans l'Explorateur d'objets, développez le nœud **Gestion** et développez **Collecte de données**, puis **Jeux d'éléments de collecte de données système**.</span><span class="sxs-lookup"><span data-stu-id="e6a78-136">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="e6a78-137">Cliquez avec le bouton droit sur un jeu d’éléments de collecte qui utilise le mode sans mise en cache, tel que **Utilisation du disque**, puis sélectionnez **Propriétés** pour ouvrir la boîte de dialogue [Propriétés du jeu d’éléments de collecte de données](#CollectionSet) .</span><span class="sxs-lookup"><span data-stu-id="e6a78-137">Right-click a collection set that uses non-cached mode, such as **Disk Usage**, and then click **Properties** to open the [Data Collection Set Properties](#CollectionSet) dialog box.</span></span>  
  
     <span data-ttu-id="e6a78-138">La boîte de dialogue **Propriétés du jeu d'éléments de collecte de données** affiche une vue avec pages des propriétés du jeu d'éléments de collecte.</span><span class="sxs-lookup"><span data-stu-id="e6a78-138">The **Data Collection Set Properties** dialog box displays a paged view of the collection set properties.</span></span>  
  
3.  <span data-ttu-id="e6a78-139">Pour modifier la planification du jeu d'éléments de collecte, cliquez sur **Choisir**.</span><span class="sxs-lookup"><span data-stu-id="e6a78-139">To change the schedule for the collection set, click **Pick**.</span></span>  
  
     <span data-ttu-id="e6a78-140">La boîte de dialogue **Choisir une planification pour le travail** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="e6a78-140">The **Pick Schedule for Job** dialog box opens.</span></span> <span data-ttu-id="e6a78-141">Les planifications disponibles se présentent sous la forme d'une table.</span><span class="sxs-lookup"><span data-stu-id="e6a78-141">The available schedules are displayed as a table.</span></span>  
  
4.  <span data-ttu-id="e6a78-142">Cliquez sur la ligne correspondant à la planification qui vous intéresse.</span><span class="sxs-lookup"><span data-stu-id="e6a78-142">Click the row with the schedule that you want.</span></span> <span data-ttu-id="e6a78-143">Par exemple, pour modifier la planification de façon à définir un intervalle de cinq minutes, cliquez sur la ligne où le nom de planification est **CollectorSchedule_Every_5min**.</span><span class="sxs-lookup"><span data-stu-id="e6a78-143">For example, to change the schedule to every 5 minutes, click the row where the schedule name is **CollectorSchedule_Every_5min**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e6a78-144">Vous pouvez afficher et modifier les propriétés de la planification sélectionnée en cliquant sur **Propriétés** pour ouvrir la boîte de dialogue **Propriétés de la planification du travail** applicable à la planification.</span><span class="sxs-lookup"><span data-stu-id="e6a78-144">You can view and edit the properties for the selected schedule by clicking **Properties** to open the **Job Schedule Properties** dialog box for the schedule.</span></span> <span data-ttu-id="e6a78-145">Vous pouvez utiliser cette boîte de dialogue pour modifier des informations de planification telles que la fréquence.</span><span class="sxs-lookup"><span data-stu-id="e6a78-145">You can use this dialog box to change schedule information, such as the frequency.</span></span>  
    >   
    >  <span data-ttu-id="e6a78-146">En guise d'alternative à la modification d'une planification existante, vous pouvez créer une planification de collecte et de téléchargement en cliquant sur **Nouveau** dans la page **Général** .</span><span class="sxs-lookup"><span data-stu-id="e6a78-146">As an alternative to modifying an existing schedule, you can create a new collect and upload schedule by clicking **New** on the **General** page.</span></span> <span data-ttu-id="e6a78-147">Cette action ouvre la boîte de dialogue **Nouvelle planification du travail** .</span><span class="sxs-lookup"><span data-stu-id="e6a78-147">This action opens the **New Job Schedule** dialog box.</span></span>  
  
5.  <span data-ttu-id="e6a78-148">Lorsque vous avez fini de configurer la planification, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6a78-148">When you are finished configuring the schedule, click **OK**.</span></span>  
  
6.  <span data-ttu-id="e6a78-149">Cliquez sur **OK** pour enregistrer les modifications et fermer la boîte de dialogue **Propriétés du jeu d'éléments de collecte de données** .</span><span class="sxs-lookup"><span data-stu-id="e6a78-149">Click **OK** to save the changes and to close the **Data Collection Set Properties** dialog box.</span></span>  
  
####  <a name="data-collection-set-properties-dialog-box"></a><a name="CollectionSet"></a> <span data-ttu-id="e6a78-150">Boîte de dialogue Propriétés du jeu d'éléments de collecte de données</span><span class="sxs-lookup"><span data-stu-id="e6a78-150">Data Collection Set Properties Dialog Box</span></span>  
 <span data-ttu-id="e6a78-151">**Page Général**</span><span class="sxs-lookup"><span data-stu-id="e6a78-151">**General Page**</span></span>  
  
 <span data-ttu-id="e6a78-152">Utilisez cette page pour configurer le mode de collecte et de téléchargement des données, des planifications, ainsi que des périodes de rétention des données dans l'entrepôt de données de gestion.</span><span class="sxs-lookup"><span data-stu-id="e6a78-152">Use this page to configure how data is collected and uploaded, configure schedules, and configure data retention periods in the management data warehouse.</span></span> <span data-ttu-id="e6a78-153">Cette page fournit également des informations sur les jeux d'éléments de collecte, tels que les types de collecteurs et les fréquences de collecte, et les paramètres d'entrée utilisés pour un jeu d'éléments de collecte.</span><span class="sxs-lookup"><span data-stu-id="e6a78-153">This page also provides information about collection sets, such as collector types and collection frequencies, as well as the input parameters that are used for a collection set.</span></span>  
  
 <span data-ttu-id="e6a78-154">**Nom**</span><span class="sxs-lookup"><span data-stu-id="e6a78-154">**Name**</span></span>  
 <span data-ttu-id="e6a78-155">Affiche le nom du jeu d'éléments de collecte auquel cette page fait référence.</span><span class="sxs-lookup"><span data-stu-id="e6a78-155">Displays the name of the collection set that this page refers to.</span></span>  
  
 <span data-ttu-id="e6a78-156">**Collecte et téléchargement de données**</span><span class="sxs-lookup"><span data-stu-id="e6a78-156">**Data collection and upload**</span></span>  
 <span data-ttu-id="e6a78-157">Spécifie la façon dont les données sont collectées et téléchargées dans l'entrepôt de données de gestion.</span><span class="sxs-lookup"><span data-stu-id="e6a78-157">Specifies how data is collected and uploaded to the management data warehouse.</span></span> <span data-ttu-id="e6a78-158">Choisissez l'une des options suivantes.</span><span class="sxs-lookup"><span data-stu-id="e6a78-158">Pick one of the following options.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e6a78-159">**Aucune mise en cache. Collecte et chargement de données sur la même planification.**</span><span class="sxs-lookup"><span data-stu-id="e6a78-159">**Non-cached. Collection and data upload on the same schedule.**</span></span>|<span data-ttu-id="e6a78-160">Lorsque vous sélectionnez cette option, spécifiez l'un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="e6a78-160">When selected, specify one of the following:</span></span><br /><br /> <span data-ttu-id="e6a78-161">**À la demande**.</span><span class="sxs-lookup"><span data-stu-id="e6a78-161">**On-demand**.</span></span> <span data-ttu-id="e6a78-162">Les données sont collectées et téléchargées à la demande.</span><span class="sxs-lookup"><span data-stu-id="e6a78-162">Data is collected and uploaded on demand.</span></span><br /><br /> <span data-ttu-id="e6a78-163">**Planification**.</span><span class="sxs-lookup"><span data-stu-id="e6a78-163">**Schedule**.</span></span> <span data-ttu-id="e6a78-164">Les données sont collectées et téléchargées selon une planification.</span><span class="sxs-lookup"><span data-stu-id="e6a78-164">Data is collected and uploaded according to a schedule.</span></span> <span data-ttu-id="e6a78-165">Cliquez sur **Choisir** pour faire votre sélection dans une liste prédéfinie de planifications ou sur **Nouvelle** pour créer une planification.</span><span class="sxs-lookup"><span data-stu-id="e6a78-165">Click **Pick** to select from a predefined list of schedules, or click **New** to create a new schedule.</span></span>|  
|<span data-ttu-id="e6a78-166">**Mise en cache. Collecter les données et les mettre en cache selon des fréquences de collecte. Charger les données mises en cache sur une planification distincte.**</span><span class="sxs-lookup"><span data-stu-id="e6a78-166">**Cached. Collect and cache data at a set of collection frequencies. Upload cached data on a separate schedule.**</span></span>|<span data-ttu-id="e6a78-167">Les données sont collectées et mises en cache à une fréquence de collecte spécifiée.</span><span class="sxs-lookup"><span data-stu-id="e6a78-167">Collect and cache data for a specified collection frequency.</span></span> <span data-ttu-id="e6a78-168">Les données collectées sont téléchargées selon une planification séparée.</span><span class="sxs-lookup"><span data-stu-id="e6a78-168">Upload the collected data on a separate schedule.</span></span>|  
  
 <span data-ttu-id="e6a78-169">**Éléments de collecte**</span><span class="sxs-lookup"><span data-stu-id="e6a78-169">**Collection items**</span></span>  
 <span data-ttu-id="e6a78-170">Affiche les éléments de collecte dans le jeu d'éléments de collecte.</span><span class="sxs-lookup"><span data-stu-id="e6a78-170">Displays the collection items in the collection set.</span></span> <span data-ttu-id="e6a78-171">Les informations suivantes sont fournies pour chaque élément de collecte :</span><span class="sxs-lookup"><span data-stu-id="e6a78-171">The following information is provided for each collection item:</span></span>  
  
-   <span data-ttu-id="e6a78-172">**Nom**</span><span class="sxs-lookup"><span data-stu-id="e6a78-172">**Name**</span></span>  
  
-   <span data-ttu-id="e6a78-173">**Type de collecteur**</span><span class="sxs-lookup"><span data-stu-id="e6a78-173">**Collector Type**</span></span>  
  
-   <span data-ttu-id="e6a78-174">**Fréquence de collecte** (s).</span><span class="sxs-lookup"><span data-stu-id="e6a78-174">**Collection Frequency** (secs).</span></span> <span data-ttu-id="e6a78-175">Ce champ est modifiable si **Collecte et téléchargement de données** est configurée pour la mise en cache.</span><span class="sxs-lookup"><span data-stu-id="e6a78-175">This field is editable if **Data collection and upload** is configured as cached.</span></span> <span data-ttu-id="e6a78-176">Double-cliquez sur cette cellule pour définir la fréquence de collecte.</span><span class="sxs-lookup"><span data-stu-id="e6a78-176">Double-click this cell to set the collection frequency.</span></span>  
  
 <span data-ttu-id="e6a78-177">**Paramètres d'entrée**</span><span class="sxs-lookup"><span data-stu-id="e6a78-177">**Input parameters**</span></span>  
 <span data-ttu-id="e6a78-178">Affiche les paramètres d'entrée utilisés pour le jeu d'éléments de collecte.</span><span class="sxs-lookup"><span data-stu-id="e6a78-178">Displays the input parameters used for the collection set.</span></span>  
  
 <span data-ttu-id="e6a78-179">**Exécuter en tant que**</span><span class="sxs-lookup"><span data-stu-id="e6a78-179">**Run as**</span></span>  
 <span data-ttu-id="e6a78-180">Spécifie le compte utilisé pour exécuter le jeu d'éléments de collecte.</span><span class="sxs-lookup"><span data-stu-id="e6a78-180">Specifies the account used to run the collection set.</span></span> <span data-ttu-id="e6a78-181">Par défaut, il s'agit du compte de service Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e6a78-181">By default this is the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Service Account.</span></span> <span data-ttu-id="e6a78-182">Si des comptes proxy sont définis, cette liste inclut les noms des comptes proxy disponibles.</span><span class="sxs-lookup"><span data-stu-id="e6a78-182">If proxy accounts are defined, this list includes the names of the available proxy accounts.</span></span>  
  
 <span data-ttu-id="e6a78-183">**Spécifier la durée pendant laquelle les données doivent être conservées dans l'entrepôt de données de gestion.**</span><span class="sxs-lookup"><span data-stu-id="e6a78-183">**Set how long collected data will be retained in the management data warehouse.**</span></span>  
 <span data-ttu-id="e6a78-184">Spécifie la période de rétention des données collectées.</span><span class="sxs-lookup"><span data-stu-id="e6a78-184">Specifies how long collected data is retained.</span></span> <span data-ttu-id="e6a78-185">Choisissez l'une des options suivantes.</span><span class="sxs-lookup"><span data-stu-id="e6a78-185">Pick one of the following options.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e6a78-186">**Conserver les données pendant**</span><span class="sxs-lookup"><span data-stu-id="e6a78-186">**Retain data for**</span></span>|<span data-ttu-id="e6a78-187">Cette option est sélectionnée par défaut, et la période de rétention par défaut est de 14 jours.</span><span class="sxs-lookup"><span data-stu-id="e6a78-187">This option is selected by default, and the default retention period is 14 days.</span></span>|  
|<span data-ttu-id="e6a78-188">**Conserver les données indéfiniment**</span><span class="sxs-lookup"><span data-stu-id="e6a78-188">**Retain data indefinitely**</span></span>|<span data-ttu-id="e6a78-189">Il n'y a aucune limite sur la période de rétention des données.</span><span class="sxs-lookup"><span data-stu-id="e6a78-189">There is no time limit on the length of time that data is retained.</span></span>|  
  
 <span data-ttu-id="e6a78-190">**Page Téléchargements**</span><span class="sxs-lookup"><span data-stu-id="e6a78-190">**Uploads Page**</span></span>  
  
 <span data-ttu-id="e6a78-191">Utilisez cette page pour configurer la planification du téléchargement pour les données collectées par ce jeu d'éléments de collecte.</span><span class="sxs-lookup"><span data-stu-id="e6a78-191">Use this page to configure the upload schedule for data that is collected by this collection set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e6a78-192">Cet onglet est activé uniquement si l’option **Mises en cache** est configurée pour **Collecte et téléchargement de données**.</span><span class="sxs-lookup"><span data-stu-id="e6a78-192">This tab is only enabled if the **Cached** option is configured for **Data collection and upload**.</span></span>  
  
 <span data-ttu-id="e6a78-193">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="e6a78-193">**Server**</span></span>  
 <span data-ttu-id="e6a78-194">Affiche le nom du serveur qui héberge l'entrepôt de données de gestion.</span><span class="sxs-lookup"><span data-stu-id="e6a78-194">Displays the name of the server that hosts the management data warehouse.</span></span> <span data-ttu-id="e6a78-195">Pour plus d’informations, consultez [Configurer l’entrepôt de données de gestion &#40;SQL Server Management Studio&#41;](configure-the-management-data-warehouse-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="e6a78-195">For more information, see [Configure the Management Data Warehouse &#40;SQL Server Management Studio&#41;](configure-the-management-data-warehouse-sql-server-management-studio.md).</span></span>  
  
 <span data-ttu-id="e6a78-196">**Entrepôt de données de gestion**</span><span class="sxs-lookup"><span data-stu-id="e6a78-196">**Management data warehouse**</span></span>  
 <span data-ttu-id="e6a78-197">Affiche le nom de l'entrepôt de données de gestion.</span><span class="sxs-lookup"><span data-stu-id="e6a78-197">Displays the name of the management data warehouse.</span></span> <span data-ttu-id="e6a78-198">Pour plus d’informations, consultez [Configurer l’entrepôt de données de gestion &#40;SQL Server Management Studio&#41;](configure-the-management-data-warehouse-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="e6a78-198">For more information, see [Configure the Management Data Warehouse &#40;SQL Server Management Studio&#41;](configure-the-management-data-warehouse-sql-server-management-studio.md).</span></span>  
  
 <span data-ttu-id="e6a78-199">**Dernier téléchargement**</span><span class="sxs-lookup"><span data-stu-id="e6a78-199">**Last upload**</span></span>  
 <span data-ttu-id="e6a78-200">Affiche des informations sur la date et l'heure du dernier téléchargement effectué pour le jeu d'éléments de collecte.</span><span class="sxs-lookup"><span data-stu-id="e6a78-200">Displays date and time information for the last upload done for the collection set.</span></span>  
  
 <span data-ttu-id="e6a78-201">**Planification de téléchargement**</span><span class="sxs-lookup"><span data-stu-id="e6a78-201">**Upload schedule**</span></span>  
 <span data-ttu-id="e6a78-202">Spécifie la planification du téléchargement pour le jeu d'éléments de collecte.</span><span class="sxs-lookup"><span data-stu-id="e6a78-202">Specifies the upload schedule for the collection set.</span></span> <span data-ttu-id="e6a78-203">Si cette option est activée, cliquez sur **Choisir** pour faire votre sélection dans une liste prédéfinie de planifications ou sur **Nouvelle** pour créer une planification.</span><span class="sxs-lookup"><span data-stu-id="e6a78-203">If enabled, Click **Pick** to select from a predefined list of schedules, or click **New** to create a new schedule.</span></span>  
  
 <span data-ttu-id="e6a78-204">**Page Description**</span><span class="sxs-lookup"><span data-stu-id="e6a78-204">**Description Page**</span></span>  
  
 <span data-ttu-id="e6a78-205">Utilisez cette page pour consulter une description du jeu d'éléments de collecte auquel cette page de propriétés fait référence.</span><span class="sxs-lookup"><span data-stu-id="e6a78-205">Use this page to view a description of the collection set that this properties page refers to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6a78-206">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e6a78-206">See Also</span></span>  
 <span data-ttu-id="e6a78-207">[Gérer la collecte de données](manage-data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="e6a78-207">[Manage Data Collection](manage-data-collection.md) </span></span>  
 [<span data-ttu-id="e6a78-208">Collecte de données</span><span class="sxs-lookup"><span data-stu-id="e6a78-208">Data Collection</span></span>](data-collection.md)  
  
  
