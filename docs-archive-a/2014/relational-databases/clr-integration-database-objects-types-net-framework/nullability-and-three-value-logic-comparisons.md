---
title: Possibilité de valeur null et comparaisons logiques de trois valeurs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- precision [CLR integration]
- overflow detections [CLR integration]
- null values [CLR integration]
- three-value logic comparisons [CLR integration]
- data types [CLR integration]
- SqlBoolean data type
ms.assetid: 13da4c7f-1010-4b2d-a63c-c69b6bfd96f1
author: rothja
ms.author: jroth
ms.openlocfilehash: 7b8000c1c28d5a1d3d129b6e8d01c4ab2fbbbc7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709632"
---
# <a name="nullability-and-three-value-logic-comparisons"></a><span data-ttu-id="4fc0f-102">Possibilité de valeur Null et comparaisons logiques de trois valeurs</span><span class="sxs-lookup"><span data-stu-id="4fc0f-102">Nullability and Three-Value Logic Comparisons</span></span>
  <span data-ttu-id="4fc0f-103">Si vous avez une bonne connaissance des types de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vous trouverez une sémantique et une précision semblables dans l'espace de noms `System.Data.SqlTypes` dans le [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4fc0f-103">If you are familiar with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, you will find similar semantics and precision in the `System.Data.SqlTypes` namespace in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="4fc0f-104">Il existe toutefois certaines différences, dont les principales sont décrites dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="4fc0f-104">There are some differences, however, and this topic covers the most important of these differences.</span></span>  
  
## <a name="null-values"></a><span data-ttu-id="4fc0f-105">Valeurs Null</span><span class="sxs-lookup"><span data-stu-id="4fc0f-105">NULL Values</span></span>  
 <span data-ttu-id="4fc0f-106">L'une des principales différences entre les types de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et les types de données CLR (Common Language Runtime) natifs porte sur le fait que ceux-ci n'autorisent pas les valeurs Null, tandis que ceux-là fournissent une sémantique Null complète.</span><span class="sxs-lookup"><span data-stu-id="4fc0f-106">A primary difference between native common language runtime (CLR) data types and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types is that the former do not allow for NULL values, while the latter provide full NULL semantics.</span></span>  
  
 <span data-ttu-id="4fc0f-107">Les comparaisons sont affectées par les valeurs Null.</span><span class="sxs-lookup"><span data-stu-id="4fc0f-107">Comparisons are affected by NULL values.</span></span> <span data-ttu-id="4fc0f-108">Lors de la comparaison de deux valeurs x et y, si x ou y a la valeur Null, certaines comparaisons logiques évaluent à une valeur UNKNOWN plutôt que true ou false.</span><span class="sxs-lookup"><span data-stu-id="4fc0f-108">When comparing two values x and y, if either x or y is NULL, then some logical comparisons evaluate to an UNKNOWN value rather than true or false.</span></span>  
  
## <a name="sqlboolean-data-type"></a><span data-ttu-id="4fc0f-109">Type de données SqlBoolean</span><span class="sxs-lookup"><span data-stu-id="4fc0f-109">SqlBoolean Data Type</span></span>  
 <span data-ttu-id="4fc0f-110">L'espace de noms `System.Data.SqlTypes` introduit un type `SqlBoolean` pour représenter cette logique à 3 valeurs.</span><span class="sxs-lookup"><span data-stu-id="4fc0f-110">The `System.Data.SqlTypes` namespace introduces a `SqlBoolean` type to represent this 3-value logic.</span></span> <span data-ttu-id="4fc0f-111">Les comparaisons entre des `SqlTypes` retournent un type de valeur `SqlBoolean`.</span><span class="sxs-lookup"><span data-stu-id="4fc0f-111">Comparisons between any `SqlTypes` return a `SqlBoolean` value type.</span></span> <span data-ttu-id="4fc0f-112">La valeur UNKNOWN est représentée par la valeur Null du type `SqlBoolean`.</span><span class="sxs-lookup"><span data-stu-id="4fc0f-112">The UNKNOWN value is represented by the null value of the `SqlBoolean` type.</span></span> <span data-ttu-id="4fc0f-113">Les propriétés `IsTrue`, `IsFalse` et `IsNull` sont fournies afin de vérifier la valeur d'un type `SqlBoolean`.</span><span class="sxs-lookup"><span data-stu-id="4fc0f-113">The properties `IsTrue`, `IsFalse`, and `IsNull` are provided to check the value of a `SqlBoolean` type.</span></span>  
  
## <a name="operations-functions-and-null-values"></a><span data-ttu-id="4fc0f-114">Opérations, fonctions et valeurs Null</span><span class="sxs-lookup"><span data-stu-id="4fc0f-114">Operations, Functions, and NULL Values</span></span>  
 <span data-ttu-id="4fc0f-115">Tous les opérateurs arithmétiques (+,-, \* ,/,%), les opérateurs de bits (~, & et |) et la plupart des fonctions retournent Null si l’un des opérandes ou arguments de `SqlTypes` est null.</span><span class="sxs-lookup"><span data-stu-id="4fc0f-115">All arithmetic operators (+, -, \*, /, %), bitwise operators (~, &, and |), and most functions return NULL if any of the operands or arguments of `SqlTypes` are NULL.</span></span> <span data-ttu-id="4fc0f-116">La propriété `IsNull` retourne toujours une valeur true ou false.</span><span class="sxs-lookup"><span data-stu-id="4fc0f-116">The `IsNull` property always returns a true or false value.</span></span>  
  
## <a name="precision"></a><span data-ttu-id="4fc0f-117">Précision</span><span class="sxs-lookup"><span data-stu-id="4fc0f-117">Precision</span></span>  
 <span data-ttu-id="4fc0f-118">Les types de données décimaux dans le CLR [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] ont des valeurs maximales différentes de celles des types de données numériques et décimaux dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4fc0f-118">Decimal data types in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] CLR have different maximum values than those of the numeric and decimal data types in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4fc0f-119">De plus, dans le CLR [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], les types de données décimaux supposent la précision maximale.</span><span class="sxs-lookup"><span data-stu-id="4fc0f-119">In addition, in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] CLR decimal data types assume the maximum precision.</span></span> <span data-ttu-id="4fc0f-120">Dans le CLR pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], en revanche, `SqlDecimal` fournit les mêmes échelle et précision maximale, ainsi que la même sémantique que le type de données décimal dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4fc0f-120">In the CLR for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], however, `SqlDecimal` provides the same maximum precision and scale, and the same semantics as the decimal data type in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="overflow-detection"></a><span data-ttu-id="4fc0f-121">Détection de dépassement de capacité</span><span class="sxs-lookup"><span data-stu-id="4fc0f-121">Overflow Detection</span></span>  
 <span data-ttu-id="4fc0f-122">Dans le CLR [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], l'addition de deux très grands nombres peut ne pas lever d'exception.</span><span class="sxs-lookup"><span data-stu-id="4fc0f-122">In the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] CLR, the addition of two very large numbers may not throw an exception.</span></span> <span data-ttu-id="4fc0f-123">Au lieu de cela, si aucun opérateur de contrôle n'a été utilisé, le résultat retourné peut être « enveloppé » en tant qu'entier négatif.</span><span class="sxs-lookup"><span data-stu-id="4fc0f-123">Instead, if no check operator has been used, the returned result may "wrap around" as a negative integer.</span></span> <span data-ttu-id="4fc0f-124">Dans `System.Data.SqlTypes`, des exceptions sont levées pour toutes les erreurs de dépassement de capacité et de dépassement de précision et pour les erreurs de division par zéro.</span><span class="sxs-lookup"><span data-stu-id="4fc0f-124">In `System.Data.SqlTypes`, exceptions are thrown for all overflow and underflow errors, and divide-by-zero errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fc0f-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4fc0f-125">See Also</span></span>  
 [<span data-ttu-id="4fc0f-126">Types de données SQL Server dans le .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4fc0f-126">SQL Server Data Types in the .NET Framework</span></span>](sql-server-data-types-in-the-net-framework.md)  
  
  
