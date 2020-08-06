---
title: MSSQLSERVER_2 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "2"
helpviewer_keywords:
- 2 (Database Engine error)
ms.assetid: 567fb571-7cda-4ce8-a702-cdff2df5d419
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 87d19a24219fda79de2cad4c06af4f1936b37b24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612881"
---
# <a name="mssqlserver_2"></a><span data-ttu-id="b7f55-102">MSSQLSERVER_2</span><span class="sxs-lookup"><span data-stu-id="b7f55-102">MSSQLSERVER_2</span></span>
    
## <a name="details"></a><span data-ttu-id="b7f55-103">Détails</span><span class="sxs-lookup"><span data-stu-id="b7f55-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b7f55-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="b7f55-104">Product Name</span></span>|<span data-ttu-id="b7f55-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b7f55-105">SQL Server</span></span>|  
|<span data-ttu-id="b7f55-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="b7f55-106">Event ID</span></span>|<span data-ttu-id="b7f55-107">2</span><span class="sxs-lookup"><span data-stu-id="b7f55-107">2</span></span>|  
|<span data-ttu-id="b7f55-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="b7f55-108">Event Source</span></span>|<span data-ttu-id="b7f55-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b7f55-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b7f55-110">Composant</span><span class="sxs-lookup"><span data-stu-id="b7f55-110">Component</span></span>|<span data-ttu-id="b7f55-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b7f55-111">SQLEngine</span></span>|  
|<span data-ttu-id="b7f55-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="b7f55-112">Symbolic Name</span></span>||  
|<span data-ttu-id="b7f55-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="b7f55-113">Message Text</span></span>|<span data-ttu-id="b7f55-114">Une erreur s'est produite lors de l'établissement d'une connexion au serveur.</span><span class="sxs-lookup"><span data-stu-id="b7f55-114">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="b7f55-115">Lors de la connexion à SQL Server, cet échec peut être dû au fait que les paramètres par défaut de SQL Server n'autorisent pas les connexions à distance.</span><span class="sxs-lookup"><span data-stu-id="b7f55-115">When connecting to SQL Server, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.</span></span> <span data-ttu-id="b7f55-116">(fournisseur : Fournisseur de canaux nommés, erreur : 40 - Impossible d’ouvrir une connexion à SQL Server) (Fournisseur de données SqlClient .Net).</span><span class="sxs-lookup"><span data-stu-id="b7f55-116">(provider: Named Pipes Provider, error: 40 - Could not open a connection to SQL Server) (.Net SqlClient Data Provider)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b7f55-117">Explication</span><span class="sxs-lookup"><span data-stu-id="b7f55-117">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b7f55-118">n’a pas répondu à la demande du client parce que le serveur n’a probablement pas été démarré.</span><span class="sxs-lookup"><span data-stu-id="b7f55-118">did not respond to the client request because the server is probably not started.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b7f55-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="b7f55-119">User Action</span></span>  
 <span data-ttu-id="b7f55-120">Assurez-vous que le serveur a été démarré.</span><span class="sxs-lookup"><span data-stu-id="b7f55-120">Make sure that the server is started.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7f55-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b7f55-121">See Also</span></span>  
 <span data-ttu-id="b7f55-122">[Gérer les services du moteur de base de données](../../database-engine/configure-windows/manage-the-database-engine-services.md) </span><span class="sxs-lookup"><span data-stu-id="b7f55-122">[Manage the Database Engine Services](../../database-engine/configure-windows/manage-the-database-engine-services.md) </span></span>  
 <span data-ttu-id="b7f55-123">[Configurer des protocoles clients](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="b7f55-123">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="b7f55-124">[Protocoles réseau et bibliothèques réseau](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="b7f55-124">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="b7f55-125">[Configuration du réseau client](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="b7f55-125">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="b7f55-126">[Configurer des protocoles clients](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="b7f55-126">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="b7f55-127">Activer ou désactiver un protocole réseau de serveur</span><span class="sxs-lookup"><span data-stu-id="b7f55-127">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
