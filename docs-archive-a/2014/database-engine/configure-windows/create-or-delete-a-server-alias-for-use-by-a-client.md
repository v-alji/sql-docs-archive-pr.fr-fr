---
title: Créer ou supprimer un alias de serveur devant être utilisé par un client (Gestionnaire de configuration SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- server alias
helpviewer_keywords:
- aliases [SQL Server], deleting
- aliases [SQL Server], creating
ms.assetid: b687e376-ee33-470d-b65a-87246bfefe6f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: bead257b40c33e3640b18890a7d109d774131123
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610859"
---
# <a name="create-or-delete-a-server-alias-for-use-by-a-client-sql-server-configuration-manager"></a><span data-ttu-id="922d5-102">Créer ou modifier un alias de serveur devant être utilisé par un client (Gestionnaire de configuration SQL Server)</span><span class="sxs-lookup"><span data-stu-id="922d5-102">Create or Delete a Server Alias for Use by a Client (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="922d5-103">Cette rubrique explique comment créer ou supprimer un alias de serveur dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide du Gestionnaire de configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="922d5-103">This topic describes how to create or delete a server alias in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="922d5-104">Un alias est un nom de remplacement permettant d'établir une connexion.</span><span class="sxs-lookup"><span data-stu-id="922d5-104">An alias is an alternate name that can be used to make a connection.</span></span> <span data-ttu-id="922d5-105">L'alias encapsule les éléments requis d'une chaîne de connexion, puis les expose sous un nom choisi par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="922d5-105">The alias encapsulates the required elements of a connection string, and exposes them with a name chosen by the user.</span></span> <span data-ttu-id="922d5-106">Les alias peuvent être utilisés avec toute application cliente.</span><span class="sxs-lookup"><span data-stu-id="922d5-106">Aliases can be used with any client application.</span></span> <span data-ttu-id="922d5-107">En créant des alias de serveur, votre ordinateur client peut se connecter à plusieurs serveurs utilisant différents protocoles réseau, sans avoir à spécifier les détails concernant le protocole et la connexion pour chacun d'eux.</span><span class="sxs-lookup"><span data-stu-id="922d5-107">By creating server aliases, your client computer can connect to multiple servers using different network protocols, without having to specify the protocol and connection details for each one.</span></span> <span data-ttu-id="922d5-108">De plus, vous pouvez également faire en sorte que différents protocoles réseau soient activés en permanence, même si vous n'avez besoin de les utiliser qu'occasionnellement.</span><span class="sxs-lookup"><span data-stu-id="922d5-108">In addition, you can also have different network protocols enabled all the time, even if you only need to use them occasionally.</span></span> <span data-ttu-id="922d5-109">Si vous avez configuré le serveur de sorte qu'il soit à l'écoute sur un numéro de port ou un canal de communication nommé autre que celui utilisé par défaut, alors que vous avez désactivé le service SQL Server Browser, créez un alias indiquant le nouveau numéro de port ou le nouveau canal de communication nommé.</span><span class="sxs-lookup"><span data-stu-id="922d5-109">If you have configured the server to listen on a non-default port number or named pipe, and you have disabled the SQL Server Browser service, create an alias that specifies the new port number or named pipe.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="922d5-110">Utilisation du Gestionnaire de configuration SQL Server</span><span class="sxs-lookup"><span data-stu-id="922d5-110">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-create-an-alias"></a><span data-ttu-id="922d5-111">Pour créer un alias</span><span class="sxs-lookup"><span data-stu-id="922d5-111">To create an alias</span></span>  
  
1.  <span data-ttu-id="922d5-112">Dans le Gestionnaire de configuration SQL Server, développez **Configuration de SQL Native Client**, cliquez avec le bouton droit sur **Alias**, puis sélectionnez **Nouvel alias**.</span><span class="sxs-lookup"><span data-stu-id="922d5-112">In SQL Server Configuration Manager, expand **SQL Server Native Client Configuration**, right-click **Aliases**, and then click **New Alias**.</span></span>  
  
2.  <span data-ttu-id="922d5-113">Dans la zone **Nom de l’alias** , tapez le nom de l’alias.</span><span class="sxs-lookup"><span data-stu-id="922d5-113">In the **Alias Name** box, type the name of the alias.</span></span> <span data-ttu-id="922d5-114">Il s'agit du nom que les applications clientes utiliseront pour se connecter.</span><span class="sxs-lookup"><span data-stu-id="922d5-114">Client applications use this name when they connect.</span></span>  
  
3.  <span data-ttu-id="922d5-115">Dans la zone **Serveur** , tapez le nom ou l’adresse IP d’un serveur.</span><span class="sxs-lookup"><span data-stu-id="922d5-115">In the **Server** box, type the name or IP address of a server.</span></span> <span data-ttu-id="922d5-116">Pour une instance nommée, ajoutez le nom de l'instance.</span><span class="sxs-lookup"><span data-stu-id="922d5-116">For a named instance append the instance name.</span></span>  
  
4.  <span data-ttu-id="922d5-117">Dans la zone **Protocole** , sélectionnez le protocole utilisé pour cet alias.</span><span class="sxs-lookup"><span data-stu-id="922d5-117">In the **Protocol** box, select the protocol used for this alias.</span></span> <span data-ttu-id="922d5-118">La sélection d'un protocole modifie le titre de la zone des propriétés facultatives en Numéro de port, Nom du canal ou Chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="922d5-118">Selecting a protocol, changes the title of the optional properties box to Port No, Pipe Name, or Connection String.</span></span>  
  
 <span data-ttu-id="922d5-119">Les chaînes de connexion décrites dans l’aide du Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peuvent s’avérer utiles pour les programmeurs qui créent leurs propres chaînes de connexion.</span><span class="sxs-lookup"><span data-stu-id="922d5-119">The connection strings described in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager Help can be useful for programmers who create their own connection strings.</span></span> <span data-ttu-id="922d5-120">Pour accéder à ces informations, dans la boîte de dialogue **Nouvel alias** , appuyez sur F1 ou cliquez sur **Aide**.</span><span class="sxs-lookup"><span data-stu-id="922d5-120">To access this information, in the **New Alias** dialog box, press F1, or click **Help**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="922d5-121">Si un alias configuré se connecte au serveur ou à l'instance incorrect, désactivez puis réactivez le protocole réseau associé.</span><span class="sxs-lookup"><span data-stu-id="922d5-121">If a configured alias is connecting to the wrong server or instance, disable and then reenable the associated network protocol.</span></span> <span data-ttu-id="922d5-122">Cette opération efface toute information de connexion mise en cache et permet au client de se connecter correctement.</span><span class="sxs-lookup"><span data-stu-id="922d5-122">Doing this clears any cached connection information and allows the client to connect correctly.</span></span>  
  
#### <a name="to-delete-an-alias"></a><span data-ttu-id="922d5-123">Pour supprimer un alias</span><span class="sxs-lookup"><span data-stu-id="922d5-123">To delete an alias</span></span>  
  
1.  <span data-ttu-id="922d5-124">Dans le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , développez **Configuration de SQL Server Native Client**et cliquez sur **Alias**.</span><span class="sxs-lookup"><span data-stu-id="922d5-124">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Native Client Configuration**, and then click **Aliases**.</span></span>  
  
2.  <span data-ttu-id="922d5-125">Dans le volet d’informations, cliquez avec le bouton droit sur l’alias à supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="922d5-125">In the details pane, right-click the alias that you want to delete, and then click **Delete**.</span></span>  
  
  
