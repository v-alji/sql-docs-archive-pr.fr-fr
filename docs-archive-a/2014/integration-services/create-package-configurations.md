---
title: Créer des configurations de package | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Integration Services packages, configurations
- Package Configurations Organizer dialog box
- SSIS packages, configurations
- Integration Services packages, configurations
- configurations [Integration Services]
- packages [Integration Services], configurations
- deploying packages [Integration Services], configurations
ms.assetid: 91ac0347-f908-44f5-bd3d-115790223af4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 58c93242c9ef51a5e00076bd367e46b43187098e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604059"
---
# <a name="create-package-configurations"></a><span data-ttu-id="92712-102">Créer des configurations de package</span><span class="sxs-lookup"><span data-stu-id="92712-102">Create Package Configurations</span></span>
  <span data-ttu-id="92712-103">Vous pouvez créer des configurations de package à l'aide de la boîte de dialogue **Bibliothèque des configurations du package** et de l'Assistant Configuration de package.</span><span class="sxs-lookup"><span data-stu-id="92712-103">You create package configurations by using the **Package Configuration Organizer** dialog box and the Package Configuration Wizard.</span></span> <span data-ttu-id="92712-104">Pour accéder à ces outils, cliquez sur **Configurations du package** dans le menu **SSIS** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92712-104">To access these tools, click **Package Configurations** on the **SSIS** menu in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="92712-105">Vous pouvez également accéder à l' **organiseur de configuration de package**en cliquant sur le bouton de sélection en regard de la propriété de **configuration** .</span><span class="sxs-lookup"><span data-stu-id="92712-105">You can also access the **Package Configuration Organizer**, by clicking the ellipsis button next to the **Configuration** property.</span></span> <span data-ttu-id="92712-106">La propriété Configuration apparaît dans la fenêtre des propriétés du package.</span><span class="sxs-lookup"><span data-stu-id="92712-106">The Configuration property appears in the properties window for the package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="92712-107">Des configurations sont disponibles pour le modèle de déploiement de package.</span><span class="sxs-lookup"><span data-stu-id="92712-107">Configurations are available for the package deployment model.</span></span> <span data-ttu-id="92712-108">Les paramètres sont utilisés à la place des configurations pour le modèle de déploiement de projet.</span><span class="sxs-lookup"><span data-stu-id="92712-108">Parameters are used in place of configurations for the project deployment model.</span></span> <span data-ttu-id="92712-109">Le modèle de déploiement de projet vous permet de déployer des projets [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sur le serveur [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="92712-109">The project deployment model enables you to deploy [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="92712-110">Pour plus d'informations sur les modèles de déploiement, consultez [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="92712-110">For more information about the deployment models, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="92712-111">Dans la boîte de dialogue **Bibliothèque des configurations du package** , vous pouvez permettre aux packages d'utiliser des configurations, ajouter et supprimer des configurations et définir l'ordre souhaité dans lequel sont chargées les configurations.</span><span class="sxs-lookup"><span data-stu-id="92712-111">In the **Package Configuration Organizer** dialog box, you can enable packages to use configurations, add and delete configurations, and set the preferred order in which configurations should be loaded.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="92712-112">Lorsque les configurations du package sont chargées dans l'ordre souhaité, le chargement est effectué du haut vers le bas de la liste affichée dans la boîte de dialogue **Bibliothèques des configurations du package** .</span><span class="sxs-lookup"><span data-stu-id="92712-112">When package configurations load in the preferred order, configurations load from the top of the list shown in the **Package Configuration Organizer** dialog box to the bottom of the list.</span></span> <span data-ttu-id="92712-113">Toutefois, au moment de l'exécution, il se peut que les configurations de package ne soient pas chargées dans l'ordre souhaité.</span><span class="sxs-lookup"><span data-stu-id="92712-113">However, at run time, package configurations might not load in the preferred order.</span></span> <span data-ttu-id="92712-114">Les configurations de package parent sont notamment chargées après les configurations d'autres types.</span><span class="sxs-lookup"><span data-stu-id="92712-114">In particular, parent package configurations load after configurations of other types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="92712-115">Si plusieurs configurations définissent la même propriété d'objet, la dernière valeur chargée est utilisée à l'exécution.</span><span class="sxs-lookup"><span data-stu-id="92712-115">If multiple configurations set the same object property, the value loaded last is used at run time.</span></span>  
  
 <span data-ttu-id="92712-116">À partir de la boîte de dialogue **Bibliothèque des configurations du package** , vous pouvez exécuter l'Assistant Configuration de package, qui vous guide à travers les étapes de création d'une configuration.</span><span class="sxs-lookup"><span data-stu-id="92712-116">From the **Package Configuration Organizer** dialog box, you run the Package Configuration Wizard, which guides you through the steps to create a configuration.</span></span> <span data-ttu-id="92712-117">Pour exécuter l'Assistant Configuration de package, ajoutez une nouvelle configuration dans la boîte de dialogue **Bibliothèque des configurations du package** ou modifiez une configuration existante.</span><span class="sxs-lookup"><span data-stu-id="92712-117">To run the Package Configuration Wizard, add a new configuration in the **Package Configurations Organizer** dialog box or edit an existing one.</span></span> <span data-ttu-id="92712-118">Sur les pages de l'Assistant, vous choisissez un type de configuration, vous choisissez si vous souhaitez accéder directement à la configuration ou utiliser des variables d'environnement, et vous sélectionnez les propriétés à enregistrer dans la configuration.</span><span class="sxs-lookup"><span data-stu-id="92712-118">On the wizard pages, you choose the configuration type, select whether you want to access the configuration directly or use environment variables, and select the properties to save in the configuration.</span></span>  
  
 <span data-ttu-id="92712-119">L'exemple suivant illustre les propriétés cibles d'une variable et d'un package telles qu'elles apparaissent dans la page Fin de l'Assistant de l'Assistant Configuration de package :</span><span class="sxs-lookup"><span data-stu-id="92712-119">The following example shows the target properties of a variable and a package as they appear on the Completing the Wizard page of the Package Configuration Wizard.:</span></span>  
  
 <span data-ttu-id="92712-120">\Package.Variables[User::TodaysDate].Properties[RaiseChangedEvent]</span><span class="sxs-lookup"><span data-stu-id="92712-120">\Package.Variables[User::TodaysDate].Properties[RaiseChangedEvent]</span></span>  
  
 <span data-ttu-id="92712-121">\Package.Properties[MaximumErrorCount]</span><span class="sxs-lookup"><span data-stu-id="92712-121">\Package.Properties[MaximumErrorCount]</span></span>  
  
 <span data-ttu-id="92712-122">\Package.Properties[LoggingMode]</span><span class="sxs-lookup"><span data-stu-id="92712-122">\Package.Properties[LoggingMode]</span></span>  
  
 <span data-ttu-id="92712-123">\Package.Properties[LocaleID]</span><span class="sxs-lookup"><span data-stu-id="92712-123">\Package.Properties[LocaleID]</span></span>  
  
 <span data-ttu-id="92712-124">\Package\My SQL Task.Variables[User::varTableName].Properties[Value]</span><span class="sxs-lookup"><span data-stu-id="92712-124">\Package\My SQL Task.Variables[User::varTableName].Properties[Value]</span></span>  
  
 <span data-ttu-id="92712-125">Dans cet exemple, la configuration met à jour ces propriétés :</span><span class="sxs-lookup"><span data-stu-id="92712-125">In this example, the configuration updates these properties:</span></span>  
  
-   <span data-ttu-id="92712-126">Propriété RaiseChangedEvent de la variable définie par l’utilisateur `TodaysDate`</span><span class="sxs-lookup"><span data-stu-id="92712-126">The RaiseChangedEvent property of user-defined variable, `TodaysDate`.</span></span>  
  
-   <span data-ttu-id="92712-127">Propriétés MaximumErrorCount, LoggingMode et LocaleID du package</span><span class="sxs-lookup"><span data-stu-id="92712-127">The MaximumErrorCount, LoggingMode, and LocaleID properties of the package.</span></span>  
  
-   <span data-ttu-id="92712-128">Propriété Value de la variable définie par l’utilisateur `varTableName`, dans la portée de la tâche My SQL Task</span><span class="sxs-lookup"><span data-stu-id="92712-128">The Value property of user-defined variable, `varTableName`, within scope of the task, My SQL Task.</span></span>  
  
 <span data-ttu-id="92712-129">La syntaxe « \Package » représente la racine, et les points (.) séparent les objets qui définissent le chemin d'accès de la propriété mise à jour par la configuration.</span><span class="sxs-lookup"><span data-stu-id="92712-129">The "\Package" represents the root, and periods (.) separate the objects that define the path to the property that the configuration updates.</span></span> <span data-ttu-id="92712-130">Les noms de variables et de propriétés figurent entre crochets.</span><span class="sxs-lookup"><span data-stu-id="92712-130">The names of variables and properties are enclosed in brackets.</span></span> <span data-ttu-id="92712-131">Le terme Package est toujours utilisé dans la configuration, quel que soit le nom du package ; toutefois, tous les autres objets indiqués dans le chemin d'accès portent leur nom défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="92712-131">The term Package is always used in configuration, regardless of the package name; however, all other objects in the path use their user-defined names.</span></span>  
  
 <span data-ttu-id="92712-132">Une fois l'Assistant terminé, la nouvelle configuration est ajoutée à la liste des configurations dans la boîte de dialogue **Bibliothèque des configurations du package** .</span><span class="sxs-lookup"><span data-stu-id="92712-132">After the wizard finishes, the new configuration is added to the configuration list in the **Package Configuration Organizer** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="92712-133">La dernière page de l'Assistant Configuration de package, Fin de l'Assistant, répertorie les propriétés cibles dans la configuration.</span><span class="sxs-lookup"><span data-stu-id="92712-133">The last page in the Package Configuration Wizard, Completing the Wizard, lists the target properties in the configuration.</span></span> <span data-ttu-id="92712-134">Si vous souhaitez mettre à jour des propriétés pendant l’exécution de packages à l’aide de l’utilitaire d’invite de commandes **dtexec** , vous pouvez générer les chaînes qui représentent les chemins d’accès aux propriétés en exécutant l’Assistant Configuration de package, puis les copier et les coller dans la fenêtre d’invite de commandes pour les utiliser avec l’option set de **dtexec**.</span><span class="sxs-lookup"><span data-stu-id="92712-134">If you want to update properties when you run packages by using the **dtexec** command prompt utility, you can generate the strings that represent the property paths by running the Package Configuration Wizard and then copy and paste them into the command prompt window for use with the set option of **dtexec.**</span></span>  
  
 <span data-ttu-id="92712-135">Le tableau suivant décrit les colonnes dans la liste des configurations de la boîte de dialogue **Bibliothèque des configurations du package** .</span><span class="sxs-lookup"><span data-stu-id="92712-135">The following table describes the columns in the configuration list in the **Package Configuration Organizer** dialog box.</span></span>  
  
|<span data-ttu-id="92712-136">Colonne</span><span class="sxs-lookup"><span data-stu-id="92712-136">Column</span></span>|<span data-ttu-id="92712-137">Description</span><span class="sxs-lookup"><span data-stu-id="92712-137">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="92712-138">**Nom de la configuration**</span><span class="sxs-lookup"><span data-stu-id="92712-138">**Configuration Name**</span></span>|<span data-ttu-id="92712-139">Le nom de la configuration.</span><span class="sxs-lookup"><span data-stu-id="92712-139">The name of the configuration.</span></span>|  
|<span data-ttu-id="92712-140">**Type de configuration**</span><span class="sxs-lookup"><span data-stu-id="92712-140">**Configuration Type**</span></span>|<span data-ttu-id="92712-141">Le type de la configuration.</span><span class="sxs-lookup"><span data-stu-id="92712-141">The configuration type.</span></span>|  
|<span data-ttu-id="92712-142">**Chaîne de configuration**</span><span class="sxs-lookup"><span data-stu-id="92712-142">**Configuration String**</span></span>|<span data-ttu-id="92712-143">L'emplacement de la configuration.</span><span class="sxs-lookup"><span data-stu-id="92712-143">The location of the configuration.</span></span> <span data-ttu-id="92712-144">L'emplacement peut être un chemin d'accès, une variable d'environnement, une clé de Registre, un nom de variable d'un package parent ou une table d'une base de données [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="92712-144">The location can be a path, an environment variable, a Registry key, a parent package variable name, or a table in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="92712-145">**Objet cible**</span><span class="sxs-lookup"><span data-stu-id="92712-145">**Target Object**</span></span>|<span data-ttu-id="92712-146">Le nom de l'objet dont une propriété a une configuration.</span><span class="sxs-lookup"><span data-stu-id="92712-146">The name of the object with a property that has a configuration.</span></span> <span data-ttu-id="92712-147">Si la configuration est un fichier de configuration XML, la colonne est vide, car la configuration peut mettre à jour plusieurs objets.</span><span class="sxs-lookup"><span data-stu-id="92712-147">If the configuration is an XML configuration file, the column is blank, because the configuration can update multiple objects.</span></span>|  
|<span data-ttu-id="92712-148">**Propriété cible**</span><span class="sxs-lookup"><span data-stu-id="92712-148">**Target Property**</span></span>|<span data-ttu-id="92712-149">Nom de la propriété.</span><span class="sxs-lookup"><span data-stu-id="92712-149">The name of the property.</span></span> <span data-ttu-id="92712-150">Si la configuration écrit dans un fichier de configuration XML ou dans une table SQL Server, la colonne est vide puisque la configuration peut mettre à jour plusieurs objets.</span><span class="sxs-lookup"><span data-stu-id="92712-150">If the configuration writes to an XML configuration file or a SQL Server table, the column is blank, because the configuration can update multiple objects.</span></span>|  
  
### <a name="to-create-a-package-configuration"></a><span data-ttu-id="92712-151">Pour créer une configuration de package</span><span class="sxs-lookup"><span data-stu-id="92712-151">To create a package configuration</span></span>  
  
1.  <span data-ttu-id="92712-152">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="92712-152">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="92712-153">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="92712-153">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="92712-154">Dans le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] , cliquez sur l'onglet **Flux de contrôle**, **Flux de données**, **Gestionnaire d'événements**ou **Explorateur de package** .</span><span class="sxs-lookup"><span data-stu-id="92712-154">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Control Flow**, **Data Flow**, **Event Handler**, or **Package Explorer** tab.</span></span>  
  
4.  <span data-ttu-id="92712-155">Dans le menu **SSIS** , cliquez sur **Configurations du package**.</span><span class="sxs-lookup"><span data-stu-id="92712-155">On the **SSIS** menu, click **Package Configurations**.</span></span>  
  
5.  <span data-ttu-id="92712-156">Dans la boîte de dialogue **Bibliothèque des configurations du package** , sélectionnez **Activer les configurations du package**et cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="92712-156">In the **Package Configuration Organizer** dialog box, select **Enable package configurations**, and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="92712-157">Sur la page d'accueil de l'Assistant Configuration de package, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="92712-157">On the welcome page of the Package Configuration Wizard page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="92712-158">Sur la page Sélectionner le type de configuration, spécifiez le type de configuration, puis définissez les propriétés se rapportant au type de configuration.</span><span class="sxs-lookup"><span data-stu-id="92712-158">On the Select Configuration Type page, specify the configuration type, and then set the properties that are relevant to the configuration type.</span></span> <span data-ttu-id="92712-159">Pour plus d’informations, voir [Package Configuration Wizard UI Reference](../../2014/integration-services/package-configuration-wizard-ui-reference.md).</span><span class="sxs-lookup"><span data-stu-id="92712-159">For more information, see [Package Configuration Wizard UI Reference](../../2014/integration-services/package-configuration-wizard-ui-reference.md).</span></span>  
  
8.  <span data-ttu-id="92712-160">Dans la page Sélectionner les propriétés à exporter, sélectionnez les propriétés des objets de package à inclure dans la configuration.</span><span class="sxs-lookup"><span data-stu-id="92712-160">On the Select Properties to Export page, select the properties of package objects to include in the configuration.</span></span> <span data-ttu-id="92712-161">Si le type de configuration ne prend en charge qu'une seule propriété, le titre de cette page de l'Assistant est Sélectionner la propriété cible.</span><span class="sxs-lookup"><span data-stu-id="92712-161">If the configuration type supports only one property, the title of this wizard page is Select Target Property.</span></span> <span data-ttu-id="92712-162">Pour plus d’informations, voir [Package Configuration Wizard UI Reference](../../2014/integration-services/package-configuration-wizard-ui-reference.md).</span><span class="sxs-lookup"><span data-stu-id="92712-162">For more information, see [Package Configuration Wizard UI Reference](../../2014/integration-services/package-configuration-wizard-ui-reference.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="92712-163">Seuls les types de configuration **Fichier de configuration XML** et **SQL Server** prennent en charge l’inclusion de plusieurs propriétés dans une configuration.</span><span class="sxs-lookup"><span data-stu-id="92712-163">Only the **XML Configuration File** and **SQL Server** configuration types support including multiple properties in a configuration.</span></span>  
  
9. <span data-ttu-id="92712-164">Dans la page Fin de l'Assistant, tapez le nom de la configuration, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="92712-164">On the Completing the Wizard page, type the name of the configuration, and then click **Finish**.</span></span>  
  
10. <span data-ttu-id="92712-165">Affichez la configuration dans la boîte de dialogue **Bibliothèque des configurations du package** .</span><span class="sxs-lookup"><span data-stu-id="92712-165">View the configuration in the **Package Configuration Organizer** dialog box.</span></span>  
  
11. <span data-ttu-id="92712-166">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="92712-166">Click **Close**.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="92712-167">Ressources externes</span><span class="sxs-lookup"><span data-stu-id="92712-167">External Resources</span></span>  
  
-   <span data-ttu-id="92712-168">Article technique, [Understanding Integration Services Package Configurations](https://go.microsoft.com/fwlink/?LinkId=165643), sur msdn.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="92712-168">Technical article, [Understanding Integration Services Package Configurations](https://go.microsoft.com/fwlink/?LinkId=165643), on msdn.microsoft.com</span></span>  
  
-   <span data-ttu-id="92712-169">Entrée de blog, [création de packages dans le code-configurations de package](https://go.microsoft.com/fwlink/?LinkId=217663), sur www.SQLIS.com.</span><span class="sxs-lookup"><span data-stu-id="92712-169">Blog entry, [Creating packages in code - Package Configurations](https://go.microsoft.com/fwlink/?LinkId=217663), on www.sqlis.com.</span></span>  
  
-   <span data-ttu-id="92712-170">Entrée de blog, [exemple d’API-ajouter par programmation un fichier de configuration à un package](https://go.microsoft.com/fwlink/?LinkId=217664), sur blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="92712-170">Blog entry, [API Sample - Programmatically add a configuration file to a package](https://go.microsoft.com/fwlink/?LinkId=217664), on blogs.msdn.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92712-171">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="92712-171">See Also</span></span>  
 <span data-ttu-id="92712-172">[Configurations du package](../../2014/integration-services/package-configurations.md) </span><span class="sxs-lookup"><span data-stu-id="92712-172">[Package Configurations](../../2014/integration-services/package-configurations.md) </span></span>  
 <span data-ttu-id="92712-173">[Déploiement de packages &#40;&#41;SSIS](packages/legacy-package-deployment-ssis.md) </span><span class="sxs-lookup"><span data-stu-id="92712-173">[Package Deployment &#40;SSIS&#41;](packages/legacy-package-deployment-ssis.md) </span></span>  
 [<span data-ttu-id="92712-174">Utilisation de variables par programmation</span><span class="sxs-lookup"><span data-stu-id="92712-174">Working with Variables Programmatically</span></span>](building-packages-programmatically/working-with-variables-programmatically.md)  
  
  
