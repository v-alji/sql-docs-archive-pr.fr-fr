---
title: MSSQLSERVER_11409 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 11409 (Database Engine error)
ms.assetid: 99b71a1c-a72d-4ca9-9d00-4230c9042ba5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e4249e13a3530f69978c78f2e2ca6e4583eed46a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600987"
---
# <a name="mssqlserver_11409"></a><span data-ttu-id="73ff3-102">MSSQLSERVER_11409</span><span class="sxs-lookup"><span data-stu-id="73ff3-102">MSSQLSERVER_11409</span></span>
    
## <a name="details"></a><span data-ttu-id="73ff3-103">Détails</span><span class="sxs-lookup"><span data-stu-id="73ff3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="73ff3-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="73ff3-104">Product Name</span></span>|<span data-ttu-id="73ff3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="73ff3-105">SQL Server</span></span>|  
|<span data-ttu-id="73ff3-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="73ff3-106">Event ID</span></span>|<span data-ttu-id="73ff3-107">11409</span><span class="sxs-lookup"><span data-stu-id="73ff3-107">11409</span></span>|  
|<span data-ttu-id="73ff3-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="73ff3-108">Event Source</span></span>|<span data-ttu-id="73ff3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="73ff3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="73ff3-110">Composant</span><span class="sxs-lookup"><span data-stu-id="73ff3-110">Component</span></span>|<span data-ttu-id="73ff3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="73ff3-111">SQLEngine</span></span>|  
|<span data-ttu-id="73ff3-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="73ff3-112">Symbolic Name</span></span>|<span data-ttu-id="73ff3-113">ALTERCOL_COLSET_DROP</span><span class="sxs-lookup"><span data-stu-id="73ff3-113">ALTERCOL_COLSET_DROP</span></span>|  
|<span data-ttu-id="73ff3-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="73ff3-114">Message Text</span></span>|<span data-ttu-id="73ff3-115">Impossible de supprimer le jeu de colonnes '%.\*ls' dans la table '%.\*ls', car celle-ci contient plus de 1 025 colonnes.</span><span class="sxs-lookup"><span data-stu-id="73ff3-115">Cannot drop column set '%.\*ls' in table '%.\*ls' because the table contains more than 1025 columns.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="73ff3-116">Explication</span><span class="sxs-lookup"><span data-stu-id="73ff3-116">Explanation</span></span>  
 <span data-ttu-id="73ff3-117">Les tables peuvent contenir un maximum de 1 024 colonnes non désignées en tant que colonnes éparses ou calculées.</span><span class="sxs-lookup"><span data-stu-id="73ff3-117">Tables can contain a maximum of 1024 columns that are not designated as sparse, or computed.</span></span> <span data-ttu-id="73ff3-118">Lorsqu'une table dépasse 1 024 colonnes en raison de colonnes éparses, il convient de définir un jeu de colonnes pour la table en question.</span><span class="sxs-lookup"><span data-stu-id="73ff3-118">When sparse columns cause the table to exceed 1024 columns, a column set must be defined for the table.</span></span> <span data-ttu-id="73ff3-119">La table référencée comporte plus de 1 024 colonnes et vous avez essayé de supprimer le jeu de colonnes.</span><span class="sxs-lookup"><span data-stu-id="73ff3-119">The table referenced has more than 1024 columns and you have attempted to remove the column set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="73ff3-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="73ff3-120">User Action</span></span>  
 <span data-ttu-id="73ff3-121">Étant donné le nombre actuel de colonnes dans la table, vous devez conserver le jeu de colonnes.</span><span class="sxs-lookup"><span data-stu-id="73ff3-121">With the current columns in the table, you must retain the column set.</span></span>  
  
 <span data-ttu-id="73ff3-122">Pour supprimer le jeu de colonnes, vous devez au préalable supprimer de la table un nombre de colonnes qui vous permettra de réduire leur nombre à 1 024.</span><span class="sxs-lookup"><span data-stu-id="73ff3-122">To remove the column set, first remove columns from the table, until you have no more than 1024 columns.</span></span> <span data-ttu-id="73ff3-123">Vous pourrez alors supprimer le jeu de colonnes.</span><span class="sxs-lookup"><span data-stu-id="73ff3-123">Then, you can remove the column set.</span></span>  
  
  
