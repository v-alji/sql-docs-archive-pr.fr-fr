---
title: Configurer l’authentification personnalisée ou par formulaire sur le serveur de rapports| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Forms authentication, configuring
- custom authentication [Reporting Services]
ms.assetid: e8601a8f-e66d-4649-8e4d-a46ca20ec7d0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1447e1e695f0e59dbc07b7e19f4df335a1220a97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602715"
---
# <a name="configure-custom-or-forms-authentication-on-the-report-server"></a><span data-ttu-id="6467d-102">Configurer l'authentification personnalisée ou par formulaire sur le serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="6467d-102">Configure Custom or Forms Authentication on the Report Server</span></span>
  <span data-ttu-id="6467d-103">Reporting Services fournit une architecture extensible vous permettant d’incorporer des modules d'authentification personnalisés ou par formulaires.</span><span class="sxs-lookup"><span data-stu-id="6467d-103">Reporting Services provides an extensible architecture that allows you to plug in custom or forms-based authentication modules.</span></span> <span data-ttu-id="6467d-104">Vous pouvez envisager d'implémenter une extension d'authentification personnalisée si les spécifications de déploiement n'incluent pas la sécurité intégrée de Windows ou l’authentification de base.</span><span class="sxs-lookup"><span data-stu-id="6467d-104">You might consider implementing a custom authentication extension if deployment requirements do not include Windows integrated security or Basic authentication.</span></span> <span data-ttu-id="6467d-105">Le scénario d’utilisation de l'authentification personnalisée le plus courant est la prise en charge d’un accès Internet ou extranet à une application Web.</span><span class="sxs-lookup"><span data-stu-id="6467d-105">The most common scenario for using custom authentication is to support Internet or extranet access to a Web application.</span></span> <span data-ttu-id="6467d-106">Le remplacement de l’extension d’authentification Windows par défaut par une extension d'authentification personnalisée vous permet de mieux contrôler l'habilitation des utilisateurs externes à accéder au serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="6467d-106">Replacing the default Windows Authentication extension with a custom authentication extension gives you more control over how external users are granted access to the report server.</span></span>  
  
 <span data-ttu-id="6467d-107">En pratique, le déploiement d'une extension d'authentification personnalisée requiert plusieurs étapes, notamment la copie des assemblys et des fichiers d'application, la modification des fichiers de configuration et le test du système.</span><span class="sxs-lookup"><span data-stu-id="6467d-107">In practice, deploying a custom authentication extension requires multiple steps that include copying assemblies and application files, modifying configuration files, and testing.</span></span> <span data-ttu-id="6467d-108">Cette rubrique traite uniquement des paramètres d'authentification spécifiés dans les fichiers de configuration.</span><span class="sxs-lookup"><span data-stu-id="6467d-108">This topic focuses on just the authentication settings that you specify in the configuration files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6467d-109">La création d’une extension d’authentification personnalisée nécessite du code personnalisé et des compétences en matière de sécurité [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6467d-109">Creating a custom authentication extension requires custom code and expertise in [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] security.</span></span> <span data-ttu-id="6467d-110">Si vous ne souhaitez pas créer de code pour une extension d'authentification personnalisée, vous pouvez utiliser des comptes et des groupes [!INCLUDE[msCoName](../../includes/msconame-md.md)] Active Directory, mais vous devez réduire grandement l'étendue d'un déploiement de serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="6467d-110">If you do not want to create a custom authentication extension, you can use [!INCLUDE[msCoName](../../includes/msconame-md.md)] Active Directory groups and accounts, but you should greatly reduce the scope of a report server deployment.</span></span> <span data-ttu-id="6467d-111">Pour plus d’informations sur l’authentification personnalisée, consultez [Implémentation d’une extension de sécurité](../extensions/security-extension/implementing-a-security-extension.md).</span><span class="sxs-lookup"><span data-stu-id="6467d-111">For more information about custom authentication, see [Implementing a Security Extension](../extensions/security-extension/implementing-a-security-extension.md).</span></span>  
  
 <span data-ttu-id="6467d-112">En outre, si vous souhaitez utiliser une authentification par formulaires ou une extension d'authentification personnalisée dans un environnement [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] intégré à un produit SharePoint, vous devez configurer le site SharePoint pour qu'il utilise la méthode d'authentification que vous choisissez.</span><span class="sxs-lookup"><span data-stu-id="6467d-112">Additionally, if you want to use Forms authentication or a custom authentication extension in a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] environment that is integrated with a SharePoint product, you must configure the SharePoint site to use the authentication method that you choose.</span></span> <span data-ttu-id="6467d-113">Pour plus d’informations sur la configuration de l’authentification dans SharePoint, consultez [Exemples d’authentification](https://go.microsoft.com/fwlink/?LinkId=115575) sur [!INCLUDE[msCoName](../../includes/msconame-md.md)] Developer Network (MSDN).</span><span class="sxs-lookup"><span data-stu-id="6467d-113">For more information about configuring authentication in SharePoint, see [Authentication Samples](https://go.microsoft.com/fwlink/?LinkId=115575) on [!INCLUDE[msCoName](../../includes/msconame-md.md)] Developer Network (MSDN).</span></span>  
  
### <a name="to-configure-a-report-server-to-use-custom-authentication"></a><span data-ttu-id="6467d-114">Pour configurer un serveur de rapports pour utiliser l'authentification personnalisée</span><span class="sxs-lookup"><span data-stu-id="6467d-114">To configure a report server to use Custom authentication</span></span>  
  
1.  <span data-ttu-id="6467d-115">Ouvrez RSReportServer.config dans un éditeur de texte.</span><span class="sxs-lookup"><span data-stu-id="6467d-115">Open RSReportServer.config in a text editor.</span></span>  
  
2.  <span data-ttu-id="6467d-116">Recherchez <`Authentication`>.</span><span class="sxs-lookup"><span data-stu-id="6467d-116">Find <`Authentication`>.</span></span>  
  
3.  <span data-ttu-id="6467d-117">Copiez la structure XML suivante :</span><span class="sxs-lookup"><span data-stu-id="6467d-117">Copy the following XML structure:</span></span>  
  
    ```  
    <Authentication>  
          <AuthenticationTypes>  
                 <Custom />  
          </AuthenticationTypes>  
          <EnableAuthPersistence>true</EnableAuthPersistence>  
    </Authentication>  
    ```  
  
4.  <span data-ttu-id="6467d-118">Collez-la sur les entrées existantes pour <`Authentication`>.</span><span class="sxs-lookup"><span data-stu-id="6467d-118">Paste it over the existing entries for <`Authentication`>.</span></span>  
  
     <span data-ttu-id="6467d-119">Notez que vous ne pouvez pas utiliser `Custom` avec d'autres types d'authentification.</span><span class="sxs-lookup"><span data-stu-id="6467d-119">Note that you cannot use `Custom` with other authentication types.</span></span>  
  
5.  <span data-ttu-id="6467d-120">Enregistrez le fichier .</span><span class="sxs-lookup"><span data-stu-id="6467d-120">Save the file.</span></span>  
  
6.  <span data-ttu-id="6467d-121">Ouvrez le fichier Web.config du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="6467d-121">Open the Web.config file for the report server.</span></span> <span data-ttu-id="6467d-122">Par défaut, celui-ci se trouve dans le dossier \Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\ReportServer.</span><span class="sxs-lookup"><span data-stu-id="6467d-122">By default, it is located at \Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\ReportServer.</span></span>  
  
7.  <span data-ttu-id="6467d-123">Recherchez `authentication mode` et affectez lui la valeur `Forms`.</span><span class="sxs-lookup"><span data-stu-id="6467d-123">Find `authentication mode` and set it `Forms`.</span></span>  
  
    ```  
    <authentication mode = "Forms" />  
    ```  
  
8.  <span data-ttu-id="6467d-124">Recherchez `identity impersonate` et affectez-lui la valeur `False`.</span><span class="sxs-lookup"><span data-stu-id="6467d-124">Find `identity impersonate` and set it to `False`.</span></span>  
  
    ```  
    <identity impersonate = "false" />  
    ```  
  
9. <span data-ttu-id="6467d-125">Ouvrez le fichier Web.config du Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="6467d-125">Open the Web.config file for Report Manager.</span></span> <span data-ttu-id="6467d-126">Par défaut, celui-ci se trouve dans le dossier \Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\ReportManager.</span><span class="sxs-lookup"><span data-stu-id="6467d-126">By default, it is located at \Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\ReportManager.</span></span>  
  
10. <span data-ttu-id="6467d-127">Recherchez `authentication mode` et affectez lui la valeur `Forms`.</span><span class="sxs-lookup"><span data-stu-id="6467d-127">Find `authentication mode` and set it `Forms`.</span></span>  
  
    ```  
    <authentication mode = "Forms" />  
    ```  
  
11. <span data-ttu-id="6467d-128">Recherchez `identity impersonate` et affectez-lui la valeur `False`.</span><span class="sxs-lookup"><span data-stu-id="6467d-128">Find `identity impersonate` and set it to `False`.</span></span>  
  
    ```  
    <identity impersonate = "false" />  
    ```  
  
12. <span data-ttu-id="6467d-129">Ajouter la structure d’éléments `PassThroughCookies` au fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="6467d-129">Add the `PassThroughCookies` element structure to the configuration file.</span></span> <span data-ttu-id="6467d-130">Pour plus d’informations, consultez [Configurer le Gestionnaire de rapports pour passer des cookies d’authentification personnalisée](configure-the-web-portal-to-pass-custom-authentication-cookies.md).</span><span class="sxs-lookup"><span data-stu-id="6467d-130">For more information, see [Configure Report Manager to Pass Custom Authentication Cookies](configure-the-web-portal-to-pass-custom-authentication-cookies.md).</span></span>  
  
13. <span data-ttu-id="6467d-131">Enregistrez le fichier .</span><span class="sxs-lookup"><span data-stu-id="6467d-131">Save the file.</span></span>  
  
14. <span data-ttu-id="6467d-132">Si vous avez configuré un déploiement avec montée en puissance parallèle, répétez l’ensemble des étapes précédentes pour d'autres serveurs de rapports du déploiement.</span><span class="sxs-lookup"><span data-stu-id="6467d-132">If you configured a scale-out deployment, repeat all of the previous steps for other report servers in the deployment.</span></span>  
  
15. <span data-ttu-id="6467d-133">Redémarrez le serveur de rapports pour effacer toutes les sessions qui sont actuellement ouvertes.</span><span class="sxs-lookup"><span data-stu-id="6467d-133">Restart the report server to clear any sessions that are currently open.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6467d-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6467d-134">See Also</span></span>  
 <span data-ttu-id="6467d-135">[Implémentation d’une extension de sécurité](../extensions/security-extension/implementing-a-security-extension.md) </span><span class="sxs-lookup"><span data-stu-id="6467d-135">[Implementing a Security Extension](../extensions/security-extension/implementing-a-security-extension.md) </span></span>  
 <span data-ttu-id="6467d-136">[Authentification avec le serveur de rapports](authentication-with-the-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="6467d-136">[Authentication with the Report Server](authentication-with-the-report-server.md) </span></span>  
 <span data-ttu-id="6467d-137">[Fichier de configuration RSReportServer](../report-server/rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="6467d-137">[RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md) </span></span>  
 <span data-ttu-id="6467d-138">[Configurer l’authentification de base sur le serveur de rapports](configure-basic-authentication-on-the-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="6467d-138">[Configure Basic Authentication on the Report Server](configure-basic-authentication-on-the-report-server.md) </span></span>  
 [<span data-ttu-id="6467d-139">Configurer une authentification Windows sur le serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="6467d-139">Configure Windows Authentication on the Report Server</span></span>](configure-windows-authentication-on-the-report-server.md)  
  
  
