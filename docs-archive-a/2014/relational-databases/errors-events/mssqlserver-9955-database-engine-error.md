---
title: MSSQLSERVER_9955 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9955 (Database Engine error)
ms.assetid: 77f30570-7790-4747-b372-eac71c036e19
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 56b9f9b4b7923f8973bd7167c3c1bf77e92300c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604473"
---
# <a name="mssqlserver_9955"></a><span data-ttu-id="d1092-102">MSSQLSERVER_9955</span><span class="sxs-lookup"><span data-stu-id="d1092-102">MSSQLSERVER_9955</span></span>
    
## <a name="details"></a><span data-ttu-id="d1092-103">Détails</span><span class="sxs-lookup"><span data-stu-id="d1092-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d1092-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="d1092-104">Product Name</span></span>|<span data-ttu-id="d1092-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d1092-105">SQL Server</span></span>|  
|<span data-ttu-id="d1092-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="d1092-106">Event ID</span></span>|<span data-ttu-id="d1092-107">9955</span><span class="sxs-lookup"><span data-stu-id="d1092-107">9955</span></span>|  
|<span data-ttu-id="d1092-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="d1092-108">Event Source</span></span>|<span data-ttu-id="d1092-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d1092-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d1092-110">Composant</span><span class="sxs-lookup"><span data-stu-id="d1092-110">Component</span></span>|<span data-ttu-id="d1092-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d1092-111">SQLEngine</span></span>|  
|<span data-ttu-id="d1092-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="d1092-112">Symbolic Name</span></span>|<span data-ttu-id="d1092-113">FTXT2_MSSEARCHACCESSDENY</span><span class="sxs-lookup"><span data-stu-id="d1092-113">FTXT2_MSSEARCHACCESSDENY</span></span>|  
|<span data-ttu-id="d1092-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="d1092-114">Message Text</span></span>|<span data-ttu-id="d1092-115">SQL Server n'a pas pu créer de canal nommé '%ls' pour communiquer avec le démon de filtre de texte intégral (erreur Windows : %d).</span><span class="sxs-lookup"><span data-stu-id="d1092-115">SQL Server failed to create named pipe '%ls' to communicate with the full-text filter daemon (Windows error: %d).</span></span> <span data-ttu-id="d1092-116">Il existe déjà un canal nommé pour un processus hôte de démon de filtre, le système manque de ressources ou la recherche de numéro d'identification de sécurité (SID) du groupe de comptes du démon de filtre a échoué.</span><span class="sxs-lookup"><span data-stu-id="d1092-116">Either a named pipe already exists for a filter daemon host process, the system is low on resources, or the security identification number (SID) lookup for the filter daemon account group failed.</span></span> <span data-ttu-id="d1092-117">Pour résoudre cette erreur, arrêtez les processus de démon de filtre de texte intégral en cours d'exécution et reconfigurez si nécessaire le compte de service du lanceur de démon de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="d1092-117">To resolve this error, terminate any running full-text filter daemon processes, and if necessary reconfigure the full-text daemon launcher service account.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d1092-118">Explication</span><span class="sxs-lookup"><span data-stu-id="d1092-118">Explanation</span></span>  
 <span data-ttu-id="d1092-119">Ce message s'affiche parce que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] n'a pas pu créer de canal nommé pour communiquer avec le démon de filtre de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="d1092-119">This message occurs because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failed to create a named pipe to communicate with the full-text filter daemon.</span></span> <span data-ttu-id="d1092-120">Il existe déjà un canal nommé pour un processus hôte de démon de filtre, le système manque de ressources ou la recherche de numéro d'identification de sécurité (SID) du groupe de comptes du démon de filtre a échoué.</span><span class="sxs-lookup"><span data-stu-id="d1092-120">Either a named pipe already exists for a filter daemon host process, the system is low on resources, or the security identification number (SID) lookup for the filter daemon account group failed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d1092-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="d1092-121">User Action</span></span>  
 <span data-ttu-id="d1092-122">Pour résoudre cette erreur, arrêtez les processus de démon de filtre de texte intégral en cours d'exécution et reconfigurez si nécessaire le compte hôte du démon de texte intégral à l'aide du Gestionnaire de configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d1092-122">To resolve this error, terminate any running full-text filter daemon processes, and if necessary reconfigure the full-text daemon host account by using the SQL Server Configuration Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1092-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d1092-123">See Also</span></span>  
 <span data-ttu-id="d1092-124">[Gestionnaire de configuration SQL Server](../sql-server-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="d1092-124">[SQL Server Configuration Manager](../sql-server-configuration-manager.md) </span></span>  
 <span data-ttu-id="d1092-125">[Définir le compte de service du lanceur de démon de filtre de texte intégral](../search/set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span><span class="sxs-lookup"><span data-stu-id="d1092-125">[Set the Service Account for the Full-text Filter Daemon Launcher](../search/set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span></span>  
 [<span data-ttu-id="d1092-126">Recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="d1092-126">Full-Text Search</span></span>](../search/full-text-search.md)  
  
  
