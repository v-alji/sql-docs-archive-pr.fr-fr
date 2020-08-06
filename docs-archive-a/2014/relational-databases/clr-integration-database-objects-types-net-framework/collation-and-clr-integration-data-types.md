---
title: Types de données d’intégration du classement et du CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- data types [CLR integration]
- parameter collation [CLR integration]
- collations [CLR integration]
ms.assetid: 6ebaed8e-2e2b-4f6d-bf4b-bc25452de441
author: rothja
ms.author: jroth
ms.openlocfilehash: 1a5b0367487aeb80355b8c5c976818e1b6c1ac04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709647"
---
# <a name="collation-and-clr-integration-data-types"></a><span data-ttu-id="3bd4a-102">Classement et types de données de l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="3bd4a-102">Collation and CLR Integration Data Types</span></span>
  <span data-ttu-id="3bd4a-103">Dans le [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], l'objet `CompareInfo` gère les classements.</span><span class="sxs-lookup"><span data-stu-id="3bd4a-103">In the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], the `CompareInfo` object handles collations.</span></span> <span data-ttu-id="3bd4a-104">Les interfaces de programmation d'applications (API) de chaîne du [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] utilisent la propriété `CompareInfo` associée à l'objet `CultureInfo` du thread courant pour effectuer les comparaisons de chaînes.</span><span class="sxs-lookup"><span data-stu-id="3bd4a-104">The [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] string application programming interfaces (APIs) use the `CompareInfo` property associated with the `CultureInfo` object of the current thread to perform string comparisons.</span></span> <span data-ttu-id="3bd4a-105">Le paramètre par défaut de l' `CultureInfo` objet est basé sur les paramètres [!INCLUDE[msCoName](../../includes/msconame-md.md)] régionaux Windows de l’ordinateur sur lequel [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s’exécute.</span><span class="sxs-lookup"><span data-stu-id="3bd4a-105">The default setting of the `CultureInfo` object is based on the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows locale setting for the computer on which [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span> <span data-ttu-id="3bd4a-106">Cela détermine la sémantique de comparaison par défaut, si aucune propriété `CultureInfo` explicite n'est spécifiée, pour les comparaisons de valeurs `System.String`.</span><span class="sxs-lookup"><span data-stu-id="3bd4a-106">This determines the default comparison semantics, if no explicit `CultureInfo` is specified, for comparisons of `System.String` values.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3bd4a-107">ne change pas explicitement la propriété `CompareInfo` en classement de la base de données ou du serveur.</span><span class="sxs-lookup"><span data-stu-id="3bd4a-107">does not explicitly change the `CompareInfo` property to the database or server collation.</span></span> <span data-ttu-id="3bd4a-108">Si besoin est, les utilisateurs doivent définir la propriété `CompareInfo` appropriée dans leurs routines.</span><span class="sxs-lookup"><span data-stu-id="3bd4a-108">If required, users must set the appropriate `CompareInfo` property in their routines.</span></span>  
  
## <a name="parameter-collation"></a><span data-ttu-id="3bd4a-109">Paramètre Collation</span><span class="sxs-lookup"><span data-stu-id="3bd4a-109">Parameter Collation</span></span>  
 <span data-ttu-id="3bd4a-110">Lorsque vous créez une routine CLR et qu'un paramètre d'une méthode CLR liée à la routine est de type `SQLString`, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] crée une instance du paramètre avec le classement par défaut de la base de données qui contient la routine d'appel.</span><span class="sxs-lookup"><span data-stu-id="3bd4a-110">When you create a common language runtime (CLR) routine, and a parameter of a CLR method bound to the routine is of type `SQLString`, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creates an instance of the parameter with the default collation of the database containing the calling routine.</span></span> <span data-ttu-id="3bd4a-111">Si un paramètre n'est pas un `SqlType` (par exemple, `String` au lieu de `SQLString`), les informations de classement de la base de données ne sont pas associées au paramètre.</span><span class="sxs-lookup"><span data-stu-id="3bd4a-111">If a parameter is not a `SqlType` (for example, `String` rather than `SQLString`), the collation information from the database is not associated with the parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bd4a-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3bd4a-112">See Also</span></span>  
 [<span data-ttu-id="3bd4a-113">Types de données SQL Server dans le .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3bd4a-113">SQL Server Data Types in the .NET Framework</span></span>](sql-server-data-types-in-the-net-framework.md)  
  
  
