---
title: Destination SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlserverdest.f1
helpviewer_keywords:
- SQL Server destination
- loading data
- destinations [Integration Services], SQL Server
- inserting data
- bulk load [Integration Services]
ms.assetid: a0227cd8-6944-4547-87e8-7b2507e26442
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fcd65007e1e6af36386cb2ceba1f7242305b81a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697032"
---
# <a name="sql-server-destination"></a><span data-ttu-id="e5353-102">Destination SQL Server</span><span class="sxs-lookup"><span data-stu-id="e5353-102">SQL Server Destination</span></span>
  <span data-ttu-id="e5353-103">La destination SQL Server se connecte à une base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] locale et charge en masse des données dans des tables et des vues [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e5353-103">The SQL Server destination connects to a local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database and bulk loads data into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables and views.</span></span> <span data-ttu-id="e5353-104">Vous ne pouvez pas utiliser la destination SQL Server dans des packages ayant accès à une base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur un serveur distant.</span><span class="sxs-lookup"><span data-stu-id="e5353-104">You cannot use the SQL Server destination in packages that access a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database on a remote server.</span></span> <span data-ttu-id="e5353-105">Les packages doivent plutôt utiliser la destination OLE DB.</span><span class="sxs-lookup"><span data-stu-id="e5353-105">Instead, the packages should use the OLE DB destination.</span></span> <span data-ttu-id="e5353-106">Pour plus d’informations, consultez [OLE DB Destination](ole-db-destination.md).</span><span class="sxs-lookup"><span data-stu-id="e5353-106">For more information, see [OLE DB Destination](ole-db-destination.md).</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="e5353-107">Autorisations</span><span class="sxs-lookup"><span data-stu-id="e5353-107">Permissions</span></span>  
 <span data-ttu-id="e5353-108">Les utilisateurs qui exécutent des packages incluant la destination SQL Server nécessitent l'autorisation « Create global objects » (Créer des objets globaux).</span><span class="sxs-lookup"><span data-stu-id="e5353-108">Users who execute packages that include the SQL Server destination require the "Create global objects" permission.</span></span> <span data-ttu-id="e5353-109">Vous pouvez attribuer cette autorisation aux utilisateurs à l’aide de l’outil Stratégie de sécurité locale accessible dans le menu **Outils d’administration** .</span><span class="sxs-lookup"><span data-stu-id="e5353-109">You can grant this permission to users by using the Local Security Policy tool opened from the **Administrative Tools** menu.</span></span> <span data-ttu-id="e5353-110">Si vous recevez un message d'erreur lors de l'exécution d'un package qui utilise la destination SQL Server, assurez-vous que le compte exécutant le package a l'autorisation « Create global objects » (Créer des objets globaux).</span><span class="sxs-lookup"><span data-stu-id="e5353-110">If you receive an error message when executing a package that uses the SQL Server destination, make sure that the account running the package has the "Create global objects" permission.</span></span>  
  
## <a name="bulk-inserts"></a><span data-ttu-id="e5353-111">Insertions en bloc</span><span class="sxs-lookup"><span data-stu-id="e5353-111">Bulk Inserts</span></span>  
 <span data-ttu-id="e5353-112">Si vous tentez d'utiliser la destination SQL Server pour charger en masse des données dans une base de données SQL Server distante, il est possible qu'un message d'erreur semblable au message suivant s'affiche : « Un enregistrement OLE DB est disponible.</span><span class="sxs-lookup"><span data-stu-id="e5353-112">If you attempt to use the SQL Server destination to bulk load data into a remote SQL Server database, you may see an error message similar to the following: "An OLE DB record is available.</span></span> <span data-ttu-id="e5353-113">Source : « Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client » Hresult : 0x80040E14 Description : « Chargement en masse impossible, car l’objet de mappage de fichier SSIS 'Global\DTSQLIMPORT ' n’a pas pu être ouvert.</span><span class="sxs-lookup"><span data-stu-id="e5353-113">Source: "Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client" Hresult: 0x80040E14 Description: "Could not bulk load because SSIS file mapping object 'Global\DTSQLIMPORT ' could not be opened.</span></span> <span data-ttu-id="e5353-114">Code d'erreur du système d'exploitation 2 (Le système ne trouve pas le fichier spécifié.).</span><span class="sxs-lookup"><span data-stu-id="e5353-114">Operating system error code 2 (The system cannot find the file specified.).</span></span> <span data-ttu-id="e5353-115">Vérifiez que vous accédez à un serveur local par le biais de la sécurité Windows." »</span><span class="sxs-lookup"><span data-stu-id="e5353-115">Make sure you are accessing a local server via Windows security.""</span></span>  
  
 <span data-ttu-id="e5353-116">La destination SQL Server offre la même insertion rapide de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que la tâche d’insertion en bloc ; toutefois, l’utilisation d’une destination SQL Server permet à un package d’appliquer des transformations à des données de colonne avant que les données ne soient chargées dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5353-116">The SQL Server destination offers the same high-speed insertion of data into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that the Bulk Insert task provides; however, by using the SQL Server destination, a package can apply transformations to column data before the data is loaded into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="e5353-117">Pour le chargement de données dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], envisagez l'utilisation de la destination SQL Server plutôt que la destination OLE DB.</span><span class="sxs-lookup"><span data-stu-id="e5353-117">For loading data into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you should consider using the SQL Server destination instead of the OLE DB destination.</span></span>  
  
### <a name="bulk-insert-options"></a><span data-ttu-id="e5353-118">Options d'insertion en bloc</span><span class="sxs-lookup"><span data-stu-id="e5353-118">Bulk Insert Options</span></span>  
 <span data-ttu-id="e5353-119">Si la destination SQL Server utilise un mode d'accès aux données par chargement rapide, vous pouvez spécifier les options de chargement rapide suivantes :</span><span class="sxs-lookup"><span data-stu-id="e5353-119">If the SQL Server destination uses a fast-load data access mode, you can specify the following fast load options:</span></span>  
  
-   <span data-ttu-id="e5353-120">Conservation des valeurs d'identité du fichier de données importé ou utilisation de valeurs uniques assignées par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5353-120">Retain identity values from the imported data file, or use unique values assigned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="e5353-121">Conservation des valeurs nulles durant l'opération de chargement en masse.</span><span class="sxs-lookup"><span data-stu-id="e5353-121">Retain null values during the bulk load operation.</span></span>  
  
-   <span data-ttu-id="e5353-122">Vérification des contraintes sur la table ou la vue cible durant l'opération d'importation en bloc.</span><span class="sxs-lookup"><span data-stu-id="e5353-122">Verify constraints on the target table or view during the bulk import operation.</span></span>  
  
-   <span data-ttu-id="e5353-123">Acquisition d'un verrou au niveau de la table pour la durée de l'opération de chargement en masse.</span><span class="sxs-lookup"><span data-stu-id="e5353-123">Acquire a table-level lock for the duration of the bulk load operation.</span></span>  
  
-   <span data-ttu-id="e5353-124">Exécution de déclencheurs d'insertion définis sur la table de destination durant l'opération de chargement en masse.</span><span class="sxs-lookup"><span data-stu-id="e5353-124">Execute insert triggers defined on the destination table during the bulk load operation.</span></span>  
  
-   <span data-ttu-id="e5353-125">Spécification du numéro de la première ligne de l'entrée à charger durant l'opération d'insertion en bloc.</span><span class="sxs-lookup"><span data-stu-id="e5353-125">Specify the number of the first row in the input to load during the bulk insert operation.</span></span>  
  
-   <span data-ttu-id="e5353-126">Spécification du numéro de la dernière ligne de l'entrée à charger durant l'opération d'insertion en bloc.</span><span class="sxs-lookup"><span data-stu-id="e5353-126">Specify the number of the last row in the input to load during the bulk insert operation.</span></span>  
  
-   <span data-ttu-id="e5353-127">Spécification du nombre maximal d'erreurs tolérées avant l'annulation de l'opération de chargement en masse.</span><span class="sxs-lookup"><span data-stu-id="e5353-127">Specify the maximum number of errors allowed before the bulk load operation is canceled.</span></span> <span data-ttu-id="e5353-128">Chaque ligne ne pouvant pas être importée est comptée comme une erreur.</span><span class="sxs-lookup"><span data-stu-id="e5353-128">Each row that cannot be imported is counted as one error.</span></span>  
  
-   <span data-ttu-id="e5353-129">Spécification des colonnes de l'entrée qui contiennent des données triées.</span><span class="sxs-lookup"><span data-stu-id="e5353-129">Specify the columns in the input that contain sorted data.</span></span>  
  
 <span data-ttu-id="e5353-130">Pour plus d’informations sur les options de chargement en masse, consultez [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e5353-130">For more information about bulk load options, see [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
#### <a name="performance-improvements"></a><span data-ttu-id="e5353-131">Optimisation des performances</span><span class="sxs-lookup"><span data-stu-id="e5353-131">Performance Improvements</span></span>  
 <span data-ttu-id="e5353-132">Pour améliorer les performances d'une insertion en bloc et l'accès aux données de table durant l'opération d'insertion en bloc, vous devez modifier les options par défaut comme suit :</span><span class="sxs-lookup"><span data-stu-id="e5353-132">To improve the performance of a bulk insert and the access to table data during the bulk insert operation, you should change the default options as follows:</span></span>  
  
-   <span data-ttu-id="e5353-133">Ne pas vérifier les contraintes sur la table ou la vue cible durant l'opération d'importation en bloc.</span><span class="sxs-lookup"><span data-stu-id="e5353-133">Do not verify constraints on the target table or view during the bulk import operation.</span></span>  
  
-   <span data-ttu-id="e5353-134">Ne pas exécuter de déclencheurs d'insertion définis sur la table de destination durant l'opération de chargement en masse.</span><span class="sxs-lookup"><span data-stu-id="e5353-134">Do not execute insert triggers defined on the destination table during the bulk load operation.</span></span>  
  
-   <span data-ttu-id="e5353-135">Ne pas appliquer de verrou sur la table.</span><span class="sxs-lookup"><span data-stu-id="e5353-135">Do not apply a lock to the table.</span></span> <span data-ttu-id="e5353-136">De cette manière, la table reste disponible pour les autres utilisateurs et applications durant l'opération d'insertion en bloc.</span><span class="sxs-lookup"><span data-stu-id="e5353-136">That way, the table remains available to other users and applications during the bulk insert operation.</span></span>  
  
## <a name="configuration-of-the-sql-server-destination"></a><span data-ttu-id="e5353-137">Configuration de la destination SQL Server</span><span class="sxs-lookup"><span data-stu-id="e5353-137">Configuration of the SQL Server Destination</span></span>  
 <span data-ttu-id="e5353-138">Vous pouvez configurer la destination SQL Server de plusieurs manières :</span><span class="sxs-lookup"><span data-stu-id="e5353-138">You can configure the SQL Server destination in the following ways:</span></span>  
  
-   <span data-ttu-id="e5353-139">Spécifiez la table ou la vue dans laquelle charger les données en masse.</span><span class="sxs-lookup"><span data-stu-id="e5353-139">Specify the table or view into which to bulk load the data.</span></span>  
  
-   <span data-ttu-id="e5353-140">Personnalisez l'opération de chargement en masse en spécifiant des options telles que la vérification des contraintes.</span><span class="sxs-lookup"><span data-stu-id="e5353-140">Customize the bulk load operation by specifying options such as whether to check constraints.</span></span>  
  
-   <span data-ttu-id="e5353-141">Indiquez si toutes les lignes doivent être validées en un seul traitement ou définissez le nombre maximum de lignes à valider en tant que traitement.</span><span class="sxs-lookup"><span data-stu-id="e5353-141">Specify whether all rows commit in one batch or set the maximum number of rows to commit as a batch.</span></span>  
  
-   <span data-ttu-id="e5353-142">Spécifiez un délai d'expiration pour l'opération de chargement en masse.</span><span class="sxs-lookup"><span data-stu-id="e5353-142">Specify a time-out for the bulk load operation.</span></span>  
  
 <span data-ttu-id="e5353-143">Cette destination utilise un gestionnaire de connexions OLE DB pour se connecter à une source de données et le gestionnaire de connexions spécifie le fournisseur OLE DB à utiliser.</span><span class="sxs-lookup"><span data-stu-id="e5353-143">This destination uses an OLE DB connection manager to connect to a data source, and the connection manager specifies the OLE DB provider to use.</span></span> <span data-ttu-id="e5353-144">Pour plus d’informations, consultez [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="e5353-144">For more information, see [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span></span>  
  
 <span data-ttu-id="e5353-145">Un projet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] fournit également l'objet de source de données à partir duquel vous pouvez créer un gestionnaire de connexions OLE DB.</span><span class="sxs-lookup"><span data-stu-id="e5353-145">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project also provides the data source object from which you can create an OLE DB connection manager.</span></span> <span data-ttu-id="e5353-146">Les sources de données et les vues de sources de données sont ainsi disponibles pour la destination SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e5353-146">This makes data sources and data source views available to the SQL Server destination.</span></span>  
  
 <span data-ttu-id="e5353-147">La destination SQL Server possède une entrée.</span><span class="sxs-lookup"><span data-stu-id="e5353-147">The SQL Server destination has one input.</span></span> <span data-ttu-id="e5353-148">Elle ne prend pas en charge de sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="e5353-148">It does not support an error output.</span></span>  
  
 <span data-ttu-id="e5353-149">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="e5353-149">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="e5353-150">Pour plus d’informations sur les propriétés définissables dans la boîte de dialogue **Éditeur de destination SQL**, cliquez sur l’une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="e5353-150">For more information about the properties that you can set in the **SQL Server Destination Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="e5353-151">Éditeur de destination SQL &#40;page Gestionnaire de connexions&#41;</span><span class="sxs-lookup"><span data-stu-id="e5353-151">SQL Destination Editor &#40;Connection Manager Page&#41;</span></span>](../sql-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="e5353-152">Éditeur de destination SQL &#40;page Mappages&#41;</span><span class="sxs-lookup"><span data-stu-id="e5353-152">SQL Destination Editor &#40;Mappings Page&#41;</span></span>](../sql-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="e5353-153">Éditeur de destination SQL &#40;page Avancé&#41;</span><span class="sxs-lookup"><span data-stu-id="e5353-153">SQL Destination Editor &#40;Advanced Page&#41;</span></span>](../sql-destination-editor-advanced-page.md)  
  
 <span data-ttu-id="e5353-154">La boîte de dialogue **Éditeur avancé** reflète les propriétés qui peuvent être définies par programmation.</span><span class="sxs-lookup"><span data-stu-id="e5353-154">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="e5353-155">Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur avancé** ou par programmation, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="e5353-155">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="e5353-156">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="e5353-156">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="e5353-157">Propriétés personnalisées de la destination SQL Server</span><span class="sxs-lookup"><span data-stu-id="e5353-157">SQL Server Destination Custom Properties</span></span>](sql-server-destination-custom-properties.md)  
  
 <span data-ttu-id="e5353-158">Pour plus d'informations sur la définition des propriétés, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="e5353-158">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="e5353-159">Charger des données en masse à l'aide de la destination SQL Server</span><span class="sxs-lookup"><span data-stu-id="e5353-159">Bulk Load Data by Using the SQL Server Destination</span></span>](sql-server-destination.md)  
  
-   [<span data-ttu-id="e5353-160">Définir les propriétés d’un composant de flux de données</span><span class="sxs-lookup"><span data-stu-id="e5353-160">Set the Properties of a Data Flow Component</span></span>](set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="e5353-161">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="e5353-161">Related Tasks</span></span>  
  
-   [<span data-ttu-id="e5353-162">Charger des données en masse à l'aide de la destination SQL Server</span><span class="sxs-lookup"><span data-stu-id="e5353-162">Bulk Load Data by Using the SQL Server Destination</span></span>](sql-server-destination.md)  
  
-   [<span data-ttu-id="e5353-163">Définir les propriétés d’un composant de flux de données</span><span class="sxs-lookup"><span data-stu-id="e5353-163">Set the Properties of a Data Flow Component</span></span>](set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-content"></a><span data-ttu-id="e5353-164">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="e5353-164">Related Content</span></span>  
  
-   <span data-ttu-id="e5353-165">Article technique, [You may get "Unable to prepare the SSIS bulk insert for data insertion" error on UAC enabled systems](https://go.microsoft.com/fwlink/?LinkId=199482), sur support.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e5353-165">Technical article, [You may get "Unable to prepare the SSIS bulk insert for data insertion" error on UAC enabled systems](https://go.microsoft.com/fwlink/?LinkId=199482), on support.microsoft.com.</span></span>  
  
-   <span data-ttu-id="e5353-166">Article technique, [Guide des performances de chargement des données](https://go.microsoft.com/fwlink/?LinkId=233700), sur le site msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e5353-166">Technical article, [The Data Loading Performance Guide](https://go.microsoft.com/fwlink/?LinkId=233700), on msdn.microsoft.com.</span></span>  
  
-   <span data-ttu-id="e5353-167">Article technique, [Using SQL Server Integration Services to Bulk Load Data](https://go.microsoft.com/fwlink/?LinkId=233701), sur le site simple-talk.com.</span><span class="sxs-lookup"><span data-stu-id="e5353-167">Technical article, [Using SQL Server Integration Services to Bulk Load Data](https://go.microsoft.com/fwlink/?LinkId=233701), on simple-talk.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5353-168">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e5353-168">See Also</span></span>  
 [<span data-ttu-id="e5353-169">Flux de données</span><span class="sxs-lookup"><span data-stu-id="e5353-169">Data Flow</span></span>](data-flow.md)  
  
  
