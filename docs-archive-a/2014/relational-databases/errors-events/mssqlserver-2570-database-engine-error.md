---
title: MSSQLSERVER_2570 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2570 (Database Engine error)
ms.assetid: 29800aa9-81aa-4371-992c-487dbb617f46
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 79137d0f70c05c6aa7b758f7e073d152681a14b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696868"
---
# <a name="mssqlserver_2570"></a><span data-ttu-id="b5c78-102">MSSQLSERVER_2570</span><span class="sxs-lookup"><span data-stu-id="b5c78-102">MSSQLSERVER_2570</span></span>
    
## <a name="details"></a><span data-ttu-id="b5c78-103">Détails</span><span class="sxs-lookup"><span data-stu-id="b5c78-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b5c78-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="b5c78-104">Product Name</span></span>|<span data-ttu-id="b5c78-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b5c78-105">SQL Server</span></span>|  
|<span data-ttu-id="b5c78-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="b5c78-106">Event ID</span></span>|<span data-ttu-id="b5c78-107">2570</span><span class="sxs-lookup"><span data-stu-id="b5c78-107">2570</span></span>|  
|<span data-ttu-id="b5c78-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="b5c78-108">Event Source</span></span>|<span data-ttu-id="b5c78-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b5c78-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b5c78-110">Composant</span><span class="sxs-lookup"><span data-stu-id="b5c78-110">Component</span></span>|<span data-ttu-id="b5c78-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b5c78-111">SQLEngine</span></span>|  
|<span data-ttu-id="b5c78-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="b5c78-112">Symbolic Name</span></span>|<span data-ttu-id="b5c78-113">DBCC_COLUMN_VALUE_OUT_OF_RANGE</span><span class="sxs-lookup"><span data-stu-id="b5c78-113">DBCC_COLUMN_VALUE_OUT_OF_RANGE</span></span>|  
|<span data-ttu-id="b5c78-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="b5c78-114">Message Text</span></span>|<span data-ttu-id="b5c78-115">Page P_ID, slot S_ID de l'ID d'objet O_ID, ID d'index I_ID, ID de partition PN_ID, ID d'unité d'allocation A_ID (type TYPE).</span><span class="sxs-lookup"><span data-stu-id="b5c78-115">Page P_ID, slot S_ID in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="b5c78-116">La valeur COLUMN_NAME de colonne est hors limite pour le type de données "DATATYPE".</span><span class="sxs-lookup"><span data-stu-id="b5c78-116">Column COLUMN_NAME value is out of range for data type "DATATYPE".</span></span> <span data-ttu-id="b5c78-117">Mettez la colonne à jour avec une valeur valide.</span><span class="sxs-lookup"><span data-stu-id="b5c78-117">Update column to a legal value.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b5c78-118">Explication</span><span class="sxs-lookup"><span data-stu-id="b5c78-118">Explanation</span></span>  
 <span data-ttu-id="b5c78-119">La valeur de colonne qui est contenue dans la colonne spécifiée se trouve en dehors de la plage des valeurs possibles pour le type de données de colonne.</span><span class="sxs-lookup"><span data-stu-id="b5c78-119">The column value that is contained in the specified column is outside the range of possible values for the column data type.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b5c78-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="b5c78-120">User Action</span></span>  
 <span data-ttu-id="b5c78-121">L'erreur ne peut pas être réparée.</span><span class="sxs-lookup"><span data-stu-id="b5c78-121">The error is not repairable.</span></span> <span data-ttu-id="b5c78-122">Mettez à jour la colonne avec une valeur comprise dans la plage des valeurs pour le type de données de la colonne, puis réexécutez la commande.</span><span class="sxs-lookup"><span data-stu-id="b5c78-122">Update the column to a value within the range for the data type of the column and run the command again.</span></span>  <span data-ttu-id="b5c78-123">Pour plus d’informations, consultez l’article [923247](https://support.microsoft.com/kb/923247) de la Base de connaissances.</span><span class="sxs-lookup"><span data-stu-id="b5c78-123">For more information, see this KB article [923247](https://support.microsoft.com/kb/923247).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5c78-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b5c78-124">See Also</span></span>  
 <span data-ttu-id="b5c78-125">[UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b5c78-125">[UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql) </span></span>  
 [<span data-ttu-id="b5c78-126">Types de données &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b5c78-126">Data Types &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/data-types-transact-sql)  
  
  
