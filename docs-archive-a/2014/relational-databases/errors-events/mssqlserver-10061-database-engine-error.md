---
title: MSSQLSERVER_10061 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "10061"
helpviewer_keywords:
- 10061 (Database Engine error)
ms.assetid: 729602f3-08df-474c-8740-8dea13c1eee3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0c866bd8dce01f65036f1d508a94252a97613424
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704112"
---
# <a name="mssqlserver_10061"></a><span data-ttu-id="0ffd9-102">MSSQLSERVER_10061</span><span class="sxs-lookup"><span data-stu-id="0ffd9-102">MSSQLSERVER_10061</span></span>
    
## <a name="details"></a><span data-ttu-id="0ffd9-103">Détails</span><span class="sxs-lookup"><span data-stu-id="0ffd9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0ffd9-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="0ffd9-104">Product Name</span></span>|<span data-ttu-id="0ffd9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0ffd9-105">SQL Server</span></span>|  
|<span data-ttu-id="0ffd9-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="0ffd9-106">Event ID</span></span>|<span data-ttu-id="0ffd9-107">10061</span><span class="sxs-lookup"><span data-stu-id="0ffd9-107">10061</span></span>|  
|<span data-ttu-id="0ffd9-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="0ffd9-108">Event Source</span></span>|<span data-ttu-id="0ffd9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0ffd9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0ffd9-110">Composant</span><span class="sxs-lookup"><span data-stu-id="0ffd9-110">Component</span></span>|<span data-ttu-id="0ffd9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0ffd9-111">SQLEngine</span></span>|  
|<span data-ttu-id="0ffd9-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="0ffd9-112">Symbolic Name</span></span>||  
|<span data-ttu-id="0ffd9-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="0ffd9-113">Message Text</span></span>|<span data-ttu-id="0ffd9-114">Une erreur s'est produite lors de l'établissement d'une connexion au serveur.</span><span class="sxs-lookup"><span data-stu-id="0ffd9-114">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="0ffd9-115">Lors de la connexion à SQL Server, cet échec peut être dû au fait que les paramètres par défaut de SQL Server n'autorisent pas les connexions à distance.</span><span class="sxs-lookup"><span data-stu-id="0ffd9-115">When connecting to SQL Server, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.</span></span> <span data-ttu-id="0ffd9-116">(fournisseur : Fournisseur TCP, erreur : 0 - Aucune connexion n’a pu être établie, car l’ordinateur cible l’a expressément refusée.) (Microsoft SQL Server, Erreur: 10061)</span><span class="sxs-lookup"><span data-stu-id="0ffd9-116">(provider: TCP Provider, error: 0 - No connection could be made because the target machine actively refused it.) (Microsoft SQL Server, Error: 10061)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0ffd9-117">Explication</span><span class="sxs-lookup"><span data-stu-id="0ffd9-117">Explanation</span></span>  
 <span data-ttu-id="0ffd9-118">Le serveur n'a pas répondu à la demande du client.</span><span class="sxs-lookup"><span data-stu-id="0ffd9-118">The server did not respond to the client request.</span></span> <span data-ttu-id="0ffd9-119">Cette erreur s'est peut-être produite parce que le serveur n'a pas été démarré.</span><span class="sxs-lookup"><span data-stu-id="0ffd9-119">This error could occur because the server is not started.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0ffd9-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="0ffd9-120">User Action</span></span>  
 <span data-ttu-id="0ffd9-121">Assurez-vous que le serveur a été démarré.</span><span class="sxs-lookup"><span data-stu-id="0ffd9-121">Make sure that the server is started.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ffd9-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0ffd9-122">See Also</span></span>  
 <span data-ttu-id="0ffd9-123">[Gérer les services du moteur de base de données](../../database-engine/configure-windows/manage-the-database-engine-services.md) </span><span class="sxs-lookup"><span data-stu-id="0ffd9-123">[Manage the Database Engine Services](../../database-engine/configure-windows/manage-the-database-engine-services.md) </span></span>  
 <span data-ttu-id="0ffd9-124">[Configurer des protocoles clients](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="0ffd9-124">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="0ffd9-125">[Protocoles réseau et bibliothèques réseau](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="0ffd9-125">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="0ffd9-126">[Configuration du réseau client](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="0ffd9-126">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="0ffd9-127">[Configurer des protocoles clients](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="0ffd9-127">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="0ffd9-128">Activer ou désactiver un protocole réseau de serveur</span><span class="sxs-lookup"><span data-stu-id="0ffd9-128">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
