---
title: MSSQLSERVER_125 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "125"
helpviewer_keywords:
- 125 (Database Engine error)
ms.assetid: 0f58338d-2ea0-48b8-8a20-c438b0940433
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 59c732d80ccfafc8f242bb1c42fe60e3dea81f19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605495"
---
# <a name="mssqlserver_125"></a><span data-ttu-id="7affe-102">MSSQLSERVER_125</span><span class="sxs-lookup"><span data-stu-id="7affe-102">MSSQLSERVER_125</span></span>
    
## <a name="details"></a><span data-ttu-id="7affe-103">Détails</span><span class="sxs-lookup"><span data-stu-id="7affe-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7affe-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="7affe-104">Product Name</span></span>|<span data-ttu-id="7affe-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7affe-105">SQL Server</span></span>|  
|<span data-ttu-id="7affe-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="7affe-106">Event ID</span></span>|<span data-ttu-id="7affe-107">125</span><span class="sxs-lookup"><span data-stu-id="7affe-107">125</span></span>|  
|<span data-ttu-id="7affe-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="7affe-108">Event Source</span></span>|<span data-ttu-id="7affe-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7affe-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7affe-110">Composant</span><span class="sxs-lookup"><span data-stu-id="7affe-110">Component</span></span>|<span data-ttu-id="7affe-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7affe-111">SQLEngine</span></span>|  
|<span data-ttu-id="7affe-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="7affe-112">Symbolic Name</span></span>||  
|<span data-ttu-id="7affe-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="7affe-113">Message Text</span></span>|<span data-ttu-id="7affe-114">Les expressions Case ne peuvent être imbriquées que jusqu'au niveau %d.</span><span class="sxs-lookup"><span data-stu-id="7affe-114">Case expressions may only be nested to level %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7affe-115">Explication</span><span class="sxs-lookup"><span data-stu-id="7affe-115">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7affe-116">autorise uniquement 10 niveaux d'imbrication dans les expressions CASE.</span><span class="sxs-lookup"><span data-stu-id="7affe-116">allows for only 10 levels of nesting in CASE expressions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7affe-117">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="7affe-117">User Action</span></span>  
 <span data-ttu-id="7affe-118">Réduisez le niveau des instructions CASE à 10 ou une valeur inférieure.</span><span class="sxs-lookup"><span data-stu-id="7affe-118">Reduce the level of CASE statements to 10 or less.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7affe-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7affe-119">See Also</span></span>  
 [<span data-ttu-id="7affe-120">CASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7affe-120">CASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/case-transact-sql)  
  
  
