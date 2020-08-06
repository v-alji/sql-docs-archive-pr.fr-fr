---
title: MSSQLSERVER_10060 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "10060"
helpviewer_keywords:
- 10060 (Database Engine error)
ms.assetid: 28c21277-cad8-406c-a955-07933a56982a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d634cfb06381fb916ef2e421e0677e76edb9ae02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706544"
---
# <a name="mssqlserver_10060"></a><span data-ttu-id="9795b-102">MSSQLSERVER_10060</span><span class="sxs-lookup"><span data-stu-id="9795b-102">MSSQLSERVER_10060</span></span>
    
## <a name="details"></a><span data-ttu-id="9795b-103">Détails</span><span class="sxs-lookup"><span data-stu-id="9795b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9795b-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="9795b-104">Product Name</span></span>|<span data-ttu-id="9795b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9795b-105">SQL Server</span></span>|  
|<span data-ttu-id="9795b-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="9795b-106">Event ID</span></span>|<span data-ttu-id="9795b-107">10060</span><span class="sxs-lookup"><span data-stu-id="9795b-107">10060</span></span>|  
|<span data-ttu-id="9795b-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="9795b-108">Event Source</span></span>|<span data-ttu-id="9795b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9795b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9795b-110">Composant</span><span class="sxs-lookup"><span data-stu-id="9795b-110">Component</span></span>|<span data-ttu-id="9795b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9795b-111">SQLEngine</span></span>|  
|<span data-ttu-id="9795b-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="9795b-112">Symbolic Name</span></span>||  
|<span data-ttu-id="9795b-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="9795b-113">Message Text</span></span>|<span data-ttu-id="9795b-114">Une erreur s'est produite lors de l'établissement d'une connexion au serveur.</span><span class="sxs-lookup"><span data-stu-id="9795b-114">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="9795b-115">Lors de la connexion à SQL Server, cet échec peut être dû au fait que les paramètres par défaut de SQL Server n'autorisent pas les connexions à distance.</span><span class="sxs-lookup"><span data-stu-id="9795b-115">When connecting to SQL Server, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.</span></span> <span data-ttu-id="9795b-116">(fournisseur : Fournisseur TCP, erreur : 0 - Une tentative de connexion a échoué car le participant connecté n’a pas répondu convenablement au-delà d’une certaine durée, ou une connexion établie a échoué car l’hôte de connexion n’a pas répondu.) (Microsoft SQL Server, Erreur : 10060)</span><span class="sxs-lookup"><span data-stu-id="9795b-116">(provider: TCP Provider, error: 0 - A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.) (Microsoft SQL Server, Error: 10060)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9795b-117">Explication</span><span class="sxs-lookup"><span data-stu-id="9795b-117">Explanation</span></span>  
 <span data-ttu-id="9795b-118">Le client [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne peut pas se connecter au serveur.</span><span class="sxs-lookup"><span data-stu-id="9795b-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="9795b-119">Cette erreur s'est peut-être produite parce que le pare-feu sur le serveur a refusé la connexion ou le serveur n'est pas configuré pour accepter des connexions distantes.</span><span class="sxs-lookup"><span data-stu-id="9795b-119">This error could occur because either the firewall on the server has refused the connection or the server is not configured to accept remote connections.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9795b-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="9795b-120">User Action</span></span>  
 <span data-ttu-id="9795b-121">Pour résoudre cette erreur, essayez d'effectuer l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="9795b-121">To resolve this error, try one of the following actions:</span></span>  
  
-   <span data-ttu-id="9795b-122">Assurez-vous d'avoir configuré le pare-feu sur l'ordinateur afin de permettre à cette instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] d'accepter les connexions.</span><span class="sxs-lookup"><span data-stu-id="9795b-122">Make sure that you have configured the firewall on the computer to allow this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept connections.</span></span>  
  
-   <span data-ttu-id="9795b-123">Utilisez l'outil Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour permettre à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] d'accepter des connexions distantes.</span><span class="sxs-lookup"><span data-stu-id="9795b-123">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager tool to allow [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept remote connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9795b-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9795b-124">See Also</span></span>  
 <span data-ttu-id="9795b-125">[Configurer un pare-feu Windows pour l’accès Moteur de base de données](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span><span class="sxs-lookup"><span data-stu-id="9795b-125">[Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span></span>  
 <span data-ttu-id="9795b-126">[Configurer des protocoles clients](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="9795b-126">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="9795b-127">[Protocoles réseau et bibliothèques réseau](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="9795b-127">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="9795b-128">[Configuration du réseau client](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="9795b-128">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="9795b-129">[Configurer des protocoles clients](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="9795b-129">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="9795b-130">Activer ou désactiver un protocole réseau de serveur</span><span class="sxs-lookup"><span data-stu-id="9795b-130">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
