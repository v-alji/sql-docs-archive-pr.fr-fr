---
title: MSSQLSERVER_5554 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5554 (Database Engine error)
ms.assetid: 7134bbe5-d240-4a98-85ce-b13cc8ae9b0e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5095a50f257abafb6ebde97bb32c57bc71fc4e09
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610674"
---
# <a name="mssqlserver_5554"></a><span data-ttu-id="25afb-102">MSSQLSERVER_5554</span><span class="sxs-lookup"><span data-stu-id="25afb-102">MSSQLSERVER_5554</span></span>
    
## <a name="details"></a><span data-ttu-id="25afb-103">Détails</span><span class="sxs-lookup"><span data-stu-id="25afb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="25afb-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="25afb-104">Product Name</span></span>|<span data-ttu-id="25afb-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="25afb-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="25afb-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="25afb-106">Event ID</span></span>|<span data-ttu-id="25afb-107">5554</span><span class="sxs-lookup"><span data-stu-id="25afb-107">5554</span></span>|  
|<span data-ttu-id="25afb-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="25afb-108">Event Source</span></span>|<span data-ttu-id="25afb-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="25afb-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="25afb-110">Composant</span><span class="sxs-lookup"><span data-stu-id="25afb-110">Component</span></span>|<span data-ttu-id="25afb-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="25afb-111">SQLEngine</span></span>|  
|<span data-ttu-id="25afb-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="25afb-112">Symbolic Name</span></span>|<span data-ttu-id="25afb-113">FS_MINIVER_OVERFLOW</span><span class="sxs-lookup"><span data-stu-id="25afb-113">FS_MINIVER_OVERFLOW</span></span>|  
|<span data-ttu-id="25afb-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="25afb-114">Message Text</span></span>|<span data-ttu-id="25afb-115">La limite maximale du nombre total de versions d'un seul fichier pour le système de fichiers a été atteinte.</span><span class="sxs-lookup"><span data-stu-id="25afb-115">The total number of versions for a single file has reached the maximum limit set by the file system.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="25afb-116">Explication</span><span class="sxs-lookup"><span data-stu-id="25afb-116">Explanation</span></span>  
 <span data-ttu-id="25afb-117">Dans les scénarios de déclencheur ou MARS (Multiple Active Result Set), [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilise la miniversion spécifiée par le système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="25afb-117">In multiple active result sets (MARS) or trigger scenarios, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses the miniversion specified by the operating system.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="25afb-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="25afb-118">User Action</span></span>  
 <span data-ttu-id="25afb-119">Essayez d'éviter les mises à jour répétées des données dans la même transaction.</span><span class="sxs-lookup"><span data-stu-id="25afb-119">Try to avoid repeated updates to the data in the same transaction.</span></span>  
  
  
