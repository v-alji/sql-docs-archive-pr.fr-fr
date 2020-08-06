---
title: Activer les connexions chiffrées dans le Moteur de base de données (Gestionnaire de configuration SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server], encrypted
- SSL [SQL Server]
- Secure Sockets Layer (SSL)
- encryption [SQL Server], connections
- cryptography [SQL Server], connections
- certificates [SQL Server], installing
- requesting encrypted connections
- installing certificates
- security [SQL Server], encryption
ms.assetid: e1e55519-97ec-4404-81ef-881da3b42006
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e1653df929e3f8bc67158a0685ce07b8ba65de6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708603"
---
# <a name="enable-encrypted-connections-to-the-database-engine-sql-server-configuration-manager"></a><span data-ttu-id="1eaeb-102">Activer les connexions chiffrées dans le moteur de base de données (Gestionnaire de configuration SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1eaeb-102">Enable Encrypted Connections to the Database Engine (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="1eaeb-103">Cette rubrique explique comment activer les connexions chiffrées d’une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] en spécifiant un certificat pour le [!INCLUDE[ssDE](../../includes/ssde-md.md)] à l’aide du Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1eaeb-103">This topic describes how to enable encrypted connections for an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] by specifying a certificate for the [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="1eaeb-104">L'ordinateur serveur doit être accompagné (approvisionné) d'un certificat et vous devez configurer l'ordinateur client pour permettre l'approbation de l'autorité racine du certificat.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-104">The server computer must have a certificate provisioned, and the client machine must be set up to trust the certificate's root authority.</span></span> <span data-ttu-id="1eaeb-105">L'approvisionnement désigne le processus d'installation d'un certificat par son importation dans Windows.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-105">Provisioning is the process of installing a certificate by importing it into Windows.</span></span>  
  
 <span data-ttu-id="1eaeb-106">Le certificat doit être émis pour l' **authentification serveur**.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-106">The certificate must be issued for **Server Authentication**.</span></span> <span data-ttu-id="1eaeb-107">Le nom du certificat doit être le nom de domaine complet de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-107">The name of the certificate must be the fully qualified domain name (FQDN) of the computer.</span></span>  
  
 <span data-ttu-id="1eaeb-108">Les certificats sont stockés localement pour les utilisateurs de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-108">Certificates are stored locally for the users on the computer.</span></span> <span data-ttu-id="1eaeb-109">Pour installer un certificat et l'utiliser dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vous devez exécuter le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sous le même compte d'utilisateur que le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , à moins que le service ne s'exécute en tant que compte LocalSystem, NetworkService ou LocalService, auquel cas vous pouvez utiliser un compte d'administrateur.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-109">To install a certificate for use by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must be running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager under the same user account as the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service unless the service is running as LocalSystem, NetworkService, or LocalService, in which case you may use an administrative account.</span></span>  
  
 <span data-ttu-id="1eaeb-110">Le client doit être en mesure de vérifier la propriété du certificat employé par le serveur.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-110">The client must be able to verify the ownership of the certificate used by the server.</span></span> <span data-ttu-id="1eaeb-111">Si le client dispose du certificat de clé publique de l'autorité de certification qui a signé le certificat de serveur, aucune configuration supplémentaire n'est requise.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-111">If the client has the public key certificate of the certification authority that signed the server certificate, no further configuration is necessary.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="1eaeb-112">Windows comprend les certificats de clé publique d'un grand nombre d'autorités de certification.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-112">Windows includes the public key certificates of many certification authorities.</span></span> <span data-ttu-id="1eaeb-113">Si le certificat de serveur a été signé par une autorité de certification publique ou privée pour laquelle le client ne dispose pas de certificat de clé publique, vous devez installer le certificat de clé publique de l'autorité de certification ayant signé le certificat de serveur.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-113">If the server certificate was signed by a public or private certification authority for which the client does not have the public key certificate, you must install the public key certificate of the certification authority that signed the server certificate.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1eaeb-114">Pour utiliser le chiffrement à l'aide d'un cluster de basculement, installez le certificat du serveur avec le nom DNS complet du serveur virtuel sur tous les nœuds du cluster de basculement.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-114">To use encryption with a failover cluster, you must install the server certificate with the fully qualified DNS name of the virtual server on all nodes in the failover cluster.</span></span> <span data-ttu-id="1eaeb-115">Par exemple, si vous avez un cluster à deux nœuds, avec des nœuds nommés test1. *\<your company>* . com et test2. *\<your company>* . et que vous disposez d’un serveur virtuel nommé Virtsql, vous devez installer un certificat pour *\<your company>* Virtsql. com sur les deux nœuds.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-115">For example, if you have a two-node cluster, with nodes named test1.*\<your company>*.com and test2.*\<your company>*.com, and you have a virtual server named virtsql, you need to install a certificate for virtsql.*\<your company>*.com on both nodes.</span></span> <span data-ttu-id="1eaeb-116">Vous pouvez affecter la valeur **ForceEncryption**(Oui) à l’option **ForceEncryption**.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-116">You can set the value of the **ForceEncryption**option to **Yes**.</span></span>  
  
 <span data-ttu-id="1eaeb-117">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="1eaeb-117">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1eaeb-118">**Pour activer les connexions chiffrées :**</span><span class="sxs-lookup"><span data-stu-id="1eaeb-118">**To enable encrypted connections:**</span></span>  
  
     [<span data-ttu-id="1eaeb-119">Installer un certificat sur le serveur</span><span class="sxs-lookup"><span data-stu-id="1eaeb-119">Provision (install) a certificate on the server</span></span>](#Provision)  
  
     [<span data-ttu-id="1eaeb-120">Exporter le certificat de serveur</span><span class="sxs-lookup"><span data-stu-id="1eaeb-120">Export the server certificate</span></span>](#Export)  
  
     [<span data-ttu-id="1eaeb-121">Configurer le serveur afin qu'il accepte les connexions chiffrées</span><span class="sxs-lookup"><span data-stu-id="1eaeb-121">Configure the server to accept encrypted connections</span></span>](#ConfigureServerConnections)  
  
     [<span data-ttu-id="1eaeb-122">Configurer le client pour demander des connexions chiffrées</span><span class="sxs-lookup"><span data-stu-id="1eaeb-122">Configure the client to request encrypted connections</span></span>](#ConfigureClientConnections)  
  
     [<span data-ttu-id="1eaeb-123">Chiffrer une connexion dans SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1eaeb-123">Encrypt a connection from SQL Server Management Studio</span></span>](#EncryptConnection)  
  
##  <a name="SSMSProcedure"></a>  
  
###  <a name="to-provision-install-a-certificate-on-the-server"></a><a name="Provision"></a> <span data-ttu-id="1eaeb-124">Pour installer un certificat sur le serveur</span><span class="sxs-lookup"><span data-stu-id="1eaeb-124">To provision (install) a certificate on the server</span></span>  
  
1.  <span data-ttu-id="1eaeb-125">Dans le menu **Démarrer** , cliquez sur **exécuter**, puis dans la zone **ouvrir** , tapez `MMC` et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-125">On the **Start** menu, click **Run**, and in the **Open** box, type `MMC` and click **OK**.</span></span>  
  
2.  <span data-ttu-id="1eaeb-126">Dans la console MMC, dans le menu **Fichier** , cliquez sur **Ajouter/Supprimer un composant logiciel enfichable**.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-126">In the MMC console, on the **File** menu, click **Add/Remove Snap-in**.</span></span>  
  
3.  <span data-ttu-id="1eaeb-127">Dans la boîte de dialogue **Ajouter/Supprimer un composant logiciel enfichable** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-127">In the **Add/Remove Snap-in** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="1eaeb-128">Dans la boîte de dialogue **Ajout d’un composant logiciel enfichable autonome** , cliquez sur **Certificats**, puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-128">In the **Add Standalone Snap-in** dialog box, click **Certificates**, click **Add**.</span></span>  
  
5.  <span data-ttu-id="1eaeb-129">Dans la boîte de dialogue **Composant logiciel enfichable Certificats** , cliquez sur **Compte d’ordinateur**, puis sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-129">In the **Certificates snap-in** dialog box, click **Computer account**, and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="1eaeb-130">Dans la boîte de dialogue **Ajout d’un composant logiciel enfichable autonome** , cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-130">In the **Add Standalone Snap-in** dialog box, click **Close.**</span></span>  
  
7.  <span data-ttu-id="1eaeb-131">Dans la boîte de dialogue **Ajouter/Supprimer un composant logiciel enfichable** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-131">In the **Add/Remove Snap-in** dialog box, click **OK**.</span></span>  
  
8.  <span data-ttu-id="1eaeb-132">Dans le composant logiciel enfichable **Certificats** , développez **Certificats**, **Personnel**, cliquez avec le bouton droit sur **Certificats**, pointez sur **Toutes les tâches**, puis cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-132">In the **Certificates** snap-in, expand **Certificates**, expand **Personal**, and then right-click **Certificates**, point to **All Tasks**, and then click **Import**.</span></span>  
  
9. <span data-ttu-id="1eaeb-133">Remplissez les informations dans l' **Assistant Importation de certificat**afin d'ajouter un certificat à l'ordinateur, puis fermez la console MMC.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-133">Complete the **Certificate Import Wizard**, to add a certificate to the computer, and close the MMC console.</span></span> <span data-ttu-id="1eaeb-134">Pour plus d'informations sur l'ajout d'un certificat à un ordinateur, consultez la documentation Windows.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-134">For more information about adding a certificate to a computer, see your Windows documentation.</span></span>  
  
###  <a name="to-export-the-server-certificate"></a><a name="Export"></a> <span data-ttu-id="1eaeb-135">Pour exporter le certificat de serveur</span><span class="sxs-lookup"><span data-stu-id="1eaeb-135">To export the server certificate</span></span>  
  
1.  <span data-ttu-id="1eaeb-136">Dans le composant logiciel enfichable **Certificats** , recherchez le certificat dans le dossier **Certificats** / **Personnel** , cliquez avec le bouton droit sur **Certificat**, pointez sur **Toutes les tâches**, puis cliquez sur **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-136">From the **Certificates** snap-in, locate the certificate in the **Certificates** / **Personal** folder, right-click the **Certificate**, point to **All Tasks**, and then click **Export**.</span></span>  
  
2.  <span data-ttu-id="1eaeb-137">Suivez les étapes de l' **Assistant d'exportation de certificats**en stockant le fichier de certificat à un emplacement approprié.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-137">Complete the **Certificate Export Wizard**, storing the certificate file in a convenient location.</span></span>  
  
###  <a name="to-configure-the-server-to-accept-encrypted-connections"></a><a name="ConfigureServerConnections"></a> <span data-ttu-id="1eaeb-138">Pour configurer le serveur afin qu'il accepte les connexions chiffrées</span><span class="sxs-lookup"><span data-stu-id="1eaeb-138">To configure the server to accept encrypted connections</span></span>  
  
1.  <span data-ttu-id="1eaeb-139">Dans le **Gestionnaire de configuration SQL Server**, développez **Configuration du réseau SQL Server**, cliquez avec le bouton droit sur **Protocoles pour** _\<server instance>_ , puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-139">In **SQL Server Configuration Manager**, expand **SQL Server Network Configuration**, right-click **Protocols for** _\<server instance>_, and then select**Properties**.</span></span>  
  
2.  <span data-ttu-id="1eaeb-140">Dans la boîte de dialogue Propriétés de **protocoles pour** _\<instance name>_ **Properties** , sous l’onglet **certificat** , sélectionnez le certificat souhaité dans la liste déroulante de la zone **certificat** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-140">In the **Protocols for**_\<instance name>_ **Properties** dialog box, on the **Certificate** tab, select the desired certificate from the drop down for the **Certificate** box, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="1eaeb-141">Sur l'onglet **Indicateurs** , dans la zone **ForceEncryption** , sélectionnez **Oui**, puis cliquez sur **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-141">On the **Flags** tab, in the **ForceEncryption** box, select **Yes**, and then click **OK** to close the dialog box.</span></span>  
  
4.  <span data-ttu-id="1eaeb-142">Redémarrez le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1eaeb-142">Restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
###  <a name="to-configure-the-client-to-request-encrypted-connections"></a><a name="ConfigureClientConnections"></a> <span data-ttu-id="1eaeb-143">Pour configurer le client afin qu'il demande l'établissement de connexions chiffrées</span><span class="sxs-lookup"><span data-stu-id="1eaeb-143">To configure the client to request encrypted connections</span></span>  
  
1.  <span data-ttu-id="1eaeb-144">Copiez le certificat d'origine ou le fichier de certificat exporté sur l'ordinateur client.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-144">Copy either the original certificate or the exported certificate file to the client computer.</span></span>  
  
2.  <span data-ttu-id="1eaeb-145">Sur l’ordinateur client, utilisez le composant logiciel enfichable **Certificats** pour installer le certificat racine ou le fichier de certificat exporté.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-145">On the client computer, use the **Certificates** snap-in to install either the root certificate or the exported certificate file.</span></span>  
  
3.  <span data-ttu-id="1eaeb-146">Dans le volet de la console, cliquez avec le bouton droit sur **Configuration de SQL Server Native Client**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-146">In the console pane, right-click **SQL Server Native Client Configuration**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="1eaeb-147">Sur la page **Indicateurs** , dans la zone **Forcer le chiffrement du protocole** , cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-147">On the **Flags** page, in the **Force protocol encryption** box, click **Yes**.</span></span>  
  
###  <a name="to-encrypt-a-connection-from-sql-server-management-studio"></a><a name="EncryptConnection"></a><span data-ttu-id="1eaeb-148">Pour chiffrer une connexion à partir de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1eaeb-148">To encrypt a connection from SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="1eaeb-149">Dans la barre d'outils de l'Explorateur d'objets, cliquez sur **Connecter**, puis sur **Moteur de base de données**.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-149">On the Object Explorer toolbar, click **Connect**, and then click **Database Engine**.</span></span>  
  
2.  <span data-ttu-id="1eaeb-150">Dans la boîte de dialogue **Se connecter au serveur** , fournissez les informations de connexion, puis cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-150">In the **Connect to Server** dialog box, complete the connection information, and then click **Options**.</span></span>  
  
3.  <span data-ttu-id="1eaeb-151">Sous l'onglet **Propriétés de connexion** , cliquez sur **Chiffrer la connexion**.</span><span class="sxs-lookup"><span data-stu-id="1eaeb-151">On the **Connection Properties** tab, click **Encrypt connection**.</span></span>  
  
  
