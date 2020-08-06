---
title: Charger des données en masse à l’aide de la destination SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server destination
- loading data
- destinations [Integration Services], SQL Server
- inserting data
- bulk load [Integration Services]
ms.assetid: 8f982f85-a82e-4e2d-9cd8-cd2f85402d8e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 92ed530ae849f7a4ce123cded421ac0cd0c411ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604667"
---
# <a name="bulk-load-data-by-using-the-sql-server-destination"></a><span data-ttu-id="9b601-102">Charger des données en masse à l'aide de la destination SQL Server</span><span class="sxs-lookup"><span data-stu-id="9b601-102">Bulk Load Data by Using the SQL Server Destination</span></span>
  <span data-ttu-id="9b601-103">Pour pouvoir ajouter et configurer une destination [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , le package doit inclure au moins une tâche de flux de données et une source de données.</span><span class="sxs-lookup"><span data-stu-id="9b601-103">To add and configure a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, the package must already include at least one Data Flow task and a data source.</span></span>  
  
### <a name="to-load-data-using-a-sql-server-destination"></a><span data-ttu-id="9b601-104">Pour charger des données à l'aide d'une destination SQL Server</span><span class="sxs-lookup"><span data-stu-id="9b601-104">To load data using a SQL Server destination</span></span>  
  
1.  <span data-ttu-id="9b601-105">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="9b601-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="9b601-106">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="9b601-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="9b601-107">Cliquez sur l’onglet **Flux de données** , puis dans la **Boîte à outils**, faites glisser la destination [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur l’aire de conception.</span><span class="sxs-lookup"><span data-stu-id="9b601-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination to the design surface.</span></span>  
  
4.  <span data-ttu-id="9b601-108">Connectez la destination à une source ou à une transformation précédente du flux de données en faisant glisser un connecteur vers la destination.</span><span class="sxs-lookup"><span data-stu-id="9b601-108">Connect the destination to a source or a previous transformation in the data flow by dragging a connector to the destination.</span></span>  
  
5.  <span data-ttu-id="9b601-109">Double-cliquez sur la destination.</span><span class="sxs-lookup"><span data-stu-id="9b601-109">Double-click the destination.</span></span>  
  
6.  <span data-ttu-id="9b601-110">Dans la boîte de dialogue **Éditeur de destination SQL Server**, dans la page **Gestionnaire de connexions** , sélectionnez un gestionnaire de connexions OLE DB existant ou cliquez sur **Nouveau** pour créer un gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="9b601-110">In the **SQL Server Destination Editor**, on the **Connection Manager** page, select an existing OLE DB connection manager or click **New** to create a new connection manager.</span></span> <span data-ttu-id="9b601-111">Pour plus d’informations, consultez [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="9b601-111">For more information, see [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span></span>  
  
7.  <span data-ttu-id="9b601-112">Pour spécifier la table ou la vue dans laquelle charger les données, effectuez l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="9b601-112">To specify the table or view into which to load the data, do one of the following:</span></span>  
  
    -   <span data-ttu-id="9b601-113">Sélectionnez une table ou une vue existante.</span><span class="sxs-lookup"><span data-stu-id="9b601-113">Select an existing table or view.</span></span>  
  
    -   <span data-ttu-id="9b601-114">Cliquez sur **Nouveau**, puis, dans la boîte de dialogue **Créer une table** , écrivez une instruction SQL qui crée une table ou une vue.</span><span class="sxs-lookup"><span data-stu-id="9b601-114">Click **New**, and in the **Create Table** dialog boxwrite an SQL statement that creates a table or view.</span></span>  
  
        > [!NOTE]  
        >  [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="9b601-115">génère une instruction CREATE TABLE par défaut basée sur la source de données connectée.</span><span class="sxs-lookup"><span data-stu-id="9b601-115">generates a default CREATE TABLE statement based on the connected data source.</span></span> <span data-ttu-id="9b601-116">Cette instruction CREATE TABLE par défaut n'inclut pas l'attribut FILESTREAM, même si la table source inclut une colonne dans laquelle l'attribut FILESTREAM est déclaré.</span><span class="sxs-lookup"><span data-stu-id="9b601-116">This default CREATE TABLE statement will not include the FILESTREAM attribute even if the source table includes a column with the FILESTREAM attribute declared.</span></span> <span data-ttu-id="9b601-117">Pour exécuter un composant [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] avec l'attribut FILESTREAM, implémentez d'abord le stockage FILESTREAM sur la base de données de destination.</span><span class="sxs-lookup"><span data-stu-id="9b601-117">To run an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] component with the FILESTREAM attribute, first implement FILESTREAM storage on the destination database.</span></span> <span data-ttu-id="9b601-118">Ajoutez ensuite l’attribut FILESTREAM à l’instruction CREATE TABLE dans la boîte de dialogue **Créer une table** .</span><span class="sxs-lookup"><span data-stu-id="9b601-118">Then, add the FILESTREAM attribute to the CREATE TABLE statement in the **Create Table** dialog box.</span></span> <span data-ttu-id="9b601-119">Pour plus d’informations, consultez [Données blob &#40;Binary Large Object&#41; &#40;SQL Server&#41;](../../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9b601-119">For more information, see [Binary Large Object &#40;Blob&#41; Data &#40;SQL Server&#41;](../../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span></span>  
  
8.  <span data-ttu-id="9b601-120">Cliquez sur **Mappages** et mappez les colonnes de la liste **Colonnes d’entrée disponibles** aux colonnes de la liste **Colonnes de destination disponibles** en faisant glisser les colonnes d’une liste à l’autre.</span><span class="sxs-lookup"><span data-stu-id="9b601-120">Click **Mappings** and map columns from the **Available Input Columns** list to columns in the **Available Destination Columns** list by dragging columns from one list to another.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9b601-121">La destination mappe automatiquement les colonnes portant le même nom.</span><span class="sxs-lookup"><span data-stu-id="9b601-121">The destination automatically maps same-named columns.</span></span>  
  
9. <span data-ttu-id="9b601-122">Cliquez sur **Avancé** et définissez les options de chargement en masse : **Conserver l’identité**, **Conserver les valeurs NULL**, **Verrou de table**, **Vérifier les contraintes**et **Exécuter les déclencheurs**.</span><span class="sxs-lookup"><span data-stu-id="9b601-122">Click **Advanced** and set the bulk load options: **Keep identity**, **Keep nulls**, **Table lock**, **Check constraints**, and **Fire triggers**.</span></span>  
  
     <span data-ttu-id="9b601-123">Si vous le souhaitez, indiquez la première et la dernière ligne d'entrée à insérer, le nombre maximal d'erreurs avant arrêt de l'opération d'insertion et les colonnes sur lesquelles l'insertion est triée.</span><span class="sxs-lookup"><span data-stu-id="9b601-123">Optionally, specify the first and last input rows to insert, the maximum number of errors that can occur before the insert operation stops, and the columns on which the insert is sorted.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9b601-124">L'ordre de tri est déterminé par l'ordre dans lequel les colonnes apparaissent dans la liste.</span><span class="sxs-lookup"><span data-stu-id="9b601-124">The sort order is determined by the order in which the columns are listed.</span></span>  
  
10. <span data-ttu-id="9b601-125">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b601-125">Click **OK**.</span></span>  
  
11. <span data-ttu-id="9b601-126">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="9b601-126">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b601-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9b601-127">See Also</span></span>  
 <span data-ttu-id="9b601-128">[SQL Server Destination](sql-server-destination.md) </span><span class="sxs-lookup"><span data-stu-id="9b601-128">[SQL Server Destination](sql-server-destination.md) </span></span>  
 <span data-ttu-id="9b601-129">[Transformations Integration Services](transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="9b601-129">[Integration Services Transformations](transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="9b601-130">[Chemins Integration Services](integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="9b601-130">[Integration Services Paths](integration-services-paths.md) </span></span>  
 [<span data-ttu-id="9b601-131">tâche de flux de données</span><span class="sxs-lookup"><span data-stu-id="9b601-131">Data Flow Task</span></span>](../control-flow/data-flow-task.md)  
  
  
