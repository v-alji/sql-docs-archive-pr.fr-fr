---
title: MSSQLSERVER_11001 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "12001"
helpviewer_keywords:
- 11001 (Database Engine error)
ms.assetid: 53d4d63a-61e3-441f-bfe9-9d44f7a05fd4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da7dd171d1b6a64e0cc1666eda1e3593a81eece1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612923"
---
# <a name="mssqlserver_11001"></a><span data-ttu-id="81b05-102">MSSQLSERVER_11001</span><span class="sxs-lookup"><span data-stu-id="81b05-102">MSSQLSERVER_11001</span></span>
    
## <a name="details"></a><span data-ttu-id="81b05-103">Détails</span><span class="sxs-lookup"><span data-stu-id="81b05-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="81b05-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="81b05-104">Product Name</span></span>|<span data-ttu-id="81b05-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="81b05-105">SQL Server</span></span>|  
|<span data-ttu-id="81b05-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="81b05-106">Event ID</span></span>|<span data-ttu-id="81b05-107">11001</span><span class="sxs-lookup"><span data-stu-id="81b05-107">11001</span></span>|  
|<span data-ttu-id="81b05-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="81b05-108">Event Source</span></span>|<span data-ttu-id="81b05-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="81b05-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="81b05-110">Composant</span><span class="sxs-lookup"><span data-stu-id="81b05-110">Component</span></span>|<span data-ttu-id="81b05-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="81b05-111">SQLEngine</span></span>|  
|<span data-ttu-id="81b05-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="81b05-112">Symbolic Name</span></span>||  
|<span data-ttu-id="81b05-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="81b05-113">Message Text</span></span>|<span data-ttu-id="81b05-114">Une erreur s'est produite lors de l'établissement d'une connexion au serveur.</span><span class="sxs-lookup"><span data-stu-id="81b05-114">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="81b05-115">Lors de la connexion à SQL Server, cet échec peut être dû au fait que les paramètres par défaut de SQL Server n'autorisent pas les connexions à distance.</span><span class="sxs-lookup"><span data-stu-id="81b05-115">When connecting to SQL Server, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.</span></span> <span data-ttu-id="81b05-116">(fournisseur : Fournisseur TCP, erreur : 0 – Hôte inconnu) (Fournisseur de données SqlClient .Net)</span><span class="sxs-lookup"><span data-stu-id="81b05-116">(provider: TCP Provider, error: 0 - No such host is known.) (.Net SqlClient Data Provider)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="81b05-117">Explication</span><span class="sxs-lookup"><span data-stu-id="81b05-117">Explanation</span></span>  
 <span data-ttu-id="81b05-118">Le client [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne peut pas se connecter au serveur.</span><span class="sxs-lookup"><span data-stu-id="81b05-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="81b05-119">Cette erreur s'est peut-être produite parce que le client ne peut pas résoudre le nom du serveur ou le nom du serveur est incorrect.</span><span class="sxs-lookup"><span data-stu-id="81b05-119">The error could occur because either the client cannot resolve the name of the server or the name of the server is incorrect.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="81b05-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="81b05-120">User Action</span></span>  
 <span data-ttu-id="81b05-121">Assurez-vous que vous avez entré le nom de serveur correct sur le client et que vous pouvez résoudre ce nom à partir du client.</span><span class="sxs-lookup"><span data-stu-id="81b05-121">Make sure that you have entered the correct server name on the client, and that you can resolve the name of the server from the client.</span></span> <span data-ttu-id="81b05-122">Pour vérifier la résolution du nom TCP/IP, vous pouvez exécuter la commande **ping** dans le système d’exploitation Windows.</span><span class="sxs-lookup"><span data-stu-id="81b05-122">To check TCP/IP name resolution, you can use the **ping** command in the Windows operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81b05-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="81b05-123">See Also</span></span>  
 <span data-ttu-id="81b05-124">[Protocoles réseau et bibliothèques réseau](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="81b05-124">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="81b05-125">[Configuration du réseau client](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="81b05-125">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="81b05-126">[Configurer des protocoles clients](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="81b05-126">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="81b05-127">Activer ou désactiver un protocole réseau de serveur</span><span class="sxs-lookup"><span data-stu-id="81b05-127">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
