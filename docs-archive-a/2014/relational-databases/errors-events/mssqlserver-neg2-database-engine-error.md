---
title: MSSQLSERVER_-2 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "2"
helpviewer_keywords:
- -2 (Database Engine error)
ms.assetid: f37a7b7d-26e1-4b9e-bcb4-57f7805393d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5d39b4a11387a60056bba3f87adffcb2653b60f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701220"
---
# <a name="mssqlserver_-2"></a><span data-ttu-id="5eab3-102">MSSQLSERVER_-2</span><span class="sxs-lookup"><span data-stu-id="5eab3-102">MSSQLSERVER_-2</span></span>
    
## <a name="details"></a><span data-ttu-id="5eab3-103">Détails</span><span class="sxs-lookup"><span data-stu-id="5eab3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5eab3-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="5eab3-104">Product Name</span></span>|<span data-ttu-id="5eab3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5eab3-105">SQL Server</span></span>|  
|<span data-ttu-id="5eab3-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="5eab3-106">Event ID</span></span>|<span data-ttu-id="5eab3-107">-2</span><span class="sxs-lookup"><span data-stu-id="5eab3-107">-2</span></span>|  
|<span data-ttu-id="5eab3-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="5eab3-108">Event Source</span></span>|<span data-ttu-id="5eab3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5eab3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5eab3-110">Composant</span><span class="sxs-lookup"><span data-stu-id="5eab3-110">Component</span></span>|<span data-ttu-id="5eab3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5eab3-111">SQLEngine</span></span>|  
|<span data-ttu-id="5eab3-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="5eab3-112">Symbolic Name</span></span>||  
|<span data-ttu-id="5eab3-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="5eab3-113">Message Text</span></span>|<span data-ttu-id="5eab3-114">Délai expiré.</span><span class="sxs-lookup"><span data-stu-id="5eab3-114">Timeout expired.</span></span>  <span data-ttu-id="5eab3-115">Période de délai d'attente écoulée avant l'achèvement de l'opération, ou le serveur ne répond pas.</span><span class="sxs-lookup"><span data-stu-id="5eab3-115">The timeout period elapsed prior to completion of the operation or the server is not responding.</span></span> <span data-ttu-id="5eab3-116">(Microsoft SQL Server, erreur : -2)</span><span class="sxs-lookup"><span data-stu-id="5eab3-116">(Microsoft SQL Server, Error: -2)</span></span>|   
  
## <a name="explanation"></a><span data-ttu-id="5eab3-117">Explication</span><span class="sxs-lookup"><span data-stu-id="5eab3-117">Explanation</span></span>  
 <span data-ttu-id="5eab3-118">Le client [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne peut pas se connecter au serveur.</span><span class="sxs-lookup"><span data-stu-id="5eab3-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="5eab3-119">Cette erreur s'est peut-être produite parce que le pare-feu sur le serveur a refusé la connexion.</span><span class="sxs-lookup"><span data-stu-id="5eab3-119">This error could occur because the firewall on the server has refused the connection.</span></span> 
  
## <a name="user-action"></a><span data-ttu-id="5eab3-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="5eab3-120">User Action</span></span>  
 <span data-ttu-id="5eab3-121">Assurez-vous que vous avez configuré le pare-feu sur l’instance de serveur de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour accepter les connexions.</span><span class="sxs-lookup"><span data-stu-id="5eab3-121">Make sure that you have configured the firewall on the server instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eab3-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5eab3-122">See Also</span></span>  
 <span data-ttu-id="5eab3-123">[Configurer le pare-feu Windows pour autoriser l’accès SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md) </span><span class="sxs-lookup"><span data-stu-id="5eab3-123">[Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md) </span></span>  
 <span data-ttu-id="5eab3-124">[Configurer un pare-feu Windows pour l’accès Moteur de base de données](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span><span class="sxs-lookup"><span data-stu-id="5eab3-124">[Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span></span>  
 <span data-ttu-id="5eab3-125">[Configurer des protocoles clients](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="5eab3-125">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="5eab3-126">[Protocoles réseau et bibliothèques réseau](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="5eab3-126">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="5eab3-127">[Configuration du réseau client](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="5eab3-127">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="5eab3-128">[Configurer des protocoles clients](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="5eab3-128">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="5eab3-129">Activer ou désactiver un protocole réseau de serveur</span><span class="sxs-lookup"><span data-stu-id="5eab3-129">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
