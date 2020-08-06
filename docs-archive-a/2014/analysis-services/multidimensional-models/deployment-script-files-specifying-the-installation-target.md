---
title: Spécification de la cible d’installation | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- input files [Analysis Services]
- installation targets [Analysis Services]
- Analysis Services deployments, installation targets
- Analysis Services Deployment Wizard, installation targets
- deploying [Analysis Services], installation targets
- modifying installation targets
ms.assetid: cb706817-6f63-4771-92c3-b70030bbce3d
author: minewiskan
ms.author: owend
ms.openlocfilehash: e830fc353898e3ec835b338e84765a0cad0de43f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610892"
---
# <a name="specifying-the-installation-target"></a><span data-ttu-id="1fe57-102">Spécification de la cible d'installation</span><span class="sxs-lookup"><span data-stu-id="1fe57-102">Specifying the Installation Target</span></span>
  <span data-ttu-id="1fe57-103">L' [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Assistant Déploiement de lit les informations sur la cible d’installation à partir du \<*project name*> fichier. deploymenttargets.</span><span class="sxs-lookup"><span data-stu-id="1fe57-103">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard reads the installation target information from the \<*project name*>.deploymenttargets file.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="1fe57-104">crée ce fichier lorsque vous générez le [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projet.</span><span class="sxs-lookup"><span data-stu-id="1fe57-104">creates this file when you build the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="1fe57-105">utilise la base de données et le serveur spécifiés dans la page **déploiement** de la *\<project name>* boîte de dialogue pages de **Propriétés** pour créer le \<*project name*> fichier. targets.</span><span class="sxs-lookup"><span data-stu-id="1fe57-105">uses the database and server specified on the **Deployment** page of the *\<project name>* **Properties Pages** dialog box to create the \<*project name*>.targets file.</span></span>  
  
## <a name="modifying-the-installation-target-for-deployment"></a><span data-ttu-id="1fe57-106">Modification de la cible d'installation pour le déploiement</span><span class="sxs-lookup"><span data-stu-id="1fe57-106">Modifying the Installation Target for Deployment</span></span>  
 <span data-ttu-id="1fe57-107">Dans certaines situations, il peut s'avérer nécessaire de déployer un projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] vers une base de données ou une instance de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] différente de celle spécifiée sur la page **Déploiement** .</span><span class="sxs-lookup"><span data-stu-id="1fe57-107">In some situations, you may need to deploy an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project to a database or [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance that is different than the one specified on the **Deployment** page.</span></span> <span data-ttu-id="1fe57-108">Par exemple, vous pouvez choisir de déployer le projet vers un serveur où il sera testé avant son déploiement, puis de le déployer vers un serveur de production une fois les tests terminés.</span><span class="sxs-lookup"><span data-stu-id="1fe57-108">For example, you may want to deploy the project to a server for testing before deployment, and then deploy it to a production server after testing is finished.</span></span> <span data-ttu-id="1fe57-109">Vous pouvez aussi décider de déployer un projet terminé et testé vers plusieurs serveurs de production dans un cluster d'équilibrage de la charge réseau, ou encore vers un serveur de test et un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="1fe57-109">You may also want to deploy a completed and tested project to multiple production servers in a Network Load Balancing cluster, or to a staging server and a production server.</span></span>  
  
 <span data-ttu-id="1fe57-110">Pour déployer un projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] vers une base de données ou une instance de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] différente, vous pouvez modifier la cible d'installation dans le fichier d'entrée en employant l'une des méthodes décrites dans la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="1fe57-110">To deploy an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project to a different database or [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, you can change the installation target in the input file by using one of the methods described in the following procedure.</span></span>  
  
#### <a name="to-change-the-installation-target-after-the-input-files-have-been-generated"></a><span data-ttu-id="1fe57-111">Pour modifier la cible d'installation après la génération des fichiers d'entrée</span><span class="sxs-lookup"><span data-stu-id="1fe57-111">To change the installation target after the input files have been generated</span></span>  
  
-   <span data-ttu-id="1fe57-112">Exécutez l'Assistant Déploiement de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en mode interactif.</span><span class="sxs-lookup"><span data-stu-id="1fe57-112">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard interactively.</span></span> <span data-ttu-id="1fe57-113">Sur la page **Cible d'installation** , spécifiez une nouvelle destination pour l'instance de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] et la base de données.</span><span class="sxs-lookup"><span data-stu-id="1fe57-113">On the **Installation Target** page, specify a new destination for the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and database.</span></span>  
  
     <span data-ttu-id="1fe57-114">-ou-</span><span class="sxs-lookup"><span data-stu-id="1fe57-114">-or-</span></span>  
  
-   <span data-ttu-id="1fe57-115">Exécutez l'Assistant Déploiement de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] à l'invite de commandes en mode fichier de réponses.</span><span class="sxs-lookup"><span data-stu-id="1fe57-115">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard at the command prompt and set the wizard to run in answer file mode.</span></span> <span data-ttu-id="1fe57-116">Pour plus d'informations sur le mode fichier de réponses, consultez [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="1fe57-116">For more information about answer file mode, see [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).</span></span>  
  
     <span data-ttu-id="1fe57-117">-ou-</span><span class="sxs-lookup"><span data-stu-id="1fe57-117">-or-</span></span>  
  
-   <span data-ttu-id="1fe57-118">Modifiez le \<*project name*> fichier. deploymenttargets à l’aide de n’importe quel éditeur de texte.</span><span class="sxs-lookup"><span data-stu-id="1fe57-118">Modify the \<*project name*>.deploymenttargets file by using any text editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fe57-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1fe57-119">See Also</span></span>  
 <span data-ttu-id="1fe57-120">[Spécification des options de déploiement de partitions et de rôles](deployment-script-files-partition-and-role-deployment-options.md) </span><span class="sxs-lookup"><span data-stu-id="1fe57-120">[Specifying Partition and Role Deployment Options](deployment-script-files-partition-and-role-deployment-options.md) </span></span>  
 <span data-ttu-id="1fe57-121">[Spécification des paramètres de configuration pour le déploiement de solutions](deployment-script-files-solution-deployment-config-settings.md) </span><span class="sxs-lookup"><span data-stu-id="1fe57-121">[Specifying Configuration Settings for Solution Deployment](deployment-script-files-solution-deployment-config-settings.md) </span></span>  
 [<span data-ttu-id="1fe57-122">Spécification d'options de traitement</span><span class="sxs-lookup"><span data-stu-id="1fe57-122">Specifying Processing Options</span></span>](deployment-script-files-specifying-processing-options.md)  
  
  
