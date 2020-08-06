---
title: Protocoles clients-propriétés TCP et IP (onglet protocole) | Microsoft Docs
description: Découvrez comment spécifier les options TCP/IP dans Microsoft SQL Server Configuration Manager, telles que le paramètre Keep Alive et le numéro de port par défaut.
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- TCP/IP [SQL Server], client protocols
- client protocols [SQL Server]
ms.assetid: d04f1bce-069c-4a02-b561-c87c3282be36
author: rothja
ms.author: jroth
ms.openlocfilehash: dfcf0348dc863970384a40cc9e773481adeedb35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705815"
---
# <a name="client-protocols---tcp-and-ip-properties-protocol-tab"></a><span data-ttu-id="7a462-103">Protocoles clients - Propriétés TCP/IP (onglet Protocole)</span><span class="sxs-lookup"><span data-stu-id="7a462-103">Client Protocols - TCP and IP Properties (Protocol Tab)</span></span>
  <span data-ttu-id="7a462-104">Dans le Gestionnaire de connexions de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , utilisez l’onglet **Protocole** de la boîte de dialogue **Propriétés TCP/IP** pour afficher ou spécifier les options suivantes.</span><span class="sxs-lookup"><span data-stu-id="7a462-104">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, use the **Protocol** tab on the **TCP/IP Properties** dialog box to view or specify the following options.</span></span> <span data-ttu-id="7a462-105">Pour vous connecter à un autre port, tapez le numéro du port dans la zone **Port par défaut** .</span><span class="sxs-lookup"><span data-stu-id="7a462-105">To connect to a different port, type the port number in the **Default Port** box.</span></span> <span data-ttu-id="7a462-106">Pour plus d’informations sur les chaînes de connexion, consultez [Création d’une chaîne de connexion valide à l’aide du protocole TCP/IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md).</span><span class="sxs-lookup"><span data-stu-id="7a462-106">For more information about connection strings, see [Creating a Valid Connection String Using TCP IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="7a462-107">Options</span><span class="sxs-lookup"><span data-stu-id="7a462-107">Options</span></span>  
 <span data-ttu-id="7a462-108">**Port par défaut**</span><span class="sxs-lookup"><span data-stu-id="7a462-108">**Default Port**</span></span>  
 <span data-ttu-id="7a462-109">Spécifie le port par défaut que la Net-Library TCP/IP essaie d'utiliser pour se connecter à l'instance cible de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a462-109">Specifies the port that the TCP/IP Net-library will use to attempt to connect to the target instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7a462-110">Le port par défaut est 1433.</span><span class="sxs-lookup"><span data-stu-id="7a462-110">The default value port is 1433.</span></span>  
  
 <span data-ttu-id="7a462-111">Lorsqu'un client se connecte à une instance par défaut du [!INCLUDE[ssDE](../../includes/ssde-md.md)], il utilise cette valeur.</span><span class="sxs-lookup"><span data-stu-id="7a462-111">When connecting to a default instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)], the client uses this value.</span></span> <span data-ttu-id="7a462-112">Si une instance par défaut a été configurée pour écouter sur un port différent, remplacez cette valeur par ce numéro de port.</span><span class="sxs-lookup"><span data-stu-id="7a462-112">If a default instance has been configured to listen on a different port, change this value to that port number.</span></span>  
  
 <span data-ttu-id="7a462-113">Lorsqu'un client se connecte à une instance nommée de [!INCLUDE[ssDE](../../includes/ssde-md.md)], il essaie d'obtenir le numéro de port auprès du service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser exécuté sur l'ordinateur serveur.</span><span class="sxs-lookup"><span data-stu-id="7a462-113">When connecting to a named instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)], the client will attempt to obtain the port number from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser Service running on the server computer.</span></span> <span data-ttu-id="7a462-114">Si le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser n'est pas en cours d'exécution, le numéro de port doit être spécifié par le biais de ce paramètre ou dans la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="7a462-114">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser Service is not running, the port number must be provided through this setting, or as part of the connection string.</span></span>  
  
 <span data-ttu-id="7a462-115">**Activé**</span><span class="sxs-lookup"><span data-stu-id="7a462-115">**Enabled**</span></span>  
 <span data-ttu-id="7a462-116">Les valeurs possibles sont **Yes** et **no**.</span><span class="sxs-lookup"><span data-stu-id="7a462-116">Possible values are **Yes** and **No**.</span></span>  
  
 <span data-ttu-id="7a462-117">**Conserver actif**</span><span class="sxs-lookup"><span data-stu-id="7a462-117">**Keep Alive**</span></span>  
 <span data-ttu-id="7a462-118">Ce paramètre (en millisecondes) contrôle la fréquence à laquelle TCP tente de vérifier qu’une connexion inactive est toujours intacte en envoyant un paquet **KEEPALIVE** .</span><span class="sxs-lookup"><span data-stu-id="7a462-118">This parameter (in milliseconds) controls how often TCP attempts to verify that an idle connection is still intact by sending a **KEEPALIVE** packet.</span></span> <span data-ttu-id="7a462-119">La valeur par défaut est 30  000 millisecondes.</span><span class="sxs-lookup"><span data-stu-id="7a462-119">The default is 30000 milliseconds.</span></span>  
  
 <span data-ttu-id="7a462-120">**Intervalle Keep Alive**</span><span class="sxs-lookup"><span data-stu-id="7a462-120">**Keep Alive Interval**</span></span>  
 <span data-ttu-id="7a462-121">Ce paramètre (en millisecondes), détermine l’intervalle qui sépare les retransmissions **KEEPALIVE** jusqu’à ce qu’une réponse soit reçue.</span><span class="sxs-lookup"><span data-stu-id="7a462-121">This parameter (in milliseconds) determines the interval separating **KEEPALIVE** retransmissions until a response is received.</span></span> <span data-ttu-id="7a462-122">La valeur par défaut est 1 000 millisecondes.</span><span class="sxs-lookup"><span data-stu-id="7a462-122">The default is 1000 milliseconds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a462-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7a462-123">See Also</span></span>  
 <span data-ttu-id="7a462-124">[Choix d’un protocole réseau](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="7a462-124">[Choosing a Network Protocol](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span></span>  
 <span data-ttu-id="7a462-125">[Nouvel alias &#40;onglet alias&#41;](../../../2014/tools/configuration-manager/new-alias-alias-tab.md) </span><span class="sxs-lookup"><span data-stu-id="7a462-125">[New Alias &#40;Alias Tab&#41;](../../../2014/tools/configuration-manager/new-alias-alias-tab.md) </span></span>  
 [<span data-ttu-id="7a462-126">Propriétés d’&#60;alias&#62; &#40;onglet Alias&#41;</span><span class="sxs-lookup"><span data-stu-id="7a462-126">&#60;Alias&#62; Properties &#40;Alias Tab&#41;</span></span>](../../../2014/tools/configuration-manager/alias-properties-alias-tab.md)  
  
  
