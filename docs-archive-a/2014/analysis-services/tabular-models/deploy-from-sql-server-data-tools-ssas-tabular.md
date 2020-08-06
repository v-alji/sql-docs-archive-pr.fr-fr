---
title: Déployer à partir de SQL Server Data Tools (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.deploystatus.f1
ms.assetid: 67dde3fe-ba43-41f3-b56c-c656029ee93f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8bc8008e7c79e1652b54b21e6afb116301d1700b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610874"
---
# <a name="deploy-from-sql-server-data-tools-ssas-tabular"></a><span data-ttu-id="0d545-102">Déployer à partir de SQL Server Data Tools (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="0d545-102">Deploy From SQL Server Data Tools (SSAS Tabular)</span></span>
  <span data-ttu-id="0d545-103">Utilisez les tâches de cette rubrique pour déployer une solution de modèle tabulaire à l'aide de la commande Déployer de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d545-103">Use the tasks in this topic to deploy a tabular model solution by using the Deploy command in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="0d545-104">Sections de cette rubrique :</span><span class="sxs-lookup"><span data-stu-id="0d545-104">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="0d545-105">Configurer les propriétés Options de déploiement et Serveur de déploiement</span><span class="sxs-lookup"><span data-stu-id="0d545-105">Configure Deployment Options and Deployment Server Properties</span></span>](#bkmk_deploy)  
  
-   [<span data-ttu-id="0d545-106">Déployer une solution de modèle tabulaire</span><span class="sxs-lookup"><span data-stu-id="0d545-106">Deploy a Tabular Model Solution</span></span>](#bkmk_deploy_proc)  
  
-   [<span data-ttu-id="0d545-107">État du déploiement</span><span class="sxs-lookup"><span data-stu-id="0d545-107">Deploy Status</span></span>](#bkmk_deploy_status)  
  
##  <a name="configure-deployment-options-and-deployment-server-properties"></a><a name="bkmk_deploy"></a><span data-ttu-id="0d545-108">Configurer les propriétés options de déploiement et serveur de déploiement</span><span class="sxs-lookup"><span data-stu-id="0d545-108">Configure Deployment Options and Deployment Server Properties</span></span>  
 <span data-ttu-id="0d545-109">Avant de déployer votre solution de modèle tabulaire, vous devez spécifier les propriétés Options de déploiement et Serveur de déploiement.</span><span class="sxs-lookup"><span data-stu-id="0d545-109">Before you deploy your tabular model solution, you must first specify the Deployment Options and Deployment Server properties.</span></span> <span data-ttu-id="0d545-110">Pour plus d’informations sur les paramètres et les propriétés de déploiement, consultez [Déploiement d’une solution de modèle tabulaire &#40;SSAS Tabulaire&#41;](tabular-model-solution-deployment-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="0d545-110">For more information about deployment properties and settings, see [Tabular Model Solution Deployment &#40;SSAS Tabular&#41;](tabular-model-solution-deployment-ssas-tabular.md).</span></span>  
  
#### <a name="to-configure-deployment-options-and-deployment-server-properties"></a><span data-ttu-id="0d545-111">Pour configurer les propriétés Options de déploiement et Serveur de déploiement</span><span class="sxs-lookup"><span data-stu-id="0d545-111">To configure Deployment Options and Deployment Server properties</span></span>  
  
1.  <span data-ttu-id="0d545-112">Dans [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], dans **l’Explorateur de solutions**, cliquez avec le bouton droit sur le nom du projet, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="0d545-112">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], in **Solution Explorer**, right-click the project name, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="0d545-113">Dans la boîte de dialogue \*\* \<project name> Propriétés\*\* , dans **options de déploiement**, spécifiez les paramètres de propriété s’ils sont différents des paramètres par défaut.</span><span class="sxs-lookup"><span data-stu-id="0d545-113">In the **\<project name> Properties** dialog, in **Deployment Options**, specify property settings if different from the default settings.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0d545-114">Pour les modèles en mode mis en cache, **Mode de requête** a toujours la valeur **In-Memory**.</span><span class="sxs-lookup"><span data-stu-id="0d545-114">For models in cached mode, **Query Mode** is always **In-Memory**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0d545-115">Vous ne pouvez pas spécifier de **Paramètres d’emprunt d’identité** pour les modèles en mode DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="0d545-115">You cannot specify **Impersonation Settings** for models in DirectQuery mode.</span></span>  
  
3.  <span data-ttu-id="0d545-116">Dans **Serveur de déploiement**, spécifiez les paramètres de propriété **Serveur** (nom), **Édition**, **Base de données** (nom) et **Nom du cube** , s’ils sont différents des paramètres par défaut, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0d545-116">In **Deployment Server**, specify the **Server** (name), **Edition**, **Database** (name), and **Cube Name** property settings, if different from the default settings, and then click **OK**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0d545-117">Vous pouvez également spécifier le paramètre de propriété Serveur de déploiement par défaut afin que tous les nouveaux projets que vous créez soient automatiquement déployés sur le serveur spécifié.</span><span class="sxs-lookup"><span data-stu-id="0d545-117">You can also specify the Default Deployment Server property setting so any new projects you create will automatically be deployed to the specified server.</span></span> <span data-ttu-id="0d545-118">Pour plus d’informations, consultez [Configurer les propriétés par défaut de modélisation des données et de déploiement &#40;SSAS Tabulaire&#41;](properties-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="0d545-118">For more information, see [Configure Default Data Modeling and Deployment Properties &#40;SSAS Tabular&#41;](properties-ssas-tabular.md).</span></span>  
  
##  <a name="deploy-a-tabular-model-solution"></a><a name="bkmk_deploy_proc"></a><span data-ttu-id="0d545-119">Déployer une solution de modèle tabulaire</span><span class="sxs-lookup"><span data-stu-id="0d545-119">Deploy a Tabular Model Solution</span></span>  
  
#### <a name="to-deploy-a-tabular-model-solution"></a><span data-ttu-id="0d545-120">Pour déployer une solution de modèle tabulaire</span><span class="sxs-lookup"><span data-stu-id="0d545-120">To deploy a tabular model solution</span></span>  
  
-   <span data-ttu-id="0d545-121">Dans [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] , dans le menu **générer** , cliquez \*\*sur \<project name> déployer \*\*.</span><span class="sxs-lookup"><span data-stu-id="0d545-121">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], on the **Build** menu, click **Deploy \<project name>**.</span></span>  
  
     <span data-ttu-id="0d545-122">La boîte de dialogue **Déployer** apparaît et indique l’état du déploiement des métadonnées et du traitement (sauf si la propriété Option de traitement a la valeur Ne pas traiter) de chaque table incluse dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="0d545-122">The **Deploy** dialog box will appear and indicate the status of the metadata deployment and the processing (unless Processing Option property is set to Do Not Process) of each table included in the model.</span></span> <span data-ttu-id="0d545-123">Lorsque le déploiement est terminé, utilisez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour vous connecter à l'instance d'Analysis Services et vérifier que le nouvel objet de base de données model a été créé ou utilisez une application de création de rapports cliente pour vous connecter au modèle déployé.</span><span class="sxs-lookup"><span data-stu-id="0d545-123">After the deployment process is complete, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to connect to the Analysis Services instance and verify the new model database object has been created or use a client reporting application to connect to the deployed model.</span></span>  
  
##  <a name="deploy-status"></a><a name="bkmk_deploy_status"></a><span data-ttu-id="0d545-124">État du déploiement</span><span class="sxs-lookup"><span data-stu-id="0d545-124">Deploy Status</span></span>  
 <span data-ttu-id="0d545-125">La boîte de dialogue **Déployer** vous permet de surveiller la progression d'une opération de déploiement.</span><span class="sxs-lookup"><span data-stu-id="0d545-125">The **Deploy** dialog box enables you to monitor the progress of a Deploy operation.</span></span> <span data-ttu-id="0d545-126">Une opération de déploiement peut également être arrêtée.</span><span class="sxs-lookup"><span data-stu-id="0d545-126">A deploy operation can also be stopped.</span></span>  
  
 <span data-ttu-id="0d545-127">**État**</span><span class="sxs-lookup"><span data-stu-id="0d545-127">**Status**</span></span>  
 <span data-ttu-id="0d545-128">Indique si l'opération de déploiement a abouti.</span><span class="sxs-lookup"><span data-stu-id="0d545-128">Indicates whether the Deploy operation was successful or not.</span></span>  
  
 <span data-ttu-id="0d545-129">**Détails**</span><span class="sxs-lookup"><span data-stu-id="0d545-129">**Details**</span></span>  
 <span data-ttu-id="0d545-130">Répertorie les éléments de métadonnées déployés, l'état pour chaque élément de métadonnées, et affiche un message en cas de problèmes.</span><span class="sxs-lookup"><span data-stu-id="0d545-130">Lists the metadata items that were deployed, the status for each metadata item, and provides a message of any issues.</span></span>  
  
 <span data-ttu-id="0d545-131">**Arrêter le déploiement**</span><span class="sxs-lookup"><span data-stu-id="0d545-131">**Stop Deploy**</span></span>  
 <span data-ttu-id="0d545-132">Cliquez pour arrêter l'opération de déploiement.</span><span class="sxs-lookup"><span data-stu-id="0d545-132">Click to halt the Deploy operation.</span></span> <span data-ttu-id="0d545-133">Cette option est utile si l'opération de déploiement prend trop de temps ou génère trop d'erreurs.</span><span class="sxs-lookup"><span data-stu-id="0d545-133">This option is useful if the Deploy operation is taking too long, or if there are too many errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d545-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0d545-134">See Also</span></span>  
 <span data-ttu-id="0d545-135">[Déploiement de solutions de modèles tabulaires &#40;&#41;SSAS tabulaire](tabular-model-solution-deployment-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="0d545-135">[Tabular Model Solution Deployment &#40;SSAS Tabular&#41;](tabular-model-solution-deployment-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="0d545-136">Configurer les propriétés par défaut de modélisation des données et de déploiement &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="0d545-136">Configure Default Data Modeling and Deployment Properties &#40;SSAS Tabular&#41;</span></span>](properties-ssas-tabular.md)  
  
  
