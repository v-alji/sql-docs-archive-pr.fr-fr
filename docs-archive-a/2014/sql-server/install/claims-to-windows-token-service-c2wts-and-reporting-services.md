---
title: Service d’jetons Revendications vers Windows (C2WTS) et Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/25/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- c2wts.exe.config
- SharePoint mode
- C2WTS
- WSS_WPG
ms.assetid: 4d380509-deed-4b4b-a9c1-a9134cc40641
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: cf2e245dfae17556bdb906c134ba0d53898a8631
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604959"
---
# <a name="claims-to-windows-token-service-c2wts-and-reporting-services"></a><span data-ttu-id="a6a95-102">Service d'émission de jetons Revendications vers Windows (C2WTS) et Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a6a95-102">Claims to Windows Token Service (C2WTS) and Reporting Services</span></span>
  <span data-ttu-id="a6a95-103">Le service d’jetons Revendications vers Windows SharePoint (c2WTS) est requis avec le [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] mode SharePoint si vous souhaitez utiliser l’authentification Windows pour les sources de données qui se trouvent en dehors de la batterie de serveurs SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a6a95-103">The SharePoint Claims to Windows Token Service (c2WTS) is required with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode if you want to use windows authentication for Data Sources that are outside the SharePoint farm.</span></span> <span data-ttu-id="a6a95-104">Ceci s'applique même si les utilisateurs accèdent aux sources de données à l'aide de l'authentification Windows, car la communication entre le serveur Web frontal (WFE) et le service partagé [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] se fera toujours via l'authentification basée sur les revendications.</span><span class="sxs-lookup"><span data-stu-id="a6a95-104">This is true even if the user accesses the data sources with Windows Authentication because the communication between the web front-end (WFE) and the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] shared service will always be Claims authentication.</span></span>  
  
 <span data-ttu-id="a6a95-105">C2WTS est nécessaire même si votre ou vos sources de données résident sur le même ordinateur que le service partagé.</span><span class="sxs-lookup"><span data-stu-id="a6a95-105">c2WTS is needed even if your data source(s) are on the same computer as the shared service.</span></span> <span data-ttu-id="a6a95-106">Toutefois dans ce scénario, la délégation contrainte n'est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="a6a95-106">However in this scenario, constrained delegation is not needed.</span></span>  
  
 <span data-ttu-id="a6a95-107">Les jetons créés par C2WTS ne fonctionnent qu’avec la délégation contrainte (pour certains services uniquement) et l’option de configuration « avec n’importe quel protocole d’authentification ».</span><span class="sxs-lookup"><span data-stu-id="a6a95-107">The tokens created by c2WTS will only work with constrained delegation (constrains to specific services) and the configuration option "using any authentication protocol".</span></span> <span data-ttu-id="a6a95-108">Comme indiqué précédemment, si vos sources de données sont sur le même ordinateur que le service partagé, la délégation contrainte n'est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="a6a95-108">As noted earlier, if your data sources are on the same computer as the shared service, then constrained delegation is not needed.</span></span>  
  
 <span data-ttu-id="a6a95-109">Si votre environnement utilise la délégation contrainte Kerberos, le service SharePoint server et les sources de données externes doivent résider dans le même domaine Windows.</span><span class="sxs-lookup"><span data-stu-id="a6a95-109">If your environment will use Kerberos constrained delegation, then the SharePoint Server service and external data sources need to reside in the same Windows domain.</span></span> <span data-ttu-id="a6a95-110">Tout service qui s’appuie sur le service d’émission de jetons Revendications vers Windows (C2WTS) doit utiliser la délégation **contrainte** Kerberos pour permettre à C2WTS d’utiliser une transition de protocole Kerberos dans la conversion de revendications en informations d’identification Windows.</span><span class="sxs-lookup"><span data-stu-id="a6a95-110">Any service that relies on the Claims to Windows token service (c2WTS) must use Kerberos **constrained** delegation to allow c2WTS to use Kerberos protocol transition to translate claims into Windows credentials.</span></span> <span data-ttu-id="a6a95-111">Ces exigences s'appliquent à tous les services partagés SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a6a95-111">These requirements are true for all SharePoint Shared Services.</span></span> <span data-ttu-id="a6a95-112">Pour plus d’informations, consultez [vue d’ensemble de l’authentification Kerberos pour les https://technet.microsoft.com/library/gg502594.aspx) produits Microsoft SharePoint 2010 (](https://technet.microsoft.com/library/gg502594.aspx).</span><span class="sxs-lookup"><span data-stu-id="a6a95-112">For more information, see [Overview of Kerberos authentication for Microsoft SharePoint 2010 Products  (https://technet.microsoft.com/library/gg502594.aspx)](https://technet.microsoft.com/library/gg502594.aspx).</span></span>  
  
 <span data-ttu-id="a6a95-113">La procédure est résumée dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="a6a95-113">The procedure is summarized in this topic.</span></span>  
  
||  
|-|  
|<span data-ttu-id="a6a95-114">**[!INCLUDE[applies](../../includes/applies-md.md)]** SharePoint 2013 &#124; SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="a6a95-114">**[!INCLUDE[applies](../../includes/applies-md.md)]**  SharePoint 2013 &#124; SharePoint 2010</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="a6a95-115">Prérequis</span><span class="sxs-lookup"><span data-stu-id="a6a95-115">Prerequisites</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a6a95-116">Remarque : certaines étapes de configuration peuvent changer, ou peuvent ne pas fonctionner dans certaines topologies de batteries de serveurs.</span><span class="sxs-lookup"><span data-stu-id="a6a95-116">Note: Some of the configuration steps may change, or may not work in certain farm topologies.</span></span> <span data-ttu-id="a6a95-117">Par exemple, l’installation d’un serveur ne prend pas en charge les services C2WTS Windows Identity Foundation. C’est pourquoi les scénarios de délégation de jetons Windows ne sont pas possibles avec cette configuration de batterie de serveurs.</span><span class="sxs-lookup"><span data-stu-id="a6a95-117">For instance, a single server install does not support the Windows Identity Foundation c2WTS services so claims to windows token delegation scenarios are not possible with this farm configuration.</span></span>  
  
### <a name="basic-steps-needed-to-configure-c2wts"></a><span data-ttu-id="a6a95-118">Étapes de base nécessaires pour configurer C2WTS</span><span class="sxs-lookup"><span data-stu-id="a6a95-118">Basic steps needed to configure c2WTS</span></span>  
  
1.  <span data-ttu-id="a6a95-119">Configurez le compte de service C2WTS.</span><span class="sxs-lookup"><span data-stu-id="a6a95-119">Configure the c2WTS service account.</span></span> <span data-ttu-id="a6a95-120">Ajoutez le compte de service au groupe Administrateurs local sur chaque serveur d’applications exécutant C2WTS.</span><span class="sxs-lookup"><span data-stu-id="a6a95-120">Add the service account to the local Administrators group on each application server running c2WTS.</span></span> <span data-ttu-id="a6a95-121">De plus, vérifiez que le compte possède les droits de stratégie de sécurité locale suivants :</span><span class="sxs-lookup"><span data-stu-id="a6a95-121">In addition, verify that the account has the following local security policy rights:</span></span>  
  
    -   <span data-ttu-id="a6a95-122">Agir en tant que partie du système d'exploitation</span><span class="sxs-lookup"><span data-stu-id="a6a95-122">Act as part of the operating system</span></span>  
  
    -   <span data-ttu-id="a6a95-123">Emprunter l'identité d'un client après authentification</span><span class="sxs-lookup"><span data-stu-id="a6a95-123">Impersonate a client after authentication</span></span>  
  
    -   <span data-ttu-id="a6a95-124">Ouvrir une session en tant que service</span><span class="sxs-lookup"><span data-stu-id="a6a95-124">Log on as a service</span></span>  
  
     <span data-ttu-id="a6a95-125">Le compte que vous utilisez pour c2WTS doit également être configuré pour la délégation restreinte avec la transition de protocole et nécessite des autorisations pour déléguer aux services avec lesquels il doit communiquer (c.-à-d. SQL Server Engine, SQL Server Analysis Services). Pour configurer la délégation, vous pouvez utiliser le composant logiciel enfichable utilisateurs et ordinateurs Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a6a95-125">The account you use for c2WTS also needs to be configured for Constrained Delegation with Protocol Transitioning and needs permissions to delegate to the Services it is required to communicate with (i.e. SQL Server Engine, SQL Server Analysis Services).To configure delegation you can use the Active Directory Users and Computer snap-in.</span></span>  
  
    1.  <span data-ttu-id="a6a95-126">Cliquez avec le bouton droit sur chaque compte de service et ouvrez la boîte de dialogue des propriétés.</span><span class="sxs-lookup"><span data-stu-id="a6a95-126">Right-click each service account and open the properties dialog.</span></span> <span data-ttu-id="a6a95-127">Dans la boîte de dialogue, cliquez sur l'onglet **Délégation** .</span><span class="sxs-lookup"><span data-stu-id="a6a95-127">In the dialog click the **Delegation** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="a6a95-128">Remarque : l'onglet Délégation est visible uniquement si l'objet a un SPN qui lui est affecté.</span><span class="sxs-lookup"><span data-stu-id="a6a95-128">Note: the delegation tab is only visible if the object has an SPN assigned to it.</span></span> <span data-ttu-id="a6a95-129">c2WTS ne nécessite pas de SPN sur le compte c2WTS, mais sans SPN, l’onglet **délégation** ne sera pas visible.</span><span class="sxs-lookup"><span data-stu-id="a6a95-129">c2WTS does not require an SPN on the c2WTS Account, however, without an SPN, the **Delegation** tab will not be visible.</span></span> <span data-ttu-id="a6a95-130">Une autre façon de configurer la délégation contrainte consiste à utiliser un utilitaire tel que **ADSIEdit**.</span><span class="sxs-lookup"><span data-stu-id="a6a95-130">An alternative way to configure constrained delegation is to use a utility such as **ADSIEdit**.</span></span>  
  
    2.  <span data-ttu-id="a6a95-131">Les options de configuration principales dans l'onglet Délégation sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="a6a95-131">Key configuration options on the delegation tab are the following:</span></span>  
  
        -   <span data-ttu-id="a6a95-132">Sélectionnez « n’approuver cet utilisateur que pour la délégation aux services spécifiés »</span><span class="sxs-lookup"><span data-stu-id="a6a95-132">Select "Trust this user for delegation to specified services only"</span></span>  
  
        -   <span data-ttu-id="a6a95-133">Sélectionnez « utiliser n’importe quel protocole d’authentification »</span><span class="sxs-lookup"><span data-stu-id="a6a95-133">Select "Use any authentication protocol"</span></span>  
  
         <span data-ttu-id="a6a95-134">Pour plus d’informations, consultez la section « configurer la délégation Kerberos autorisée pour les ordinateurs et les comptes de service » dans le livre blanc suivant : configuration de l' [authentification Kerberos pour les produits SharePoint 2010 et SQL Server 2008 R2](https://docs.microsoft.com/archive/blogs/tothesharepoint/white-paper-configuring-kerberos-authentication-for-sharepoint-2010-and-sql-server-2008-r2-products)</span><span class="sxs-lookup"><span data-stu-id="a6a95-134">For more information, see the "configure Kerberos constrained delegation for computers and service accounts" section of the following white paper, [Configuring Kerberos authentication for SharePoint 2010 and SQL Server 2008 R2 products](https://docs.microsoft.com/archive/blogs/tothesharepoint/white-paper-configuring-kerberos-authentication-for-sharepoint-2010-and-sql-server-2008-r2-products)</span></span>  
  
2.  <span data-ttu-id="a6a95-135">Configurer c2WTS « AllowedCallers »</span><span class="sxs-lookup"><span data-stu-id="a6a95-135">Configure c2WTS 'AllowedCallers'</span></span>  
  
     <span data-ttu-id="a6a95-136">c2WTS requiert que les identités des appelants soient explicitement listées dans le fichier de configuration, **c2wtshost.exe.config**. c2WTS n’accepte pas les demandes de tous les utilisateurs authentifiés dans le système, sauf s’il est configuré pour ce faire.</span><span class="sxs-lookup"><span data-stu-id="a6a95-136">c2WTS requires the 'callers' identities explicitly listed in the configuration file, **c2wtshost.exe.config**. c2WTS does not accept requests from all authenticated users in the system unless it is configured to do so.</span></span> <span data-ttu-id="a6a95-137">Dans ce cas, l’appelant est le groupe Windows WSS_WPG.</span><span class="sxs-lookup"><span data-stu-id="a6a95-137">In this case the 'caller' is the WSS_WPG Windows group.</span></span> <span data-ttu-id="a6a95-138">Le fichier c2wtshost.exe.confi est enregistré à l'emplacement suivant :</span><span class="sxs-lookup"><span data-stu-id="a6a95-138">The c2wtshost.exe.confi file is saved in the following location:</span></span>  
  
     <span data-ttu-id="a6a95-139">**\Program Files\Windows Identity Foundation\v3.5\c2wtshost.exe.config**</span><span class="sxs-lookup"><span data-stu-id="a6a95-139">**\Program Files\Windows Identity Foundation\v3.5\c2wtshost.exe.config**</span></span>  
  
     <span data-ttu-id="a6a95-140">L'exemple suivant montre le fichier de configuration :</span><span class="sxs-lookup"><span data-stu-id="a6a95-140">The following is an example of the configuration file:</span></span>  
  
    ```  
    <configuration>  
      <windowsTokenService>  
        <!--  
            By default no callers are allowed to use the Windows Identity Foundation Claims To NT Token Service.  
            Add the identities you wish to allow below.  
          -->  
        <allowedCallers>  
          <clear/>  
          <add value="WSS_WPG" />  
        </allowedCallers>  
      </windowsTokenService>  
    </configuration>  
    ```  
  
3.  <span data-ttu-id="a6a95-141">Démarrez le service C2WTS du système d’exploitation :</span><span class="sxs-lookup"><span data-stu-id="a6a95-141">Start the operating system c2WTS service:</span></span>  
  
    1.  <span data-ttu-id="a6a95-142">Configurez le service pour utiliser le compte de service que vous avez configuré à l'étape précédente.</span><span class="sxs-lookup"><span data-stu-id="a6a95-142">Configure the service to use the service account you configured in the previous step.</span></span>  
  
    2.  <span data-ttu-id="a6a95-143">Définissez le type de démarrage sur**automatique**et démarrez le service.</span><span class="sxs-lookup"><span data-stu-id="a6a95-143">Change the Startup type to "**Automatic**" and start the service.</span></span>  
  
4.  <span data-ttu-id="a6a95-144">Démarrez le service d’jetons Revendications vers Windows SharePoint : démarrez le service d’jetons Revendications vers Windows via l’administration centrale de SharePoint sur la page **gérer les services sur le serveur** .</span><span class="sxs-lookup"><span data-stu-id="a6a95-144">Start the SharePoint 'Claims to Windows Token Service': Start the Claims to Windows Token Service through SharePoint Central Administration on the **Manage Services on Server** page.</span></span> <span data-ttu-id="a6a95-145">Le service doit être démarré sur le serveur qui effectuera l'action.</span><span class="sxs-lookup"><span data-stu-id="a6a95-145">The service should be started on the server that will be performing the action.</span></span> <span data-ttu-id="a6a95-146">Par exemple si vous avez un serveur Web frontal et un serveur d’applications exécutant le service partagé [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , il vous suffit de démarrer C2WTS sur le serveur d’applications.</span><span class="sxs-lookup"><span data-stu-id="a6a95-146">For example if you have a server that is a WFE and another server that is an Application Server that has the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] shared service running, you only need to start c2WTS on the Application Server.</span></span> <span data-ttu-id="a6a95-147">C2WTS n’est pas nécessaire sur le serveur Web frontal.</span><span class="sxs-lookup"><span data-stu-id="a6a95-147">c2WTS is not needed on the WFE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6a95-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a6a95-148">See Also</span></span>  
 <span data-ttu-id="a6a95-149">[Vue d’ensemble du service d’jetons Revendications vers Windows (c2WTS) (https://msdn.microsoft.com/library/ee517278.aspx)](https://msdn.microsoft.com/library/ee517278.aspx) </span><span class="sxs-lookup"><span data-stu-id="a6a95-149">[Claims to Windows Token Service (c2WTS) Overview (https://msdn.microsoft.com/library/ee517278.aspx)](https://msdn.microsoft.com/library/ee517278.aspx) </span></span>  
 [<span data-ttu-id="a6a95-150">Vue d’ensemble de l’authentification Kerberos pour les produits Microsoft SharePoint 2010 (https://technet.microsoft.com/library/gg502594.aspx)</span><span class="sxs-lookup"><span data-stu-id="a6a95-150">Overview of Kerberos authentication for Microsoft SharePoint 2010 Products (https://technet.microsoft.com/library/gg502594.aspx)</span></span>](https://technet.microsoft.com/library/gg502594.aspx)  
  
