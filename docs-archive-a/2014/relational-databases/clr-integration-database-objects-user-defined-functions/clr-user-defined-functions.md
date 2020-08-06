---
title: Fonctions CLR définies par l’utilisateur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- building database objects [CLR integration], user-defined functions
- functions [CLR integration]
- common language runtime [SQL Server], user-defined functions
- database objects [CLR integration], user-defined functions
- user-defined functions [CLR integration]
ms.assetid: 6f7491f1-9a46-4146-ae09-056248634de2
author: rothja
ms.author: jroth
ms.openlocfilehash: ba7a4a983ec0cb36ef0fd79df44491f7f23f7648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612404"
---
# <a name="clr-user-defined-functions"></a><span data-ttu-id="d3c6d-102">Fonctions CLR définies par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="d3c6d-102">CLR User-Defined Functions</span></span>
  <span data-ttu-id="d3c6d-103">Les fonctions définies par l'utilisateur sont des routines qui acceptent des paramètres, effectuent des calculs ou d'autres actions et retournent un résultat.</span><span class="sxs-lookup"><span data-stu-id="d3c6d-103">User-defined functions are routines that can take parameters, perform calculations or other actions, and return a result.</span></span> <span data-ttu-id="d3c6d-104">Dans [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], vous pouvez écrire des fonctions définies par l'utilisateur dans un langage de programmation [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework, tel que [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET ou [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="d3c6d-104">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], you can write user-defined functions in any [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework programming language, such as [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C#.</span></span>  
  
 <span data-ttu-id="d3c6d-105">Il existe deux types de fonctions : fonction scalaire, qui retourne une valeur unique, et fonction table, qui retourne un ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="d3c6d-105">There are two types of functions: scalar, which returns a single value, and table-valued, which returns a set of rows.</span></span>  
  
 <span data-ttu-id="d3c6d-106">Le tableau suivant décrit les rubriques de cette section.</span><span class="sxs-lookup"><span data-stu-id="d3c6d-106">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="d3c6d-107">Fonctions scalaires CLR</span><span class="sxs-lookup"><span data-stu-id="d3c6d-107">CLR Scalar-Valued Functions</span></span>](clr-scalar-valued-functions.md)  
 <span data-ttu-id="d3c6d-108">Couvre les spécifications d'implémentation et des exemples de fonctions scalaires.</span><span class="sxs-lookup"><span data-stu-id="d3c6d-108">Covers implementation requirements and examples of scalar-valued functions.</span></span>  
  
 [<span data-ttu-id="d3c6d-109">Fonctions table CLR</span><span class="sxs-lookup"><span data-stu-id="d3c6d-109">CLR Table-Valued Functions</span></span>](clr-table-valued-functions.md)  
 <span data-ttu-id="d3c6d-110">Explique comment implémenter et utiliser les fonctions table, ainsi que les différences entre les fonctions table [!INCLUDE[tsql](../../includes/tsql-md.md)] et les fonctions table du CLR.</span><span class="sxs-lookup"><span data-stu-id="d3c6d-110">Discusses how to implement and use table-valued functions (TVFs), as well as differences between [!INCLUDE[tsql](../../includes/tsql-md.md)] and common language runtime (CLR) TVFs.</span></span>  
  
 [<span data-ttu-id="d3c6d-111">Agrégats CLR définis par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="d3c6d-111">CLR User-Defined Aggregates</span></span>](clr-user-defined-aggregates.md)  
 <span data-ttu-id="d3c6d-112">Décrit comment implémenter et utiliser les agrégats définis par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d3c6d-112">Describes how to implement and use user-defined aggregates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3c6d-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d3c6d-113">See Also</span></span>  
 [<span data-ttu-id="d3c6d-114">Fonctions définies par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="d3c6d-114">User-Defined Functions</span></span>](../user-defined-functions/user-defined-functions.md)  
  
  
