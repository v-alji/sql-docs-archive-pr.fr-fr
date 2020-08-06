---
title: MSSQLSERVER_9532 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9532 (Database Engine error)
ms.assetid: ab95cce8-4f97-4aea-a746-a73eea7c9aab
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c34ebc7c682d2ffe8bc0205565f5dfd44fdd5b66
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604485"
---
# <a name="mssqlserver_9532"></a><span data-ttu-id="1a74b-102">MSSQLSERVER_9532</span><span class="sxs-lookup"><span data-stu-id="1a74b-102">MSSQLSERVER_9532</span></span>
    
## <a name="details"></a><span data-ttu-id="1a74b-103">Détails</span><span class="sxs-lookup"><span data-stu-id="1a74b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1a74b-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="1a74b-104">Product Name</span></span>|<span data-ttu-id="1a74b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1a74b-105">SQL Server</span></span>|  
|<span data-ttu-id="1a74b-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="1a74b-106">Event ID</span></span>|<span data-ttu-id="1a74b-107">9532</span><span class="sxs-lookup"><span data-stu-id="1a74b-107">9532</span></span>|  
|<span data-ttu-id="1a74b-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="1a74b-108">Event Source</span></span>|<span data-ttu-id="1a74b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1a74b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1a74b-110">Composant</span><span class="sxs-lookup"><span data-stu-id="1a74b-110">Component</span></span>|<span data-ttu-id="1a74b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1a74b-111">SQLEngine</span></span>|  
|<span data-ttu-id="1a74b-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="1a74b-112">Symbolic Name</span></span>|<span data-ttu-id="1a74b-113">XMLERR_COLUMNSET_CANNOT_CONVERT_FROM_TO</span><span class="sxs-lookup"><span data-stu-id="1a74b-113">XMLERR_COLUMNSET_CANNOT_CONVERT_FROM_TO</span></span>|  
|<span data-ttu-id="1a74b-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="1a74b-114">Message Text</span></span>|<span data-ttu-id="1a74b-115">Dans l’opération de requête/DML impliquant le jeu de colonnes '%.\*ls', la conversion a échoué lors de la conversion du type de données '%ls' en type de données '%ls' pour la colonne '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="1a74b-115">In the query/DML operation involving  column set '%.\*ls', conversion failed when converting from the data type '%ls' to the data type '%ls' for the column '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1a74b-116">Explication</span><span class="sxs-lookup"><span data-stu-id="1a74b-116">Explanation</span></span>  
 <span data-ttu-id="1a74b-117">Un jeu de colonnes est une représentation XML non typée qui associe certaines colonnes d'une table dans une sortie structurée.</span><span class="sxs-lookup"><span data-stu-id="1a74b-117">A column set is an untyped XML representation that combines some of the columns of a table into a structured output.</span></span> <span data-ttu-id="1a74b-118">Lorsque vous insérez ou mettez à jour des valeurs de colonnes éparses à l'aide du jeu de colonnes XML, les valeurs insérées dans les colonnes éparses sous-jacentes sont converties implicitement à partir du type de données `xml`.</span><span class="sxs-lookup"><span data-stu-id="1a74b-118">When you are inserting or updating sparse column values through the XML column set, the values that are inserted into the underlying sparse columns are implicitly converted from the `xml` data type.</span></span> <span data-ttu-id="1a74b-119">Une valeur a été fournie qui ne peut pas être convertie vers le type de données de la colonne.</span><span class="sxs-lookup"><span data-stu-id="1a74b-119">A value was provided that cannot be converted to the data type of the column.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1a74b-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="1a74b-120">User Action</span></span>  
 <span data-ttu-id="1a74b-121">Comme la valeur fournie n'a pas pu être convertie implicitement, il peut s'agir d'une entrée non valide.</span><span class="sxs-lookup"><span data-stu-id="1a74b-121">Because the value provided could not be implicitly converted, it might be an invalid entry.</span></span> <span data-ttu-id="1a74b-122">Corrigez l'erreur et réessayez.</span><span class="sxs-lookup"><span data-stu-id="1a74b-122">Correct the error and retry.</span></span> <span data-ttu-id="1a74b-123">Si la valeur est correcte, modifiez l'instruction pour utiliser les colonnes individuelles à la place du jeu de colonnes.</span><span class="sxs-lookup"><span data-stu-id="1a74b-123">If the value is correct, modify the statement to use the individual columns instead of the column set.</span></span> <span data-ttu-id="1a74b-124">Cela vous permettra de convertir explicitement le type de la valeur vers le type de données correct.</span><span class="sxs-lookup"><span data-stu-id="1a74b-124">This will allow you to explicitly cast the value into the correct data type.</span></span>  
  
  
