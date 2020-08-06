---
title: Reporting Services pour SQL Server Management Studio (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], how-to topics
ms.assetid: 60685458-9108-47bf-820a-5e7db454d408
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3f4083d8b288c8816925723f4cfaef4342dd0298
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704836"
---
# <a name="reporting-services-in-sql-server-management-studio-ssrs"></a><span data-ttu-id="86c0c-102">Reporting Services pour SQL Server Management Studio (SSRS)</span><span class="sxs-lookup"><span data-stu-id="86c0c-102">Reporting Services in SQL Server Management Studio (SSRS)</span></span>
  <span data-ttu-id="86c0c-103">Les administrateurs du serveur de rapports peuvent utiliser [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour :</span><span class="sxs-lookup"><span data-stu-id="86c0c-103">Report server administrators can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to:</span></span>  
  
-   <span data-ttu-id="86c0c-104">Activer les fonctionnalités, définir les valeurs par défaut du serveur, et gérer des travaux en cours de exécution.</span><span class="sxs-lookup"><span data-stu-id="86c0c-104">Enable features, set server defaults, and manage running jobs.</span></span>  
  
-   <span data-ttu-id="86c0c-105">Afficher et créer des rapports personnalisés.</span><span class="sxs-lookup"><span data-stu-id="86c0c-105">View and create custom reports.</span></span> <span data-ttu-id="86c0c-106">Dans l’Explorateur d’objets, un grand nombre de nœuds présentent un ensemble de rapports standard qui sont installés avec [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="86c0c-106">In Object Explorer, many nodes display a set of standard reports that are installed with [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="86c0c-107">Vous devez disposer des autorisations administrateur.</span><span class="sxs-lookup"><span data-stu-id="86c0c-107">You must have administrator permissions.</span></span> <span data-ttu-id="86c0c-108">Le schéma d'un rapport personnalisé doit correspondre au schéma des rapports installés.</span><span class="sxs-lookup"><span data-stu-id="86c0c-108">The schema of a custom report must match the schema of the installed reports.</span></span> <span data-ttu-id="86c0c-109">Pour plus d’informations, consultez [Rapports personnalisés dans Management Studio](../../ssms/object/custom-reports-in-management-studio.md) et [Rechercher la version du schéma de définition de rapport &#40;SSRS&#41;](../reports/find-the-report-definition-schema-version-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="86c0c-109">For more information, see [Custom Reports in Management Studio](../../ssms/object/custom-reports-in-management-studio.md) and [Find the Report Definition Schema Version &#40;SSRS&#41;](../reports/find-the-report-definition-schema-version-ssrs.md).</span></span>  
  
 <span data-ttu-id="86c0c-110">Les auteurs de rapport peuvent utiliser [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] pour :</span><span class="sxs-lookup"><span data-stu-id="86c0c-110">Report authors can use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to:</span></span>  
  
-   <span data-ttu-id="86c0c-111">visualiser les données spatiales d'un jeu de résultats de la requête pour un rapport cartographique.</span><span class="sxs-lookup"><span data-stu-id="86c0c-111">Visualize spatial data from a query result set for a map report.</span></span> <span data-ttu-id="86c0c-112">Après avoir exécuté la requête, utilisez l’onglet **Résultats spatiaux** dans le volet de jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="86c0c-112">After you run the query, use the **Spatial results** tab in the result set pane.</span></span> <span data-ttu-id="86c0c-113">Pour plus d’informations, consultez [Afficher des données spatiales dans l’Explorateur d’objets](../../relational-databases/scripting/view-spatial-data-in-object-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="86c0c-113">For more information, see [View Spatial Data in Object Explorer](../../relational-databases/scripting/view-spatial-data-in-object-explorer.md).</span></span>  
  
 <span data-ttu-id="86c0c-114">Cette section propose des instructions pas à pas pour effectuer diverses tâches de création de rapports à l’aide de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="86c0c-114">This section contains step-by-step instructions for performing various reporting tasks using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="86c0c-115">La création et la gestion de planifications partagées peuvent également être effectuées à l'aide du Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="86c0c-115">Creating and managing shared schedules can also be performed using Report Manager.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="86c0c-116">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="86c0c-116">In This Section</span></span>  
  
-   [<span data-ttu-id="86c0c-117">Se connecter à un serveur de rapports dans Management Studio</span><span class="sxs-lookup"><span data-stu-id="86c0c-117">Connect to a Report Server in Management Studio</span></span>](connect-to-a-report-server-in-management-studio.md)  
  
-   [<span data-ttu-id="86c0c-118">Définir les propriétés du serveur de rapports &#40;Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="86c0c-118">Set Report Server Properties &#40;Management Studio&#41;</span></span>](set-report-server-properties-management-studio.md)  
  
-   [<span data-ttu-id="86c0c-119">Créer, supprimer ou modifier un rôle &#40;Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="86c0c-119">Create, Delete, or Modify a Role &#40;Management Studio&#41;</span></span>](../security/role-definitions-create-delete-or-modify.md)  
  
-   [<span data-ttu-id="86c0c-120">Supprimer un élément &#40;Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="86c0c-120">Delete an Item &#40;Management Studio&#41;</span></span>](delete-an-item-management-studio.md)  
  
-   [<span data-ttu-id="86c0c-121">Annuler les travaux du serveur de rapports &#40;Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="86c0c-121">Cancel Report Server Jobs &#40;Management Studio&#41;</span></span>](cancel-report-server-jobs-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="86c0c-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="86c0c-122">See Also</span></span>  
 <span data-ttu-id="86c0c-123">[Serveur de rapports dans Management Studio aide (F1)](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="86c0c-123">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="86c0c-124">Présentation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="86c0c-124">Introducing SQL Server Management Studio</span></span>](../../ssms/sql-server-management-studio-ssms.md)  
  
  
