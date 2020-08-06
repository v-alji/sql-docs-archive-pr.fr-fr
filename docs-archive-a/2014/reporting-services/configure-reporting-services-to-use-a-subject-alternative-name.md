---
title: Configurer Reporting Services pour utiliser un autre nom de l’objet | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ce458f9f-4b4f-4a58-aa75-9a90dda1e622
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0312d2d1fff8f854eb2ffb8d0dad2563212ee23b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707268"
---
# <a name="configure-reporting-services-to-use-a-subject-alternative-name"></a><span data-ttu-id="bd319-102">Configurer Reporting Services pour utiliser un autre nom de l'objet</span><span class="sxs-lookup"><span data-stu-id="bd319-102">Configure Reporting Services to Use a Subject Alternative Name</span></span>
  <span data-ttu-id="bd319-103">Cette rubrique explique comment configurer [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] (SSRS) pour utiliser un autre nom de l’objet (SAN, Subject Alternative Name) en modifiant le fichier rsreportserver.config et en utilisant l’outil Netsh.exe.</span><span class="sxs-lookup"><span data-stu-id="bd319-103">This topic explains how to configure [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] (SSRS) to use a subject alternative name (SAN) by modifying the rsreportserver.config file and using the Netsh.exe tool.</span></span>

||
|-|
|<span data-ttu-id="bd319-104">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] en mode natif</span><span class="sxs-lookup"><span data-stu-id="bd319-104">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Native mode</span></span>|

 <span data-ttu-id="bd319-105">Les instructions s'appliquent à l'URL Reporting Services, ainsi qu'à une URL de service web.</span><span class="sxs-lookup"><span data-stu-id="bd319-105">The instructions apply to the Reporting Service URL as well as a Web Service URL.</span></span>

 <span data-ttu-id="bd319-106">Pour utiliser un nom SAN, le certificat SSL doit être inscrit sur le serveur, être signé et posséder la clé privée.</span><span class="sxs-lookup"><span data-stu-id="bd319-106">To use a SAN, the SSL certificate must be registered on the server, signed, and have the private key.</span></span> <span data-ttu-id="bd319-107">Vous ne pouvez pas utiliser un certificat auto-signé.</span><span class="sxs-lookup"><span data-stu-id="bd319-107">You cannot use a self-signed certificate</span></span>

 <span data-ttu-id="bd319-108">Vous pouvez configurer les URL dans [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] pour utiliser un certificat SSL.</span><span class="sxs-lookup"><span data-stu-id="bd319-108">URLs in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] can be configured to use an SSL certificate.</span></span> <span data-ttu-id="bd319-109">Normalement, un certificat a juste un nom d'objet qui n'autorise qu'une seule URL pour une session SSL (Secure Sockets Layer).</span><span class="sxs-lookup"><span data-stu-id="bd319-109">A certificate normally has just a subject name, which allows only one URL for an SSL (Secure Sockets Layer) session.</span></span> <span data-ttu-id="bd319-110">Le nom SAN est un champ supplémentaire dans le certificat qui permet à un service SSL d'être à l'écoute et d'être valide pour plusieurs URL. Il permet également au service SSL de partager le port SSL avec d'autres applications.</span><span class="sxs-lookup"><span data-stu-id="bd319-110">The SAN is an additional field in the certificate that allows an SSL service to listen and be valid for many URLs, and to share the SSL port with other applications.</span></span> <span data-ttu-id="bd319-111">Le nom du SAN ressemble à ceci : www.s2.com.</span><span class="sxs-lookup"><span data-stu-id="bd319-111">The SAN looks something like the following: www.s2.com.</span></span>

 <span data-ttu-id="bd319-112">Pour plus d’informations sur l’activation de SSL pour [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], consultez [Configurer des connexions SSL sur un serveur de rapports en mode natif](security/configure-ssl-connections-on-a-native-mode-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="bd319-112">For more information about SSL settings for [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], see [Configure SSL Connections on a Native Mode Report Server](security/configure-ssl-connections-on-a-native-mode-report-server.md).</span></span>

### <a name="configure-ssrs-to-use-a-subject-alternative-name-for-web-service-url"></a><span data-ttu-id="bd319-113">Configurer SSRS pour utiliser un autre nom de l'objet pour l'URL d'un service web</span><span class="sxs-lookup"><span data-stu-id="bd319-113">Configure SSRS to use a subject alternative name for Web Service URL</span></span>

1.  <span data-ttu-id="bd319-114">Démarrez le Gestionnaire de configuration de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="bd319-114">Start Reporting Services Configuration Manager.</span></span>

     <span data-ttu-id="bd319-115">Pour plus d’informations, consultez [Gestionnaire de configuration de Reporting Services &#40;mode natif&#41;](../sql-server/install/reporting-services-configuration-manager-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="bd319-115">For more information, see [Reporting Services Configuration Manager &#40;Native Mode&#41;](../sql-server/install/reporting-services-configuration-manager-native-mode.md).</span></span>

2.  <span data-ttu-id="bd319-116">Dans la page **URL du service web** , sélectionnez un port SSL et un certificat SSL.</span><span class="sxs-lookup"><span data-stu-id="bd319-116">On the **Web Service URL** page, select an SSL port and SSL Certificate.</span></span>

     <span data-ttu-id="bd319-117">![Gestionnaire de configuration de Reporting Services](media/reportingservices-configurationmanager.png "Gestionnaire de configuration de Reporting Services")</span><span class="sxs-lookup"><span data-stu-id="bd319-117">![Reporting Services Configuration Manager](media/reportingservices-configurationmanager.png "Reporting Services Configuration Manager")</span></span>

     <span data-ttu-id="bd319-118">Le gestionnaire de configuration inscrit le certificat SSL pour le port.</span><span class="sxs-lookup"><span data-stu-id="bd319-118">The configuration manager registers the SSL certificate for the port.</span></span>

3.  <span data-ttu-id="bd319-119">Ouvrez le fichier rsreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="bd319-119">Open the rsreportserver.config file.</span></span>

     <span data-ttu-id="bd319-120">Pour SSRS en mode natif, le fichier se trouve par défaut dans le dossier suivant.</span><span class="sxs-lookup"><span data-stu-id="bd319-120">For SSRS Native mode, the file is located by default in the following folder.</span></span>

    ```
    \Program Files\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer
    ```

4.  <span data-ttu-id="bd319-121">Copiez la section URL de l'application du service web Report Server.</span><span class="sxs-lookup"><span data-stu-id="bd319-121">Copy the URL section for the Report Server Web Service application.</span></span>

     <span data-ttu-id="bd319-122">Par exemple, voici la section URL d'origine.</span><span class="sxs-lookup"><span data-stu-id="bd319-122">For example, the following is the original URL section.</span></span>

    ```
        <URL>
         <UrlString>https://localhost:443</UrlString>
         <AccountSid>S-1-5-20</AccountSid>
         <AccountName>NT Authority\NetworkService</AccountName>
        </URL>

    ```

     <span data-ttu-id="bd319-123">Ce qui suit est la section URL, une fois changée.</span><span class="sxs-lookup"><span data-stu-id="bd319-123">The following is the modified URL section.</span></span>

    ```
    <URL>
         <UrlString>https://www.s1.com:443</UrlString>
         <AccountSid>S-1-5-20</AccountSid>
         <AccountName>NT Authority\NetworkService</AccountName>
        </URL>
        <URL>
         <UrlString>https://www.s2.com:443</UrlString>
         <AccountSid>S-1-5-20</AccountSid>
         <AccountName>NT Authority\NetworkService</AccountName>
        </URL>

    ```

5.  <span data-ttu-id="bd319-124">Enregistrez le fichier rsreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="bd319-124">Save the rsreportserver.config file.</span></span>

6.  <span data-ttu-id="bd319-125">Démarrez une invite de commandes en tant qu'administrateur, puis exécutez l'outil Netsh.exe.</span><span class="sxs-lookup"><span data-stu-id="bd319-125">Start a command prompt as an administrator, and run the Netsh.exe tool.</span></span>

    ```
    C:\windows\system32\netsh
    ```

7.  <span data-ttu-id="bd319-126">Passez au contexte http en tapant ce qui suit.</span><span class="sxs-lookup"><span data-stu-id="bd319-126">Switch to the http context by typing the following.</span></span>

    ```
    Netsh>http
    ```

8.  <span data-ttu-id="bd319-127">Affichez les urlacl existantes en tapant ce qui suit.</span><span class="sxs-lookup"><span data-stu-id="bd319-127">Show the existing urlacls by typing the following.</span></span>

    ```
    Netsh http>show urlacl
    ```

     <span data-ttu-id="bd319-128">Une entrée semblable à ce qui suit s'affiche.</span><span class="sxs-lookup"><span data-stu-id="bd319-128">An entry such as the following appears.</span></span>

    ```
    Reserved URL            : https:// www.s1.com:443/ReportServer/
        User: NT SERVICE\ReportServer
            Listen: Yes
            Delegate: No
            SDDL: D:(A;;GX;;;S-1-5-80-1234567890-123456789-123456789-123456789-1234567890)
    ```

     <span data-ttu-id="bd319-129">Une urlacl est une liste de contrôle d'accès discrétionnaire (DACL, Discretionary Access Control List) pour une URL réservée.</span><span class="sxs-lookup"><span data-stu-id="bd319-129">An urlacl is a DACL (Discretionary Access Control List) for a reserved URL.</span></span>

9. <span data-ttu-id="bd319-130">Créez une entrée pour l'autre nom de l'objet, avec le même utilisateur et la même chaîne SDDL que l'entrée existante, en tapant ce qui suit.</span><span class="sxs-lookup"><span data-stu-id="bd319-130">Create a new entry for the subject alternative name, with the same user and SDDL as the existing entry, by typing the following.</span></span>

    ```
    netsh http>add urlacl  url=https://www.s2.com:443/ReportServer  
    user="NT Service\ReportServer" sddl=D:(A;;GX;;;S-1-5-80-1234567980-12346579-123456789-123456789-1234567890)

    ```

10. <span data-ttu-id="bd319-131">Dans la page **État de Report Server** du Gestionnaire de configuration de Reporting Services, cliquez sur **Arrêter** , puis sur **Démarrer** pour redémarrer le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="bd319-131">On the **Report Server Status** page of the Reporting Services Configuration Manager, Click **Stop** and then click **Start** to restart the report server.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd319-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bd319-132">See Also</span></span>
 <span data-ttu-id="bd319-133">[Fichier de configuration RSReportServer](report-server/rsreportserver-config-configuration-file.md) [Gestionnaire de configuration de Reporting Services &#40;mode natif&#41;](../sql-server/install/reporting-services-configuration-manager-native-mode.md) [modifier un fichier de configuration Reporting Services &#40;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md) RSreportserver.config&#41;[configurer les url du serveur de rapports &#40;SSRS Configuration Manager&#41;](install-windows/configure-report-server-urls-ssrs-configuration-manager.md)</span><span class="sxs-lookup"><span data-stu-id="bd319-133">[RSReportServer Configuration File](report-server/rsreportserver-config-configuration-file.md) [Reporting Services Configuration Manager &#40;Native Mode&#41;](../sql-server/install/reporting-services-configuration-manager-native-mode.md) [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md) [Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;](install-windows/configure-report-server-urls-ssrs-configuration-manager.md)</span></span>


