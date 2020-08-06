---
title: La recherche en texte intégral a changé depuis SQL Server 2008 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: d253bb05-9166-4b50-bd4a-27b818f514e0
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 99d3ed4478f007bbe7f05838250aa33a9c4fe448
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604925"
---
# <a name="full-text-search-has-changed-since-sql-server-2008"></a><span data-ttu-id="d5742-102">La recherche en texte intégral a été modifiée dans SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="d5742-102">Full-Text Search has changed since SQL Server 2008</span></span>
  <span data-ttu-id="d5742-103">Le Conseiller de mise à niveau a détecté que la fonctionnalité de recherche en texte intégral va être mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="d5742-103">Upgrade Advisor detected that full-text search is going to be upgraded.</span></span> <span data-ttu-id="d5742-104">De nombreux paramètres et options de recherche en texte intégral ont changé.</span><span class="sxs-lookup"><span data-stu-id="d5742-104">Many full-text search options and settings have changed.</span></span> <span data-ttu-id="d5742-105">Par conséquent, lorsque vous effectuez une mise à niveau vers la recherche en texte intégral [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], vous pourriez avoir besoin de modifier quelques-uns de vos paramètres.</span><span class="sxs-lookup"><span data-stu-id="d5742-105">Therefore, when you upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Full-Text Search, some of your settings might need modification.</span></span>  
  
## <a name="component"></a><span data-ttu-id="d5742-106">Composant</span><span class="sxs-lookup"><span data-stu-id="d5742-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="d5742-107">Description</span><span class="sxs-lookup"><span data-stu-id="d5742-107">Description</span></span>  
 <span data-ttu-id="d5742-108">Plusieurs fonctions, paramètres et objets de la recherche en texte intégral ont été modifiés depuis [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] et beaucoup de vos paramètres existants ne seront pas maintenus à l'issue de la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="d5742-108">Several full-text search features, settings and objects have been modified since [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and many of your existing settings will not be maintained when you upgrade.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="d5742-109">Action corrective</span><span class="sxs-lookup"><span data-stu-id="d5742-109">Corrective Action</span></span>  
 <span data-ttu-id="d5742-110">Nous recommandons également de consulter la documentation de recherche en texte intégral dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour les modifications avec rupture et les meilleures pratiques recommandées lorsque vous effectuez une mise à niveau vers [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5742-110">We also recommend reviewing full-text search documentation in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online for breaking changes and best practices when you upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="d5742-111">Ressources externes</span><span class="sxs-lookup"><span data-stu-id="d5742-111">External Resources</span></span>  
 [<span data-ttu-id="d5742-112">Compatibilité descendante de la recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="d5742-112">Full-Text Search Backward Compatibility</span></span>](../../../2014/database-engine/full-text-search-backward-compatibility.md)  
  
 [<span data-ttu-id="d5742-113">Mise à niveau de la fonction de recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="d5742-113">Full-Text Search Upgrade</span></span>](https://go.microsoft.com/fwlink/?LinkId=112291)  
  
 [<span data-ttu-id="d5742-114">Modifications importantes apportées à la recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="d5742-114">Breaking Changes to Full-Text Search</span></span>](../../../2014/database-engine/breaking-changes-to-full-text-search.md)  
  
  
