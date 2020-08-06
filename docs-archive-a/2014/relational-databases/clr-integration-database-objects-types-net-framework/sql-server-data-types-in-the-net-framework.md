---
title: SQL Server des types de données dans le .NET Framework | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- System.Data library
- System.Data.SqlTypes namespace
- data types [CLR integration]
- SqlTypes library
- database objects [CLR integration], data types
- common language runtime [SQL Server], data types
- building database objects [CLR integration], data types
- mapping data types [CLR integration]
ms.assetid: c70d3ffe-2c32-45a5-849b-ef113dda09b9
author: rothja
ms.author: jroth
ms.openlocfilehash: fe0ed680e7050c58738301256575e4138f21276f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709631"
---
# <a name="sql-server-data-types-in-the-net-framework"></a><span data-ttu-id="ef907-102">Types de données SQL Server dans le .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ef907-102">SQL Server Data Types in the .NET Framework</span></span>
  <span data-ttu-id="ef907-103">La bibliothèque `SqlTypes` fait partie de la bibliothèque de classes de base de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ef907-103">The `SqlTypes` library is part of the base class library of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span></span> <span data-ttu-id="ef907-104">Elle est conçue pour fournir des types de données avec les mêmes sémantique et précision que celles figurant dans la base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef907-104">It is designed to provide data types with the same semantics and precision as those found in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="ef907-105">Cette rubrique décrit la nouvelle sémantique aux programmeurs .NET Framework et introduit les types implémentés dans l'espace de noms `System.Data.SqlTypes` qui est inclus dans la bibliothèque `System.Data`.</span><span class="sxs-lookup"><span data-stu-id="ef907-105">This topic describes the new semantics to .NET Framework programmers, and introduces the types implemented in the `System.Data.SqlTypes` namespace that is included in the `System.Data` library.</span></span>  
  
 <span data-ttu-id="ef907-106">Le tableau ci-dessous répertorie les rubriques de cette section.</span><span class="sxs-lookup"><span data-stu-id="ef907-106">This following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="ef907-107">Possibilité de valeur Null et comparaisons logiques de trois valeurs</span><span class="sxs-lookup"><span data-stu-id="ef907-107">Nullability and Three-Value Logic Comparisons</span></span>](nullability-and-three-value-logic-comparisons.md)  
 <span data-ttu-id="ef907-108">Explique comment les valeurs NULL sont traitées avec les types de données d'intégration CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="ef907-108">Discusses how NULL values are handled with common language runtime (CLR) integration data types.</span></span>  
  
 [<span data-ttu-id="ef907-109">Classement et types de données de l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="ef907-109">Collation and CLR Integration Data Types</span></span>](collation-and-clr-integration-data-types.md)  
 <span data-ttu-id="ef907-110">Décrit comment les classements sont traités avec l'intégration du CLR.</span><span class="sxs-lookup"><span data-stu-id="ef907-110">Describes how collations are handled with CLR integration.</span></span>  
  
 [<span data-ttu-id="ef907-111">Gestion des paramètres de&#41; Large Object &#40;LOB dans le CLR</span><span class="sxs-lookup"><span data-stu-id="ef907-111">Handling Large Object &#40;LOB&#41; Parameters in the CLR</span></span>](handling-large-object-lob-parameters-in-the-clr.md)  
 <span data-ttu-id="ef907-112">Décrit comment transmettre des types LOB entre [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et le CLR.</span><span class="sxs-lookup"><span data-stu-id="ef907-112">Describes how to pass LOB types between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the CLR.</span></span>  
  
 [<span data-ttu-id="ef907-113">Mappage des données de paramètres CLR</span><span class="sxs-lookup"><span data-stu-id="ef907-113">Mapping CLR Parameter Data</span></span>](mapping-clr-parameter-data.md)  
 <span data-ttu-id="ef907-114">Affiche les mappages des types de données entre [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], l'intégration du CLR et le .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ef907-114">Shows data type mappings between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], CLR integration, and the .NET Framework.</span></span>  
  
  
