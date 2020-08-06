---
title: Troncation de données (SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- truncating data
- data truncation [Integration Services]
- expressions [Integration Services], data truncation
- truncate options [Integration Services]
ms.assetid: 02461e15-49ca-445b-abb3-5c369c283ec2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e0c4280c9eacd22ebf84bf1570d485de51cab09b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614183"
---
# <a name="data-truncation-ssis"></a><span data-ttu-id="73b55-102">Troncation de données (SSIS)</span><span class="sxs-lookup"><span data-stu-id="73b55-102">Data Truncation (SSIS)</span></span>
  <span data-ttu-id="73b55-103">Une expression peut accidentellement tronquer des données.</span><span class="sxs-lookup"><span data-stu-id="73b55-103">An expression may inadvertently cause data to be truncated.</span></span> <span data-ttu-id="73b55-104">La troncation peut se produire dans les circonstances suivantes :</span><span class="sxs-lookup"><span data-stu-id="73b55-104">Truncation can occur under the following circumstances:</span></span>  
  
-   <span data-ttu-id="73b55-105">Chaînes.</span><span class="sxs-lookup"><span data-stu-id="73b55-105">Strings.</span></span> <span data-ttu-id="73b55-106">Par exemple, la conversion de données de chaîne ayant pour type de données DT_WSTR en une chaîne de même longueur mesurée en caractères et de type de données DT_STR provoque une perte de données si la chaîne d'origine contient des caractères codés sur deux octets.</span><span class="sxs-lookup"><span data-stu-id="73b55-106">For example, translating string data with a DT_WSTR data type to the same length string, measured in characters, with a DT_STR data type causes data loss if the original string contains double-byte characters.</span></span>  
  
-   <span data-ttu-id="73b55-107">Chiffres significatifs.</span><span class="sxs-lookup"><span data-stu-id="73b55-107">Significant digits.</span></span> <span data-ttu-id="73b55-108">Par exemple, la conversion d'un entier d'un type de données DT_I4 en un type de données DT_I2, ou d'un entier non signé en un entier signé.</span><span class="sxs-lookup"><span data-stu-id="73b55-108">For example, casting an integer from a DT_I4 data type to a DT_I2 data type or an unsigned integer to a signed integer.</span></span>  
  
-   <span data-ttu-id="73b55-109">Chiffres non significatifs.</span><span class="sxs-lookup"><span data-stu-id="73b55-109">Insignificant digits.</span></span> <span data-ttu-id="73b55-110">Par exemple, la conversion d'un nombre réel d'un type de données DT_R8 en un type de données DT_R4, ou d'un entier d'un type de données DT_I4 en un type de données DT_R4.</span><span class="sxs-lookup"><span data-stu-id="73b55-110">For example, casting a real number from a DT_R8 to a DT_R4 or an integer from a DT_I4 data type to a DT_R4 data type.</span></span>  
  
 <span data-ttu-id="73b55-111">L'évaluateur d'expression identifie les conversions explicites pouvant provoquer une troncation et émet un avertissement lorsque l'expression est analysée.</span><span class="sxs-lookup"><span data-stu-id="73b55-111">The expression evaluator identifies explicit casts that may cause truncation and issues a warning when the expression is parsed.</span></span> <span data-ttu-id="73b55-112">Par exemple, l'évaluateur d'expression émet un avertissement si vous convertissez une chaîne de 30 caractères en une chaîne de 20 caractères.</span><span class="sxs-lookup"><span data-stu-id="73b55-112">For example, the expression evaluator warns you if a 30-character string is cast into a 20-character string.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73b55-113">La troncation n'est pas vérifiée à l'exécution ; les données sont tronquées sans que vous en soyez averti.</span><span class="sxs-lookup"><span data-stu-id="73b55-113">Truncation is not checked at run time; data is truncated without warning.</span></span> <span data-ttu-id="73b55-114">Toutefois, la plupart des transformations et des adaptateurs de données prennent en charge des sorties d'erreur pouvant gérer la disposition des lignes d'erreur.</span><span class="sxs-lookup"><span data-stu-id="73b55-114">However, most data adapters and transformations support error outputs that can handle the disposition of error rows.</span></span> <span data-ttu-id="73b55-115">Pour plus d’informations sur la gestion de la troncation des données, consultez [gestion des erreurs dans les données](../data-flow/error-handling-in-data.md).</span><span class="sxs-lookup"><span data-stu-id="73b55-115">For more information about handling truncation of data, see [Error Handling in Data](../data-flow/error-handling-in-data.md).</span></span>  
  
  
