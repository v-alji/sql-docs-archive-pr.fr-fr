---
title: Scripts et PowerShell avec Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- scripts [Reporting Services]
- Reporting Services, scripting
- scripting [Reporting Services]
ms.assetid: 1ac2646d-ed5a-4436-b18f-2150c33f3d87
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a7a8dc805351897c11202467ed8bcb0373ef77c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610971"
---
# <a name="scripting-and-powershell-with-reporting-services"></a><span data-ttu-id="572f3-102">Scripts et PowerShell avec Reporting Services</span><span class="sxs-lookup"><span data-stu-id="572f3-102">Scripting and PowerShell with Reporting Services</span></span>
  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="572f3-103">prend en charge un large éventail de scénarios de développement et de gestion via script, notamment l'utilitaire de ligne de commande rs.exe, les applets de commande PowerShell pour les serveurs de rapports en mode SharePoint et l'exploitation du modèle d'objet [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] de PowerShell pour le mode natif et le mode SharePoint.</span><span class="sxs-lookup"><span data-stu-id="572f3-103">supports a wide range of development and management scenarios through script, including the rs.exe command line utility, PowerShell cmdlets for SharePoint mode report servers, and leveraging the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] object model from PowerShell for both Native and SharePoint mode.</span></span>

-   <span data-ttu-id="572f3-104">Les administrateurs peuvent écrire les scripts dans [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] pour automatiser le déploiement et la gestion d'une installation du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="572f3-104">Administrators can write script in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] to automate how they deploy and manage a report server installation.</span></span> <span data-ttu-id="572f3-105">Les administrateurs peuvent également générer et exécuter des scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] qui créent, configurent et mettent à jour une base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="572f3-105">Administrators can also generate and run [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts that create, configure, and update a report server database.</span></span> <span data-ttu-id="572f3-106">Les administrateurs peuvent aussi utiliser les fonctionnalités d'enregistrement et de lecture de scripts de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] pour automatiser les tâches régulières de maintenance.</span><span class="sxs-lookup"><span data-stu-id="572f3-106">Administrators can also use the record and playback script features in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to automate routine maintenance tasks.</span></span>

-   <span data-ttu-id="572f3-107">Les développeurs peuvent créer des applications personnalisées incluant des scripts.</span><span class="sxs-lookup"><span data-stu-id="572f3-107">Developers can create custom applications that include script.</span></span> <span data-ttu-id="572f3-108">Vous pouvez exécuter des scripts qui effectuent des appels au service Web Report Server.</span><span class="sxs-lookup"><span data-stu-id="572f3-108">You can run script that makes calls to the Report Server Web service.</span></span> <span data-ttu-id="572f3-109">Pratiquement chaque opération que vous pouvez écrire en code managé peut également l'être écrite sous forme de script.</span><span class="sxs-lookup"><span data-stu-id="572f3-109">Almost any operation that you can write in managed code can also be written in script.</span></span>

-   [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="572f3-110">prend en charge le script .NET [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] comme langage de script pouvant être traité par l'utilitaire RS.exe, un hôte de script qui s'exécute sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="572f3-110">supports [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET script as the script language that can be processed by the RS.exe utility, a script host that runs on the report server.</span></span>

## <a name="reporting-services-sharepoint-mode-powershell-cmdlets-and-samples"></a><span data-ttu-id="572f3-111">Exemples et applets de commande PowerShell du mode SharePoint de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="572f3-111">Reporting Services SharePoint mode PowerShell cmdlets and samples</span></span>
 <span data-ttu-id="572f3-112">![Contenu relatif à PowerShell](../media/rs-powershellicon.jpg "Contenu relatif à PowerShell")</span><span class="sxs-lookup"><span data-stu-id="572f3-112">![PowerShell related content](../media/rs-powershellicon.jpg "PowerShell related content")</span></span>

 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="572f3-113">Le mode SharePoint inclut des applets de commande [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] pour l'administration des serveurs de rapports.</span><span class="sxs-lookup"><span data-stu-id="572f3-113">SharePoint mode includes [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] cmdlets for report server administration.</span></span>

-   <span data-ttu-id="572f3-114">La section[PowerShell cmdlets for Reporting Services SharePoint Mode](../powershell-cmdlets-for-reporting-services-sharepoint-mode.md) inclut les exemples suivants :</span><span class="sxs-lookup"><span data-stu-id="572f3-114">[PowerShell cmdlets for Reporting Services SharePoint Mode](../powershell-cmdlets-for-reporting-services-sharepoint-mode.md) Includes the following examples:</span></span>

    -   <span data-ttu-id="572f3-115">Créer une application de service et un proxy</span><span class="sxs-lookup"><span data-stu-id="572f3-115">Create a service application and proxy</span></span>

    -   <span data-ttu-id="572f3-116">Analyse et mise à jour d'une extension de remise</span><span class="sxs-lookup"><span data-stu-id="572f3-116">Review and update a delivery extension</span></span>

    -   <span data-ttu-id="572f3-117">Obtenir et définir les propriétés de la base de données d'application Reporting Services, par exemple le délai d'expiration de la base de données</span><span class="sxs-lookup"><span data-stu-id="572f3-117">Get and set Properties of the Reporting Service Application Database, for example database timeout</span></span>

    -   <span data-ttu-id="572f3-118">Extensions de données Liste</span><span class="sxs-lookup"><span data-stu-id="572f3-118">List Data Extensions</span></span>

## <a name="reporting-services-object-model-and-powershell-samples"></a><span data-ttu-id="572f3-119">Exemples du modèle d'objet Reporting Services et de Powershell</span><span class="sxs-lookup"><span data-stu-id="572f3-119">Reporting Services Object model and Powershell samples</span></span>
 <span data-ttu-id="572f3-120">![Contenu relatif à PowerShell](../media/rs-powershellicon.jpg "Contenu relatif à PowerShell")</span><span class="sxs-lookup"><span data-stu-id="572f3-120">![PowerShell related content](../media/rs-powershellicon.jpg "PowerShell related content")</span></span>

 <span data-ttu-id="572f3-121">Appel du modèle d'objet principal par PowerShell, valide en grande partie pour les modes natif et SharePoint, comme les tâches de migration et d'abonnement, et d'autres exemples associés de tâches d'abonnement dans SQL15.</span><span class="sxs-lookup"><span data-stu-id="572f3-121">PowerShell calling the core object model and for the most part valid for SharePoint and native mode, for example the migration work, subscription work, and more related samples for subscriptions work in SQL15.</span></span>

-   <span data-ttu-id="572f3-122">[Utiliser PowerShell pour modifier et répertorier les propriétaires d’abonnements Reporting Services, et exécuter un abonnement](../subscriptions/manage-subscription-owners-and-run-subscription-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="572f3-122">[Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription](../subscriptions/manage-subscription-owners-and-run-subscription-powershell.md).</span></span>

-   <span data-ttu-id="572f3-123">[Utilisation de PowerShell pour créer une machine virtuelle Azure avec un serveur de rapports en mode natif](https://msdn.microsoft.com/library/azure/dn449661.aspx).</span><span class="sxs-lookup"><span data-stu-id="572f3-123">[Use PowerShell to Create an Azure VM With a Native Mode Report Server](https://msdn.microsoft.com/library/azure/dn449661.aspx).</span></span>

-   <span data-ttu-id="572f3-124">Consultez la section « Accéder aux classes WMI à l’aide de PowerShell » dans [Accéder au fournisseur WMI de Reporting Services](access-the-reporting-services-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="572f3-124">See the section "Access the WMI classes using PowerShell" in [Access the Reporting Services WMI Provider](access-the-reporting-services-wmi-provider.md).</span></span>

-   <span data-ttu-id="572f3-125">[Comment administrer SSRS à l'aide de PowerShell](https://www.sqlshack.com/how-to-administer-sql-server-reporting-services-ssrs-subscriptions-using-powershell/).scriptin</span><span class="sxs-lookup"><span data-stu-id="572f3-125">[How to Administer SSRS using PowerShell](https://www.sqlshack.com/how-to-administer-sql-server-reporting-services-ssrs-subscriptions-using-powershell/).scriptin</span></span>

## <a name="rsexe-scripting-samples"></a><span data-ttu-id="572f3-126">Exemples de scripts RS.exe</span><span class="sxs-lookup"><span data-stu-id="572f3-126">RS.exe scripting samples</span></span>

-   <span data-ttu-id="572f3-127">[Exemple Reporting Services rs.exe script pour migrer le contenu entre les serveurs de rapports](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="572f3-127">[Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span></span>

-   <span data-ttu-id="572f3-128">Pour obtenir des exemples supplémentaires de script, d'application et d'extension, consultez les [exemples de produit SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="572f3-128">For additional script, application, and extension examples, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>

## <a name="see-also"></a><span data-ttu-id="572f3-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="572f3-129">See Also</span></span>
 <span data-ttu-id="572f3-130">[Utilitaire deRS.exe &#40;](rs-exe-utility-ssrs.md) script de [déploiement et de tâches d’administration SSRS&#41;script](script-deployment-and-administrative-tasks.md) [avec l’utilitaire rs.exe et le service Web](script-with-the-rs-exe-utility-and-the-web-service.md)</span><span class="sxs-lookup"><span data-stu-id="572f3-130">[RS.exe Utility &#40;SSRS&#41;](rs-exe-utility-ssrs.md) [Script Deployment and Administrative Tasks](script-deployment-and-administrative-tasks.md) [Script with the rs.exe Utility and the Web Service](script-with-the-rs-exe-utility-and-the-web-service.md)</span></span>


