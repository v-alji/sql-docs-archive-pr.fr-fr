---
title: Agrégats CLR définis par l’utilisateur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- aggregate functions [CLR integration]
- custom aggregates [CLR integration]
- calculations [CLR integration]
- user-defined functions [CLR integration]
ms.assetid: bad9b7e8-5967-4afa-8dc8-6d840faf9372
author: rothja
ms.author: jroth
ms.openlocfilehash: d1ef5d07fe082d0eeb2c3484d6e99572d8fc80e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610687"
---
# <a name="clr-user-defined-aggregates"></a><span data-ttu-id="99c6a-102">Agrégats CLR définis par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="99c6a-102">CLR User-Defined Aggregates</span></span>
  <span data-ttu-id="99c6a-103">Les fonctions d’agrégation effectuent un calcul sur un ensemble de valeurs et renvoient une valeur unique.</span><span class="sxs-lookup"><span data-stu-id="99c6a-103">Aggregate functions perform a calculation on a set of values and return a single value.</span></span> <span data-ttu-id="99c6a-104">Traditionnellement, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a pris en charge uniquement les fonctions d’agrégation intégrées, telles que `SUM` ou `MAX` , qui opèrent sur un ensemble de valeurs scalaires d’entrée et génèrent une valeur d’agrégation unique à partir de cet ensemble.</span><span class="sxs-lookup"><span data-stu-id="99c6a-104">Traditionally, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has supported only built-in aggregate functions, such as `SUM` or `MAX`, that operate on a set of input scalar values and generate a single aggregate value from that set.</span></span> <span data-ttu-id="99c6a-105">L'intégration de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avec le CLR (Common Language Runtime) de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework permet à présent aux développeurs de créer des fonctions d'agrégation personnalisées en code managé et de mettre ces fonctions à la disposition de [!INCLUDE[tsql](../../includes/tsql-md.md)] ou d'un autre code managé.</span><span class="sxs-lookup"><span data-stu-id="99c6a-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] integration with the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework common language runtime (CLR) now allows developers to create custom aggregate functions in managed code, and to make these functions accessible to [!INCLUDE[tsql](../../includes/tsql-md.md)] or other managed code.</span></span>  
  
 <span data-ttu-id="99c6a-106">Le tableau suivant décrit les rubriques de cette section.</span><span class="sxs-lookup"><span data-stu-id="99c6a-106">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="99c6a-107">Conditions requises pour les agrégats CLR définis par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="99c6a-107">Requirements for CLR User-Defined Aggregates</span></span>](clr-user-defined-aggregates-requirements.md)  
 <span data-ttu-id="99c6a-108">Fournit une vue d'ensemble de la configuration requise pour l'implémentation des fonctions d'agrégation définies par l'utilisateur du CLR.</span><span class="sxs-lookup"><span data-stu-id="99c6a-108">Provides an overview of the requirements for implementing CLR user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="99c6a-109">Appel de fonctions d'agrégation CLR définies par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="99c6a-109">Invoking CLR User-Defined Aggregate Functions</span></span>](clr-user-defined-aggregate-invoking-functions.md)  
 <span data-ttu-id="99c6a-110">Explique comment appeler des agrégats définis par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="99c6a-110">Explains how to invoke user-defined aggregates.</span></span>  
  
  
