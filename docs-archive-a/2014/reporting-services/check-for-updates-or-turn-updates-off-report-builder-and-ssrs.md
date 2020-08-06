---
title: Rechercher les mises à jour ou désactiver les mises à jour (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9c69792d-d7c4-453b-ae2f-6d2d071d8606
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 088d41e71d770f746367f2760cff8ff67b15623c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605246"
---
# <a name="check-for-updates-or-turn-updates-off-report-builder-and-ssrs"></a><span data-ttu-id="47340-102">Vérifier la présence de mises à jour ou désactiver les mises à jour (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="47340-102">Check for Updates or Turn Updates Off (Report Builder and SSRS)</span></span>
  <span data-ttu-id="47340-103">Chaque fois que vous ouvrez un rapport, le Générateur de rapports vérifie si les instances publiées des parties de rapports de ce rapport ont été mises à jour sur le serveur de rapports ou site SharePoint intégré à un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="47340-103">Every time you open a report, Report Builder checks to see if the published instances of report parts in that report have been updated on the report server or SharePoint site integrated with a report server.</span></span> <span data-ttu-id="47340-104">Il recherche également des modifications dans les éléments dépendants des parties de rapport, tels que le dataset et les paramètres.</span><span class="sxs-lookup"><span data-stu-id="47340-104">It also checks for changes in the report parts' dependent items, such as the dataset and parameters.</span></span> <span data-ttu-id="47340-105">Si des parties de rapport ou leurs dépendances ont été mises à jour sur le site ou serveur, une barre d'informations dans votre rapport affiche le nombre de parties mises à jour.</span><span class="sxs-lookup"><span data-stu-id="47340-105">If any report parts or their dependencies have been updated on the site or server, an information bar in your report displays the number of updated parts.</span></span> <span data-ttu-id="47340-106">Vous pouvez choisir d'afficher et d'accepter ou de rejeter les mises à jour ou de faire disparaître la barre d'informations.</span><span class="sxs-lookup"><span data-stu-id="47340-106">You can choose to view and accept or reject the updates, or dismiss the information bar.</span></span>  
  
 <span data-ttu-id="47340-107">Vous pouvez également désactiver la barre d'informations, auquel cas vous ne serez plus informé en cas de modification des instances publiées des parties de rapport.</span><span class="sxs-lookup"><span data-stu-id="47340-107">You can also disable the information bar and not be informed if published instances of report parts have changed.</span></span> <span data-ttu-id="47340-108">Il s'agit d'un paramètre utilisateur ; il sera désactivé pour tous les rapports que vous ouvrez.</span><span class="sxs-lookup"><span data-stu-id="47340-108">This is a user setting; it will be disabled for all reports that you open.</span></span> <span data-ttu-id="47340-109">Même si vous avez désactivé la barre d'informations, vous pouvez toujours rechercher des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="47340-109">Even if you have disabled the information bar, you can still check for updates.</span></span>  
  
### <a name="to-turn-on-and-off-report-part-updates"></a><span data-ttu-id="47340-110">Pour activer et désactiver les mises à jour des parties de rapport</span><span class="sxs-lookup"><span data-stu-id="47340-110">To turn on and off report part updates</span></span>  
  
1.  <span data-ttu-id="47340-111">Cliquez sur le bouton Générateur de rapports, puis sur **options**.</span><span class="sxs-lookup"><span data-stu-id="47340-111">Click the Report Builder button, and then click **Options**.</span></span>  
  
2.  <span data-ttu-id="47340-112">Dans la boîte de dialogue **options** , sous l’onglet **ressources** , activez ou désactivez la case à cocher **afficher les mises à jour des parties de rapport dans mes rapports** .</span><span class="sxs-lookup"><span data-stu-id="47340-112">In the **Options** dialog box, on the **Resources** tab, select or clear the **Show updates to report parts in my reports** check box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="47340-113">Il s'agit d'un paramètre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="47340-113">This is a user setting.</span></span> <span data-ttu-id="47340-114">Il sera désactivé pour tous les rapports que vous ouvrez.</span><span class="sxs-lookup"><span data-stu-id="47340-114">It will be disabled for all reports that you open.</span></span>  
  
### <a name="to-check-for-updates"></a><span data-ttu-id="47340-115">Pour rechercher des mises à jour</span><span class="sxs-lookup"><span data-stu-id="47340-115">To check for updates</span></span>  
  
-   <span data-ttu-id="47340-116">Cliquez avec le bouton droit sur l’aire de conception en dehors du rapport ou dans le corps du rapport, puis cliquez sur **Rechercher les mises à jour**.</span><span class="sxs-lookup"><span data-stu-id="47340-116">Right-click the design surface outside the report, or in the report body, and click **Check for Updates**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47340-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="47340-117">See Also</span></span>  
 <span data-ttu-id="47340-118">[Parties de rapport &#40;Générateur de rapports et SSRS&#41;](report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="47340-118">[Report Parts &#40;Report Builder and SSRS&#41;](report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="47340-119">[Publier et republier des parties de rapports &#40;Générateur de rapports et SSRS&#41;](report-design/publish-and-republish-report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="47340-119">[Publish and Republish Report Parts &#40;Report Builder and SSRS&#41;](report-design/publish-and-republish-report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="47340-120">[Rechercher des parties de rapports et définir un dossier par défaut &#40;Générateur de rapports et SSRS&#41;](report-design/browse-for-report-parts-and-set-a-default-folder-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="47340-120">[Browse for Report Parts and Set a Default Folder &#40;Report Builder and SSRS&#41;](report-design/browse-for-report-parts-and-set-a-default-folder-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="47340-121">[Résoudre les problèmes liés aux parties de rapports &#40;Générateur de rapports et SSRS&#41;](../../2014/reporting-services/troubleshoot-report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="47340-121">[Troubleshoot Report Parts &#40;Report Builder and SSRS&#41;](../../2014/reporting-services/troubleshoot-report-parts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="47340-122">Parties de rapports et datasets dans le Générateur de rapports</span><span class="sxs-lookup"><span data-stu-id="47340-122">Report Parts and Datasets in Report Builder</span></span>](report-data/report-parts-and-datasets-in-report-builder.md)  
  
  
