---
title: Classes managées SQLXML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- .NET Framework [SQLXML], Managed Classes
- SQL Server .NET Data Provider
- Managed Classes [SQLXML], about managed classes
- providers [SQLXML], SQL Server .NET Data Provider
- data providers [SQLXML], SQL Server .NET Data Provider
- Managed Classes [SQLXML]
- XML [SQLXML]
- SQLXML Managed Classes
- providers [SQLXML], SQLXML Managed Classes
- data providers [SQLXML], SQLXML Managed Classes
- SQLXML, Managed Classes
ms.assetid: 73a5faeb-dabf-4895-acb5-a9651b646065
author: rothja
ms.author: jroth
ms.openlocfilehash: bb8d2d4f2d2fc512901e4ad37f0e46cf696b9475
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599857"
---
# <a name="sqlxml-managed-classes"></a><span data-ttu-id="1c364-102">classes managées SQLXML</span><span class="sxs-lookup"><span data-stu-id="1c364-102">SQLXML Managed Classes</span></span>
  <span data-ttu-id="1c364-103">Les classes managées [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML expose les fonctionnalités de SQLXML 4.0 à l'intérieur de [!INCLUDE[msCoName](../../../includes/msconame-md.md)].NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1c364-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML Managed Classes exposes the functionality of SQLXML 4.0 inside the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span></span> <span data-ttu-id="1c364-104">Avec les classes managées SQLXML, vous pouvez écrire une application C# pour accéder aux données XML à partir d'une instance [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], placer les données dans l'environnement du .NET Framework, traiter les données et retourner les mises à jour à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] comme DiffGram pour qu'elles soient appliquées.</span><span class="sxs-lookup"><span data-stu-id="1c364-104">With SQLXML Managed Classes, you can write a C# application to access XML data from an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], bring the data into the .NET Framework environment, process the data, and send the updates back to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as a DiffGram to apply the updates.</span></span> <span data-ttu-id="1c364-105">Vous devez utiliser un schéma de mappage lors de l'application des mises à jour à une base de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à l'aide des classes managées SQLXML.</span><span class="sxs-lookup"><span data-stu-id="1c364-105">You must use a mapping schema when applying updates to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database using SQLXML Managed Classes.</span></span> <span data-ttu-id="1c364-106">Pour obtenir un exemple fonctionnel, consultez [accès à la fonctionnalité SQLXML dans l’environnement .net](accessing-sqlxml-functionality-in-the-net-environment.md).</span><span class="sxs-lookup"><span data-stu-id="1c364-106">For a working sample, see [Accessing SQLXML Functionality in the .NET Environment](accessing-sqlxml-functionality-in-the-net-environment.md).</span></span>  
  
 <span data-ttu-id="1c364-107">Pour utiliser les classes managées SQLXML avec SQLXML 4.0, vous devez installer Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1c364-107">To use the SQLXML Managed Classes with SQLXML 4.0, you must install Microsoft Visual Studio.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1c364-108">Le .NET Framework inclut le fournisseur de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .NET.</span><span class="sxs-lookup"><span data-stu-id="1c364-108">The .NET Framework includes the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .NET Data Provider.</span></span> <span data-ttu-id="1c364-109">Ce fournisseur peut être utilisé pour accéder à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à partir de l'environnement .NET ; toutefois, il ne peut gérer que les requêtes SQL traditionnelles (autrement dit, les requêtes de base de données relationnelle à l'exception des requêtes FOR XML).</span><span class="sxs-lookup"><span data-stu-id="1c364-109">This provider can be used to access [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] from the .NET environment; however, it can handle only traditional SQL queries (that is, relational database queries with the exception of FOR XML queries).</span></span> <span data-ttu-id="1c364-110">Vous ne pouvez pas exécuter les modèles XML ou les requêtes XPath côté serveur dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c364-110">You cannot execute XML templates or the server-side XPath queries in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1c364-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="1c364-111">In This Section</span></span>  
 [<span data-ttu-id="1c364-112">Modèle objet de classes managées SQLXML</span><span class="sxs-lookup"><span data-stu-id="1c364-112">SQLXML Managed Classes Object Model</span></span>](../../../database-engine/dev-guide/sqlxml-managed-classes-object-model.md)  
 <span data-ttu-id="1c364-113">Documente les classes managées SQLXML, ainsi que leurs propriétés et leurs méthodes.</span><span class="sxs-lookup"><span data-stu-id="1c364-113">Documents SQLXML Managed Classes and their properties and methods.</span></span>  
  
 [<span data-ttu-id="1c364-114">Utilisation des classes managées SQLXML</span><span class="sxs-lookup"><span data-stu-id="1c364-114">Using the SQLXML Managed Classes</span></span>](sqlxml-4-0-net-framework-support-managed-classes.md)  
 <span data-ttu-id="1c364-115">Fournit des exemples d'utilisation des classes managées SQLXML.</span><span class="sxs-lookup"><span data-stu-id="1c364-115">Provides examples of using SQLXML Managed Classes.</span></span>  
  
  
