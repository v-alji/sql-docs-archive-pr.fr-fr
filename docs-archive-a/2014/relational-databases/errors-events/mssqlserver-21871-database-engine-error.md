---
title: MSSQLSERVER_21871 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21871 (Database Engine error)
ms.assetid: d3215378-9282-444f-a18b-00b96fd0133d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f26211da21829a0a898dfb36ff9fefd453c7ad44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699653"
---
# <a name="mssqlserver_21871"></a><span data-ttu-id="2e371-102">MSSQLSERVER_21871</span><span class="sxs-lookup"><span data-stu-id="2e371-102">MSSQLSERVER_21871</span></span>
    
## <a name="details"></a><span data-ttu-id="2e371-103">Détails</span><span class="sxs-lookup"><span data-stu-id="2e371-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2e371-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="2e371-104">Product Name</span></span>|<span data-ttu-id="2e371-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2e371-105">SQL Server</span></span>|  
|<span data-ttu-id="2e371-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="2e371-106">Event ID</span></span>|<span data-ttu-id="2e371-107">21871</span><span class="sxs-lookup"><span data-stu-id="2e371-107">21871</span></span>|  
|<span data-ttu-id="2e371-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="2e371-108">Event Source</span></span>|<span data-ttu-id="2e371-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2e371-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2e371-110">Composant</span><span class="sxs-lookup"><span data-stu-id="2e371-110">Component</span></span>|<span data-ttu-id="2e371-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2e371-111">SQLEngine</span></span>|  
|<span data-ttu-id="2e371-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="2e371-112">Symbolic Name</span></span>|<span data-ttu-id="2e371-113">SQLErrorNum21871</span><span class="sxs-lookup"><span data-stu-id="2e371-113">SQLErrorNum21871</span></span>|  
|<span data-ttu-id="2e371-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="2e371-114">Message Text</span></span>|<span data-ttu-id="2e371-115">Le serveur de publication %s de la base de données %s n'a pas été redirigé.</span><span class="sxs-lookup"><span data-stu-id="2e371-115">Publisher %s of database %s has not been redirected.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2e371-116">Explication</span><span class="sxs-lookup"><span data-stu-id="2e371-116">Explanation</span></span>  
 <span data-ttu-id="2e371-117">`sp_validate_replica_hosts_as_publishers` vérifie la table MSredirected_publishers dans la base de données de distribution pour les entrées du serveur de publication et de la base de données du serveur de publication identifiées.</span><span class="sxs-lookup"><span data-stu-id="2e371-117">`sp_validate_replica_hosts_as_publishers` checks the table MSredirected_publishers in the distribution database for an entry for the identified publisher and publisher database.</span></span>  <span data-ttu-id="2e371-118">`sp_validate_replica_hosts_as_publishers` retourne l'erreur 21871 lorsqu'aucune entrée n'est trouvée.</span><span class="sxs-lookup"><span data-stu-id="2e371-118">`sp_validate_replica_hosts_as_publishers` returns error 21871 when no entry is found.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2e371-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="2e371-119">User Action</span></span>  
 <span data-ttu-id="2e371-120">`sp_validate_replica_hosts_as_publishers` est uniquement applicable aux serveurs de publication redirigés.</span><span class="sxs-lookup"><span data-stu-id="2e371-120">`sp_validate_replica_hosts_as_publishers` is only relevant for redirected publishers.</span></span> <span data-ttu-id="2e371-121">Si la base de données du serveur de publication est membre d'un groupe de disponibilité, utilisez la procédure stockée `sp_redirect_publisher` pour associer le serveur de publication et la base de données du serveur de publication au nom d'écouteur du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="2e371-121">If the publisher database is a member of an availability group, use the stored procedure `sp_redirect_publisher` to associate the publisher and publisher database with the Availability Group Listener Name of the availability group.</span></span>  
  
  
