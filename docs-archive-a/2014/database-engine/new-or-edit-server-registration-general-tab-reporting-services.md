---
title: Nouvelle inscription de serveur ou modifier l’inscription du serveur (onglet général) (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.registerserver.general.reportserver.f1
ms.assetid: 5f899a8e-52ef-46b5-b7a9-f200ccd9f724
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 195756498dcefe4686d4b06e758dba9919c0b304
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613616"
---
# <a name="new-or-edit-server-registration-general-tab-reporting-services"></a><span data-ttu-id="cc0b0-102">Nouvelle inscription de serveur ou Modifier l'enregistrement du serveur (onglet Général) (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="cc0b0-102">New or Edit Server Registration (General Tab) (Reporting Services)</span></span>
  <span data-ttu-id="cc0b0-103">Cet onglet vous permet de spécifier des options lors de l'inscription d'une instance de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc0b0-103">Use this tab to specify options when registering an instance of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="cc0b0-104">Pour accéder à cette page, dans Serveurs inscrits, cliquez sur **Reporting Services** dans la barre d’outils **Serveurs inscrits** , cliquez avec le bouton droit sur un groupe de serveurs inscrits quelconque, tel que **Reporting Services**, pointez sur **Nouveau**, puis cliquez sur **Inscription du serveur**.</span><span class="sxs-lookup"><span data-stu-id="cc0b0-104">To access this page, in Registered Servers, click **Reporting Services** on the **Registered Servers** toolbar, right-click any registered servers group such as **Reporting Services**, point to **New**, and then click **Server Registration**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cc0b0-105">Options</span><span class="sxs-lookup"><span data-stu-id="cc0b0-105">Options</span></span>  
 <span data-ttu-id="cc0b0-106">**Type de serveur**</span><span class="sxs-lookup"><span data-stu-id="cc0b0-106">**Server type**</span></span>  
 <span data-ttu-id="cc0b0-107">Lorsqu’un serveur est inscrit à partir de serveurs inscrits, la zone **type de serveur** est en lecture seule et correspond au type de serveur affiché dans le volet **serveurs inscrits** .</span><span class="sxs-lookup"><span data-stu-id="cc0b0-107">When a server is registered from Registered Servers, the **Server type** box is read-only, and it matches the type of server displayed in the **Registered Servers** pane.</span></span> <span data-ttu-id="cc0b0-108">Pour inscrire un autre type de serveur, cliquez sur le serveur souhaité dans la barre d'outils **Serveurs inscrits** avant de commencer l'inscription du nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="cc0b0-108">To register a different type of server, click the server you want on the **Registered Servers** toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="cc0b0-109">**Nom du serveur**</span><span class="sxs-lookup"><span data-stu-id="cc0b0-109">**Server name**</span></span>  
 <span data-ttu-id="cc0b0-110">Spécifiez l'instance de serveur de rapports à laquelle se connecter.</span><span class="sxs-lookup"><span data-stu-id="cc0b0-110">Specify the report server instance to connect to.</span></span> <span data-ttu-id="cc0b0-111">Dans [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], vous pouvez accéder à un serveur de rapports par son nom d'instance.</span><span class="sxs-lookup"><span data-stu-id="cc0b0-111">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], you can access a report server through its instance name.</span></span> <span data-ttu-id="cc0b0-112">Vous pouvez avoir une instance de serveur de rapports pour chaque instance SQL Server que vous installez.</span><span class="sxs-lookup"><span data-stu-id="cc0b0-112">You can have one report server instance for each SQL Server instance that you install.</span></span> <span data-ttu-id="cc0b0-113">Si vous utilisez l'instance par défaut, tapez le nom de l'instance SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cc0b0-113">If you are using the default instance, type the name of the SQL Server instance.</span></span> <span data-ttu-id="cc0b0-114">Si vous utilisez une instance nommée, spécifiez cette instance nommée pour vous connecter au serveur de rapports, sous le format MSSQL$InstanceName.</span><span class="sxs-lookup"><span data-stu-id="cc0b0-114">If you are using a named instance, specify the named instance to connect to the report server in the format MSSQL$InstanceName.</span></span>  
  
 <span data-ttu-id="cc0b0-115">**Authentification**</span><span class="sxs-lookup"><span data-stu-id="cc0b0-115">**Authentication**</span></span>  
 <span data-ttu-id="cc0b0-116">L'authentification sur un serveur de rapports s'effectue par l'intermédiaire d'IIS (Internet Information Services).</span><span class="sxs-lookup"><span data-stu-id="cc0b0-116">Authentication to a report server is made through Internet Information Services (IIS).</span></span> <span data-ttu-id="cc0b0-117">Sélectionnez l'un des modes d'authentification ci-dessous pour vous connecter à Reporting Services :</span><span class="sxs-lookup"><span data-stu-id="cc0b0-117">Select from one of the following authentication modes when connecting to Reporting Services:</span></span>  
  
 <span data-ttu-id="cc0b0-118">**Mode d'authentification Windows (authentification Windows)**</span><span class="sxs-lookup"><span data-stu-id="cc0b0-118">**Windows Authentication Mode (Windows Authentication)**</span></span>  
 <span data-ttu-id="cc0b0-119">La connexion à l'instance de serveur de rapports s'effectue à l'aide de l'authentification [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="cc0b0-119">Connect to the report server instance using your [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows credentials.</span></span>  
  
 <span data-ttu-id="cc0b0-120">**Authentification de base**</span><span class="sxs-lookup"><span data-stu-id="cc0b0-120">**Basic Authentication**</span></span>  
 <span data-ttu-id="cc0b0-121">Connectez-vous au moyen de l’ **Authentification de base** si votre installation Reporting Services est configurée pour utiliser l’authentification de base.</span><span class="sxs-lookup"><span data-stu-id="cc0b0-121">Connect using **Basic Authentication** if your Reporting Services installation is configured to use Basic Authentication.</span></span>  
  
 <span data-ttu-id="cc0b0-122">**Authentification par formulaire**</span><span class="sxs-lookup"><span data-stu-id="cc0b0-122">**Forms Authentication**</span></span>  
 <span data-ttu-id="cc0b0-123">Connectez-vous au moyen de l’ **Authentification par formulaire** si votre installation Reporting Services est configurée pour utiliser une extension d’authentification personnalisée.</span><span class="sxs-lookup"><span data-stu-id="cc0b0-123">Connect using **Forms Authentication** if your Reporting Services installation is configured to use a custom authentication extension.</span></span>  
  
 <span data-ttu-id="cc0b0-124">**Nom d’utilisateur**</span><span class="sxs-lookup"><span data-stu-id="cc0b0-124">**User Name**</span></span>  
 <span data-ttu-id="cc0b0-125">Entrez le nom d'utilisateur à utiliser pour se connecter.</span><span class="sxs-lookup"><span data-stu-id="cc0b0-125">Enter the login name to use for the connection.</span></span> <span data-ttu-id="cc0b0-126">Cette option n'est disponible que si vous avez choisi **Authentification de base** ou **Authentification par formulaire**.</span><span class="sxs-lookup"><span data-stu-id="cc0b0-126">This option is only available if you have selected **Basic** or **Forms Authentication**.</span></span>  
  
 <span data-ttu-id="cc0b0-127">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="cc0b0-127">**Password**</span></span>  
 <span data-ttu-id="cc0b0-128">Entrez le mot de passe correspondant au nom d'utilisateur indiqué.</span><span class="sxs-lookup"><span data-stu-id="cc0b0-128">Enter the password for the user name.</span></span> <span data-ttu-id="cc0b0-129">Cette option n'est modifiable que si vous avez choisi **Authentification de base** ou **Authentification par formulaire**.</span><span class="sxs-lookup"><span data-stu-id="cc0b0-129">This option is only editable if you have selected **Basic** or **Forms Authentication**.</span></span>  
  
 <span data-ttu-id="cc0b0-130">**Mémoriser le mot de passe**</span><span class="sxs-lookup"><span data-stu-id="cc0b0-130">**Remember password**</span></span>  
 <span data-ttu-id="cc0b0-131">Permet d'enregistrer le mot de passe que vous avez entré.</span><span class="sxs-lookup"><span data-stu-id="cc0b0-131">Store the password you have entered.</span></span> <span data-ttu-id="cc0b0-132">Cette option n'est disponible que si vous avez cliqué sur **Authentification de base** ou **Authentification par formulaire**.</span><span class="sxs-lookup"><span data-stu-id="cc0b0-132">This option is only available if you have clicked **Basic** or **Forms Authentication**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cc0b0-133"> Si vous avez activé la case à cocher d'enregistrement du mot de passe et si vous ne voulez plus continuer à l'enregistrer, désactivez la case à cocher, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="cc0b0-133">If you have stored the password and want to stop storing it, clear this check box and then click **Save**.</span></span>  
  
 <span data-ttu-id="cc0b0-134">**Nom du serveur inscrit**</span><span class="sxs-lookup"><span data-stu-id="cc0b0-134">**Registered server name**</span></span>  
 <span data-ttu-id="cc0b0-135">Le nom qui doit apparaître dans Serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="cc0b0-135">The name you want to appear in Registered Servers.</span></span> <span data-ttu-id="cc0b0-136">Il n'est pas nécessaire que ce nom corresponde à celui de la zone **Nom du serveur** .</span><span class="sxs-lookup"><span data-stu-id="cc0b0-136">This name does not have to match the name in the **Server name** box.</span></span>  
  
 <span data-ttu-id="cc0b0-137">**Description du serveur inscrit**</span><span class="sxs-lookup"><span data-stu-id="cc0b0-137">**Registered server description**</span></span>  
 <span data-ttu-id="cc0b0-138">Entrez une description facultative du serveur.</span><span class="sxs-lookup"><span data-stu-id="cc0b0-138">Enter an optional description of the server.</span></span>  
  
 <span data-ttu-id="cc0b0-139">**Test**</span><span class="sxs-lookup"><span data-stu-id="cc0b0-139">**Test**</span></span>  
 <span data-ttu-id="cc0b0-140">Cliquez sur cette option pour tester la connexion au serveur sélectionné dans la zone **Nom du serveur**.</span><span class="sxs-lookup"><span data-stu-id="cc0b0-140">Click to test the connection to the server selected in **Server name**.</span></span>  
  
 <span data-ttu-id="cc0b0-141">**Save**</span><span class="sxs-lookup"><span data-stu-id="cc0b0-141">**Save**</span></span>  
 <span data-ttu-id="cc0b0-142">Cliquez sur ce bouton pour enregistrer les paramètres des serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="cc0b0-142">Click to save the registered server settings.</span></span>  
  
  
