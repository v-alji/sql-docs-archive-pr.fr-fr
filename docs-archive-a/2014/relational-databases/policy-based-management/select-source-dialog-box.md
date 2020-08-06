---
title: Sélectionner une source, boîte de dialogue | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.selectsource.f1
ms.assetid: d664c2e5-dd0c-4da8-b27d-aa4ee4fc0ffd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 535d211d6827477fcf029accc27a9000e8c695c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708215"
---
# <a name="select-source-dialog-box"></a><span data-ttu-id="21fc4-102">Boîte de dialogue Sélectionner une source</span><span class="sxs-lookup"><span data-stu-id="21fc4-102">Select Source Dialog Box</span></span>
  <span data-ttu-id="21fc4-103">Utilisez cette boîte de dialogue pour sélectionner la source des stratégies à exécuter.</span><span class="sxs-lookup"><span data-stu-id="21fc4-103">Use this dialog box to select the source of the policies to be run.</span></span> <span data-ttu-id="21fc4-104">Pour sélectionner un ou plusieurs fichiers XML qui contiennent des stratégies, sélectionnez **Fichiers**.</span><span class="sxs-lookup"><span data-stu-id="21fc4-104">To select one or more XML files that contain policies, select **Files**.</span></span> <span data-ttu-id="21fc4-105">Pour exécuter les stratégies détectées sur l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], sélectionnez **Serveur**.</span><span class="sxs-lookup"><span data-stu-id="21fc4-105">To run the policies that are found on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], select **Server**.</span></span>  
  
 <span data-ttu-id="21fc4-106">Vous pouvez ouvrir cette boîte de dialogue de plusieurs façons.</span><span class="sxs-lookup"><span data-stu-id="21fc4-106">You can open this dialog box in several ways.</span></span>  
  
 <span data-ttu-id="21fc4-107">**Pour ouvrir cette boîte de dialogue**</span><span class="sxs-lookup"><span data-stu-id="21fc4-107">**To open this dialog box**</span></span>  
  
-   <span data-ttu-id="21fc4-108">Dans Serveurs inscrits, cliquez avec le bouton droit sur **Groupes de serveurs locaux** ou sur un serveur répertorié sous **Groupes de serveurs locaux**ou encore sur un serveur répertorié sous **Serveurs de gestion centralisée**, puis sélectionnez **Évaluer les stratégies**.</span><span class="sxs-lookup"><span data-stu-id="21fc4-108">In Registered Servers, right-click **Local Server Groups** or any server under **Local Server Groups**, or any server under **Central Management Servers**, and then select **Evaluate Policies**.</span></span> <span data-ttu-id="21fc4-109">Dans la page **Sélection de la stratégie** de la boîte de dialogue **Évaluer les stratégies** , cliquez sur le bouton d’exploration ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="21fc4-109">In the **Policy Selection** page of the **Evaluate Policies** dialog box, click the Browse (**...**) button.</span></span>  
  
-   <span data-ttu-id="21fc4-110">Dans l’Explorateur d’objets, développez **Gestion**, **Gestion de la stratégie**, cliquez avec le bouton droit sur **Stratégies**, puis sélectionnez **Importer une stratégie**.</span><span class="sxs-lookup"><span data-stu-id="21fc4-110">In Object Explorer, expand **Management**, expand **Policy Management**, right-click **Policies**, and select **Import Policy**.</span></span> <span data-ttu-id="21fc4-111">Dans la boîte de dialogue **Importer** , cliquez sur le bouton d’exploration ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="21fc4-111">In the **Import** dialog box, click the Browse (**...**) button.</span></span>  
  
-   <span data-ttu-id="21fc4-112">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur, une base de données ou un objet de base de données, sélectionnez **Stratégies**, puis **Évaluer**.</span><span class="sxs-lookup"><span data-stu-id="21fc4-112">In Object Explorer, right-click a server, database, or database object, select **Policies**, and then select **Evaluate**.</span></span> <span data-ttu-id="21fc4-113">Dans la page **Sélection de la stratégie** de la boîte de dialogue **Évaluer les stratégies** , cliquez sur le bouton d’exploration ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="21fc4-113">In the **Policy Selection** page of the **Evaluate Policies** dialog box, click the Browse (**...**) button.</span></span>  
  
## <a name="options"></a><span data-ttu-id="21fc4-114">Options</span><span class="sxs-lookup"><span data-stu-id="21fc4-114">Options</span></span>  
 <span data-ttu-id="21fc4-115">**Fichiers**</span><span class="sxs-lookup"><span data-stu-id="21fc4-115">**Files**</span></span>  
 <span data-ttu-id="21fc4-116">Sélectionnez un ou plusieurs fichiers XML qui contiennent des stratégies.</span><span class="sxs-lookup"><span data-stu-id="21fc4-116">Select one or more XML files that contain policies.</span></span>  
  
 <span data-ttu-id="21fc4-117">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="21fc4-117">**Server**</span></span>  
 <span data-ttu-id="21fc4-118">Vous permet de sélectionner un serveur qui contient les stratégies à exécuter.</span><span class="sxs-lookup"><span data-stu-id="21fc4-118">Enables you to select a server that contains the policies that you want to run.</span></span>  
  
 <span data-ttu-id="21fc4-119">**Type de serveur**</span><span class="sxs-lookup"><span data-stu-id="21fc4-119">**Server type**</span></span>  
 <span data-ttu-id="21fc4-120">Seuls les serveurs du [!INCLUDE[ssDE](../../includes/ssde-md.md)] contiennent des stratégies.</span><span class="sxs-lookup"><span data-stu-id="21fc4-120">Only [!INCLUDE[ssDE](../../includes/ssde-md.md)] servers contain policies.</span></span> <span data-ttu-id="21fc4-121">Cette zone est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="21fc4-121">This box is read-only.</span></span>  
  
 <span data-ttu-id="21fc4-122">**Nom du serveur**</span><span class="sxs-lookup"><span data-stu-id="21fc4-122">**Server name**</span></span>  
 <span data-ttu-id="21fc4-123">Sélectionnez l'instance de serveur à laquelle se connecter.</span><span class="sxs-lookup"><span data-stu-id="21fc4-123">Select the server instance to connect to.</span></span> <span data-ttu-id="21fc4-124">Par défaut, la dernière instance de serveur à laquelle une connexion a été établie est affichée.</span><span class="sxs-lookup"><span data-stu-id="21fc4-124">By default, the server instance last connected to is displayed.</span></span>  
  
 <span data-ttu-id="21fc4-125">**Authentification**</span><span class="sxs-lookup"><span data-stu-id="21fc4-125">**Authentication**</span></span>  
 <span data-ttu-id="21fc4-126">Deux modes d'authentification sont disponibles lors de la connexion à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="21fc4-126">Two authentication modes are available when you connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="21fc4-127">**Mode d'authentification Windows (authentification Windows)**</span><span class="sxs-lookup"><span data-stu-id="21fc4-127">**Windows Authentication Mode (Windows Authentication)**</span></span>  
 <span data-ttu-id="21fc4-128">Le mode d'authentification Windows permet à un utilisateur de se connecter au moyen d'un compte d'utilisateur Windows.</span><span class="sxs-lookup"><span data-stu-id="21fc4-128">Windows Authentication mode allows for a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="21fc4-129">**Authentification SQL Server**</span><span class="sxs-lookup"><span data-stu-id="21fc4-129">**SQL Server Authentication**</span></span>  
 <span data-ttu-id="21fc4-130">Quand un utilisateur se connecte avec un nom de connexion et un mot de passe spécifiés à partir d’une connexion non approuvée, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] réalise lui-même l’authentification en vérifiant si un compte de connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a été défini et si le mot de passe spécifié correspond à celui enregistré précédemment.</span><span class="sxs-lookup"><span data-stu-id="21fc4-130">When a user connects with a specified login name and password from a nontrusted connection, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs the authentication itself by checking whether a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login account has been set up and whether the specified password matches the one previously recorded.</span></span> <span data-ttu-id="21fc4-131">Si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne possède pas de compte de connexion, l'authentification échoue et un message d'erreur est envoyé à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="21fc4-131">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not have a login account set, authentication fails, and the user receives an error message.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="21fc4-132">Lorsque c'est possible, utilisez l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="21fc4-132">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="21fc4-133">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="21fc4-133">**User name**</span></span>  
 <span data-ttu-id="21fc4-134">Entrez le nom d'utilisateur avec lequel se connecter.</span><span class="sxs-lookup"><span data-stu-id="21fc4-134">Enter the user name to connect with.</span></span> <span data-ttu-id="21fc4-135">Cette option est disponible uniquement si vous avez choisi la connexion avec l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="21fc4-135">This option is available only if you have selected to connect by using Windows Authentication.</span></span>  
  
 <span data-ttu-id="21fc4-136">**Connexion**</span><span class="sxs-lookup"><span data-stu-id="21fc4-136">**Login**</span></span>  
 <span data-ttu-id="21fc4-137">Entrez le nom d'accès avec lequel se connecter.</span><span class="sxs-lookup"><span data-stu-id="21fc4-137">Enter the login to connect with.</span></span> <span data-ttu-id="21fc4-138">Cette option est disponible uniquement si vous avez choisi d'établir une connexion à l'aide de l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="21fc4-138">This option is available only if you have selected to connect by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="21fc4-139">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="21fc4-139">**Password**</span></span>  
 <span data-ttu-id="21fc4-140">Entrez le mot de passe utilisé avec la connexion.</span><span class="sxs-lookup"><span data-stu-id="21fc4-140">Enter the password for the login.</span></span> <span data-ttu-id="21fc4-141">Ce mot de passe ne peut être modifié que si vous avez choisi la connexion avec l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="21fc4-141">This option is editable only if you have selected to connect by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21fc4-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="21fc4-142">See Also</span></span>  
 <span data-ttu-id="21fc4-143">[Nœud Gestion de la stratégie &#40;Explorateur d’objets&#41;](../../ssms/object/object-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="21fc4-143">[Policy Management Node &#40;Object Explorer&#41;](../../ssms/object/object-explorer.md) </span></span>  
 [<span data-ttu-id="21fc4-144">Administrer des serveurs à l'aide de la Gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="21fc4-144">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
