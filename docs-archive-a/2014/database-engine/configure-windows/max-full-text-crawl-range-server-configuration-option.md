---
title: max full-text crawl range (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- crawls [full-text search]
- max full-text crawl range option
ms.assetid: a49de86b-0891-4dcd-89c0-ead30aab00e0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e1dbd9e44518b6e849a06a76e21fc605172fd2ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696048"
---
# <a name="max-full-text-crawl-range-server-configuration-option"></a><span data-ttu-id="fa88e-102">max full-text crawl range (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="fa88e-102">max full-text crawl range Server Configuration Option</span></span>
  <span data-ttu-id="fa88e-103">Utilisez l’option **max full-text crawl range** pour optimiser l’utilisation du processeur, ce qui permet d’améliorer les performances de l’analyse durant une analyse complète.</span><span class="sxs-lookup"><span data-stu-id="fa88e-103">Use the **max full-text crawl range** option to optimize CPU utilization, which improves crawl performance during a full crawl.</span></span> <span data-ttu-id="fa88e-104">Avec cette option, vous pouvez spécifier le nombre de partitions que [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doit utiliser au cours d’une analyse d’index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="fa88e-104">Using this option, you can specify the number of partitions that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should use during a full index crawl.</span></span> <span data-ttu-id="fa88e-105">Par exemple, s'il existe plusieurs processeurs et si leur utilisation n'est pas optimale, vous pouvez augmenter la valeur maximale de cette option.</span><span class="sxs-lookup"><span data-stu-id="fa88e-105">For example, if there are many CPUs and their utilization is not optimal, you can increase the maximum value of this option.</span></span> <span data-ttu-id="fa88e-106">En plus de cette option, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilise d'autres facteurs, tels que le nombre de lignes d'une table et le nombre de processeurs, pour déterminer le nombre réel de partitions utilisées.</span><span class="sxs-lookup"><span data-stu-id="fa88e-106">In addition to this option, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses a number of other factors, such as the number of rows in the table and the number of CPUs, to determine the actual number of partitions used.</span></span>  
  
 <span data-ttu-id="fa88e-107">La valeur par défaut de cette option est 4, la valeur minimale est 1 et la valeur maximale est 256.</span><span class="sxs-lookup"><span data-stu-id="fa88e-107">The default value of this option is 4; the minimum value is 1, and the maximum value is 256.</span></span> <span data-ttu-id="fa88e-108">Les modifications apportées à cette option affectent uniquement les analyses ultérieures.</span><span class="sxs-lookup"><span data-stu-id="fa88e-108">Changes made to this option affect only subsequent crawls.</span></span> <span data-ttu-id="fa88e-109">Les analyses en cours d'exécution ne seront pas affectées par une modification de cette option.</span><span class="sxs-lookup"><span data-stu-id="fa88e-109">Crawls in process will not be affected by a change in this option setting.</span></span>  
  
 <span data-ttu-id="fa88e-110">L’option **max full-text crawl range** est une option avancée.</span><span class="sxs-lookup"><span data-stu-id="fa88e-110">The **max full-text crawl range** option is an advanced option.</span></span> <span data-ttu-id="fa88e-111">Si vous utilisez la procédure stockée système **sp_configure** pour modifier sa valeur, vous ne pouvez modifier l’option **max full-text crawl range** que si l’option **show advanced options** a la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="fa88e-111">If you are using the **sp_configure** system stored procedure to change the setting, you can change **max full-text crawl range** only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="fa88e-112">Le paramètre prend effet immédiatement (sans redémarrage du serveur).</span><span class="sxs-lookup"><span data-stu-id="fa88e-112">The setting takes effect immediately without a server restart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa88e-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fa88e-113">See Also</span></span>  
 <span data-ttu-id="fa88e-114">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fa88e-114">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="fa88e-115">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fa88e-115">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="fa88e-116">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fa88e-116">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
