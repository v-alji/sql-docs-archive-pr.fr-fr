---
title: Configurer un serveur de rapports pour la remise par messagerie (SSRS Configuration Manager) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services], distributing
- report servers [Reporting Services], e-mail delivery
- remote SMTP service [Reporting Services]
- distributing reports [Reporting Services], e-mail
- CDO
- Collaboration Data Objects
- SMTP settings [Reporting Services]
- e-mail [Reporting Services]
- sending reports
- mail [Reporting Services]
- local SMTP service [Reporting Services]
ms.assetid: b838f970-d11a-4239-b164-8d11f4581d83
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 3122dbbb5debc90afa73ca0f8ab0d8e23d38a0ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611518"
---
# <a name="configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager"></a><span data-ttu-id="2378f-102">Configurer un serveur de rapports pour la remise par messagerie (Gestionnaire de configuration de SSRS)</span><span class="sxs-lookup"><span data-stu-id="2378f-102">Configure a Report Server for E-Mail Delivery (SSRS Configuration Manager)</span></span>


  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="2378f-103">comprend une extension de la remise du courrier électronique que vous pouvez utiliser pour distribuer les rapports par courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="2378f-103">includes an e-mail delivery extension so that you can distribute reports through e-mail.</span></span> <span data-ttu-id="2378f-104">Selon la façon dont vous définissez l'abonnement de messagerie électronique, une remise peut consister en une notification, un lien, une pièce jointe ou un rapport incorporé.</span><span class="sxs-lookup"><span data-stu-id="2378f-104">Depending on how you define the e-mail subscription, a delivery might consist of a notification, link, attachment, or embedded report.</span></span> <span data-ttu-id="2378f-105">L'extension de remise de courrier électronique fonctionne avec votre technologie de serveur de messagerie existante.</span><span class="sxs-lookup"><span data-stu-id="2378f-105">The e-mail delivery extension works with your existing mail server technology.</span></span> <span data-ttu-id="2378f-106">Le serveur de messagerie doit être un serveur SMTP ou redirecteur.</span><span class="sxs-lookup"><span data-stu-id="2378f-106">The mail server must be an SMTP server or forwarder.</span></span> <span data-ttu-id="2378f-107">Le serveur de rapports se connecte à un serveur SMTP par le biais de bibliothèques CDO (Collaboration Data Objects) (cdosys.dll) fournies par le système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="2378f-107">The report server connects to an SMTP server through Collaboration Data Objects (CDO) libraries (cdosys.dll) that are provided by the operating system.</span></span>  
  
 <span data-ttu-id="2378f-108">L'extension de remise du courrier électronique par le serveur de rapports n'est pas configurée par défaut.</span><span class="sxs-lookup"><span data-stu-id="2378f-108">The report server e-mail delivery extension is not configured by default.</span></span> <span data-ttu-id="2378f-109">Vous devez utiliser le Gestionnaire de configuration de Reporting Services pour effectuer une configuration minimale de l'extension.</span><span class="sxs-lookup"><span data-stu-id="2378f-109">You must use the Reporting Services Configuration Manager to minimally configure the extension.</span></span> <span data-ttu-id="2378f-110">Pour définir des propriétés avancées, vous devez modifier le fichier `RSReportServer.config` .</span><span class="sxs-lookup"><span data-stu-id="2378f-110">To set advanced properties, you must edit the `RSReportServer.config` file.</span></span> <span data-ttu-id="2378f-111">Si vous ne pouvez pas configurer le serveur de rapports afin qu'il utilise cette extension, vous pouvez remettre les rapports dans un dossier partagé à la place.</span><span class="sxs-lookup"><span data-stu-id="2378f-111">If you cannot configure the report server to use this extension, you can deliver reports to a shared folder instead.</span></span> <span data-ttu-id="2378f-112">Pour plus d'informations, consultez [File Share Delivery in Reporting Services](../../reporting-services/subscriptions/file-share-delivery-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="2378f-112">For more information, see [File Share Delivery in Reporting Services](../../reporting-services/subscriptions/file-share-delivery-in-reporting-services.md).</span></span>  
  
||  
|-|  
|[!INCLUDE[applies](../../includes/applies-md.md)]<span data-ttu-id="2378f-113">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Mode natif</span><span class="sxs-lookup"><span data-stu-id="2378f-113">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode</span></span>|  
  
 
  
##  <a name="configuration-requirements"></a><a name="bkmk_configuration_requirements"></a><span data-ttu-id="2378f-114">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="2378f-114">Configuration Requirements</span></span>  
  
-   <span data-ttu-id="2378f-115">La remise du courrier électronique par le serveur de rapports est implémentée sur des objets de données de collaboration (CDO) et nécessite un serveur SMTP (Simple Mail Transfer Protocol) local ou distant, ou encore un redirecteur SMTP.</span><span class="sxs-lookup"><span data-stu-id="2378f-115">Report server e-mail delivery is implemented on Collaboration Data Objects (CDO) and requires a local or remote Simple Mail Transfer Protocol (SMTP) server or SMTP forwarder.</span></span> <span data-ttu-id="2378f-116">Le protocole SMTP n'est pas pris en charge sur tous les systèmes d'exploitation Windows.</span><span class="sxs-lookup"><span data-stu-id="2378f-116">SMTP is not supported on all Windows operating systems.</span></span> <span data-ttu-id="2378f-117">Si vous utilisez l'édition Itanium de Windows Server 2008, le protocole SMTP n'est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="2378f-117">If you are using the Itanium-based edition of Windows Server 2008, SMTP is not supported.</span></span> <span data-ttu-id="2378f-118">Pour plus d'informations sur les options de configuration fournies par le biais des objets CDO, consultez [Configuration CoClass](https://go.microsoft.com/fwlink/?LinkId=98237) sur MSDN.</span><span class="sxs-lookup"><span data-stu-id="2378f-118">For more information about configuration options provided through CDO, see [Configuration CoClass](https://go.microsoft.com/fwlink/?LinkId=98237) on MSDN.</span></span>  
  
-   <span data-ttu-id="2378f-119">Le compte de service Report Server doit être autorisé à envoyer du courrier sur le serveur SMTP.</span><span class="sxs-lookup"><span data-stu-id="2378f-119">The Report Server service account must have permission on the SMTP server to send mail.</span></span>  
  
-   <span data-ttu-id="2378f-120">L'extension de remise du courrier électronique utilise l'encodage UTF-8 dans les pièces jointes électroniques.</span><span class="sxs-lookup"><span data-stu-id="2378f-120">The e-mail delivery extension uses UTF-8 encoding in e-mail attachments.</span></span> <span data-ttu-id="2378f-121">Vous ne pouvez pas modifier cet encodage ; l'extension de rendu HTML prend en charge UTF-8 uniquement.</span><span class="sxs-lookup"><span data-stu-id="2378f-121">You cannot modify the encoding; the HTML rendering extension only supports UTF-8.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2378f-122">L'extension par défaut de la remise du courrier électronique ne prend pas en charge la signature numérique et le chiffrement des messages sortants.</span><span class="sxs-lookup"><span data-stu-id="2378f-122">The default e-mail delivery extension does not provide support for digitally signing or encrypting outgoing mail messages.</span></span>  
  
 
  
##  <a name="configuring-a-report-server-for-local-or-remote-smtp-service"></a><a name="bkmk_configure_for_local_or_remote_SMTP"></a><span data-ttu-id="2378f-123">Configuration d’un serveur de rapports pour un service SMTP local ou distant</span><span class="sxs-lookup"><span data-stu-id="2378f-123">Configuring a Report Server for Local or Remote SMTP Service</span></span>  
 <span data-ttu-id="2378f-124">Vous pouvez utiliser un service SMTP local ou un serveur ou un redirecteur SMTP distant pour la prise en charge de la remise du courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="2378f-124">You can use a local SMTP service or a remote SMTP server or forwarder to support e-mail delivery.</span></span> <span data-ttu-id="2378f-125">Si vous pouvez accéder à un serveur SMTP existant à distance, pensez à l'utiliser.</span><span class="sxs-lookup"><span data-stu-id="2378f-125">If you have access to an existing remote SMTP server, you should consider using it.</span></span> <span data-ttu-id="2378f-126">Si aucun serveur SMTP n'est disponible ou si vous rencontrez par la suite des erreurs liées à la remise des rapports attribuables aux pannes de connexion de l'ordinateur, nous vous recommandons d'utiliser plutôt un service SMTP local.</span><span class="sxs-lookup"><span data-stu-id="2378f-126">If there is no SMTP server available or if you subsequently encounter report delivery errors that can be attributed to computer connection failures, you should switch to using a local SMTP service.</span></span> <span data-ttu-id="2378f-127">Cette rubrique couvre plus en détail le mode de configuration d'un serveur de rapports pour un service local ou distant.</span><span class="sxs-lookup"><span data-stu-id="2378f-127">Details about how to configure a report server for local or remote service are provided further on in this topic.</span></span>  
  
  
  
##  <a name="setting-configuration-options-for-e-mail-delivery"></a><a name="bkmk_setting_email_delivery"></a><span data-ttu-id="2378f-128">Définition des options de configuration pour la remise par messagerie</span><span class="sxs-lookup"><span data-stu-id="2378f-128">Setting Configuration Options for E-Mail Delivery</span></span>  
 <span data-ttu-id="2378f-129">Avant d'utiliser la remise du courrier électronique par le serveur de rapports, vous devez définir les valeurs de configuration fournissant des informations sur le mode d'utilisation du serveur SMTP.</span><span class="sxs-lookup"><span data-stu-id="2378f-129">Before you can use Report Server e-mail delivery, you must set configuration values that provide information about which SMTP server to use.</span></span>  
  
 <span data-ttu-id="2378f-130">Pour configurer un serveur de rapports pour la remise par messagerie, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="2378f-130">To configure a report server for e-mail delivery, do the following:</span></span>  
  
-   <span data-ttu-id="2378f-131">Utilisez le Gestionnaire de configuration de Reporting Services si vous spécifiez simplement un serveur SMTP et un compte d'utilisateur ayant l'autorisation d'envoyer des messages électroniques.</span><span class="sxs-lookup"><span data-stu-id="2378f-131">Use the Reporting Services Configuration Manager if you are specifying just an SMTP server and a user account that has permission to send e-mail.</span></span> <span data-ttu-id="2378f-132">Ce sont les paramètres minimum requis pour configurer l'extension de remise du courrier électronique par le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="2378f-132">These are the minimum settings that are required for configuring the Report Server e-mail delivery extension.</span></span> <span data-ttu-id="2378f-133">Pour plus d’informations, consultez [paramètres de messagerie électronique-Configuration Manager &#40;mode natif SSRS&#41;](../../reporting-services/install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager.md) et [remise par courrier électronique dans Reporting Services](../../reporting-services/subscriptions/e-mail-delivery-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="2378f-133">For more information, see [E-mail Settings - Configuration Manager &#40;SSRS Native Mode&#41;](../../reporting-services/install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager.md) and [E-Mail Delivery in Reporting Services](../../reporting-services/subscriptions/e-mail-delivery-in-reporting-services.md).</span></span>  
  
-   <span data-ttu-id="2378f-134">(Facultatif) Utilisez un éditeur de texte pour spécifier les paramètres supplémentaires dans le fichier RSreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="2378f-134">(Optionally) Use a text editor to specify additional settings in the RSreportserver.config file.</span></span> <span data-ttu-id="2378f-135">Ce fichier contient tous les paramètres de configuration pour la remise du courrier électronique par le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="2378f-135">This file contains all of the configuration settings for Report Server e-mail delivery.</span></span> <span data-ttu-id="2378f-136">La spécification de paramètres supplémentaires dans ces fichiers est obligatoire si vous utilisez un serveur SMTP local ou si vous limitez la remise par messagerie à des hôtes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="2378f-136">Specifying additional settings in these files is required if you are using a local SMTP server or if you are restricting e-mail delivery to specific hosts.</span></span> <span data-ttu-id="2378f-137">Pour plus d’informations sur la recherche et la modification des fichiers de configuration, consultez [modifier un fichier de configuration Reporting Services &#40;RSreportserver.config&#41;](../../reporting-services/report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md) dans documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2378f-137">For more information about finding and modifying configuration files, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](../../reporting-services/report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md) in SQL Server Books Online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2378f-138">Les paramètres du courrier électronique pour le serveur de rapports dépendent du CDO.</span><span class="sxs-lookup"><span data-stu-id="2378f-138">Report server e-mail settings are based on CDO.</span></span> <span data-ttu-id="2378f-139">Si vous souhaitez obtenir plus de détails sur des paramètres spécifiques, reportez-vous à la documentation de production CDO.</span><span class="sxs-lookup"><span data-stu-id="2378f-139">If you want more detail about specific settings, you can refer to the CDO production documentation.</span></span>  
  

  
##  <a name="example-report-server-e-mail-configuration"></a><a name="bkmk_example_config_file"></a><span data-ttu-id="2378f-140">Exemple de configuration de la messagerie du serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="2378f-140">Example Report Server E-Mail Configuration</span></span>  
 <span data-ttu-id="2378f-141">L'exemple suivant illustre les paramètres dans le fichier RSreportserver.config pour un serveur SMTP distant.</span><span class="sxs-lookup"><span data-stu-id="2378f-141">The following example illustrates the settings in the RSreportserver.config file for a remote SMTP server.</span></span> <span data-ttu-id="2378f-142">Pour plus d'dans la documentation en ligne deformations sur les descriptions et les valeurs valides de paramètres, consultez [RSReportServer Configuration File](../../reporting-services/report-server/rsreportserver-config-configuration-file.md) dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Onldans la documentation en ligne dee or the CDO product documentation.</span><span class="sxs-lookup"><span data-stu-id="2378f-142">To read about the setting descriptions and valid values, see [RSReportServer Configuration File](../../reporting-services/report-server/rsreportserver-config-configuration-file.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online or the CDO product documentation.</span></span>  
  
```  
<RSEmailDPConfiguration>  
     <SMTPServer>mySMTPServer.Adventure-Works.com</SMTPServer>  
     <SMTPServerPort></SMTPServerPort>  
     <SMTPAccountName></SMTPAccountName>  
     <SMTPConnectionTimeout></SMTPConnectionTimeout>  
     <SMTPServerPickupDirectory></SMTPServerPickupDirectory>  
     <SMTPUseSSL></SMTPUseSSL>  
     <SendUsing>2</SendUsing>  
     <SMTPAuthenticate></SMTPAuthenticate>  
     <From>my-rs-email-account@Adventure-Works.com</From>  
     <EmbeddedRenderFormats>  
          <RenderingExtension>MHTML</RenderingExtension>  
     </EmbeddedRenderFormats>  
     <PrivilegedUserRenderFormats></PrivilegedUserRenderFormats>  
     <ExcludedRenderFormats>  
          <RenderingExtension>HTMLOWC</RenderingExtension>  
          <RenderingExtension>NULL</RenderingExtension>  
     </ExcludedRenderFormats>  
     <SendEmailToUserAlias>True</SendEmailToUserAlias>  
     <DefaultHostName></DefaultHostName>  
     <PermittedHosts>  
          <HostName>Adventure-Works.com</HostName>  
          <HostName>hotmail.com</HostName>  
     </PermittedHosts>  
</RSEmailDPConfiguration>  
```  
  

  
##  <a name="configuration-options-for-setting-the-to-field-in-a-message"></a><a name="bkmk_setting_TO_field"></a><span data-ttu-id="2378f-143">Options de configuration pour la définition du champ à : dans un message</span><span class="sxs-lookup"><span data-stu-id="2378f-143">Configuration Options for Setting the To: Field in a Message</span></span>  
 <span data-ttu-id="2378f-144">Les abonnements définis par l’utilisateur qui sont créés en fonction des autorisations accordées par la tâche **gérer les abonnements individuels** contiennent un nom d’utilisateur prédéfini basé sur le compte d’utilisateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="2378f-144">User-defined subscriptions that are created according to the permissions granted by the **Manage individual subscriptions** task contain a pre-set user name that is based on the domain user account.</span></span> <span data-ttu-id="2378f-145">Quand l’utilisateur crée l’abonnement, le nom du destinataire dans le champ **À :** est configuré automatiquement à l’adresse de la personne qui crée l’abonnement, au moyen du compte d’utilisateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="2378f-145">When the user creates the subscription, the recipient name in the **To:** field is self-addressed using the domain user account of the person creating the subscription.</span></span>  
  
 <span data-ttu-id="2378f-146">Si vous utilisez un redirecteur ou un serveur SMTP qui utilise des comptes de messagerie différents du compte d'utilisateur de domaine, la remise des rapports échouera lorsque le serveur SMTP tentera de remettre le rapport à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2378f-146">If you are using an SMTP server or forwarder that uses e-mail accounts that are different from the domain user account, the report delivery will fail when the SMTP server tries to deliver the report to that user.</span></span>  
  
 <span data-ttu-id="2378f-147">Pour contourner ce problème, vous pouvez modifier les paramètres de configuration qui permettent aux utilisateurs d'entrer un nom dans le champ **À :** .</span><span class="sxs-lookup"><span data-stu-id="2378f-147">To workaround this issue, you can modify configuration settings that allow users to enter a name in the **To:** field:</span></span>  
  
1.  <span data-ttu-id="2378f-148">Ouvrez le fichier RSReportServer.config avec un éditeur de texte.</span><span class="sxs-lookup"><span data-stu-id="2378f-148">Open RSReportServer.config with a text editor.</span></span>  
  
2.  <span data-ttu-id="2378f-149">Définissez `SendEmailToUserAlias` sur `False`.</span><span class="sxs-lookup"><span data-stu-id="2378f-149">Set `SendEmailToUserAlias` to `False`.</span></span>  
  
3.  <span data-ttu-id="2378f-150">Définissez `DefaultHostName` au nom DNS (Domain Name System) ou à l'adresse IP du redirecteur ou du serveur SMTP.</span><span class="sxs-lookup"><span data-stu-id="2378f-150">Set `DefaultHostName` to the Domain Name System (DNS) name or IP address of the SMTP server or forwarder.</span></span>  
  
4.  <span data-ttu-id="2378f-151">Enregistrez le fichier .</span><span class="sxs-lookup"><span data-stu-id="2378f-151">Save the file.</span></span>  
  
  
  
##  <a name="configuration-options-for-remote-smtp-service"></a><a name="bkmk_options_remote_SMTP"></a><span data-ttu-id="2378f-152">Options de configuration pour le service SMTP distant</span><span class="sxs-lookup"><span data-stu-id="2378f-152">Configuration Options for Remote SMTP Service</span></span>  
 <span data-ttu-id="2378f-153">La connexion entre le serveur de rapports et le serveur ou redirecteur SMTP est déterminée par les paramètres de configuration suivants :</span><span class="sxs-lookup"><span data-stu-id="2378f-153">The connection between the report server and an SMTP server or forwarder is determined by the following configuration settings:</span></span>  
  
-   <span data-ttu-id="2378f-154">`SendUsing` spécifie une méthode pour l’envoi de messages.</span><span class="sxs-lookup"><span data-stu-id="2378f-154">`SendUsing` specifies a method for sending messages.</span></span> <span data-ttu-id="2378f-155">Vous pouvez choisir entre un service SMTP réseau ou un répertoire de collecte du service SMTP local.</span><span class="sxs-lookup"><span data-stu-id="2378f-155">You can choose between a network SMTP service or a local SMTP service pickup directory.</span></span> <span data-ttu-id="2378f-156">Pour utiliser un service SMTP distant, cette valeur doit être définie sur **2** dans le fichier RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="2378f-156">To use a remote SMTP service, this value must be set to **2** in the RSReportServer.config file.</span></span>  
  
-   <span data-ttu-id="2378f-157">`SMTPServer` spécifie le serveur ou le redirecteur SMTP distant.</span><span class="sxs-lookup"><span data-stu-id="2378f-157">`SMTPServer` specifies the remote SMTP server or forwarder.</span></span> <span data-ttu-id="2378f-158">Cette valeur est obligatoire si vous utilisez un serveur ou un redirecteur SMTP distant.</span><span class="sxs-lookup"><span data-stu-id="2378f-158">This value is a required value if you are using a remote SMTP server or forwarder.</span></span>  
  
-   <span data-ttu-id="2378f-159">`From`définit la valeur qui s’affiche dans la ligne de **:** d’un message électronique.</span><span class="sxs-lookup"><span data-stu-id="2378f-159">`From` sets the value that appears in the **From:** line of an e-mail message.</span></span> <span data-ttu-id="2378f-160">Cette valeur est obligatoire si vous utilisez un serveur ou un redirecteur SMTP distant.</span><span class="sxs-lookup"><span data-stu-id="2378f-160">This value is a required value if you are using a remote SMTP server or forwarder.</span></span>  
  
 <span data-ttu-id="2378f-161">D'autres valeurs utilisées pour le service SMTP distant comprennent ce qui suit (notez que vous n'avez pas besoin de les spécifier à moins de vouloir remplacer les valeurs par défaut).</span><span class="sxs-lookup"><span data-stu-id="2378f-161">Other values that are used for remote SMTP service include the following (note that you do not need to specify these values unless you want to override the default values).</span></span>  
  
-   <span data-ttu-id="2378f-162">**SMTPServerPort** est configuré pour le port 25.</span><span class="sxs-lookup"><span data-stu-id="2378f-162">**SMTPServerPort** is configured for port 25.</span></span>  
  
-   <span data-ttu-id="2378f-163">**SMTPAuthenticate** spécifie le mode de connexion du serveur de rapports au serveur SMTP distant.</span><span class="sxs-lookup"><span data-stu-id="2378f-163">**SMTPAuthenticate** specifies how the report server connects to the remote SMTP server.</span></span> <span data-ttu-id="2378f-164">La valeur par défaut est 0 (ou aucune authentification).</span><span class="sxs-lookup"><span data-stu-id="2378f-164">The default value is 0 (or no authentication).</span></span> <span data-ttu-id="2378f-165">Dans ce cas, la connexion est effectuée par un accès anonyme.</span><span class="sxs-lookup"><span data-stu-id="2378f-165">In this case, the connection is made through Anonymous access.</span></span> <span data-ttu-id="2378f-166">En fonction de la configuration de votre domaine, il est possible que le serveur de rapports et le serveur SMTP soient obligés d'être des membres du même domaine.</span><span class="sxs-lookup"><span data-stu-id="2378f-166">Depending on your domain configuration, the report server and the SMTP server may need to be members of the same domain.</span></span>  
  
     <span data-ttu-id="2378f-167">Pour envoyer du courrier électronique aux listes de distribution limitée (par exemple, les listes de distribution qui acceptent des messages entrants uniquement à partir de comptes authentifiés), définissez **SMTPAuthenticate** sur la valeur **2**.</span><span class="sxs-lookup"><span data-stu-id="2378f-167">To send e-mail to restricted distribution lists (for example, distribution lists that accept incoming messages only from authenticated accounts), set **SMTPAuthenticate** to **2**.</span></span>  
  

  
##  <a name="configuration-options-for-local-smtp-service"></a><a name="bkmk_options_local_SMTP"></a><span data-ttu-id="2378f-168">Options de configuration pour le service SMTP local</span><span class="sxs-lookup"><span data-stu-id="2378f-168">Configuration Options for Local SMTP Service</span></span>  
 <span data-ttu-id="2378f-169">La configuration d'un service SMTP local est pratique si vous testez ou dépannez la remise du courrier électronique par le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="2378f-169">Configuring a local SMTP service is useful if you are testing or troubleshooting report server e-mail delivery.</span></span> <span data-ttu-id="2378f-170">Par défaut, le service SMTP local n'est pas activé.</span><span class="sxs-lookup"><span data-stu-id="2378f-170">The local SMTP service is not enabled by default.</span></span> <span data-ttu-id="2378f-171">Pour obtenir des instructions sur la façon de l’activer, consultez [configurer un serveur de rapports pour la remise par messagerie (SSRS Configuration Manager)](../../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) et [paramètres de messagerie-Configuration Manager &#40;le Mode natif SSRS&#41;](../../reporting-services/install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2378f-171">For instructions on how to enable it, see [Configure a Report Server for E-Mail Delivery (SSRS Configuration Manager)](../../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) and [E-mail Settings - Configuration Manager &#40;SSRS Native Mode&#41;](../../reporting-services/install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager.md).</span></span>  
  
 <span data-ttu-id="2378f-172">La connexion entre le serveur de rapports et le serveur ou le redirecteur SMTP local est déterminée par les paramètres de configuration suivants :</span><span class="sxs-lookup"><span data-stu-id="2378f-172">The connection between the report server and a local SMTP server or forwarder is determined by the following configuration settings:</span></span>  
  
-   <span data-ttu-id="2378f-173">`SendUsing` est défini sur **1**.</span><span class="sxs-lookup"><span data-stu-id="2378f-173">`SendUsing` is set to **1**.</span></span>  
  
-   <span data-ttu-id="2378f-174">**SMTPServerPickupDirectory** est défini sur un dossier de lecteur local.</span><span class="sxs-lookup"><span data-stu-id="2378f-174">**SMTPServerPickupDirectory** is set to a folder on the local drive.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2378f-175">Veillez à ne pas définir `SMTPServer` si vous utilisez un serveur SMTP local.</span><span class="sxs-lookup"><span data-stu-id="2378f-175">Be sure that you do not set `SMTPServer` if you are using a local SMTP server.</span></span>  
  
-   <span data-ttu-id="2378f-176">`From`définit la valeur qui s’affiche dans la ligne de **:** d’un message électronique.</span><span class="sxs-lookup"><span data-stu-id="2378f-176">`From` sets the value that appears in the **From:** line of an e-mail message.</span></span> <span data-ttu-id="2378f-177">Cette valeur est requise.</span><span class="sxs-lookup"><span data-stu-id="2378f-177">This value is required.</span></span>  
  
 
  
##  <a name="to-configure-report-server-e-mail-using-the-reporting-services-configuration-manager"></a><a name="bkmk_use_configuration_manager"></a><span data-ttu-id="2378f-178">Pour configurer la messagerie électronique du serveur de rapports à l’aide de l’Gestionnaire de configuration de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="2378f-178">To configure report server e-mail using the Reporting Services Configuration Manager</span></span>  
  
1.  <span data-ttu-id="2378f-179">Vérifiez que le service Report Server Windows a des autorisations `Send As` sur le serveur SMTP.</span><span class="sxs-lookup"><span data-stu-id="2378f-179">Verify that the Report Server Windows service has `Send As` permissions on the SMTP server.</span></span>  
  
2.  <span data-ttu-id="2378f-180">Démarrez le Gestionnaire de configuration de Reporting Services, puis connectez-vous à l'instance du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="2378f-180">Start the Reporting Services Configuration Manager and connect to the report server instance.</span></span>  
  
3.  <span data-ttu-id="2378f-181">Sur la page Paramètres de messagerie, entrez le nom du serveur SMTP.</span><span class="sxs-lookup"><span data-stu-id="2378f-181">On the Email Settings page, enter the name of the SMTP server.</span></span> <span data-ttu-id="2378f-182">Il peut s'agir d'une adresse IP, du nom UNC d'un ordinateur sur l'intranet de votre entreprise ou d'un nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="2378f-182">This value can be an IP address, a UNC name of a computer on your corporate intranet, or a fully qualified domain name.</span></span>  
  
4.  <span data-ttu-id="2378f-183">Dans **Adresse de l'expéditeur**, tapez le nom d'un compte qui a l'autorisation d'envoyer des messages électroniques à partir du serveur SMTP.</span><span class="sxs-lookup"><span data-stu-id="2378f-183">In **Sender Address**, enter the name an account that has permission to send e-mail from the SMTP server.</span></span>  
  
5.  <span data-ttu-id="2378f-184">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="2378f-184">Click **Apply**.</span></span>  
  

  
##  <a name="to-configure-a-remote-smtp-service-for-the-report-server"></a><a name="bkmk_confiugre_remote_SMTP"></a><span data-ttu-id="2378f-185">Pour configurer un service SMTP distant pour le serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="2378f-185">To configure a remote SMTP Service for the report server</span></span>  
  
1.  <span data-ttu-id="2378f-186">Vérifiez que le service Report Server Windows a des autorisations `Send As` sur le serveur SMTP.</span><span class="sxs-lookup"><span data-stu-id="2378f-186">Verify that the Report Server Windows service has `Send As` permissions on the SMTP server.</span></span>  
  
2.  <span data-ttu-id="2378f-187">Ouvrez le fichier RSReportServer.config dans un éditeur de texte.</span><span class="sxs-lookup"><span data-stu-id="2378f-187">Open the RSReportServer.config file in a text editor.</span></span>  
  
3.  <span data-ttu-id="2378f-188">Vérifiez que <`UrlRoot`> est définie sur l’adresse URL du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="2378f-188">Verify that <`UrlRoot`> is set to the report server URL address.</span></span> <span data-ttu-id="2378f-189">Cette valeur est définie lorsque vous configurez le serveur de rapports et elle devrait normalement être déjà définie.</span><span class="sxs-lookup"><span data-stu-id="2378f-189">This value is set when you configure the report server and it should be filled in already.</span></span> <span data-ttu-id="2378f-190">Si elle n'est pas définie, tapez l'adresse URL du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="2378f-190">If it is not set, type the report server URL address.</span></span>  
  
4.  <span data-ttu-id="2378f-191">Dans la section remise, recherchez <`ReportServerEmail`>.</span><span class="sxs-lookup"><span data-stu-id="2378f-191">In the Delivery section, find <`ReportServerEmail`>.</span></span>  
  
5.  <span data-ttu-id="2378f-192">Dans <`SMTPServer`>, tapez le nom du serveur SMTP.</span><span class="sxs-lookup"><span data-stu-id="2378f-192">In <`SMTPServer`>, type the name of the SMTP server.</span></span> <span data-ttu-id="2378f-193">Il peut s'agir d'une adresse IP, du nom UNC d'un ordinateur sur l'intranet de votre entreprise ou d'un nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="2378f-193">This value can be an IP address, a UNC name of a computer on your corporate intranet, or a fully qualified domain name.</span></span>  
  
6.  <span data-ttu-id="2378f-194">Vérifiez que <`SendUsing`> a la valeur 2.</span><span class="sxs-lookup"><span data-stu-id="2378f-194">Verify that <`SendUsing`> is set to 2.</span></span> <span data-ttu-id="2378f-195">Si la valeur est différente, le serveur de rapports n'est pas configuré pour utiliser un service SMTP distant.</span><span class="sxs-lookup"><span data-stu-id="2378f-195">If it is set another value, the report server is not configured to use a remote SMTP service.</span></span>  
  
7.  <span data-ttu-id="2378f-196">Dans <`From`>, tapez le nom d’un compte qui a l’autorisation d’envoyer du courrier électronique à partir du serveur SMTP.</span><span class="sxs-lookup"><span data-stu-id="2378f-196">In <`From`>, type the name an account that has permission to send e-mail from the SMTP server.</span></span>  
  
8.  <span data-ttu-id="2378f-197">Enregistrez le fichier .</span><span class="sxs-lookup"><span data-stu-id="2378f-197">Save the file.</span></span>  
  
     <span data-ttu-id="2378f-198">Le serveur de rapports utilise automatiquement les nouveaux paramètres ; il n'est pas nécessaire de redémarrer le service.</span><span class="sxs-lookup"><span data-stu-id="2378f-198">The report server will use the new settings automatically; you do not need to restart the service.</span></span> <span data-ttu-id="2378f-199">Vous pouvez spécifier des paramètres SMTP supplémentaires pour configurer comment le serveur SMTP est utilisé pour la remise par messagerie du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="2378f-199">You can specify additional SMTP settings to further configure how the SMTP server is used for report server e-mail delivery.</span></span> <span data-ttu-id="2378f-200">Pour plus d'dans la documentation en ligne deformations, consultez [Configurdans la documentation en ligne deg a Report Server for E-Mail Delivery](../../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) et [RSReportServer Configuration File](../../reporting-services/report-server/rsreportserver-config-configuration-file.md) dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Onldans la documentation en ligne dee.</span><span class="sxs-lookup"><span data-stu-id="2378f-200">For more information, see [Configuring a Report Server for E-Mail Delivery](../../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) and [RSReportServer Configuration File](../../reporting-services/report-server/rsreportserver-config-configuration-file.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  

  
##  <a name="to-configure-a-local-smtp-service-for-the-report-server"></a><a name="bkmk_confiugre_local_SMTP"></a><span data-ttu-id="2378f-201">Pour configurer un service SMTP local pour le serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="2378f-201">To configure a local SMTP Service for the report server</span></span>  
  
1.  <span data-ttu-id="2378f-202">Dans le Panneau de configuration, cliquez sur **Ajout/Suppression de programmes**.</span><span class="sxs-lookup"><span data-stu-id="2378f-202">In Control Panel, click **Add or Remove Programs**.</span></span>  
  
2.  <span data-ttu-id="2378f-203">Cliquez sur **Ajouter/Supprimer des composants Windows** pour démarrer l'Assistant Composants Windows.</span><span class="sxs-lookup"><span data-stu-id="2378f-203">Click **Add/Remove Windows Components** to start the Windows Component Wizard.</span></span>  
  
3.  <span data-ttu-id="2378f-204">Sélectionnez **Serveur d'applications** et cliquez sur **Détails**.</span><span class="sxs-lookup"><span data-stu-id="2378f-204">Select **Application Server** and click **Details**.</span></span>  
  
4.  <span data-ttu-id="2378f-205">Sélectionnez **Services Internet (IIS)** , puis cliquez sur **Détails**.</span><span class="sxs-lookup"><span data-stu-id="2378f-205">Select **Internet Information Services (IIS)** and click **Details**.</span></span>  
  
5.  <span data-ttu-id="2378f-206">Activez la case à cocher **Service SMTP** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2378f-206">Select the **SMTP Service** checkbox and click **OK**.</span></span>  
  
6.  <span data-ttu-id="2378f-207">Dans l'Assistant Composants Windows, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="2378f-207">On the Windows Component Wizard, click **Next**.</span></span> <span data-ttu-id="2378f-208">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="2378f-208">Click **Finish**.</span></span>  
  
7.  <span data-ttu-id="2378f-209">Vérifiez que le service s'exécute dans la console **Services** .</span><span class="sxs-lookup"><span data-stu-id="2378f-209">Verify that the service is running in the **Services** console.</span></span>  
  
8.  <span data-ttu-id="2378f-210">Ouvrez le fichier **RSReportServer.config** dans un éditeur de texte.</span><span class="sxs-lookup"><span data-stu-id="2378f-210">Open the **RSReportServer.config** file in a text editor.</span></span>  
  
9. <span data-ttu-id="2378f-211">Vérifiez que `<UrlRoot>` est paramétré à l'adresse URL du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="2378f-211">Verify that `<UrlRoot>` is set to the report server URL address.</span></span> <span data-ttu-id="2378f-212">Cette valeur est définie lorsque vous configurez le serveur de rapports et elle devrait normalement être déjà définie.</span><span class="sxs-lookup"><span data-stu-id="2378f-212">This value is set when you configure the report server and it should be filled in already.</span></span> <span data-ttu-id="2378f-213">Si elle n'est pas définie, tapez l'adresse URL du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="2378f-213">If it is not set, type the report server URL address.</span></span>  
  
10. <span data-ttu-id="2378f-214">Dans la section Remise, recherchez `<ReportServerEmail>.`.</span><span class="sxs-lookup"><span data-stu-id="2378f-214">In the Delivery section, find `<ReportServerEmail>.`</span></span>  
  
11. <span data-ttu-id="2378f-215">Dans `<SMTPServer>`, effacez les valeurs pour ce paramètre, mais ne supprimez pas les balises.</span><span class="sxs-lookup"><span data-stu-id="2378f-215">In `<SMTPServer>`, clear any values for this setting, but do not delete the tags.</span></span>  
  
12. <span data-ttu-id="2378f-216">Affectez à `<SendUsing>` la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="2378f-216">Set `<SendUsing>` to 1.</span></span> <span data-ttu-id="2378f-217">Si la valeur est différente, le serveur de rapports n'est pas configuré pour utiliser un service SMTP local.</span><span class="sxs-lookup"><span data-stu-id="2378f-217">If it is set another value, the report server is not configured to use a local SMTP service.</span></span>  
  
13. <span data-ttu-id="2378f-218">Définissez `<SMTPServerPickupDirectory>` sur un dossier de lecteur local.</span><span class="sxs-lookup"><span data-stu-id="2378f-218">Set `<SMTPServerPickupDirectory>` to a folder on the local drive.</span></span>  
  
14. <span data-ttu-id="2378f-219">Définissez `<From>` sur un compte qui a l'autorisation d'envoyer des messages électroniques à partir du serveur SMTP.</span><span class="sxs-lookup"><span data-stu-id="2378f-219">Set `<From>` to an account that has permission to send e-mail from the SMTP server.</span></span>  
  
15. <span data-ttu-id="2378f-220">Enregistrez le fichier .</span><span class="sxs-lookup"><span data-stu-id="2378f-220">Save the file.</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="2378f-221">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2378f-221">See Also</span></span>  
 [<span data-ttu-id="2378f-222">Gestionnaire de configuration de Reporting Services &#40;mode natif&#41;</span><span class="sxs-lookup"><span data-stu-id="2378f-222">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md)  
  
  
