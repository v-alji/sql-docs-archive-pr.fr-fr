---
title: Configurer IIS 7 pour la synchronisation web | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- IIS 7 server configuration [SQL Server replication]
- Web synchronization, IIS 7 servers
ms.assetid: c201fe2c-0a76-44e5-a233-05e14cd224a6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 65b5aa1ea0d314a9675b1c1b90b688d2990e6d24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615129"
---
# <a name="configure-iis-7-for-web-synchronization"></a><span data-ttu-id="f6959-102">Configurer IIS 7 pour la synchronisation web</span><span class="sxs-lookup"><span data-stu-id="f6959-102">Configure IIS 7 for Web Synchronization</span></span>
  <span data-ttu-id="f6959-103">Les procédures décrites dans cette rubrique vous guident dans le processus de configuration manuelle des services IIS ([!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services) version 7 et ultérieures pour une utilisation avec la synchronisation web en vue de la réplication de fusion.</span><span class="sxs-lookup"><span data-stu-id="f6959-103">The procedures in this topic will guide you through the process of manually configuring [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) version 7 and higher for use with Web synchronization for merge replication.</span></span> 
  
 <span data-ttu-id="f6959-104">La configuration d'IIS 7 est la première des trois étapes nécessaires pour activer la synchronisation Web.</span><span class="sxs-lookup"><span data-stu-id="f6959-104">Configuring IIS 7 is the first of three steps needed to enable Web synchronization.</span></span>  
  
 <span data-ttu-id="f6959-105">L’ensemble du processus de configuration est présenté dans [Configurer la synchronisation web](configure-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="f6959-105">For an overview of the entire configuration process, see [Configure Web Synchronization](configure-web-synchronization.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f6959-106">Assurez-vous que votre application utilise uniquement [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] ou une version ultérieure et qu'aucune version antérieure de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] n'est installée sur le serveur IIS.</span><span class="sxs-lookup"><span data-stu-id="f6959-106">Make sure that your application uses only [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] or later versions, and that earlier versions of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] are not installed on the IIS server.</span></span> <span data-ttu-id="f6959-107">Les versions antérieures de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] peuvent provoquer des erreurs, par exemple : « Le format d’un message pendant la synchronisation Web n'était pas valide.</span><span class="sxs-lookup"><span data-stu-id="f6959-107">Earlier versions of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] can cause errors, such as: "The format of a message during Web synchronization was invalid.</span></span> <span data-ttu-id="f6959-108">Vérifiez que les composants de réplication sont correctement configurés sur le serveur Web ».</span><span class="sxs-lookup"><span data-stu-id="f6959-108">Ensure that replication components are properly configured at the Web server."</span></span>  
  
 <span data-ttu-id="f6959-109">Pour utiliser la synchronisation Web, vous devez configurer IIS 7 en effectuant les étapes ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="f6959-109">To use Web synchronization, you must configure IIS 7 by completing the following steps.</span></span> <span data-ttu-id="f6959-110">Chaque étape est détaillée dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="f6959-110">Each step is described in detail in this topic.</span></span>  
  
1.  <span data-ttu-id="f6959-111">Installez et configurez l’écouteur de réplication [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur l’ordinateur qui exécute IIS.</span><span class="sxs-lookup"><span data-stu-id="f6959-111">Install and configure the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener on the computer that is running IIS.</span></span>  
  
2.  <span data-ttu-id="f6959-112">Configurer SSL (Secure Sockets Layer).</span><span class="sxs-lookup"><span data-stu-id="f6959-112">Configure Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="f6959-113">SSL est requis pour les communications entre IIS et tous les abonnés.</span><span class="sxs-lookup"><span data-stu-id="f6959-113">SSL is required for communication between IIS and all subscribers.</span></span>  
  
3.  <span data-ttu-id="f6959-114">Configurez l'authentification IIS.</span><span class="sxs-lookup"><span data-stu-id="f6959-114">Configure IIS authentication.</span></span>  
  
4.  <span data-ttu-id="f6959-115">Configurez un compte et définissez des autorisations pour l'écouteur de réplication [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f6959-115">Configure an account and set permissions for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener.</span></span>  
  
## <a name="installing-the-sql-server-replication-listener"></a><span data-ttu-id="f6959-116">Installation de l'écouteur de réplication SQL Server</span><span class="sxs-lookup"><span data-stu-id="f6959-116">Installing the SQL Server Replication Listener</span></span>  

<span data-ttu-id="f6959-117">La synchronisation web est prise en charge sur IIS à compter de la version 5.0.</span><span class="sxs-lookup"><span data-stu-id="f6959-117">Web synchronization is supported on IIS, beginning with version 5.0.</span></span> <span data-ttu-id="f6959-118">L’Assistant Configuration de la synchronisation Web d’IIS versions 5 et 6 n’est pas disponible avec IIS version 7.0 et ultérieures.</span><span class="sxs-lookup"><span data-stu-id="f6959-118">The Configure Web Synchronization Wizard of IIS version 5 and 6, is not available with IIS version 7.0 and higher.</span></span> <span data-ttu-id="f6959-119">**À partir de SQL Server 2012, pour utiliser le composant de synchronisation web sur le serveur IIS, vous devez installer SQL Server avec la réplication. Il peut s’agir de l’édition gratuite de SQL Server Express.**</span><span class="sxs-lookup"><span data-stu-id="f6959-119">**Beginning with SQL Server 2012, to use the web sync component on IIS server, you should install SQL Server with replication. This can be the free SQL Server Express edition.**</span></span>
  
#### <a name="to-install-and-configure-the-sql-server-replication-listener"></a><span data-ttu-id="f6959-120">Pour installer et configurer l'écouteur de réplication SQL Server</span><span class="sxs-lookup"><span data-stu-id="f6959-120">To install and configure the SQL Server Replication Listener</span></span>  
  
1. <span data-ttu-id="f6959-121">Installez la réplication SQL Server sur l’ordinateur IIS.</span><span class="sxs-lookup"><span data-stu-id="f6959-121">Install SQL Server replication on the IIS computer.</span></span>

2.  <span data-ttu-id="f6959-122">Créez un nouveau répertoire de fichiers pour replisapi.dll sur l'ordinateur exécutant IIS.</span><span class="sxs-lookup"><span data-stu-id="f6959-122">Create a new file directory for replisapi.dll on the computer that is running IIS.</span></span> <span data-ttu-id="f6959-123">Vous pouvez créer le répertoire où vous le souhaitez, mais il est recommandé de le créer sous le répertoire \<*drive*>:\Inetpub.</span><span class="sxs-lookup"><span data-stu-id="f6959-123">You can create the directory wherever you want, but we recommend that you create the directory under the \<*drive*>:\Inetpub directory.</span></span> <span data-ttu-id="f6959-124">Par exemple, créez le répertoire \<*drive*>:\Inetpub\SQLReplication\\.</span><span class="sxs-lookup"><span data-stu-id="f6959-124">For example, create the directory \<*drive*>:\Inetpub\SQLReplication\\.</span></span>  
  
3.  <span data-ttu-id="f6959-125">Copiez replisapi.dll à partir du répertoire [!INCLUDE[ssInstallPathVar](../../includes/ssinstallpathvar-md.md)]com\ vers le répertoire de fichiers que vous avez créé à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="f6959-125">Copy replisapi.dll from the directory [!INCLUDE[ssInstallPathVar](../../includes/ssinstallpathvar-md.md)]com\ to the file directory that you created in step 1.</span></span>  
  
4.  <span data-ttu-id="f6959-126">Inscrivez replisapi.dll :</span><span class="sxs-lookup"><span data-stu-id="f6959-126">Register replisapi.dll:</span></span>  
  
    1.  <span data-ttu-id="f6959-127">Cliquez sur **Démarrer**, puis sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="f6959-127">Click **Start**, and then click **Run**.</span></span> <span data-ttu-id="f6959-128">Dans la zone **ouvrir** , entrez `cmd` , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6959-128">In the **Open** box, enter `cmd`, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="f6959-129">Dans le répertoire créé à l'étape 1, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f6959-129">In the directory created in step 1, execute the following command:</span></span>  
  
         `regsvr32 replisapi.dll`  
  
5.  <span data-ttu-id="f6959-130">Créez un nouveau site Web pour la réplication ou bien utilisez un site Web existant.</span><span class="sxs-lookup"><span data-stu-id="f6959-130">Create a new Web site for replication or use an existing site.</span></span> <span data-ttu-id="f6959-131">Les composants de la réplication accèdent à ce site Web au cours de la synchronisation.</span><span class="sxs-lookup"><span data-stu-id="f6959-131">This Web site will be accessed by replication components during synchronization.</span></span> <span data-ttu-id="f6959-132">Les procédures décrites dans cette rubrique utilisent le site Web par défaut.</span><span class="sxs-lookup"><span data-stu-id="f6959-132">Procedures in this topic will assume the Default Web Site.</span></span> <span data-ttu-id="f6959-133">Pour plus d'informations sur la création de sites Web, consultez la documentation d'IIS.</span><span class="sxs-lookup"><span data-stu-id="f6959-133">For more information about how to create Web sites, see the IIS documentation</span></span>  
  
6.  <span data-ttu-id="f6959-134">Créez un répertoire virtuel dans IIS.</span><span class="sxs-lookup"><span data-stu-id="f6959-134">Create a virtual directory in IIS.</span></span> <span data-ttu-id="f6959-135">Le répertoire virtuel doit être créé sous le site Web créé à l'étape 4 et doit être mappé au répertoire créé à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="f6959-135">The virtual directory should be created under the Web site that you created in step 4 and map it to the directory created in step 1.</span></span> <span data-ttu-id="f6959-136">Soyez aussi restrictif que possible lors de l'attribution des autorisations sur ce répertoire.</span><span class="sxs-lookup"><span data-stu-id="f6959-136">Be as restrictive as possible when you assign permissions to this directory.</span></span> <span data-ttu-id="f6959-137">Vous devez sélectionner au moins les autorisations **Lire** et **Exécuter** .</span><span class="sxs-lookup"><span data-stu-id="f6959-137">You must select at least **Read** and **Execute** permissions.</span></span>  
  
    1.  <span data-ttu-id="f6959-138">Dans le **Gestionnaire des services Internet (IIS)** , dans le volet **Connexions** , cliquez avec le bouton droit sur **Site Web par défaut**, puis sélectionnez **Ajouter un répertoire virtuel**.</span><span class="sxs-lookup"><span data-stu-id="f6959-138">In **Internet Information Services (IIS) Manager**, in the **Connections** pane, right-click **Default Web Site**, and then select **Add Virtual Directory**.</span></span>  
  
    2.  <span data-ttu-id="f6959-139">Pour **alias**, entrez `SQLReplication` .</span><span class="sxs-lookup"><span data-stu-id="f6959-139">For **Alias**, enter `SQLReplication`.</span></span>  
  
    3.  <span data-ttu-id="f6959-140">Pour **Chemin d’accès physique**, entrez **\<drive>:\Inetpub\SQLReplication\\** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6959-140">For **Physical Path**, enter **\<drive>:\Inetpub\SQLReplication\\**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="f6959-141">Configurez IIS pour permettre à replisapi.dll de s'exécuter.</span><span class="sxs-lookup"><span data-stu-id="f6959-141">Configure IIS to enable replisapi.dll to execute.</span></span>  
  
    1.  <span data-ttu-id="f6959-142">Dans le **Gestionnaire des services Internet (IIS)** , cliquez sur **Site Web par défaut**.</span><span class="sxs-lookup"><span data-stu-id="f6959-142">In **Internet Information Services (IIS) Manager**, click **Default Web Site**.</span></span>  
  
    2.  <span data-ttu-id="f6959-143">Dans le volet central, cliquez sur **Mappages de gestionnaire**.</span><span class="sxs-lookup"><span data-stu-id="f6959-143">In the center pane, click **Handler Mappings**.</span></span>  
  
    3.  <span data-ttu-id="f6959-144">Dans le volet **Actions** , cliquez sur **Ajouter un mappage de modules**.</span><span class="sxs-lookup"><span data-stu-id="f6959-144">In the **Actions** pane, click **Add Module Mapping**.</span></span>  
  
    4.  <span data-ttu-id="f6959-145">Pour le chemin d’accès de la **demande** , entrez `replisapi.dll` .</span><span class="sxs-lookup"><span data-stu-id="f6959-145">For **Request** Path, enter `replisapi.dll`.</span></span>  
  
    5.  <span data-ttu-id="f6959-146">Dans la liste déroulante **Module** , sélectionnez **IsapiModule**.</span><span class="sxs-lookup"><span data-stu-id="f6959-146">From the **Module** drop-down list, select **IsapiModule**.</span></span>  
  
    6.  <span data-ttu-id="f6959-147">Pour **Exécutable**, entrez **\<drive>:\Inetpub\SQLReplication\replisapi.dll**.</span><span class="sxs-lookup"><span data-stu-id="f6959-147">For **Executable**, enter **\<drive>:\Inetpub\SQLReplication\replisapi.dll**.</span></span>  
  
    7.  <span data-ttu-id="f6959-148">Pour **Nom**, entrez `Replisapi`.</span><span class="sxs-lookup"><span data-stu-id="f6959-148">For **Name**, enter `Replisapi`.</span></span>  
  
    8.  <span data-ttu-id="f6959-149">Cliquez sur le bouton **Restrictions des demandes** , cliquez sur l'onglet **Accès** , puis sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="f6959-149">Click the **Request Restrictions** button, click the **Access** tab, and then click **Execute**.</span></span>  
  
    9. <span data-ttu-id="f6959-150">Cliquez sur **OK** pour fermer la boîte de dialogue **Restrictions des demandes** , puis cliquez à nouveau sur **OK** pour fermer la boîte de dialogue **Ajouter un mappage de modules** .</span><span class="sxs-lookup"><span data-stu-id="f6959-150">Click **OK** to close the **Request Restrictions** dialog box, and then click **OK** again to close the **Add Module Mapping** dialog box.</span></span> <span data-ttu-id="f6959-151">Lorsque vous êtes invité à autoriser l'extension ISAPI, cliquez sur **Oui** pour ajouter l'extension.</span><span class="sxs-lookup"><span data-stu-id="f6959-151">When you are prompted to allow the ISAPI extension, click **Yes** to add the extension.</span></span>  
  
    10. <span data-ttu-id="f6959-152">Vérifiez que Replisapi.dll apparaît sous les mappages de gestionnaire **Activé** .</span><span class="sxs-lookup"><span data-stu-id="f6959-152">Verify that Replisapi.dll is listed under the **Enabled** handler mappings.</span></span> <span data-ttu-id="f6959-153">S'il est dans la liste **Désactivé** , cliquez avec le bouton droit sur l'entrée Replisapi, puis cliquez sur **Modifier les autorisations de fonction**.</span><span class="sxs-lookup"><span data-stu-id="f6959-153">If it is in the **Disabled** list, right-click the Replisapi entry and then click **Edit Feature Permissions**.</span></span> <span data-ttu-id="f6959-154">Activez la case à cocher **Exécuter** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6959-154">Check the **Execute** box, and then click **OK**.</span></span>  
  
## <a name="configuring-iis-authentication"></a><span data-ttu-id="f6959-155">Configuration de l'authentification IIS</span><span class="sxs-lookup"><span data-stu-id="f6959-155">Configuring IIS Authentication</span></span>  
 <span data-ttu-id="f6959-156">Quand des ordinateurs d'abonnés se connectent à IIS, IIS doit authentifier les abonnés avant qu'ils puissent accéder aux ressources et aux processus.</span><span class="sxs-lookup"><span data-stu-id="f6959-156">When subscriber computers connect to IIS, IIS must authenticate the subscribers before they can access resources and processes.</span></span> <span data-ttu-id="f6959-157">L'authentification peut être appliquée au site Web tout entier ou au répertoire virtuel que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="f6959-157">Authentication can be applied to the whole Web site or to the virtual directory that you created.</span></span>  
  
 <span data-ttu-id="f6959-158">Nous vous recommandons d'utiliser l'authentification de base avec SSL.</span><span class="sxs-lookup"><span data-stu-id="f6959-158">We recommend that you use Basic Authentication with SSL.</span></span> <span data-ttu-id="f6959-159">SSL est nécessaire quel que soit le type d'authentification utilisé.</span><span class="sxs-lookup"><span data-stu-id="f6959-159">SSL is required, regardless of the type of authentication that is used.</span></span>  
  
 <span data-ttu-id="f6959-160">Nous vous recommandons d'utiliser l'authentification de base avec SSL.</span><span class="sxs-lookup"><span data-stu-id="f6959-160">We recommend that you use Basic Authentication with SSL.</span></span> <span data-ttu-id="f6959-161">SSL est nécessaire quel que soit le type d'authentification utilisé.</span><span class="sxs-lookup"><span data-stu-id="f6959-161">SSL is required, regardless of the type of authentication that is used.</span></span>  
  
#### <a name="to-configure-iis-authentication"></a><span data-ttu-id="f6959-162">Pour configurer l'authentification IIS</span><span class="sxs-lookup"><span data-stu-id="f6959-162">To Configure IIS Authentication</span></span>  
  
1.  <span data-ttu-id="f6959-163">Dans le **Gestionnaire des services Internet (IIS)** , cliquez sur **Site Web par défaut**.</span><span class="sxs-lookup"><span data-stu-id="f6959-163">In **Internet Information Services (IIS) Manager**, click **Default Web Site**.</span></span>  
  
2.  <span data-ttu-id="f6959-164">Dans le volet central, double-cliquez sur **Authentification**.</span><span class="sxs-lookup"><span data-stu-id="f6959-164">In the middle pane, double-click **Authentication**.</span></span>  
  
3.  <span data-ttu-id="f6959-165">Cliquez avec le bouton droit sur Authentification anonyme, puis choisissez Désactiver.</span><span class="sxs-lookup"><span data-stu-id="f6959-165">Right-click Anonymous Authentication, and then choose Disable.</span></span>  
  
4.  <span data-ttu-id="f6959-166">Cliquez avec le bouton droit sur Authentification de base, puis choisissez Activer.</span><span class="sxs-lookup"><span data-stu-id="f6959-166">Right-click Basic Authentication, and then choose Enable.</span></span>  
  
## <a name="configuring-secure-sockets-layer"></a><span data-ttu-id="f6959-167">Configuration de SSL (Secure Sockets Layer)</span><span class="sxs-lookup"><span data-stu-id="f6959-167">Configuring Secure Sockets Layer</span></span>  
 <span data-ttu-id="f6959-168">Pour configurer SSL, spécifiez un certificat à utiliser par l'ordinateur exécutant IIS.</span><span class="sxs-lookup"><span data-stu-id="f6959-168">To configure SSL, specify a certificate to be used by the computer running IIS.</span></span> <span data-ttu-id="f6959-169">La synchronisation Web pour la réplication de fusion prend en charge l'utilisation des certificats de serveur, mais pas celle des certificats clients.</span><span class="sxs-lookup"><span data-stu-id="f6959-169">Web synchronization for merge replication supports using server certificates, but not client certificates.</span></span> <span data-ttu-id="f6959-170">Pour configurer IIS pour le déploiement, vous devez d'abord obtenir un certificat auprès d'une Autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="f6959-170">To configure IIS for deployment, you must first obtain a certificate from a certification authority (CA).</span></span> <span data-ttu-id="f6959-171">Pour plus d'informations sur les certificats, consultez la documentation de IIS.</span><span class="sxs-lookup"><span data-stu-id="f6959-171">For more information about certificates, see the IIS documentation.</span></span>  
  
 <span data-ttu-id="f6959-172">Après avoir installé le certificat, vous devez l'associer au site Web utilisé par la synchronisation Web.</span><span class="sxs-lookup"><span data-stu-id="f6959-172">After you install the certificate, you must associate the certificate with the Web site that is used by Web synchronization.</span></span> <span data-ttu-id="f6959-173">Pour le développement et les tests, vous pouvez spécifier un certificat auto-signé.</span><span class="sxs-lookup"><span data-stu-id="f6959-173">For development and testing, you can specify a self-signed certificate.</span></span> <span data-ttu-id="f6959-174">IIS 7 peut créer un certificat automatiquement et l'enregistrer sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="f6959-174">IIS 7 can create a certificate for you and register it on your computer.</span></span>  
  
 <span data-ttu-id="f6959-175">La différence entre un déploiement pour la production et les procédures indiquées ici est que dans le cadre de tests de production et de préproduction, vous utiliseriez un certificat délivré par une autorité de certification au lieu d'un certificat auto-signé.</span><span class="sxs-lookup"><span data-stu-id="f6959-175">The difference between deploying for production and the procedures given here is that in production and pre-production testing, you would use a certificate issued by a CA instead of a self-signed certificate.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f6959-176">Un certificat auto-signé n'est pas recommandé pour une installation de production.</span><span class="sxs-lookup"><span data-stu-id="f6959-176">A self-signed certificate is not recommended for a production installation.</span></span> <span data-ttu-id="f6959-177">Les certificats auto-signés ne sont pas sécurisés.</span><span class="sxs-lookup"><span data-stu-id="f6959-177">Self-signed certificates are not secure.</span></span> <span data-ttu-id="f6959-178">Utilisez des certificats auto-signés uniquement à des fins de développement et de test.</span><span class="sxs-lookup"><span data-stu-id="f6959-178">Use self-signed certificates for development and testing only.</span></span>  
  
 <span data-ttu-id="f6959-179">Pour configurer SSL, vous devez effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="f6959-179">To configure SSL, you will perform the following steps:</span></span>  
  
1.  <span data-ttu-id="f6959-180">Configurez le site Web de manière à ce qu'il exige SSL et ignore les certificats client.</span><span class="sxs-lookup"><span data-stu-id="f6959-180">Configure the Web site to require SSL and ignore client certificates.</span></span>  
  
2.  <span data-ttu-id="f6959-181">Obtenez un certificat auprès d'une autorité de certification ou créez un certificat auto-signé.</span><span class="sxs-lookup"><span data-stu-id="f6959-181">Obtain a certificate from a CA or create a self-signed certificate.</span></span>  
  
3.  <span data-ttu-id="f6959-182">Liez le certificat au site Web de réplication.</span><span class="sxs-lookup"><span data-stu-id="f6959-182">Bind the certificate to the replication Web site.</span></span>  
  
#### <a name="to-require-ssl-security-for-a-web-site"></a><span data-ttu-id="f6959-183">Pour exiger la sécurité SSL pour un site Web</span><span class="sxs-lookup"><span data-stu-id="f6959-183">To require SSL security for a Web site</span></span>  
  
1.  <span data-ttu-id="f6959-184">Dans **Gestionnaire des services Internet (IIS)** , développez le nœud de serveur local, puis cliquez sur le **Site Web par défaut** (ou votre site de synchronisation Web s'il est différent du site Web par défaut).</span><span class="sxs-lookup"><span data-stu-id="f6959-184">In **Internet Information Services (IIS) Manager**, expand the local server node, and then click the **Default Web Site** (or your Web synchronization site if it is different from the default Web site).</span></span>  
  
2.  <span data-ttu-id="f6959-185">Dans le volet central, double-cliquez sur **Paramètres SSL**.</span><span class="sxs-lookup"><span data-stu-id="f6959-185">In the middle pane, double-click **SSL Settings**.</span></span>  
  
3.  <span data-ttu-id="f6959-186">Activez l'option **Exiger SSL** .</span><span class="sxs-lookup"><span data-stu-id="f6959-186">Check the **Require SSL** option.</span></span> <span data-ttu-id="f6959-187">Sous **Certificats clients**, vérifiez que le bouton **Ignorer** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f6959-187">Under **Client certificates**, verify that the **Ignore** button is selected.</span></span>  
  
#### <a name="to-create-a-self-signed-certificate-for-testing"></a><span data-ttu-id="f6959-188">Pour créer un certificat auto-signé à des fins de test</span><span class="sxs-lookup"><span data-stu-id="f6959-188">To create a self-signed certificate for testing</span></span>  
  
1.  <span data-ttu-id="f6959-189">Dans **Gestionnaire des services Internet (IIS)** , cliquez sur le nœud de serveur local, puis dans le volet central, double-cliquez sur **Certificats de serveur**.</span><span class="sxs-lookup"><span data-stu-id="f6959-189">In **Internet Information Services (IIS) Manager**, click the local server node, and then in the center pane, double-click on **Server Certificates**.</span></span>  
  
2.  <span data-ttu-id="f6959-190">Dans le volet **Actions** , cliquez sur **Créer un certificat auto-signé**.</span><span class="sxs-lookup"><span data-stu-id="f6959-190">In the **Actions** pane, click **Create Self-Signed Certificate**.</span></span>  
  
3.  <span data-ttu-id="f6959-191">Dans la boîte de dialogue **Créer un certificat auto-signé** , entrez un nom pour le certificat, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6959-191">In the **Create Self-Signed Certificate** dialog box, enter a name for the certificate, and then click **OK**.</span></span>  
  
###### <a name="to-bind-a-certificate-to-a-web-site"></a><span data-ttu-id="f6959-192">Pour lier un certificat à un site Web</span><span class="sxs-lookup"><span data-stu-id="f6959-192">To bind a certificate to a Web site</span></span>  
  
1.  <span data-ttu-id="f6959-193">Dans le volet **Connexions** , cliquez sur **Site Web par défaut** (ou votre site de synchronisation Web, s'il est différent du site Web par défaut).</span><span class="sxs-lookup"><span data-stu-id="f6959-193">In the **Connections** pane, click the **Default Web Site** (or your Web synchronization site, if it is different from the default Web site).</span></span>  
  
2.  <span data-ttu-id="f6959-194">Dans le volet **Actions** , cliquez sur **Liaisons**, puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f6959-194">In the **Actions** pane, click **Bindings**, and then click **Add**.</span></span> <span data-ttu-id="f6959-195">La boîte de dialogue **Ajouter la liaison de site** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="f6959-195">The **Add Site Binding** dialog box will appear.</span></span>  
  
3.  <span data-ttu-id="f6959-196">Dans la liste déroulante **Type** , sélectionnez **https**.</span><span class="sxs-lookup"><span data-stu-id="f6959-196">From the **Type** drop-down list, select **https**.</span></span> <span data-ttu-id="f6959-197">Laissez les paramètres par défaut pour **Adresse IP** et **Port**.</span><span class="sxs-lookup"><span data-stu-id="f6959-197">Leave the default settings for **IP address** and **Port**.</span></span>  
  
4.  <span data-ttu-id="f6959-198">Dans la liste déroulante **Certificat SSL** , sélectionnez le certificat créé dans « Pour créer un certificat auto-signé à des fins de test », cliquez sur **OK**, puis sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="f6959-198">From the **SSL certificate** drop-down list, select the certificate created in "To create a self-signed certificate for testing," click **OK**, and then click **Close**.</span></span>  
  
###### <a name="to-test-the-certificate"></a><span data-ttu-id="f6959-199">Pour tester le certificat</span><span class="sxs-lookup"><span data-stu-id="f6959-199">To test the certificate</span></span>  
  
1.  <span data-ttu-id="f6959-200">Dans le **Dans leternet Dans leformation Services (IIS) Manager**, cliquez sur **Site Web par défaut.**</span><span class="sxs-lookup"><span data-stu-id="f6959-200">In **Internet Information Services (IIS) Manager**, click **Default Web Site.**</span></span>  
  
2.  <span data-ttu-id="f6959-201">Dans le volet **Actions**, cliquez sur **Parcourir \*:443(https)** .</span><span class="sxs-lookup"><span data-stu-id="f6959-201">From the **Actions** pane, click **Browse \*:443(https)**.</span></span>  
  
3.  <span data-ttu-id="f6959-202">Internet Explorer ouvrira et affichera un message indiquant : « le certificat de sécurité de ce site Web présente un problème ».</span><span class="sxs-lookup"><span data-stu-id="f6959-202">Internet Explorer will open and display a message that "There is a problem with this website's security certificate."</span></span> <span data-ttu-id="f6959-203">Cet avertissement indique que le certificat associé n'a pas été émis par une autorité de certification reconnue et n'est peut-être pas digne de confiance.</span><span class="sxs-lookup"><span data-stu-id="f6959-203">This warning tells you that the associated certificate was not issued by a recognized CA and might not be trustworthy.</span></span> <span data-ttu-id="f6959-204">Cet avertissement est attendu, donc cliquez sur **Poursuivre sur ce site Web (non recommandé)** .</span><span class="sxs-lookup"><span data-stu-id="f6959-204">This is an expected warning, so click **Continue to this website (not recommended)**.</span></span>  
  
4.  <span data-ttu-id="f6959-205">Si vous êtes invité à **Se connecter à localhost**, entrez un nom d'utilisateur et un mot de passe pour continuer.</span><span class="sxs-lookup"><span data-stu-id="f6959-205">If you are prompted to **Connect to localhost**, enter a user name and password to proceed.</span></span> <span data-ttu-id="f6959-206">La page par défaut du site Web doit s'afficher.</span><span class="sxs-lookup"><span data-stu-id="f6959-206">You should see the default page for the Web site.</span></span>  
  
## <a name="setting-permissions-for-the-sql-server-replication-listener"></a><span data-ttu-id="f6959-207">Définition des autorisations pour l'écouteur de réplication SQL Server</span><span class="sxs-lookup"><span data-stu-id="f6959-207">Setting Permissions for the SQL Server Replication Listener</span></span>  
 <span data-ttu-id="f6959-208">Lorsque l'ordinateur d'un abonné se connecte à l'ordinateur exécutant IIS, l'abonné est authentifié à l'aide du type d'authentification spécifié lors de la configuration d'IIS.</span><span class="sxs-lookup"><span data-stu-id="f6959-208">When a subscriber computer connects to the computer running IIS, the subscriber is authenticated by using the type of authentication specified when you configured IIS.</span></span> <span data-ttu-id="f6959-209">Après avoir authentifié l'abonné, IIS vérifie que l'abonné est autorisé à appeler la réplication [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f6959-209">After IIS authenticates the subscriber, IIS checks whether the subscriber is authorized to invoke [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replication.</span></span> <span data-ttu-id="f6959-210">Vous contrôlez les utilisateurs en mesure d'appeler la réplication [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en définissant des autorisations pour replisapi.dll.</span><span class="sxs-lookup"><span data-stu-id="f6959-210">You control the users that can invoke [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replication by setting permissions for replisapi.dll.</span></span> <span data-ttu-id="f6959-211">La configuration correcte des autorisations est cruciale pour empêcher les accès non autorisés à la réplication [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f6959-211">Properly configuring permissions is necessary to prevent unauthorized access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replication.</span></span>  
  
 <span data-ttu-id="f6959-212">Pour configurer les autorisations minimales du compte sous lequel est exécuté l'écouteur de réplication [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , suivez la procédure ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="f6959-212">To configure the minimum permissions for the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener runs, complete the following procedure.</span></span> <span data-ttu-id="f6959-213">Les étapes dans la procédure suivante s'appliquent à [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Server 2008 qui exécute IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="f6959-213">The steps in the following procedure apply to [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Server 2008 running IIS 7.0.</span></span>  
  
 <span data-ttu-id="f6959-214">En plus de suivre les étapes ci-dessous, vérifiez que les noms de connexion requis se trouvent dans la liste d'accès à la publication (PAL, Publication Access List).</span><span class="sxs-lookup"><span data-stu-id="f6959-214">In addition to performing the following steps, make sure that the required logins are in the publication access list (PAL).</span></span> <span data-ttu-id="f6959-215">Pour plus d’informations sur la liste d’accès à la publication, consultez [Sécuriser le serveur de publication](security/secure-the-publisher.md).</span><span class="sxs-lookup"><span data-stu-id="f6959-215">For more information about the PAL, see [Secure the Publisher](security/secure-the-publisher.md).</span></span>  
  
 <span data-ttu-id="f6959-216">**Important** Le compte créé dans cette section est le compte qui se connecte au serveur de publication et au serveur de distribution lors de la synchronisation.</span><span class="sxs-lookup"><span data-stu-id="f6959-216">**Important** The account created in this section is the account that will connect to the Publisher and Distributor during synchronization.</span></span> <span data-ttu-id="f6959-217">Ce compte doit être ajouté comme compte de connexion SQL sur le serveur de distribution et le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="f6959-217">This account must be added as a SQL Login account on the distribution and publication server.</span></span>  
  
 <span data-ttu-id="f6959-218">Le compte utilisé pour l'écouteur de réplication SQL Server doit avoir les autorisations décrites dans la rubrique Sécurité de l'Agent de fusion, dans la section « Se connecter au serveur de publication ou au serveur de distribution ».</span><span class="sxs-lookup"><span data-stu-id="f6959-218">The account used for the SQL Server Replication Listener must have permissions as described in the Merge Agent Security topic, in the "Connect to the Publisher or Distributor" section.</span></span>  
  
 <span data-ttu-id="f6959-219">En résumé, le compte doit :</span><span class="sxs-lookup"><span data-stu-id="f6959-219">In summary, the account must:</span></span>  
  
-   <span data-ttu-id="f6959-220">être membre de la liste d'accès à la publication (PAL) ;</span><span class="sxs-lookup"><span data-stu-id="f6959-220">Be a member of the Publication Access List (PAL).</span></span>  
  
-   <span data-ttu-id="f6959-221">être mappé à une connexion associée à un utilisateur enregistré dans la base de données de publication ;</span><span class="sxs-lookup"><span data-stu-id="f6959-221">Be mapped to a login associated with a user in the publication database.</span></span>  
  
-   <span data-ttu-id="f6959-222">être mappé à une connexion associée à un utilisateur enregistré dans la base de données de distribution ;</span><span class="sxs-lookup"><span data-stu-id="f6959-222">Be mapped to a login associated with a user in the distribution database.</span></span>  
  
-   <span data-ttu-id="f6959-223">être autorisé à lire sur le partage de fichiers d'instantanés.</span><span class="sxs-lookup"><span data-stu-id="f6959-223">Have Read permissions on the snapshot share.</span></span>  
  
#### <a name="to-configure-the-account-and-permissions"></a><span data-ttu-id="f6959-224">Pour configurer le compte et les autorisations</span><span class="sxs-lookup"><span data-stu-id="f6959-224">To configure the account and permissions</span></span>  
  
1.  <span data-ttu-id="f6959-225">Créez un compte local sur l'ordinateur exécutant IIS :</span><span class="sxs-lookup"><span data-stu-id="f6959-225">Create a local account on the computer running IIS:</span></span>  
  
    1.  <span data-ttu-id="f6959-226">Ouvrez **Gestionnaire de serveur**.</span><span class="sxs-lookup"><span data-stu-id="f6959-226">Open **Server Manager**.</span></span> <span data-ttu-id="f6959-227">Dans le menu Démarrer, cliquez avec le bouton droit sur **Poste de travail**, puis cliquez sur **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="f6959-227">From the Start menu, right-click **Computer**, and then click **Manage**.</span></span>  
  
    2.  <span data-ttu-id="f6959-228">Dans **Gestionnaire de serveur**, développez **Configuration**, puis développez **Utilisateurs et groupes locaux**.</span><span class="sxs-lookup"><span data-stu-id="f6959-228">In **Server Manager**, expand **Configuration**, and then expand **Local Users and Groups**.</span></span>  
  
    3.  <span data-ttu-id="f6959-229">Cliquez avec le bouton droit sur **Utilisateurs**, puis cliquez sur **Nouvel utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="f6959-229">Right-click **Users**, and then click **New User**.</span></span>  
  
    4.  <span data-ttu-id="f6959-230">Entrez un nom d'utilisateur et un mot de passe fort.</span><span class="sxs-lookup"><span data-stu-id="f6959-230">Enter a user name and a strong password.</span></span> <span data-ttu-id="f6959-231">Désactivez **L'utilisateur doit changer le mot de passe à la prochaine ouverture de session**.</span><span class="sxs-lookup"><span data-stu-id="f6959-231">Clear **User must change password at next logon**.</span></span>  
  
    5.  <span data-ttu-id="f6959-232">Cliquez sur **Créer**, puis sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="f6959-232">Click **Create**, and then click **Close**.</span></span>  
  
2.  <span data-ttu-id="f6959-233">Ajoutez le compte au groupe IIS_IUSRS :</span><span class="sxs-lookup"><span data-stu-id="f6959-233">Add the account to the IIS_IUSRS group:</span></span>  
  
    1.  <span data-ttu-id="f6959-234">Dans **Gestionnaire de serveur**, développez **Configuration**, développez **Utilisateurs et groupes locaux**, puis cliquez sur **Groupes**.</span><span class="sxs-lookup"><span data-stu-id="f6959-234">In **Server Manager**, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>  
  
    2.  <span data-ttu-id="f6959-235">Cliquez avec le bouton droit sur **IIS_IUSRS**, puis cliquez sur **Ajouter au groupe**.</span><span class="sxs-lookup"><span data-stu-id="f6959-235">Right-click **IIS_IUSRS**, and then click **Add to Group**.</span></span>  
  
    3.  <span data-ttu-id="f6959-236">Dans la boîte de dialogue **Propriétés de IIS_IUSRS** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f6959-236">In the **IIS_IUSRS Properties** dialog box, click **Add**.</span></span>  
  
    4.  <span data-ttu-id="f6959-237">Dans la boîte de dialogue **Choisir des utilisateurs, des ordinateurs ou des groupes** , ajoutez le compte créé à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="f6959-237">In the **Select Users, Computers, or Groups** dialog box, add the account created in step 1.</span></span>  
  
    5.  <span data-ttu-id="f6959-238">Vérifiez que **À partir de cet emplacement** indique le nom de l'ordinateur local (et non un domaine).</span><span class="sxs-lookup"><span data-stu-id="f6959-238">Verify that **From this location** displays the name of the local computer (not a domain).</span></span> <span data-ttu-id="f6959-239">Si ce champ n'indique pas le nom de l'ordinateur local, cliquez sur **Emplacements**.</span><span class="sxs-lookup"><span data-stu-id="f6959-239">If this field does not display the local computer name, click **Locations**.</span></span> <span data-ttu-id="f6959-240">Dans la boîte de dialogue **Emplacements** , choisissez l'ordinateur local, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6959-240">In the **Locations** dialog box, select the local computer, and then click **OK**.</span></span>  
  
    6.  <span data-ttu-id="f6959-241">Dans les boîtes de dialogue **Sélectionnez les utilisateurs** et **Propriétés de IIS_IUSRS** , cliquez sur**OK**.</span><span class="sxs-lookup"><span data-stu-id="f6959-241">In the **Select Users** dialog box and the **IIS_IUSRS Properties** dialog box, click**OK**.</span></span>  
  
3.  <span data-ttu-id="f6959-242">Attribuez des autorisations de compte minimales sur le dossier qui contient replisapi.dll :</span><span class="sxs-lookup"><span data-stu-id="f6959-242">Grant minimum account permissions on the folder that contains replisapi.dll:</span></span>  
  
    1.  <span data-ttu-id="f6959-243">Dans Windows Explorer, cliquez avec le bouton droit sur le dossier créé pour replisapi.dll, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f6959-243">In Windows Explorer, right-click the folder that you created for replisapi.dll, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="f6959-244">Sur l'onglet **Sécurité** , cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="f6959-244">On the **Security** tab, click **Edit**.</span></span>  
  
    3.  <span data-ttu-id="f6959-245">Dans la boîte de dialogue **Autorisations pour \<foldername>** , cliquez sur **Ajouter** pour ajouter le compte créé à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="f6959-245">In the **Permissions for \<foldername>** dialog box, click **Add** to add the account that you created in step 1.</span></span>  
  
    4.  <span data-ttu-id="f6959-246">Vérifiez que **À partir de cet emplacement** indique le nom de l'ordinateur local (et non un domaine).</span><span class="sxs-lookup"><span data-stu-id="f6959-246">Verify that **From this location** displays the name of the local computer (not a domain).</span></span> <span data-ttu-id="f6959-247">Si ce champ n'indique pas le nom de l'ordinateur local, cliquez sur **Emplacements**.</span><span class="sxs-lookup"><span data-stu-id="f6959-247">If this field does not display the local computer name, click **Locations**.</span></span> <span data-ttu-id="f6959-248">Dans la boîte de dialogue **Emplacements** , choisissez l'ordinateur local, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6959-248">In the **Locations** dialog box, select the local computer, and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="f6959-249">Vérifiez que le compte dispose uniquement des autorisations **Lecture**, **Lecture et exécution** et **Affichage du contenu du dossier**.</span><span class="sxs-lookup"><span data-stu-id="f6959-249">Verify that the account is granted only **Read**, **Read & Execute**, and **List Folder Contents** permissions.</span></span>  
  
    6.  <span data-ttu-id="f6959-250">Sélectionnez tous les utilisateurs ou groupes qui ne requièrent pas l'accès au répertoire, cliquez sur **Supprimer**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6959-250">Select any users or groups that do not require access to the directory, click **Remove**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="f6959-251">Créez un pool d'applications dans **Gestionnaire des services Internet (IIS)** :</span><span class="sxs-lookup"><span data-stu-id="f6959-251">Create an application pool in **Internet Information Services (IIS) Manager**:</span></span>  
  
    1.  <span data-ttu-id="f6959-252">Dans **Gestionnaire des services Internet (IIS)** , dans le volet **Connexions** développez le nœud de serveur local.</span><span class="sxs-lookup"><span data-stu-id="f6959-252">In **Internet Information Services (IIS) Manager**, in the **Connections** pane, expand the local server node.</span></span>  
  
    2.  <span data-ttu-id="f6959-253">Cliquez avec le bouton droit sur **Pools d'applications**, puis cliquez sur **Ajouter un pool d'applications**.</span><span class="sxs-lookup"><span data-stu-id="f6959-253">Right-click **Application Pools**, and then click **Add Application Pool**.</span></span>  
  
    3.  <span data-ttu-id="f6959-254">Entrez un nom pour le pool d'applications, laissez les valeurs par défaut pour les champs restants, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6959-254">Enter a name for the application pool, leave the default values for the remaining fields, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f6959-255">Si vous prévoyez d'avoir plus de deux clients de synchronisation simultanés, vous pouvez créer un domaine privé Web.</span><span class="sxs-lookup"><span data-stu-id="f6959-255">If you anticipate having more than two concurrent synchronization clients, you might want to create a web garden.</span></span> <span data-ttu-id="f6959-256">Pour plus d’informations, consultez « Création d’un domaine privé web » dans [Configurer la synchronisation web](configure-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="f6959-256">For more information, see "Creating a Web Garden" in [Configure Web Synchronization](configure-web-synchronization.md).</span></span>  
  
5.  <span data-ttu-id="f6959-257">Associez le compte au pool d'applications :</span><span class="sxs-lookup"><span data-stu-id="f6959-257">Associate the account with the application pool:</span></span>  
  
    1.  <span data-ttu-id="f6959-258">Dans **Gestionnaire des services Internet (IIS)** , développez le nœud du serveur local, puis cliquez sur le nœud **Pools d'applications**.</span><span class="sxs-lookup"><span data-stu-id="f6959-258">In **Internet Information Services (IIS) Manager**, expand the local server node, and then click on **Application Pools**.</span></span>  
  
    2.  <span data-ttu-id="f6959-259">Cliquez avec le bouton droit sur le pool d'applications que vous avez créé, puis cliquez sur **Définir les valeurs par défaut des pools d'applications**.</span><span class="sxs-lookup"><span data-stu-id="f6959-259">Right-click the application pool that you created, and then click **Set Application Pool Defaults**.</span></span>  
  
    3.  <span data-ttu-id="f6959-260">Dans la boîte de dialogue **Valeurs par défaut du pool d'applications** , faites défiler jusqu'à la section **Traiter le modèle** , puis cliquez sur le champ **Identité** .</span><span class="sxs-lookup"><span data-stu-id="f6959-260">In the **Application Pool Defaults** dialog box, scroll down to the **Process Model** section, and then click the **Identity** field.</span></span>  
  
    4.  <span data-ttu-id="f6959-261">Cliquez sur le bouton de sélection à droite de la ligne **Identité** .</span><span class="sxs-lookup"><span data-stu-id="f6959-261">Click the ellipsis button on the right side of the **Identity** row.</span></span>  
  
    5.  <span data-ttu-id="f6959-262">Cliquez sur la case d'option **Compte personnalisé** , puis sur **Définir**.</span><span class="sxs-lookup"><span data-stu-id="f6959-262">Click the **Custom Account** radio button, and then click **Set**.</span></span>  
  
    6.  <span data-ttu-id="f6959-263">Dans les champs **Nom d'utilisateur** et **Mot de passe** , entrez le compte et le mot de passe créés à l'étape 1, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6959-263">In the **User name** and **Password** fields, enter the account and password that were created in step 1, and then click **OK**.</span></span>  
  
    7.  <span data-ttu-id="f6959-264">Cliquez sur **OK** pour fermer la boîte de dialogue **Identité du pool d’applications** , puis cliquez à nouveau sur **OK** pour fermer la boîte de dialogue **Valeurs par défaut du pool d’applications**.</span><span class="sxs-lookup"><span data-stu-id="f6959-264">Click **OK** to close the **Application Pool Identity** dialog box, and then click **OK** again to close the **Application Pool Defaults**dialog box.</span></span>  
  
6.  <span data-ttu-id="f6959-265">Associez le pool d'applications au site Web de réplication :</span><span class="sxs-lookup"><span data-stu-id="f6959-265">Associate the application pool with the replication Web site:</span></span>  
  
    1.  <span data-ttu-id="f6959-266">Dans **Gestionnaire des services Internet (IIS)** , développez le nœud de serveur local, puis cliquez sur le **Site Web par défaut** (ou votre site de synchronisation Web s'il est différent du site Web par défaut).</span><span class="sxs-lookup"><span data-stu-id="f6959-266">In **Internet Information Services (IIS) Manager**, expand the local server node, and then click on the **Default Web Site** (or your Web synchronization site if it is different from the default Web site).</span></span>  
  
    2.  <span data-ttu-id="f6959-267">Dans le volet **Actions** , sous **Gérer le site Web**, cliquez sur **Paramètres avancés**.</span><span class="sxs-lookup"><span data-stu-id="f6959-267">In the **Actions** pane, under **Manage Web Site**, click **Advanced Settings**.</span></span>  
  
    3.  <span data-ttu-id="f6959-268">Dans la boîte de dialogue **Paramètres avancés** , cliquez sur le bouton de sélection à droite de **Pool d'applications**.</span><span class="sxs-lookup"><span data-stu-id="f6959-268">In the **Advanced Settings** dialog box, click on the ellipsis button to the right of **Application Pool**.</span></span>  
  
    4.  <span data-ttu-id="f6959-269">Dans la liste déroulante **Pool d'applications** , sélectionnez le pool d'applications créé à l'étape 4, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6959-269">From the **Application pool** drop-down list, select the application pool you created in step 4, and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="f6959-270">Cliquez à nouveau sur **OK** pour fermer Paramètres avancés.</span><span class="sxs-lookup"><span data-stu-id="f6959-270">Click **OK** again to close Advanced Settings.</span></span>  
  
## <a name="testing-the-connection-to-replisapidll"></a><span data-ttu-id="f6959-271">Test de la connexion à replisapi.dll</span><span class="sxs-lookup"><span data-stu-id="f6959-271">Testing the Connection to replisapi.dll</span></span>  
 <span data-ttu-id="f6959-272">Exécutez la synchronisation Web en mode de diagnostic pour tester la connexion à l'ordinateur exécutant IIS et pour vérifier que le certificat SSL (Secure Sockets Layer) est correctement installé.</span><span class="sxs-lookup"><span data-stu-id="f6959-272">Run Web synchronization in diagnostic mode to test the connection to the computer running IIS and to make sure that the Secure Sockets Layer (SSL) certificate is properly installed.</span></span> <span data-ttu-id="f6959-273">Pour exécuter la synchronisation Web en mode de diagnostic, vous devez avoir la qualité d'administrateur sur l'ordinateur qui exécute les services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="f6959-273">To run Web synchronization in diagnostic mode, you must be an administrator on the computer running IIS.</span></span>  
  
#### <a name="to-test-the-connection-to-replisapidll"></a><span data-ttu-id="f6959-274">Pour tester la connexion à replisapi.dll</span><span class="sxs-lookup"><span data-stu-id="f6959-274">To test the connection to replisapi.dll</span></span>  
  
1.  <span data-ttu-id="f6959-275">Vérifiez que les paramètres du réseau local (LAN) sur l'Abonné sont corrects :</span><span class="sxs-lookup"><span data-stu-id="f6959-275">Make sure that local area network (LAN) settings at the Subscriber are correct:</span></span>  
  
    1.  <span data-ttu-id="f6959-276">Dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer, dans le menu **Outils** , cliquez sur **Options Internet**.</span><span class="sxs-lookup"><span data-stu-id="f6959-276">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer, on the **Tools** menu, click **Internet Options**.</span></span>  
  
    2.  <span data-ttu-id="f6959-277">Sur l'onglet **Connexions** , cliquez sur **Paramètres LAN**.</span><span class="sxs-lookup"><span data-stu-id="f6959-277">On the **Connections** tab, click **LAN Settings**.</span></span>  
  
    3.  <span data-ttu-id="f6959-278">S'il n'y a pas de serveur proxy utilisé sur le réseau local, désactivez **Détecter automatiquement les paramètres de connexion** et **Utiliser un serveur proxy pour votre réseau local**.</span><span class="sxs-lookup"><span data-stu-id="f6959-278">If a proxy server is not used on the LAN, clear **Automatically Detect Settings** and **Use a proxy server for your LAN**.</span></span>  
  
    4.  <span data-ttu-id="f6959-279">Si un serveur proxy est utilisé, cliquez sur **Utiliser un serveur proxy pour votre réseau local** et **Ne pas utiliser de serveur proxy pour les adresses locales**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6959-279">If a proxy server is used, click **Use a proxy server for your LAN** and **Bypass proxy server for local addresses**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="f6959-280">Sur l'Abonné, dans Internet Explorer, connectez-vous au serveur en mode de diagnostic en ajoutant `?diag` à l'adresse pour le fichier replisapi.dll.</span><span class="sxs-lookup"><span data-stu-id="f6959-280">At the Subscriber, in Internet Explorer, connect to the server in diagnostic mode by appending `?diag` to the address for the replisapi.dll.</span></span> <span data-ttu-id="f6959-281">Par exemple : `https://server.domain.com/directory/replisapi.dll?diag`.</span><span class="sxs-lookup"><span data-stu-id="f6959-281">For example: `https://server.domain.com/directory/replisapi.dll?diag`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f6959-282">Dans l'exemple ci-dessus, **server.domain.com** doit être remplacé par le nom exact de **Délivré à** répertorié sous la section **Certificats de serveur** dans Gestionnaire des services IIS.</span><span class="sxs-lookup"><span data-stu-id="f6959-282">In the example above, **server.domain.com** should be replaced with the exact **Issued To** name listed under the **Server Certificates** section in IIS Manager.</span></span>  
  
3.  <span data-ttu-id="f6959-283">Si le certificat spécifié pour IIS n'est pas reconnu par le système d'exploitation Windows, la boîte de dialogue **Alerte de sécurité** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="f6959-283">If the certificate that you specified for IIS is not recognized by the Windows operating system, the **Security Alert** dialog box appears.</span></span> <span data-ttu-id="f6959-284">Cette alerte peut se produire si le certificat est un certificat de test ou si le certificat a été émis par une Autorité de certification non reconnue par Windows.</span><span class="sxs-lookup"><span data-stu-id="f6959-284">This alert might occur because the certificate is a test certificate or the certificate was issued by a certification authority (CA) that Windows does not recognize.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f6959-285">Si cette boîte de dialogue ne s'affiche pas, vérifiez que le certificat pour le serveur auquel vous accédez a été ajouté au magasin de certificats sur l'Abonné en tant que certificat approuvé.</span><span class="sxs-lookup"><span data-stu-id="f6959-285">If this dialog box does not appear, make sure that the certificate for the server that you are accessing has been added to the certificate store at the Subscriber as a trusted certificate.</span></span> <span data-ttu-id="f6959-286">Pour plus d'informations sur l'exportation de certificats, consultez la documentation d'IIS.</span><span class="sxs-lookup"><span data-stu-id="f6959-286">For more information about exporting certificates, see the IIS documentation.</span></span>  
  
    1.  <span data-ttu-id="f6959-287">Dans la boîte de dialogue **Alerte de sécurité** , cliquez sur **Afficher le certificat**.</span><span class="sxs-lookup"><span data-stu-id="f6959-287">In the **Security Alert** dialog box, click **View Certificate**.</span></span>  
  
    2.  <span data-ttu-id="f6959-288">Dans la boîte de dialogue **Certificat** , sur l'onglet **Général** , cliquez sur **Installer le certificat**.</span><span class="sxs-lookup"><span data-stu-id="f6959-288">In the **Certificate** dialog box, on the **General** tab, click **Install Certificate**.</span></span>  
  
    3.  <span data-ttu-id="f6959-289">Terminez l'Assistant Importation de certificat, en acceptant les valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="f6959-289">Complete the Certificate Import Wizard, accepting the defaults.</span></span>  
  
    4.  <span data-ttu-id="f6959-290">Dans la boîte de dialogue **Avertissement de sécurité** , cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="f6959-290">In the **Security Warning** dialog box, click **Yes**.</span></span>  
  
    5.  <span data-ttu-id="f6959-291">Dans la boîte de dialogue de confirmation de l'Assistant Importation de certificat, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6959-291">In the Certificate Import Wizard confirmation dialog box, click **OK**.</span></span>  
  
    6.  <span data-ttu-id="f6959-292">Fermez la boîte de dialogue **Certificat** .</span><span class="sxs-lookup"><span data-stu-id="f6959-292">Close the **Certificate** dialog box.</span></span>  
  
    7.  <span data-ttu-id="f6959-293">Dans la boîte de dialogue **Alerte de sécurité** , cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="f6959-293">In the **Security Alert** dialog box, click **Yes**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f6959-294">Les certificats sont installés pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f6959-294">Certificates are installed for users.</span></span> <span data-ttu-id="f6959-295">Ce processus doit être effectué pour chaque utilisateur qui réalisera des synchronisations avec IIS.</span><span class="sxs-lookup"><span data-stu-id="f6959-295">This process must be performed for each user that will synchronize with IIS.</span></span>  
  
4.  <span data-ttu-id="f6959-296">Dans la boîte de dialogue **Se connecter à\<ServerName>** , spécifiez la connexion et le mot de passe que l’'Agent de fusion va utiliser pour se connecter à IIS.</span><span class="sxs-lookup"><span data-stu-id="f6959-296">In the **Connect to \<ServerName>** dialog box, specify the login and password that the Merge Agent will use to connect to IIS.</span></span> <span data-ttu-id="f6959-297">Ces informations d'identification seront aussi spécifiées dans l'Assistant Nouvel abonnement.</span><span class="sxs-lookup"><span data-stu-id="f6959-297">These credentials will also be specified in the New Subscription Wizard.</span></span>  
  
5.  <span data-ttu-id="f6959-298">Dans la fenêtre Internet Explorer relative aux **informations de diagnostic SQL Websync**, vérifiez que la valeur de chaque colonne **État** de la page est **RÉUSSITE**.</span><span class="sxs-lookup"><span data-stu-id="f6959-298">In the Internet Explorer window called **SQL Websync diagnostic information**, verify that the value in each **Status** column on the page is **SUCCESS**.</span></span>  
  
6.  <span data-ttu-id="f6959-299">Vérifiez que le certificat est installé correctement sur l'Abonné :</span><span class="sxs-lookup"><span data-stu-id="f6959-299">Make sure that the certificate is installed correctly on the Subscriber:</span></span>  
  
    1.  <span data-ttu-id="f6959-300">Fermez, puis rouvrez Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="f6959-300">Close and then reopen Internet Explorer.</span></span>  
  
    2.  <span data-ttu-id="f6959-301">Connectez-vous au serveur en mode de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="f6959-301">Connect to the server in diagnostic mode.</span></span> <span data-ttu-id="f6959-302">Si le certificat est installé correctement, la boîte de dialogue **Alerte de sécurité** ne s'affiche pas.</span><span class="sxs-lookup"><span data-stu-id="f6959-302">If the certificate is installed properly, the **Security Alert** dialog box will not appear.</span></span> <span data-ttu-id="f6959-303">Si cette boîte de dialogue s'affiche, l'Agent de fusion échoue quand il tente de se connecter à l'ordinateur exécutant IIS.</span><span class="sxs-lookup"><span data-stu-id="f6959-303">If the dialog box appears, the Merge Agent will fail when it tries to connect to the computer that is running IIS.</span></span> <span data-ttu-id="f6959-304">Vous devez vérifier que le certificat pour le serveur auquel vous accédez a été ajouté au magasin de certificats sur l'Abonné en tant que certificat approuvé.</span><span class="sxs-lookup"><span data-stu-id="f6959-304">You must make sure that the certificate for the server that you are accessing has been added to the certificate store at the Subscriber as a trusted certificate.</span></span> <span data-ttu-id="f6959-305">Pour plus d'informations sur l'exportation de certificats, consultez la documentation d'IIS.</span><span class="sxs-lookup"><span data-stu-id="f6959-305">For more information about exporting certificates, see the IIS documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6959-306">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f6959-306">See Also</span></span>  
 <span data-ttu-id="f6959-307">[Synchronisation web pour la réplication de fusion](web-synchronization-for-merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="f6959-307">[Web Synchronization for Merge Replication](web-synchronization-for-merge-replication.md) </span></span>  
 [<span data-ttu-id="f6959-308">Configurer la synchronisation web</span><span class="sxs-lookup"><span data-stu-id="f6959-308">Configure Web Synchronization</span></span>](configure-web-synchronization.md)  
  
  
