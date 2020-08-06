---
title: Fonctionnalités des outils d’administration déconseillées dans SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: a08d1354-cc91-4ab7-a73f-3ad815af3d5a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 484e4078e25249e17a1d8b87426a395c3cfa1725
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603004"
---
# <a name="deprecated-management-tools-features-in-sql-server-2014"></a><span data-ttu-id="65a12-102">Fonctionnalités des outils d'administration déconseillées dans SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="65a12-102">Deprecated Management Tools Features in SQL Server 2014</span></span>
  <span data-ttu-id="65a12-103">Cette rubrique décrit les fonctionnalités des outils d'administration déconseillées qui sont toujours disponibles dans [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65a12-103">This topic describes the deprecated Management Tools features that are still available in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="65a12-104">Il est prévu que ces fonctionnalités soient supprimées dans une prochaine version de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65a12-104">These features are scheduled to be removed in a future release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="65a12-105">Les fonctions déconseillées ne doivent pas être utilisées dans de nouvelles applications.</span><span class="sxs-lookup"><span data-stu-id="65a12-105">Deprecated features should not be used in new applications.</span></span>  
  
|<span data-ttu-id="65a12-106">Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="65a12-106">Feature</span></span>|<span data-ttu-id="65a12-107">Étape d'abandon</span><span class="sxs-lookup"><span data-stu-id="65a12-107">Deprecation stage</span></span>|  
|-------------|-----------------------|  
|[!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)]<span data-ttu-id="65a12-108">API de serveur inscrit</span><span class="sxs-lookup"><span data-stu-id="65a12-108">Registered Server API</span></span>|<span data-ttu-id="65a12-109">Annonce</span><span class="sxs-lookup"><span data-stu-id="65a12-109">Announcement</span></span>|  
|<span data-ttu-id="65a12-110">sqlps.exe</span><span class="sxs-lookup"><span data-stu-id="65a12-110">sqlps.exe</span></span>|<span data-ttu-id="65a12-111">Warning</span><span class="sxs-lookup"><span data-stu-id="65a12-111">Warning</span></span>|  
|<span data-ttu-id="65a12-112">osql.exe</span><span class="sxs-lookup"><span data-stu-id="65a12-112">osql.exe</span></span>|<span data-ttu-id="65a12-113">Warning</span><span class="sxs-lookup"><span data-stu-id="65a12-113">Warning</span></span>|  
|<span data-ttu-id="65a12-114">SQLMail</span><span class="sxs-lookup"><span data-stu-id="65a12-114">SQLMail</span></span>|<span data-ttu-id="65a12-115">Warning</span><span class="sxs-lookup"><span data-stu-id="65a12-115">Warning</span></span>|  
|<span data-ttu-id="65a12-116">Classe SMO : classe Microsoft.SQLServer.Management.Smo.Information</span><span class="sxs-lookup"><span data-stu-id="65a12-116">SMO class: Microsoft.SQLServer.Management.Smo.Information class</span></span>|<span data-ttu-id="65a12-117">Annonce</span><span class="sxs-lookup"><span data-stu-id="65a12-117">Announcement</span></span>|  
|<span data-ttu-id="65a12-118">Classe SMO : classe Microsoft.SQLServer.Management.Smo.Settings</span><span class="sxs-lookup"><span data-stu-id="65a12-118">SMO class: Microsoft.SQLServer.Management.Smo.Settings class</span></span>|<span data-ttu-id="65a12-119">Annonce</span><span class="sxs-lookup"><span data-stu-id="65a12-119">Announcement</span></span>|  
|<span data-ttu-id="65a12-120">Classe SMO : classe Microsoft.SQLServer.Management.Smo.DatabaseOptions</span><span class="sxs-lookup"><span data-stu-id="65a12-120">SMO Class: Microsoft.SQLServer.Management.Smo.DatabaseOptions class</span></span>|<span data-ttu-id="65a12-121">Annonce</span><span class="sxs-lookup"><span data-stu-id="65a12-121">Announcement</span></span>|  
|<span data-ttu-id="65a12-122">Classe SMO : propriété Microsoft.SqlServer.Management.Smo.DatabaseDdlTrigger.NotForReplication</span><span class="sxs-lookup"><span data-stu-id="65a12-122">SMO Class: Microsoft.SqlServer.Management.Smo.DatabaseDdlTrigger.NotForReplication property</span></span>|<span data-ttu-id="65a12-123">Annonce</span><span class="sxs-lookup"><span data-stu-id="65a12-123">Announcement</span></span>|  
|<span data-ttu-id="65a12-124">Système de projet de base de données, incluant l'intégration du contrôle de code source, dans SSMS</span><span class="sxs-lookup"><span data-stu-id="65a12-124">The Database Project System, including source-control integration, in SSMS</span></span>|<span data-ttu-id="65a12-125">Annonce</span><span class="sxs-lookup"><span data-stu-id="65a12-125">Announcement</span></span>|  
|<span data-ttu-id="65a12-126">Notifications Net send (Agent[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="65a12-126">Net send notifications ([!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent)</span></span>|<span data-ttu-id="65a12-127">Annonce</span><span class="sxs-lookup"><span data-stu-id="65a12-127">Announcement</span></span>|  
|<span data-ttu-id="65a12-128">Notifications par radiomessagerie (Agent[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="65a12-128">Pager notifications ([!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent)</span></span>|<span data-ttu-id="65a12-129">Annonce</span><span class="sxs-lookup"><span data-stu-id="65a12-129">Announcement</span></span>|  
|<span data-ttu-id="65a12-130">Sous-système ActiveX (Agent[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="65a12-130">The ActiveX subsystem ([!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent)</span></span>|<span data-ttu-id="65a12-131">Annonce</span><span class="sxs-lookup"><span data-stu-id="65a12-131">Announcement</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="65a12-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="65a12-132">See Also</span></span>  
 [<span data-ttu-id="65a12-133">Compatibilité descendante</span><span class="sxs-lookup"><span data-stu-id="65a12-133">Backward Compatibility</span></span>](../../2014/getting-started/backward-compatibility.md)  
  
  
