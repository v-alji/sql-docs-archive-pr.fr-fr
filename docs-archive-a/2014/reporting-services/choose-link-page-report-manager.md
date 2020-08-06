---
title: Page choisir un lien (Gestionnaire de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a89a555d-efa3-45d6-951e-db78ec6a2c8e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bc40fe726555babee8d9940e198a93577bd6a09f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603315"
---
# <a name="choose-link-page-report-manager"></a><span data-ttu-id="fe6ca-102">Page Choisir un lien (Gestionnaire de rapports)</span><span class="sxs-lookup"><span data-stu-id="fe6ca-102">Choose Link Page (Report Manager)</span></span>
  <span data-ttu-id="fe6ca-103">La page Choisir un lien vous permet de choisir un autre rapport sur lequel baser le rapport lié qui est actuellement sélectionné.</span><span class="sxs-lookup"><span data-stu-id="fe6ca-103">Use the Choose Link page to choose a different report upon which to base the currently selected linked report.</span></span> <span data-ttu-id="fe6ca-104">Les rapports liés sont basés sur d'autres rapports qui sont déjà publiés sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="fe6ca-104">Linked reports are based on other reports already published to a report server.</span></span> <span data-ttu-id="fe6ca-105">Un rapport lié utilise la mise en page et les données du rapport de base, mais a des pages de propriétés séparées afin que vous puissiez personnaliser les propriétés de paramètres, les paramètres de sécurité, le nom, la description et l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="fe6ca-105">A linked report uses the layout and data of the base report, but has separate property pages so that you can customize parameter properties, security settings, name, description, and location.</span></span>  
  
 <span data-ttu-id="fe6ca-106">Vous pouvez utiliser la page Choisir un lien pour choisir un rapport publié différent à utiliser avec le rapport lié.</span><span class="sxs-lookup"><span data-stu-id="fe6ca-106">Through the Choose Link page, you can choose a different published report to use with the linked report.</span></span> <span data-ttu-id="fe6ca-107">Les autres paramètres du rapport lié (tels que les paramètres de sécurité et de paramètres) ne sont pas affectés par les modifications apportées aux informations sur le lien.</span><span class="sxs-lookup"><span data-stu-id="fe6ca-107">Other settings of the linked report (such as security and parameter settings) are unaffected by changes to the link information.</span></span> <span data-ttu-id="fe6ca-108">Dans la mesure où le serveur de rapports ne validera pas votre sélection, veillez à choisir un rapport qui a les mêmes paramètres que ceux que vous avez spécifiés sur le rapport lié.</span><span class="sxs-lookup"><span data-stu-id="fe6ca-108">The report server will not validate your selection, so be sure to choose a report that has the same parameters as those you specified on the linked report.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="fe6ca-109">Navigation</span><span class="sxs-lookup"><span data-stu-id="fe6ca-109">Navigation</span></span>  
 <span data-ttu-id="fe6ca-110">Utilisez la procédure suivante pour naviguer jusqu'à cet emplacement dans l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fe6ca-110">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-choose-link-page"></a><span data-ttu-id="fe6ca-111">Pour ouvrir la page Choisir un lien</span><span class="sxs-lookup"><span data-stu-id="fe6ca-111">To open the Choose Link page</span></span>  
  
1.  <span data-ttu-id="fe6ca-112">Ouvrez le Gestionnaire de rapports et recherchez le rapport lié que vous souhaitez changer.</span><span class="sxs-lookup"><span data-stu-id="fe6ca-112">Open Report Manager, and locate the linked report you want to change.</span></span>  
  
2.  <span data-ttu-id="fe6ca-113">Pointez sur le rapport lié et cliquez sur la flèche déroulante.</span><span class="sxs-lookup"><span data-stu-id="fe6ca-113">Hover over the linked report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="fe6ca-114">Dans le menu déroulant, cliquez sur **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="fe6ca-114">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="fe6ca-115">Ainsi, vous ouvrez la page des propriétés **Général** pour le rapport lié.</span><span class="sxs-lookup"><span data-stu-id="fe6ca-115">This opens the **General** properties page for the linked report.</span></span>  
  
4.  <span data-ttu-id="fe6ca-116">Dans l'onglet **Général** , dans la page de propriétés, cliquez sur **Changer le lien**.</span><span class="sxs-lookup"><span data-stu-id="fe6ca-116">On the **General** tab, on the properties page, click **Change Link**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fe6ca-117">Options</span><span class="sxs-lookup"><span data-stu-id="fe6ca-117">Options</span></span>  
 <span data-ttu-id="fe6ca-118">**Lieu**</span><span class="sxs-lookup"><span data-stu-id="fe6ca-118">**Location**</span></span>  
 <span data-ttu-id="fe6ca-119">Spécifiez le nom complet du rapport publié, notamment le chemin d'accès au dossier et le nom du rapport.</span><span class="sxs-lookup"><span data-stu-id="fe6ca-119">Specify the full name of the published report, including the folder path and report name.</span></span> <span data-ttu-id="fe6ca-120">Vous pouvez taper le nom complet du rapport ou utiliser l'arborescence pour naviguer jusqu'au rapport que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="fe6ca-120">You can type the full name of the report or use the tree view to navigate to the report you want to use.</span></span>  
  
 <span data-ttu-id="fe6ca-121">**Arborescence**</span><span class="sxs-lookup"><span data-stu-id="fe6ca-121">**Tree view**</span></span>  
 <span data-ttu-id="fe6ca-122">Affiche tous les dossiers de l'arborescence des dossiers du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="fe6ca-122">Shows all of the folders in the report server folder hierarchy.</span></span> <span data-ttu-id="fe6ca-123">Pour utiliser l'arborescence afin de remplir le champ **Emplacement** , cliquez sur le nom du rapport.</span><span class="sxs-lookup"><span data-stu-id="fe6ca-123">To use the tree view to fill in the **Location** field, click the name of the report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe6ca-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fe6ca-124">See Also</span></span>  
 <span data-ttu-id="fe6ca-125">[Page Propriétés générales, rapports &#40;Gestionnaire de rapports&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="fe6ca-125">[General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span></span>  
 <span data-ttu-id="fe6ca-126">[Page nouveau rapport lié &#40;Gestionnaire de rapports&#41;](../../2014/reporting-services/new-linked-report-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="fe6ca-126">[New Linked Report Page &#40;Report Manager&#41;](../../2014/reporting-services/new-linked-report-page-report-manager.md) </span></span>  
 [<span data-ttu-id="fe6ca-127">Aide F1 du Gestionnaire de rapports</span><span class="sxs-lookup"><span data-stu-id="fe6ca-127">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
