---
title: Formats de données numériques | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- integer data types [Integration Services]
- numeric data formats for fast parse
- locale-sensitive parsing [Integration Services]
- fast parse [Integration Services]
ms.assetid: fa3975ce-9d21-408a-857d-f85e30af27b0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cc54a331c3762e31ba9d9a431aaca7eda6374d8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605541"
---
# <a name="numeric-data-formats"></a><span data-ttu-id="1f590-102">Formats de données numériques</span><span class="sxs-lookup"><span data-stu-id="1f590-102">Numeric Data Formats</span></span>
  <span data-ttu-id="1f590-103">L'analyse rapide fournit un ensemble de routines simple, rapide et insensible aux paramètres régionaux pour l'analyse des données.</span><span class="sxs-lookup"><span data-stu-id="1f590-103">Fast parse provides a fast, simple, locale-insensitive set of routines for parsing data.</span></span> <span data-ttu-id="1f590-104">Elle prend en charge uniquement un ensemble limité de formats pour les types de données integer.</span><span class="sxs-lookup"><span data-stu-id="1f590-104">Fast parse supports only a limited set of formats for integer data types.</span></span>  
  
## <a name="integer-data-types"></a><span data-ttu-id="1f590-105">Types de données integer</span><span class="sxs-lookup"><span data-stu-id="1f590-105">Integer Data Types</span></span>  
 <span data-ttu-id="1f590-106">Les types de données integer fournis par [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sont DT_I1, DT_UI1, DT_I2, DT_UI2, DT_I4, DT_UI4, DT_I8 et DT_UI8.</span><span class="sxs-lookup"><span data-stu-id="1f590-106">The integer data types that [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] provides are DT_I1, DT_UI1, DT_I2, DT_UI2, DT_I4, DT_UI4, DT_I8, and DT_UI8.</span></span> <span data-ttu-id="1f590-107">Pour plus d’informations, consultez [Types de données Integration Services](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="1f590-107">For more information, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="1f590-108">L'analyse rapide prend en charge les formats suivants pour les types de données integer :</span><span class="sxs-lookup"><span data-stu-id="1f590-108">Fast parse supports the following formats for integer data types:</span></span>  
  
-   <span data-ttu-id="1f590-109">Zéro ou plusieurs espaces de début et de fin ou taquets de tabulation.</span><span class="sxs-lookup"><span data-stu-id="1f590-109">Zero or more leading and trailing spaces or tab stops.</span></span> <span data-ttu-id="1f590-110">Par exemple, la valeur «  123  » est valide.</span><span class="sxs-lookup"><span data-stu-id="1f590-110">For example, the value "  123  " is valid.</span></span> <span data-ttu-id="1f590-111">Une valeur composée uniquement d'espaces est évaluée comme zéro.</span><span class="sxs-lookup"><span data-stu-id="1f590-111">A value that is all spaces evaluates to zero.</span></span>  
  
-   <span data-ttu-id="1f590-112">Un signe plus ou signe moins de début, ou ni l'un ni l'autre.</span><span class="sxs-lookup"><span data-stu-id="1f590-112">A leading plus sign, minus sign, or neither.</span></span> <span data-ttu-id="1f590-113">Par exemple, les valeurs +123, -123 et 123 sont valides.</span><span class="sxs-lookup"><span data-stu-id="1f590-113">For example, the values +123, -123, and 123 are valid.</span></span>  
  
-   <span data-ttu-id="1f590-114">Un ou plusieurs chiffres hindou-arabe (0-9).</span><span class="sxs-lookup"><span data-stu-id="1f590-114">One or more Hindu-Arabic numerals (0-9).</span></span> <span data-ttu-id="1f590-115">Par exemple, la valeur 345 est valide.</span><span class="sxs-lookup"><span data-stu-id="1f590-115">For example, the value 345 is valid.</span></span> <span data-ttu-id="1f590-116">Aucun autre chiffre linguistique n'est pris en charge.</span><span class="sxs-lookup"><span data-stu-id="1f590-116">Other language numerals are not supported.</span></span>  
  
 <span data-ttu-id="1f590-117">Les formats de données non pris en charge sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="1f590-117">Non-supported data formats include the following:</span></span>  
  
-   <span data-ttu-id="1f590-118">Caractères spéciaux.</span><span class="sxs-lookup"><span data-stu-id="1f590-118">Special characters.</span></span> <span data-ttu-id="1f590-119">Par exemple, le symbole monétaire $ n'est pas pris en charge et la valeur $20 ne peut pas être analysée.</span><span class="sxs-lookup"><span data-stu-id="1f590-119">For example, the currency character $ is not supported, and the value $20 cannot be parsed.</span></span>  
  
-   <span data-ttu-id="1f590-120">Les caractères d'espaces blancs tels que les sauts de ligne, les retours chariot et les espaces insécables.</span><span class="sxs-lookup"><span data-stu-id="1f590-120">White-space characters such as line feed, carriage returns, and non-breaking spaces.</span></span> <span data-ttu-id="1f590-121">Par exemple, la valeur « 123» ne peut pas être analysée.</span><span class="sxs-lookup"><span data-stu-id="1f590-121">For example, the value " 123" cannot be parsed.</span></span>  
  
-   <span data-ttu-id="1f590-122">Les représentations hexadécimales d'entiers.</span><span class="sxs-lookup"><span data-stu-id="1f590-122">Hexadecimal representations of integers.</span></span> <span data-ttu-id="1f590-123">Par exemple, la valeur 2EE ne peut pas être analysée.</span><span class="sxs-lookup"><span data-stu-id="1f590-123">For example, the value 2EE cannot be parsed.</span></span>  
  
-   <span data-ttu-id="1f590-124">La représentation en notation scientifique d'entiers.</span><span class="sxs-lookup"><span data-stu-id="1f590-124">Scientific notation representation of integers.</span></span> <span data-ttu-id="1f590-125">Par exemple, la valeur 1E+10 ne peut pas être analysée.</span><span class="sxs-lookup"><span data-stu-id="1f590-125">For example, the value 1E+10 cannot be parsed.</span></span>  
  
 <span data-ttu-id="1f590-126">Les formats suivants sont des formats de données de sortie pour les entiers :</span><span class="sxs-lookup"><span data-stu-id="1f590-126">The following formats are output data formats for integers:</span></span>  
  
-   <span data-ttu-id="1f590-127">Un signe moins pour les nombres négatifs et rien pour les nombres positifs.</span><span class="sxs-lookup"><span data-stu-id="1f590-127">A minus sign for negative numbers and nothing for positive ones.</span></span>  
  
-   <span data-ttu-id="1f590-128">Aucun espace blanc.</span><span class="sxs-lookup"><span data-stu-id="1f590-128">No white spaces.</span></span>  
  
-   <span data-ttu-id="1f590-129">Un ou plusieurs chiffres hindou-arabe (0-9).</span><span class="sxs-lookup"><span data-stu-id="1f590-129">One or more Hindu-Arabic numerals (0-9).</span></span>  
  
  
