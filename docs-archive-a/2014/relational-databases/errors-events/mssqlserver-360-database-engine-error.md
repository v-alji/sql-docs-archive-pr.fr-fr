---
title: MSSQLSERVER_360 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 360 (Database Engine error)
ms.assetid: e2b7c1b2-3679-4206-9b25-6bd55ef96a2c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b30311d7f55231c1e7a6d5969d49c5d1bc07a848
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604026"
---
# <a name="mssqlserver_360"></a><span data-ttu-id="53b2a-102">MSSQLSERVER_360</span><span class="sxs-lookup"><span data-stu-id="53b2a-102">MSSQLSERVER_360</span></span>
    
## <a name="details"></a><span data-ttu-id="53b2a-103">Détails</span><span class="sxs-lookup"><span data-stu-id="53b2a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="53b2a-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="53b2a-104">Product Name</span></span>|<span data-ttu-id="53b2a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="53b2a-105">SQL Server</span></span>|  
|<span data-ttu-id="53b2a-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="53b2a-106">Event ID</span></span>|<span data-ttu-id="53b2a-107">360</span><span class="sxs-lookup"><span data-stu-id="53b2a-107">360</span></span>|  
|<span data-ttu-id="53b2a-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="53b2a-108">Event Source</span></span>|<span data-ttu-id="53b2a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="53b2a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="53b2a-110">Composant</span><span class="sxs-lookup"><span data-stu-id="53b2a-110">Component</span></span>|<span data-ttu-id="53b2a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="53b2a-111">SQLEngine</span></span>|  
|<span data-ttu-id="53b2a-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="53b2a-112">Symbolic Name</span></span>|<span data-ttu-id="53b2a-113">DML_UPDATE_SPARSE_AND_COLSET</span><span class="sxs-lookup"><span data-stu-id="53b2a-113">DML_UPDATE_SPARSE_AND_COLSET</span></span>|  
|<span data-ttu-id="53b2a-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="53b2a-114">Message Text</span></span>|<span data-ttu-id="53b2a-115">La liste de colonnes cibles d'une instruction INSERT, UPDATE ou MERGE ne peut pas contenir à la fois une colonne éparse et le jeu de colonnes qui contient cette colonne éparse.</span><span class="sxs-lookup"><span data-stu-id="53b2a-115">The target column list of an INSERT, UPDATE, or MERGE statement cannot contain both a sparse column and the column set that contains the sparse column.</span></span> <span data-ttu-id="53b2a-116">Réécrivez l'instruction de manière à inclure la colonne éparse ou le jeu de colonnes, mais pas les deux.</span><span class="sxs-lookup"><span data-stu-id="53b2a-116">Rewrite the statement to include either the sparse column or the column set, but not both.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="53b2a-117">Explication</span><span class="sxs-lookup"><span data-stu-id="53b2a-117">Explanation</span></span>  
 <span data-ttu-id="53b2a-118">Un jeu de colonnes est une représentation XML non typée qui associe certaines colonnes d’une table dans une sortie structurée.</span><span class="sxs-lookup"><span data-stu-id="53b2a-118">A column set is an untyped XML representation that combines some columns of a table into a structured output.</span></span> <span data-ttu-id="53b2a-119">Une tentative a été effectuée de modifier à la fois le jeu de colonnes et une colonne incluse dans le jeu de colonnes, provoquant ainsi deux références à la même colonne.</span><span class="sxs-lookup"><span data-stu-id="53b2a-119">An attempt was made to modify both the column set and a column that is included in the column set, causing two references to the same column.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="53b2a-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="53b2a-120">User Action</span></span>  
 <span data-ttu-id="53b2a-121">Réécrivez l'instruction de manière à inclure des références à la colonne ou au jeu de colonnes, mais pas aux deux.</span><span class="sxs-lookup"><span data-stu-id="53b2a-121">Rewrite the statement to include references to either the column or the column set, but do not include both in the statement.</span></span>  
  
  
