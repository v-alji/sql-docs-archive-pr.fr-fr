---
title: Configuration de SQL Native Client 11,0 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- client configuration [SQL Server], SQL Server Native Client
ms.assetid: e73143e9-5e7b-4d0a-8827-ab900efdcb35
author: stevestein
ms.author: sstein
ms.openlocfilehash: 183dd2d161b1bf0b13140a607167b81dab086fdf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601865"
---
# <a name="sql-native-client-110-configuration"></a><span data-ttu-id="5c7d2-102">Configuration de SQL Server Native Client 11.0</span><span class="sxs-lookup"><span data-stu-id="5c7d2-102">SQL Native Client 11.0 Configuration</span></span>
  <span data-ttu-id="5c7d2-103">Cette section contient les rubriques d'aide accessibles au moyen de la touche F1, relatives aux boîtes de dialogue de **Configuration de SQL Server Native Client** du Gestionnaire de configuration [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c7d2-103">This section contains the F1 Help topics for the **SQL Server Native Client Configuration** dialogs in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5c7d2-104">Native Client est la bibliothèque réseau que les ordinateurs clients utilisent pour se connecter à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], à compter de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c7d2-104">Native Client is the network library that client computers use to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], starting with [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="5c7d2-105">Les paramètres définis dans la configuration de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client sont utilisés sur l'ordinateur exécutant le programme client.</span><span class="sxs-lookup"><span data-stu-id="5c7d2-105">The settings configured in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client Configuration, are used on the computer running the client program.</span></span> <span data-ttu-id="5c7d2-106">Lorsqu'ils sont configurés sur l'ordinateur exécutant [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ils n'affectent que les programmes clients en cours d'exécution sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="5c7d2-106">When configured on the computer running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], they affect only those client programs running on the server.</span></span>  
  
 <span data-ttu-id="5c7d2-107">Ces paramètres n'affectent pas les clients qui se connectent aux versions antérieures de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], sauf s'ils utilisent les outils clients disponibles à partir de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], tels que [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c7d2-107">These settings do not affect clients connecting to previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], unless they are using the client tools starting with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5c7d2-108">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="5c7d2-108">In this Section</span></span>  
  
-   [<span data-ttu-id="5c7d2-109">Propriétés de la configuration de SQL Server Native Client &#40;onglet Indicateurs&#41;</span><span class="sxs-lookup"><span data-stu-id="5c7d2-109">SQL Server Native Client Configuration Properties &#40;Flags Tab&#41;</span></span>](../../../2014/tools/configuration-manager/sql-server-native-client-configuration-properties-flags-tab.md)  
  
-   [<span data-ttu-id="5c7d2-110">Protocoles clients &#40;Gestionnaire de configuration SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5c7d2-110">Client Protocols &#40;SQL Server Configuration Manager&#41;</span></span>](../../relational-databases/sql-server-configuration-manager.md)  
  
    -   [<span data-ttu-id="5c7d2-111">Propriétés de protocoles clients &#40;onglet Ordre&#41;</span><span class="sxs-lookup"><span data-stu-id="5c7d2-111">Client Protocols Properties &#40;Order Tab&#41;</span></span>](../../../2014/tools/configuration-manager/client-protocols-properties-order-tab.md)  
  
    -   [<span data-ttu-id="5c7d2-112">Protocoles clients - Propriétés de Mémoire partagée &#40;onglet Protocole&#41;</span><span class="sxs-lookup"><span data-stu-id="5c7d2-112">Client Protocols - Shared Memory Properties &#40;Protocol Tab&#41;</span></span>](../../../2014/tools/configuration-manager/client-protocols-shared-memory-properties-protocol-tab.md)  
  
    -   [<span data-ttu-id="5c7d2-113">Protocoles clients-propriétés TCP et IP &#40;onglet protocole&#41;</span><span class="sxs-lookup"><span data-stu-id="5c7d2-113">Client Protocols - TCP and IP Properties &#40;Protocol Tab&#41;</span></span>](../../../2014/tools/configuration-manager/client-protocols-tcp-and-ip-properties-protocol-tab.md)  
  
    -   [<span data-ttu-id="5c7d2-114">Protocoles clients - Propriétés de Canaux nommés &#40;onglet Protocole&#41;</span><span class="sxs-lookup"><span data-stu-id="5c7d2-114">Client Protocols - Named Pipes Properties &#40;Protocol Tab&#41;</span></span>](../../../2014/tools/configuration-manager/client-protocols-named-pipes-properties-protocol-tab.md)  
  
-   [<span data-ttu-id="5c7d2-115">Alias &#40;Gestionnaire de configuration SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5c7d2-115">Aliases &#40;SQL Server Configuration Manager&#41;</span></span>](../../../2014/tools/configuration-manager/aliases-sql-server-configuration-manager.md)  
  
    -   [<span data-ttu-id="5c7d2-116">Nouvel alias &#40;onglet Alias&#41;</span><span class="sxs-lookup"><span data-stu-id="5c7d2-116">New Alias &#40;Alias Tab&#41;</span></span>](../../../2014/tools/configuration-manager/new-alias-alias-tab.md)  
  
    -   [<span data-ttu-id="5c7d2-117">Propriétés d’&#60;alias&#62; &#40;onglet Alias&#41;</span><span class="sxs-lookup"><span data-stu-id="5c7d2-117">&#60;Alias&#62; Properties &#40;Alias Tab&#41;</span></span>](../../../2014/tools/configuration-manager/alias-properties-alias-tab.md)  
  
    -   [<span data-ttu-id="5c7d2-118">Création d'une chaîne de connexion valide à l'aide du protocole de mémoire partagée</span><span class="sxs-lookup"><span data-stu-id="5c7d2-118">Creating a Valid Connection String Using Shared Memory Protocol</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md)  
  
    -   [<span data-ttu-id="5c7d2-119">Création d’une chaîne de connexion valide à l’aide du protocole TCP/IP</span><span class="sxs-lookup"><span data-stu-id="5c7d2-119">Creating a Valid Connection String Using TCP IP</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md)  
  
    -   [<span data-ttu-id="5c7d2-120">Création d’une chaîne de connexion valide avec des canaux nommés</span><span class="sxs-lookup"><span data-stu-id="5c7d2-120">Creating a Valid Connection String Using Named Pipes</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md)  
  
  
