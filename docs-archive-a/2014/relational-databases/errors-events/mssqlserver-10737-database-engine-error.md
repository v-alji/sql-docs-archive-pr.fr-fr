---
title: MSSQLSERVER_10737 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10737 (Database Engine error)
ms.assetid: 208af6ed-b271-4ab8-803e-7666025385c8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: df8a4de014552d3aca00b3eb244f7ff8df56756b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612396"
---
# <a name="mssqlserver_10737"></a><span data-ttu-id="e015e-102">MSSQLSERVER_10737</span><span class="sxs-lookup"><span data-stu-id="e015e-102">MSSQLSERVER_10737</span></span>
    
## <a name="details"></a><span data-ttu-id="e015e-103">Détails</span><span class="sxs-lookup"><span data-stu-id="e015e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e015e-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="e015e-104">Product Name</span></span>|<span data-ttu-id="e015e-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e015e-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e015e-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="e015e-106">Event ID</span></span>|<span data-ttu-id="e015e-107">10737</span><span class="sxs-lookup"><span data-stu-id="e015e-107">10737</span></span>|  
|<span data-ttu-id="e015e-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="e015e-108">Event Source</span></span>|<span data-ttu-id="e015e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e015e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e015e-110">Composant</span><span class="sxs-lookup"><span data-stu-id="e015e-110">Component</span></span>|<span data-ttu-id="e015e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e015e-111">SQLEngine</span></span>|  
|<span data-ttu-id="e015e-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="e015e-112">Symbolic Name</span></span>|<span data-ttu-id="e015e-113">REBUILD_PARTITION_ALL_NOT_SPECIFIED</span><span class="sxs-lookup"><span data-stu-id="e015e-113">REBUILD_PARTITION_ALL_NOT_SPECIFIED</span></span>|  
|<span data-ttu-id="e015e-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="e015e-114">Message Text</span></span>|<span data-ttu-id="e015e-115">Dans une instruction ALTER TABLE REBUILD ou ALTER INDEX REBUILD, lorsqu'une partition est spécifiée dans une clause DATA_COMPRESSION, PARTITION=ALL est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="e015e-115">In an ALTER TABLE REBUILD or ALTER INDEX REBUILD statement, when a partition is specified in a DATA_COMPRESSION clause, PARTITION=ALL must be specified.</span></span> <span data-ttu-id="e015e-116">La clause PARTITION=ALL permet d'imposer que toutes les partitions de la table ou de l'index soient régénérées, même si un seul sous-ensemble est spécifié dans la clause DATA_COMPRESSION.</span><span class="sxs-lookup"><span data-stu-id="e015e-116">The PARTITION=ALL clause is used to reinforce that all partitions of the table or index will be rebuilt, even if only a subset is specified in the DATA_COMPRESSION clause.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="e015e-117">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e015e-117">User Action</span></span>  
 <span data-ttu-id="e015e-118">Ajoutez la clause PARTITION=ALL à l'instruction ALTER TABLE ou ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="e015e-118">Add the PARTITION=ALL clause to the ALTER TABLE or ALTER INDEX statement.</span></span> <span data-ttu-id="e015e-119">Ou, pour reconstruire une partition spécifique, utilisez REBUILD PARTITION = \<partition-number-expr> WITH (DATA_COMPRESSION={ON | OFF}).</span><span class="sxs-lookup"><span data-stu-id="e015e-119">Or, to rebuild a specific partition, use REBUILD PARTITION = \<partition-number-expr> WITH (DATA_COMPRESSION={ON | OFF}).</span></span>  
  
  
