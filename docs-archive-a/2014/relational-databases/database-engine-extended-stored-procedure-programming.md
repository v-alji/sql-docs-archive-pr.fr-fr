---
title: Programmation de procédure stockée étendue de moteur de base de données | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], programming
- stored procedures [SQL Server], extended
- Database Engine [SQL Server], stored procedures
- macros [SQL Server]
- Extended Stored Procedure API [SQL Server]
ms.assetid: 158a6765-0542-4e84-b5ab-f173d946ef5e
author: rothja
ms.author: jroth
ms.openlocfilehash: fecb8f996ddfcaede83cdb330e9c82bffdce5819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614117"
---
# <a name="database-engine-extended-stored-procedure-programming"></a><span data-ttu-id="613fd-102">Programmation de procédure stockée étendue de moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="613fd-102">Database Engine Extended Stored Procedure Programming</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="613fd-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="613fd-103">Use CLR Integration instead.</span></span> <span data-ttu-id="613fd-104">Pour plus d’informations, consultez [Concepts de programmation pour l’intégration du CLR &#40;Common Language Runtime&#41;](clr-integration/common-language-runtime-clr-integration-programming-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="613fd-104">For more information, see [Common Language Runtime &#40;CLR&#41; Integration Programming Concepts](clr-integration/common-language-runtime-clr-integration-programming-concepts.md).</span></span>  
  
 <span data-ttu-id="613fd-105">L' [!INCLUDE[msCoName](../includes/msconame-md.md)] API de procédure stockée étendue fournit une interface de programmation d’applications (API) basée sur un serveur pour étendre les [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="613fd-105">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Extended Stored Procedure API provides a server-based application programming interface (API) for extending [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] functionality.</span></span> <span data-ttu-id="613fd-106">L'API est constituée de fonctions C et C++ et de macros permettant de générer des applications dans les catégories suivantes : procédures stockées étendues et applications de passerelle.</span><span class="sxs-lookup"><span data-stu-id="613fd-106">The API consists of C and C++ functions and macros used to build applications in the following categories: extended stored procedures and gateway applications.</span></span>  
  
 <span data-ttu-id="613fd-107">Les procédures stockées étendues vous permettent de créer vos propres routines externes dans un langage de programmation comme le langage C. Elles apparaissent aux utilisateurs comme des procédures stockées standard et s’exécutent de la même façon.</span><span class="sxs-lookup"><span data-stu-id="613fd-107">Extended stored procedures allow you to create your own external routines in a programming language such as C. The extended stored procedures appear to users as typical stored procedures and are executed in the same way.</span></span> <span data-ttu-id="613fd-108">Des paramètres peuvent être passés à des procédures stockées étendues, qui peuvent retourner des résultats et un état.</span><span class="sxs-lookup"><span data-stu-id="613fd-108">Parameters can be passed to extended stored procedures, and they can return results and return status.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="613fd-109">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="613fd-109">In This Section</span></span>  
 [<span data-ttu-id="613fd-110">Programmation de procédures stockées étendues</span><span class="sxs-lookup"><span data-stu-id="613fd-110">Programming Extended Stored Procedures</span></span>](extended-stored-procedures-programming/database-engine-extended-stored-procedures-programming.md)  
 <span data-ttu-id="613fd-111">Explique comment créer, gérer et utiliser des procédures stockées étendues.</span><span class="sxs-lookup"><span data-stu-id="613fd-111">Explains how to create, manage, and use extended stored procedures.</span></span>  
  
 [<span data-ttu-id="613fd-112">Guide de référence du programmeur sur les procédures stockées étendues</span><span class="sxs-lookup"><span data-stu-id="613fd-112">Extended Stored Procedures Programmer's Reference</span></span>](extended-stored-procedures-reference/database-engine-extended-stored-procedures-reference.md)  
 <span data-ttu-id="613fd-113">Contient des rubriques de référence pour l'API de procédure stockée étendue.</span><span class="sxs-lookup"><span data-stu-id="613fd-113">Contains reference topics for the Extended Stored Procedure API.</span></span>  
  
  
