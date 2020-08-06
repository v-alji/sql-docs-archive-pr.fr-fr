---
title: Accéder au fournisseur WMI de Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- Reporting Services WMI Provider
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- WMI provider [Reporting Services]
- programming [Reporting Services]
ms.assetid: 22cfbeb8-4ea3-4182-8f54-3341c771e87b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: db0848ae8c988229a1804bbd4b19e6c38b68c35f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706195"
---
# <a name="access-the-reporting-services-wmi-provider"></a><span data-ttu-id="e8fed-102">Accéder au fournisseur WMI de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="e8fed-102">Access the Reporting Services WMI Provider</span></span>
  <span data-ttu-id="e8fed-103">Le fournisseur WMI de Reporting Services présente deux classes WMI pour l'administration des instances de serveur de rapports en mode natif par script :</span><span class="sxs-lookup"><span data-stu-id="e8fed-103">The Reporting Services WMI provider exposes two WMI classes for administration of Native mode report server instances through scripting:</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e8fed-104">À compter de la version [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , le fournisseur WMI est pris en charge uniquement pour les serveurs de rapports en mode natif.</span><span class="sxs-lookup"><span data-stu-id="e8fed-104">Starting with the [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] release, the WMI provider is supported for only native mode report servers.</span></span> <span data-ttu-id="e8fed-105">Les serveurs de rapports en mode SharePoint peuvent être gérés avec les scripts PowerShell et les pages de l'Administration centrale de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e8fed-105">SharePoint mode report servers can be managed with SharePoint Central Administration pages and PowerShell scripts.</span></span>  
  
|<span data-ttu-id="e8fed-106">Classe</span><span class="sxs-lookup"><span data-stu-id="e8fed-106">Class</span></span>|<span data-ttu-id="e8fed-107">Espace de noms</span><span class="sxs-lookup"><span data-stu-id="e8fed-107">Namespace</span></span>|<span data-ttu-id="e8fed-108">Description</span><span class="sxs-lookup"><span data-stu-id="e8fed-108">Description</span></span>|  
|-----------|---------------|-----------------|  
|<span data-ttu-id="e8fed-109">MSReportServer_Instance</span><span class="sxs-lookup"><span data-stu-id="e8fed-109">MSReportServer_Instance</span></span>|<span data-ttu-id="e8fed-110">root\Microsoft\SqlServer\ReportServer\ RS_ *\<EncodedInstanceName>* \v11</span><span class="sxs-lookup"><span data-stu-id="e8fed-110">root\Microsoft\SqlServer\ReportServer\RS_*\<EncodedInstanceName>* \v11</span></span>|<span data-ttu-id="e8fed-111">Fournit les informations de base nécessaires à un client pour établir la connexion à un serveur de rapports installé.</span><span class="sxs-lookup"><span data-stu-id="e8fed-111">Provides basic information required for a client to connect to an installed report server.</span></span>|  
|<span data-ttu-id="e8fed-112">MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="e8fed-112">MSReportServer_ConfigurationSetting</span></span>|<span data-ttu-id="e8fed-113">root\Microsoft\SqlServer\ReportServer\ RS_ *\<EncodedInstanceName>* \v11\Admin</span><span class="sxs-lookup"><span data-stu-id="e8fed-113">root\Microsoft\SqlServer\ReportServer\RS_*\<EncodedInstanceName>* \v11\Admin</span></span>|<span data-ttu-id="e8fed-114">Représente les paramètres d'installation et d'exécution d'une instance de serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="e8fed-114">Represents the installation and run-time parameters of a report server instance.</span></span> <span data-ttu-id="e8fed-115">Ces paramètres sont stockés dans le fichier de configuration du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="e8fed-115">These parameters are stored in the configuration file for the report server.</span></span><br /><br /> <span data-ttu-id="e8fed-116">**\*\* Important \*\*** Cette classe est accessible uniquement avec des privilèges d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="e8fed-116">**\*\* Important \*\*** This class is only accessible with administrative privileges.</span></span>|  
  
 <span data-ttu-id="e8fed-117">Une instance de chaque classe ci-dessus est créée pour chaque instance du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="e8fed-117">An instance of each of the above classes is created for each report server instance.</span></span> <span data-ttu-id="e8fed-118">Vous pouvez utiliser tous les outils Microsoft ou tiers pour accéder aux objets WMI exposés par le serveur de rapports, notamment les interfaces de programmation WMI exposées par .NET framework lui-même.</span><span class="sxs-lookup"><span data-stu-id="e8fed-118">You can use any Microsoft or third party tools to access the WMI objects exposed by the report server, including WMI programming interfaces exposed by the .NET Framework itself.</span></span> <span data-ttu-id="e8fed-119">Cette rubrique décrit comment accéder aux instances de classes WMI, et les utiliser, avec la commande PowerShell [Get-WmiObject](https://technet.microsoft.com/library/dd315295.aspx).</span><span class="sxs-lookup"><span data-stu-id="e8fed-119">This topic describes how to access and use the WMI class instances with the PowerShell command [Get-WmiObject](https://technet.microsoft.com/library/dd315295.aspx).</span></span>  
  
## <a name="determine-the-instance-name-in-the-namespace-string"></a><span data-ttu-id="e8fed-120">Déterminez le nom de l'instance dans la chaîne de l'espace de noms</span><span class="sxs-lookup"><span data-stu-id="e8fed-120">Determine the Instance Name in the Namespace String</span></span>  
 <span data-ttu-id="e8fed-121">Le nom de l'instance dans le chemin d'accès de l'espace de noms pour les classes WMI de Reporting Services est un encodage des noms d'instance que vous spécifiez lors de l'installation des instances nommées Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="e8fed-121">The instance name in the namespace path for the Reporting Services WMI classes is an encoding of the instance names that you specify when installing the named Reporting Services instances.</span></span> <span data-ttu-id="e8fed-122">À savoir, les caractères spéciaux dans les noms d'instance sont encodés.</span><span class="sxs-lookup"><span data-stu-id="e8fed-122">Namely, special characters in the instance names are encoded.</span></span> <span data-ttu-id="e8fed-123">Par exemple, un trait de soulignement (_) étant encodé en « _5f », le nom d’instance « Mon_instance » est encodé en « Mon_5finstance » dans le chemin de l’espace de noms WMI.</span><span class="sxs-lookup"><span data-stu-id="e8fed-123">For example, an underline (_) is encoded as "_5f", so an instance name of "My_Instance" is encoded as "My_5fInstance" in the WMI namespace path.</span></span>  
  
 <span data-ttu-id="e8fed-124">Pour répertorier les noms d'instance encodés de vos instances de serveur de rapports dans le chemin d'accès de l'espace de noms WMI, utilisez la commande suivante PowerShell :</span><span class="sxs-lookup"><span data-stu-id="e8fed-124">To list the encoded instance names of your report server instances in the WMI namespace path, use the following PowerShell command:</span></span>  
  
```powershell
Get-WmiObject -Namespace root\Microsoft\SqlServer\ReportServer -Class __Namespace -ComputerName hostname | Select Name  
```  
  
## <a name="access-the-wmi-classes-using-powershell"></a><span data-ttu-id="e8fed-125">Accédez aux classes WMI à l'aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8fed-125">Access the WMI Classes Using PowerShell</span></span>  
 <span data-ttu-id="e8fed-126">Pour accéder aux classes WMI, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="e8fed-126">To access the WMI classes, run the following command:</span></span>  
  
```powershell
Get-WmiObject -Namespace <namespacename> -Class <classname> -ComputerName <hostname>  
```  
  
 <span data-ttu-id="e8fed-127">Par exemple, pour accéder à la classe MSReportServer_ConfigurationSetting sur l'instance de serveur de rapports par défaut de l'hôte myrshost, exécutez la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="e8fed-127">For example, to access the MSReportServer_ConfigurationSetting class on the default report server instance of the host myrshost, run the following command.</span></span> <span data-ttu-id="e8fed-128">L'instance du serveur de rapports par défaut doit être installée sur myrshost pour que cette commande réussisse.</span><span class="sxs-lookup"><span data-stu-id="e8fed-128">The default report server instance must be installed on myrshost for this command to succeed.</span></span>  
  
```powershell
Get-WmiObject -Namespace "root\Microsoft\SqlServer\ReportServer\RS_MSSQLSERER\v11\Admin" -Class MSReportServer_ConfigurationSetting -ComputerName myrshost  
```  
  
 <span data-ttu-id="e8fed-129">Cette syntaxe de commande génère tous les noms et valeurs de propriété de classe.</span><span class="sxs-lookup"><span data-stu-id="e8fed-129">This command syntax outputs all class property names and values.</span></span> <span data-ttu-id="e8fed-130">Notez que toutes les instances de la classe MSReportServer_ConfigurationSetting sont retournées, même si vous accédez à la classe dans l'espace de noms de l'instance de serveur de rapports par défaut (RS_MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="e8fed-130">Note that all instances of the class MSReportServer_ConfigurationSetting is returned, even though you are accessing the class in the namespace of the default report server instance (RS_MSSQLSERVER).</span></span> <span data-ttu-id="e8fed-131">Par exemple, si myrshost est installé avec l'instance de serveur de rapports par défaut et une instance du serveur de rapports nommée appelées SHAREPOINT, cette commande retourne deux objets WMI et génère les noms et valeurs des propriétés pour les deux instances du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="e8fed-131">For example, if myrshost is installed with the default report server instance and a named report server instance called SHAREPOINT, this command will return two WMI objects and output the property names and values for both report server instances.</span></span>  
  
 <span data-ttu-id="e8fed-132">Pour retourner une instance de classe spécifique quand plusieurs instances sont retournées, utilisez le paramètre –Filter pour filtrer les résultats en fonction de propriétés à valeurs uniques comme InstanceName.</span><span class="sxs-lookup"><span data-stu-id="e8fed-132">To return a specific class instance when multiple instances are returned, use the -Filter parameter to filter the results based on properties with unique values such as InstanceName.</span></span> <span data-ttu-id="e8fed-133">Par exemple, pour retourner uniquement l'objet WMI pour l'instance de serveur de rapports par défaut, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="e8fed-133">For example, to return only the WMI object for the default report server instance, use the following command:</span></span>  
  
```powershell
Get-WmiObject -Namespace "root\Microsoft\SqlServer\ReportServer\RS_MSSQLServer\v11\Admin" -Class MSReportServer_ConfigurationSetting -ComputerName myrshost -Filter "InstanceName='MSSQLSERVER'"  
```  
  
## <a name="query-the-available-methods-and-properties"></a><span data-ttu-id="e8fed-134">Interrogez les méthodes et les propriétés disponibles</span><span class="sxs-lookup"><span data-stu-id="e8fed-134">Query the Available Methods and Properties</span></span>  
 <span data-ttu-id="e8fed-135">Pour connaître les méthodes et propriétés disponibles dans l'une des classes WMI de Reporting Services, acheminez les résultats de Get-WmiObject vers la commande Get-Member.</span><span class="sxs-lookup"><span data-stu-id="e8fed-135">To see what methods and properties are available in one of the Reporting Services WMI classes, pipe the results from Get-WmiObject to the Get-Member command.</span></span> <span data-ttu-id="e8fed-136">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="e8fed-136">For example:</span></span>  
  
```powershell
Get-WmiObject -Namespace "root\Microsoft\SqlServer\ReportServer\RS_MSSQLServer\v11\Admin" -Class MSReportServer_ConfigurationSetting -ComputerName myrshost | Get-Member  
```  
  
 <span data-ttu-id="e8fed-137">Pour obtenir de la documentation sur les propriétés et les méthodes des classes WMI Reporting Services, consultez....</span><span class="sxs-lookup"><span data-stu-id="e8fed-137">For documentation on the properties and methods of the Reporting Services WMI classes, see ....</span></span>  
  
## <a name="use-a-wmi-method-or-property"></a><span data-ttu-id="e8fed-138">Utilisez une propriété ou une méthode WMI</span><span class="sxs-lookup"><span data-stu-id="e8fed-138">Use a WMI Method or Property</span></span>  
 <span data-ttu-id="e8fed-139">une fois que vous avez les objets WMI dans les classes de Reporting Services et que vous connaissez les propriétés et les méthodes disponibles, vous pouvez utiliser ces méthodes et propriétés.</span><span class="sxs-lookup"><span data-stu-id="e8fed-139">Once you have the WMI objects to the Reporting Services classes and know the available methods and properties, you can use these methods and properties.</span></span> <span data-ttu-id="e8fed-140">Par exemple, si vous avez une instance de serveur de rapports nommée dans le mode intégré SharePoint appelée SHAREPOINT, utilisez la séquence de commande suivante pour récupérer l'URL pour le site Administration centrale de SharePoint :</span><span class="sxs-lookup"><span data-stu-id="e8fed-140">For example, if you have a named report server instance in SharePoint integrated mode called SHAREPOINT, use the following command sequence to retrieve the URL for the SharePoint Central Administration site:</span></span>  
  
```powershell
$rsconfig = Get-WmiObject -Namespace "root\Microsoft\SqlServer\ReportServer\RS_MSSQLServer\v11\Admin" -Class MSReportServer_ConfigurationSetting -ComputerName myrshost -Filter "InstanceName='SHAREPOINT'"  
$rsconfig.GetAdminSiteUrl()  
```  
  
## <a name="see-also"></a><span data-ttu-id="e8fed-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e8fed-141">See Also</span></span>
 <span data-ttu-id="e8fed-142">[Informations de référence sur la bibliothèque du fournisseur WMI Reporting Services &#40;SSRS&#41;](../wmi-provider-library-reference/reporting-services-wmi-provider-library-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e8fed-142">[Reporting Services WMI Provider Library Reference &#40;SSRS&#41;](../wmi-provider-library-reference/reporting-services-wmi-provider-library-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="e8fed-143">Fichier de configuration RSReportServer</span><span class="sxs-lookup"><span data-stu-id="e8fed-143">RSReportServer Configuration File</span></span>](../report-server/rsreportserver-config-configuration-file.md)  
