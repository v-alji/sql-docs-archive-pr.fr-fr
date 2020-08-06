---
title: MSSQLSERVER_-1 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "-1"
helpviewer_keywords:
- -1 (Database Engine error)
ms.assetid: bad25b91-eaed-46c0-a5b7-71117a32304c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 880212b1d2e9572bbb31535a5ba68b445c7e6f35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704119"
---
# <a name="mssqlserver_-1"></a><span data-ttu-id="b9317-102">MSSQLSERVER_-1</span><span class="sxs-lookup"><span data-stu-id="b9317-102">MSSQLSERVER_-1</span></span>
    
## <a name="details"></a><span data-ttu-id="b9317-103">Détails</span><span class="sxs-lookup"><span data-stu-id="b9317-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b9317-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="b9317-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="b9317-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="b9317-105">Event ID</span></span>|<span data-ttu-id="b9317-106">-1</span><span class="sxs-lookup"><span data-stu-id="b9317-106">-1</span></span>|  
|<span data-ttu-id="b9317-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="b9317-107">Event Source</span></span>|<span data-ttu-id="b9317-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b9317-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b9317-109">Composant</span><span class="sxs-lookup"><span data-stu-id="b9317-109">Component</span></span>|<span data-ttu-id="b9317-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b9317-110">SQLEngine</span></span>|  
|<span data-ttu-id="b9317-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="b9317-111">Symbolic Name</span></span>||  
|<span data-ttu-id="b9317-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="b9317-112">Message Text</span></span>|<span data-ttu-id="b9317-113">Une erreur s'est produite lors de l'établissement d'une connexion au serveur.</span><span class="sxs-lookup"><span data-stu-id="b9317-113">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="b9317-114">Lors de la connexion à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], cette erreur est peut être due au fait que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] n'autorise pas les connexions distantes selon les paramètres par défaut.</span><span class="sxs-lookup"><span data-stu-id="b9317-114">When connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], this failure may be caused by the fact that under the default settings [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not allow remote connections.</span></span> <span data-ttu-id="b9317-115">(fournisseur : interfaces réseau SQL, erreur : 28 - Le serveur ne prend pas en charge le protocole demandé) (Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], erreur : -1)</span><span class="sxs-lookup"><span data-stu-id="b9317-115">(provider: SQL Network Interfaces, error: 28 - Server doesn't support requested protocol) (Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Error: -1)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b9317-116">Explication</span><span class="sxs-lookup"><span data-stu-id="b9317-116">Explanation</span></span>  
 <span data-ttu-id="b9317-117">Le client [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne peut pas se connecter au serveur.</span><span class="sxs-lookup"><span data-stu-id="b9317-117">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="b9317-118">Cette erreur peut être causée par l'une des raisons suivantes :</span><span class="sxs-lookup"><span data-stu-id="b9317-118">This error could be caused by one of the following reasons:</span></span>  
  
-   <span data-ttu-id="b9317-119">Le nom d'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] spécifié n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="b9317-119">A specified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name is not valid.</span></span>  
  
-   <span data-ttu-id="b9317-120">Les protocoles TCP ou de canaux nommés ne sont pas activés.</span><span class="sxs-lookup"><span data-stu-id="b9317-120">The TCP, or named pipes protocols are not enabled.</span></span>  
  
-   <span data-ttu-id="b9317-121">Le pare-feu sur le serveur a refusé la connexion.</span><span class="sxs-lookup"><span data-stu-id="b9317-121">The firewall on the server has refused the connection.</span></span>  
  
-   <span data-ttu-id="b9317-122">Le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser (sqlbrowser) n’est pas démarré.</span><span class="sxs-lookup"><span data-stu-id="b9317-122">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service (sqlbrowser) is not started.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b9317-123">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="b9317-123">User Action</span></span>  
 <span data-ttu-id="b9317-124">Pour résoudre cette erreur, essayez d'effectuer l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="b9317-124">To resolve this error, try one of the following actions:</span></span>  
  
-   <span data-ttu-id="b9317-125">Vérifiez l'orthographe du nom de l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] spécifié dans la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="b9317-125">Check the spelling of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name that is specified in the connection string.</span></span>  
  
-   <span data-ttu-id="b9317-126">Utilisez l’outil Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour faire en sorte que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] accepte les connexions distantes par l’intermédiaire des protocoles TCP ou de canaux nommés.</span><span class="sxs-lookup"><span data-stu-id="b9317-126">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager tool to enable [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept remote connections over the TCP or named pipes protocols.</span></span>  
  
-   <span data-ttu-id="b9317-127">Veillez à configurer le pare-feu sur l’instance de serveur de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] afin d’ouvrir des ports pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et le port [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser (UDP 1434).</span><span class="sxs-lookup"><span data-stu-id="b9317-127">Make sure that you have configured the firewall on the server instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to open ports for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser port (UDP 1434).</span></span>  
  
-   <span data-ttu-id="b9317-128">Assurez-vous que le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser est démarré sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="b9317-128">Make sure that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service is started on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9317-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b9317-129">See Also</span></span>  
 <span data-ttu-id="b9317-130">[Configurer un pare-feu Windows pour l’accès Moteur de base de données](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span><span class="sxs-lookup"><span data-stu-id="b9317-130">[Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span></span>  
 <span data-ttu-id="b9317-131">[Configurer des protocoles clients](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="b9317-131">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="b9317-132">[Protocoles réseau et bibliothèques réseau](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="b9317-132">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="b9317-133">[Configuration du réseau client](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="b9317-133">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="b9317-134">[Configurer des protocoles clients](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="b9317-134">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="b9317-135">Activer ou désactiver un protocole réseau de serveur</span><span class="sxs-lookup"><span data-stu-id="b9317-135">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
