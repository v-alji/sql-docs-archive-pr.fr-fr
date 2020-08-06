---
title: MSSQLSERVER_2508 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2508 (Database Engine error)
ms.assetid: c37d40e5-c665-4d66-a727-5cb845634fcc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 11dd1c72c8cae868b7ebcb02e72ef0db81aeafe2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699641"
---
# <a name="mssqlserver_2508"></a><span data-ttu-id="24ec6-102">MSSQLSERVER_2508</span><span class="sxs-lookup"><span data-stu-id="24ec6-102">MSSQLSERVER_2508</span></span>
    
## <a name="details"></a><span data-ttu-id="24ec6-103">Détails</span><span class="sxs-lookup"><span data-stu-id="24ec6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="24ec6-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="24ec6-104">Product Name</span></span>|<span data-ttu-id="24ec6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="24ec6-105">SQL Server</span></span>|  
|<span data-ttu-id="24ec6-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="24ec6-106">Event ID</span></span>|<span data-ttu-id="24ec6-107">2508</span><span class="sxs-lookup"><span data-stu-id="24ec6-107">2508</span></span>|  
|<span data-ttu-id="24ec6-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="24ec6-108">Event Source</span></span>|<span data-ttu-id="24ec6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="24ec6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="24ec6-110">Composant</span><span class="sxs-lookup"><span data-stu-id="24ec6-110">Component</span></span>|<span data-ttu-id="24ec6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="24ec6-111">SQLEngine</span></span>|  
|<span data-ttu-id="24ec6-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="24ec6-112">Symbolic Name</span></span>|<span data-ttu-id="24ec6-113">DBCC_OUT_OF_DATE_PAGE_OR_ROW_COUNT</span><span class="sxs-lookup"><span data-stu-id="24ec6-113">DBCC_OUT_OF_DATE_PAGE_OR_ROW_COUNT</span></span>|  
|<span data-ttu-id="24ec6-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="24ec6-114">Message Text</span></span>|<span data-ttu-id="24ec6-115">Le nombre %.\*ls pour l’objet « %.\*ls », ID d’index %d, ID de partition %I64d, ID d’unité d’allocation %I64d (type %.\*ls) est incorrect.</span><span class="sxs-lookup"><span data-stu-id="24ec6-115">The %.\*ls count for object "%.\*ls", index ID %d, partition ID %I64d, alloc unit ID %I64d (type %.\*ls) is incorrect.</span></span> <span data-ttu-id="24ec6-116">Exécutez DBCC UPDATEUSAGE.</span><span class="sxs-lookup"><span data-stu-id="24ec6-116">Run DBCC UPDATEUSAGE.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="24ec6-117">Explication</span><span class="sxs-lookup"><span data-stu-id="24ec6-117">Explanation</span></span>  
 <span data-ttu-id="24ec6-118">Dans les versions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] antérieures à [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], les valeurs du nombre de lignes de table et d'index et du nombre de pages peuvent être incorrectes.</span><span class="sxs-lookup"><span data-stu-id="24ec6-118">In versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], the values for the table and index row counts and page counts can become incorrect.</span></span> <span data-ttu-id="24ec6-119">Les bases de données créées avec des versions antérieures à [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] peuvent contenir des nombres incorrects.</span><span class="sxs-lookup"><span data-stu-id="24ec6-119">Databases that were created on versions prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] may contain incorrect counts.</span></span> <span data-ttu-id="24ec6-120">DBCC CHECKDB a été amélioré pour détecter ces erreurs et retourne ce message d'avertissement lorsque l'erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="24ec6-120">DBCC CHECKDB has been enhanced to detect these errors and returns this warning message when the error encountered.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="24ec6-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="24ec6-121">User Action</span></span>  
 <span data-ttu-id="24ec6-122">Exécutez DBCC UPDATEUSAGE sur l'objet ou l'index spécifié ou sur la base de données qui contient l'objet pour corriger les nombres non valides.</span><span class="sxs-lookup"><span data-stu-id="24ec6-122">Run DBCC UPDATEUSAGE against the specified object or index, or against the database in which the object is contained to correct the invalid counts.</span></span>  
  
  
