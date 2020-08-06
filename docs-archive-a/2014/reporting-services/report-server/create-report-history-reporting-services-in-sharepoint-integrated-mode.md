---
title: Créer un historique de rapport (Reporting Services en mode intégré SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report history [Reporting Services], SharePoint
ms.assetid: e57ec746-05ae-4ff6-8e39-6cde87310daa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 996202580bbacc24080460c2c43218db27294d76
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611535"
---
# <a name="create-report-history-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="929b5-102">Créer un historique de rapport (Reporting Services en mode intégré SharePoint)</span><span class="sxs-lookup"><span data-stu-id="929b5-102">Create Report History (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="929b5-103">L'historique de rapport est un ensemble d'instantanés de rapport que vous créez au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="929b5-103">Report history is a collection of report snapshots that you create over time.</span></span> <span data-ttu-id="929b5-104">Chaque instantané est une copie du rapport tel qu'il existait lors de sa création.</span><span class="sxs-lookup"><span data-stu-id="929b5-104">Each snapshot is a copy of the report as it existed when it was created.</span></span> <span data-ttu-id="929b5-105">Il inclut la mise en page et les données en vigueur dans le rapport lors de la création de l'instantané.</span><span class="sxs-lookup"><span data-stu-id="929b5-105">It includes the layout and data that was current for the report when the snapshot was created.</span></span> <span data-ttu-id="929b5-106">Les informations de rendu ne sont pas stockées avec l'instantané.</span><span class="sxs-lookup"><span data-stu-id="929b5-106">Rendering information is not stored with the snapshot.</span></span> <span data-ttu-id="929b5-107">Lorsque vous ouvrez un instantané dans l'historique de rapport, elle s'affiche au format HTML dans le composant WebPart Visionneuse de rapports.</span><span class="sxs-lookup"><span data-stu-id="929b5-107">When you open a snapshot in report history, it opens in HTML in the Report Viewer Web Part.</span></span> <span data-ttu-id="929b5-108">Une fois son rendu effectué, vous pouvez l'exporter vers d'autres formats d'application.</span><span class="sxs-lookup"><span data-stu-id="929b5-108">After it is rendered, you can export it to other application formats.</span></span>  
  
 <span data-ttu-id="929b5-109">Pour créer un historique de rapport, le rapport doit être capable de s'exécuter sans assistance (c'est-à-dire que le serveur de rapports doit être capable d'exécuter le rapport sans intervention de l'utilisateur).</span><span class="sxs-lookup"><span data-stu-id="929b5-109">To create report history, the report must be able to run unattended (that is, the report server must be able to run the report without user interaction).</span></span> <span data-ttu-id="929b5-110">Vous devez disposer de l'autorisation Modifier les éléments sur la bibliothèque qui contient le rapport.</span><span class="sxs-lookup"><span data-stu-id="929b5-110">You must have Edit Items permission on the library that contains the report.</span></span> <span data-ttu-id="929b5-111">Pour afficher ou supprimer l'historique de rapport, vous devez posséder l'autorisation Afficher les versions ou Supprimer les versions.</span><span class="sxs-lookup"><span data-stu-id="929b5-111">To view or delete report history, you must have View Versions or Delete Versions permissions.</span></span>  
  
### <a name="to-create-a-snapshot-or-report-history-on-demand"></a><span data-ttu-id="929b5-112">Pour créer un historique des instantanés et des rapports à la demande</span><span class="sxs-lookup"><span data-stu-id="929b5-112">To create a snapshot or report history on demand</span></span>  
  
1.  <span data-ttu-id="929b5-113">Pointez sur le rapport.</span><span class="sxs-lookup"><span data-stu-id="929b5-113">Point to the report.</span></span>  
  
2.  <span data-ttu-id="929b5-114">Cliquez pour afficher la flèche orientée vers le bas, puis sélectionnez **Afficher l’historique du rapport**.</span><span class="sxs-lookup"><span data-stu-id="929b5-114">Click to display the down arrow, and then select **View Report History**.</span></span>  
  
3.  <span data-ttu-id="929b5-115">Cliquez sur **Nouvel instantané**.</span><span class="sxs-lookup"><span data-stu-id="929b5-115">Click **New Snapshot**.</span></span> <span data-ttu-id="929b5-116">Si le bouton n'est pas visible, cela signifie que vous n'êtes pas autorisé à créer des instantanés dans l'historique de rapport.</span><span class="sxs-lookup"><span data-stu-id="929b5-116">If the button is not visible, it is because you do not have permission to create snapshots in report history.</span></span>  
  
4.  <span data-ttu-id="929b5-117">Pour afficher l'instantané que vous venez de créer, sélectionnez-le dans la liste.</span><span class="sxs-lookup"><span data-stu-id="929b5-117">To view the snapshot you just created, select it from the list.</span></span> <span data-ttu-id="929b5-118">Chaque instantané est identifié par un horodatage qui indique sa date et son heure de création.</span><span class="sxs-lookup"><span data-stu-id="929b5-118">Each snapshot is identified by a timestamp that shows when the snapshot was created.</span></span> <span data-ttu-id="929b5-119">Vous ne pouvez pas renommer l'instantané, le déplacer ni le modifier.</span><span class="sxs-lookup"><span data-stu-id="929b5-119">You cannot rename the snapshot, move it to another location, or modify it.</span></span>  
  
### <a name="to-schedule-report-history"></a><span data-ttu-id="929b5-120">Pour planifier un historique de rapport</span><span class="sxs-lookup"><span data-stu-id="929b5-120">To schedule report history</span></span>  
  
1.  <span data-ttu-id="929b5-121">Pointez sur le rapport.</span><span class="sxs-lookup"><span data-stu-id="929b5-121">Point to the report.</span></span>  
  
2.  <span data-ttu-id="929b5-122">Cliquez pour afficher la flèche orientée vers le bas, puis sélectionnez **Gérer les options de traitement**.</span><span class="sxs-lookup"><span data-stu-id="929b5-122">Click to display the down arrow, and then select **Manage Processing Options**.</span></span>  
  
3.  <span data-ttu-id="929b5-123">Dans **Options des instantanés d’historique**, cliquez sur **Créer des instantanés d’historique de rapport dans une planification**.</span><span class="sxs-lookup"><span data-stu-id="929b5-123">In **History Snapshot Options**, click **Create report history snapshots on a schedule**.</span></span>  
  
4.  <span data-ttu-id="929b5-124">Si vous disposez d’une planification partagée qui contient les informations de planification à utiliser, cliquez sur **Suivant une planification partagée** , puis sélectionnez la planification appropriée.</span><span class="sxs-lookup"><span data-stu-id="929b5-124">If you have a shared schedule that contains the schedule information you want to use, click **On a shared schedule** and select the schedule you want to use.</span></span> <span data-ttu-id="929b5-125">Sinon, cliquez sur **Suivant une planification personnalisée**, puis sur **Configurer** , afin de spécifier les options de création d’un historique de rapport selon une planification périodique.</span><span class="sxs-lookup"><span data-stu-id="929b5-125">Otherwise, click **On a custom schedule**, and then click **Configure** to specify options to create report history on a recurring schedule.</span></span>  
  
### <a name="to-create-report-history-when-data-is-refreshed-in-a-report"></a><span data-ttu-id="929b5-126">Pour créer un historique de rapport lorsque les données sont actualisées dans un rapport</span><span class="sxs-lookup"><span data-stu-id="929b5-126">To create report history when data is refreshed in a report</span></span>  
  
1.  <span data-ttu-id="929b5-127">Pointez sur le rapport.</span><span class="sxs-lookup"><span data-stu-id="929b5-127">Point to the report.</span></span>  
  
2.  <span data-ttu-id="929b5-128">Cliquez pour afficher la flèche orientée vers le bas, puis sélectionnez **Gérer les options de traitement**.</span><span class="sxs-lookup"><span data-stu-id="929b5-128">Click to display the down arrow, and then select **Manage Processing Options**.</span></span>  
  
3.  <span data-ttu-id="929b5-129">Dans **Options des instantanés d’historique**, cliquez sur **Stocker tous les instantanés de données de rapports dans l’historique de rapport**.</span><span class="sxs-lookup"><span data-stu-id="929b5-129">In **History Snapshot Options**, click **Store all report data snapshots in report history**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="929b5-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="929b5-130">See Also</span></span>  
 [<span data-ttu-id="929b5-131">Définir les options de traitement &#40;Reporting Services en mode intégré SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="929b5-131">Set Processing Options &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../set-processing-options-reporting-services-in-sharepoint-integrated-mode.md)  
  
  
