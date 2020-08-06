---
title: SMO and DMO XPs (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: bcd945ba-5d81-4124-9a2b-d87491c2a369
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f18fc6fafcf033113c983f990700158a10aec92a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707848"
---
# <a name="smo-and-dmo-xps-server-configuration-option"></a><span data-ttu-id="504c9-102">SMO and DMO XPs (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="504c9-102">SMO and DMO XPs Server Configuration Option</span></span>
  <span data-ttu-id="504c9-103">Utilisez l'option SMO and DMO XPs pour activer les procédures stockées étendues [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Object (SMO) sur ce serveur.</span><span class="sxs-lookup"><span data-stu-id="504c9-103">Use the SMO and DMO XPs option to enable [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Object (SMO) extended stored procedures on this server.</span></span>  
  
 <span data-ttu-id="504c9-104">Remarque : à compter de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], DMO a été supprimé de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="504c9-104">Note than beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], DMO has been removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="504c9-105">Les valeurs possibles sont décrites dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="504c9-105">The possible values are described in the following table:</span></span>  
  
|<span data-ttu-id="504c9-106">Valeur</span><span class="sxs-lookup"><span data-stu-id="504c9-106">Value</span></span>|<span data-ttu-id="504c9-107">Signification</span><span class="sxs-lookup"><span data-stu-id="504c9-107">Meaning</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="504c9-108">0</span><span class="sxs-lookup"><span data-stu-id="504c9-108">0</span></span>|<span data-ttu-id="504c9-109">Les procédures étendues SMO ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="504c9-109">SMO XPs are not available.</span></span>|  
|<span data-ttu-id="504c9-110">1</span><span class="sxs-lookup"><span data-stu-id="504c9-110">1</span></span>|<span data-ttu-id="504c9-111">Les procédures étendues SMO sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="504c9-111">SMO XPs are available.</span></span> <span data-ttu-id="504c9-112">Il s’agit de la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="504c9-112">This is the default.</span></span>|  
  
 <span data-ttu-id="504c9-113">Le paramètre prend effet immédiatement.</span><span class="sxs-lookup"><span data-stu-id="504c9-113">The setting takes effect immediately.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="504c9-114">Exemples</span><span class="sxs-lookup"><span data-stu-id="504c9-114">Examples</span></span>  
 <span data-ttu-id="504c9-115">L'exemple suivant active les procédures stockées étendues de SMO.</span><span class="sxs-lookup"><span data-stu-id="504c9-115">The following example enables SMO extended stored procedures.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'SMO and DMO XPs', 1;  
GO  
RECONFIGURE  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="504c9-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="504c9-116">See Also</span></span>  
 [<span data-ttu-id="504c9-117">Guide de programmation SQL Server Management Objects &#40;SMO&#41;</span><span class="sxs-lookup"><span data-stu-id="504c9-117">SQL Server Management Objects &#40;SMO&#41; Programming Guide</span></span>](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md)  
  
  
