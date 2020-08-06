---
title: MSSQLSERVER_21892 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21892 (Database Engine error)
ms.assetid: 199818e8-28f4-440e-ad85-7bea88f51153
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5fd3bfa1213f0569293991d6bd759619c6e7b596
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707591"
---
# <a name="mssqlserver_21892"></a><span data-ttu-id="2de41-102">MSSQLSERVER_21892</span><span class="sxs-lookup"><span data-stu-id="2de41-102">MSSQLSERVER_21892</span></span>
    
## <a name="details"></a><span data-ttu-id="2de41-103">Détails</span><span class="sxs-lookup"><span data-stu-id="2de41-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2de41-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="2de41-104">Product Name</span></span>|<span data-ttu-id="2de41-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2de41-105">SQL Server</span></span>|  
|<span data-ttu-id="2de41-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="2de41-106">Event ID</span></span>|<span data-ttu-id="2de41-107">21892</span><span class="sxs-lookup"><span data-stu-id="2de41-107">21892</span></span>|  
|<span data-ttu-id="2de41-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="2de41-108">Event Source</span></span>|<span data-ttu-id="2de41-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2de41-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2de41-110">Composant</span><span class="sxs-lookup"><span data-stu-id="2de41-110">Component</span></span>|<span data-ttu-id="2de41-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2de41-111">SQLEngine</span></span>|  
|<span data-ttu-id="2de41-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="2de41-112">Symbolic Name</span></span>|<span data-ttu-id="2de41-113">SQLErrorNum21892</span><span class="sxs-lookup"><span data-stu-id="2de41-113">SQLErrorNum21892</span></span>|  
|<span data-ttu-id="2de41-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="2de41-114">Message Text</span></span>|<span data-ttu-id="2de41-115">Impossible d’interroger sys.availability_replicas sur le groupe de disponibilité principal associé au nom de réseau virtuel « %1!s! » pour les noms de serveur des réplicas membres : erreur = « %2!s! », message d’erreur = « %3!s! ».',</span><span class="sxs-lookup"><span data-stu-id="2de41-115">Unable to query sys.availability_replicas at the availability group primary associated with virtual network name '%s' for the server names of the member replicas: error = %d, error message = %s.',</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2de41-116">Explication</span><span class="sxs-lookup"><span data-stu-id="2de41-116">Explanation</span></span>  
 <span data-ttu-id="2de41-117">`sp_validate_replica_hosts_as_publishers` interroge le principal actuel du groupe de disponibilité associé au serveur de publication redirigé pour déterminer les instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui hébergent les réplicas membres.</span><span class="sxs-lookup"><span data-stu-id="2de41-117">`sp_validate_replica_hosts_as_publishers` queries the current primary of the availability group associated with the redirected publisher, to determine the instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that host the member replicas.</span></span>  <span data-ttu-id="2de41-118">Lorsque cette requête échoue, l'erreur 21892 est retournée.</span><span class="sxs-lookup"><span data-stu-id="2de41-118">When this query fails, error 21892 is returned.</span></span>  
  
 <span data-ttu-id="2de41-119">`sp_validate_replica_hosts_as_publishers` est généralement la première utilisation qui est faite du serveur lié temporaire, par conséquent, si des problèmes de connectivité sont présents, ils sont susceptibles d'apparaître d'abord avec `sp_validate_replica_hosts_as_publishers`.</span><span class="sxs-lookup"><span data-stu-id="2de41-119">`sp_validate_replica_hosts_as_publishers` is typically on of the first use of the temporary linked server, so if there are connectivity problems they are likely to appear first with `sp_validate_replica_hosts_as_publishers`.</span></span> <span data-ttu-id="2de41-120">Contrairement à `sp_validate_redirected_publisher`, le serveur lié utilisé par `sp_validate_replica_hosts_as_publishers` utilise toujours les informations d'identification de l'appelant lors de la connexion à n'importe quel hôte de réplica de groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="2de41-120">Unlike `sp_validate_redirected_publisher`, the linked server used by `sp_validate_replica_hosts_as_publishers` always uses the credentials of the caller when connecting to any of the availability group replica hosts.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2de41-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="2de41-121">User Action</span></span>  
 <span data-ttu-id="2de41-122">Lorsque vous exécutez cette procédure stockée, assurez-vous que vous utilisez une connexion valide sur tous les réplicas.</span><span class="sxs-lookup"><span data-stu-id="2de41-122">When running this stored procedure, made certain that you run from a login that is valid on all of the replicas.</span></span> <span data-ttu-id="2de41-123">La connexion nécessite des autorisations suffisantes pour interroger les tables de métadonnées du groupe de disponibilité ainsi que les tables de métadonnées d'abonnement dans le réplica de base de données du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="2de41-123">The login will require sufficient authorization to query availability group metadata tables as well as to query the subscription metadata tables in the publisher database replica.</span></span>  
  
 <span data-ttu-id="2de41-124">Examinez l'erreur référencée d'origine pour déterminer la cause de l'échec et l'action corrective appropriée.</span><span class="sxs-lookup"><span data-stu-id="2de41-124">Examine the original referenced error to determine the cause of the failure and appropriate corrective action.</span></span>  
  
  
