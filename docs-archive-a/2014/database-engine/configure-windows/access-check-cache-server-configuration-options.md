---
title: access check cache (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- access check cache option
- access check cache bucket count
- access check cache quota
ms.assetid: 0a992ea8-3ec6-4a4d-97b5-460ae7326247
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: feed895eeb7b11b4c41c51c4c26859a1057d2733
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600236"
---
# <a name="access-check-cache-server-configuration-options"></a><span data-ttu-id="21f69-102">access check cache (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="21f69-102">access check cache Server Configuration Options</span></span>
<span data-ttu-id="21f69-103">Lorsque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]accède aux objets de base de données, la vérification de l'accès est mise en cache dans une structure interne appelée le **cache de résultat de la vérification d'accès**.</span><span class="sxs-lookup"><span data-stu-id="21f69-103">When database objects are accessed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the access check is cached in an internal structure called the **access check result cache**.</span></span> 
  
<span data-ttu-id="21f69-104">L’option **access check cache bucket count** contrôle le nombre de compartiments de hachage utilisés pour le cache des résultats de la vérification d’accès.</span><span class="sxs-lookup"><span data-stu-id="21f69-104">The **access check cache bucket count** option controls the number of hash buckets that are used for the access check result cache.</span></span> 

<span data-ttu-id="21f69-105">L’option **access check cache quota** contrôle le nombre d’entrées stockées dans le cache des résultats de la vérification d’accès.</span><span class="sxs-lookup"><span data-stu-id="21f69-105">The **access check cache quota** option controls the number of entries that are stored in the access check result cache.</span></span> <span data-ttu-id="21f69-106">Quand le nombre maximal d’entrées est atteint, les entrées les plus anciennes sont supprimées du cache des résultats de la vérification d’accès.</span><span class="sxs-lookup"><span data-stu-id="21f69-106">When the maximum number of entries is reached, the oldest entries are removed from the access check result cache.</span></span>
  
<span data-ttu-id="21f69-107">Les valeurs par défaut 0 indiquent que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gère ces options.</span><span class="sxs-lookup"><span data-stu-id="21f69-107">The default values of 0 indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is managing these options.</span></span> <span data-ttu-id="21f69-108">À partir de [!INCLUDE[ssKatmai](../../includes/ssKatmai-md.md)] [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] , les valeurs par défaut sont converties en configurations internes suivantes :</span><span class="sxs-lookup"><span data-stu-id="21f69-108">From [!INCLUDE[ssKatmai](../../includes/ssKatmai-md.md)] through [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], the default values translate to the following internal configurations:</span></span>
-   <span data-ttu-id="21f69-109">Pour la vérification d’accès nombre de compartiments du cache, la valeur 0 définit une valeur par défaut de 256 compartiments pour l’architecture x86 et 2 048 compartiments pour les architectures x64 et IA-64.</span><span class="sxs-lookup"><span data-stu-id="21f69-109">For access check cache bucket count, the value 0 sets a default value of 256 buckets for x86 architecture, and 2,048 buckets for x64 and IA-64 architectures.</span></span>
-   <span data-ttu-id="21f69-110">Pour le quota de vérification d’accès du cache, la valeur 0 définit une valeur par défaut de 1 024 entrées pour l’architecture x86 et 28 192 048 compartiments pour les architectures x64 et IA-64.</span><span class="sxs-lookup"><span data-stu-id="21f69-110">For access check cache quota, the value 0 sets a default value of 1,024 entries for x86 architecture, and 28,192,048 buckets for x64 and IA-64 architectures.</span></span>

<span data-ttu-id="21f69-111">Dans de rares circonstances, la modification de ces options peut améliorer les performances.</span><span class="sxs-lookup"><span data-stu-id="21f69-111">In rare circumstances, performance can be improved by changing these options.</span></span> <span data-ttu-id="21f69-112">Par exemple, vous pouvez réduire la taille du cache des résultats de la vérification d’accès si la quantité de mémoire utilisée est trop importante.</span><span class="sxs-lookup"><span data-stu-id="21f69-112">For example, you may want to reduce the size of the access check result cache if too much memory is used.</span></span> <span data-ttu-id="21f69-113">Vous pouvez aussi augmenter la taille du cache des résultats de la vérification d’accès si vous constatez une utilisation intensive du processeur quand les autorisations sont recalculées.</span><span class="sxs-lookup"><span data-stu-id="21f69-113">Or, you may want to increase the size of the access check result cache if you experience high CPU usage when permissions are recalculated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="21f69-114">Microsoft recommande de ne modifier ces options que sur recommandation du support technique.</span><span class="sxs-lookup"><span data-stu-id="21f69-114">Microsoft recommends only changing these options when directed by Microsoft Customer Support Services.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="21f69-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="21f69-115">See Also</span></span>  
 <span data-ttu-id="21f69-116">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="21f69-116">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="21f69-117">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="21f69-117">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
