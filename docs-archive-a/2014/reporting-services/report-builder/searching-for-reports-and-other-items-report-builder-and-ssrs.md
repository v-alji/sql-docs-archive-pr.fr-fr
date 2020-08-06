---
title: Recherche de rapports et d’autres éléments (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6a586659-5c2b-453b-8f40-a3a469277b17
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a964cbdbc674fb3d29e18b5e5075695f0033801e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600597"
---
# <a name="searching-for-reports-and-other-items-report-builder--and-ssrs"></a><span data-ttu-id="ef5b7-102">Recherche de rapports et d’autres éléments (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="ef5b7-102">Searching for Reports and Other Items (Report Builder  and SSRS)</span></span>
  <span data-ttu-id="ef5b7-103">Vous pouvez utiliser le Gestionnaire de rapports pour rechercher sur un serveur de rapports des éléments spécifiques en fonction de leur nom ou de leur description.</span><span class="sxs-lookup"><span data-stu-id="ef5b7-103">You can use Report Manager to search a report server for specific items by name or description.</span></span> <span data-ttu-id="ef5b7-104">Vous pouvez rechercher des rapports publiés, des modèles de rapports, des dossiers, des sources de données partagées et des ressources.</span><span class="sxs-lookup"><span data-stu-id="ef5b7-104">You can search for published reports, report models, folders, shared data sources, and resources.</span></span> <span data-ttu-id="ef5b7-105">Il est impossible de rechercher des planifications, des propriétaires, des attributions de rôles, des instantanés d'historique de rapport spécifiques ou des abonnements.</span><span class="sxs-lookup"><span data-stu-id="ef5b7-105">You cannot search for schedules, owners, role assignments, specific snapshots in report history, or subscriptions.</span></span> <span data-ttu-id="ef5b7-106">La recherche est effectuée dans la base de données du serveur de rapports dans laquelle les éléments sont stockés.</span><span class="sxs-lookup"><span data-stu-id="ef5b7-106">The search is performed on the report server database where the items are stored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ef5b7-107">Une recherche effectuée sur un système de fichiers ne permet pas d'afficher un résultat contenant des éléments gérés par un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="ef5b7-107">Performing a file system search will not return search results for items managed by a report server.</span></span>  
  
-   <span data-ttu-id="ef5b7-108">Pour rechercher des éléments dans le Gestionnaire de rapports, tapez une chaîne dans la zone de texte **Rechercher** en haut de la page.</span><span class="sxs-lookup"><span data-stu-id="ef5b7-108">To search for items in Report Manager, type a search string in the **Search for** text box at the top of the page.</span></span> <span data-ttu-id="ef5b7-109">La recherche débute par le nœud supérieur de l'arborescence des dossiers et se poursuit dans tous les niveaux.</span><span class="sxs-lookup"><span data-stu-id="ef5b7-109">Searches begin at the top node in the folder hierarchy and then proceed through every branch.</span></span> <span data-ttu-id="ef5b7-110">Si vous ne disposez pas des autorisations requises pour accéder à un niveau particulier, ce niveau est ignoré.</span><span class="sxs-lookup"><span data-stu-id="ef5b7-110">If you do not have permission to access a specific branch, that branch is skipped.</span></span> <span data-ttu-id="ef5b7-111">Ceci concerne les dossiers Mes rapports qui appartiennent à d'autres utilisateurs et également ceux des autres dossiers qui ne sont généralement pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="ef5b7-111">This applies to My Reports folders that belong to other users, and to other folders that are not generally available.</span></span> <span data-ttu-id="ef5b7-112">Seuls les rapports et les éléments que vous êtes autorisé à visualiser sont inclus dans les résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="ef5b7-112">Only reports and items that you have permission to view are included in the search results.</span></span>  
  
-   <span data-ttu-id="ef5b7-113">Pour rechercher un élément en fonction de son nom ou de sa description, spécifiez tout ou partie du texte recherché.</span><span class="sxs-lookup"><span data-stu-id="ef5b7-113">To search for an item by name or description, specify all or part of the text that you want to match.</span></span> <span data-ttu-id="ef5b7-114">La fonction de recherche ne distingue pas les majuscules des minuscules.</span><span class="sxs-lookup"><span data-stu-id="ef5b7-114">The search string is not case-sensitive.</span></span> <span data-ttu-id="ef5b7-115">Vous ne pouvez pas utiliser des opérateurs de recherche comme les symboles plus (+) ou moins (-) pour exiger ou exclure des critères de recherche.</span><span class="sxs-lookup"><span data-stu-id="ef5b7-115">You cannot use search operators such as plus (+) or minus (-) symbols to require or exclude search criteria.</span></span>  
  
-   <span data-ttu-id="ef5b7-116">Pour rechercher un texte spécifique dans un rapport, utilisez la barre d'outils située dans la partie supérieure du rapport.</span><span class="sxs-lookup"><span data-stu-id="ef5b7-116">To search for specific text within a report, use the toolbar at the top of the report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ef5b7-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ef5b7-117">See Also</span></span>  
 <span data-ttu-id="ef5b7-118">[Recherche et affichage de rapports dans Gestionnaire de rapports &#40;Générateur de rapports et SSRS&#41;](finding-and-viewing-reports-in-the-web-portal-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ef5b7-118">[Finding and Viewing Reports in Report Manager &#40;Report Builder and SSRS&#41;](finding-and-viewing-reports-in-the-web-portal-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ef5b7-119">[Utilisation de Mes rapports &#40;Générateur de rapports et de SSRS&#41;](using-my-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ef5b7-119">[Using My Reports &#40;Report Builder and SSRS&#41;](using-my-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ef5b7-120">[Recherche, affichage et gestion de rapports &#40;Générateur de rapports et SSRS &#41;](finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ef5b7-120">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ef5b7-121">Ouvrir et fermer un rapport &#40;Gestionnaire de rapports&#41;</span><span class="sxs-lookup"><span data-stu-id="ef5b7-121">Open and Close a Report &#40;Report Manager&#41;</span></span>](../reports/open-and-close-a-report-report-manager.md)  
  
  
