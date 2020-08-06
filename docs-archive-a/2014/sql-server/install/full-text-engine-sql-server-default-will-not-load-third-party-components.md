---
title: Le moteur de recherche en texte intégral Microsoft pour SQL Server ne chargera pas par défaut les composants tiers non signés | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Full-Text Engine for SQL service
- MSFTESQL service
ms.assetid: 029f9895-7232-4149-9362-3ab1a4133d21
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 12ff188fb6aa6ac286817a7cc1c3ad726483c886
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615000"
---
# <a name="the-microsoft-full-text-engine-for-sql-server-will-not-load-unsigned-third-party-components-by-default"></a><span data-ttu-id="2ac79-102">Le service MSFTESQL (Microsoft Full-Text Engine for SQL Server) ne chargera pas par défaut les composants tiers non signés</span><span class="sxs-lookup"><span data-stu-id="2ac79-102">The Microsoft Full-Text Engine for SQL Server will not load unsigned third-party components by default</span></span>
  <span data-ttu-id="2ac79-103">Par défaut, le service MSFTESQL ([!INCLUDE[msCoName](../../includes/msconame-md.md)] Full-Text Engine for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]) ne charge pas les composants qui ne sont pas signés par [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ac79-103">By default, [!INCLUDE[msCoName](../../includes/msconame-md.md)] Full-Text Engine for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will not load components that are not signed by [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span></span>  
  
## <a name="component"></a><span data-ttu-id="2ac79-104">Composant</span><span class="sxs-lookup"><span data-stu-id="2ac79-104">Component</span></span>  
 <span data-ttu-id="2ac79-105">Recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="2ac79-105">Full-Text Search</span></span>  
  
## <a name="description"></a><span data-ttu-id="2ac79-106">Description</span><span class="sxs-lookup"><span data-stu-id="2ac79-106">Description</span></span>  
 <span data-ttu-id="2ac79-107">Un filtre d'un fournisseur tiers, par exemple un filtre PDF déjà installé sur le serveur, n'est pas chargé par le service MSFTESQL ([!INCLUDE[msCoName](../../includes/msconame-md.md)] Full-Text Engine for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]) par défaut après la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="2ac79-107">A third-party filter, such as a PDF filter, that is currently installed on the server will not be loaded by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Full-Text Engine for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by default after upgrade.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="2ac79-108">Action corrective</span><span class="sxs-lookup"><span data-stu-id="2ac79-108">Corrective Action</span></span>  
 <span data-ttu-id="2ac79-109">Pour charger un filtre tiers, vous devez définir *load_os_resource* et désactiver *verify_signature* sur cette instance.</span><span class="sxs-lookup"><span data-stu-id="2ac79-109">To load a third party filter, you must set *load_os_resource* and turn off *verify_signature* on that instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ac79-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2ac79-110">See Also</span></span>  
 [<span data-ttu-id="2ac79-111">Utilisation du Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="2ac79-111">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
