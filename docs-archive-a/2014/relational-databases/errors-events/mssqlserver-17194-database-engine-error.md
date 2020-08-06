---
title: MSSQLSERVER_17194 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "17194"
helpviewer_keywords:
- 17194 (Database Engine error)
ms.assetid: 0d03eb20-28a7-4ceb-8903-7f9420a620f7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d3f56a104841c4825bba1f60b3588fadd63555c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604531"
---
# <a name="mssqlserver_17194"></a><span data-ttu-id="591c8-102">MSSQLSERVER_17194</span><span class="sxs-lookup"><span data-stu-id="591c8-102">MSSQLSERVER_17194</span></span>
    
## <a name="details"></a><span data-ttu-id="591c8-103">Détails</span><span class="sxs-lookup"><span data-stu-id="591c8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="591c8-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="591c8-104">Product Name</span></span>|<span data-ttu-id="591c8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="591c8-105">SQL Server</span></span>|  
|<span data-ttu-id="591c8-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="591c8-106">Event ID</span></span>|<span data-ttu-id="591c8-107">17194</span><span class="sxs-lookup"><span data-stu-id="591c8-107">17194</span></span>|  
|<span data-ttu-id="591c8-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="591c8-108">Event Source</span></span>|<span data-ttu-id="591c8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="591c8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="591c8-110">Composant</span><span class="sxs-lookup"><span data-stu-id="591c8-110">Component</span></span>|<span data-ttu-id="591c8-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="591c8-111">SQLEngine</span></span>|  
|<span data-ttu-id="591c8-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="591c8-112">Symbolic Name</span></span>||  
|<span data-ttu-id="591c8-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="591c8-113">Message Text</span></span>|<span data-ttu-id="591c8-114">Le serveur n'a pas pu charger la bibliothèque de fournisseurs SSL requise pour la connexion ; cette connexion a été fermée.</span><span class="sxs-lookup"><span data-stu-id="591c8-114">The server was unable to load the SSL provider library needed to log in; the connection has been closed.</span></span> <span data-ttu-id="591c8-115">SSL sert à chiffrer la séquence d'ouverture de session ou l'ensemble des communications, en fonction de la manière dont l'administrateur a configuré le serveur.</span><span class="sxs-lookup"><span data-stu-id="591c8-115">SSL is used to encrypt either the login sequence or all communications, depending on how the administrator has configured the server.</span></span> <span data-ttu-id="591c8-116">Consultez la documentation en ligne pour plus d’informations sur ce message d’erreur :  0xXXXX.</span><span class="sxs-lookup"><span data-stu-id="591c8-116">See Books Online for information on this error message:  0xXXXX.</span></span> <span data-ttu-id="591c8-117">[CLIENT : 11.11.11.11]</span><span class="sxs-lookup"><span data-stu-id="591c8-117">[CLIENT: 11.11.11.11]</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="591c8-118">Explication</span><span class="sxs-lookup"><span data-stu-id="591c8-118">Explanation</span></span>  
 <span data-ttu-id="591c8-119">Cette erreur indique que le client a fermé la connexion.</span><span class="sxs-lookup"><span data-stu-id="591c8-119">This error indicates that the client has closed the connection.</span></span> <span data-ttu-id="591c8-120">Elle peut survenir si le délai de connexion a expiré.</span><span class="sxs-lookup"><span data-stu-id="591c8-120">This error could occur because the connection time-out has expired.</span></span> <span data-ttu-id="591c8-121">Le message d'erreur affiche une valeur provenant du système d'exploitation qui décrit le problème sous-jacent.</span><span class="sxs-lookup"><span data-stu-id="591c8-121">The error message displays a value from the operating system that describes the underlying problem.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="591c8-122">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="591c8-122">User Action</span></span>  
 <span data-ttu-id="591c8-123">Si le code d'erreur dans le message est 0x2746 (valeur décimale 10054), cela signifie que le client a réinitialisé la connexion, généralement suite à un délai d'attente. Pour résoudre l'erreur, augmentez le délai de la connexion sur le client ou le programme appelant.</span><span class="sxs-lookup"><span data-stu-id="591c8-123">If the error code in the message is 0x2746 (decimal value 10054), this means that the connection was reset by the client, typically because of a time-out. To resolve the error, increase the connection time-out on the client or calling program.</span></span>  
  
 <span data-ttu-id="591c8-124">Pour identifier une solution possible pour d’autres valeurs du message d’erreur, utilisez la commande **net helpmsg** du système d’exploitation et précisez la valeur décimale du code d’erreur.</span><span class="sxs-lookup"><span data-stu-id="591c8-124">To determine a possible solution for other error message values, use the operating system command **net helpmsg** and specify the decimal value of the error code.</span></span>  
  
 <span data-ttu-id="591c8-125">Pour plus d’informations sur la connexion à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consultez [Configuration réseau du serveur](../../database-engine/configure-windows/server-network-configuration.md) et [Configuration du réseau client](../../database-engine/configure-windows/client-network-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="591c8-125">For more information about how to connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Server Network Configuration](../../database-engine/configure-windows/server-network-configuration.md) and [Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md).</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="591c8-126">Interne uniquement</span><span class="sxs-lookup"><span data-stu-id="591c8-126">Internal-Only</span></span>  
  
