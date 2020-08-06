---
title: Modifier le compte de contrôleur et les comptes de services clients | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 44a73ddb-18ad-415c-bfbe-126ab2e3290b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 62a054749f1d53323bde5c9d05a1e7632b1dda85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703652"
---
# <a name="modify-the-controller-and-client-services-accounts"></a><span data-ttu-id="70d0e-102">Modifier le compte de contrôleur et les comptes de services clients</span><span class="sxs-lookup"><span data-stu-id="70d0e-102">Modify the Controller and Client Services Accounts</span></span>
  <span data-ttu-id="70d0e-103">Dans cette rubrique, vous apprendrez à modifier les comptes de service Distributed Replay Controller et Distributed Replay Client, puis à réappliquer les listes de contrôle d'accès (ACL).</span><span class="sxs-lookup"><span data-stu-id="70d0e-103">In this topic, you will learn how to modify the Distributed Replay controller and client service accounts, and then reapply the access control lists (ACLs).</span></span>  
  
### <a name="to-start-or-stop-the-distributed-replay-services-using-computer-management"></a><span data-ttu-id="70d0e-104">Pour démarrer ou arrêter les services Distributed Replay à l'aide de Gestion de l'ordinateur</span><span class="sxs-lookup"><span data-stu-id="70d0e-104">To start or stop the Distributed Replay services using Computer Management</span></span>  
  
1.  <span data-ttu-id="70d0e-105">Sur l’ordinateur sur lequel les services Distributed Replay sont installés, depuis l’invite de commandes, tapez `dcomcnfg`.</span><span class="sxs-lookup"><span data-stu-id="70d0e-105">On the computer on which the Distributed Replay services are installed, from the command prompt, type `dcomcnfg`.</span></span>  
  
2.  <span data-ttu-id="70d0e-106">Double-cliquez sur **services**, faites défiler la liste et cliquez avec le bouton droit sur \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay \<service name> \*\*, puis cliquez sur **Démarrer** ou **arrêter**.</span><span class="sxs-lookup"><span data-stu-id="70d0e-106">Double-click **Services**, scroll down and right-click **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay \<service name>**, and then click **Start** or **Stop**.</span></span>  
  
### <a name="to-modify-the-distributed-replay-controller-service"></a><span data-ttu-id="70d0e-107">Pour modifier le service Distributed Replay Controller</span><span class="sxs-lookup"><span data-stu-id="70d0e-107">To modify the Distributed Replay controller service</span></span>  
  
1.  <span data-ttu-id="70d0e-108">Sur l'ordinateur contrôleur, arrêtez le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Controller.</span><span class="sxs-lookup"><span data-stu-id="70d0e-108">On the controller computer, stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay controller service.</span></span>  
  
2.  <span data-ttu-id="70d0e-109">Sous **Services**, cliquez avec le bouton droit sur **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Controller**, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="70d0e-109">Under **Services**, right-click **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Controller**, and then select **Properties**.</span></span>  
  
3.  <span data-ttu-id="70d0e-110">Dans la fenêtre **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Controller** , sous l'onglet **Ouvrir une session** , sélectionnez **Ce compte**, tapez ou cliquez sur **Parcourir** pour entrer le nouveau compte d'ouverture de session, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="70d0e-110">In the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Controller Properties** window, on the **Log On** tab, select **This account**, type or click **Browse** to enter the new logon account, and then click **OK**.</span></span>  
  
     <span data-ttu-id="70d0e-111">**Important !** Lorsque vous configurez le contrôleur Distributed Replay, vous pouvez spécifier un ou plusieurs comptes d'utilisateurs qui seront utilisés pour exécuter les services clients Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="70d0e-111">**Important**: When you configure Distributed Replay Controller, you can specify one or more user accounts that will be used to run the Distributed Replay Client services.</span></span> <span data-ttu-id="70d0e-112">Vous trouverez ci-dessous la liste des comptes pris en charge :</span><span class="sxs-lookup"><span data-stu-id="70d0e-112">The following is the list of supported accounts:</span></span>  
  
    -   <span data-ttu-id="70d0e-113">Compte d’utilisateur de domaine</span><span class="sxs-lookup"><span data-stu-id="70d0e-113">Domain user account</span></span>  
  
    -   <span data-ttu-id="70d0e-114">Compte d'utilisateur local créé par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="70d0e-114">User created local user account</span></span>  
  
    -   <span data-ttu-id="70d0e-115">Administrateur</span><span class="sxs-lookup"><span data-stu-id="70d0e-115">Administrator</span></span>  
  
    -   <span data-ttu-id="70d0e-116">Compte virtuel et Compte de service administré (MSA)</span><span class="sxs-lookup"><span data-stu-id="70d0e-116">Virtual account and MSA (Managed Service Account)</span></span>  
  
    -   <span data-ttu-id="70d0e-117">Services réseau, Services locaux et Système</span><span class="sxs-lookup"><span data-stu-id="70d0e-117">Network Services, Local Services, and System</span></span>  
  
     <span data-ttu-id="70d0e-118">Les comptes de groupe (locaux ou de domaine) et autres comptes intégrés (comme Tout le monde) ne sont pas acceptés.</span><span class="sxs-lookup"><span data-stu-id="70d0e-118">Group accounts (local or domain) and other built-in accounts (like Everyone) are not accepted.</span></span>  
  
4.  <span data-ttu-id="70d0e-119">Démarrez le service Distributed Replay Controller.</span><span class="sxs-lookup"><span data-stu-id="70d0e-119">Start the Distributed Replay controller service.</span></span>  
  
### <a name="to-modify-the-distributed-replay-client-service"></a><span data-ttu-id="70d0e-120">Pour modifier le service Distributed Replay Client</span><span class="sxs-lookup"><span data-stu-id="70d0e-120">To modify the Distributed Replay client service</span></span>  
  
1.  <span data-ttu-id="70d0e-121">Avant de modifier le service Distributed Replay Client, assurez-vous que le compte de service client que vous modifiez a été spécifié durant l'installation (dans le paramètre CTLRUSERS sur l'ordinateur contrôleur).</span><span class="sxs-lookup"><span data-stu-id="70d0e-121">Before you modify the Distributed Replay client service, make sure the client service account you are changing was specified during setup (in the CTLRUSERS parameter on the controller computer).</span></span> <span data-ttu-id="70d0e-122">Si le compte de service client que vous modifiez n'a pas été spécifié pendant l'installation, vous devez effectuer les étapes suivantes au préalable :</span><span class="sxs-lookup"><span data-stu-id="70d0e-122">If the client service account you are changing was not specified during setup, you must perform the following steps first:</span></span>  
  
    1.  <span data-ttu-id="70d0e-123">Arrêtez le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Controller.</span><span class="sxs-lookup"><span data-stu-id="70d0e-123">Stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay controller service.</span></span>  
  
    2.  <span data-ttu-id="70d0e-124">Sur l’ordinateur contrôleur sur lequel le service contrôleur est installé, depuis l’invite de commandes, tapez `dcomcnfg`.</span><span class="sxs-lookup"><span data-stu-id="70d0e-124">On the controller computer on which the controller service is installed, from the command prompt, type `dcomcnfg`.</span></span>  
  
    3.  <span data-ttu-id="70d0e-125">Dans la fenêtre **Services de composants**, accédez à **Racine de la console -> Services de composants -> Ordinateurs -> Poste de travail -> DCOM Config ->DReplayController**.</span><span class="sxs-lookup"><span data-stu-id="70d0e-125">In the **Component Services** window, navigate to **Console Root -> Component Services -> Computers -> My Computer -> DCOM Config ->DReplayController**.</span></span>  
  
    4.  <span data-ttu-id="70d0e-126">Cliquez avec le bouton droit sur **DReplayController**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="70d0e-126">Right-click **DReplayController**, and then click **Properties**.</span></span>  
  
    5.  <span data-ttu-id="70d0e-127">Dans la fenêtre **Propriétés de DReplayController** , sous l'onglet **Sécurité** , cliquez sur **Modifier** dans la section **Autorisations d'exécution et d'activation** .</span><span class="sxs-lookup"><span data-stu-id="70d0e-127">In the **DReplayController Properties** window, on the **Security** tab, click **Edit** in the **Launch and Activation Permissions** section.</span></span>  
  
    6.  <span data-ttu-id="70d0e-128">Accordez au nouveau compte d'ouverture de session du service client des autorisations **Activation locale et à distance** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="70d0e-128">Grant the new client service logon account **Local and Remote activation** permissions, and then click **OK**.</span></span>  
  
    7.  <span data-ttu-id="70d0e-129">Cliquez sur **Modifier** dans la section **Autorisations d'accès** et accordez des autorisations **Accès local et distant** au nouveau compte d'ouverture de session du service client, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="70d0e-129">Click **Edit** in the **Access Permissions** section, and grant the new client service logon account **Local and Remote access** permissions, and then click **OK**.</span></span>  
  
    8.  <span data-ttu-id="70d0e-130">Cliquez sur **OK** pour fermer la fenêtre **Propriétés de DReplayController** .</span><span class="sxs-lookup"><span data-stu-id="70d0e-130">Click **OK** to close the **DReplayController Properties** window.</span></span>  
  
    9. <span data-ttu-id="70d0e-131">Sur l'ordinateur contrôleur, ajoutez le compte d'ouverture de session du service client modifié au groupe **Utilisateurs du modèle COM distribué** .</span><span class="sxs-lookup"><span data-stu-id="70d0e-131">On the controller computer, add the changed client service logon account to the **Distributed COM Users** group.</span></span>  
  
    10. <span data-ttu-id="70d0e-132">Démarrez le service SQL Server Distributed Replay Controller.</span><span class="sxs-lookup"><span data-stu-id="70d0e-132">Start the SQL Server Distributed Replay controller service.</span></span>  
  
2.  <span data-ttu-id="70d0e-133">Arrêtez le service client [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Client.</span><span class="sxs-lookup"><span data-stu-id="70d0e-133">Stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay client service.</span></span>  
  
3.  <span data-ttu-id="70d0e-134">Dans la fenêtre **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Client** , sous l'onglet **Ouvrir une session** , sélectionnez **Ce compte**, tapez ou cliquez sur **Parcourir** pour entrer le nouveau compte d'ouverture de session, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="70d0e-134">In the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Client Properties** window, on the **Log On** tab, select **This account**, type or click **Browse** to enter the new logon account, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="70d0e-135">Démarrez le service Distributed Replay Client.</span><span class="sxs-lookup"><span data-stu-id="70d0e-135">Start the Distributed Replay client service.</span></span>  
  
  
