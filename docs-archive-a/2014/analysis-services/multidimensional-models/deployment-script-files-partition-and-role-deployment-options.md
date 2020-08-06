---
title: Spécification des options de déploiement de partitions et de rôles | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- input files [Analysis Services]
- partitions [Analysis Services], deployment options
- Analysis Services deployments, roles
- Analysis Services deployments, partitions
- Analysis Services Deployment Wizard, roles
- Analysis Services Deployment Wizard, partitions
- deploying [Analysis Services], roles
- roles [Analysis Services], deployment options
- deploying [Analysis Services], partitions
- modifying role deployments
- modifying partition deployments
ms.assetid: e9b9ca57-a5cc-4fc0-87b5-305257038d56
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8c8dd7bcb482c2d28a18e3039f5acb777b121202
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613650"
---
# <a name="specifying-partition-and-role-deployment-options"></a><span data-ttu-id="bb68c-102">Spécification des options de déploiement de partitions et de rôles</span><span class="sxs-lookup"><span data-stu-id="bb68c-102">Specifying Partition and Role Deployment Options</span></span>
  <span data-ttu-id="bb68c-103">L' [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Assistant Déploiement de lit les options de déploiement de partitions et de rôles à partir du \<*project name*> fichier. deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="bb68c-103">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard reads the partition and role deployment options from the \<*project name*>.deploymentoptions file.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="bb68c-104">crée ce fichier lorsque vous générez le [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projet.</span><span class="sxs-lookup"><span data-stu-id="bb68c-104">creates this file when you build the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="bb68c-105">utilise les options de déploiement de partitions et de rôles du projet actif lors de la \<*project name*> création du fichier. deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="bb68c-105">uses the partition and role deployment options of the current project when the \<*project name*>.deploymentoptions file is created.</span></span> <span data-ttu-id="bb68c-106">Pour plus d'informations sur les paramètres de configuration, consultez [Understanding the Input Files Used to Create the Deployment Script](deployment-script-files-input-used-to-create-deployment-script.md).</span><span class="sxs-lookup"><span data-stu-id="bb68c-106">For more information about configuration settings, see [Understanding the Input Files Used to Create the Deployment Script](deployment-script-files-input-used-to-create-deployment-script.md).</span></span>  
  
## <a name="reviewing-the-partition-and-role-deployment-options"></a><span data-ttu-id="bb68c-107">Examen des options de déploiement de partitions et de rôles</span><span class="sxs-lookup"><span data-stu-id="bb68c-107">Reviewing the Partition and Role Deployment Options</span></span>  
 <span data-ttu-id="bb68c-108">Les options de déploiement dans le \<*project name*> fichier. deploymentoptions sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="bb68c-108">The deployment options in the \<*project name*>.deploymentoptions file include the following:</span></span>  
  
 <span data-ttu-id="bb68c-109">**Options de déploiement de partitions**</span><span class="sxs-lookup"><span data-stu-id="bb68c-109">**Partition deployment options**</span></span>  
 <span data-ttu-id="bb68c-110">Le \<*project name*> fichier. deploymentoptions spécifie si les partitions existantes dans la base de données de destination sont conservées ou remplacées (par défaut).</span><span class="sxs-lookup"><span data-stu-id="bb68c-110">The \<*project name*>.deploymentoptions file specifies whether existing partitions in the destination database are retained or overwritten (default).</span></span> <span data-ttu-id="bb68c-111">Si les partitions existantes sont conservées, seules les nouvelles partitions sont déployées, et les partitions et les conceptions d'agrégation sur tous les groupes de mesures restent inchangées.</span><span class="sxs-lookup"><span data-stu-id="bb68c-111">If existing partitions are retained, only new partitions will be deployed, and the partitions and aggregation designs on all existing measure groups are left unchanged.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb68c-112">Si le groupe de mesures dans lequel existe la partition est supprimé, la partition est supprimée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="bb68c-112">If the measure group in which the partition exists is deleted, the partition is automatically deleted.</span></span>  
  
 <span data-ttu-id="bb68c-113">**Options de déploiement de rôles**</span><span class="sxs-lookup"><span data-stu-id="bb68c-113">**Role deployment options**</span></span>  
 <span data-ttu-id="bb68c-114">Le \<*project name*> fichier. deploymentoptions spécifie l’une des options de déploiement de rôle suivantes :</span><span class="sxs-lookup"><span data-stu-id="bb68c-114">The \<*project name*>.deploymentoptions file specifies one of the following role deployment options:</span></span>  
  
-   <span data-ttu-id="bb68c-115">Les rôles et les membres de rôle existant dans la base de données de destination sont conservés, et seuls les nouveaux rôles et membres de rôle sont déployés.</span><span class="sxs-lookup"><span data-stu-id="bb68c-115">Existing roles and role members in the destination database are retained, and only new roles and role members are deployed.</span></span>  
  
-   <span data-ttu-id="bb68c-116">Tous les rôles et les membres de rôle existant dans la base de données de destination sont remplacés par les rôles et les membres de rôle déployés.</span><span class="sxs-lookup"><span data-stu-id="bb68c-116">All existing roles and members in the destination database are replaced by the roles and members being deployed.</span></span>  
  
-   <span data-ttu-id="bb68c-117">Les rôles et les membres de rôle existant dans la base de données de destination sont conservés, et aucun nouveau rôle n'est déployé.</span><span class="sxs-lookup"><span data-stu-id="bb68c-117">Existing roles and role members in the destination database are retained, and no new roles are deployed.</span></span>  
  
-   <span data-ttu-id="bb68c-118">**Remarque** Lorsque des membres et des rôles existants sont conservés, les autorisations associées à ces rôles sont réinitialisées à Aucune autorisation.</span><span class="sxs-lookup"><span data-stu-id="bb68c-118">**Note** When existing roles and members are retained, the permissions associated with those roles are reset to none.</span></span> <span data-ttu-id="bb68c-119">Les autorisations de sécurité sont contenues dans les objets qu'elles sécurisent, et non dans les rôles de sécurité auxquels elles sont associées.</span><span class="sxs-lookup"><span data-stu-id="bb68c-119">Security permissions are contained by the objects they secure, not by the security roles with which they are associated.</span></span> <span data-ttu-id="bb68c-120">Pour plus d’informations sur l’utilisation de ce comportement à l’aide de l’Assistant Déploiement d’Analysis Services, consultez la rubrique relative à la conservation des rôles et des membres dans la base de connaissances Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bb68c-120">For more information about how to work with this behavior by using the Analysis Service Deployment Wizard, see 'Retain Roles and Members' in the Microsoft Knowledge Base.</span></span>  
  
## <a name="modifying-the-partition-and-role-deployment-options"></a><span data-ttu-id="bb68c-121">Modification des options de déploiement de partitions et de rôles</span><span class="sxs-lookup"><span data-stu-id="bb68c-121">Modifying the Partition and Role Deployment Options</span></span>  
 <span data-ttu-id="bb68c-122">Vous devrez peut-être déployer le [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projet en utilisant des options de partitions et de rôles différentes de celles stockées dans le \<*project name*> fichier. deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="bb68c-122">You may have to deploy the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project using different partition and role options than those stored in the \<*project name*>.deploymentoptions file.</span></span> <span data-ttu-id="bb68c-123">Par exemple, vous souhaiterez peut-être conserver les partitions, rôles et membres de rôle existants, au lieu de remplacer toutes les partitions, rôles et membres existants comme indiqué dans le \<*project name*> fichier. deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="bb68c-123">For example, you may want to retain existing partitions, roles, and role members, instead of replacing all existing partitions, roles, and members as indicated in the \<*project name*>.deploymentoptions file.</span></span>  
  
 <span data-ttu-id="bb68c-124">Pour modifier le déploiement des partitions et des rôles dans un [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projet, vous ne pouvez pas modifier les paramètres de partitions et de rôles dans le projet, car la *\<project name>* boîte de dialogue **pages de propriétés** de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] n’affiche pas ces options.</span><span class="sxs-lookup"><span data-stu-id="bb68c-124">To modify the deployment of partitions and roles in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, you cannot change the partition and roles settings within the project because the *\<project name>* **Properties Pages** dialog box in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] does not display these options.</span></span> <span data-ttu-id="bb68c-125">Si vous souhaitez modifier les options de déploiement pour les rôles et les partitions, vous devez modifier ces informations dans le \<*project name*> fichier. deploymentoptions lui-même.</span><span class="sxs-lookup"><span data-stu-id="bb68c-125">If you want to change the deployment options for roles and partitions, you must change this information within the \<*project name*>.deploymentoptions file itself.</span></span> <span data-ttu-id="bb68c-126">La procédure suivante décrit comment modifier les options de déploiement de partitions et de rôles dans le \<*project name*> fichier. deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="bb68c-126">The following procedure describes how to change the partition and role deployment options within the \<*project name*>.deploymentoptions file.</span></span>  
  
#### <a name="to-change-the-deployment-of-partitions-or-roles-after-the-input-files-have-been-generated"></a><span data-ttu-id="bb68c-127">Pour modifier le déploiement de partitions ou de rôles après la génération des fichiers d'entrée</span><span class="sxs-lookup"><span data-stu-id="bb68c-127">To change the deployment of partitions or roles after the input files have been generated</span></span>  
  
-   <span data-ttu-id="bb68c-128">Exécutez l'Assistant Déploiement de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en mode interactif et, sur la page **Spécifiez des options pour les partitions et les rôles** , spécifiez de nouvelles options de déploiement pour les partitions et les rôles.</span><span class="sxs-lookup"><span data-stu-id="bb68c-128">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard interactively, and on the **Partition and Role Deployment Options** page, specify new deployment options for the partitions and roles.</span></span>  
  
     <span data-ttu-id="bb68c-129">-ou-</span><span class="sxs-lookup"><span data-stu-id="bb68c-129">-or-</span></span>  
  
-   <span data-ttu-id="bb68c-130">Exécutez l'Assistant Déploiement de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] à l'invite de commandes en mode fichier de réponses.</span><span class="sxs-lookup"><span data-stu-id="bb68c-130">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard at the command prompt, and set the wizard to run in answer file mode.</span></span> <span data-ttu-id="bb68c-131">(Pour plus d’informations sur le mode fichier de réponses, consultez [exécution de l’Assistant Déploiement de Analysis Services](running-the-analysis-services-deployment-wizard.md).)</span><span class="sxs-lookup"><span data-stu-id="bb68c-131">(For more information about answer file mode, see [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).)</span></span>  
  
     <span data-ttu-id="bb68c-132">-ou-</span><span class="sxs-lookup"><span data-stu-id="bb68c-132">-or-</span></span>  
  
-   <span data-ttu-id="bb68c-133">Ouvrez le \<*project name*> . deploymentoptions dans n’importe quel éditeur de texte et modifiez manuellement les options.</span><span class="sxs-lookup"><span data-stu-id="bb68c-133">Open the \<*project name*>.deploymentoptions in any text editor and manually change the options.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb68c-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bb68c-134">See Also</span></span>  
 <span data-ttu-id="bb68c-135">[Spécification de la cible d’installation](deployment-script-files-specifying-the-installation-target.md) </span><span class="sxs-lookup"><span data-stu-id="bb68c-135">[Specifying the Installation Target](deployment-script-files-specifying-the-installation-target.md) </span></span>  
 <span data-ttu-id="bb68c-136">[Spécification des paramètres de configuration pour le déploiement de solutions](deployment-script-files-solution-deployment-config-settings.md) </span><span class="sxs-lookup"><span data-stu-id="bb68c-136">[Specifying Configuration Settings for Solution Deployment](deployment-script-files-solution-deployment-config-settings.md) </span></span>  
 [<span data-ttu-id="bb68c-137">Spécification d'options de traitement</span><span class="sxs-lookup"><span data-stu-id="bb68c-137">Specifying Processing Options</span></span>](deployment-script-files-specifying-processing-options.md)  
  
  
