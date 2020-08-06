---
title: Informations de référence sur l’interface utilisateur de l’Assistant Configuration de package | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.configwizard.selectobjects.f1
- sql12.dts.configwizard.selecconfigtype.f1
- sql12.dts.configwizard.finishdtsconfiguration.f1
- sql12.dts.configwizard.welcome.f1
ms.assetid: adca6938-6d5a-40ec-950e-dceb79d044fe
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 222c5f58ca4e942dd23909b433ab346c500fceed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613539"
---
# <a name="package-configuration-wizard-ui-reference"></a><span data-ttu-id="e4bbb-102">Référence de l'interface utilisateur de l'Assistant Configuration de package</span><span class="sxs-lookup"><span data-stu-id="e4bbb-102">Package Configuration Wizard UI Reference</span></span>
  <span data-ttu-id="e4bbb-103">**L’Assistant Configuration de package** vous permet de créer des configurations chargées de mettre à jour les propriétés d’un package [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ainsi que les objets qui s’y rattachent au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-103">Use the **Package Configuration Wizard** to create configurations that update the properties of an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package and its objects at run time.</span></span> <span data-ttu-id="e4bbb-104">Cet Assistant s’exécute quand vous ajoutez une nouvelle configuration ou modifiez une configuration existante dans la boîte de dialogue **Bibliothèque des configurations du package** .</span><span class="sxs-lookup"><span data-stu-id="e4bbb-104">This wizard runs when you add a new configuration or modify an existing one in the **Package Configurations Organizer** dialog box.</span></span> <span data-ttu-id="e4bbb-105">Pour ouvrir la boîte de dialogue **Bibliothèque des configurations du package** , sélectionnez **Configurations du package** dans le menu **SSIS** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4bbb-105">To open the **Package Configurations Organizer** dialog box, select **Package Configurations** on the **SSIS** menu in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="e4bbb-106">Pour plus d’informations, consultez [Créer des configurations de package](../../2014/integration-services/create-package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="e4bbb-106">For more information, see [Create Package Configurations](../../2014/integration-services/create-package-configurations.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e4bbb-107">Des configurations sont disponibles pour le modèle de déploiement de package.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-107">Configurations are available for the package deployment model.</span></span> <span data-ttu-id="e4bbb-108">Les paramètres sont utilisés à la place des configurations pour le modèle de déploiement de projet.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-108">Parameters are used in place of configurations for the project deployment model.</span></span> <span data-ttu-id="e4bbb-109">Le modèle de déploiement de projet vous permet de déployer des projets [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sur le serveur [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e4bbb-109">The project deployment model enables you to deploy [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="e4bbb-110">Pour plus d'informations sur les modèles de déploiement, consultez [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="e4bbb-110">For more information about the deployment models, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="e4bbb-111">Les sections suivantes décrivent les pages de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-111">The following sections describe pages of the Wizard.</span></span>  
  
## <a name="welcome-to-the-package-configuration-wizard-page"></a><span data-ttu-id="e4bbb-112">Page Assistant Configuration de package</span><span class="sxs-lookup"><span data-stu-id="e4bbb-112">Welcome to the Package Configuration Wizard Page</span></span>  
 <span data-ttu-id="e4bbb-113">**L’Assistant de configuration de SSIS** vous permet de créer des configurations chargées de mettre à jour les propriétés d’un package ainsi que les objets qui s’y rattachent au moment de l’exécution du programme.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-113">Use the **SSIS Configuration Wizard** to create configurations that update the properties of a package and its objects at run time.</span></span>  
  
### <a name="options"></a><span data-ttu-id="e4bbb-114">Options</span><span class="sxs-lookup"><span data-stu-id="e4bbb-114">Options</span></span>  
 <span data-ttu-id="e4bbb-115">**Ne plus afficher cette page**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-115">**Don't show this page again**</span></span>  
 <span data-ttu-id="e4bbb-116">Option permettant d'ignorer cette page d'accueil la prochaine fois que vous ouvrez l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-116">Skip the welcome page the next time you open the wizard.</span></span>  
  
 <span data-ttu-id="e4bbb-117">**Next**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-117">**Next**</span></span>  
 <span data-ttu-id="e4bbb-118">Permet de passer à la page suivante de l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-118">Go the next page in the wizard.</span></span>  
  
## <a name="select-configuration-type-page"></a><span data-ttu-id="e4bbb-119">Page Sélectionner le type de configuration</span><span class="sxs-lookup"><span data-stu-id="e4bbb-119">Select Configuration Type Page</span></span>  
 <span data-ttu-id="e4bbb-120">La page **Sélectionner le type de configuration** permet de spécifier le type de configuration à créer.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-120">Use the **Select Configuration Type** page to specify the type of configuration to create.</span></span>  
  
 <span data-ttu-id="e4bbb-121">Si vous souhaitez obtenir des informations supplémentaires pour déterminer quel type de configuration utiliser, consultez [Configurations de package](../../2014/integration-services/package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="e4bbb-121">If you need additional information to determine which type of configuration to use, see [Package Configurations](../../2014/integration-services/package-configurations.md).</span></span>  
  
### <a name="static-options"></a><span data-ttu-id="e4bbb-122">Options statiques</span><span class="sxs-lookup"><span data-stu-id="e4bbb-122">Static Options</span></span>  
 <span data-ttu-id="e4bbb-123">**Type de configuration**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-123">**Configuration type**</span></span>  
 <span data-ttu-id="e4bbb-124">Sélectionnez le type de source dans lequel stocker la configuration, à l'aide des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="e4bbb-124">Select the type of source in which to store the configuration, using the following options:</span></span>  
  
|<span data-ttu-id="e4bbb-125">Valeur</span><span class="sxs-lookup"><span data-stu-id="e4bbb-125">Value</span></span>|<span data-ttu-id="e4bbb-126">Description</span><span class="sxs-lookup"><span data-stu-id="e4bbb-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e4bbb-127">**Fichier de configuration XML**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-127">**XML configuration file**</span></span>|<span data-ttu-id="e4bbb-128">Stocke la configuration sous forme de fichier XML.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-128">Store the configuration as an XML file.</span></span> <span data-ttu-id="e4bbb-129">Si cette valeur est sélectionnée, les options dynamiques s’affichent dans la section **Type de configuration**.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-129">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
|<span data-ttu-id="e4bbb-130">**Variable d'environnement**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-130">**Environment variable**</span></span>|<span data-ttu-id="e4bbb-131">Stocke la configuration dans une des variables d'environnement.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-131">Store the configuration in one of the environment variables.</span></span> <span data-ttu-id="e4bbb-132">Si cette valeur est sélectionnée, les options dynamiques s’affichent dans la section **Type de configuration**.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-132">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
|<span data-ttu-id="e4bbb-133">**Entrée de Registre**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-133">**Registry entry**</span></span>|<span data-ttu-id="e4bbb-134">Stocke la configuration dans le Registre.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-134">Store the configuration in the Registry.</span></span> <span data-ttu-id="e4bbb-135">Si cette valeur est sélectionnée, les options dynamiques s’affichent dans la section **Type de configuration**.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-135">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
|<span data-ttu-id="e4bbb-136">**Variable de package parent**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-136">**Parent package variable**</span></span>|<span data-ttu-id="e4bbb-137">Stocke la configuration en tant que variable dans le package qui contient la tâche.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-137">Store the configuration as a variable in the package that contains the task.</span></span>  <span data-ttu-id="e4bbb-138">Si cette valeur est sélectionnée, les options dynamiques s’affichent dans la section **Type de configuration**.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-138">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
|<span data-ttu-id="e4bbb-139">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-139">**SQL Server**</span></span>|<span data-ttu-id="e4bbb-140">Stocke la configuration dans une table de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4bbb-140">Store the configuration in a table in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e4bbb-141">Si cette valeur est sélectionnée, les options dynamiques s’affichent dans la section **Type de configuration**.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-141">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
  
 <span data-ttu-id="e4bbb-142">**Next**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-142">**Next**</span></span>  
 <span data-ttu-id="e4bbb-143">Affiche la page suivante de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-143">View the next page in the wizard sequence.</span></span>  
  
### <a name="dynamic-options"></a><span data-ttu-id="e4bbb-144">Options dynamiques</span><span class="sxs-lookup"><span data-stu-id="e4bbb-144">Dynamic Options</span></span>  
  
#### <a name="configuration-type-option--xml-configuration-file"></a><span data-ttu-id="e4bbb-145">Option Type de configuration = Fichier de configuration XML</span><span class="sxs-lookup"><span data-stu-id="e4bbb-145">Configuration Type Option = XML Configuration File</span></span>  
 <span data-ttu-id="e4bbb-146">**Spécifier directement les paramètres de configuration**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-146">**Specify configuration settings directly**</span></span>  
 <span data-ttu-id="e4bbb-147">Permet de spécifier directement les paramètres.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-147">Use to specify settings directly.</span></span>  
  
|<span data-ttu-id="e4bbb-148">Valeur</span><span class="sxs-lookup"><span data-stu-id="e4bbb-148">Value</span></span>|<span data-ttu-id="e4bbb-149">Description</span><span class="sxs-lookup"><span data-stu-id="e4bbb-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e4bbb-150">**Nom du fichier de configuration**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-150">**Configuration file name**</span></span>|<span data-ttu-id="e4bbb-151">Tapez le chemin d'accès du fichier de configuration généré par l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-151">Type the path of the configuration file that the wizard generates.</span></span>|  
|<span data-ttu-id="e4bbb-152">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-152">**Browse**</span></span>|<span data-ttu-id="e4bbb-153">La boîte de dialogue **Sélectionner l’emplacement du fichier de configuration** permet de spécifier le chemin d’accès au fichier de configuration généré par l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-153">Use the **Select Configuration File Location** dialog box to specify the path of the configuration file that the wizard generates.</span></span> <span data-ttu-id="e4bbb-154">Si le fichier n'existe pas, l'Assistant le crée.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-154">If the file does not exist, it is created by the wizard.</span></span>|  
  
 <span data-ttu-id="e4bbb-155">**L'emplacement de la configuration est stocké dans une variable d'environnement**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-155">**Configuration location is stored in an environment variable**</span></span>  
 <span data-ttu-id="e4bbb-156">Permet de spécifier la variable d’environnement dans laquelle stocker la configuration.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-156">Use to specify the environment variable in which to store the configuration.</span></span>  
  
|<span data-ttu-id="e4bbb-157">Valeur</span><span class="sxs-lookup"><span data-stu-id="e4bbb-157">Value</span></span>|<span data-ttu-id="e4bbb-158">Description</span><span class="sxs-lookup"><span data-stu-id="e4bbb-158">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e4bbb-159">**Variable d'environnement**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-159">**Environment variable**</span></span>|<span data-ttu-id="e4bbb-160">Permet de sélectionner une variable d'environnement dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-160">Select an environment variable from the list.</span></span>|  
  
#### <a name="configuration-type-option--environment-variable"></a><span data-ttu-id="e4bbb-161">Option Type de configuration = Variable d'environnement</span><span class="sxs-lookup"><span data-stu-id="e4bbb-161">Configuration Type Option = Environment Variable</span></span>  
 <span data-ttu-id="e4bbb-162">**Variable d'environnement**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-162">**Environment variable**</span></span>  
 <span data-ttu-id="e4bbb-163">Permet de sélectionner la variable d'environnement qui contient les informations de configuration.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-163">Select the environment variable that contains the configuration information.</span></span>  
  
#### <a name="configuration-type-option--registry-entry"></a><span data-ttu-id="e4bbb-164">Option Type de configuration = Entrée de Registre</span><span class="sxs-lookup"><span data-stu-id="e4bbb-164">Configuration Type Option = Registry Entry</span></span>  
 <span data-ttu-id="e4bbb-165">**Spécifier directement les paramètres de configuration**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-165">**Specify configuration settings directly**</span></span>  
 <span data-ttu-id="e4bbb-166">Permet de spécifier directement les paramètres.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-166">Use to specify settings directly.</span></span>  
  
|<span data-ttu-id="e4bbb-167">Valeur</span><span class="sxs-lookup"><span data-stu-id="e4bbb-167">Value</span></span>|<span data-ttu-id="e4bbb-168">Description</span><span class="sxs-lookup"><span data-stu-id="e4bbb-168">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e4bbb-169">**Entrée de Registre**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-169">**Registry entry**</span></span>|<span data-ttu-id="e4bbb-170">Tapez la clé de Registre qui contient les informations de configuration.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-170">Type the Registry key that contains the configuration information.</span></span> <span data-ttu-id="e4bbb-171">Le format est \<registry key>.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-171">The format is \<registry key>.</span></span><br /><br /> <span data-ttu-id="e4bbb-172">La clé de Registre doit déjà exister dans HKEY_CURRENT_USER et porter une valeur nommée Value.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-172">The Registry key must already exist in HKEY_CURRENT_USER and have a value named Value.</span></span> <span data-ttu-id="e4bbb-173">Cette valeur peut être de type DWORD ou une chaîne.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-173">The value can be a DWORD or a string.</span></span><br /><br /> <span data-ttu-id="e4bbb-174">Si vous souhaitez utiliser une clé de Registre qui n’est pas à la racine de HKEY_CURRENT_USER, utilisez le format \<Registry key\registry key\\...> pour identifier la clé.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-174">If you want to use a Registry key is not at the root of HKEY_CURRENT_USER, use the format \<Registry key\registry key\\...> to identify the key.</span></span>|  
  
 <span data-ttu-id="e4bbb-175">**L'emplacement de la configuration est stocké dans une variable d'environnement**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-175">**Configuration location is stored in an environment variable**</span></span>  
 <span data-ttu-id="e4bbb-176">Permet de spécifier la variable d’environnement dans laquelle stocker la configuration.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-176">Use to specify the environment variable to store the configuration in.</span></span>  
  
|<span data-ttu-id="e4bbb-177">Valeur</span><span class="sxs-lookup"><span data-stu-id="e4bbb-177">Value</span></span>|<span data-ttu-id="e4bbb-178">Description</span><span class="sxs-lookup"><span data-stu-id="e4bbb-178">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e4bbb-179">**Variable d'environnement**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-179">**Environment variable**</span></span>|<span data-ttu-id="e4bbb-180">Permet de sélectionner une variable d'environnement dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-180">Select an environment variable from the list.</span></span>|  
  
#### <a name="configuration-type-option--parent-package-variable"></a><span data-ttu-id="e4bbb-181">Option Type de configuration = Variable de package parent</span><span class="sxs-lookup"><span data-stu-id="e4bbb-181">Configuration Type Option = Parent Package Variable</span></span>  
 <span data-ttu-id="e4bbb-182">**Spécifier directement les paramètres de configuration**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-182">**Specify configuration settings directly**</span></span>  
 <span data-ttu-id="e4bbb-183">Permet de spécifier directement les paramètres.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-183">Use to specify settings directly.</span></span>  
  
|<span data-ttu-id="e4bbb-184">Valeur</span><span class="sxs-lookup"><span data-stu-id="e4bbb-184">Value</span></span>|<span data-ttu-id="e4bbb-185">Description</span><span class="sxs-lookup"><span data-stu-id="e4bbb-185">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e4bbb-186">**Variable parent**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-186">**Parent variable**</span></span>|<span data-ttu-id="e4bbb-187">Permet de spécifier la variable dans le package parent qui contient les informations de configuration.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-187">Specify the variable in the parent package that contains the configuration information.</span></span>|  
  
 <span data-ttu-id="e4bbb-188">**L'emplacement de la configuration est stocké dans une variable d'environnement**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-188">**Configuration location is stored in an environment variable**</span></span>  
 <span data-ttu-id="e4bbb-189">Permet de spécifier la variable d’environnement dans laquelle stocker la configuration.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-189">Use to specify the environment variable that stores the configuration.</span></span>  
  
|<span data-ttu-id="e4bbb-190">Valeur</span><span class="sxs-lookup"><span data-stu-id="e4bbb-190">Value</span></span>|<span data-ttu-id="e4bbb-191">Description</span><span class="sxs-lookup"><span data-stu-id="e4bbb-191">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e4bbb-192">**Variable d'environnement**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-192">**Environment variable**</span></span>|<span data-ttu-id="e4bbb-193">Permet de sélectionner une variable d'environnement dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-193">Select an environment variable from the list.</span></span>|  
  
#### <a name="configuration-type-options--sql-server"></a><span data-ttu-id="e4bbb-194">Options Type de configuration = SQL Server</span><span class="sxs-lookup"><span data-stu-id="e4bbb-194">Configuration Type Options = SQL Server</span></span>  
 <span data-ttu-id="e4bbb-195">**Spécifier directement les paramètres de configuration**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-195">**Specify configuration settings directly**</span></span>  
 <span data-ttu-id="e4bbb-196">Permet de spécifier directement les paramètres.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-196">Use to specify settings directly.</span></span>  
  
|<span data-ttu-id="e4bbb-197">Valeur</span><span class="sxs-lookup"><span data-stu-id="e4bbb-197">Value</span></span>|<span data-ttu-id="e4bbb-198">Description</span><span class="sxs-lookup"><span data-stu-id="e4bbb-198">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e4bbb-199">**Connection**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-199">**Connection**</span></span>|<span data-ttu-id="e4bbb-200">Permet de sélectionner une connexion dans la liste ou de cliquer sur **Nouvelle** pour créer une connexion.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-200">Select a connection from the list, or click **New** to create a new connection.</span></span>|  
|<span data-ttu-id="e4bbb-201">**Table de configuration**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-201">**Configuration table**</span></span>|<span data-ttu-id="e4bbb-202">Permet de sélectionner une table existante ou de cliquer sur **Nouvelle** pour écrire une instruction SQL qui crée une table.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-202">Select an existing table, or click **New** to write a SQL statement that creates a new table.</span></span>|  
|<span data-ttu-id="e4bbb-203">**Filtre de la configuration**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-203">**Configuration filter**</span></span>|<span data-ttu-id="e4bbb-204">Permet de sélectionner le nom d'une configuration existante ou de taper un nouveau nom.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-204">Select an existing configuration name or type a new name.</span></span><br /><br /> <span data-ttu-id="e4bbb-205">Un grand nombre de configurations SQL Server peuvent être stockées dans la même table et chacune d'entre elles peut inclure plusieurs éléments de configuration.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-205">Many SQL Server configurations can be stored in the same table, and each configuration can include multiple configuration items.</span></span><br /><br /> <span data-ttu-id="e4bbb-206">La valeur définie par l'utilisateur est stockée dans la table pour identifier les éléments de configuration qui appartiennent à une configuration particulière.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-206">This user-defined value is stored in the table to identify configuration items that belong to a particular configuration</span></span>|  
  
 <span data-ttu-id="e4bbb-207">**L'emplacement de la configuration est stocké dans une variable d'environnement**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-207">**Configuration location is stored in an environment variable**</span></span>  
 <span data-ttu-id="e4bbb-208">Permet de spécifier la variable d'environnement dans laquelle stocker la configuration.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-208">Use to specify the environment variable where the configuration is stored.</span></span>  
  
|<span data-ttu-id="e4bbb-209">Valeur</span><span class="sxs-lookup"><span data-stu-id="e4bbb-209">Value</span></span>|<span data-ttu-id="e4bbb-210">Description</span><span class="sxs-lookup"><span data-stu-id="e4bbb-210">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e4bbb-211">**Variable d'environnement**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-211">**Environment variable**</span></span>|<span data-ttu-id="e4bbb-212">Permet de sélectionner une variable d'environnement dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-212">Select an environment variable from the list.</span></span>|  
  
## <a name="select-objects-to-export-page"></a><span data-ttu-id="e4bbb-213">Page Sélectionner des objets à exporter</span><span class="sxs-lookup"><span data-stu-id="e4bbb-213">Select Objects to Export Page</span></span>  
 <span data-ttu-id="e4bbb-214">Utilisez la page **Sélectionner la propriété cible ou Sélectionner les propriétés à exporter** pour définir les propriétés des objets que contient la configuration.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-214">Use the **Select Target Property or Select Properties to Export** page to specify the object properties that the configuration contains.</span></span> <span data-ttu-id="e4bbb-215">La sélection de plusieurs propriétés n'est possible que si vous sélectionnez le type de configuration XML.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-215">The ability to select multiple properties is available only if you select the XML configuration type.</span></span>  
  
### <a name="options"></a><span data-ttu-id="e4bbb-216">Options</span><span class="sxs-lookup"><span data-stu-id="e4bbb-216">Options</span></span>  
 <span data-ttu-id="e4bbb-217">**Objets**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-217">**Objects**</span></span>  
 <span data-ttu-id="e4bbb-218">Développe la hiérarchie du package et sélectionne les propriétés à exporter.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-218">Expand the package hierarchy and select the properties to export.</span></span>  
  
 <span data-ttu-id="e4bbb-219">**Attributs de la propriété**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-219">**Property attributes**</span></span>  
 <span data-ttu-id="e4bbb-220">Affiche les attributs d'une propriété.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-220">View the attributes of a property.</span></span>  
  
 <span data-ttu-id="e4bbb-221">**Next**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-221">**Next**</span></span>  
 <span data-ttu-id="e4bbb-222">Permet de passer à la page suivante de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-222">Go to the next page in the wizard.</span></span>  
  
## <a name="completing-the-wizard-page"></a><span data-ttu-id="e4bbb-223">Page Fin de l’Assistant</span><span class="sxs-lookup"><span data-stu-id="e4bbb-223">Completing the Wizard Page</span></span>  
 <span data-ttu-id="e4bbb-224">Utilisez la page **Fin de l’Assistant** pour nommer les paramètres de configuration et d’affichage utilisés par l’Assistant pour créer la configuration.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-224">Use the **Completing the Wizard** page to provide a name for the configuration and view settings used by the wizard to create the configuration.</span></span> <span data-ttu-id="e4bbb-225">Quand l’Assistant est terminé, la **Bibliothèque des configurations du package** affiche la liste de toutes les configurations du package.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-225">After the wizard completes, the **Package Configurations Organizer** is displayed, which lists all configurations for the package.</span></span>  
  
### <a name="options"></a><span data-ttu-id="e4bbb-226">Options</span><span class="sxs-lookup"><span data-stu-id="e4bbb-226">Options</span></span>  
 <span data-ttu-id="e4bbb-227">**Nom de la configuration**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-227">**Configuration name**</span></span>  
 <span data-ttu-id="e4bbb-228">Tapez le nom de la configuration.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-228">Type the name of the configuration.</span></span>  
  
 <span data-ttu-id="e4bbb-229">**Préversion**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-229">**Preview**</span></span>  
 <span data-ttu-id="e4bbb-230">Affiche les paramètres utilisés par l'Assistant pour créer la configuration.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-230">View the settings used by the wizard to create the configuration.</span></span>  
  
 <span data-ttu-id="e4bbb-231">**Terminer**</span><span class="sxs-lookup"><span data-stu-id="e4bbb-231">**Finish**</span></span>  
 <span data-ttu-id="e4bbb-232">Crée la configuration et quitte **l’Assistant Configuration de package**.</span><span class="sxs-lookup"><span data-stu-id="e4bbb-232">Create the configuration and exit the **Package Configuration Wizard**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4bbb-233">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e4bbb-233">See Also</span></span>  
 [<span data-ttu-id="e4bbb-234">Créer des configurations de package</span><span class="sxs-lookup"><span data-stu-id="e4bbb-234">Create Package Configurations</span></span>](../../2014/integration-services/create-package-configurations.md)  
  
  
