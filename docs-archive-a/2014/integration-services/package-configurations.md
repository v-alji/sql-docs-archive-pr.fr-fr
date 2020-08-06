---
title: Configurations du package | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- package configuration syntax [Integration Services]
- SQL Server Integration Services packages, configurations
- SSIS packages, configurations
- XML [Integration Services]
- Integration Services packages, configurations
- configuration syntax [Integration Services]
- indirect configurations [Integration Services]
- configurations [Integration Services]
- direct configurations [Integration Services]
- packages [Integration Services], configurations
ms.assetid: d20e0311-1fc9-4ddc-a381-6d127cf11b69
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0d22dbfedcf4cf7084e1667586f9774926f3b2a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614731"
---
# <a name="package-configurations"></a><span data-ttu-id="da00f-102">Configurations du package</span><span class="sxs-lookup"><span data-stu-id="da00f-102">Package Configurations</span></span>
  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="da00f-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] fournit des configurations de package avec lesquelles vous pouvez mettre à jour les valeurs des propriétés au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="da00f-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] provides package configurations that you can use to update the values of properties at run time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="da00f-104">Des configurations sont disponibles pour le modèle de déploiement de package.</span><span class="sxs-lookup"><span data-stu-id="da00f-104">Configurations are available for the package deployment model.</span></span> <span data-ttu-id="da00f-105">Les paramètres sont utilisés à la place des configurations pour le modèle de déploiement de projet.</span><span class="sxs-lookup"><span data-stu-id="da00f-105">Parameters are used in place of configurations for the project deployment model.</span></span> <span data-ttu-id="da00f-106">Le modèle de déploiement de projet vous permet de déployer des projets [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sur le serveur [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="da00f-106">The project deployment model enables you to deploy [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="da00f-107">Pour plus d'informations sur les modèles de déploiement, consultez [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="da00f-107">For more information about the deployment models, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="da00f-108">Une configuration est une paire propriété/valeur que vous ajoutez à un package terminé.</span><span class="sxs-lookup"><span data-stu-id="da00f-108">A configuration is a property/value pair that you add to a completed package.</span></span> <span data-ttu-id="da00f-109">En règle générale, vous devez créer un package, définir des propriétés sur les objets du package lors du développement de ce dernier, puis ajouter la configuration au package.</span><span class="sxs-lookup"><span data-stu-id="da00f-109">Typically, you create a package set properties on the package objects during package development, and then add the configuration to the package.</span></span> <span data-ttu-id="da00f-110">Lors de son exécution, le package extrait les nouvelles valeurs de la propriété à partir de la configuration.</span><span class="sxs-lookup"><span data-stu-id="da00f-110">When the package runs, it gets the new values of the property from the configuration.</span></span> <span data-ttu-id="da00f-111">Par exemple, lorsque vous utilisez une configuration, vous pouvez modifier la chaîne de connexion d'un gestionnaire de connexions ou mettre à jour la valeur d'une variable.</span><span class="sxs-lookup"><span data-stu-id="da00f-111">For example, by using a configuration, you can change the connection string of a connection manager, or update the value of a variable.</span></span>  
  
 <span data-ttu-id="da00f-112">Les configurations de package offrent les avantages suivants :</span><span class="sxs-lookup"><span data-stu-id="da00f-112">Package configurations provide the following benefits:</span></span>  
  
-   <span data-ttu-id="da00f-113">Les configurations facilitent le déplacement des packages d'un environnement de développement vers un environnement de production.</span><span class="sxs-lookup"><span data-stu-id="da00f-113">Configurations make it easier to move packages from a development environment to a production environment.</span></span> <span data-ttu-id="da00f-114">Par exemple, une configuration peut mettre à jour le chemin d'accès d'un fichier source ou bien modifier le nom d'une base de données ou d'un serveur.</span><span class="sxs-lookup"><span data-stu-id="da00f-114">For example, a configuration can update the path of a source file, or change the name of a database or server.</span></span>  
  
-   <span data-ttu-id="da00f-115">Les configurations sont utiles lorsque vous déployez des packages sur de nombreux serveurs différents.</span><span class="sxs-lookup"><span data-stu-id="da00f-115">Configurations are useful when you deploy packages to many different servers.</span></span> <span data-ttu-id="da00f-116">Par exemple, une variable dans la configuration de chaque package déployé peut contenir une valeur d'espace disque différente, et si l'espace disque disponible ne correspond pas à cette valeur, le package ne s'exécute pas.</span><span class="sxs-lookup"><span data-stu-id="da00f-116">For example, a variable in the configuration for each deployed package can contain a different disk space value, and if the available disk space does not meet this value, the package does not run.</span></span>  
  
-   <span data-ttu-id="da00f-117">Les configurations rendent ces packages plus souples.</span><span class="sxs-lookup"><span data-stu-id="da00f-117">Configurations make packages more flexible.</span></span> <span data-ttu-id="da00f-118">Par exemple, une configuration peut mettre à jour la valeur d'une variable utilisée dans une expression de propriété.</span><span class="sxs-lookup"><span data-stu-id="da00f-118">For example, a configuration can update the value of a variable that is used in a property expression.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="da00f-119">prend en charge différentes méthodes de stockage des configurations de package, telles que les fichiers XML, les tables d'une base de données [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] et les variables d'environnement et de package.</span><span class="sxs-lookup"><span data-stu-id="da00f-119">supports several different methods of storing package configurations, such as XML files, tables in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database, and environment and package variables.</span></span>  
  
 <span data-ttu-id="da00f-120">Chaque configuration est une paire propriété/valeur.</span><span class="sxs-lookup"><span data-stu-id="da00f-120">Each configuration is a property/value pair.</span></span> <span data-ttu-id="da00f-121">Le fichier de configuration XML et les types de configuration [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] peuvent inclure plusieurs configurations.</span><span class="sxs-lookup"><span data-stu-id="da00f-121">The XML configuration file and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] configuration types can include multiple configurations.</span></span>  
  
 <span data-ttu-id="da00f-122">Les configurations sont incluses lorsque vous créez un utilitaire de déploiement de package pour l'installation des packages.</span><span class="sxs-lookup"><span data-stu-id="da00f-122">The configurations are included when you create a package deployment utility for installing packages.</span></span> <span data-ttu-id="da00f-123">Lorsque vous installez les packages, les configurations peuvent être mises à jour lors d'une étape de l'installation du package.</span><span class="sxs-lookup"><span data-stu-id="da00f-123">When you install the packages, the configurations can be updated as a step in the package installation.</span></span>  
  
## <a name="understanding-how-package-configurations-are-applied-at-run-time"></a><span data-ttu-id="da00f-124">Fonctionnement de l'application des configurations de package au moment de l'exécution</span><span class="sxs-lookup"><span data-stu-id="da00f-124">Understanding How Package Configurations Are Applied at Run Time</span></span>  
 <span data-ttu-id="da00f-125">Quand vous utilisez l’utilitaire d’invite de commandes **dtexec** (dtexec.exe) pour exécuter un package déployé, l’utilitaire applique les configurations de package à deux reprises.</span><span class="sxs-lookup"><span data-stu-id="da00f-125">When you use the **dtexec** command prompt utility (dtexec.exe) to run a deployed package, the utility applies package configurations twice.</span></span> <span data-ttu-id="da00f-126">L'utilitaire applique les configurations avant et après avoir appliqué les options que vous avez spécifiées sur la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="da00f-126">The utility applies configurations both before and after it applies the options that you specified on command line.</span></span>  
  
 <span data-ttu-id="da00f-127">Lorsque l'utilitaire charge et exécute le package, des événements se produisent dans l'ordre suivant :</span><span class="sxs-lookup"><span data-stu-id="da00f-127">As the utility loads and runs the package, events occur in the following order:</span></span>  
  
1.  <span data-ttu-id="da00f-128">L’utilitaire **dtexec** charge le package.</span><span class="sxs-lookup"><span data-stu-id="da00f-128">The **dtexec** utility loads the package.</span></span>  
  
2.  <span data-ttu-id="da00f-129">L'utilitaire applique les configurations spécifiées dans le package au moment de la conception et dans l'ordre spécifié dans le package.</span><span class="sxs-lookup"><span data-stu-id="da00f-129">The utility applies the configurations that were specified in the package at design time and in the order that is specified in the package.</span></span> <span data-ttu-id="da00f-130">(La seule exception concerne les configurations des variables de package parent.</span><span class="sxs-lookup"><span data-stu-id="da00f-130">(The one exception to this is the Parent Package Variables configurations.</span></span> <span data-ttu-id="da00f-131">L'utilitaire applique ces configurations une seule fois et ultérieurement au cours du processus).</span><span class="sxs-lookup"><span data-stu-id="da00f-131">The utility applies these configurations only once and later in the process.)</span></span>  
  
3.  <span data-ttu-id="da00f-132">L'utilitaire applique ensuite les options que vous avez spécifiées sur la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="da00f-132">The utility then applies any options that you specified on the command line.</span></span>  
  
4.  <span data-ttu-id="da00f-133">L'utilitaire recharge ensuite les configurations spécifiées dans le package au moment du design et dans l'ordre spécifié dans le package.</span><span class="sxs-lookup"><span data-stu-id="da00f-133">The utility then reloads the configurations that were specified in the package at design time and in the order specified in the package.</span></span> <span data-ttu-id="da00f-134">(Une fois encore, la seule exception à cette règle concerne les configurations des variables de package parent).</span><span class="sxs-lookup"><span data-stu-id="da00f-134">(Again, the exception to this rule is the Parent Package Variables configurations).</span></span> <span data-ttu-id="da00f-135">L'utilitaire se base sur les options de ligne de commande spécifiées pour recharger les configurations.</span><span class="sxs-lookup"><span data-stu-id="da00f-135">The utility uses any command-line options that were specified to reload the configurations.</span></span> <span data-ttu-id="da00f-136">Par conséquent, des valeurs différentes peuvent être rechargées à partir d'un emplacement distinct.</span><span class="sxs-lookup"><span data-stu-id="da00f-136">Therefore, different values might be reloaded from a different location.</span></span>  
  
5.  <span data-ttu-id="da00f-137">L'utilitaire applique les configurations des variables de package parent.</span><span class="sxs-lookup"><span data-stu-id="da00f-137">The utility applies the Parent Package Variable configurations.</span></span>  
  
6.  <span data-ttu-id="da00f-138">L'utilitaire exécute le package.</span><span class="sxs-lookup"><span data-stu-id="da00f-138">The utility runs the package.</span></span>  
  
 <span data-ttu-id="da00f-139">La façon dont l’utilitaire **dtexec** applique les configurations affecte les options de ligne de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="da00f-139">The way in which the **dtexec** utility applies configurations affects the following command-line options:</span></span>  
  
-   <span data-ttu-id="da00f-140">Vous pouvez utiliser l’option **/Connection** ou **/Set** à l’exécution pour charger les configurations de package à partir d’un emplacement autre que celui que vous avez spécifié au moment de la conception.</span><span class="sxs-lookup"><span data-stu-id="da00f-140">You can use the **/Connection** or **/Set** option at run time to load package configurations from a location other than the location that you specified at design time.</span></span>  
  
-   <span data-ttu-id="da00f-141">Vous pouvez utiliser l’option **/ConfigFile** pour charger des configurations supplémentaires que vous n’aviez pas spécifiées au moment de la conception.</span><span class="sxs-lookup"><span data-stu-id="da00f-141">You can use the **/ConfigFile** option to load additional configurations that you did not specify at design time.</span></span>  
  
 <span data-ttu-id="da00f-142">Toutefois, ces options de ligne de commande sont soumises à quelques restrictions :</span><span class="sxs-lookup"><span data-stu-id="da00f-142">However, these command-line options do have some restrictions:</span></span>  
  
-   <span data-ttu-id="da00f-143">Vous ne pouvez pas utiliser l’option **/Set** ou **/Connection** pour remplacer des valeurs uniques qui sont également définies par une configuration.</span><span class="sxs-lookup"><span data-stu-id="da00f-143">You cannot use the **/Set** or the **/Connection** option to override single values that are also set by a configuration.</span></span>  
  
-   <span data-ttu-id="da00f-144">Vous ne pouvez pas utiliser l’option **/ConfigFile** pour charger des configurations qui remplacent celles que vous aviez spécifiées au moment de la conception.</span><span class="sxs-lookup"><span data-stu-id="da00f-144">You cannot use the **/ConfigFile** option to load configurations that replace the configurations that you specified at design time.</span></span>  
  
 <span data-ttu-id="da00f-145">Pour plus d’informations sur ces options et sur la façon dont le comportement de ces options diffère entre [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] et les versions antérieures, consultez [modification du comportement des fonctionnalités de Integration Services dans SQL Server 2014](../../2014/integration-services/behavior-changes-to-integration-services-features-in-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="da00f-145">For more information about these options, and how the behavior of these options differs between [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] and earlier versions, see [Behavior Changes to Integration Services Features in SQL Server 2014](../../2014/integration-services/behavior-changes-to-integration-services-features-in-sql-server-2014.md).</span></span>  
  
## <a name="package-configuration-types"></a><span data-ttu-id="da00f-146">Types de configuration de package</span><span class="sxs-lookup"><span data-stu-id="da00f-146">Package Configuration Types</span></span>  
 <span data-ttu-id="da00f-147">Le tableau suivant décrit les types de configuration de package.</span><span class="sxs-lookup"><span data-stu-id="da00f-147">The following table describes the package configuration types.</span></span>  
  
|<span data-ttu-id="da00f-148">Type</span><span class="sxs-lookup"><span data-stu-id="da00f-148">Type</span></span>|<span data-ttu-id="da00f-149">Description</span><span class="sxs-lookup"><span data-stu-id="da00f-149">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="da00f-150">Fichier de configuration XML</span><span class="sxs-lookup"><span data-stu-id="da00f-150">XML configuration file</span></span>|<span data-ttu-id="da00f-151">Un fichier XML contient les configurations.</span><span class="sxs-lookup"><span data-stu-id="da00f-151">An XML file contains the configurations.</span></span> <span data-ttu-id="da00f-152">Le fichier XML peut inclure plusieurs configurations.</span><span class="sxs-lookup"><span data-stu-id="da00f-152">The XML file can include multiple configurations.</span></span>|  
|<span data-ttu-id="da00f-153">Variable d’environnement</span><span class="sxs-lookup"><span data-stu-id="da00f-153">Environment variable</span></span>|<span data-ttu-id="da00f-154">Une variable d'environnement contient la configuration.</span><span class="sxs-lookup"><span data-stu-id="da00f-154">An environment variable contains the configuration.</span></span>|  
|<span data-ttu-id="da00f-155">Entrée de Registre</span><span class="sxs-lookup"><span data-stu-id="da00f-155">Registry entry</span></span>|<span data-ttu-id="da00f-156">Une entrée de Registre contient la configuration.</span><span class="sxs-lookup"><span data-stu-id="da00f-156">A Registry entry contains the configuration.</span></span>|  
|<span data-ttu-id="da00f-157">Variable de package parent</span><span class="sxs-lookup"><span data-stu-id="da00f-157">Parent package variable</span></span>|<span data-ttu-id="da00f-158">Une variable dans le package contient la configuration.</span><span class="sxs-lookup"><span data-stu-id="da00f-158">A variable in the package contains the configuration.</span></span> <span data-ttu-id="da00f-159">Ce type de configuration est généralement utilisé pour mettre à jour les propriétés dans les packages enfants.</span><span class="sxs-lookup"><span data-stu-id="da00f-159">This configuration type is typically used to update properties in child packages.</span></span>|  
|<span data-ttu-id="da00f-160">Table [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da00f-160">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table</span></span>|<span data-ttu-id="da00f-161">Une table d'une base de données [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] contient la configuration.</span><span class="sxs-lookup"><span data-stu-id="da00f-161">A table in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database contains the configuration.</span></span> <span data-ttu-id="da00f-162">La table peut inclure plusieurs configurations.</span><span class="sxs-lookup"><span data-stu-id="da00f-162">The table can include multiple configurations.</span></span>|  
  
### <a name="xml-configuration-files"></a><span data-ttu-id="da00f-163">Fichiers de configuration XML</span><span class="sxs-lookup"><span data-stu-id="da00f-163">XML Configuration Files</span></span>  
 <span data-ttu-id="da00f-164">Si vous sélectionnez le type de configuration **Fichier de configuration XML** , vous pouvez créer un nouveau fichier de configuration, réutiliser un fichier existant et ajouter de nouvelles configurations, ou réutiliser un fichier existant en remplaçant son contenu.</span><span class="sxs-lookup"><span data-stu-id="da00f-164">If you select the **XML configuration file** configuration type, you can create a new configuration file, reuse an existing file and add new configurations, or reuse an existing file but overwrite existing file content.</span></span>  
  
 <span data-ttu-id="da00f-165">Un fichier de configuration XML est composé de deux sections :</span><span class="sxs-lookup"><span data-stu-id="da00f-165">An XML configuration file includes two sections:</span></span>  
  
-   <span data-ttu-id="da00f-166">Un en-tête qui contient des informations sur le fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="da00f-166">A heading that contains information about the configuration file.</span></span> <span data-ttu-id="da00f-167">Cet élément comprend des attributs tels que la date de création du fichier et le nom de la personne qui a généré le fichier.</span><span class="sxs-lookup"><span data-stu-id="da00f-167">This element includes attributes such as when the file was created and the name of the person who generated the file.</span></span>  
  
-   <span data-ttu-id="da00f-168">Les éléments de configuration qui contiennent des informations sur chaque configuration.</span><span class="sxs-lookup"><span data-stu-id="da00f-168">Configuration elements that contain information about each configuration.</span></span> <span data-ttu-id="da00f-169">Cet élément comprend des attributs tels que le chemin d'accès de la propriété et la valeur configurée de la propriété.</span><span class="sxs-lookup"><span data-stu-id="da00f-169">This element includes attributes such as the property path and the configured value of a property.</span></span>  
  
 <span data-ttu-id="da00f-170">Le code XML suivant présente la syntaxe d'un fichier de configuration XML.</span><span class="sxs-lookup"><span data-stu-id="da00f-170">The following XML code demonstrates the syntax of an XML configuration file.</span></span> <span data-ttu-id="da00f-171">Cet exemple montre une configuration de la propriété Valeur d’une variable de type entier nommée `MyVar`.</span><span class="sxs-lookup"><span data-stu-id="da00f-171">This example shows a configuration for the Value property of an integer variable named `MyVar`.</span></span>  
  
```  
<?xml version="1.0"?>  
<DTSConfiguration>  
   <DTSConfigurationHeading>  
      <DTSConfigurationFileInfo  
          GeneratedBy="DomainName\UserName"  
          GeneratedFromPackageName="Package"  
          GeneratedFromPackageID="{2AF06766-817A-4E28-9878-0DE37A150648}"  
          GeneratedDate="2/01/2005 5:58:09 PM"/>  
   </DTSConfigurationHeading>  
   <Configuration ConfiguredType="Property" Path="\Package.Variables[User::MyVar].Value" ValueType="Int32">  
      <ConfiguredValue>0</ConfiguredValue>  
   </Configuration>  
</DTSConfiguration>  
  
```  
  
### <a name="registry-entry"></a><span data-ttu-id="da00f-172">Entrée de Registre</span><span class="sxs-lookup"><span data-stu-id="da00f-172">Registry Entry</span></span>  
 <span data-ttu-id="da00f-173">Si vous souhaitez utiliser une entrée de Registre pour stocker la configuration, vous pouvez utiliser une clé existante ou créer une nouvelle clé dans HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="da00f-173">If you want to use a Registry entry to store the configuration, you can either use an existing key or create a new key in HKEY_CURRENT_USER.</span></span> <span data-ttu-id="da00f-174">La clé de Registre que vous utilisez doit contenir une valeur nommée `Value`.</span><span class="sxs-lookup"><span data-stu-id="da00f-174">The Registry key that you use must have a value named `Value`.</span></span> <span data-ttu-id="da00f-175">Cette valeur peut être de type DWORD ou une chaîne.</span><span class="sxs-lookup"><span data-stu-id="da00f-175">The value can be a DWORD or a string.</span></span>  
  
 <span data-ttu-id="da00f-176">Si vous sélectionnez le type de configuration **Entrée de Registre** , tapez le nom de la clé de Registre dans la zone d'entrée de Registre.</span><span class="sxs-lookup"><span data-stu-id="da00f-176">If you select the **Registry entry** configuration type, you type the name of the Registry key in the Registry entry box.</span></span> <span data-ttu-id="da00f-177">Le format est \<registry key>.</span><span class="sxs-lookup"><span data-stu-id="da00f-177">The format is \<registry key>.</span></span> <span data-ttu-id="da00f-178">Si vous souhaitez utiliser une clé de Registre qui n’est pas à la racine de HKEY_CURRENT_USER, utilisez le format \<Registry key\registry key\\...> pour identifier la clé.</span><span class="sxs-lookup"><span data-stu-id="da00f-178">If you want to use a Registry key that is not at the root of HKEY_CURRENT_USER, use the format \<Registry key\registry key\\...> to identify the key.</span></span> <span data-ttu-id="da00f-179">Par exemple, pour utiliser la clé MyPackage située dans SSISPackages, tapez `SSISPackages\MyPackage`.</span><span class="sxs-lookup"><span data-stu-id="da00f-179">For example, to use the MyPackage key located in SSISPackages, type `SSISPackages\MyPackage`.</span></span>  
  
### <a name="sql-server"></a><span data-ttu-id="da00f-180">SQL Server</span><span class="sxs-lookup"><span data-stu-id="da00f-180">SQL Server</span></span>  
 <span data-ttu-id="da00f-181">Si vous sélectionnez le type de configuration **SQL Server** , vous spécifiez la connexion à la base de données [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] dans laquelle vous voulez stocker les configurations.</span><span class="sxs-lookup"><span data-stu-id="da00f-181">If you select the **SQL Server** configuration type, you specify the connection to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database in which you want to store the configurations.</span></span> <span data-ttu-id="da00f-182">Vous pouvez enregistrer les configurations dans une table existante ou créer une nouvelle table dans la base de données spécifiée.</span><span class="sxs-lookup"><span data-stu-id="da00f-182">You can save the configurations to an existing table or create a new table in the specified database.</span></span>  
  
 <span data-ttu-id="da00f-183">L'instruction SQL suivante montre l'instruction CREATE TABLE par défaut fournie par l'Assistant Configuration de package.</span><span class="sxs-lookup"><span data-stu-id="da00f-183">The following SQL statement shows the default CREATE TABLE statement that the Package Configuration Wizard provides.</span></span>  
  
```  
CREATE TABLE [dbo].[SSIS Configurations]  
(  
ConfigurationFilter NVARCHAR(255) NOT NULL,  
ConfiguredValue NVARCHAR(255) NULL,  
PackagePath NVARCHAR(255) NOT NULL,  
ConfiguredValueType NVARCHAR(20) NOT NULL  
)  
  
```  
  
 <span data-ttu-id="da00f-184">Le nom que vous donnez à la configuration est la valeur stockée dans la colonne **ConfigurationFilter** .</span><span class="sxs-lookup"><span data-stu-id="da00f-184">The name that you provide for the configuration is the value stored in the **ConfigurationFilter** column.</span></span>  
  
## <a name="direct-and-indirect-configurations"></a><span data-ttu-id="da00f-185">Configurations directes et indirectes</span><span class="sxs-lookup"><span data-stu-id="da00f-185">Direct and Indirect Configurations</span></span>  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="da00f-186">fournit des configurations directes et indirectes.</span><span class="sxs-lookup"><span data-stu-id="da00f-186">provides direct and indirect configurations.</span></span> <span data-ttu-id="da00f-187">Si vous spécifiez directement les configurations, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] crée un lien direct entre l'élément de configuration et la propriété de l'objet package.</span><span class="sxs-lookup"><span data-stu-id="da00f-187">If you specify configurations directly, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] creates a direct link between the configuration item and the package object property.</span></span> <span data-ttu-id="da00f-188">Les configurations directes sont un meilleur choix lorsque l'emplacement de la source ne change pas.</span><span class="sxs-lookup"><span data-stu-id="da00f-188">Direct configurations are a better choice when the location of the source does not change.</span></span> <span data-ttu-id="da00f-189">Par exemple, si vous êtes sûr que tous les déploiements dans le package utilisent le même chemin d'accès de fichier, vous pouvez spécifier un fichier de configuration XML.</span><span class="sxs-lookup"><span data-stu-id="da00f-189">For example, if you are sure that all deployments in the package use the same file path, you can specify an XML configuration file.</span></span>  
  
 <span data-ttu-id="da00f-190">Les configurations indirectes utilisent des variables d'environnement.</span><span class="sxs-lookup"><span data-stu-id="da00f-190">Indirect configurations use environment variables.</span></span> <span data-ttu-id="da00f-191">Au lieu de spécifier directement le paramètre de configuration, la configuration pointe vers une variable d'environnement, qui contient à son tour la valeur de configuration.</span><span class="sxs-lookup"><span data-stu-id="da00f-191">Instead of specifying the configuration setting directly, the configuration points to an environment variable, which in turn contains the configuration value.</span></span> <span data-ttu-id="da00f-192">L'utilisation de configurations indirectes est un meilleur choix lorsque l'emplacement de la configuration peut changer pour chaque déploiement d'un package.</span><span class="sxs-lookup"><span data-stu-id="da00f-192">Using indirect configurations is a better choice when the location of the configuration can change for each deployment of a package.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="da00f-193">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="da00f-193">Related Tasks</span></span>  
 [<span data-ttu-id="da00f-194">Créer des configurations de package</span><span class="sxs-lookup"><span data-stu-id="da00f-194">Create Package Configurations</span></span>](../../2014/integration-services/create-package-configurations.md)  
  
## <a name="related-content"></a><span data-ttu-id="da00f-195">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="da00f-195">Related Content</span></span>  
  
-   <span data-ttu-id="da00f-196">Article technique, [Understanding Integration Services Package Configurations](https://go.microsoft.com/fwlink/?LinkId=165643), sur msdn.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="da00f-196">Technical article, [Understanding Integration Services Package Configurations](https://go.microsoft.com/fwlink/?LinkId=165643), on msdn.microsoft.com</span></span>  
  
-   <span data-ttu-id="da00f-197">Entrée de blog, [création de packages dans le code-configurations de package](https://go.microsoft.com/fwlink/?LinkId=217663), sur www.SQLIS.com.</span><span class="sxs-lookup"><span data-stu-id="da00f-197">Blog entry, [Creating packages in code - Package Configurations](https://go.microsoft.com/fwlink/?LinkId=217663), on www.sqlis.com.</span></span>  
  
-   <span data-ttu-id="da00f-198">Entrée de blog, [exemple d’API-ajouter par programmation un fichier de configuration à un package](https://go.microsoft.com/fwlink/?LinkId=217664), sur blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="da00f-198">Blog entry, [API Sample - Programmatically add a configuration file to a package](https://go.microsoft.com/fwlink/?LinkId=217664), on blogs.msdn.com.</span></span>  
  
  
