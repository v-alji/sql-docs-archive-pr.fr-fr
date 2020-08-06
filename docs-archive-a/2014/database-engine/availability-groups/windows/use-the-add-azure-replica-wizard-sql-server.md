---
title: Utiliser l’Assistant Ajout d’un réplica Azure (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.addreplicawizard.azurereplica.f1
ms.assetid: b89cc41b-07b4-49f3-82cc-bc42b2e793ae
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8f7ee9e80f0511fe23aebb887b15b5e8b7e9cabf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696060"
---
# <a name="use-the-add-azure-replica-wizard-sql-server"></a><span data-ttu-id="6ceed-102">Utiliser l'Assistant Ajout d’un réplica Azure (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6ceed-102">Use the Add Azure Replica Wizard (SQL Server)</span></span>
  <span data-ttu-id="6ceed-103">Utilisez l’Assistant Ajout d’un réplica Azure pour vous aider à créer une machine virtuelle Azure dans un environnement informatique hybride et à le configurer comme réplica secondaire pour un groupe de disponibilité AlwaysOn nouveau ou existant.</span><span class="sxs-lookup"><span data-stu-id="6ceed-103">Use the Add Azure Replica Wizard to help you create a new Azure VM in hybrid IT and configure it as a secondary replica for a new or existing AlwaysOn availability group.</span></span>  
  
-   <span data-ttu-id="6ceed-104">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="6ceed-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6ceed-105">Composants requis</span><span class="sxs-lookup"><span data-stu-id="6ceed-105">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="6ceed-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="6ceed-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6ceed-107">**Pour ajouter un réplica, consultez**  [Assistant Ajouter un réplica Microsoft Azure (SQL Server Management Studio)](#SSMSProcedure)</span><span class="sxs-lookup"><span data-stu-id="6ceed-107">**To add a replica, using:**  [Add Azure Replica Wizard (SQL Server Management Studio)](#SSMSProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6ceed-108">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="6ceed-108">Before You Begin</span></span>  
 <span data-ttu-id="6ceed-109">Si vous n’avez jamais ajouté de réplica de disponibilité à un groupe de disponibilité, consultez les sections « instances de serveur » et « groupes de disponibilité et réplicas » dans [conditions préalables requises, restrictions et recommandations pour groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="6ceed-109">If you have never added any availability replica to an availability group, see the "Server instances" and "Availability groups and replicas" sections in [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="6ceed-110">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="6ceed-110">Prerequisites</span></span>  
  
-   <span data-ttu-id="6ceed-111">Vous devez être connecté à l'instance de serveur qui héberge le réplica principal actuel.</span><span class="sxs-lookup"><span data-stu-id="6ceed-111">You must be connected to the server instance that hosts the current primary replica.</span></span>  
  
-   <span data-ttu-id="6ceed-112">Vous devez travailler dans un environnement informatique hybride où votre sous-réseau local dispose d’un réseau privé virtuel (VPN) de site à site avec Azure.</span><span class="sxs-lookup"><span data-stu-id="6ceed-112">You must have a hybrid-IT environment where your on-premise subnet has a site-to-site VPN with Azure.</span></span> <span data-ttu-id="6ceed-113">Pour plus d’informations, consultez [Configurer un réseau privé virtuel (VPN) de site à site dans le portail de gestion](https://azure.microsoft.com/documentation/articles/vpn-gateway-site-to-site-create).</span><span class="sxs-lookup"><span data-stu-id="6ceed-113">For more information, see [Configure a Site-to-Site VPN in the Management Portal](https://azure.microsoft.com/documentation/articles/vpn-gateway-site-to-site-create).</span></span>  
  
-   <span data-ttu-id="6ceed-114">Votre groupe de disponibilité doit contenir des réplicas de disponibilité locaux.</span><span class="sxs-lookup"><span data-stu-id="6ceed-114">Your availability group must contain on-premise availability replicas.</span></span>  
  
-   <span data-ttu-id="6ceed-115">Les clients de l’écouteur de groupe de disponibilité doivent disposer d’une connectivité à Internet s’ils souhaitent maintenir la connectivité avec l’écouteur lorsque le groupe de disponibilité est basculé vers un réplica Azure.</span><span class="sxs-lookup"><span data-stu-id="6ceed-115">Clients to the availability group listener must have connectivity to the Internet if they want to maintain connectivity with the listener when the availability group is failed over to an Azure replica.</span></span>  
  
-   <span data-ttu-id="6ceed-116">**Conditions préalables requises pour utiliser la synchronisation de données initiale complète** Vous devez spécifier un partage réseau pour que l'assistant crée des sauvegardes et puisse y accéder.</span><span class="sxs-lookup"><span data-stu-id="6ceed-116">**Prerequisites for using full initial data synchronization** You will need to specify a network share in order for the wizard to create and access backups.</span></span> <span data-ttu-id="6ceed-117">Pour le réplica principal, le compte utilisé pour démarrer le [!INCLUDE[ssDE](../../../includes/ssde-md.md)] doit disposer d'autorisations de système de fichiers en lecture et en écriture sur un partage réseau.</span><span class="sxs-lookup"><span data-stu-id="6ceed-117">For the primary replica, the account used to start the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] must have read and write file-system permissions on a network share.</span></span> <span data-ttu-id="6ceed-118">Pour les réplicas secondaires, le compte doit disposer d'une autorisation en lecture sur le partage réseau.</span><span class="sxs-lookup"><span data-stu-id="6ceed-118">For secondary replicas, the account must have read permission on the network share.</span></span>  
  
     <span data-ttu-id="6ceed-119">Si vous ne pouvez pas utiliser l'Assistant pour effectuer la synchronisation des données initiale complète, vous devez préparer vos bases de données secondaires manuellement.</span><span class="sxs-lookup"><span data-stu-id="6ceed-119">If you are unable to use the wizard to perform full initial data synchronization, you need to prepare your secondary databases manually.</span></span> <span data-ttu-id="6ceed-120">Vous pouvez le faire avant ou après l'exécution de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="6ceed-120">You can do this before or after running the wizard.</span></span> <span data-ttu-id="6ceed-121">Pour plus d’informations, consultez [Préparer manuellement une base de données secondaire pour un groupe de disponibilité &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6ceed-121">For more information, see [Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6ceed-122">Sécurité</span><span class="sxs-lookup"><span data-stu-id="6ceed-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6ceed-123">Autorisations</span><span class="sxs-lookup"><span data-stu-id="6ceed-123">Permissions</span></span>  
 <span data-ttu-id="6ceed-124">Consultez [Security](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md#Security)</span><span class="sxs-lookup"><span data-stu-id="6ceed-124">See [Security](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md#Security)</span></span>  
  
##  <a name="using-the-add-azure-replica-wizard-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6ceed-125">Utilisation de l'Assistant Ajouter un réplica Windows Azure (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="6ceed-125">Using the Add Azure Replica Wizard (SQL Server Management Studio)</span></span>  
 <span data-ttu-id="6ceed-126">L'Assistant Ajouter un réplica Windows Azure peut être lancé depuis la page [Spécifier les réplicas](specify-replicas-page-new-availability-group-wizard-add-replica-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="6ceed-126">The Add Azure Replica Wizard can be launched from the [Specify Replicas Page](specify-replicas-page-new-availability-group-wizard-add-replica-wizard.md).</span></span> <span data-ttu-id="6ceed-127">Il existe deux moyens d'atteindre cette page :</span><span class="sxs-lookup"><span data-stu-id="6ceed-127">There are two ways to reach this page:</span></span>  
  
-   [<span data-ttu-id="6ceed-128">Utiliser l’Assistant Groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6ceed-128">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="6ceed-129">Utiliser l’Assistant Ajouter un réplica au groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6ceed-129">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
 <span data-ttu-id="6ceed-130">Une fois que vous avez lancé l'Assistant Ajouter un réplica Windows Azure, suivez les étapes ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="6ceed-130">Once you have launched the Add Azure Replica Wizard, follow the steps below:</span></span>  
  
1.  <span data-ttu-id="6ceed-131">Commencez par télécharger un certificat de gestion pour votre abonnement Azure.</span><span class="sxs-lookup"><span data-stu-id="6ceed-131">First, download a management certificate for your Azure subscription.</span></span> <span data-ttu-id="6ceed-132">Cliquez sur **Télécharger** pour ouvrir la page de connexion.</span><span class="sxs-lookup"><span data-stu-id="6ceed-132">Click **Download** to open the sign-in page.</span></span>  
  
2.  <span data-ttu-id="6ceed-133">Dans la page de connexion, connectez-vous à votre abonnement Azure.</span><span class="sxs-lookup"><span data-stu-id="6ceed-133">In the sign-in page, sign in to your Azure subscription.</span></span> <span data-ttu-id="6ceed-134">Une fois que vous êtes connecté, l'Assistant installe un certificat de gestion sur votre ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="6ceed-134">Once you are signed in, the wizard installs a management certificate onto your local machine.</span></span> <span data-ttu-id="6ceed-135">Ce certificat de gestion sera chargé automatiquement lorsque vous utiliserez à nouveau cet Assistant.</span><span class="sxs-lookup"><span data-stu-id="6ceed-135">This management certificate is automatically loaded when you use this wizard again.</span></span> <span data-ttu-id="6ceed-136">Si vous avez téléchargé plusieurs certificats de gestion, vous pouvez cliquer sur le bouton **...** pour sélectionner celui à utiliser.</span><span class="sxs-lookup"><span data-stu-id="6ceed-136">If you have downloaded multiple management certificates, you can click the **...** button to select the one you want to use.</span></span>  
  
3.  <span data-ttu-id="6ceed-137">Connectez-vous ensuite à votre abonnement en cliquant sur **Connexion**.</span><span class="sxs-lookup"><span data-stu-id="6ceed-137">Next, connect to your subscription by clicking **Connect**.</span></span> <span data-ttu-id="6ceed-138">Une fois que vous êtes connecté, les listes déroulantes sont remplies avec vos paramètres Azure, tels que **Réseau virtuel** et **Sous-réseau de réseau virtuel**.</span><span class="sxs-lookup"><span data-stu-id="6ceed-138">Once you are connected, the drop-down lists are populated with your Azure parameters, such as **Virtual Network** and **Virtual Network Subnet**.</span></span>  
  
4.  <span data-ttu-id="6ceed-139">Spécifiez les paramètres de la machine virtuelle Azure qui hébergera le nouveau réplica secondaire :</span><span class="sxs-lookup"><span data-stu-id="6ceed-139">Specify the settings for the Azure VM that will host the new secondary replica:</span></span>  
  
     <span data-ttu-id="6ceed-140">Image</span><span class="sxs-lookup"><span data-stu-id="6ceed-140">Image</span></span>  
     <span data-ttu-id="6ceed-141">Nom de l’image SQL Server à utiliser pour la machine virtuelle Azure</span><span class="sxs-lookup"><span data-stu-id="6ceed-141">The name of the SQL Server image to use for the Azure VM</span></span>  
  
     <span data-ttu-id="6ceed-142">Taille de la machine virtuelle</span><span class="sxs-lookup"><span data-stu-id="6ceed-142">VM Size</span></span>  
     <span data-ttu-id="6ceed-143">Taille de la machine virtuelle Azure</span><span class="sxs-lookup"><span data-stu-id="6ceed-143">The size of the Azure VM</span></span>  
  
     <span data-ttu-id="6ceed-144">Nom de la machine virtuelle</span><span class="sxs-lookup"><span data-stu-id="6ceed-144">VM Name</span></span>  
     <span data-ttu-id="6ceed-145">Nom DNS de la machine virtuelle Azure</span><span class="sxs-lookup"><span data-stu-id="6ceed-145">The DNS name of the Azure VM</span></span>  
  
     <span data-ttu-id="6ceed-146">Nom d'utilisateur de l'ordinateur virtuel</span><span class="sxs-lookup"><span data-stu-id="6ceed-146">VM Username</span></span>  
     <span data-ttu-id="6ceed-147">Nom d’utilisateur de l’administrateur par défaut de la machine virtuelle Azure</span><span class="sxs-lookup"><span data-stu-id="6ceed-147">The username of the default administrator for the Azure VM</span></span>  
  
     <span data-ttu-id="6ceed-148">Mot de passe d'administrateur de l'ordinateur virtuel (et Confirmer le mot de passe)</span><span class="sxs-lookup"><span data-stu-id="6ceed-148">VM Administrator Password (and Confirm Password)</span></span>  
     <span data-ttu-id="6ceed-149">Mot de passe de l’administrateur par défaut de la machine virtuelle Azure</span><span class="sxs-lookup"><span data-stu-id="6ceed-149">The password for the default administrator for the Azure VM</span></span>  
  
     <span data-ttu-id="6ceed-150">Réseau virtuel</span><span class="sxs-lookup"><span data-stu-id="6ceed-150">Virtual Network</span></span>  
     <span data-ttu-id="6ceed-151">Réseau virtuel dans lequel placer la machine virtuelle Azure</span><span class="sxs-lookup"><span data-stu-id="6ceed-151">The virtual network in which to place the Azure VM</span></span>  
  
     <span data-ttu-id="6ceed-152">Sous-réseau de réseau virtuel</span><span class="sxs-lookup"><span data-stu-id="6ceed-152">Virtual Network Subnet</span></span>  
     <span data-ttu-id="6ceed-153">Sous-réseau de réseau virtuel dans lequel placer la machine virtuelle Azure</span><span class="sxs-lookup"><span data-stu-id="6ceed-153">The virtual network subnet in which to place the Azure VM</span></span>  
  
     <span data-ttu-id="6ceed-154">Domain</span><span class="sxs-lookup"><span data-stu-id="6ceed-154">Domain</span></span>  
     <span data-ttu-id="6ceed-155">Domaine Active Directory (AD) auquel joindre la machine virtuelle Azure</span><span class="sxs-lookup"><span data-stu-id="6ceed-155">The Active Directory (AD) domain to join the Azure VM</span></span>  
  
     <span data-ttu-id="6ceed-156">Domain Username</span><span class="sxs-lookup"><span data-stu-id="6ceed-156">Domain Username</span></span>  
     <span data-ttu-id="6ceed-157">Nom d’utilisateur AD utilisé pour joindre la machine virtuelle Azure au domaine</span><span class="sxs-lookup"><span data-stu-id="6ceed-157">The AD username used to join the Azure VM to the domain</span></span>  
  
     <span data-ttu-id="6ceed-158">Mot de passe</span><span class="sxs-lookup"><span data-stu-id="6ceed-158">Password</span></span>  
     <span data-ttu-id="6ceed-159">Mot de passe utilisé pour joindre la machine virtuelle Azure au domaine</span><span class="sxs-lookup"><span data-stu-id="6ceed-159">The password used to join the Azure VM to the domain</span></span>  
  
5.  <span data-ttu-id="6ceed-160">Cliquez sur **OK** pour valider vos paramètres et quitter l'Assistant Ajouter un réplica Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="6ceed-160">Click **OK** to commit your settings and exit the Add Azure Replica Wizard.</span></span>  
  
6.  <span data-ttu-id="6ceed-161">Effectuez les autres étapes de configuration décrites à la page [Spécifier les réplicas](specify-replicas-page-new-availability-group-wizard-add-replica-wizard.md) , comme vous le feriez pour tout nouveau réplica.</span><span class="sxs-lookup"><span data-stu-id="6ceed-161">Continue with the rest of the configuration steps for [Specify Replicas Page](specify-replicas-page-new-availability-group-wizard-add-replica-wizard.md) as you do for any new replica.</span></span>  
  
     <span data-ttu-id="6ceed-162">Une fois que vous avez terminé avec l’Assistant groupe de disponibilité ou l’Assistant Ajouter un réplica au groupe de disponibilité, le processus de configuration effectue toutes les opérations dans Azure pour créer le nouvel ordinateur virtuel, le joindre au domaine AD, l’ajouter au cluster Windows, activer la haute disponibilité AlwaysOn et ajouter le nouveau réplica au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="6ceed-162">Once you are finished with the Availability Group Wizard or the Add Replica to Availability Group Wizard, the configuration process performs all operations in Azure to create the new VM, join it to the AD domain, add it to the Windows cluster, enable AlwaysOn High Availability, and add the new replica to the availability group.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="6ceed-163">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="6ceed-163">Related Tasks</span></span>  
  
-   [<span data-ttu-id="6ceed-164">Ajouter un réplica secondaire à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6ceed-164">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="6ceed-165">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6ceed-165">See Also</span></span>  
 <span data-ttu-id="6ceed-166">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6ceed-166">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="6ceed-167">[Conditions préalables requises, restrictions et recommandations pour groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="6ceed-167">[Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span></span>  
 [<span data-ttu-id="6ceed-168">Ajouter un réplica secondaire à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6ceed-168">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
  
