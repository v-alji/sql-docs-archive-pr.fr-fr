---
title: Se connecter à SQL Server par le biais d’un serveur proxy (Gestionnaire de configuration SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Remote WinSock
- RWS
- LATs
- proxy servers [SQL Server]
- connections [SQL Server], proxy server
- Microsoft Proxy Server [SQL Server]
- local address tables [SQL Server]
ms.assetid: 39714de0-2a1f-4179-9091-5c3fa4612545
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: de22ad6043c509f08471a6bea40c0efa18d76842
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611281"
---
# <a name="connect-to-sql-server-through-a-proxy-server-sql-server-configuration-manager"></a><span data-ttu-id="16292-102">Se connecter à SQL Server par le biais d'un serveur proxy (Gestionnaire de configuration SQL Server)</span><span class="sxs-lookup"><span data-stu-id="16292-102">Connect to SQL Server Through a Proxy Server (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="16292-103">Cette rubrique explique comment se connecter à SQL Server via un serveur proxy dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide du Gestionnaire de configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="16292-103">This topic describes how to connect to SQL Server through a proxy server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="16292-104">Pour pouvoir écouter à distance au moyen de RWS (Remote WinSock), définissez la table d'adresses locales (LAT, Local Address Table) du serveur proxy pour que l'adresse du nœud à l'écoute se situe en dehors de la plage des entrées LAT.</span><span class="sxs-lookup"><span data-stu-id="16292-104">To listen remotely by way of Remote WinSock (RWS), define the local address table (LAT) for the proxy server so that the listening node address is outside the range of LAT entries.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="16292-105">Utilisation du Gestionnaire de configuration SQL Server</span><span class="sxs-lookup"><span data-stu-id="16292-105">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-enable-connections-to-sql-server-through-microsoft-proxy-server"></a><span data-ttu-id="16292-106">Pour autoriser les connexions à SQL Server via Microsoft Proxy Server</span><span class="sxs-lookup"><span data-stu-id="16292-106">To enable connections to SQL Server through Microsoft Proxy Server</span></span>  
  
1.  <span data-ttu-id="16292-107">Suivez les étapes décrites dans [Configurer un serveur pour écouter un port TCP spécifique &#40;Gestionnaire de configuration SQL Server&#41;](configure-a-server-to-listen-on-a-specific-tcp-port.md) pour déterminer quels ports TCP/IP sont utilisés par le [!INCLUDE[ssDE](../../includes/ssde-md.md)] ou pour configurer le [!INCLUDE[ssDE](../../includes/ssde-md.md)] pour qu’il utilise le port de votre choix.</span><span class="sxs-lookup"><span data-stu-id="16292-107">Follow the steps in [Configure a Server to Listen on a Specific TCP Port &#40;SQL Server Configuration Manager&#41;](configure-a-server-to-listen-on-a-specific-tcp-port.md) to determine which TCP/IP ports are used by the [!INCLUDE[ssDE](../../includes/ssde-md.md)], or to configure the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to use a desired port.</span></span>  
  
2.  <span data-ttu-id="16292-108">Dans votre serveur proxy, définissez la table d'adresses locales de ce serveur pour que l'adresse du nœud à l'écoute se situe en dehors de la plage des entrées de la table.</span><span class="sxs-lookup"><span data-stu-id="16292-108">In your proxy server define the local address table (LAT) for the proxy server so that the listening node address is outside the range of LAT entries.</span></span> <span data-ttu-id="16292-109">Pour plus d'informations, consultez la documentation de votre serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="16292-109">For more information, see your proxy server documentation.</span></span>  
  
  
