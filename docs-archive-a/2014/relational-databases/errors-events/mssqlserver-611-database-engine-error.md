---
title: MSSQLSERVER_611 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 611 (Database Engine error)
ms.assetid: ac6a213f-5c38-44ad-bc85-a62863786614
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f0caa1c218e8b80059c0c97aac652da7db870af3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614106"
---
# <a name="mssqlserver_611"></a><span data-ttu-id="e8216-102">MSSQLSERVER_611</span><span class="sxs-lookup"><span data-stu-id="e8216-102">MSSQLSERVER_611</span></span>
    
## <a name="details"></a><span data-ttu-id="e8216-103">Détails</span><span class="sxs-lookup"><span data-stu-id="e8216-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e8216-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="e8216-104">Product Name</span></span>|<span data-ttu-id="e8216-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e8216-105">SQL Server</span></span>|  
|<span data-ttu-id="e8216-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="e8216-106">Event ID</span></span>|<span data-ttu-id="e8216-107">611</span><span class="sxs-lookup"><span data-stu-id="e8216-107">611</span></span>|  
|<span data-ttu-id="e8216-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="e8216-108">Event Source</span></span>|<span data-ttu-id="e8216-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e8216-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e8216-110">Composant</span><span class="sxs-lookup"><span data-stu-id="e8216-110">Component</span></span>|<span data-ttu-id="e8216-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e8216-111">SQLEngine</span></span>|  
|<span data-ttu-id="e8216-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="e8216-112">Symbolic Name</span></span>|<span data-ttu-id="e8216-113">VAR_SIZE_TOO_BIG</span><span class="sxs-lookup"><span data-stu-id="e8216-113">VAR_SIZE_TOO_BIG</span></span>|  
|<span data-ttu-id="e8216-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="e8216-114">Message Text</span></span>|<span data-ttu-id="e8216-115">Impossible d'insérer ou de mettre à jour une ligne, car la taille totale de colonne variable, surcharge comprise, dépasse la limite de %d octets.</span><span class="sxs-lookup"><span data-stu-id="e8216-115">Cannot insert or update a row because total variable column size, including overhead, is %d bytes more than the limit.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e8216-116">Explication</span><span class="sxs-lookup"><span data-stu-id="e8216-116">Explanation</span></span>  
 <span data-ttu-id="e8216-117">La taille de colonne variable maximale est supérieure à celle autorisée par le schéma.</span><span class="sxs-lookup"><span data-stu-id="e8216-117">The maximum variable column size is more than that allowed by the schema.</span></span> <span data-ttu-id="e8216-118">L'erreur 611 est retournée lorsque la colonne variable est supérieure à la limite dans le cas où le format de stockage VarDecimal est activé, ou lorsque la taille de la colonne variable est supérieure à la limite autorisée dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] pour un enregistrement de données compressé.</span><span class="sxs-lookup"><span data-stu-id="e8216-118">Error 611 is returned when the variable column is over the limit in the fixed case when vardecimal storage format is enabled, or when the variable column size is over the limit allowed in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] for a compressed data record.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e8216-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e8216-119">User Action</span></span>  
 <span data-ttu-id="e8216-120">Réduisez la taille de l'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="e8216-120">Reduce the size of the record.</span></span>  
  
  
