---
title: Implémenter une transformation de recherche en mode cache complet à l’aide du gestionnaire de connexions OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Lookup transformation [Integration Services]
ms.assetid: c4150e1b-bdff-4f7a-af4c-3401c34def83
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f77a753dd71bc487d57492371906fc48bc114357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613098"
---
# <a name="implement-a-lookup-transformation-in-full-cache-mode-using-the-ole-db-connection-manager"></a><span data-ttu-id="33b59-102">Implémenter une transformation de recherche en mode Cache complet à l'aide du gestionnaire de connexions OLE DB</span><span class="sxs-lookup"><span data-stu-id="33b59-102">Implement a Lookup Transformation in Full Cache Mode Using the OLE DB Connection Manager</span></span>
  <span data-ttu-id="33b59-103">Vous pouvez configurer la transformation de recherche afin qu'elle utilise le mode Cache complet et un gestionnaire de connexions OLE DB.</span><span class="sxs-lookup"><span data-stu-id="33b59-103">You can configure the Lookup transformation to use full cache mode and an OLE DB connection manager.</span></span> <span data-ttu-id="33b59-104">Dans le mode Cache complet, le dataset de référence est chargé dans le cache avant l’exécution de la transformation de recherche.</span><span class="sxs-lookup"><span data-stu-id="33b59-104">In the full cache mode, the reference dataset is loaded into cache before the Lookup transformation runs.</span></span>  
  
 <span data-ttu-id="33b59-105">La transformation de recherche effectue des recherches en joignant les données des colonnes d'entrée d'une source de données connectée aux colonnes d'un dataset de référence.</span><span class="sxs-lookup"><span data-stu-id="33b59-105">The Lookup transformation performs lookups by joining data in input columns from a connected data source with columns in a reference dataset.</span></span> <span data-ttu-id="33b59-106">Pour plus d’informations, voir [Lookup Transformation](../data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="33b59-106">For more information, see [Lookup Transformation](../data-flow/transformations/lookup-transformation.md).</span></span>  
  
 <span data-ttu-id="33b59-107">Lorsque vous configurez la transformation de recherche pour utiliser un gestionnaire de connexions OLE DB, vous sélectionnez une table, une vue ou une requête SQL pour générer le dataset de référence.</span><span class="sxs-lookup"><span data-stu-id="33b59-107">When you configure the Lookup transformation to use an OLE DB connection manager, you select a table, view, or SQL query to generate the reference dataset.</span></span>  
  
### <a name="to-implement-a-lookup-transformation-in-full-cache-mode-by-using-ole-db-connection-manager"></a><span data-ttu-id="33b59-108">Pour implémenter une transformation de recherche en mode Cache complet à l'aide du gestionnaire de connexions OLE DB</span><span class="sxs-lookup"><span data-stu-id="33b59-108">To implement a Lookup transformation in full cache mode by using OLE DB connection manager</span></span>  
  
1.  <span data-ttu-id="33b59-109">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui contient le package souhaité, puis double-cliquez sur le package dans l'Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="33b59-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want, and then double-click the package in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="33b59-110">Sous l’onglet **Flux de données** , faites glisser la transformation de recherche à partir de la **Boîte à outils**jusqu’à l’aire de conception.</span><span class="sxs-lookup"><span data-stu-id="33b59-110">On the **Data Flow** tab, from the **Toolbox**, drag the Lookup transformation to the design surface.</span></span>  
  
3.  <span data-ttu-id="33b59-111">Connectez la transformation de recherche au flux de données en faisant glisser un connecteur à partir d'une source ou d'une transformation précédente jusqu'à la transformation de recherche.</span><span class="sxs-lookup"><span data-stu-id="33b59-111">Connect the Lookup transformation to the data flow by dragging a connector from a source or a previous transformation to the Lookup transformation.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="33b59-112">Une transformation de recherche peut ne pas se valider si cette transformation se connecte à un fichier plat qui contient un champ Date vide.</span><span class="sxs-lookup"><span data-stu-id="33b59-112">A Lookup transformation might not validate if that transformation connects to a flat file that contains an empty date field.</span></span> <span data-ttu-id="33b59-113">La validation de la transformation dépend si le gestionnaire de connexions pour le fichier plat a été configuré pour conserver des valeurs NULL.</span><span class="sxs-lookup"><span data-stu-id="33b59-113">Whether the transformation validates depends on whether the connection manager for the flat file has been configured to retain null values.</span></span> <span data-ttu-id="33b59-114">Pour que la validation de la transformation de recherche soit validée, dans **l’Éditeur de source de fichier plat**, dans la **page Gestionnaire de connexions**, sélectionnez l’option **Conserver les valeurs NULL de la source comme valeurs NULL dans le flux de données** .</span><span class="sxs-lookup"><span data-stu-id="33b59-114">To ensure that the Lookup transformation validates, in the **Flat File Source Editor**, on the **Connection Manager Page**, select the **Retain null values from the source as null values in the data flow** option.</span></span>  
  
4.  <span data-ttu-id="33b59-115">Double-cliquez sur la transformation source ou précédente pour configurer le composant.</span><span class="sxs-lookup"><span data-stu-id="33b59-115">Double-click the source or previous transformation to configure the component.</span></span>  
  
5.  <span data-ttu-id="33b59-116">Double-cliquez sur la transformation de recherche, puis dans **l’Éditeur de transformation de recherche**, dans la page **Général** , sélectionnez **Cache complet**.</span><span class="sxs-lookup"><span data-stu-id="33b59-116">Double-click the Lookup transformation, and then in the **Lookup Transformation Editor**, on the **General** page, select **Full cache**.</span></span>  
  
6.  <span data-ttu-id="33b59-117">Dans la zone **Type de connexion** , sélectionnez **Gestionnaire de connexions OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="33b59-117">In the **Connection type** area, select **OLE DB connection manager**.</span></span>  
  
7.  <span data-ttu-id="33b59-118">Dans la liste **Spécifier comment gérer les lignes sans entrées correspondantes** , sélectionnez une option de gestion des erreurs pour les lignes sans entrées correspondantes.</span><span class="sxs-lookup"><span data-stu-id="33b59-118">In the **Specify how to handle rows with no matching entries** list, select an error handling option for rows without matching entries.</span></span>  
  
8.  <span data-ttu-id="33b59-119">Dans la page Connexion, sélectionnez un gestionnaire de connexions dans la liste **Gestionnaire de connexions OLE DB** ou cliquez sur **Nouveau** pour créer un gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="33b59-119">On the Connection page, select a connection manager from the **OLE DB connection manager** list or click **New** to create a new connection manager.</span></span> <span data-ttu-id="33b59-120">Pour plus d’informations, consultez [OLE DB Connection Manager](ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="33b59-120">For more information, see [OLE DB Connection Manager](ole-db-connection-manager.md).</span></span>  
  
9. <span data-ttu-id="33b59-121">Exécutez l'une des tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="33b59-121">Do one of the following tasks:</span></span>  
  
    -   <span data-ttu-id="33b59-122">Cliquez sur **Utiliser une table ou une vue**, puis sélectionnez une table ou une vue, ou cliquez sur **Nouveau** pour créer une table ou une vue.</span><span class="sxs-lookup"><span data-stu-id="33b59-122">Click **Use a table or a view**, and then either select a table or view, or click **New** to create a table or view.</span></span>  
  
         <span data-ttu-id="33b59-123">-ou-</span><span class="sxs-lookup"><span data-stu-id="33b59-123">-or-</span></span>  
  
    -   <span data-ttu-id="33b59-124">Cliquez sur **Utiliser les résultats d’une requête SQL**, puis générez une requête dans la fenêtre **Commande SQL** , ou cliquez sur **Générer la requête** pour générer une requête à l’aide des outils graphiques du **Générateur de requêtes** .</span><span class="sxs-lookup"><span data-stu-id="33b59-124">Click **Use results of an SQL query**, and then build a query in the **SQL Command** window, or click **Build Query** to build a query by using the graphical tools that the **Query Builder** provides.</span></span>  
  
         <span data-ttu-id="33b59-125">-ou-</span><span class="sxs-lookup"><span data-stu-id="33b59-125">-or-</span></span>  
  
    -   <span data-ttu-id="33b59-126">Vous pouvez aussi cliquer sur **Parcourir** pour importer une instruction SQL à partir d’un fichier.</span><span class="sxs-lookup"><span data-stu-id="33b59-126">Alternatively, click **Browse** to import an SQL statement from a file.</span></span>  
  
     <span data-ttu-id="33b59-127">Pour valider la requête SQL, cliquez sur **Analyser la requête**.</span><span class="sxs-lookup"><span data-stu-id="33b59-127">To validate the SQL query, click **Parse Query**.</span></span>  
  
     <span data-ttu-id="33b59-128">Pour afficher un échantillon des données, cliquez sur **Aperçu**.</span><span class="sxs-lookup"><span data-stu-id="33b59-128">To view a sample of the data, click **Preview**.</span></span>  
  
10. <span data-ttu-id="33b59-129">Cliquez sur la page **Colonnes** , puis faites glisser au moins une colonne de la liste **Colonnes d’entrée disponibles** vers une colonne de la liste **Colonnes de recherche disponibles** .</span><span class="sxs-lookup"><span data-stu-id="33b59-129">Click the **Columns** page, and then from the **Available Input Columns** list, drag at least one column to a column in the **Available Lookup Column** list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="33b59-130">La transformation de recherche mappe automatiquement les colonnes ayant le même nom et le même type de données.</span><span class="sxs-lookup"><span data-stu-id="33b59-130">The Lookup transformation automatically maps columns that have the same name and the same data type.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="33b59-131">Les types de données des colonnes doivent correspondre pour que les colonnes puissent être mappées.</span><span class="sxs-lookup"><span data-stu-id="33b59-131">Columns must have matching data types to be mapped.</span></span> <span data-ttu-id="33b59-132">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="33b59-132">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
11. <span data-ttu-id="33b59-133">Incluez des colonnes de recherche dans la sortie en exécutant les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="33b59-133">Include lookup columns in the output by doing the following tasks:</span></span>  
  
    1.  <span data-ttu-id="33b59-134">Dans la liste **Colonnes de recherche disponibles** ,</span><span class="sxs-lookup"><span data-stu-id="33b59-134">In the **Available Lookup Columns** list.</span></span> <span data-ttu-id="33b59-135">sélectionnez des colonnes.</span><span class="sxs-lookup"><span data-stu-id="33b59-135">select columns.</span></span>  
  
    2.  <span data-ttu-id="33b59-136">Dans la liste **Opération de recherche** , spécifiez si les valeurs des colonnes de recherche remplacent les valeurs des colonnes d’entrée ou si elles sont écrites dans une nouvelle colonne.</span><span class="sxs-lookup"><span data-stu-id="33b59-136">In **Lookup Operation** list, specify whether the values from the lookup columns replace values in the input column or are written to a new column.</span></span>  
  
12. <span data-ttu-id="33b59-137">Pour configurer la sortie d’erreur, cliquez sur la page **Sortie d’erreur** et définissez les options de gestion des erreurs.</span><span class="sxs-lookup"><span data-stu-id="33b59-137">To configure the error output, click the **Error Output** page and set the error handling options.</span></span> <span data-ttu-id="33b59-138">Pour plus d’informations, consultez [Éditeur de transformation de recherche &#40;page Sortie d’erreur&#41;](../lookup-transformation-editor-error-output-page.md).</span><span class="sxs-lookup"><span data-stu-id="33b59-138">For more information, see [Lookup Transformation Editor &#40;Error Output Page&#41;](../lookup-transformation-editor-error-output-page.md).</span></span>  
  
13. <span data-ttu-id="33b59-139">Cliquez sur **OK** pour enregistrer les modifications apportées à la transformation de recherche, puis exécutez le package.</span><span class="sxs-lookup"><span data-stu-id="33b59-139">Click **OK** to save your changes to the Lookup transformation, and then run the package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33b59-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="33b59-140">See Also</span></span>  
 <span data-ttu-id="33b59-141">[Implémenter une transformation de recherche en mode Cache complet à l’aide du gestionnaire de connexions du cache](lookup-transformation-full-cache-mode-ole-db-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="33b59-141">[Implement a Lookup Transformation in Full Cache Mode Using the Cache Connection Manager](lookup-transformation-full-cache-mode-ole-db-connection-manager.md) </span></span>  
 <span data-ttu-id="33b59-142">[Implémenter une recherche en mode Aucun cache ou Cache partiel](../data-flow/transformations/implement-a-lookup-in-no-cache-or-partial-cache-mode.md) </span><span class="sxs-lookup"><span data-stu-id="33b59-142">[Implement a Lookup in No Cache or Partial Cache Mode](../data-flow/transformations/implement-a-lookup-in-no-cache-or-partial-cache-mode.md) </span></span>  
 [<span data-ttu-id="33b59-143">Transformations Integration Services</span><span class="sxs-lookup"><span data-stu-id="33b59-143">Integration Services Transformations</span></span>](../data-flow/transformations/integration-services-transformations.md)  
  
  
