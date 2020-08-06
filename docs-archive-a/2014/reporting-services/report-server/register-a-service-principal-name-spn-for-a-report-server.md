---
title: Enregistrer un nom de principal du service (SPN) pour un serveur de rapports | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: dda91d4f-77cc-4898-ad03-810ece5f8e74
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 502170f16aad66757e8f44419ccbac3017072449
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614386"
---
# <a name="register-a-service-principal-name-spn-for-a-report-server"></a><span data-ttu-id="cb8f7-102">Inscrire un nom de principal du service (SPN) pour un serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="cb8f7-102">Register a Service Principal Name (SPN) for a Report Server</span></span>
  <span data-ttu-id="cb8f7-103">Si vous déployez [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] dans un réseau qui utilise le protocole Kerberos pour l'authentification mutuelle, vous devez créer un nom de principal du service (SPN) pour le service Report Server, si vous le configurez pour s'exécuter en tant que compte d'utilisateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-103">If you are deploying [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in a network that uses the Kerberos protocol for mutual authentication, you must create a Service Principal Name (SPN) for the Report Server service if you configure it to run as a domain user account.</span></span>  
  
## <a name="about-spns"></a><span data-ttu-id="cb8f7-104">À propos des noms principaux de service</span><span class="sxs-lookup"><span data-stu-id="cb8f7-104">About SPNs</span></span>  
 <span data-ttu-id="cb8f7-105">Un nom principal de service est un identificateur unique pour un service sur un réseau qui utilise l'authentification Kerberos.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-105">An SPN is a unique identifier for a service on a network that uses Kerberos authentication.</span></span> <span data-ttu-id="cb8f7-106">Il est composé d'une classe de service, d'un nom d'hôte et d'un port.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-106">It consists of a service class, a host name, and a port.</span></span> <span data-ttu-id="cb8f7-107">Sur un réseau qui utilise l'authentification Kerberos, un nom principal de service pour le serveur doit être inscrit sous un compte d'ordinateur prédéfini (tel que NetworkService ou LocalSystem) ou un compte d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-107">On a network that uses Kerberos authentication, an SPN for the server must be registered under either a built-in computer account (such as NetworkService or LocalSystem) or user account.</span></span> <span data-ttu-id="cb8f7-108">Les noms principaux de service sont enregistrés automatiquement pour les comptes intégrés.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-108">SPNs are registered for built-in accounts automatically.</span></span> <span data-ttu-id="cb8f7-109">Toutefois, lorsque vous exécutez un service sous un compte d'utilisateur de domaine, vous devez inscrire manuellement le nom principal de service pour le compte que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-109">However, when you run a service under a domain user account, you must manually register the SPN for the account you want to use.</span></span>  
  
 <span data-ttu-id="cb8f7-110">Pour créer un SPN, vous pouvez utiliser l’utilitaire de ligne de commande **SetSPN** .</span><span class="sxs-lookup"><span data-stu-id="cb8f7-110">To create an SPN, you can use the **SetSPN** command line utility.</span></span> <span data-ttu-id="cb8f7-111">Pour plus d’informations, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="cb8f7-111">For more information, see the following:</span></span>  
  
-   <span data-ttu-id="cb8f7-112">[Setspn](https://technet.microsoft.com/library/cc731241\(WS.10\).aspx) ( https://technet.microsoft.com/library/cc731241(WS.10).aspx) .</span><span class="sxs-lookup"><span data-stu-id="cb8f7-112">[Setspn](https://technet.microsoft.com/library/cc731241\(WS.10\).aspx) (https://technet.microsoft.com/library/cc731241(WS.10).aspx).</span></span>  
  
-   <span data-ttu-id="cb8f7-113">[Nom de principal du service (SPN), syntaxe setspn (Setspn.exe)](https://social.technet.microsoft.com/wiki/contents/articles/717.service-principal-names-spns-setspn-syntax-setspn-exe.aspx) ( https://social.technet.microsoft.com/wiki/contents/articles/717.service-principal-names-spns-setspn-syntax-setspn-exe.aspx) .</span><span class="sxs-lookup"><span data-stu-id="cb8f7-113">[Service Principal Names (SPNs) SetSPN Syntax (Setspn.exe)](https://social.technet.microsoft.com/wiki/contents/articles/717.service-principal-names-spns-setspn-syntax-setspn-exe.aspx) (https://social.technet.microsoft.com/wiki/contents/articles/717.service-principal-names-spns-setspn-syntax-setspn-exe.aspx).</span></span>  
  
 <span data-ttu-id="cb8f7-114">Vous devez être administrateur de domaine pour exécuter l'utilitaire sur le contrôleur de domaine.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-114">You must be a domain administrator to run the utility on the domain controller.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb8f7-115">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="cb8f7-115">Syntax</span></span>  
 <span data-ttu-id="cb8f7-116">La syntaxe de commande pour utiliser l'utilitaire SetSPN en vue de créer un SPN pour le serveur de rapports ressemble à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="cb8f7-116">The command syntax for using SetSPN utility to create an SPN for the report server resembles the following:</span></span>  
  
```  
Setspn -s http/<computername>.<domainname>:<port> <domain-user-account>  
```  
  
 <span data-ttu-id="cb8f7-117">**SetSPN** est disponible dans Windows Server.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-117">**SetSPN** is available with Windows Server.</span></span> <span data-ttu-id="cb8f7-118">L'argument `-s` ajoute un SPN après avoir vérifié qu'aucun doublon n'existe.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-118">The `-s` argument adds a SPN after validating no duplicate exists.</span></span> <span data-ttu-id="cb8f7-119">**REMARQUE** -s est disponible dans Windows Server depuis Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-119">**NOTE:-s** is available in Windows Server starting with Windows Server 2008.</span></span>  
  
 <span data-ttu-id="cb8f7-120">`HTTP` est la classe de service.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-120">`HTTP` is the service class.</span></span> <span data-ttu-id="cb8f7-121">Le service Web Report Server s'exécute dans HTTP.SYS.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-121">The Report Server Web service runs in HTTP.SYS.</span></span> <span data-ttu-id="cb8f7-122">L'une des conséquences de la création d'un nom principal de service pour HTTP est que des tickets seront accordés à toutes les applications Web sur le même ordinateur qui s'exécutent dans HTTP.SYS (y compris les applications hébergées dans les services Internet (IIS)) en fonction du compte d'utilisateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-122">A by-product of creating an SPN for HTTP is that all Web applications on the same computer that run in HTTP.SYS (including applications hosted in IIS) will be granted tickets based on the domain user account.</span></span> <span data-ttu-id="cb8f7-123">Si ces services s'exécutent sous un compte différent, les demandes d'authentification échouent.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-123">If those services run under a different account, the authentication requests will fail.</span></span> <span data-ttu-id="cb8f7-124">Pour éviter ce problème, assurez-vous de configurer toutes les applications HTTP pour qu'elles s'exécutent sous le même compte ou envisagez la création d'en-têtes d'hôtes pour chaque application puis la création de noms principaux de service distincts pour chaque en-tête d'hôte.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-124">To avoid this problem, be sure to configure all HTTP applications to run under the same account, or consider creating host headers for each application and then creating separate SPNs for each host header.</span></span> <span data-ttu-id="cb8f7-125">Lorsque vous configurez des en-tête de l'hôte, les modifications de DNS sont requises indépendamment de la configuration [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cb8f7-125">When you configure host headers, DNS changes are required regardless of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] configuration.</span></span>  
  
 <span data-ttu-id="cb8f7-126">Les valeurs que vous spécifiez pour \<*computername*> , \<*domainname*> et \<*port*> identifient l’adresse réseau unique de l’ordinateur qui héberge le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-126">The values that you specify for \<*computername*>, \<*domainname*>, and \<*port*> identify the unique network address of the computer that hosts the report server.</span></span> <span data-ttu-id="cb8f7-127">Ce peut être un nom d'hôte local ou un nom de domaine complet (FQDN).</span><span class="sxs-lookup"><span data-stu-id="cb8f7-127">This can be a local host name or a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="cb8f7-128">Si vous n’avez qu’un seul domaine et que vous utilisez le port 80, vous pouvez omettre \<*domainname*> et \<*port*> à partir de votre ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-128">If you only have one domain and are using port 80, you can omit \<*domainname*> and \<*port*> from your command line.</span></span> <span data-ttu-id="cb8f7-129">\<*domain-user-account*>compte d’utilisateur sous lequel le service Report Server s’exécute et pour lequel le SPN doit être inscrit.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-129">\<*domain-user-account*> is the user account under which the Report Server service runs and for which the SPN must be registered.</span></span>  
  
## <a name="register-an-spn-for-domain-user-account"></a><span data-ttu-id="cb8f7-130">Inscrire un SPN pour un compte d'utilisateur de domaine</span><span class="sxs-lookup"><span data-stu-id="cb8f7-130">Register an SPN for Domain User Account</span></span>  
  
#### <a name="to-register-an-spn-for-a-report-server-service-running-as-a-domain-user"></a><span data-ttu-id="cb8f7-131">Pour inscrire un SPN pour un service Report Server qui s'exécute en tant qu'utilisateur de domaine</span><span class="sxs-lookup"><span data-stu-id="cb8f7-131">To register an SPN for a Report Server service running as a domain user</span></span>  
  
1.  <span data-ttu-id="cb8f7-132">Installez [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] et configurez le service Report Server pour qu’il s’exécute en tant que compte d’utilisateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-132">Install [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and configure the Report Server service to run as a domain user account.</span></span> <span data-ttu-id="cb8f7-133">Notez que les utilisateurs ne seront pas en mesure de se connecter au serveur de rapports tant que vous n'aurez pas terminé les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-133">Note that users will not be able to connect to the report server until you complete the following steps.</span></span>  
  
2.  <span data-ttu-id="cb8f7-134">Ouvrez une session sur le contrôleur de domaine en tant qu'administrateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-134">Log on to the domain controller as domain administrator.</span></span>  
  
3.  <span data-ttu-id="cb8f7-135">Ouvrez une fenêtre d’invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-135">Open a Command Prompt window.</span></span>  
  
4.  <span data-ttu-id="cb8f7-136">Copiez la commande suivante, en remplaçant les valeurs d'espaces réservés par des valeurs réelles valides pour votre réseau :</span><span class="sxs-lookup"><span data-stu-id="cb8f7-136">Copy the following command, replacing placeholder values with actual values that are valid for your network:</span></span>  
  
    ```  
    Setspn -s http/<computer-name>.<domain-name>:<port> <domain-user-account>  
    ```  
  
     <span data-ttu-id="cb8f7-137">Par exemple : `Setspn -s http/MyReportServer.MyDomain.com:80 MyDomainUser`</span><span class="sxs-lookup"><span data-stu-id="cb8f7-137">For example: `Setspn -s http/MyReportServer.MyDomain.com:80 MyDomainUser`</span></span>  
  
5.  <span data-ttu-id="cb8f7-138">Exécutez la commande.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-138">Run the command.</span></span>  
  
6.  <span data-ttu-id="cb8f7-139">Ouvrez le fichier **RsReportServer.config** et recherchez la section `<AuthenticationTypes>` .</span><span class="sxs-lookup"><span data-stu-id="cb8f7-139">Open the **RsReportServer.config** file and locate the `<AuthenticationTypes>` section.</span></span>  
  
7.  <span data-ttu-id="cb8f7-140">Ajoutez `<RSWindowsNegotiate/>` comme première entrée de cette section pour activer NTLM.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-140">Add `<RSWindowsNegotiate/>` as the first entry in this section to enable NTLM.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb8f7-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cb8f7-141">See Also</span></span>  
 <span data-ttu-id="cb8f7-142">[Configurer un compte de service &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="cb8f7-142">[Configure a Service Account &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-service-account-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="cb8f7-143">[Configurer le compte de service Report Server &#40;Gestionnaire de configuration de SSRS&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="cb8f7-143">[Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span></span>  
 [<span data-ttu-id="cb8f7-144">Gérer un serveur de rapports Reporting Services en mode natif</span><span class="sxs-lookup"><span data-stu-id="cb8f7-144">Manage a Reporting Services Native Mode Report Server</span></span>](manage-a-reporting-services-native-mode-report-server.md)  
  
  
