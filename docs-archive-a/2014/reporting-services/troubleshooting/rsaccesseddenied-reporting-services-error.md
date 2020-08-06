---
title: rsAccessedDenied - Erreur Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rsAccessDenied error
ms.assetid: 2f76b1bf-96a2-4755-b76b-84e933220efc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 194006c2ef6f22b9bc27e9e8cbe1eebd027ed6b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605908"
---
# <a name="rsaccesseddenied---reporting-services-error"></a><span data-ttu-id="39a8e-102">rsAccessedDenied - Erreur Reporting Services</span><span class="sxs-lookup"><span data-stu-id="39a8e-102">rsAccessedDenied - Reporting Services Error</span></span>
  <span data-ttu-id="39a8e-103">L’erreur [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]**rsAccessedDenied** se produit quand un utilisateur n’est pas autorisé à effectuer une action.</span><span class="sxs-lookup"><span data-stu-id="39a8e-103">The [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] error **rsAccessedDenied** occurs when a user does not have permission to perform an action.</span></span> <span data-ttu-id="39a8e-104">Par exemple, il ne dispose pas de l'assignation de rôle lui permettant d'ouvrir un rapport ou il n'a pas ouvert son navigateur avec les autorisations requises.</span><span class="sxs-lookup"><span data-stu-id="39a8e-104">For, example, they do not have a role assignment that allows them to open a report or they did not open their browser with the required permissions.</span></span>  
  
||  
|-|  
|<span data-ttu-id="39a8e-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en mode natif &#124; en mode SharePoint</span><span class="sxs-lookup"><span data-stu-id="39a8e-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode &#124; SharePoint mode</span></span>|  
  
-   <span data-ttu-id="39a8e-106">Si l'erreur s'est produite en accédant au serveur de rapports directement par le biais d'une URL, l'exception est associée à une erreur HTTP 401.</span><span class="sxs-lookup"><span data-stu-id="39a8e-106">If the error occurred while accessing the report server directly through a URL, the exception is mapped to an HTTP 401 error.</span></span>  
  
-   <span data-ttu-id="39a8e-107">Si l'erreur s'est produite lors de l'utilisation du Gestionnaire de rapports ou d'un autre outil, l'erreur apparaît dans une page d'erreurs.</span><span class="sxs-lookup"><span data-stu-id="39a8e-107">If the error occurred while using Report Manager or another tool, the error appears in an error page.</span></span>  
  
-   <span data-ttu-id="39a8e-108">Si l'erreur s'est produite pendant une opération planifiée, un abonnement ou une remise, l'erreur apparaît uniquement dans le fichier journal du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="39a8e-108">If the error occurred during a scheduled operation, subscription, or delivery, the error will appear in the report server log file only.</span></span>  
  
## <a name="details"></a><span data-ttu-id="39a8e-109">Détails</span><span class="sxs-lookup"><span data-stu-id="39a8e-109">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="39a8e-110">**Nom du produit**</span><span class="sxs-lookup"><span data-stu-id="39a8e-110">**Product Name**</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="39a8e-111">**ID d'événement**</span><span class="sxs-lookup"><span data-stu-id="39a8e-111">**Event ID**</span></span>|<span data-ttu-id="39a8e-112">rsAccessedDenied</span><span class="sxs-lookup"><span data-stu-id="39a8e-112">rsAccessedDenied</span></span>|  
|<span data-ttu-id="39a8e-113">**Source de l'événement**</span><span class="sxs-lookup"><span data-stu-id="39a8e-113">**Event Source**</span></span>|<span data-ttu-id="39a8e-114">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span><span class="sxs-lookup"><span data-stu-id="39a8e-114">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span></span>|  
|<span data-ttu-id="39a8e-115">**Composant**</span><span class="sxs-lookup"><span data-stu-id="39a8e-115">**Component**</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="39a8e-116">**Texte du message**</span><span class="sxs-lookup"><span data-stu-id="39a8e-116">**Message Text**</span></span>|<span data-ttu-id="39a8e-117">Les autorisations accordées à l'utilisateur 'mon_domaine\mon_compte' sont insuffisantes pour vous permettre d'accomplir cette opération.</span><span class="sxs-lookup"><span data-stu-id="39a8e-117">The permissions granted to user 'mydomain\myAccount' are insufficient for performing this operation.</span></span> <span data-ttu-id="39a8e-118">(rsAccessDenied) (ReportingServicesLibrary)</span><span class="sxs-lookup"><span data-stu-id="39a8e-118">(rsAccessDenied) (ReportingServicesLibrary)</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="39a8e-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="39a8e-119">User Action</span></span>  
 <span data-ttu-id="39a8e-120">L'autorisation d'accéder au contenu et aux opérations d'un serveur de rapports est accordée par l'intermédiaire des attributions de rôles.</span><span class="sxs-lookup"><span data-stu-id="39a8e-120">Permission to access report server content and operations are granted through role assignments.</span></span> <span data-ttu-id="39a8e-121">Dans une nouvelle installation, seuls les administrateurs locaux ont accès à un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="39a8e-121">On a new installation, only local administrators have access to a report server.</span></span> <span data-ttu-id="39a8e-122">Pour accorder l'accès à d'autres utilisateurs, un administrateur local doit créer une attribution de rôle qui spécifie un utilisateur de domaine ou un compte de groupe, un ou plusieurs rôles définissant les tâches que l'utilisateur peut effectuer, ainsi qu'une étendue (en général, le dossier de base ou le nœud racine de l'arborescence des dossiers du serveur de rapports).</span><span class="sxs-lookup"><span data-stu-id="39a8e-122">To grant access to other users, a local administrator must create a role assignment that specifies a domain user or group account, one or more roles that define the tasks the user can perform, and a scope (usually the Home folder or root node of the report server folder hierarchy).</span></span> <span data-ttu-id="39a8e-123">Vous pouvez utiliser le Gestionnaire de rapports pour créer les attributions de rôles.</span><span class="sxs-lookup"><span data-stu-id="39a8e-123">You can use Report Manager to create the role assignments.</span></span> <span data-ttu-id="39a8e-124">Pour plus d'informations, recherchez «Attributions de rôles » dans la documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="39a8e-124">For more information, search for "Role Assignments" in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="39a8e-125">Cette erreur est également due à l'administration locale du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="39a8e-125">This error is also caused by local administration of the report server.</span></span> <span data-ttu-id="39a8e-126">Pour plus d’informations, consultez [Configurer un serveur de rapports en mode natif pour l’administration locale &#40;SSRS&#41;](../report-server/configure-a-native-mode-report-server-for-local-administration-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="39a8e-126">For more information, see [Configure a Native Mode Report Server for Local Administration &#40;SSRS&#41;](../report-server/configure-a-native-mode-report-server-for-local-administration-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39a8e-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="39a8e-127">See Also</span></span>  
 <span data-ttu-id="39a8e-128">[Attributions de rôles](../security/role-assignments.md) </span><span class="sxs-lookup"><span data-stu-id="39a8e-128">[Role Assignments](../security/role-assignments.md) </span></span>  
 <span data-ttu-id="39a8e-129">[Octroi d'autorisations sur un serveur de rapports en mode natif](../security/granting-permissions-on-a-native-mode-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="39a8e-129">[Granting Permissions on a Native Mode Report Server](../security/granting-permissions-on-a-native-mode-report-server.md) </span></span>  
 [<span data-ttu-id="39a8e-130">Rôles et autorisations &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="39a8e-130">Roles and Permissions &#40;Reporting Services&#41;</span></span>](../security/roles-and-permissions-reporting-services.md)  
  
  
