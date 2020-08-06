---
title: Les index de recherche en texte intégral sur les bases de données Master, tempdb et Model ne sont pas pris en charge | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- full-text indexes
ms.assetid: f7992965-42c1-4eb8-a7fb-afb38b67c740
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: fbd5e3133ed87fed9bdaf6d668df62c6471df766
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614998"
---
# <a name="full-text-indexes-on-master-tempdb-and-model-databases-are-not-supported"></a><span data-ttu-id="c23d6-102">Les index de recherche en texte intégral ne sont pas pris en charge dans les bases de données master, tempdb et model</span><span class="sxs-lookup"><span data-stu-id="c23d6-102">Full-text indexes on master, tempdb and model databases are not supported</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c23d6-103">ne permet pas de créer des index de recherche en texte intégral sur une base de données système.</span><span class="sxs-lookup"><span data-stu-id="c23d6-103">does not allow full-text indexes on any system database.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c23d6-104">Description</span><span class="sxs-lookup"><span data-stu-id="c23d6-104">Description</span></span>  
 <span data-ttu-id="c23d6-105">Dans [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], les index de texte intégral étaient pris en charge sur les bases de données master, tempdb et model.</span><span class="sxs-lookup"><span data-stu-id="c23d6-105">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], full-text indexes were supported on the master, tempdb, and model databases.</span></span>  
  
 <span data-ttu-id="c23d6-106">Les catalogues de texte intégral dans les bases de données Master, tempdb et Model sont supprimés au cours de la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="c23d6-106">Any full-text catalogs in the master, tempdb, and model databases are removed during the upgrade.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c23d6-107">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c23d6-107">See Also</span></span>  
 [<span data-ttu-id="c23d6-108">Utilisation du Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="c23d6-108">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
