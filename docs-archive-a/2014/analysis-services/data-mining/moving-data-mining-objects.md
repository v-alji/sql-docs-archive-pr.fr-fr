---
title: Déplacement d’objets d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], models
- data mining editor [Analysis Services]
- mining models [Analysis Services], managing
- Data Mining Designer
- mining models [Analysis Services], modifying
ms.assetid: bc108407-2603-4387-b930-b5bb9df78069
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2b10be3a79487376b173eab87059404b7f7a618e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696327"
---
# <a name="moving-data-mining-objects"></a><span data-ttu-id="b2807-102">Déplacement d'objets d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="b2807-102">Moving Data Mining Objects</span></span>
  <span data-ttu-id="b2807-103">Les scénarios les plus courants de déplacement des objets d'exploration de données consistent à déployer un modèle d'un environnement de test ou d'analyse vers un environnement de production, ou à partager des modèles avec d'autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b2807-103">The most common scenarios for moving data mining objects are to deploy a model from a testing or analysis environment to a production environment, or to share models with other users.</span></span>  
  
 <span data-ttu-id="b2807-104">Cette rubrique explique comment utiliser les outils et langages de script fournis par [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]pour déplacer les objets d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="b2807-104">This topic describes how you can use the tools and scripting languages provided by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], for moving data mining objects.</span></span>  
  
## <a name="moving-data-mining-objects-between-databases-or-servers"></a><span data-ttu-id="b2807-105">Déplacement d'objets d'exploration de données entre des bases de données ou des serveurs</span><span class="sxs-lookup"><span data-stu-id="b2807-105">Moving Data Mining Objects between Databases or Servers</span></span>  
 <span data-ttu-id="b2807-106">Vous pouvez déplacer des objets d'exploration de données entre des bases de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ou entre des instances [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="b2807-106">You can move data mining objects between [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] databases or between instances of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in the following ways:</span></span>  
  
-   <span data-ttu-id="b2807-107">Redéploiement de la solution sur une autre base de données.</span><span class="sxs-lookup"><span data-stu-id="b2807-107">Re-deploying the solution to a different database.</span></span>  
  
-   <span data-ttu-id="b2807-108">Création de scripts pour des objets individuels.</span><span class="sxs-lookup"><span data-stu-id="b2807-108">Scripting individual objects.</span></span>  
  
-   <span data-ttu-id="b2807-109">Sauvegarde puis restauration d'une copie de la base de données.</span><span class="sxs-lookup"><span data-stu-id="b2807-109">Backing up and then restoring a copy of the database.</span></span>  
  
-   <span data-ttu-id="b2807-110">Exportation et importation des structures et des modèles.</span><span class="sxs-lookup"><span data-stu-id="b2807-110">Exporting and importing structures and models.</span></span>  
  
 <span data-ttu-id="b2807-111">La section suivante présente ces options plus en détail.</span><span class="sxs-lookup"><span data-stu-id="b2807-111">The following section explains these options in more detail.</span></span>  
  
### <a name="deploying"></a><span data-ttu-id="b2807-112">Déploiement en cours</span><span class="sxs-lookup"><span data-stu-id="b2807-112">Deploying</span></span>  
 <span data-ttu-id="b2807-113">Le déploiement de la solution sur un autre serveur ou une autre base de données nécessite que vous disposiez du fichier solution créé à l'aide de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2807-113">Deploying the solution to a different server or database requires that you have the solution file that was created by using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="b2807-114">Pour plus d’informations sur le déploiement de solutions Analysis Services, consultez [Déployer des projets Analysis Services &#40;SSDT&#41;](../multidimensional-models/deploy-analysis-services-projects-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="b2807-114">For more information about deploying Analysis Services solutions, see [Deploy Analysis Services Projects &#40;SSDT&#41;](../multidimensional-models/deploy-analysis-services-projects-ssdt.md).</span></span>  
  
### <a name="scripting"></a><span data-ttu-id="b2807-115">Création de scripts</span><span class="sxs-lookup"><span data-stu-id="b2807-115">Scripting</span></span>  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="b2807-116">fournit plusieurs langages dont vous pouvez vous servir pour créer des scripts d’objets.</span><span class="sxs-lookup"><span data-stu-id="b2807-116">provides several languages that you can use to script objects.</span></span>  
  
-   <span data-ttu-id="b2807-117">**XMLA**: vous pouvez créer des scripts d’objets à l’aide de XMLA en cliquant avec le bouton droit sur des objets dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2807-117">**XMLA**: You can script objects using XMLA by right-clicking objects in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="b2807-118">Pour exécuter le script, ouvrez-le dans une fenêtre **Requête XMLA** sur le serveur cible.</span><span class="sxs-lookup"><span data-stu-id="b2807-118">To execute the script, open it in an **XMLA Query** window on the target server.</span></span>  
  
-   <span data-ttu-id="b2807-119">**DMX**: vous pouvez créer des scripts à l’aide de modèles ou de l’un des générateurs de requêtes fournis dans [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] et [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2807-119">**DMX**: You can create scripts by using templates or one of the query builders provided in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="b2807-120">Notez, toutefois, qu'il existe des différences quant aux tâches que vous pouvez effectuer avec chaque langage de script :</span><span class="sxs-lookup"><span data-stu-id="b2807-120">Note, however, that there are differences in the tasks that you can perform with each scripting language:</span></span>  
  
-   <span data-ttu-id="b2807-121">Certaines propriétés telles que la description d’objet et les liaisons de données ne peuvent être créées et modifiées qu’à l’aide des langages DDL [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] et pas à l’aide de DMX.</span><span class="sxs-lookup"><span data-stu-id="b2807-121">Properties such as the object description and data bindings can only by created or changed by using [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] DDL languages, not by using DMX.</span></span>  
  
-   <span data-ttu-id="b2807-122">Seul DMX prend en charge l'importation et l'exportation des objets d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="b2807-122">Only DMX supports the import and export of mining objects.</span></span>  
  
-   <span data-ttu-id="b2807-123">Seul DMX prend en charge la génération PMML ou l'importation de définitions de modèle depuis PMML.</span><span class="sxs-lookup"><span data-stu-id="b2807-123">Only DMX supports generating PMML or importing model definitions from PMML.</span></span>  
  
-   <span data-ttu-id="b2807-124">Seul DMX prend en charge l'apprentissage d'un modèle avec les données d'application.</span><span class="sxs-lookup"><span data-stu-id="b2807-124">Only DMX supports training a model with application data.</span></span> <span data-ttu-id="b2807-125">De plus, l'instruction DMX INSERT INTO prend en charge l'apprentissage d'un modèle sans fournir de valeurs pour une colonne clé.</span><span class="sxs-lookup"><span data-stu-id="b2807-125">Moreover, the DMX INSERT INTO statement supports training a model without providing values for a key column.</span></span>  
  
 <span data-ttu-id="b2807-126">Pour plus d'informations, consultez [Développement avec le langage de script Analysis Services &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span><span class="sxs-lookup"><span data-stu-id="b2807-126">For more information, see [Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span></span>  
  
### <a name="backup-and-restore"></a><span data-ttu-id="b2807-127">Sauvegarde et restauration</span><span class="sxs-lookup"><span data-stu-id="b2807-127">Backup and Restore</span></span>  
 <span data-ttu-id="b2807-128">La sauvegarde et la restauration d'une base de données Analysis Services complète est la méthode idéale si votre solution d'exploration de données repose sur des objets OLAP.</span><span class="sxs-lookup"><span data-stu-id="b2807-128">Backup and restore of an entire Analysis Services database is the method of choice if your data mining solution relies on OLAP objects.</span></span> [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="b2807-129">fournit des fonctionnalités de sauvegarde et de restauration qui accélèrent et facilitent la sauvegarde des bases de données.</span><span class="sxs-lookup"><span data-stu-id="b2807-129">provides backup and restore functionality that makes database backups faster and easier.</span></span>  
  
 <span data-ttu-id="b2807-130">Pour plus d’informations sur la sauvegarde, consultez [Sauvegarde et restauration de bases de données Analysis Services](../multidimensional-models/backup-and-restore-of-analysis-services-databases.md).</span><span class="sxs-lookup"><span data-stu-id="b2807-130">For more information about backup, see [Backup and Restore of Analysis Services Databases](../multidimensional-models/backup-and-restore-of-analysis-services-databases.md).</span></span>  
  
### <a name="exporting-and-importing"></a><span data-ttu-id="b2807-131">Exportation et importation</span><span class="sxs-lookup"><span data-stu-id="b2807-131">Exporting and Importing</span></span>  
 <span data-ttu-id="b2807-132">L'exportation puis la réimportation des modèles et des structures d'exploration de données à l'aide d'instructions DMX est la méthode la plus facile pour déplacer ou sauvegarder des objets d'exploration de données relationnelles individuels.</span><span class="sxs-lookup"><span data-stu-id="b2807-132">Exporting and then re-importing mining models and structures by using DMX statements is the easiest way to move or back up individual relational data mining objects.</span></span> <span data-ttu-id="b2807-133">Pour plus d'informations sur la syntaxe DMX de ces opérations, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="b2807-133">For more information about the DMX syntax for these operations, see the following topics:</span></span>  
  
-   [<span data-ttu-id="b2807-134">EXPORT &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="b2807-134">EXPORT &#40;DMX&#41;</span></span>](/sql/dmx/export-dmx)  
  
-   [<span data-ttu-id="b2807-135">IMPORT &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="b2807-135">IMPORT &#40;DMX&#41;</span></span>](/sql/dmx/import-dmx)  
  
 <span data-ttu-id="b2807-136">Si vous spécifiez l’option INCLUDE DEPENDENCIES, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] exporte également la définition des vues de source de données requises, et quand vous importez le modèle ou la structure, il recrée la vue de source de données sur le serveur cible.</span><span class="sxs-lookup"><span data-stu-id="b2807-136">If you specify the INCLUDE DEPENDENCIES option, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will also export the definition of any required data source views, and when you import the model or structure, it will re-create the data source view on the target server.</span></span> <span data-ttu-id="b2807-137">Lorsque vous avez terminé d'importer le modèle, n'oubliez pas de définir les autorisations d'exploration de données sur l'objet.</span><span class="sxs-lookup"><span data-stu-id="b2807-137">After you have finished importing the model, make sure to set the necessary mining permissions on the object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b2807-138">Vous ne pouvez pas exporter et importer des modèles OLAP en utilisant DMX.</span><span class="sxs-lookup"><span data-stu-id="b2807-138">You cannot export and import OLAP models by using DMX.</span></span> <span data-ttu-id="b2807-139">Si votre modèle d’exploration de données est basé sur un cube OLAP, vous devez utiliser la fonctionnalité fournie par [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] pour la sauvegarde et la restauration d’une base de données complète, ou redéployer le cube et ses modèles.</span><span class="sxs-lookup"><span data-stu-id="b2807-139">If your mining model is based on an OLAP cube, you must use the functionality provided by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] for backing up and restoring an entire database, or redeploy the cube and its models.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2807-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b2807-140">See Also</span></span>  
 [<span data-ttu-id="b2807-141">Gestion des solutions et des objets d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="b2807-141">Management of Data Mining Solutions and Objects</span></span>](management-of-data-mining-solutions-and-objects.md)  
  
  
