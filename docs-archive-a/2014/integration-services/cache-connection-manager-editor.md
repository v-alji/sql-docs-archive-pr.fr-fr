---
title: Éditeur du gestionnaire de connexions du cache | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.cacheconnection.f1
ms.assetid: 0d8f9324-0c35-4eea-b06d-da3cc2426d2c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 38a858217925496d8dd937d684368bdb2e061b14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613587"
---
# <a name="cache-connection-manager-editor"></a><span data-ttu-id="f780f-102">Éditeur du gestionnaire de connexions du cache</span><span class="sxs-lookup"><span data-stu-id="f780f-102">Cache Connection Manager Editor</span></span>
  <span data-ttu-id="f780f-103">Le gestionnaire de connexions du cache lit un dataset de référence à partir de la transformation de cache ou d'un fichier cache (.caw) et peut enregistrer les données dans un fichier cache.</span><span class="sxs-lookup"><span data-stu-id="f780f-103">The Cache connection manager reads a reference dataset from the Cache transform or from a cache file (.caw), and can save the data to a cache file.</span></span> <span data-ttu-id="f780f-104">Les données sont toujours stockées en mémoire.</span><span class="sxs-lookup"><span data-stu-id="f780f-104">The data is always stored in memory.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f780f-105">Le gestionnaire de connexions du cache ne prend pas en charge les types de données de l'objet BLOB (Binary Large Object) DT_TEXT, DT_NTEXT et DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="f780f-105">The Cache connection manager does not support the Binary Large Object (BLOB) data types DT_TEXT, DT_NTEXT, and DT_IMAGE.</span></span> <span data-ttu-id="f780f-106">Si le dataset de référence contient un type de données d'objet BLOB, le composant échoue lorsque vous exécutez le package.</span><span class="sxs-lookup"><span data-stu-id="f780f-106">If the reference dataset contains a BLOB data type, the component will fail when you run the package.</span></span> <span data-ttu-id="f780f-107">Vous pouvez utiliser l' **Éditeur du gestionnaire de connexions du cache** pour modifier des types de données de colonne.</span><span class="sxs-lookup"><span data-stu-id="f780f-107">You can use the **Cache Connection Manager Editor** to modify column data types.</span></span>  
  
 <span data-ttu-id="f780f-108">La transformation de recherche effectue des recherches sur le dataset de référence.</span><span class="sxs-lookup"><span data-stu-id="f780f-108">The Lookup transformation performs lookups on the reference dataset.</span></span>  
  
 <span data-ttu-id="f780f-109">La boîte de dialogue **Éditeur du gestionnaire de connexions du cache** inclut les onglets suivants :</span><span class="sxs-lookup"><span data-stu-id="f780f-109">The **Cache Connection ManagerEditor** dialog box includes the following tabs:</span></span>  
  
-   [<span data-ttu-id="f780f-110">Onglet Général</span><span class="sxs-lookup"><span data-stu-id="f780f-110">General tab</span></span>](#generaltab)  
  
-   [<span data-ttu-id="f780f-111">Onglet colonnes</span><span class="sxs-lookup"><span data-stu-id="f780f-111">Columns tab</span></span>](#columnstab)  
  
 <span data-ttu-id="f780f-112">Pour en savoir plus sur le gestionnaire de connexions du cache, consultez [cache Connection Manager](connection-manager/cache-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="f780f-112">To learn more about the Cache Connection Manager, see [Cache Connection Manager](connection-manager/cache-connection-manager.md).</span></span>  
  
##  <a name="general-tab"></a><a name="generaltab"></a><span data-ttu-id="f780f-113">Onglet général</span><span class="sxs-lookup"><span data-stu-id="f780f-113">General Tab</span></span>  
 <span data-ttu-id="f780f-114">Utilisez l’onglet **Général** de la boîte de dialogue **Éditeur du gestionnaire de connexions du cache** pour indiquer s’il faut lire le cache depuis un fichier ou l’enregistrer dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="f780f-114">Use the **General** tab of the **Cache Connection ManagerEditor** dialog box to indicate whether to read the cache from a file or save the cache to a file.</span></span>  
  
### <a name="options"></a><span data-ttu-id="f780f-115">Options</span><span class="sxs-lookup"><span data-stu-id="f780f-115">Options</span></span>  
 <span data-ttu-id="f780f-116">**Nom du gestionnaire de connexions**</span><span class="sxs-lookup"><span data-stu-id="f780f-116">**Connection manager name**</span></span>  
 <span data-ttu-id="f780f-117">Fournit un nom unique pour la connexion de fichiers cache dans le flux de travail.</span><span class="sxs-lookup"><span data-stu-id="f780f-117">Provide a unique name for the cache connection in the workflow.</span></span> <span data-ttu-id="f780f-118">Le nom fourni sera affiché dans le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f780f-118">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="f780f-119">**Description**</span><span class="sxs-lookup"><span data-stu-id="f780f-119">**Description**</span></span>  
 <span data-ttu-id="f780f-120">Décrit la connexion.</span><span class="sxs-lookup"><span data-stu-id="f780f-120">Describe the connection.</span></span> <span data-ttu-id="f780f-121">Il est recommandé de décrire la connexion selon son objectif, de sorte que les packages soient correctement documentés et plus faciles à gérer.</span><span class="sxs-lookup"><span data-stu-id="f780f-121">As a best practice, describe the connection according to its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="f780f-122">**Utiliser un cache de fichier**</span><span class="sxs-lookup"><span data-stu-id="f780f-122">**Use file cache**</span></span>  
 <span data-ttu-id="f780f-123">Indiquez s'il faut utiliser ou non un fichier cache.</span><span class="sxs-lookup"><span data-stu-id="f780f-123">Indicate whether to use a cache file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f780f-124">Le niveau de protection du package ne s'applique pas au fichier cache.</span><span class="sxs-lookup"><span data-stu-id="f780f-124">The protection level of the package does not apply to the cache file.</span></span> <span data-ttu-id="f780f-125">Si le fichier cache contient des informations sensibles, utilisez une liste de contrôle d'accès (ACL) pour restreindre l'accès à l'emplacement ou au dossier dans lequel vous stockez le fichier.</span><span class="sxs-lookup"><span data-stu-id="f780f-125">If the cache file contains sensitive information, use an access control list (ACL) to restrict access to the location or folder in which you store the file.</span></span> <span data-ttu-id="f780f-126">Vous devez autoriser l'accès à certains comptes uniquement.</span><span class="sxs-lookup"><span data-stu-id="f780f-126">You should enable access only to certain accounts.</span></span> <span data-ttu-id="f780f-127">Pour plus d’informations, consultez [Accéder aux fichiers utilisés par des packages](../../2014/integration-services/access-to-files-used-by-packages.md).</span><span class="sxs-lookup"><span data-stu-id="f780f-127">For more information, see [Access to Files Used by Packages](../../2014/integration-services/access-to-files-used-by-packages.md).</span></span>  
  
 <span data-ttu-id="f780f-128">Si vous configurez le gestionnaire de connexions du cache pour utiliser un fichier cache, il effectuera l'une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="f780f-128">If you configure the cache connection manager to use a cache file, the connection manager will do one of the following actions:</span></span>  
  
-   <span data-ttu-id="f780f-129">Il enregistrera les données dans le fichier lorsqu'une transformation du cache est configurée pour écrire des données depuis une source de données dans le flux de données dans le gestionnaire de connexions du cache.</span><span class="sxs-lookup"><span data-stu-id="f780f-129">Save data to the file when a Cache Transform transformation is configured to write data from a data source in the data flow to the Cache connection manager.</span></span> <span data-ttu-id="f780f-130">Pour plus d'informations, consultez [Cache Transform](data-flow/transformations/cache-transform.md).</span><span class="sxs-lookup"><span data-stu-id="f780f-130">For more information, see [Cache Transform](data-flow/transformations/cache-transform.md).</span></span>  
  
-   <span data-ttu-id="f780f-131">Il lira des données à partir du fichier cache.</span><span class="sxs-lookup"><span data-stu-id="f780f-131">Read data from the cache file.</span></span>  
  
 <span data-ttu-id="f780f-132">**Nom de fichier**</span><span class="sxs-lookup"><span data-stu-id="f780f-132">**File name**</span></span>  
 <span data-ttu-id="f780f-133">Tapez le chemin d'accès et le nom du fichier cache.</span><span class="sxs-lookup"><span data-stu-id="f780f-133">Type the path and file name of the cache file.</span></span>  
  
 <span data-ttu-id="f780f-134">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="f780f-134">**Browse**</span></span>  
 <span data-ttu-id="f780f-135">Recherchez le fichier cache.</span><span class="sxs-lookup"><span data-stu-id="f780f-135">Locate the cache file.</span></span>  
  
 <span data-ttu-id="f780f-136">**Actualiser les métadonnées**</span><span class="sxs-lookup"><span data-stu-id="f780f-136">**Refresh Metadata**</span></span>  
 <span data-ttu-id="f780f-137">Supprimez les métadonnées de colonne dans le gestionnaire de connexions du cache et remplissez à nouveau celui-ci avec les métadonnées de colonne d'un fichier cache sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f780f-137">Delete the column metadata in the Cache connection manager and repopulate the Cache connection manager with column metadata from a selected cache file.</span></span>  
  
##  <a name="columns-tab"></a><a name="columnstab"></a><span data-ttu-id="f780f-138">Onglet colonnes</span><span class="sxs-lookup"><span data-stu-id="f780f-138">Columns Tab</span></span>  
 <span data-ttu-id="f780f-139">Utilisez l'onglet **Colonnes** de la boîte de dialogue **Éditeur du gestionnaire de connexions du cache** pour configurer les propriétés de chaque colonne dans le cache.</span><span class="sxs-lookup"><span data-stu-id="f780f-139">Use the **Columns** tab of the **Cache Connection Manager Editor** dialog box to configure the properties of each column in the cache.</span></span>  
  
### <a name="options"></a><span data-ttu-id="f780f-140">Options</span><span class="sxs-lookup"><span data-stu-id="f780f-140">Options</span></span>  
 <span data-ttu-id="f780f-141">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="f780f-141">**Column**</span></span>  
 <span data-ttu-id="f780f-142">Spécifiez le nom de la colonne.</span><span class="sxs-lookup"><span data-stu-id="f780f-142">Specify the column name.</span></span>  
  
 <span data-ttu-id="f780f-143">**Position d'index**</span><span class="sxs-lookup"><span data-stu-id="f780f-143">**Index Position**</span></span>  
 <span data-ttu-id="f780f-144">Spécifiez quelles colonnes sont des colonnes d'index en indiquant la position d'index de chaque colonne.</span><span class="sxs-lookup"><span data-stu-id="f780f-144">Specify which columns are index columns by specifying the index position of each column.</span></span> <span data-ttu-id="f780f-145">L'index est une collection composée d'une ou de plusieurs colonnes.</span><span class="sxs-lookup"><span data-stu-id="f780f-145">The index is a collection of one or more columns.</span></span>  
  
 <span data-ttu-id="f780f-146">Pour les colonnes qui ne sont pas des index, la position d'index est 0.</span><span class="sxs-lookup"><span data-stu-id="f780f-146">For non-index columns, the index position is 0.</span></span>  
  
 <span data-ttu-id="f780f-147">Pour les colonnes d'index, la position d'index est un nombre séquentiel, positif.</span><span class="sxs-lookup"><span data-stu-id="f780f-147">For index columns, the index position is a sequential, positive number.</span></span> <span data-ttu-id="f780f-148">Ce nombre indique l'ordre dans lequel la transformation de recherche compare des lignes dans le dataset de référence aux lignes de la source de données d'entrée.</span><span class="sxs-lookup"><span data-stu-id="f780f-148">This number indicates the order in which the Lookup transformation compares rows in the reference dataset to rows in the input data source.</span></span> <span data-ttu-id="f780f-149">La colonne comportant la plupart des valeurs doit avoir la position d'index la plus faible.</span><span class="sxs-lookup"><span data-stu-id="f780f-149">The column with the most unique values should have the lowest index position.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f780f-150">Lorsque la transformation de recherche est configurée pour utiliser un gestionnaire de connexions du cache, seules les colonnes d'index dans le dataset de référence peuvent être mappées avec des colonnes d'entrée.</span><span class="sxs-lookup"><span data-stu-id="f780f-150">When the Lookup transformation is configured to use a Cache connection manager, only index columns in the reference dataset can be mapped to input columns.</span></span> <span data-ttu-id="f780f-151">En outre, toutes les colonnes d'index doivent être mappées.</span><span class="sxs-lookup"><span data-stu-id="f780f-151">Also, all index columns must be mapped.</span></span>  
  
 <span data-ttu-id="f780f-152">**Type**</span><span class="sxs-lookup"><span data-stu-id="f780f-152">**Type**</span></span>  
 <span data-ttu-id="f780f-153">Spécifiez le type de données de la colonne.</span><span class="sxs-lookup"><span data-stu-id="f780f-153">Specify the data type of the column.</span></span>  
  
 `Length`  
 <span data-ttu-id="f780f-154">Indique le type de données de la colonne.</span><span class="sxs-lookup"><span data-stu-id="f780f-154">Specifies the column data type.</span></span> <span data-ttu-id="f780f-155">Si le type de données le permet, vous pouvez mettre à jour `Length`.</span><span class="sxs-lookup"><span data-stu-id="f780f-155">If applicable to the data type, you can update `Length`.</span></span>  
  
 `Precision`  
 <span data-ttu-id="f780f-156">Spécifie la précision pour certains types de données de colonne.</span><span class="sxs-lookup"><span data-stu-id="f780f-156">Specifies the precision for certain column data types.</span></span> <span data-ttu-id="f780f-157">La précision est le nombre de chiffres qui composent un nombre.</span><span class="sxs-lookup"><span data-stu-id="f780f-157">Precision is the number of digits in a number.</span></span> <span data-ttu-id="f780f-158">Si le type de données le permet, vous pouvez mettre à jour `Precision`.</span><span class="sxs-lookup"><span data-stu-id="f780f-158">If applicable to the data type, you can update `Precision`.</span></span>  
  
 `Scale`  
 <span data-ttu-id="f780f-159">Spécifie l'échelle pour certains types de données de colonne.</span><span class="sxs-lookup"><span data-stu-id="f780f-159">Specifies the scale for certain column data types.</span></span> <span data-ttu-id="f780f-160">L'échelle est le nombre de chiffres à droite du séparateur décimal dans un nombre.</span><span class="sxs-lookup"><span data-stu-id="f780f-160">Scale is the number of digits to the right of the decimal point in a number.</span></span> <span data-ttu-id="f780f-161">Si le type de données le permet, vous pouvez mettre à jour `Scale`.</span><span class="sxs-lookup"><span data-stu-id="f780f-161">If applicable to the data type, you can update `Scale`.</span></span>  
  
 `Code Page`  
 <span data-ttu-id="f780f-162">Spécifie la page de codes pour le type de colonne.</span><span class="sxs-lookup"><span data-stu-id="f780f-162">Specifies the code page for the column type.</span></span> <span data-ttu-id="f780f-163">Si le type de données le permet, vous pouvez mettre à jour `Code Page`.</span><span class="sxs-lookup"><span data-stu-id="f780f-163">If applicable to the data type, you can update `Code Page`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f780f-164">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f780f-164">See Also</span></span>  
 [<span data-ttu-id="f780f-165">Transformation de recherche</span><span class="sxs-lookup"><span data-stu-id="f780f-165">Lookup Transformation</span></span>](data-flow/transformations/lookup-transformation.md)  
  
  
