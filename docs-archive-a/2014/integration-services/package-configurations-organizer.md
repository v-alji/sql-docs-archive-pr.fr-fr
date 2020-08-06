---
title: Bibliothèque de configurations du package | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.packageconfigurationorganizer.f1
helpviewer_keywords:
- Package Configurations Organizer dialog box
ms.assetid: f20ae6cb-9e6a-4d24-88ff-d7a903a4e8d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 67fdc9ca0faeff57c18fdb6e4d10acca3e9963f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705259"
---
# <a name="package-configurations-organizer"></a><span data-ttu-id="82c2e-102">Bibliothèque des configurations du package</span><span class="sxs-lookup"><span data-stu-id="82c2e-102">Package Configurations Organizer</span></span>
  <span data-ttu-id="82c2e-103">Utilisez la boîte de dialogue **Bibliothèque des configurations du package** pour activer les configurations du package, afficher une liste des configurations du package actuel et spécifier l'ordre de chargement de préférence des configurations.</span><span class="sxs-lookup"><span data-stu-id="82c2e-103">Use the **Package Configurations Organizer** dialog box to enable package configurations, view a list of configurations for the current package, and specify the preferred order in which the configurations should be loaded.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="82c2e-104">Des configurations sont disponibles pour le modèle de déploiement de package.</span><span class="sxs-lookup"><span data-stu-id="82c2e-104">Configurations are available for the package deployment model.</span></span> <span data-ttu-id="82c2e-105">Les paramètres sont utilisés à la place des configurations pour le modèle de déploiement de projet.</span><span class="sxs-lookup"><span data-stu-id="82c2e-105">Parameters are used in place of configurations for the project deployment model.</span></span> <span data-ttu-id="82c2e-106">Le modèle de déploiement de projet vous permet de déployer des projets [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sur le serveur [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="82c2e-106">The project deployment model enables you to deploy [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="82c2e-107">Pour plus d'informations sur les modèles de déploiement, consultez [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="82c2e-107">For more information about the deployment models, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="82c2e-108">Si plusieurs configurations mettent à jour la même propriété, les valeurs des configurations du bas de la liste de configuration remplacent les valeurs des configurations du haut de la liste.</span><span class="sxs-lookup"><span data-stu-id="82c2e-108">If multiple configurations update the same property, values from configurations listed lower in the configuration list will replace values from configurations higher in the list.</span></span> <span data-ttu-id="82c2e-109">La dernière valeur chargée dans la propriété est la valeur utilisée à l'exécution du package.</span><span class="sxs-lookup"><span data-stu-id="82c2e-109">The last value loaded into the property is the value that is used when the package runs.</span></span> <span data-ttu-id="82c2e-110">De plus, si le package utilise une combinaison de configuration directe (par exemple, un fichier de configuration XML) et de configuration indirecte (par exemple, une variable d'environnement), la configuration indirecte qui pointe vers l'emplacement de la configuration directe doit figurer plus haut dans la liste.</span><span class="sxs-lookup"><span data-stu-id="82c2e-110">Also, if the package uses a combination of direct configuration such as an XML configuration file and an indirect configuration such as an environment variable, the indirect configuration that points to the location of the direct configuration must be higher in the list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="82c2e-111">Lorsque les configurations du package sont chargées dans l'ordre souhaité, le chargement est effectué du haut vers le bas de la liste affichée dans la boîte de dialogue **Bibliothèques des configurations du package** .</span><span class="sxs-lookup"><span data-stu-id="82c2e-111">When package configurations load in the preferred order, configurations load from the top of the list shown in the **Package Configuration Organizer** dialog box to the bottom of the list.</span></span> <span data-ttu-id="82c2e-112">Toutefois, au moment de l'exécution, il se peut que les configurations de package ne soient pas chargées dans l'ordre souhaité.</span><span class="sxs-lookup"><span data-stu-id="82c2e-112">However, at run time, package configurations might not load in the preferred order.</span></span> <span data-ttu-id="82c2e-113">Les configurations de package parent sont notamment chargées après les configurations d'autres types.</span><span class="sxs-lookup"><span data-stu-id="82c2e-113">In particular, Parent Package Configurations load after configurations of other types.</span></span>  
  
 <span data-ttu-id="82c2e-114">Les configurations de package mettent à jour les valeurs des propriétés des objets de package au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="82c2e-114">Package configurations update the values of properties of package objects at run time.</span></span> <span data-ttu-id="82c2e-115">Lorsqu'un package est chargé, les valeurs des configurations remplacent les valeurs définies lors du développement du package.</span><span class="sxs-lookup"><span data-stu-id="82c2e-115">When a package is loaded, the values from the configurations replace the values that were set when the package was developed.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="82c2e-116">prend en charge différents types de configuration.</span><span class="sxs-lookup"><span data-stu-id="82c2e-116">supports different configuration types.</span></span> <span data-ttu-id="82c2e-117">Par exemple, vous pouvez utiliser un fichier XML pouvant contenir plusieurs configurations, ou une variable d'environnement qui contient une seule configuration.</span><span class="sxs-lookup"><span data-stu-id="82c2e-117">For example, you can use an XML file that can contain multiple configurations, or an environment variable that contains a single configuration.</span></span> <span data-ttu-id="82c2e-118">Pour plus d’informations, consultez [Package Configurations](../../2014/integration-services/package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="82c2e-118">For more information, see [Package Configurations](../../2014/integration-services/package-configurations.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="82c2e-119">Options</span><span class="sxs-lookup"><span data-stu-id="82c2e-119">Options</span></span>  
 <span data-ttu-id="82c2e-120">**Activer les configurations du package**</span><span class="sxs-lookup"><span data-stu-id="82c2e-120">**Enable package configurations**</span></span>  
 <span data-ttu-id="82c2e-121">Sélectionnez cette option pour utiliser les configurations avec le package.</span><span class="sxs-lookup"><span data-stu-id="82c2e-121">Select to use configurations with the package.</span></span>  
  
 <span data-ttu-id="82c2e-122">**Nom de la configuration**</span><span class="sxs-lookup"><span data-stu-id="82c2e-122">**Configuration Name**</span></span>  
 <span data-ttu-id="82c2e-123">Affichez le nom de la configuration.</span><span class="sxs-lookup"><span data-stu-id="82c2e-123">View the name of the configuration.</span></span>  
  
 <span data-ttu-id="82c2e-124">**Type de configuration**</span><span class="sxs-lookup"><span data-stu-id="82c2e-124">**Configuration Type**</span></span>  
 <span data-ttu-id="82c2e-125">Affichez le type de l'emplacement où sont stockées les configurations.</span><span class="sxs-lookup"><span data-stu-id="82c2e-125">View the type of the location where configurations are stored.</span></span>  
  
 <span data-ttu-id="82c2e-126">**Chaîne de configuration**</span><span class="sxs-lookup"><span data-stu-id="82c2e-126">**Configuration String**</span></span>  
 <span data-ttu-id="82c2e-127">Affichez l'emplacement où sont stockées les valeurs de configuration.</span><span class="sxs-lookup"><span data-stu-id="82c2e-127">View the location where the configuration values are stored.</span></span> <span data-ttu-id="82c2e-128">L'emplacement peut être le chemin d'accès d'un fichier, le nom d'une variable d'environnement, le nom d'une variable de package parent, une clé de Registre ou le nom d'une table [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="82c2e-128">The location can be the path of a file, the name of an environment variable, the name of a parent package variable, a Registry key, or the name of a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="82c2e-129">**Objet cible**</span><span class="sxs-lookup"><span data-stu-id="82c2e-129">**Target Object**</span></span>  
 <span data-ttu-id="82c2e-130">Affiche le nom de l'objet mis à jour par la configuration.</span><span class="sxs-lookup"><span data-stu-id="82c2e-130">View the name of the object that the configuration updates.</span></span> <span data-ttu-id="82c2e-131">Si la configuration est un fichier de configuration XML ou une table SQL Server, la colonne est vide puisque la configuration peut inclure plusieurs objets.</span><span class="sxs-lookup"><span data-stu-id="82c2e-131">If the configuration is an XML configuration file or a SQL Server table, the column is blank because the configuration can include multiple objects.</span></span>  
  
 <span data-ttu-id="82c2e-132">**Propriété cible**</span><span class="sxs-lookup"><span data-stu-id="82c2e-132">**Target Property**</span></span>  
 <span data-ttu-id="82c2e-133">Affichez le nom de la propriété modifiée par la configuration.</span><span class="sxs-lookup"><span data-stu-id="82c2e-133">View the name of the property modified by the configuration.</span></span> <span data-ttu-id="82c2e-134">Cette colonne est vide si le type de configuration prend en charge plusieurs configurations.</span><span class="sxs-lookup"><span data-stu-id="82c2e-134">This column is blank if the configuration type supports multiple configurations.</span></span>  
  
 <span data-ttu-id="82c2e-135">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="82c2e-135">**Add**</span></span>  
 <span data-ttu-id="82c2e-136">Ajoutez une configuration à l'aide de l'Assistant Configuration de package.</span><span class="sxs-lookup"><span data-stu-id="82c2e-136">Add a configuration by using the Package Configuration Wizard.</span></span>  
  
 <span data-ttu-id="82c2e-137">**Modifier**</span><span class="sxs-lookup"><span data-stu-id="82c2e-137">**Edit**</span></span>  
 <span data-ttu-id="82c2e-138">Modifiez une configuration existante en réexécutant l'Assistant Configuration de package.</span><span class="sxs-lookup"><span data-stu-id="82c2e-138">Edit an existing configuration by rerunning the Package Configuration Wizard.</span></span>  
  
 <span data-ttu-id="82c2e-139">**Remove**</span><span class="sxs-lookup"><span data-stu-id="82c2e-139">**Remove**</span></span>  
 <span data-ttu-id="82c2e-140">Sélectionnez une configuration, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="82c2e-140">Select a configuration, and then click **Remove**.</span></span>  
  
 <span data-ttu-id="82c2e-141">**Flèches**</span><span class="sxs-lookup"><span data-stu-id="82c2e-141">**Arrows**</span></span>  
 <span data-ttu-id="82c2e-142">Sélectionnez une configuration et utilisez les flèches vers le haut et vers le bas pour la déplacer vers le haut ou vers le bas de la liste.</span><span class="sxs-lookup"><span data-stu-id="82c2e-142">Select a configuration and use the up and down arrows to move it up or down in the list.</span></span> <span data-ttu-id="82c2e-143">Les configurations sont chargées dans l'ordre dans lequel elles apparaissent dans la liste.</span><span class="sxs-lookup"><span data-stu-id="82c2e-143">Configurations are loaded in the sequence in which they appear in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82c2e-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="82c2e-144">See Also</span></span>  
 [<span data-ttu-id="82c2e-145">Créer des configurations de package</span><span class="sxs-lookup"><span data-stu-id="82c2e-145">Create Package Configurations</span></span>](../../2014/integration-services/create-package-configurations.md)  
  
  
