---
title: Créer et gérer des catalogues de texte intégral | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- full-text catalogs [SQL Server], creating
- full-text search [SQL Server], using SQL Server Management Studio
ms.assetid: 824b7131-44a6-4815-89e6-62b7bab060e3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 18efd79bc34beee94d4edc61e9165a986edba90b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614471"
---
# <a name="create-and-manage-full-text-catalogs"></a><span data-ttu-id="516f5-102">Créer et gérer des catalogues de texte intégral</span><span class="sxs-lookup"><span data-stu-id="516f5-102">Create and Manage Full-Text Catalogs</span></span>
  <span data-ttu-id="516f5-103">Un catalogue de texte intégral est un objet virtuel qui n'appartient à aucun groupe de fichiers ; c'est un concept logique qui renvoie à un groupe d'index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="516f5-103">A full-text catalog is a virtual object that does not belong to any filegroup; it is a logical concept that refers to a group of full-text indexes.</span></span>  
  
##  <a name="creating-a-full-text-catalog"></a><a name="creating"></a><span data-ttu-id="516f5-104">Création d’un catalogue de texte intégral</span><span class="sxs-lookup"><span data-stu-id="516f5-104">Creating a Full-Text Catalog</span></span>  
  
#### <a name="to-create-a-full-text-catalog"></a><span data-ttu-id="516f5-105">Pour créer un catalogue de texte intégral</span><span class="sxs-lookup"><span data-stu-id="516f5-105">To create a full-text catalog</span></span>  
  
1.  <span data-ttu-id="516f5-106">Dans l’Explorateur d’objets, développez successivement le serveur, le nœud **Bases de données**, puis la base de données contenant le catalogue de texte intégral à créer.</span><span class="sxs-lookup"><span data-stu-id="516f5-106">In Object Explorer, expand the server, expand **Databases**, and expand the database in which you want to create the full-text catalog.</span></span>  
  
2.  <span data-ttu-id="516f5-107">Développez **Stockage**, puis cliquez avec le bouton droit sur **Catalogues de texte intégral**.</span><span class="sxs-lookup"><span data-stu-id="516f5-107">Expand **Storage**, and then right-click **Full Text Catalogs**.</span></span>  
  
3.  <span data-ttu-id="516f5-108">Sélectionnez **Nouveau catalogue de recherche en texte intégral**.</span><span class="sxs-lookup"><span data-stu-id="516f5-108">Select **New Full-Text Catalog**.</span></span>  
  
4.  <span data-ttu-id="516f5-109">Dans la boîte de dialogue **Nouveau catalogue de recherche en texte intégral** , précisez les informations relatives au catalogue que vous recréez.</span><span class="sxs-lookup"><span data-stu-id="516f5-109">In the **New Full-Text Catalog** dialog box, specify the information for the catalog that you are re-creating.</span></span> <span data-ttu-id="516f5-110">Pour plus d’informations, consultez [Recherche en texte intégral &#40;page Général&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="516f5-110">For more information, see [New Full-Text Catalog &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="516f5-111">Les ID de catalogues de texte intégral commencent à 00005 et sont incrémentés d'une unité à chaque fois qu'un catalogue est créé.</span><span class="sxs-lookup"><span data-stu-id="516f5-111">Full-text catalog IDs begin at 00005 and are incremented by one for each new catalog created.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
  
  
##  <a name="viewing-the-properties-of-a-full-text-catalog"></a><a name="props"></a><span data-ttu-id="516f5-112">Affichage des propriétés d’un catalogue de texte intégral</span><span class="sxs-lookup"><span data-stu-id="516f5-112">Viewing the Properties of a Full-Text Catalog</span></span>  
 <span data-ttu-id="516f5-113">Vous pouvez faire appel à plusieurs fonctions [!INCLUDE[tsql](../../includes/tsql-md.md)], telles que FULLTEXTCATALOGPROPERTY, pour obtenir la valeur de diverses propriétés relatives à l'indexation de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="516f5-113">[!INCLUDE[tsql](../../includes/tsql-md.md)] functions such as FULLTEXTCATALOGPROPERTY can be used to obtain the value of various properties related to full-text indexing.</span></span> <span data-ttu-id="516f5-114">Ces informations sont utiles pour administrer la recherche en texte intégral et résoudre les problèmes qui la concernent.</span><span class="sxs-lookup"><span data-stu-id="516f5-114">This information is useful for administering and troubleshooting full-text search.</span></span>  
  
 <span data-ttu-id="516f5-115">Le tableau suivant répertorie les propriétés liées aux catalogues de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="516f5-115">The following table lists the properties that are related to full-text catalogs.</span></span>  
  
|<span data-ttu-id="516f5-116">Propriété</span><span class="sxs-lookup"><span data-stu-id="516f5-116">Property</span></span>|<span data-ttu-id="516f5-117">Description</span><span class="sxs-lookup"><span data-stu-id="516f5-117">Description</span></span>|<span data-ttu-id="516f5-118">Fonction</span><span class="sxs-lookup"><span data-stu-id="516f5-118">Function</span></span>|  
|--------------|-----------------|--------------|  
|`AccentSensitivity`|<span data-ttu-id="516f5-119">Respect des accents.</span><span class="sxs-lookup"><span data-stu-id="516f5-119">Accent-sensitivity setting.</span></span>|[<span data-ttu-id="516f5-120">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="516f5-120">FULLTEXTCATALOGPROPERTY</span></span>](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql)|  
|`ImportStatus`|<span data-ttu-id="516f5-121">Indique si le catalogue de texte intégral est en cours d'importation.</span><span class="sxs-lookup"><span data-stu-id="516f5-121">Whether the full-text catalog is being imported.</span></span>|<span data-ttu-id="516f5-122">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="516f5-122">FULLTEXTCATALOGPROPERTY</span></span>|  
|`IndexSize`|<span data-ttu-id="516f5-123">Taille du catalogue de texte intégral en mégaoctets (Mo).</span><span class="sxs-lookup"><span data-stu-id="516f5-123">Size of the full-text catalog in megabytes (MB).</span></span>|<span data-ttu-id="516f5-124">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="516f5-124">FULLTEXTCATALOGPROPERTY</span></span>|  
|`ItemCount`|<span data-ttu-id="516f5-125">Nombre d'éléments indexés de texte intégral actuellement dans le catalogue de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="516f5-125">Number of full-text indexed items currently in the full-text catalog.</span></span>|<span data-ttu-id="516f5-126">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="516f5-126">FULLTEXTCATALOGPROPERTY</span></span>|  
|`MergeStatus`|<span data-ttu-id="516f5-127">Indique si une fusion principale est en cours.</span><span class="sxs-lookup"><span data-stu-id="516f5-127">Whether a master merge is in progress.</span></span>|<span data-ttu-id="516f5-128">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="516f5-128">FULLTEXTCATALOGPROPERTY</span></span>|  
|`PopulateCompletionAge`|<span data-ttu-id="516f5-129">Différence en secondes entre la fin du remplissage du dernier index de texte intégral et le 01/01/1990 00:00:00.</span><span class="sxs-lookup"><span data-stu-id="516f5-129">Difference in seconds between the completion of the last full-text index population and 01/01/1990 00:00:00.</span></span>|<span data-ttu-id="516f5-130">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="516f5-130">FULLTEXTCATALOGPROPERTY</span></span>|  
|`PopulateStatus`|<span data-ttu-id="516f5-131">État de remplissage.</span><span class="sxs-lookup"><span data-stu-id="516f5-131">Populate status.</span></span><br /><br /> [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]|<span data-ttu-id="516f5-132">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="516f5-132">FULLTEXTCATALOGPROPERTY</span></span>|  
|`UniqueKeyCount`|<span data-ttu-id="516f5-133">Nombre de clés uniques dans le catalogue de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="516f5-133">Number of unique keys in the full-text catalog.</span></span>|<span data-ttu-id="516f5-134">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="516f5-134">FULLTEXTCATALOGPROPERTY</span></span>|  
  
  
  
##  <a name="rebuilding-a-full-text-catalog"></a><a name="rebuildone"></a><span data-ttu-id="516f5-135">Reconstruction d’un catalogue de texte intégral</span><span class="sxs-lookup"><span data-stu-id="516f5-135">Rebuilding a Full-Text Catalog</span></span>  
  
#### <a name="to-rebuild-a-full-text-catalog"></a><span data-ttu-id="516f5-136">Pour reconstruire un catalogue de texte intégral</span><span class="sxs-lookup"><span data-stu-id="516f5-136">To rebuild a full-text catalog</span></span>  
  
1.  <span data-ttu-id="516f5-137">Dans l’Explorateur d’objets, développez successivement le serveur, l’option **Bases de données**, puis la base de données contenant le catalogue de texte intégral à reconstruire.</span><span class="sxs-lookup"><span data-stu-id="516f5-137">In Object Explorer, expand the server, expand **Databases**, and then expand the database that contains the full-text catalog that you want to rebuild.</span></span>  
  
2.  <span data-ttu-id="516f5-138">Développez **Stockage**, puis **Catalogues de texte intégral**.</span><span class="sxs-lookup"><span data-stu-id="516f5-138">Expand **Storage**, and then expand **Full Text Catalogs**.</span></span>  
  
3.  <span data-ttu-id="516f5-139">Cliquez avec le bouton droit sur le nom du catalogue de texte intégral que vous souhaitez reconstruire, puis sélectionnez **Reconstruire**.</span><span class="sxs-lookup"><span data-stu-id="516f5-139">Right-click the name of the full-text catalog that you want to rebuild, and select **Rebuild**.</span></span>  
  
4.  <span data-ttu-id="516f5-140">En réponse à la question **Voulez-vous supprimer le catalogue de texte intégral et le reconstruire ?**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="516f5-140">To the question **Do you want to delete the full-text catalog and rebuild it?**, click **OK**.</span></span>  
  
5.  <span data-ttu-id="516f5-141">Dans la boîte de dialogue **Reconstruire le catalogue de texte intégral** , cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="516f5-141">In the **Rebuild Full-Text Catalog** dialog box, click **Close**.</span></span>  
  
  
  
##  <a name="rebuilding-all-full-text-catalogs-for-a-database"></a><a name="rebuildall"></a><span data-ttu-id="516f5-142">Reconstruction de tous les catalogues de texte intégral d’une base de données</span><span class="sxs-lookup"><span data-stu-id="516f5-142">Rebuilding All Full-Text Catalogs for a Database</span></span>  
  
#### <a name="to-rebuild-the-full-text-catalogs-for-a-database"></a><span data-ttu-id="516f5-143">Pour reconstruire les catalogues de texte intégral pour une base de données</span><span class="sxs-lookup"><span data-stu-id="516f5-143">To rebuild the full-text catalogs for a database</span></span>  
  
1.  <span data-ttu-id="516f5-144">Dans l’Explorateur d’objets, développez successivement le serveur, l’option **Bases de données**, puis la base de données contenant les catalogues de texte intégral à reconstruire.</span><span class="sxs-lookup"><span data-stu-id="516f5-144">In Object Explorer, expand the server, expand **Databases**, and then expand the database that contains the full-text catalogs that you want to rebuild.</span></span>  
  
2.  <span data-ttu-id="516f5-145">Développez **Stockage**, puis cliquez avec le bouton droit sur **Catalogues de texte intégral**.</span><span class="sxs-lookup"><span data-stu-id="516f5-145">Expand **Storage**, and then right-click **Full Text Catalogs**.</span></span>  
  
3.  <span data-ttu-id="516f5-146">Sélectionnez **Tout reconstruire**.</span><span class="sxs-lookup"><span data-stu-id="516f5-146">Select **Rebuild All**.</span></span>  
  
4.  <span data-ttu-id="516f5-147">En réponse à la question **Voulez-vous supprimer tous les catalogues de texte intégral et les reconstruire ?**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="516f5-147">To the question, **Do you want to delete all full-text catalogs and rebuild them?**, click **OK**.</span></span>  
  
5.  <span data-ttu-id="516f5-148">Dans la boîte de dialogue **Reconstruire tous les catalogues de texte intégral** , cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="516f5-148">In the **Rebuild All Full-Text Catalogs** dialog box, click **Close**.</span></span>  
  
  
  
##  <a name="removing-a-full-text-catalog-from-a-database"></a><a name="removing"></a><span data-ttu-id="516f5-149">Suppression d’un catalogue de texte intégral d’une base de données</span><span class="sxs-lookup"><span data-stu-id="516f5-149">Removing a Full-Text Catalog from a Database</span></span>  
  
#### <a name="to-remove-a-full-text-catalog-from-a-database"></a><span data-ttu-id="516f5-150">Pour supprimer un catalogue de texte intégral d'une base de données</span><span class="sxs-lookup"><span data-stu-id="516f5-150">To remove a full-text catalog from a database</span></span>  
  
1.  <span data-ttu-id="516f5-151">Dans l’Explorateur d’objets, développez successivement le serveur, l’option **Bases de données**, puis la base de données qui contient le catalogue de texte intégral à supprimer.</span><span class="sxs-lookup"><span data-stu-id="516f5-151">In Object Explorer, expand the server, expand **Databases**, and expand the database that contains the full-text catalog you want to remove.</span></span>  
  
2.  <span data-ttu-id="516f5-152">Développez **Stockage**, puis **Catalogues de texte intégral**.</span><span class="sxs-lookup"><span data-stu-id="516f5-152">Expand **Storage**, and expand **Full Text Catalogs**.</span></span>  
  
3.  <span data-ttu-id="516f5-153">Cliquez avec le bouton droit sur le catalogue de texte intégral à supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="516f5-153">Right-click the full-text catalog that you want to remove, and then select **Delete**.</span></span>  
  
4.  <span data-ttu-id="516f5-154">Dans la boîte de dialogue **Supprimer les objets** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="516f5-154">In the **Delete Objects** dialog box, click **OK**.</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="516f5-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="516f5-155">See Also</span></span>  
 [<span data-ttu-id="516f5-156">CREATE FULLTEXT CATALOG &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="516f5-156">CREATE FULLTEXT CATALOG &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-catalog-transact-sql)  
  
  
