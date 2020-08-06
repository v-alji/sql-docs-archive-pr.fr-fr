---
title: Configurer la messagerie électronique pour une application de service Reporting Services (SharePoint 2010 et SharePoint 2013) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 38fc34a6-aae7-4dde-9ad2-f1eee0c42a9f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 628122289f8a9d83a307d70a369ab51f8f571c04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611586"
---
# <a name="configure-e-mail-for-a-reporting-services-service-application-sharepoint-2010-and-sharepoint-2013"></a><span data-ttu-id="3b564-102">Configurer la messagerie électronique pour une application de service Reporting Services (SharePoint 2010 et SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="3b564-102">Configure E-mail for a Reporting Services Service Application (SharePoint 2010 and SharePoint 2013)</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="3b564-103">L’alerte de données Reporting Services envoie des messages électroniques d’alerte.</span><span class="sxs-lookup"><span data-stu-id="3b564-103">data alerting sends alerts in e-mail messages.</span></span> <span data-ttu-id="3b564-104">Pour envoyer du courrier électronique, vous devrez peut-être configurer votre application de service [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] et modifier l'extension de remise par messagerie pour l'application de service.</span><span class="sxs-lookup"><span data-stu-id="3b564-104">To send e-mail you may need to configure your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application and you may need to modify the e-mail delivery extension for the service application.</span></span> <span data-ttu-id="3b564-105">Les paramètres de messagerie sont également requis si vous prévoyez d'utiliser l'extension de remise par messagerie pour la fonctionnalité d'abonnement de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3b564-105">The e-mail settings are also required if you plan to use the e-mail delivery extension for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] subscription feature.</span></span>  
  
||  
|-|  
|[!INCLUDE[applies](../../includes/applies-md.md)]<span data-ttu-id="3b564-106">Le [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] mode sharepoint &#124; sharepoint 2010 et sharepoint 2013.</span><span class="sxs-lookup"><span data-stu-id="3b564-106">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode &#124; SharePoint 2010 and SharePoint 2013.</span></span>|  
  
### <a name="to-configure-e-mail-for-the-shared-service"></a><span data-ttu-id="3b564-107">Pour configurer la messagerie pour le service partagé</span><span class="sxs-lookup"><span data-stu-id="3b564-107">To configure e-mail for the shared service</span></span>  
  
1.  <span data-ttu-id="3b564-108">Dans l'Administration centrale de SharePoint, cliquez sur **Gestion des applications**.</span><span class="sxs-lookup"><span data-stu-id="3b564-108">In SharePoint Central Administration, click the **Application Management**.</span></span>  
  
2.  <span data-ttu-id="3b564-109">Dans le groupe **Applications de service** , cliquez sur **Gérer les applications de service**.</span><span class="sxs-lookup"><span data-stu-id="3b564-109">In the **Service Applications** group, click **Manage service applications**.</span></span>  
  
3.  <span data-ttu-id="3b564-110">Dans la liste **Nom** , cliquez sur le nom de votre application de service [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3b564-110">In the **Name** list, click the name of your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span>  
  
4.  <span data-ttu-id="3b564-111">Cliquez sur **Paramètres de messagerie** dans la page **Gérer l’application Reporting Services** .</span><span class="sxs-lookup"><span data-stu-id="3b564-111">Click **E-mail Settings** on the **Manage Reporting Services Application** page.</span></span>  
  
5.  <span data-ttu-id="3b564-112">Sélectionnez **Utiliser le serveur SMTP**.</span><span class="sxs-lookup"><span data-stu-id="3b564-112">Select **Use SMTP server**.</span></span>  
  
6.  <span data-ttu-id="3b564-113">Dans la zone **Serveur SMTP sortant** , tapez le nom d'un serveur SMTP.</span><span class="sxs-lookup"><span data-stu-id="3b564-113">In the **Outbound SMTP server** box, type the name of an SMTP server.</span></span>  
  
7.  <span data-ttu-id="3b564-114">Dans la zone **Adresse de provenance** , tapez une adresse de messagerie.</span><span class="sxs-lookup"><span data-stu-id="3b564-114">In the **From address** box, type an e-mail address.</span></span>  
  
     <span data-ttu-id="3b564-115">Cette adresse est l'expéditeur de tous les messages électroniques d'alerte.</span><span class="sxs-lookup"><span data-stu-id="3b564-115">This address is the sender of all alert e-mail messages.</span></span>  
  
     <span data-ttu-id="3b564-116">Le compte de l'utilisateur spécifié dans **Adresse de provenance** doit être un compte géré que vous avez spécifié lors de la configuration du pool d'applications pour l'application de service [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3b564-116">The account of the user specified in **From address** must be a managed account that you specified when you configured the application pool for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="3b564-117">Si vous en avez l'autorisation, vous pouvez afficher une liste des comptes gérés existants dans la page Comptes de service dans l'Administration centrale de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3b564-117">If you have permission, you can view a list of existing managed accounts on the Service Accounts page in SharePoint Central Administration.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="ntlm-authentication"></a><span data-ttu-id="3b564-118">Authentification NTLM</span><span class="sxs-lookup"><span data-stu-id="3b564-118">NTLM Authentication</span></span>  
  
1.  <span data-ttu-id="3b564-119">Si votre environnement de messagerie requiert l'authentification NTLM et n'autorise pas l'accès anonyme, vous devez modifier la configuration d'extension de remise par messagerie de vos applications de service [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3b564-119">If your email environment requires NTLM authentication and does not allow anonymous access, you need to modify the e-mail delivery extension configuration for your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service applications.</span></span> <span data-ttu-id="3b564-120">Modifiez **SMTPAuthenticate** pour utiliser la valeur « 2 ».</span><span class="sxs-lookup"><span data-stu-id="3b564-120">Change the **SMTPAuthenticate** to use a value of "2".</span></span> <span data-ttu-id="3b564-121">Cette valeur ne peut pas être modifiée à partir de l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3b564-121">This value cannot be changed from the user interface.</span></span> <span data-ttu-id="3b564-122">L’exemple de script PowerShell suivant met à jour la configuration complète pour l’extension de remise par messagerie du serveur de rapports pour l’application de service nommée « SSRS_TESTAPPLICATION ».</span><span class="sxs-lookup"><span data-stu-id="3b564-122">The following PowerShell script example, updates the full configuration for the report server e-mail delivery extension for the service application named "SSRS_TESTAPPLICATION".</span></span> <span data-ttu-id="3b564-123">Notez que certains nœuds répertoriés dans le script peuvent aussi être définis à partir de l’interface utilisateur, par exemple l’adresse « De ».</span><span class="sxs-lookup"><span data-stu-id="3b564-123">Note some of the nodes listed in the script can also be set from the user interface, for example the "From" address.</span></span>  
  
    ```powershell
    $app = Get-SPRSServiceApplication | Where {$_.name -like "SSRS_TESTAPPLICATION *"}  
    $emailCfg = Get-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml
    $emailXml = [xml]$emailCfg
    $emailXml.SelectSingleNode("//SMTPServer").InnerText = "your email server name"  
    $emailXml.SelectSingleNode("//SendUsing").InnerText = "2"  
    $emailXml.SelectSingleNode("//SMTPAuthenticate").InnerText = "2"  
    $emailXml.SelectSingleNode("//From").InnerText = "your FROM email address"  
    Set-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" -ExtensionConfiguration $emailXml.OuterXml  
    ```  
  
2.  <span data-ttu-id="3b564-124">Si vous devez vérifier le nom de votre application de service, exécutez l’applet de commande **SPRSServiceApplication** .</span><span class="sxs-lookup"><span data-stu-id="3b564-124">If you need to verify the name of your service application, run the **Get-SPRSServiceApplication** cmdlet.</span></span>  
  
    ```powershell
    Get-SPRSServiceApplication  
    ```  
  
3.  <span data-ttu-id="3b564-125">L’exemple suivant retourne les valeurs actuelles de l’extension de messagerie pour l’application de service nommée « SSRS_TESTAPPLICATION ».</span><span class="sxs-lookup"><span data-stu-id="3b564-125">The following example will return the current values of the e-mail extension for the service application named "SSRS_TESTAPPLICATION".</span></span>  
  
    ```powershell
    $app = get-sprsserviceapplication | Where {$_.name -like "SSRSTEST_APPLICATION*"}  
    Get-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml  
    ```  
  
4.  <span data-ttu-id="3b564-126">L’exemple suivant crée un fichier nommé « emailconfig.txt » avec les valeurs actuelles de l’extension de messagerie pour l’application de service nommée « SSRS_TESTAPPLICATION ».</span><span class="sxs-lookup"><span data-stu-id="3b564-126">The following example will create a new file named "emailconfig.txt" with the current values of the e-mail extension for the service application named "SSRS_TESTAPPLICATION"</span></span>  
  
    ```powershell
    $app = Get-SPRSServiceApplication | Where {$_.name -like "SSRS_TESTAPPLICATION*"}  
    Get-SPRSExtension -identity $app -ExtensionType "Delivery" -name "Report Server Email" | Select -ExpandProperty ConfigurationXml | Out-File c:\emailconfig.txt  
    ```
