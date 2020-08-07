---
title: MSSQLSERVER_41301 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41301 (Database Engine error)
ms.assetid: c6127e1e-2846-4ee9-bc42-2d896ea9730e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d4fa78b334f32033f96df002aeaf039994b396cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611102"
---
# <a name="mssqlserver_41301"></a><span data-ttu-id="9a50b-102">MSSQLSERVER_41301</span><span class="sxs-lookup"><span data-stu-id="9a50b-102">MSSQLSERVER_41301</span></span>
    
## <a name="details"></a><span data-ttu-id="9a50b-103">Détails</span><span class="sxs-lookup"><span data-stu-id="9a50b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9a50b-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="9a50b-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="9a50b-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="9a50b-105">Event ID</span></span>|<span data-ttu-id="9a50b-106">41301</span><span class="sxs-lookup"><span data-stu-id="9a50b-106">41301</span></span>|  
|<span data-ttu-id="9a50b-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="9a50b-107">Event Source</span></span>|<span data-ttu-id="9a50b-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9a50b-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9a50b-109">Composant</span><span class="sxs-lookup"><span data-stu-id="9a50b-109">Component</span></span>|<span data-ttu-id="9a50b-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9a50b-110">SQLEngine</span></span>|  
|<span data-ttu-id="9a50b-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="9a50b-111">Symbolic Name</span></span>|<span data-ttu-id="9a50b-112">COMMIT_DEPENDENCY_FAILURE</span><span class="sxs-lookup"><span data-stu-id="9a50b-112">COMMIT_DEPENDENCY_FAILURE</span></span>|  
|<span data-ttu-id="9a50b-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="9a50b-113">Message Text</span></span>|<span data-ttu-id="9a50b-114">Une transaction précédente à la transaction actuelle a pris une dépendance ou a été abandonnée, et la transaction en cours ne peut plus être validée.</span><span class="sxs-lookup"><span data-stu-id="9a50b-114">A previous transaction that the current transaction took a dependency on has aborted, and the current transaction can no longer commit.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9a50b-115">Explication</span><span class="sxs-lookup"><span data-stu-id="9a50b-115">Explanation</span></span>  
 <span data-ttu-id="9a50b-116">La transaction a rencontré une erreur de dépendance, et est maintenant vouée à l'échec.</span><span class="sxs-lookup"><span data-stu-id="9a50b-116">The transaction encountered a dependency failure, and is now doomed.</span></span>  
  
 <span data-ttu-id="9a50b-117">Cette erreur peut également être causée par un nombre de transactions dépendantes trop important.</span><span class="sxs-lookup"><span data-stu-id="9a50b-117">This error can also be caused by too many dependent transactions.</span></span> <span data-ttu-id="9a50b-118">Les transactions d'écriture ne peuvent avoir qu'un nombre limité de transactions dépendantes.</span><span class="sxs-lookup"><span data-stu-id="9a50b-118">Any write transaction can have a limited number of dependent transactions.</span></span> <span data-ttu-id="9a50b-119">Par exemple, cette erreur peut se produire si trop de transactions de lecture essaient de prendre une dépendance sur la transaction de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="9a50b-119">For example, this error can occur if too many read transactions try to take a dependency on the update transaction.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9a50b-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="9a50b-120">User Action</span></span>  
 <span data-ttu-id="9a50b-121">N'effectuez aucune tâche dans la transaction.</span><span class="sxs-lookup"><span data-stu-id="9a50b-121">Don't do any work on the transaction.</span></span> <span data-ttu-id="9a50b-122">Appelez ROLLBACK TRAN pour restaurer la transaction.</span><span class="sxs-lookup"><span data-stu-id="9a50b-122">Call ROLLBACK TRAN to roll back the transaction.</span></span> <span data-ttu-id="9a50b-123">Pour plus d’informations, consultez [OLTP en mémoire &#40;optimisation en mémoire&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="9a50b-123">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a50b-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9a50b-124">See Also</span></span>  
 [<span data-ttu-id="9a50b-125">Activer et désactiver les groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9a50b-125">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](../../database-engine/availability-groups/windows/enable-and-disable-always-on-availability-groups-sql-server.md)  
  
  
