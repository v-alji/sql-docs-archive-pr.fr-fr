---
title: Se connecter au serveur (Moteur de base de données) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.connectoserverunknownservertype.f1
- sql12.swb.connection.login.sqlserver.f1
- sql12.swb.connection.login.sqlce.f1
- sql12.swb.manageSS2k.f1
- sql12.swb.connecttoce.f1
- sql12.swb.connecttoce.connectionproperties.f1
ms.assetid: ee9017b4-8a19-4360-9003-9e6484082d41
author: stevestein
ms.author: sstein
ms.openlocfilehash: ca227d1a3bbc13160962ba2fcad23ff011c950f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702312"
---
# <a name="connect-to-server-database-engine"></a><span data-ttu-id="edba2-102">Se connecter au serveur (Moteur de base de données)</span><span class="sxs-lookup"><span data-stu-id="edba2-102">Connect to Server (Database Engine)</span></span>
  <span data-ttu-id="edba2-103">Utilisez cette boîte de dialogue pour afficher ou spécifier des options de connexion à [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="edba2-103">Use this dialog to view or specify options when connecting to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="edba2-104">Dans la plupart des cas, vous pouvez vous connecter en entrant le nom d’ordinateur du serveur de base de données dans la zone **Nom du serveur** et en cliquant sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="edba2-104">In most cases, you can connect by entering the computer name of the database server in the **Server name** box and then clicking **Connect**.</span></span> <span data-ttu-id="edba2-105">Si vous vous connectez à [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], utilisez le nom d’ordinateur suivi de **\sqlexpress**.</span><span class="sxs-lookup"><span data-stu-id="edba2-105">If you are connecting to [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], use the computer name followed by **\sqlexpress**.</span></span>  
  
 <span data-ttu-id="edba2-106">De nombreux facteurs affectent votre capacité à vous connecter à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="edba2-106">Many factors can affect your ability to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="edba2-107">Options</span><span class="sxs-lookup"><span data-stu-id="edba2-107">Options</span></span>  
 <span data-ttu-id="edba2-108">**Type de serveur**</span><span class="sxs-lookup"><span data-stu-id="edba2-108">**Server type**</span></span>  
 <span data-ttu-id="edba2-109">Lors de l'inscription d'un serveur dans l'Explorateur d'objets, sélectionnez le type de serveur auquel se connecter : [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]ou [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="edba2-109">When registering a server from Object Explorer, select the type of server to connect to: [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="edba2-110">Le reste de la boîte de dialogue affiche uniquement les options s'appliquant au type de serveur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="edba2-110">The rest of the dialog shows only the options that apply to the selected server type.</span></span> <span data-ttu-id="edba2-111">Lors de l’inscription d’un serveur de la liste Serveurs inscrits, la zone **Type de serveur** est en lecture seule et indique le type de serveur affiché dans le composant Serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="edba2-111">When registering a server from Registered Servers, the **Server type** box is read-only, and matches the type of server displayed in the Registered Servers component.</span></span> <span data-ttu-id="edba2-112">Pour inscrire un autre type de serveur, sélectionnez [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], [!INCLUDE[ssEW](../../includes/ssew-md.md)]ou [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] dans la barre d'outils Serveurs inscrits avant d'entamer l'inscription d'un nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="edba2-112">To register a different type of server, select [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], [!INCLUDE[ssEW](../../includes/ssew-md.md)], or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] from the Registered Servers toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="edba2-113">**Nom du serveur**</span><span class="sxs-lookup"><span data-stu-id="edba2-113">**Server name**</span></span>  
 <span data-ttu-id="edba2-114">Sélectionnez l'instance de serveur à laquelle se connecter.</span><span class="sxs-lookup"><span data-stu-id="edba2-114">Select the server instance to connect to.</span></span> <span data-ttu-id="edba2-115">La dernière instance de serveur à laquelle une connexion a été établie est affichée par défaut.</span><span class="sxs-lookup"><span data-stu-id="edba2-115">The server instance last connected to is displayed by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="edba2-116">Pour vous connecter à une instance utilisateur active de [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] , utilisez le protocole des canaux nommés en spécifiant le nom du canal, par exemple np:\\\\.\pipe\3C3DF6B1-2262-47\tsql\query. Pour plus d’informations, consultez la documentation de [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="edba2-116">To connect to an active user instance of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] connect using named pipes protocol specifying the pipe name, such as np:\\\\.\pipe\3C3DF6B1-2262-47\tsql\query For more information, see the [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] documentation.</span></span>  
  
 <span data-ttu-id="edba2-117">**Authentification**</span><span class="sxs-lookup"><span data-stu-id="edba2-117">**Authentication**</span></span>  
 <span data-ttu-id="edba2-118">Deux modes d’authentification sont disponibles lors de la connexion à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="edba2-118">Two authentication modes are available when connecting to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="edba2-119">**Mode d'authentification Windows (authentification Windows)**</span><span class="sxs-lookup"><span data-stu-id="edba2-119">**Windows Authentication Mode (Windows Authentication)**</span></span>  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="edba2-120">Le mode d’authentification Windows permet à l’utilisateur de se connecter au moyen d’un compte d’utilisateur Windows.</span><span class="sxs-lookup"><span data-stu-id="edba2-120">Windows Authentication mode allows a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="edba2-121">**Authentification SQL Server**</span><span class="sxs-lookup"><span data-stu-id="edba2-121">**SQL Server Authentication**</span></span>  
 <span data-ttu-id="edba2-122">Quand un utilisateur se connecte avec un nom d’accès et un mot de passe spécifiés à partir d’une connexion non autorisée, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] réalise l’authentification en vérifiant si un compte de connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a été défini et si le mot de passe spécifié correspond à celui enregistré précédemment.</span><span class="sxs-lookup"><span data-stu-id="edba2-122">When a user connects with a specified login name and password from a non-trusted connection, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs the authentication itself by checking to see if a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login account has been set up and if the specified password matches the one previously recorded.</span></span> <span data-ttu-id="edba2-123">Si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne possède pas de compte de connexion, l'authentification échoue et un message d'erreur est envoyé à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="edba2-123">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not have a login account set, authentication fails, and the user receives an error message.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="edba2-124">Lorsque c'est possible, utilisez l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="edba2-124">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="edba2-125">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="edba2-125">**User name**</span></span>  
 <span data-ttu-id="edba2-126">Entrez le nom d'utilisateur avec lequel se connecter.</span><span class="sxs-lookup"><span data-stu-id="edba2-126">Enter the user name to connect with.</span></span> <span data-ttu-id="edba2-127">Cette option est uniquement disponible si vous avez choisi la connexion avec l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="edba2-127">This option is only available if you have selected to connect using Windows Authentication.</span></span>  
  
 <span data-ttu-id="edba2-128">**Connexion**</span><span class="sxs-lookup"><span data-stu-id="edba2-128">**Login**</span></span>  
 <span data-ttu-id="edba2-129">Entrez le nom d'accès avec lequel se connecter.</span><span class="sxs-lookup"><span data-stu-id="edba2-129">Enter the login to connect with.</span></span> <span data-ttu-id="edba2-130">Cette option est uniquement disponible si vous avez choisi la connexion avec l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="edba2-130">This option is only available if you have selected to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="edba2-131">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="edba2-131">**Password**</span></span>  
 <span data-ttu-id="edba2-132">Entrez le mot de passe utilisé avec la connexion.</span><span class="sxs-lookup"><span data-stu-id="edba2-132">Enter the password for the login.</span></span> <span data-ttu-id="edba2-133">Ce mot de passe ne peut être modifié que si vous avez choisi la connexion avec l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="edba2-133">This option is only editable if you have selected to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="edba2-134">**Connexion**</span><span class="sxs-lookup"><span data-stu-id="edba2-134">**Connect**</span></span>  
 <span data-ttu-id="edba2-135">Cliquez sur cette option pour vous connecter au serveur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="edba2-135">Click to connect to the server selected above.</span></span>  
  
 <span data-ttu-id="edba2-136">**Options**</span><span class="sxs-lookup"><span data-stu-id="edba2-136">**Options**</span></span>  
 <span data-ttu-id="edba2-137">Cliquez ici pour afficher des options supplémentaires de connexion au serveur, comme l'inscription d'un serveur et la mémorisation du mot de passe.</span><span class="sxs-lookup"><span data-stu-id="edba2-137">Click to display additional server connection options, such as registering a server and remembering the password.</span></span>  
  
  
