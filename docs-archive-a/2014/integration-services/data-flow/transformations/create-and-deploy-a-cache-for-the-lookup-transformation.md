---
title: Créer et déployer un cache pour la transformation de recherche | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- creating cache files for Lookup transformation
- deploying cache files for Lookup transformation
- Lookup transformation cache files
ms.assetid: cedf5cad-2fac-42d0-ad91-9461e117d330
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b33b00b84f1f1448c2ee80882aedc3a330ba0a5a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600150"
---
# <a name="create-and-deploy-a-cache-for-the-lookup-transformation"></a><span data-ttu-id="5910b-102">Créer et déployer un cache pour la transformation de recherche</span><span class="sxs-lookup"><span data-stu-id="5910b-102">Create and Deploy a Cache for the Lookup Transformation</span></span>
  <span data-ttu-id="5910b-103">Vous pouvez créer et déployer un fichier cache (.caw) pour la transformation de recherche.</span><span class="sxs-lookup"><span data-stu-id="5910b-103">You can create and deploy a cache file (.caw) for the Lookup transformation.</span></span> <span data-ttu-id="5910b-104">Le dataset de référence est stocké dans le fichier cache.</span><span class="sxs-lookup"><span data-stu-id="5910b-104">The reference dataset is stored in the cache file.</span></span>  
  
 <span data-ttu-id="5910b-105">La transformation de recherche effectue des recherches en joignant les données des colonnes d’entrée d’une source de données connectée aux colonnes du dataset de référence.</span><span class="sxs-lookup"><span data-stu-id="5910b-105">The Lookup transformation performs lookups by joining data in input columns from a connected data source with columns in the reference dataset.</span></span>  
  
 <span data-ttu-id="5910b-106">Vous créez un fichier cache en utilisant un gestionnaire de connexions du cache et une transformation du cache.</span><span class="sxs-lookup"><span data-stu-id="5910b-106">You create a cache file by using a Cache connection manager and a Cache Transform transformation.</span></span> <span data-ttu-id="5910b-107">Pour plus d’informations, consultez [Gestionnaire de connexions du cache](../../connection-manager/cache-connection-manager.md) et [Transformation du cache](cache-transform.md).</span><span class="sxs-lookup"><span data-stu-id="5910b-107">For more information, see [Cache Connection Manager](../../connection-manager/cache-connection-manager.md) and [Cache Transform](cache-transform.md).</span></span>  
  
 <span data-ttu-id="5910b-108">Pour en savoir plus sur la transformation de recherche, consultez [Transformation de recherche](lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="5910b-108">To learn more about the Lookup transformation and cache files, see [Lookup Transformation](lookup-transformation.md).</span></span>  
  
### <a name="to-create-a-cache-file"></a><span data-ttu-id="5910b-109">Pour créer un fichier cache</span><span class="sxs-lookup"><span data-stu-id="5910b-109">To create a cache file</span></span>  
  
1.  <span data-ttu-id="5910b-110">Dans [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] qui contient le package souhaité, puis ouvrez le package.</span><span class="sxs-lookup"><span data-stu-id="5910b-110">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want, and then open the package.</span></span>  
  
2.  <span data-ttu-id="5910b-111">Sous l’onglet **Flux de contrôle** , ajoutez une tâche de flux de données.</span><span class="sxs-lookup"><span data-stu-id="5910b-111">On the **Control Flow** tab, add a Data Flow task.</span></span>  
  
3.  <span data-ttu-id="5910b-112">Sous l’onglet **Flux de données** , ajoutez une transformation du cache au flux de données, puis connectez la transformation à une source de données.</span><span class="sxs-lookup"><span data-stu-id="5910b-112">On the **Data Flow** tab, add a Cache Transform transformation to the data flow, and then connect the transformation to a data source.</span></span>  
  
     <span data-ttu-id="5910b-113">Configurez la source de données selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="5910b-113">Configure the data source as needed.</span></span>  
  
4.  <span data-ttu-id="5910b-114">Double-cliquez sur la transformation du cache puis, dans **l’Éditeur de transformation du cache**, dans la page **Gestionnaire de connexions** , cliquez sur **Nouveau** pour créer un gestionnaire de connexions du cache.</span><span class="sxs-lookup"><span data-stu-id="5910b-114">Double-click the Cache Transform, and then in the **Cache Transformation Editor**, on the **Connection Manager** page, click **New** to create a new Cache connection manager.</span></span>  
  
5.  <span data-ttu-id="5910b-115">Dans **l’Éditeur du gestionnaire de connexions du cache**, sous l’onglet **Général** , configurez le gestionnaire de connexions du cache pour enregistrer le cache en sélectionnant les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="5910b-115">In the **Cache Connection Manager Editor**, on the **General** tab, configure the Cache connection manager to save the cache by selecting the following options:</span></span>  
  
    1.  <span data-ttu-id="5910b-116">Sélectionnez **Utiliser le cache de fichier**.</span><span class="sxs-lookup"><span data-stu-id="5910b-116">Select **Use file cache**.</span></span>  
  
    2.  <span data-ttu-id="5910b-117">Dans la zone **Nom de fichier**, entrez le chemin du fichier.</span><span class="sxs-lookup"><span data-stu-id="5910b-117">For **File name**, type the file path.</span></span>  
  
     <span data-ttu-id="5910b-118">Le système crée le fichier lorsque vous exécutez le package.</span><span class="sxs-lookup"><span data-stu-id="5910b-118">The system creates the file when you run the package.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5910b-119">Le niveau de protection du package ne s'applique pas au fichier cache.</span><span class="sxs-lookup"><span data-stu-id="5910b-119">The protection level of the package does not apply to the cache file.</span></span> <span data-ttu-id="5910b-120">Si le fichier cache contient des informations sensibles, utilisez une liste de contrôle d'accès (ACL) pour restreindre l'accès à l'emplacement ou au dossier dans lequel vous stockez le fichier.</span><span class="sxs-lookup"><span data-stu-id="5910b-120">If the cache file contains sensitive information, use an access control list (ACL) to restrict access to the location or folder in which you store the file.</span></span> <span data-ttu-id="5910b-121">Vous devez autoriser l'accès à certains comptes uniquement.</span><span class="sxs-lookup"><span data-stu-id="5910b-121">You should enable access only to certain accounts.</span></span> <span data-ttu-id="5910b-122">Pour plus d’informations, consultez [Accéder aux fichiers utilisés par des packages](../../access-to-files-used-by-packages.md).</span><span class="sxs-lookup"><span data-stu-id="5910b-122">For more information, see [Access to Files Used by Packages](../../access-to-files-used-by-packages.md).</span></span>  
  
6.  <span data-ttu-id="5910b-123">Cliquez sur l’onglet **Colonnes** , puis spécifiez quelles colonnes sont les colonnes d’index en utilisant l’option **Position d’index** .</span><span class="sxs-lookup"><span data-stu-id="5910b-123">Click the **Columns** tab, and then specify which columns are the index columns by using the **Index Position** option.</span></span>  
  
     <span data-ttu-id="5910b-124">Pour les colonnes qui ne sont pas des index, la position d'index est 0.</span><span class="sxs-lookup"><span data-stu-id="5910b-124">For non-index columns, the index position is 0.</span></span> <span data-ttu-id="5910b-125">Pour les colonnes d'index, la position d'index est un nombre séquentiel, positif.</span><span class="sxs-lookup"><span data-stu-id="5910b-125">For index columns, the index position is a sequential, positive number.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5910b-126">Lorsque la transformation de recherche est configurée pour utiliser un gestionnaire de connexions du cache, seules les colonnes d'index dans le dataset de référence peuvent être mappées avec des colonnes d'entrée.</span><span class="sxs-lookup"><span data-stu-id="5910b-126">When the Lookup transformation is configured to use a Cache connection manager, only index columns in the reference dataset can be mapped to input columns.</span></span> <span data-ttu-id="5910b-127">En outre, toutes les colonnes d’index doivent être mappées.</span><span class="sxs-lookup"><span data-stu-id="5910b-127">Also all index columns must be mapped.</span></span>  
  
     <span data-ttu-id="5910b-128">Pour plus d’informations, consultez [Éditeur du gestionnaire de connexions du cache](../../cache-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="5910b-128">For more information, see [Cache Connection Manager Editor](../../cache-connection-manager-editor.md).</span></span>  
  
7.  <span data-ttu-id="5910b-129">Configurez la transformation du cache selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="5910b-129">Configure the Cache Transform as needed.</span></span>  
  
     <span data-ttu-id="5910b-130">Pour plus d’informations, consultez [Éditeur de transformation du cache &#40;page Gestionnaire de connexions&#41;](../../cache-transformation-editor-connection-manager-page.md) et [Éditeur de transformation du cache &#40;page Mappages&#41;](../../cache-transformation-editor-mappings-page.md).</span><span class="sxs-lookup"><span data-stu-id="5910b-130">For more information, see [Cache Transformation Editor &#40;Connection Manager Page&#41;](../../cache-transformation-editor-connection-manager-page.md) and [Cache Transformation Editor &#40;Mappings Page&#41;](../../cache-transformation-editor-mappings-page.md).</span></span>  
  
8.  <span data-ttu-id="5910b-131">Exécutez le package.</span><span class="sxs-lookup"><span data-stu-id="5910b-131">Run the package.</span></span>  
  
### <a name="to-deploy-a-cache-file"></a><span data-ttu-id="5910b-132">Pour déployer un fichier cache</span><span class="sxs-lookup"><span data-stu-id="5910b-132">To deploy a cache file</span></span>  
  
1.  <span data-ttu-id="5910b-133">Dans [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] qui contient le package souhaité, puis ouvrez le package.</span><span class="sxs-lookup"><span data-stu-id="5910b-133">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want, and then open the package.</span></span>  
  
2.  <span data-ttu-id="5910b-134">Vous pouvez éventuellement créer une configuration de package.</span><span class="sxs-lookup"><span data-stu-id="5910b-134">Optionally, create a package configuration.</span></span> <span data-ttu-id="5910b-135">Pour plus d’informations, consultez [Créer des configurations de package](../../create-package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="5910b-135">For more information, see [Create Package Configurations](../../create-package-configurations.md).</span></span>  
  
3.  <span data-ttu-id="5910b-136">Ajoutez le fichier cache au projet en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="5910b-136">Add the cache file to the project by doing the following:</span></span>  
  
    1.  <span data-ttu-id="5910b-137">Dans l'Explorateur de solutions, sélectionnez le projet que vous avez ouvert à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="5910b-137">In Solution Explorer, select the project you opened in step 1.</span></span>  
  
    2.  <span data-ttu-id="5910b-138">Dans le menu **Projet** , cliquez sur **Ajouter un élément existant**.</span><span class="sxs-lookup"><span data-stu-id="5910b-138">On the **Project** menu, click **AddExisting Item**.</span></span>  
  
    3.  <span data-ttu-id="5910b-139">Sélectionnez le fichier de cache, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="5910b-139">Select the cache file, and then click **Add**.</span></span>  
  
     <span data-ttu-id="5910b-140">Le fichier apparaît dans le dossier **Divers** de l’Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="5910b-140">The file appears in the **Miscellaneous** folder in Solution Explorer.</span></span>  
  
4.  <span data-ttu-id="5910b-141">Configurez le projet afin de créer un utilitaire de déploiement, puis créez le projet.</span><span class="sxs-lookup"><span data-stu-id="5910b-141">Configure the project to create a deployment utility, and then build the project.</span></span> <span data-ttu-id="5910b-142">Pour plus d’informations, consultez [Créer un utilitaire de déploiement](../../create-a-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="5910b-142">For more information, see [Create a Deployment Utility](../../create-a-deployment-utility.md).</span></span>  
  
     <span data-ttu-id="5910b-143">Un fichier manifeste, \<*project name*>.SSISDeploymentManifest.xml, est créé. Il liste les divers fichiers du projet, les packages et les configurations des packages.</span><span class="sxs-lookup"><span data-stu-id="5910b-143">A manifest file, \<*project name*>.SSISDeploymentManifest.xml, is created that lists the miscellaneous files in the project, the packages, and the package configurations.</span></span>  
  
5.  <span data-ttu-id="5910b-144">Déployez le package dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="5910b-144">Deploy the package to the file system.</span></span> <span data-ttu-id="5910b-145">Pour plus d’informations, consultez [Déployer des packages à l’aide de l’utilitaire de déploiement](../../deploy-packages-by-using-the-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="5910b-145">For more information, see [Deploy Packages by Using the Deployment Utility](../../deploy-packages-by-using-the-deployment-utility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5910b-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5910b-146">See Also</span></span>  
 [<span data-ttu-id="5910b-147">Créer un utilitaire de déploiement</span><span class="sxs-lookup"><span data-stu-id="5910b-147">Create a Deployment Utility</span></span>](../../create-a-deployment-utility.md)  
  
  
