---
title: Les filtres et les analyseurs lexicaux de recherche en texte intégral ont été considérablement améliorés dans SQL Server 2005 et SQL Server 2008 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- filters [Full-Text Search]
- word breakers [Full-Text Search]
ms.assetid: 8d06bda9-0bbf-4baa-b270-07b1c1f640eb
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d2e7d3b8da56b407d3937b05cd980c3f8a4eb0c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613806"
---
# <a name="full-text-search-word-breakers-and-filters-significantly-improved-in-sql-server-2005-and-sql-server-2008"></a><span data-ttu-id="98c7c-102">Les filtres et les analyseurs lexicaux pour la recherche en texte intégral ont été considérablement améliorés dans SQL Server 2005 et SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="98c7c-102">Full-Text Search word breakers and filters significantly improved in SQL Server 2005 and SQL Server 2008</span></span>
  <span data-ttu-id="98c7c-103">Les filtres et les analyseurs lexicaux ont été considérablement améliorés.</span><span class="sxs-lookup"><span data-stu-id="98c7c-103">The word breakers and filters were significantly changed.</span></span> <span data-ttu-id="98c7c-104">D'autres améliorations ont été apportées aux analyseurs lexicaux, notamment une prise en charge étendue des langues et une plus grande fiabilité.</span><span class="sxs-lookup"><span data-stu-id="98c7c-104">Additional improvements have been made to word breakers, including enhanced language coverage and reliability.</span></span>  
  
## <a name="description"></a><span data-ttu-id="98c7c-105">Description</span><span class="sxs-lookup"><span data-stu-id="98c7c-105">Description</span></span>  
 <span data-ttu-id="98c7c-106">Les analyseurs lexicaux et les filtres utilisés pour la recherche en texte intégral dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ont été considérablement modifiés afin d'optimiser leur fonctionnalité et fiabilité.</span><span class="sxs-lookup"><span data-stu-id="98c7c-106">Word breakers and filters used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Full-Text Search have been significantly modified to achieve improvements in functionality and reliability.</span></span> <span data-ttu-id="98c7c-107">Dans certains cas spécifiques, les modifications apportées aux analyseurs lexicaux peuvent avoir un impact sur les jetons de certaines données.</span><span class="sxs-lookup"><span data-stu-id="98c7c-107">In some specific cases, changes to the word breakers can impact how some data is tokenized.</span></span> <span data-ttu-id="98c7c-108">Les jetons créés dans [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] peuvent être différents de ceux créés dans [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] ou [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98c7c-108">Tokens created in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] may be different from earlier tokens created in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] or [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="98c7c-109">Pour plus d’informations sur les analyseurs lexicaux, consultez [configurer et gérer](../../relational-databases/search/configure-and-manage-word-breakers-and-stemmers-for-search.md)les analyseurs lexicaux et les générateurs de formes dérivées pour la recherche.</span><span class="sxs-lookup"><span data-stu-id="98c7c-109">For information about word breakers, see [Configure and Manage Word Breakers and Stemmers for Search](../../relational-databases/search/configure-and-manage-word-breakers-and-stemmers-for-search.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98c7c-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="98c7c-110">See Also</span></span>  
 [<span data-ttu-id="98c7c-111">Utilisation du Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="98c7c-111">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
