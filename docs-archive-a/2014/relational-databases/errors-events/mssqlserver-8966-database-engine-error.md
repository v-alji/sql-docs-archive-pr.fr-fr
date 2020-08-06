---
title: MSSQLSERVER_8966 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8966 (Database Engine error)
ms.assetid: 6b1150fd-9dfd-4df9-8f08-8eca237667db
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8d3a12d5d0732ba8694db3d4c7dcae1eac59d28b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615157"
---
# <a name="mssqlserver_8966"></a><span data-ttu-id="6661f-102">MSSQLSERVER_8966</span><span class="sxs-lookup"><span data-stu-id="6661f-102">MSSQLSERVER_8966</span></span>
    
## <a name="details"></a><span data-ttu-id="6661f-103">Détails</span><span class="sxs-lookup"><span data-stu-id="6661f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6661f-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="6661f-104">Product Name</span></span>|<span data-ttu-id="6661f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6661f-105">SQL Server</span></span>|  
|<span data-ttu-id="6661f-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="6661f-106">Event ID</span></span>|<span data-ttu-id="6661f-107">8966</span><span class="sxs-lookup"><span data-stu-id="6661f-107">8966</span></span>|  
|<span data-ttu-id="6661f-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="6661f-108">Event Source</span></span>|<span data-ttu-id="6661f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6661f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6661f-110">Composant</span><span class="sxs-lookup"><span data-stu-id="6661f-110">Component</span></span>|<span data-ttu-id="6661f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6661f-111">SQLEngine</span></span>|  
|<span data-ttu-id="6661f-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="6661f-112">Symbolic Name</span></span>|<span data-ttu-id="6661f-113">DBCC3_FAILED_TO_READ_AND_LATCH_PAGE</span><span class="sxs-lookup"><span data-stu-id="6661f-113">DBCC3_FAILED_TO_READ_AND_LATCH_PAGE</span></span>|  
|<span data-ttu-id="6661f-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="6661f-114">Message Text</span></span>|<span data-ttu-id="6661f-115">Impossible de lire et de verrouiller la page P_ID avec le type de verrou TYPE.</span><span class="sxs-lookup"><span data-stu-id="6661f-115">Unable to read and latch page P_ID with latch type TYPE.</span></span> <span data-ttu-id="6661f-116">Échec de OPERATION.</span><span class="sxs-lookup"><span data-stu-id="6661f-116">OPERATION failed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6661f-117">Explication</span><span class="sxs-lookup"><span data-stu-id="6661f-117">Explanation</span></span>  
 <span data-ttu-id="6661f-118">La lecture de la page a échoué ou un verrou n'a pas pu être pris en compte sur une page PFS ou GAM.</span><span class="sxs-lookup"><span data-stu-id="6661f-118">The page read failed or a latch could not be taken on a PFS or GAM page.</span></span> <span data-ttu-id="6661f-119">Le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peut contenir des messages relatifs au dépassement de délai d’attente de verrous ou d’autres messages associés.</span><span class="sxs-lookup"><span data-stu-id="6661f-119">There may be latch time-out or other accompanying messages in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6661f-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="6661f-120">User Action</span></span>  
 <span data-ttu-id="6661f-121">Vérifiez les éventuels messages associés dans le journal des erreurs SQL et résolvez ces erreurs.</span><span class="sxs-lookup"><span data-stu-id="6661f-121">Review the SQL error log for accompanying messages and resolve these errors.</span></span>  
  
  
