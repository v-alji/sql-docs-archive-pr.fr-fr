---
title: Rechercher des parties de rapports et définir un dossier par défaut (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5cf38068-65d1-4fe8-81f3-a404d8fbc663
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6605a23732799ec07b3dbe8481e88c91b18ebe5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601899"
---
# <a name="browse-for-report-parts-and-set-a-default-folder-report-builder-and-ssrs"></a><span data-ttu-id="bfdd9-102">Rechercher des parties de rapports et définir un dossier par défaut (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="bfdd9-102">Browse for Report Parts and Set a Default Folder (Report Builder and SSRS)</span></span>
  <span data-ttu-id="bfdd9-103">Pour créer un rapport, la façon la plus simple consiste à ajouter des parties de rapports existantes, telles que des tables et des graphiques, à votre rapport à partir de la bibliothèque de parties de rapports.</span><span class="sxs-lookup"><span data-stu-id="bfdd9-103">The easiest way to create a report is to add existing report parts, such as tables and charts, to your report from the Report Part Gallery.</span></span> <span data-ttu-id="bfdd9-104">Lorsque vous ajoutez une partie de rapport à votre rapport, vous ajoutez également tout ce qu'elle doit comporter pour fonctionner.</span><span class="sxs-lookup"><span data-stu-id="bfdd9-104">When you add a report part to your report, you are also adding everything it must have to work.</span></span> <span data-ttu-id="bfdd9-105">Par exemple, toute partie de rapport qui affiche des données dépend d'un dataset, autrement dit, une requête et une connexion à une source de données.</span><span class="sxs-lookup"><span data-stu-id="bfdd9-105">For example, any report part that displays data depends on a dataset, that is, a query and a connection to a data source.</span></span> <span data-ttu-id="bfdd9-106">Après avoir ajouté la partie de rapport à votre rapport, vous pouvez la modifier comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="bfdd9-106">After you add the report part to your report, you can modify it as much as you need.</span></span>  
  
 <span data-ttu-id="bfdd9-107">Vous pouvez définir un dossier par défaut pour publier des parties de rapports sur le serveur de rapports ou le site SharePoint intégré avec un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="bfdd9-107">You can set a default folder to publish report parts to the report server or SharePoint site integrated with a report server.</span></span>  
  
 <span data-ttu-id="bfdd9-108">Pour plus d’informations, consultez [Publication de parties de rapports &#40;Générateur de rapports et SSRS&#41;](../report-parts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bfdd9-108">For more information, see [Report Parts &#40;Report Builder and SSRS&#41;](../report-parts-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-browse-for-report-parts"></a><span data-ttu-id="bfdd9-109">Pour rechercher des parties de rapports</span><span class="sxs-lookup"><span data-stu-id="bfdd9-109">To browse for report parts</span></span>  
  
1.  <span data-ttu-id="bfdd9-110">Dans le menu **Insérer** , cliquez sur **Parties de rapports**.</span><span class="sxs-lookup"><span data-stu-id="bfdd9-110">On the **Insert** menu, click **Report Parts**.</span></span>  
  
     <span data-ttu-id="bfdd9-111">Si vous n’êtes pas déjà connecté, cliquez sur **Connectez-vous à un serveur de rapports**, puis entrez le nom.</span><span class="sxs-lookup"><span data-stu-id="bfdd9-111">If you are not already connected, click **Connect to a report server**, and enter the name.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bfdd9-112">Vous devez être connecté à un serveur de rapports pour rechercher des parties de rapports.</span><span class="sxs-lookup"><span data-stu-id="bfdd9-112">You must be connected to a report server to browse for report parts.</span></span>  
  
2.  <span data-ttu-id="bfdd9-113">Vous pouvez limiter votre recherche en spécifiant des détails sur la partie de rapport.</span><span class="sxs-lookup"><span data-stu-id="bfdd9-113">You can narrow your search by specifying details about the report part.</span></span> <span data-ttu-id="bfdd9-114">Tapez tout ou partie du nom et de la description dans la zone de **recherche** ou cliquez sur **Ajouter des critères** et ajoutez des valeurs pour un ou plusieurs de ces champs :</span><span class="sxs-lookup"><span data-stu-id="bfdd9-114">Type all or part of the name and description in the **Search** box, or click **Add Criteria** and add values for any or all of these fields:</span></span>  
  
    -   <span data-ttu-id="bfdd9-115">Créé par</span><span class="sxs-lookup"><span data-stu-id="bfdd9-115">Created by</span></span>  
  
    -   <span data-ttu-id="bfdd9-116">Date de création</span><span class="sxs-lookup"><span data-stu-id="bfdd9-116">Date created</span></span>  
  
    -   <span data-ttu-id="bfdd9-117">Date de dernière modification</span><span class="sxs-lookup"><span data-stu-id="bfdd9-117">Date last modified</span></span>  
  
    -   <span data-ttu-id="bfdd9-118">Auteur de la dernière modification</span><span class="sxs-lookup"><span data-stu-id="bfdd9-118">Last modified by</span></span>  
  
    -   <span data-ttu-id="bfdd9-119">Dossier du serveur</span><span class="sxs-lookup"><span data-stu-id="bfdd9-119">Server folder</span></span>  
  
    -   <span data-ttu-id="bfdd9-120">Type</span><span class="sxs-lookup"><span data-stu-id="bfdd9-120">Type</span></span>  
  
     <span data-ttu-id="bfdd9-121">Par exemple, pour rechercher une image, cliquez sur **Ajouter des critères**, puis sur **Type**.</span><span class="sxs-lookup"><span data-stu-id="bfdd9-121">For example, to find an image, click **Add Criteria**, and then click **Type**.</span></span> <span data-ttu-id="bfdd9-122">Dans la zone de liste déroulante, cochez la case **Image** , appuyez sur Entrée, puis cliquez sur la loupe Rechercher.</span><span class="sxs-lookup"><span data-stu-id="bfdd9-122">In the dropdown box, select the **Image** check box, press ENTER, and then click the Search magnifying glass.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bfdd9-123">Pour les valeurs **Créé par** et **Auteur de la dernière modification** , recherchez le nom d’utilisateur de la personne tel qu’il est représenté sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="bfdd9-123">For the **Created by** and **Last modified by** values, search for the person's user name as it is represented on the report server.</span></span>  
  
### <a name="to-set-a-default-folder-for-report-parts"></a><span data-ttu-id="bfdd9-124">Pour définir un dossier par défaut pour les parties de rapport</span><span class="sxs-lookup"><span data-stu-id="bfdd9-124">To set a default folder for report parts</span></span>  
  
1.  <span data-ttu-id="bfdd9-125">Cliquez sur **Générateur de rapports**, puis sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="bfdd9-125">Click **Report Builder**, and then click **Options**.</span></span>  
  
2.  <span data-ttu-id="bfdd9-126">Dans la boîte de dialogue **Options** , sous l’onglet **Paramètres** , tapez un nom de dossier dans la zone de texte **Publier les parties de rapports dans ce dossier par défaut** .</span><span class="sxs-lookup"><span data-stu-id="bfdd9-126">In the **Options** dialog box, on the **Settings** tab, type a folder name in the **Publish report parts to this folder by default** textbox.</span></span>  
  
 <span data-ttu-id="bfdd9-127">Le Générateur de rapports créera ce dossier si vous êtes autorisé à créer des dossiers sur le serveur de rapports et que le dossier n'existe pas encore.</span><span class="sxs-lookup"><span data-stu-id="bfdd9-127">Report Builder will create this folder if you have permissions to create folders on the report server and the folder does not exist yet.</span></span>  
  
 <span data-ttu-id="bfdd9-128">Vous n'avez pas à redémarrer le Générateur de rapports pour que ce paramètre entre en vigueur.</span><span class="sxs-lookup"><span data-stu-id="bfdd9-128">You do not need to restart Report Builder for this setting to take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfdd9-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bfdd9-129">See Also</span></span>  
 <span data-ttu-id="bfdd9-130">[Rechercher les mises à jour ou désactiver les mises à jour &#40;Générateur de rapports et SSRS&#41;](../check-for-updates-or-turn-updates-off-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bfdd9-130">[Check for Updates or Turn Updates Off &#40;Report Builder and SSRS&#41;](../check-for-updates-or-turn-updates-off-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bfdd9-131">[Parties de rapports &#40;Générateur de rapports et SSRS&#41;](../report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bfdd9-131">[Report Parts &#40;Report Builder and SSRS&#41;](../report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bfdd9-132">[Parties de rapports et datasets dans le Générateur de rapports](../report-data/report-parts-and-datasets-in-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="bfdd9-132">[Report Parts and Datasets in Report Builder](../report-data/report-parts-and-datasets-in-report-builder.md) </span></span>  
 <span data-ttu-id="bfdd9-133">[Résoudre les problèmes liés aux parties de rapports &#40;Générateur de rapports et SSRS&#41;](../troubleshoot-report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bfdd9-133">[Troubleshoot Report Parts &#40;Report Builder and SSRS&#41;](../troubleshoot-report-parts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="bfdd9-134">Publier et republier des parties de rapports &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bfdd9-134">Publish and Republish Report Parts &#40;Report Builder and SSRS&#41;</span></span>](publish-and-republish-report-parts-report-builder-and-ssrs.md)  
  
  
