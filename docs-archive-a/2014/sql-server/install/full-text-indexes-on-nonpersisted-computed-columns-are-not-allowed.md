---
title: Les index de recherche en texte intégral sur des colonnes calculées non persistantes ne sont pas autorisés | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- full-text indexes
ms.assetid: cba737f7-b187-47d0-8458-23dc18d18aca
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: de153d45e2f652bfea6e9dce68428af84be68b6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614997"
---
# <a name="full-text-indexes-on-nonpersisted-computed-columns-are-not-allowed"></a><span data-ttu-id="f1c82-102">Les index de recherche en texte intégral sur des colonnes calculées non persistantes ne sont pas autorisés</span><span class="sxs-lookup"><span data-stu-id="f1c82-102">Full-text indexes on nonpersisted, computed columns are not allowed</span></span>
  <span data-ttu-id="f1c82-103">Vous ne pouvez pas créer des index de recherche en texte intégral sur des colonnes calculées non déterministes et imprécises.</span><span class="sxs-lookup"><span data-stu-id="f1c82-103">You cannot create full-text indexes on nondeterministic and imprecise computed columns.</span></span> <span data-ttu-id="f1c82-104">Ces colonnes ne peuvent pas être utilisées en tant que colonnes de type ou en colonnes clés de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="f1c82-104">Such columns cannot be used as type columns or as full-text key columns.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f1c82-105">Description</span><span class="sxs-lookup"><span data-stu-id="f1c82-105">Description</span></span>  
 <span data-ttu-id="f1c82-106">Dans [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], un index de recherche en texte intégral peut être créé à l'aide d'une colonne calculée non déterministe et imprécise comme colonne de type ou colonne clé de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="f1c82-106">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], a full-text index can be created by using a nondeterministic and imprecise computed column as the type column or the full-text key column.</span></span> <span data-ttu-id="f1c82-107">Cette fonctionnalité n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="f1c82-107">This functionality is not supported.</span></span> <span data-ttu-id="f1c82-108">Lorsque vous effectuez une mise à niveau, les index de recherche en texte intégral plus anciens, incompatibles ou non pris en charge sont désactivés.</span><span class="sxs-lookup"><span data-stu-id="f1c82-108">When you upgrade, older, incompatible, and unsupported full-text indexes are disabled.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="f1c82-109">Action corrective</span><span class="sxs-lookup"><span data-stu-id="f1c82-109">Corrective Action</span></span>  
 <span data-ttu-id="f1c82-110">Pour activer ces index de recherche en texte intégral, modifiez les définitions de colonnes afin que les colonnes soient déterministes et précises.</span><span class="sxs-lookup"><span data-stu-id="f1c82-110">To enable these full-text indexes, modify the column definitions so that the columns are deterministic and precise.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1c82-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f1c82-111">See Also</span></span>  
 [<span data-ttu-id="f1c82-112">Utilisation du Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="f1c82-112">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
