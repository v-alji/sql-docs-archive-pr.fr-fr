---
title: ft notify bandwidth (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- ft notify bandwidth opion
- small memory buffers
- memory [SQL Server], buffers
ms.assetid: 9ca284c5-f3e0-4a67-a132-fff376ff0ffe
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: dc5839f699d55edf86c5e3e3f0eb001089a0a5dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706747"
---
# <a name="ft-notify-bandwidth-server-configuration-option"></a><span data-ttu-id="9ba34-102">ft notify bandwidth (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="9ba34-102">ft notify bandwidth Server Configuration Option</span></span>
  <span data-ttu-id="9ba34-103">Utilisez l’option **ft notify bandwidth** pour spécifier la taille maximale que peut prendre le pool des petites mémoires tampons.</span><span class="sxs-lookup"><span data-stu-id="9ba34-103">Use the **ft notify bandwidth** option to specify the size to which the pool of small memory buffers can grow.</span></span> <span data-ttu-id="9ba34-104">Les petites mémoires tampons ont une taille de 64 kilo-octets (Ko).</span><span class="sxs-lookup"><span data-stu-id="9ba34-104">Small memory buffers are 64 kilobytes (KB) in size.</span></span> <span data-ttu-id="9ba34-105">La valeur du paramètre *max* spécifie le nombre maximal de tampons que le gestionnaire de mémoire de texte intégral doit maintenir dans un pool de petites mémoires tampons.</span><span class="sxs-lookup"><span data-stu-id="9ba34-105">The *max* parameter value specifies the maximum number of buffers that the full-text memory manager should maintain in a small buffer pool.</span></span> <span data-ttu-id="9ba34-106">Si la `max` valeur est égale à zéro, il n’y a aucune limite supérieure au nombre de mémoires tampons qui peuvent se trouver dans un petit pool de mémoires tampons.</span><span class="sxs-lookup"><span data-stu-id="9ba34-106">If the `max` value is zero, then there is no upper limit to the number of buffers that can be in a small buffer pool.</span></span>  
  
 <span data-ttu-id="9ba34-107">Le paramètre **min** spécifie le nombre minimal de mémoires tampons devant être maintenues dans le pool des petites mémoires tampons.</span><span class="sxs-lookup"><span data-stu-id="9ba34-107">The **min** parameter specifies the minimum number of memory buffers that must be maintained in the pool of small memory buffers.</span></span> <span data-ttu-id="9ba34-108">À la demande du gestionnaire de mémoire [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], tous les pools de mémoires tampons supplémentaires sont libérés, mais ce nombre minimal de mémoires tampons est conservé.</span><span class="sxs-lookup"><span data-stu-id="9ba34-108">Upon request from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory manager, all extra buffer pools will be released but this minimum number of buffers will be maintained.</span></span> <span data-ttu-id="9ba34-109">Toutefois, si la valeur **min** spécifiée est nulle, toutes les mémoires tampons sont libérées.</span><span class="sxs-lookup"><span data-stu-id="9ba34-109">If, however, the **min** value specified is zero, then all memory buffers are released.</span></span>  
  
 <span data-ttu-id="9ba34-110">Dans certains cas, le nombre de mémoires tampons allouées actuellement est inférieur à la valeur spécifiée par le paramètre **min** .</span><span class="sxs-lookup"><span data-stu-id="9ba34-110">Under certain circumstances the number of buffers currently allocated is less than the value specified by the **min** parameter.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9ba34-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9ba34-111">See Also</span></span>  
 <span data-ttu-id="9ba34-112">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9ba34-112">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="9ba34-113">[ft crawl bandwidth (option de configuration de serveur)](ft-crawl-bandwidth-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="9ba34-113">[ft crawl bandwidth Server Configuration Option](ft-crawl-bandwidth-server-configuration-option.md) </span></span>  
 [<span data-ttu-id="9ba34-114">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9ba34-114">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
