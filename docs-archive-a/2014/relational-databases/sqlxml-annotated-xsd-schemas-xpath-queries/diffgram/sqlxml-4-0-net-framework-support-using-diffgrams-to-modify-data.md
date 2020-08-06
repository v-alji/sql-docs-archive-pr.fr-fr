---
title: Utilisation de DiffGrams pour modifier des données dans SQLXML 4,0 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- data deletions [SQLXML]
- updating data [SQLXML]
- DiffGrams [SQLXML]
- modifying data [SQLXML]
- .NET Framework [SQLXML], DiffGrams
- XML [SQLXML]
- database modifications [SQLXML]
- data updates [SQLXML]
- data modifications [SQLXML]
- record insertion [SQLXML]
- SQLXML, DiffGrams
- deleting data
- record updates [SQLXML]
- record deletions [SQLXML]
ms.assetid: 48b8a8f9-f3af-404f-8c84-f4c3703364d9
author: rothja
ms.author: jroth
ms.openlocfilehash: cc2e24304679a7648f18148eb45f33b9bf719a9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610542"
---
# <a name="using-diffgrams-to-modify-data-in-sqlxml-40"></a><span data-ttu-id="a337c-102">Utilisation de DiffGrams pour modifier des données dans SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="a337c-102">Using DiffGrams to Modify Data in SQLXML 4.0</span></span>
  <span data-ttu-id="a337c-103">Le format DiffGram est introduit dans le composant **DataSet** du [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a337c-103">The DiffGram format is introduced in the **DataSet** component of the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span></span> <span data-ttu-id="a337c-104">Dans le .NET Framework, vous pouvez créer des DiffGrams et les utiliser pour modifier des données dans les tables d'une base de données Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a337c-104">Within the .NET Framework, you can create DiffGrams and use them to modify data in tables in a Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a337c-105">Cette section fournit présente brièvement les DiffGrams et donne des exemples illustrant leur utilisation.</span><span class="sxs-lookup"><span data-stu-id="a337c-105">This section provides a brief introduction to DiffGrams and examples of how to use them.</span></span> <span data-ttu-id="a337c-106">Elle suppose que vous connaissez bien les DiffGrams dans le .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a337c-106">It is assumed that you are familiar with DiffGrams in the .NET Framework.</span></span> <span data-ttu-id="a337c-107">Cette documentation porte principalement sur les problèmes liés aux DiffGrams spécifiques à SQLXML.</span><span class="sxs-lookup"><span data-stu-id="a337c-107">In this documentation, the primary focus is on DiffGram issues that are specific to SQLXML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a337c-108">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="a337c-108">In This Section</span></span>  
 [<span data-ttu-id="a337c-109">Introduction aux DiffGrams dans SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="a337c-109">Introduction to DiffGrams in SQLXML 4.0</span></span>](introduction-to-diffgrams-in-sqlxml-4-0.md)  
 <span data-ttu-id="a337c-110">Fournit des informations de base sur les Diffgrams.</span><span class="sxs-lookup"><span data-stu-id="a337c-110">Provides basic information about Diffgrams.</span></span>  
  
 [<span data-ttu-id="a337c-111">Exemples DiffGram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="a337c-111">DiffGram Examples &#40;SQLXML 4.0&#41;</span></span>](diffgram-examples-sqlxml-4-0.md)  
 <span data-ttu-id="a337c-112">Fournit des exemples d'utilisation de Diffgrams.</span><span class="sxs-lookup"><span data-stu-id="a337c-112">Provides examples of using Diffgrams.</span></span>  
  
 [<span data-ttu-id="a337c-113">Exécution d’un DiffGram à l’aide d’ADO &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="a337c-113">Executing a DiffGram by Using ADO &#40;SQLXML 4.0&#41;</span></span>](executing-a-diffgram-by-using-ado-sqlxml-4-0.md)  
 <span data-ttu-id="a337c-114">Fournit un exemple d'exécution d'un Diffgram avec des objets ADO (ActiveX Data Object).</span><span class="sxs-lookup"><span data-stu-id="a337c-114">Provides an example of executing a Diffgram with ActiveX Data Objects (ADO).</span></span>  
  
 [<span data-ttu-id="a337c-115">Exécution d'un DiffGram à l'aide des classes managées SQLXML</span><span class="sxs-lookup"><span data-stu-id="a337c-115">Executing a DiffGram by Using SQLXML Managed Classes</span></span>](../net-framework-classes/sqlxml-4-0-net-framework-support-managed-classes.md)  
 <span data-ttu-id="a337c-116">Fournit un exemple d'exécution d'un Diffgram avec des classes managées SQLXML.</span><span class="sxs-lookup"><span data-stu-id="a337c-116">Provides an example of executing a Diffgram with SQLXML Managed Classes.</span></span>  
  
  
