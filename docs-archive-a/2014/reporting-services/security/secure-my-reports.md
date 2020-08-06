---
title: Sécuriser Mes rapports | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- denying My Reports folder access
- private folders [Reporting Services]
- user workspace [Reporting Services]
- security [Reporting Services], My Reports folder
- My Reports folder [Reporting Services]
ms.assetid: 3b23a382-13b8-4196-9a93-7fe62d03a63c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b0a832133852e05c54a80b73fad8a91426840467
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697443"
---
# <a name="secure-my-reports"></a><span data-ttu-id="d5143-102">Sécuriser Mes Rapports</span><span class="sxs-lookup"><span data-stu-id="d5143-102">Secure My Reports</span></span>
  <span data-ttu-id="d5143-103">La fonctionnalité Mes Rapports offre un espace géré par l'utilisateur pour utiliser des rapports.</span><span class="sxs-lookup"><span data-stu-id="d5143-103">The My Reports feature provides a user-managed workspace for working with reports.</span></span> <span data-ttu-id="d5143-104">Pour remplir sa fonction, le dossier Mes Rapports nécessite des autorisations moins restrictives que d'autres dossiers d'utilisation générale.</span><span class="sxs-lookup"><span data-stu-id="d5143-104">In order to serve its intended purpose, the My Reports folder requires less restrictive permissions than other folders that are available for general use.</span></span> <span data-ttu-id="d5143-105">Les utilisateurs qui disposent uniquement d'autorisations d'affichage et d'exécution de rapports dans d'autres dossiers peuvent nécessiter un ensemble étendu d'autorisations pour gérer leurs dossiers Mes rapports et leurs contenus.</span><span class="sxs-lookup"><span data-stu-id="d5143-105">Users who have permissions to only view and run reports in other folders might require an expanded set of permissions to manage their My Reports folders and content that they own.</span></span> [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="d5143-106">offre une attribution et une définition de rôles spécialisées à cette fin.</span><span class="sxs-lookup"><span data-stu-id="d5143-106">provides a specialized role assignment and role definition for this purpose.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d5143-107">Le dossier Mes Rapports est uniquement disponible dans le Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="d5143-107">My Reports is available only in Report Manager.</span></span> <span data-ttu-id="d5143-108">Il n’est pas disponible dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5143-108">It is not available in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
## <a name="role-assignment-for-my-reports"></a><span data-ttu-id="d5143-109">Attribution de rôle pour Mes Rapports</span><span class="sxs-lookup"><span data-stu-id="d5143-109">Role Assignment for My Reports</span></span>  
 <span data-ttu-id="d5143-110">L'attribution de rôle pour Mes Rapports contient des éléments prédéfinis et est automatiquement créée pour chaque utilisateur qui active un dossier Mes Rapports.</span><span class="sxs-lookup"><span data-stu-id="d5143-110">The role assignment for My Reports has preset elements and is automatically created for each user who activates a My Reports folder.</span></span> <span data-ttu-id="d5143-111">Compter sur le serveur de rapports pour attribuer automatiquement la sécurité est particulièrement utile pour les organisations qui utilisent beaucoup Mes Rapports puisque les administrateurs ne sont plus ainsi tenus d'activer l'accès pour chaque utilisateur de Mes Rapports.</span><span class="sxs-lookup"><span data-stu-id="d5143-111">Having the report server automatically assign security is especially useful for organizations that use My Reports widely because administrators do not have to enable access for each My Reports user.</span></span>  
  
 <span data-ttu-id="d5143-112">Une attribution de rôle **Mes Rapports** se compose des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="d5143-112">A **My Reports** role assignment consists of the following elements:</span></span>  
  
-   <span data-ttu-id="d5143-113">Le dossier de Mes rapports de l’utilisateur, situé dans dossiers des utilisateurs \\ *\<username>* \Mes rapports.</span><span class="sxs-lookup"><span data-stu-id="d5143-113">The user's My Reports folder, which is located in Users Folders\\*\<username>* \My Reports folder.</span></span>  
  
-   <span data-ttu-id="d5143-114">Le compte d'utilisateur, qui est déterminé lors de l'activation du dossier Mes Rapports.</span><span class="sxs-lookup"><span data-stu-id="d5143-114">The user account, which is determined when the My Reports folder is activated.</span></span> <span data-ttu-id="d5143-115">Un dossier est activé lorsqu'un utilisateur clique sur un dossier Mes Rapports dans le Gestionnaire de rapports ou lorsqu'il publie un rapport dans un dossier Mes Rapports depuis le Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="d5143-115">A folder is activated when a user clicks a My Reports folder in Report Manager or when publishing a report to a My Reports folder from Report Designer.</span></span> <span data-ttu-id="d5143-116">Ce dossier est également activé lorsqu'un utilisateur demande des propriétés sur le lien Mes Rapports.</span><span class="sxs-lookup"><span data-stu-id="d5143-116">This folder is also activated when a user requests properties on the My Reports link.</span></span>  
  
-   <span data-ttu-id="d5143-117">La définition de rôle prédéfinie pour Mes rapports.</span><span class="sxs-lookup"><span data-stu-id="d5143-117">The predefined role definition for My Reports.</span></span>  
  
## <a name="role-definition-for-my-reports"></a><span data-ttu-id="d5143-118">Définition de rôle pour Mes Rapports</span><span class="sxs-lookup"><span data-stu-id="d5143-118">Role Definition for My Reports</span></span>  
 <span data-ttu-id="d5143-119">La définition de rôle **Mes Rapports** comprend des tâches qui prennent en charge la gestion du contenu d’un dossier Mes Rapports.</span><span class="sxs-lookup"><span data-stu-id="d5143-119">The **My Reports** role definition includes tasks that support content management of a My Reports folder.</span></span> <span data-ttu-id="d5143-120">Le rôle **Mes Rapports** est conçu pour être un rôle à fonction unique.</span><span class="sxs-lookup"><span data-stu-id="d5143-120">The **My Reports** role is intended to be a single-purpose role.</span></span> <span data-ttu-id="d5143-121">Bien que vous puissiez le choisir pour n'importe quelle stratégie de sécurité au niveau élément, vous devez éviter de le faire pour réduire le risque de le modifier en fonction d'autres dossiers.</span><span class="sxs-lookup"><span data-stu-id="d5143-121">Although you can choose it for any item-level security policy, you should avoid doing so to minimize the chance that you will modify it to accommodate other folder requirements.</span></span> <span data-ttu-id="d5143-122">Réserver le rôle **Mes Rapports** pour la fonctionnalité Mes Rapports peut vous permettre d’assurer une expérience utilisateur cohérente.</span><span class="sxs-lookup"><span data-stu-id="d5143-122">Reserving the **My Reports** role for the My Reports feature can help you maintain a consistent experience for users.</span></span>  
  
 <span data-ttu-id="d5143-123">Par défaut, seuls les administrateurs des serveurs de rapports modifient le rôle **Mes Rapports** .</span><span class="sxs-lookup"><span data-stu-id="d5143-123">By default, only report server administrators modify the **My Reports** role.</span></span> <span data-ttu-id="d5143-124">Personnalisez le rôle **Mes Rapports** en modifiant les tâches qu’il contient.</span><span class="sxs-lookup"><span data-stu-id="d5143-124">You can customize the **My Reports** role by changing the tasks it contains.</span></span> <span data-ttu-id="d5143-125">Vous pouvez également le remplacer par un autre rôle.</span><span class="sxs-lookup"><span data-stu-id="d5143-125">You can also substitute a different role.</span></span>  
  
## <a name="denying-access-to-my-reports"></a><span data-ttu-id="d5143-126">Refus d'accès à Mes Rapports</span><span class="sxs-lookup"><span data-stu-id="d5143-126">Denying Access to My Reports</span></span>  
 <span data-ttu-id="d5143-127">Vous pouvez empêcher les utilisateurs d'accéder à Mes Rapports comme suit :</span><span class="sxs-lookup"><span data-stu-id="d5143-127">You can prevent users from accessing My Reports by:</span></span>  
  
-   <span data-ttu-id="d5143-128">Désactivation de Mes Rapports dans la page Paramètres du site.</span><span class="sxs-lookup"><span data-stu-id="d5143-128">Disabling My Reports on the Site Settings page.</span></span> <span data-ttu-id="d5143-129">Pour plus d’informations, consultez [Activer et désactiver Mes rapports](../report-server/enable-and-disable-my-reports.md).</span><span class="sxs-lookup"><span data-stu-id="d5143-129">For more information, see [Enable and Disable My Reports](../report-server/enable-and-disable-my-reports.md).</span></span>  
  
-   <span data-ttu-id="d5143-130">Suppression de toutes les tâches du rôle **Mes Rapports** .</span><span class="sxs-lookup"><span data-stu-id="d5143-130">Removing all tasks from the **My Reports** role.</span></span>  
  
 <span data-ttu-id="d5143-131">Lorsque vous désactivez Mes Rapports, tout lien vers un dossier Mes Rapports est supprimé du Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="d5143-131">When you disable My Reports, the link to a My Reports folder is removed from Report Manager.</span></span> <span data-ttu-id="d5143-132">La structure de dossiers sous-jacente qui prend en charge Mes Rapports (c'est-à-dire, le dossier Dossiers des utilisateurs et ses sous-dossiers) reste disponible et l'utilisateur peut y accéder s'il connaît le chemin d'accès au dossier.</span><span class="sxs-lookup"><span data-stu-id="d5143-132">The underlying folder structure that supports My Reports (that is, the Users Folders folder and subfolders) is still available and can be accessed if a user knows the folder path.</span></span> <span data-ttu-id="d5143-133">La suppression de toutes les tâches du rôle **Mes Rapports** garantit le refus de l’accès.</span><span class="sxs-lookup"><span data-stu-id="d5143-133">Removing tasks from **My Reports** role ensures that access is prevented.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5143-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d5143-134">See Also</span></span>  
 <span data-ttu-id="d5143-135">[Sécuriser des rapports et des ressources](secure-reports-and-resources.md) </span><span class="sxs-lookup"><span data-stu-id="d5143-135">[Secure Reports and Resources](secure-reports-and-resources.md) </span></span>  
 <span data-ttu-id="d5143-136">[Dossiers sécurisés](secure-folders.md) </span><span class="sxs-lookup"><span data-stu-id="d5143-136">[Secure Folders](secure-folders.md) </span></span>  
 [<span data-ttu-id="d5143-137">Octroi d'autorisations sur un serveur de rapports en mode natif</span><span class="sxs-lookup"><span data-stu-id="d5143-137">Granting Permissions on a Native Mode Report Server</span></span>](granting-permissions-on-a-native-mode-report-server.md)  
  
  
