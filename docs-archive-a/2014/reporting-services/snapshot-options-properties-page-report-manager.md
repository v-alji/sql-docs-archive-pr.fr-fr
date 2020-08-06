---
title: Page de propriétés options d’instantanés (Gestionnaire de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f6641f59-5267-4f57-8957-63b93d1a9679
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3025b23dfe498a92c2ce1d8535229d8d23dfd429
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696372"
---
# <a name="snapshot-options-properties-page-report-manager"></a><span data-ttu-id="fa132-102">Page de propriétés Options d'instantanés (Gestionnaire de rapports)</span><span class="sxs-lookup"><span data-stu-id="fa132-102">Snapshot Options Properties Page (Report Manager)</span></span>
  <span data-ttu-id="fa132-103">La page de propriétés Options d'instantanés vous permet de planifier les instantanés de rapport qui doivent être ajoutés à l'historique de rapport et de définir la limite du nombre d'instantanés de rapport qui sont stockés dans l'historique.</span><span class="sxs-lookup"><span data-stu-id="fa132-103">Use the Snapshot Options properties page to schedule report snapshots to be added to report history, and to set limits on the number of report snapshots that are stored in report history.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fa132-104">Cette fonctionnalité n'est pas disponible dans toutes les éditions de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa132-104">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fa132-105">Pour obtenir la liste des fonctionnalités prises en charge par les éditions de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , consultez [services de base de données supplémentaires](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md#Add_DBServices).</span><span class="sxs-lookup"><span data-stu-id="fa132-105">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Additional Database Services](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md#Add_DBServices).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="fa132-106">Navigation</span><span class="sxs-lookup"><span data-stu-id="fa132-106">Navigation</span></span>  
 <span data-ttu-id="fa132-107">Utilisez la procédure suivante pour naviguer jusqu'à cet emplacement dans l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fa132-107">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-snapshot-options-properties-page-for-a-report"></a><span data-ttu-id="fa132-108">Pour ouvrir la page de propriétés Options d'instantanés pour un rapport</span><span class="sxs-lookup"><span data-stu-id="fa132-108">To open the Snapshot Options properties page for a report</span></span>  
  
1.  <span data-ttu-id="fa132-109">Ouvrez le Gestionnaire de rapports et recherchez le rapport pour lequel vous souhaitez configurer les propriétés d'instantanés de rapport.</span><span class="sxs-lookup"><span data-stu-id="fa132-109">Open Report Manager, and locate the report for which you want to configure report snapshot properties.</span></span>  
  
2.  <span data-ttu-id="fa132-110">Pointez sur le rapport et cliquez sur la flèche déroulante.</span><span class="sxs-lookup"><span data-stu-id="fa132-110">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="fa132-111">Dans le menu déroulant, cliquez sur **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="fa132-111">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="fa132-112">La page des propriétés générales pour le rapport s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="fa132-112">This opens the General properties page for the report.</span></span>  
  
4.  <span data-ttu-id="fa132-113">Sélectionnez l'onglet **Options d'instantanés** .</span><span class="sxs-lookup"><span data-stu-id="fa132-113">Select the **Snapshot Options** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fa132-114">Options</span><span class="sxs-lookup"><span data-stu-id="fa132-114">Options</span></span>  
 <span data-ttu-id="fa132-115">**Autoriser la création manuelle de l'historique de rapport**</span><span class="sxs-lookup"><span data-stu-id="fa132-115">**Allow report history to be created manually**</span></span>  
 <span data-ttu-id="fa132-116">Activez cette case à cocher pour ajouter des instantanés à l'historique de rapport en fonction des besoins.</span><span class="sxs-lookup"><span data-stu-id="fa132-116">Select this check box to add snapshots to report history as needed.</span></span> <span data-ttu-id="fa132-117">L'activation de cette case à cocher entraîne l'affichage du bouton **Nouvel instantané** dans la page Historique.</span><span class="sxs-lookup"><span data-stu-id="fa132-117">Selecting this check box causes the **New Snapshot** button to appear on the History page.</span></span>  
  
 <span data-ttu-id="fa132-118">**Stocker tous les instantanés d'exécution de rapport dans l'historique**</span><span class="sxs-lookup"><span data-stu-id="fa132-118">**Store all report execution snapshots in report history**</span></span>  
 <span data-ttu-id="fa132-119">Activez cette case à cocher pour copier un instantané de rapport que vous avez généré selon les propriétés d'exécution de rapport dans l'historique de rapport.</span><span class="sxs-lookup"><span data-stu-id="fa132-119">Select this check box to copy a report snapshot that you generate based on report execution properties to report history.</span></span> <span data-ttu-id="fa132-120">Vous pouvez définir les propriétés d'exécution de rapport pour exécuter un rapport à partir d'un instantané générée.</span><span class="sxs-lookup"><span data-stu-id="fa132-120">You can set report execution properties to run a report from a generated snapshot.</span></span> <span data-ttu-id="fa132-121">En définissant cette propriété d'historique de rapport, vous pouvez conserver un enregistrement de tous les instantanés des rapports générés au fil du temps en plaçant des copies de ces derniers dans un historique de rapport.</span><span class="sxs-lookup"><span data-stu-id="fa132-121">By setting this report history property, you can keep a record of all reports snapshots that are generated over time by placing copies of them in report history.</span></span>  
  
 <span data-ttu-id="fa132-122">**Utilisez la planification ci-dessous pour ajouter des instantanés à l'historique de rapport.**</span><span class="sxs-lookup"><span data-stu-id="fa132-122">**Use the following schedule to add snapshots to report history**</span></span>  
 <span data-ttu-id="fa132-123">Activez cette case à cocher pour ajouter des instantanés à l'historique de rapport suivant une planification.</span><span class="sxs-lookup"><span data-stu-id="fa132-123">Select this check box to add snapshots to report history on a scheduled basis.</span></span> <span data-ttu-id="fa132-124">Vous pouvez créer une planification qui est utilisée exclusivement à cet effet ou sélectionner une planification partagée prédéfinie si celle-ci contient les informations de planification désirées.</span><span class="sxs-lookup"><span data-stu-id="fa132-124">You can create a schedule that is used exclusively for this purpose, or you can select a predefined shared schedule if one contains the schedule information you want.</span></span>  
  
 <span data-ttu-id="fa132-125">**Sélectionner le nombre d'instantanés à conserver**</span><span class="sxs-lookup"><span data-stu-id="fa132-125">**Select the number of snapshots to keep**</span></span>  
 <span data-ttu-id="fa132-126">Sélectionnez une des options ci-dessous pour contrôler le nombre de rapports qui sont conservés dans l'historique de rapport.</span><span class="sxs-lookup"><span data-stu-id="fa132-126">Select from the following options to control the number of reports that are kept in report history.</span></span> <span data-ttu-id="fa132-127">Les paramètres d'historique de rapport varient pour chaque rapport.</span><span class="sxs-lookup"><span data-stu-id="fa132-127">Report history settings can vary for each report.</span></span>  
  
-   <span data-ttu-id="fa132-128">Sélectionnez **Utiliser le paramètre par défaut** pour conserver le paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="fa132-128">Select **Use default setting** to retain the default setting.</span></span> <span data-ttu-id="fa132-129">L'administrateur du serveur de rapports contrôle un paramètre principal pour le stockage de l'historique de rapport.</span><span class="sxs-lookup"><span data-stu-id="fa132-129">The report server administrator controls a master setting for report history storage.</span></span> <span data-ttu-id="fa132-130">Si vous choisissez cette option, le nombre d'instantanés conservés dépend de ce paramètre principal.</span><span class="sxs-lookup"><span data-stu-id="fa132-130">If you choose this option, the number of snapshots that are retained is obtained from this master setting.</span></span>  
  
-   <span data-ttu-id="fa132-131">Sélectionnez **Conserver un nombre illimité d'instantanés dans l'historique de rapport** pour conserver tous les instantanés d'historique de rapport.</span><span class="sxs-lookup"><span data-stu-id="fa132-131">Select **Keep an unlimited number of snapshots in report history** to retain all report history snapshots.</span></span> <span data-ttu-id="fa132-132">Vous devez supprimer manuellement des instantanés pour réduire la taille de l'historique de rapport.</span><span class="sxs-lookup"><span data-stu-id="fa132-132">You must manually delete snapshots to reduce the size of report history.</span></span>  
  
-   <span data-ttu-id="fa132-133">Sélectionnez **Limiter les copies de l'historique de rapport** pour conserver un nombre défini d'instantanés.</span><span class="sxs-lookup"><span data-stu-id="fa132-133">Select **Limit the copies of report history** to retain a set number of snapshots.</span></span> <span data-ttu-id="fa132-134">Lorsque la limite est atteinte, des copies anciennes sont supprimées de l'historique de rapport pour libérer de l'espace pour les nouvelles copies.</span><span class="sxs-lookup"><span data-stu-id="fa132-134">When the limit is reached, older copies are removed from report history to make room for newer copies.</span></span>  
  
 <span data-ttu-id="fa132-135">L'historique de rapport est stocké dans la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="fa132-135">Report history is stored in the report server database.</span></span> <span data-ttu-id="fa132-136">Si vous avez des rapports volumineux ou en nombre important pour lesquels vous souhaitez conserver un historique, envisagez de limiter le volume d'historique de rapport pour mieux gérer l'espace disque nécessaire de la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="fa132-136">If you have large reports or numerous reports for which you want to maintain history, consider limiting the amount of report history to help manage the disk space requirements of the report server database.</span></span>  
  
 <span data-ttu-id="fa132-137">**Appliquer**</span><span class="sxs-lookup"><span data-stu-id="fa132-137">**Apply**</span></span>  
 <span data-ttu-id="fa132-138">Cliquez pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="fa132-138">Click to save your changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa132-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fa132-139">See Also</span></span>  
 <span data-ttu-id="fa132-140">[Ajoutez un instantané à l’historique de rapport &#40;Gestionnaire de rapports&#41;](report-server/add-a-snapshot-to-report-history-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="fa132-140">[Add a Snapshot to Report History &#40;Report Manager&#41;](report-server/add-a-snapshot-to-report-history-report-manager.md) </span></span>  
 <span data-ttu-id="fa132-141">[Gestionnaire de rapports &#40;SSRS en mode natif&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="fa132-141">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="fa132-142">[Créer, modifier et supprimer des instantanés dans l'historique de rapport](report-server/create-modify-and-delete-snapshots-in-report-history.md) </span><span class="sxs-lookup"><span data-stu-id="fa132-142">[Create, Modify, and Delete Snapshots in Report History](report-server/create-modify-and-delete-snapshots-in-report-history.md) </span></span>  
 [<span data-ttu-id="fa132-143">Aide F1 du Gestionnaire de rapports</span><span class="sxs-lookup"><span data-stu-id="fa132-143">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
