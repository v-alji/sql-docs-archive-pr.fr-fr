---
title: Gestionnaire de connexions FTP | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- FTP connection manager
- connections [Integration Services], FTP
- connection managers [Integration Services], FTP
ms.assetid: c4f43455-29ca-44ba-ac7f-ea729b1daf93
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a402f399ba4b7e69fc1d3cbca9dd64b32217ced1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697079"
---
# <a name="ftp-connection-manager"></a><span data-ttu-id="ea051-102">Gestionnaires de connexion FTP</span><span class="sxs-lookup"><span data-stu-id="ea051-102">FTP Connection Manager</span></span>
  <span data-ttu-id="ea051-103">Un gestionnaire de connexions FTP permet à un package de se connecter à un serveur FTP (File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="ea051-103">An FTP connection manager enables a package to connect to a File Transfer Protocol (FTP) server.</span></span> <span data-ttu-id="ea051-104">La tâche FTP incluse dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] utilise ce gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="ea051-104">The FTP task that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses this connection manager.</span></span>  
  
 <span data-ttu-id="ea051-105">Lorsque vous ajoutez un gestionnaire de connexions FTP à un package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crée un gestionnaire de connexions qui peut être résolu en tant que connexion FTP au moment de l'exécution, définit les propriétés du gestionnaire de connexions et ajoute le gestionnaire de connexions à la collection `Connections` sur le package.</span><span class="sxs-lookup"><span data-stu-id="ea051-105">When you add an FTP connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that can be resolved as an FTP connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="ea051-106">La propriété `ConnectionManagerType` du gestionnaire de connexions a pour valeur `FTP`.</span><span class="sxs-lookup"><span data-stu-id="ea051-106">The `ConnectionManagerType` property of the connection manager is set to `FTP`.</span></span>  
  
 <span data-ttu-id="ea051-107">Vous pouvez configurer le gestionnaire de connexions FTP de plusieurs manières :</span><span class="sxs-lookup"><span data-stu-id="ea051-107">You can configure the FTP connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="ea051-108">Spécifiez un nom de serveur et un port de serveur.</span><span class="sxs-lookup"><span data-stu-id="ea051-108">Specify a server name and server port.</span></span>  
  
-   <span data-ttu-id="ea051-109">Spécifiez l'accès anonyme ou fournissez un nom d'utilisateur et un mot de passe pour l'authentification de base.</span><span class="sxs-lookup"><span data-stu-id="ea051-109">Specify anonymous access, or provide a user name and a password for basic authentication.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="ea051-110">Le gestionnaire de connexions FTP prend en charge uniquement l'authentification anonyme et l'authentification de base.</span><span class="sxs-lookup"><span data-stu-id="ea051-110">The FTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="ea051-111">Il ne prend pas en charge l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="ea051-111">It does not support Windows Authentication.</span></span>  
  
-   <span data-ttu-id="ea051-112">Définissez le délai d'attente, le nombre de nouvelles tentatives et la quantité de données à copier en une fois.</span><span class="sxs-lookup"><span data-stu-id="ea051-112">Set the time-out, number of retries, and the amount of data to copy at a time.</span></span>  
  
-   <span data-ttu-id="ea051-113">Indiquez si le gestionnaire de connexions FTP utilise le mode actif ou passif.</span><span class="sxs-lookup"><span data-stu-id="ea051-113">Indicate whether the FTP connection manager uses passive or active mode.</span></span>  
  
 <span data-ttu-id="ea051-114">Selon la configuration du site FTP auquel le gestionnaire de connexions FTP se connecte, vous devrez éventuellement changer les valeurs par défaut suivantes du gestionnaire de connexions :</span><span class="sxs-lookup"><span data-stu-id="ea051-114">Depending on the configuration of the FTP site to which the FTP connection manager connects, you may need to change the following default values of the connection manager:</span></span>  
  
-   <span data-ttu-id="ea051-115">Le port du serveur est réglé sur 21.</span><span class="sxs-lookup"><span data-stu-id="ea051-115">The server port is set to 21.</span></span> <span data-ttu-id="ea051-116">Vous devez spécifier le port que le site FTP écoute.</span><span class="sxs-lookup"><span data-stu-id="ea051-116">You should specify the port that the FTP site listens to.</span></span>  
  
-   <span data-ttu-id="ea051-117">Le nom d'utilisateur prend la valeur « anonymous ».</span><span class="sxs-lookup"><span data-stu-id="ea051-117">The user name is set to "anonymous".</span></span> <span data-ttu-id="ea051-118">Vous devez fournir les informations d'identification requises par le site FTP.</span><span class="sxs-lookup"><span data-stu-id="ea051-118">You should provide the credentials that the FTP site requires.</span></span>  
  
## <a name="activepassive-modes"></a><span data-ttu-id="ea051-119">Modes actif/passif</span><span class="sxs-lookup"><span data-stu-id="ea051-119">Active/Passive Modes</span></span>  
 <span data-ttu-id="ea051-120">Un gestionnaire de connexions FTP peut envoyer et recevoir des fichiers en mode actif ou passif.</span><span class="sxs-lookup"><span data-stu-id="ea051-120">An FTP connection manager can send and receive files using either active mode or passive mode.</span></span> <span data-ttu-id="ea051-121">En mode actif, le serveur initie la connexion de données, alors qu'en mode passif il s'agit du client.</span><span class="sxs-lookup"><span data-stu-id="ea051-121">In active mode, the server initiates the data connection, and in passive mode, the client initiates the data connection.</span></span>  
  
## <a name="configuration-of-the-ftp-connection-manager"></a><span data-ttu-id="ea051-122">Configuration du gestionnaire de connexions FTP</span><span class="sxs-lookup"><span data-stu-id="ea051-122">Configuration of the FTP Connection Manager</span></span>  
 <span data-ttu-id="ea051-123">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="ea051-123">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="ea051-124">Pour plus d’informations sur les propriétés que vous pouvez définir dans le Concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , consultez [Éditeur du gestionnaire de connexions FTP](../ftp-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="ea051-124">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [FTP Connection Manager Editor](../ftp-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="ea051-125">Pour plus d’informations sur la configuration d’un gestionnaire de connexions par programmation, consultez <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> et [Ajout de connexions par programme](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="ea051-125">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea051-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ea051-126">See Also</span></span>  
 <span data-ttu-id="ea051-127">[Tâche FTP](../control-flow/ftp-task.md) </span><span class="sxs-lookup"><span data-stu-id="ea051-127">[FTP Task](../control-flow/ftp-task.md) </span></span>  
 [<span data-ttu-id="ea051-128">Connexions Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="ea051-128">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
