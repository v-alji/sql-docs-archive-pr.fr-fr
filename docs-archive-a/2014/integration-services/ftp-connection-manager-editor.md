---
title: Éditeur du gestionnaire de connexions FTP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ftpconnectionmanager.f1
helpviewer_keywords:
- FTP Connection Manager Editor
ms.assetid: 874b6585-255b-4a43-8396-bb08c3e8ac2b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d14635a4d90c267801f6d372dda5c7bcc7f4869f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710727"
---
# <a name="ftp-connection-manager-editor"></a><span data-ttu-id="ed4a5-102">Éditeur du gestionnaire de connexions FTP</span><span class="sxs-lookup"><span data-stu-id="ed4a5-102">FTP Connection Manager Editor</span></span>
  <span data-ttu-id="ed4a5-103">La boîte de dialogue **Éditeur du gestionnaire de connexions FTP** vous permet de spécifier les propriétés de connexion à un serveur FTP.</span><span class="sxs-lookup"><span data-stu-id="ed4a5-103">Use the **FTP Connection Manager Editor** dialog box to specify properties for connecting to an FTP server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ed4a5-104">Le gestionnaire de connexions FTP prend en charge uniquement l'authentification anonyme et l'authentification de base.</span><span class="sxs-lookup"><span data-stu-id="ed4a5-104">The FTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="ed4a5-105">Il ne prend pas en charge l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="ed4a5-105">It does not support Windows Authentication.</span></span>  
  
 <span data-ttu-id="ed4a5-106">Pour en savoir plus sur le gestionnaire de connexions FTP, consultez [Gestionnaire de connexions FTP](connection-manager/ftp-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="ed4a5-106">To learn more about the FTP connection manager, see [FTP Connection Manager](connection-manager/ftp-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ed4a5-107">Options</span><span class="sxs-lookup"><span data-stu-id="ed4a5-107">Options</span></span>  
 <span data-ttu-id="ed4a5-108">**Nom du serveur**</span><span class="sxs-lookup"><span data-stu-id="ed4a5-108">**Server name**</span></span>  
 <span data-ttu-id="ed4a5-109">Indiquez le nom du serveur FTP.</span><span class="sxs-lookup"><span data-stu-id="ed4a5-109">Provide the name of the FTP server.</span></span>  
  
 <span data-ttu-id="ed4a5-110">**Port du serveur**</span><span class="sxs-lookup"><span data-stu-id="ed4a5-110">**Server port**</span></span>  
 <span data-ttu-id="ed4a5-111">Spécifiez le numéro de port sur le serveur FTP à utiliser pour la connexion.</span><span class="sxs-lookup"><span data-stu-id="ed4a5-111">Specify the port number on the FTP server to use for the connection.</span></span> <span data-ttu-id="ed4a5-112">La valeur par défaut de cette propriété est **21**.</span><span class="sxs-lookup"><span data-stu-id="ed4a5-112">The default value of this property is **21**.</span></span>  
  
 <span data-ttu-id="ed4a5-113">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="ed4a5-113">**User name**</span></span>  
 <span data-ttu-id="ed4a5-114">Indiquez un nom d'utilisateur pour accéder au serveur FTP.</span><span class="sxs-lookup"><span data-stu-id="ed4a5-114">Provide a user name to access the FTP server.</span></span> <span data-ttu-id="ed4a5-115">La valeur par défaut de cette propriété est **anonyme**.</span><span class="sxs-lookup"><span data-stu-id="ed4a5-115">The default value of this property is **anonymous**.</span></span>  
  
 <span data-ttu-id="ed4a5-116">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="ed4a5-116">**Password**</span></span>  
 <span data-ttu-id="ed4a5-117">Indiquez le mot de passe permettant d'accéder au serveur FTP.</span><span class="sxs-lookup"><span data-stu-id="ed4a5-117">Provide the password to access the FTP server.</span></span>  
  
 <span data-ttu-id="ed4a5-118">**Délai d'expiration (en secondes)**</span><span class="sxs-lookup"><span data-stu-id="ed4a5-118">**Time-out (in seconds)**</span></span>  
 <span data-ttu-id="ed4a5-119">Spécifiez le nombre de secondes que prend la tâche avant l’expiration du délai d’attente. La valeur **0** indique une durée infinie.</span><span class="sxs-lookup"><span data-stu-id="ed4a5-119">Specify the number of seconds the task takes before timing out. A value of **0** indicates an infinite amount of time.</span></span> <span data-ttu-id="ed4a5-120">La valeur par défaut de cette propriété est **60**.</span><span class="sxs-lookup"><span data-stu-id="ed4a5-120">The default value of this property is **60**.</span></span>  
  
 <span data-ttu-id="ed4a5-121">**Utiliser le mode passif**</span><span class="sxs-lookup"><span data-stu-id="ed4a5-121">**Use passive mode**</span></span>  
 <span data-ttu-id="ed4a5-122">Permet de spécifier si le serveur ou le client initie la connexion.</span><span class="sxs-lookup"><span data-stu-id="ed4a5-122">Specify whether the server or the client initiates the connection.</span></span> <span data-ttu-id="ed4a5-123">Le serveur initie la connexion en mode actif, alors que le client l'initie en mode passif.</span><span class="sxs-lookup"><span data-stu-id="ed4a5-123">The server initiates the connection in active mode, and the client activates the connection in passive mode.</span></span> <span data-ttu-id="ed4a5-124">La valeur par défaut de cette propriété est **mode actif**.</span><span class="sxs-lookup"><span data-stu-id="ed4a5-124">The default value of this property is **active mode**.</span></span>  
  
 <span data-ttu-id="ed4a5-125">**Nouvelle tentatives**</span><span class="sxs-lookup"><span data-stu-id="ed4a5-125">**Retries**</span></span>  
 <span data-ttu-id="ed4a5-126">Spécifiez le nombre de fois que la tâche doit tenter d'établir une connexion.</span><span class="sxs-lookup"><span data-stu-id="ed4a5-126">Specify the number of times the task attempts to make a connection.</span></span> <span data-ttu-id="ed4a5-127">Une valeur égale à **0** indique un nombre illimité de tentatives.</span><span class="sxs-lookup"><span data-stu-id="ed4a5-127">A value of **0** indicates no limit to the number of attempts.</span></span>  
  
 <span data-ttu-id="ed4a5-128">**Taille de segment (en Ko)**</span><span class="sxs-lookup"><span data-stu-id="ed4a5-128">**Chunk size (in KB)**</span></span>  
 <span data-ttu-id="ed4a5-129">Spécifiez une taille de segment en kilo-octets pour la transmission des données.</span><span class="sxs-lookup"><span data-stu-id="ed4a5-129">Provide a chunk size in kilobytes for transmitting data.</span></span>  
  
 <span data-ttu-id="ed4a5-130">**Tester la connexion**</span><span class="sxs-lookup"><span data-stu-id="ed4a5-130">**Test Connection**</span></span>  
 <span data-ttu-id="ed4a5-131">Après avoir configuré le gestionnaire de connexions FTP, confirmez que la connexion est viable en cliquant sur **Tester la connexion**.</span><span class="sxs-lookup"><span data-stu-id="ed4a5-131">After configuring the FTP Connection Manager, confirm that the connection is viable by clicking **Test Connection**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed4a5-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ed4a5-132">See Also</span></span>  
 [<span data-ttu-id="ed4a5-133">Guide de référence des erreurs et des messages propres à Integration Services</span><span class="sxs-lookup"><span data-stu-id="ed4a5-133">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
