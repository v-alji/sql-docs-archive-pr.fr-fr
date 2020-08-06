---
title: Lanceur de démon de filtre de texte intégral SQL (Gestionnaire de configuration SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: d0dc03db-5f76-4558-b041-1ac7b9b5bb16
author: stevestein
ms.author: sstein
ms.openlocfilehash: 45194c893db048151cdb03d33f1419ef42246d69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600435"
---
# <a name="sql-full-text-filter-daemon-launcher-sql-server-configuration-manager"></a><span data-ttu-id="48818-102">Lanceur de démon de filtre de texte intégral SQL (Gestionnaire de configuration SQL Server)</span><span class="sxs-lookup"><span data-stu-id="48818-102">SQL Full-text Filter Daemon Launcher (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="48818-103">À compter de [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], le service du lanceur de démon de filtre de texte intégral SQL (lanceur FDHOST) est utilisé par la recherche en texte intégral dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour démarrer le processus hôte de démon de filtre, qui gère l'analyse lexicale et le filtrage de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="48818-103">Beginning in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], the SQL Full-text Filter Daemon Launcher (FDHOST Launcher) service is used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] full-text search to start the filter daemon host process, which handles full-text search filtering and word breaking.</span></span> <span data-ttu-id="48818-104">Ce service doit être en cours d'exécution pour que la recherche en texte intégral puisse être utilisée.</span><span class="sxs-lookup"><span data-stu-id="48818-104">This service must be running to use full-text search.</span></span> <span data-ttu-id="48818-105">Le service du lanceur FDHOST est un service dépendant d’une instance qui est associé à une instance spécifique de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48818-105">The FDHOST Launcher service is an instance-aware service that is associated with a specific instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="48818-106">Le service du lanceur FDHOST propage les informations sur le compte de service à chaque processus hôte de démon de filtre démarré.</span><span class="sxs-lookup"><span data-stu-id="48818-106">The FDHOST Launcher service propagates the service account information to each filter daemon host process started.</span></span> <span data-ttu-id="48818-107">Pour plus d'informations sur les processus hôte de démon de filtre, consultez « Architecture de la recherche en texte intégral » dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="48818-107">For information about the filter daemon host processes, see "Full-Text Search Architecture" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
  
