---
title: Exécuter l’Assistant importation et exportation SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Import and Export Wizard
- starting SQL Server Import and Export Wizard
- Import and Export Wizard
- starting Import and Export Wizard
ms.assetid: 5fc4f6d1-1f6f-444e-9aeb-827f85e1c405
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 008c541b1f1a295057b0ee7cc384982627b9689a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611871"
---
# <a name="run-the-sql-server-import-and-export-wizard"></a><span data-ttu-id="2e96b-102">Exécuter l'Assistant Importation et Exportation SQL Server</span><span class="sxs-lookup"><span data-stu-id="2e96b-102">Run the SQL Server Import and Export Wizard</span></span>
  <span data-ttu-id="2e96b-103">L'Assistant Importation et Exportation [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] constitue la méthode la plus simple pour copier des données entre des sources de données et pour construire des packages de base.</span><span class="sxs-lookup"><span data-stu-id="2e96b-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard provides the simplest method of copying data between data sources and of constructing basic packages.</span></span> <span data-ttu-id="2e96b-104">Pour plus d’informations sur l’Assistant, consultez [SQL Server Assistant importation et exportation](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="2e96b-104">For more information about the wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="2e96b-105">Pour obtenir une vidéo qui montre comment utiliser l’Assistant importation et exportation SQL Server pour créer un package qui exporte des données à partir d’une base de données SQL Server vers une feuille de calcul Microsoft Excel, consultez [exportation de données SQL Server vers Excel (SQL Server vidéo)](https://go.microsoft.com/fwlink/?LinkId=131024).</span><span class="sxs-lookup"><span data-stu-id="2e96b-105">For a video that demonstrates how to use the SQL Server Import and Export Wizard to create a package that exports data from a SQL Server database to a Microsoft Excel spreadsheet, see [Exporting SQL Server Data to Excel (SQL Server Video)](https://go.microsoft.com/fwlink/?LinkId=131024).</span></span>  
  
### <a name="to-start-the-sql-server-import-and-export-wizard"></a><span data-ttu-id="2e96b-106">Pour démarrer l'Assistant Importation et Exportation SQL Server</span><span class="sxs-lookup"><span data-stu-id="2e96b-106">To start the SQL Server Import and Export Wizard</span></span>  
  
-   <span data-ttu-id="2e96b-107">Dans le menu **Démarrer** , pointez sur **tous les programmes**, pointez sur**Microsoft SQL Server** , puis cliquez sur **Importer et exporter des données**.</span><span class="sxs-lookup"><span data-stu-id="2e96b-107">On the **Start** menu, point to **All Programs**, point to**Microsoft SQL Server** , and then click **Import and Export Data**.</span></span>  
  
     <span data-ttu-id="2e96b-108">-ou-</span><span class="sxs-lookup"><span data-stu-id="2e96b-108">-or-</span></span>  
  
     <span data-ttu-id="2e96b-109">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] , cliquez avec le bouton droit sur le dossier **packages SSIS** , puis cliquez sur **Assistant SSISImport et exportation**.</span><span class="sxs-lookup"><span data-stu-id="2e96b-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], right-click the **SSIS Packages** folder, and then click **SSISImport and Export Wizard**.</span></span>  
  
     <span data-ttu-id="2e96b-110">-ou-</span><span class="sxs-lookup"><span data-stu-id="2e96b-110">-or-</span></span>  
  
     <span data-ttu-id="2e96b-111">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] , dans le menu **projet** , cliquez sur **Assistant SSISImport et exportation**.</span><span class="sxs-lookup"><span data-stu-id="2e96b-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Project** menu, click **SSISImport and Export Wizard**.</span></span>  
  
     <span data-ttu-id="2e96b-112">-ou-</span><span class="sxs-lookup"><span data-stu-id="2e96b-112">-or-</span></span>  
  
     <span data-ttu-id="2e96b-113">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)] type de serveur, développez bases de données, cliquez avec le bouton droit sur une base de données, pointez sur **tâches**, puis cliquez sur **importer des données** ou **exporter des données**.</span><span class="sxs-lookup"><span data-stu-id="2e96b-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] server type, expand Databases, right-click a database, point to **Tasks**, and then click **Import Data** or **Export data**.</span></span>  
  
     <span data-ttu-id="2e96b-114">-ou-</span><span class="sxs-lookup"><span data-stu-id="2e96b-114">-or-</span></span>  
  
     <span data-ttu-id="2e96b-115">Dans une fenêtre d'invite de commandes, exécutez DTSWizard.exe qui se trouve dans C:\Program Files\Microsoft SQL Server\100\DTS\Binn.</span><span class="sxs-lookup"><span data-stu-id="2e96b-115">In a command prompt window, run DTSWizard.exe, located in C:\Program Files\Microsoft SQL Server\100\DTS\Binn.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2e96b-116">Sur un ordinateur 64 bits, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installe la version 64 bits de l'Assistant Importation et Exportation [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (DTSWizard.exe).</span><span class="sxs-lookup"><span data-stu-id="2e96b-116">On a 64-bit computer, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installs the 64-bit version of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard (DTSWizard.exe).</span></span> <span data-ttu-id="2e96b-117">Toutefois, certaines sources de données, telles qu'Access ou Excel, ne dispose que d'un fournisseur 32 bits.</span><span class="sxs-lookup"><span data-stu-id="2e96b-117">However, some data sources, such as Access or Excel, only have a 32-bit provider available.</span></span> <span data-ttu-id="2e96b-118">Pour utiliser ces sources de données, il peut s'avérer nécessaire d'installer et d'exécuter la version 32 bits de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="2e96b-118">To work with these data sources, you might have to install and run the 32-bit version of the wizard.</span></span> <span data-ttu-id="2e96b-119">Pour ce faire, sélectionnez Outils clients ou [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] lors de l'installation.</span><span class="sxs-lookup"><span data-stu-id="2e96b-119">To install the 32-bit version of the wizard, select either Client Tools or [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] during setup.</span></span>  
  
### <a name="to-import-or-export-data-by-using-the-sql-server-import-and-export-wizard"></a><span data-ttu-id="2e96b-120">Pour importer ou exporter des données à l'aide de l'Assistant Importation et Exportation SQL Server</span><span class="sxs-lookup"><span data-stu-id="2e96b-120">To import or export data by using the SQL Server Import and Export Wizard</span></span>  
  
1.  <span data-ttu-id="2e96b-121">Démarrez l'Assistant Importation et Exportation [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e96b-121">Start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard.</span></span>  
  
2.  <span data-ttu-id="2e96b-122">Sur les pages correspondantes de l'Assistant, sélectionnez une source de données et une destination de données.</span><span class="sxs-lookup"><span data-stu-id="2e96b-122">On the corresponding wizard pages, select a data source and a data destination.</span></span>  
  
     <span data-ttu-id="2e96b-123">Les sources de données disponibles comprennent des fournisseurs de données [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], des fournisseurs OLE DB, des fournisseurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, des fournisseurs [!INCLUDE[vstecado](../../includes/vstecado-md.md)], Microsoft Office Excel, Microsoft Office Access et la source du fichier plat.</span><span class="sxs-lookup"><span data-stu-id="2e96b-123">The available data sources include [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data providers, OLE DB providers, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client providers, [!INCLUDE[vstecado](../../includes/vstecado-md.md)] providers, Microsoft Office Excel, Microsoft Office Access, and the Flat File source.</span></span> <span data-ttu-id="2e96b-124">En fonction de la source, vous définissez des options telles que le mode d'authentification, le nom du serveur, le nom de la base de données et le format de fichier.</span><span class="sxs-lookup"><span data-stu-id="2e96b-124">Depending on the source, you set options such as the authentication mode, server name, database name, and file format.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2e96b-125">Le fournisseur de données [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider pour Oracle ne prend pas en charge les types de données Oracle BLOB, CLOB, NCLOB, BFILE et UROWID.</span><span class="sxs-lookup"><span data-stu-id="2e96b-125">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider for Oracle does not support the Oracle BLOB, CLOB, NCLOB, BFILE, and UROWID data types.</span></span> <span data-ttu-id="2e96b-126">Par conséquent, la source OLE DB ne peut pas extraire de données des tables qui contiennent des colonnes avec ces types de données.</span><span class="sxs-lookup"><span data-stu-id="2e96b-126">Therefore, the OLE DB source cannot extract data from tables that contain columns with these data types.</span></span>  
  
     <span data-ttu-id="2e96b-127">Les destinations de données disponibles incluent les fournisseurs de données [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], les fournisseurs OLE DB, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, Excel, Access et la destination de fichier plat.</span><span class="sxs-lookup"><span data-stu-id="2e96b-127">The available data destinations include [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data providers, OLE DB providers, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, Excel, Access, and the Flat File destination.</span></span>  
  
3.  <span data-ttu-id="2e96b-128">Définissez les options pour le type de destination sélectionné.</span><span class="sxs-lookup"><span data-stu-id="2e96b-128">Set the options for the type of destination that you selected.</span></span>  
  
     <span data-ttu-id="2e96b-129">Si la destination est une base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vous pouvez spécifier les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="2e96b-129">If the destination is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database you can specify the following:</span></span>  
  
    -   <span data-ttu-id="2e96b-130">Indiquez s'il faut créer une base de données et définir ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="2e96b-130">Indicate whether to create a new database and set the database properties.</span></span> <span data-ttu-id="2e96b-131">Les propriétés suivantes ne peuvent pas être configurées et l'Assistant utilise les valeurs par défaut spécifiées :</span><span class="sxs-lookup"><span data-stu-id="2e96b-131">The following properties cannot be configured and the wizard uses the specified default values:</span></span>  
  
        |<span data-ttu-id="2e96b-132">Propriété</span><span class="sxs-lookup"><span data-stu-id="2e96b-132">Property</span></span>|<span data-ttu-id="2e96b-133">Valeur</span><span class="sxs-lookup"><span data-stu-id="2e96b-133">Value</span></span>|  
        |--------------|-----------|  
        |<span data-ttu-id="2e96b-134">Classement</span><span class="sxs-lookup"><span data-stu-id="2e96b-134">Collation</span></span>|<span data-ttu-id="2e96b-135">Latin1_General_CS_AS_KS_WS</span><span class="sxs-lookup"><span data-stu-id="2e96b-135">Latin1_General_CS_AS_KS_WS</span></span>|  
        |<span data-ttu-id="2e96b-136">mode de récupération</span><span class="sxs-lookup"><span data-stu-id="2e96b-136">Recovery model</span></span>|<span data-ttu-id="2e96b-137">Complète</span><span class="sxs-lookup"><span data-stu-id="2e96b-137">Full</span></span>|  
        |<span data-ttu-id="2e96b-138">Utiliser l'indexation de texte intégral</span><span class="sxs-lookup"><span data-stu-id="2e96b-138">Use full-text indexing</span></span>|<span data-ttu-id="2e96b-139">True</span><span class="sxs-lookup"><span data-stu-id="2e96b-139">True</span></span>|  
  
    -   <span data-ttu-id="2e96b-140">Indiquez s'il faut copier des données à partir de tables ou de vues, ou copier des résultats de requête.</span><span class="sxs-lookup"><span data-stu-id="2e96b-140">Select whether to copy data from tables or views, or to copy query results.</span></span>  
  
         <span data-ttu-id="2e96b-141">Si vous souhaitez interroger la source de données et copier les résultats, vous pouvez construire une requête Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="2e96b-141">If you want to query the source data and copy the results, you can construct a Transact-SQL query.</span></span> <span data-ttu-id="2e96b-142">Vous pouvez entrer la requête Transact-SQL manuellement ou utiliser une requête enregistrée dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="2e96b-142">You can enter the Transact-SQL query manually or use a query saved to a file.</span></span> <span data-ttu-id="2e96b-143">L'Assistant propose une fonctionnalité d'exploration qui vous permet de rechercher le fichier, et il l'ouvre et colle automatiquement son contenu dans la page de l'Assistant lorsque vous sélectionnez le fichier.</span><span class="sxs-lookup"><span data-stu-id="2e96b-143">The wizard includes a browse feature for locating the file, and the wizard automatically opens the file and pastes its content into the wizard page when you select the file.</span></span>  
  
         <span data-ttu-id="2e96b-144">Si la source est un fournisseur [!INCLUDE[vstecado](../../includes/vstecado-md.md)], vous pouvez également utiliser l'option de copie des résultats de requête, en spécifiant la chaîne DBCommand en tant que requête.</span><span class="sxs-lookup"><span data-stu-id="2e96b-144">If the source is an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] provider you can also use the option to copy query results, providing the DBCommand string as the query.</span></span>  
  
         <span data-ttu-id="2e96b-145">Si la source de données est une vue, l'Assistant Importation et Exportation [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] convertit automatiquement la vue en table dans la destination.</span><span class="sxs-lookup"><span data-stu-id="2e96b-145">If the source data is a view, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard automatically converts the view to a table in the destination.</span></span>  
  
    -   <span data-ttu-id="2e96b-146">Indiquez si la table de destination est supprimée puis recréée, et si l'insertion d'identité doit être activée.</span><span class="sxs-lookup"><span data-stu-id="2e96b-146">Indicate whether the destination table is dropped and then re-created, and whether to enable identity inserts.</span></span>  
  
    -   <span data-ttu-id="2e96b-147">Indiquez s'il faut supprimer ou ajouter des lignes dans une table de destination existante.</span><span class="sxs-lookup"><span data-stu-id="2e96b-147">Indicate whether to delete rows or append rows in an existing destination table.</span></span> <span data-ttu-id="2e96b-148">Si la table n'existe pas, l'Assistant Importation et Exportation [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] la crée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="2e96b-148">If the table does not exist, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard automatically creates it.</span></span>  
  
     <span data-ttu-id="2e96b-149">Si la destination est un fichier plat, vous pouvez spécifier les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="2e96b-149">If the destination is a Flat File destination you can specify the following:</span></span>  
  
    -   <span data-ttu-id="2e96b-150">Spécifier le séparateur de lignes dans le fichier de destination.</span><span class="sxs-lookup"><span data-stu-id="2e96b-150">Specify the row delimiter in the destination file.</span></span>  
  
    -   <span data-ttu-id="2e96b-151">Spécifier le délimiteur de colonne dans le fichier de destination.</span><span class="sxs-lookup"><span data-stu-id="2e96b-151">Specify the column delimiter in the destination file.</span></span>  
  
4.  <span data-ttu-id="2e96b-152">(Facultatif) Sélectionnez une table et modifiez les mappages entre les colonnes sources et de destination, ou modifiez les métadonnées des colonnes de destination :</span><span class="sxs-lookup"><span data-stu-id="2e96b-152">(Optional) Select one table and change the mappings between source and destination columns, or change the metadata of destination columns:</span></span>  
  
    -   <span data-ttu-id="2e96b-153">Mappez les colonnes sources à des colonnes de destination différentes.</span><span class="sxs-lookup"><span data-stu-id="2e96b-153">Map source columns to different destination columns.</span></span>  
  
    -   <span data-ttu-id="2e96b-154">Modifiez le type de données dans la colonne de destination.</span><span class="sxs-lookup"><span data-stu-id="2e96b-154">Change the data type in the destination column.</span></span>  
  
    -   <span data-ttu-id="2e96b-155">Définissez la longueur des colonnes avec des types de données character.</span><span class="sxs-lookup"><span data-stu-id="2e96b-155">Set the length of columns with character data types.</span></span>  
  
    -   <span data-ttu-id="2e96b-156">Définissez la précision et l'échelle des colonnes avec des types de données numériques.</span><span class="sxs-lookup"><span data-stu-id="2e96b-156">Set the precision and scale of columns with numeric data types.</span></span>  
  
    -   <span data-ttu-id="2e96b-157">Indiquez si la colonne peut contenir des valeurs Null.</span><span class="sxs-lookup"><span data-stu-id="2e96b-157">Specify whether the column can contain null values.</span></span>  
  
5.  <span data-ttu-id="2e96b-158">(Facultatif) Sélectionnez plusieurs tables, et mettez à jour les métadonnées et options à appliquer à ces tables :</span><span class="sxs-lookup"><span data-stu-id="2e96b-158">(Optional) Select multiple tables, and update the metadata and options to apply to those tables:</span></span>  
  
    -   <span data-ttu-id="2e96b-159">Sélectionnez un schéma de destination existant ou fournissez un nouveau schéma auquel affecter les tables.</span><span class="sxs-lookup"><span data-stu-id="2e96b-159">Select an existing destination schema or provide a new schema to which to assign tables.</span></span>  
  
    -   <span data-ttu-id="2e96b-160">Indiquez si les insertions d'identité doivent être activées dans les tables de destination.</span><span class="sxs-lookup"><span data-stu-id="2e96b-160">Specify whether to enable identity inserts in destination tables.</span></span>  
  
    -   <span data-ttu-id="2e96b-161">Indiquez si les tables de destination doivent être supprimées et recréées.</span><span class="sxs-lookup"><span data-stu-id="2e96b-161">Specify whether to drop and re-create destination tables.</span></span>  
  
    -   <span data-ttu-id="2e96b-162">Indiquez si les tables de destination existantes doivent être tronquées.</span><span class="sxs-lookup"><span data-stu-id="2e96b-162">Specify whether to truncate existing destination tables.</span></span>  
  
6.  <span data-ttu-id="2e96b-163">Enregistrez et exécutez un package.</span><span class="sxs-lookup"><span data-stu-id="2e96b-163">Save and run a package.</span></span>  
  
     <span data-ttu-id="2e96b-164">Si l'Assistant est démarré à partir de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de l'invite de commandes, le package peut s'exécuter immédiatement.</span><span class="sxs-lookup"><span data-stu-id="2e96b-164">If the wizard is started from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or the command prompt, the package can run immediately.</span></span> <span data-ttu-id="2e96b-165">Vous pouvez éventuellement enregistrer le package dans la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] base de données **msdb** ou dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="2e96b-165">You can optionally save the package to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **msdb** database or to the file system.</span></span> <span data-ttu-id="2e96b-166">Pour plus d’informations sur la base de données **msdb** , consultez [Package Management &#40;service SSIS&#41;](../service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="2e96b-166">For more information about the **msdb** database, see [Package Management &#40;SSIS Service&#41;](../service/package-management-ssis-service.md).</span></span>  
  
     <span data-ttu-id="2e96b-167">Lorsque vous enregistrez le package, vous pouvez définir son niveau de protection et, si ce niveau utilise un mot de passe, fournir celui-ci.</span><span class="sxs-lookup"><span data-stu-id="2e96b-167">When you save the package you can set the package protection level, and if the protection level uses a password, provide the password.</span></span> <span data-ttu-id="2e96b-168">Pour plus d’informations sur les niveaux de protection des packages, consultez [Access Control pour obtenir des données sensibles dans des packages](../security/access-control-for-sensitive-data-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="2e96b-168">For more information about package protection levels, see [Access Control for Sensitive Data in Packages](../security/access-control-for-sensitive-data-in-packages.md).</span></span>  
  
     <span data-ttu-id="2e96b-169">Si l'Assistant est démarré à partir d'un projet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], vous ne pouvez pas exécuter le package à partir de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="2e96b-169">If the wizard is started from an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you cannot run the package from the wizard.</span></span> <span data-ttu-id="2e96b-170">Au lieu de cela, le package est ajouté au projet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] à partir duquel vous avez démarré l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="2e96b-170">Instead, the package is added to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project from which you started the wizard.</span></span> <span data-ttu-id="2e96b-171">Vous pouvez ensuite exécuter le package dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e96b-171">You can then run the package in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2e96b-172">Dans [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], l'option permettant d'enregistrer le package créé par l'Assistant n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="2e96b-172">In [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], the option to save the package created by the wizard is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e96b-173">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2e96b-173">See Also</span></span>  
 <span data-ttu-id="2e96b-174">[Assistant importation et exportation SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="2e96b-174">[SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md) </span></span>  
 [<span data-ttu-id="2e96b-175">Créer des packages dans les outils de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="2e96b-175">Create Packages in SQL Server Data Tools</span></span>](../create-packages-in-sql-server-data-tools.md)  
  
  
