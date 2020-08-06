---
title: Basculer une base de données Analysis Services entre les modes ReadOnly et ReadWrite | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- ReadOnly property
- ReadWriteMode command
- operations [Analysis Services - multidimensional data]
ms.assetid: 4eff8181-08dd-4fad-b091-d400fc21a020
author: minewiskan
ms.author: owend
ms.openlocfilehash: 757aedd985d969f932deacf5599716078021a1af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694751"
---
# <a name="switch-an-analysis-services-database-between-readonly-and-readwrite-modes"></a><span data-ttu-id="76824-102">Basculer une base de données Analysis Services entre les modes ReadOnly et ReadWrite</span><span class="sxs-lookup"><span data-stu-id="76824-102">Switch an Analysis Services database between ReadOnly and ReadWrite modes</span></span>
  <span data-ttu-id="76824-103">Il existe souvent des situations où un administrateur de base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] souhaite modifier le mode lecture/écriture d'une base de données tabulaire ou multidimensionnelle.</span><span class="sxs-lookup"><span data-stu-id="76824-103">There are often situations when a [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database administrator (dba) wants to change the read/write mode of a tabular or multidimensional database.</span></span> <span data-ttu-id="76824-104">Ces situations sont souvent justifiées par des exigences opérationnelles, telles que le partage de la base de données au sein d'un pool de serveurs [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] pour un plus grand confort de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="76824-104">These situations are often driven by business needs, such as sharing the database among a pool of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] servers for a better user experience.</span></span>  
  
 <span data-ttu-id="76824-105">Vous pouvez basculer d'un mode de base de données à un autre de différentes façons.</span><span class="sxs-lookup"><span data-stu-id="76824-105">A database mode can be switched in many ways.</span></span> <span data-ttu-id="76824-106">Ce document explique les scénarios courants suivants :</span><span class="sxs-lookup"><span data-stu-id="76824-106">This document explains the following common scenarios:</span></span>  
  
-   <span data-ttu-id="76824-107">Par interaction à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76824-107">Interactively using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]</span></span>  
  
-   <span data-ttu-id="76824-108">Par programmation à l'aide d'AMO</span><span class="sxs-lookup"><span data-stu-id="76824-108">Programmatically using AMO</span></span>  
  
-   <span data-ttu-id="76824-109">Par script à l'aide de XMLA</span><span class="sxs-lookup"><span data-stu-id="76824-109">By script using XMLA</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="76824-110">Procédures</span><span class="sxs-lookup"><span data-stu-id="76824-110">Procedures</span></span>  
  
#### <a name="to-switch-the-readwrite-mode-of-a-database-interactively-using-management-studio"></a><span data-ttu-id="76824-111">Pour basculer interactivement le mode lecture/écriture d'une base de données à l'aide de Management Studio</span><span class="sxs-lookup"><span data-stu-id="76824-111">To switch the read/write mode of a database interactively using Management Studio</span></span>  
  
1.  <span data-ttu-id="76824-112">Localisez la base de données à basculer dans le volet gauche ou droit de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76824-112">Locate the database to be switched in the left or right pane of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
2.  <span data-ttu-id="76824-113">Cliquez avec le bouton droit sur la base de données et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="76824-113">Right-click the database and select **Properties**.</span></span> <span data-ttu-id="76824-114">Recherchez le dossier de base de données et notez l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="76824-114">Find the database folder and note the location.</span></span> <span data-ttu-id="76824-115">Un emplacement de stockage de base de données vide indique que le dossier de base de données se trouve dans le dossier de données de serveur.</span><span class="sxs-lookup"><span data-stu-id="76824-115">An empty database storage location indicates that the database folder is located in the server data folder.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="76824-116">Dès que la base de données est détachée, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] ne peut plus vous aider à obtenir l'emplacement de base de données.</span><span class="sxs-lookup"><span data-stu-id="76824-116">As soon as the database is detached, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] can no longer help you obtain the database location.</span></span>  
  
3.  <span data-ttu-id="76824-117">Cliquez avec le bouton droit sur la base de données et sélectionnez **détacher...**</span><span class="sxs-lookup"><span data-stu-id="76824-117">Right-click the database and select **Detach...**</span></span>  
  
4.  <span data-ttu-id="76824-118">Assignez un mot de passe à la base de données à détacher, puis cliquez sur **OK** pour exécuter la commande de détachement.</span><span class="sxs-lookup"><span data-stu-id="76824-118">Assign a password to the database to be detached, and then click **OK** to execute the detach command.</span></span>  
  
5.  <span data-ttu-id="76824-119">Localisez le dossier **bases de données** dans le volet gauche ou droit de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76824-119">Locate the **Databases** folder in the left or right pane of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
6.  <span data-ttu-id="76824-120">Cliquez avec le bouton droit sur le dossier **bases de données** , puis sélectionnez **attacher...**</span><span class="sxs-lookup"><span data-stu-id="76824-120">Right-click the **Databases** folder and select **Attach...**</span></span>  
  
7.  <span data-ttu-id="76824-121">Dans la zone de texte **dossier** , tapez l'emplacement d'origine du dossier de base de données.</span><span class="sxs-lookup"><span data-stu-id="76824-121">In the **folder** text box, type the original location of the database folder.</span></span> <span data-ttu-id="76824-122">Vous pouvez également utiliser le bouton Parcourir (**...**) pour rechercher le dossier de base de données.</span><span class="sxs-lookup"><span data-stu-id="76824-122">Alternatively, you can use the browse button (**...**) to locate the database folder.</span></span>  
  
8.  <span data-ttu-id="76824-123">Sélectionnez le mode lecture/écriture pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="76824-123">Select the read/write mode for the database.</span></span>  
  
9. <span data-ttu-id="76824-124">Tapez le mot de passe utilisé à l’étape 3, puis cliquez sur **OK** pour exécuter la commande d’attachement.</span><span class="sxs-lookup"><span data-stu-id="76824-124">Type the password that was used in step 3 and click **OK** to execute the attach command.</span></span>  
  
#### <a name="to-switch-the-readwrite-mode-to-a-database-programmatically-using-amo"></a><span data-ttu-id="76824-125">Pour basculer par programmation le mode lecture/écriture sur une base de données à l'aide d'AMO</span><span class="sxs-lookup"><span data-stu-id="76824-125">To switch the read/write mode to a database programmatically using AMO</span></span>  
  
1.  <span data-ttu-id="76824-126">Dans votre application C#, adaptez l'exemple de code suivant et complétez les tâches indiquées.</span><span class="sxs-lookup"><span data-stu-id="76824-126">In your C# application, adapt the following sample code and complete the indicated tasks.</span></span>  
  
 `private void SwitchReadWrite(Server server, string dbName,`  
  
 `ReadWriteMode dbReadWriteMode)`  
  
 `{`  
  
 `if (server.Databases.ContainsName(dbName))`  
  
 `{`  
  
 `Database db;`  
  
 `string databaseLocation;`  
  
 `db = server.Databases[dbName];`  
  
 `databaseLocation = db.DbStorageLocation;`  
  
 `if (databaseLocation == null)`  
  
 `{`  
  
 `string dataDir = server.ServerProperties["DataDir"].Value;`  
  
 `String[] possibleFolders = Directory.GetDirectories(dataDir, string.Concat(dbName,"*"), SearchOption.TopDirectoryOnly);`  
  
 `if (possibleFolders.Length > 1)`  
  
 `{`  
  
 `List<String> sortedFolders = new List<string>(possibleFolders.Length);`  
  
 `sortedFolders.AddRange(possibleFolders);`  
  
 `sortedFolders.Sort();`  
  
 `databaseLocation = sortedFolders[sortedFolders.Count - 1];`  
  
 `}`  
  
 `else`  
  
 `{`  
  
 `databaseLocation = possibleFolders[0];`  
  
 `}`  
  
 `}`  
  
 `db.Detach();`  
  
 `server.Attach(databaseLocation, dbReadWriteMode);`  
  
 `}`  
  
 `}`  
  
1.  <span data-ttu-id="76824-127">Dans votre application C#, appelez `SwitchReadWrite()` avec les paramètres nécessaires.</span><span class="sxs-lookup"><span data-stu-id="76824-127">In your C# application, invoke `SwitchReadWrite()` with the necessary parameters.</span></span>  
  
2.  <span data-ttu-id="76824-128">Compilez et exécutez le code pour déplacer la base de données.</span><span class="sxs-lookup"><span data-stu-id="76824-128">Compile and execute your code to move the database.</span></span>  
  
#### <a name="to-switch-the-readwrite-mode-to-a-database-by-script-using-xmla"></a><span data-ttu-id="76824-129">Pour basculer le mode lecture/écriture sur une base de données par script à l'aide de XMLA</span><span class="sxs-lookup"><span data-stu-id="76824-129">To switch the read/write mode to a database by script using XMLA</span></span>  
  
1.  <span data-ttu-id="76824-130">Localisez la base de données à basculer dans le volet gauche ou droit de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76824-130">Locate the database to be switched in the left or right pane of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
2.  <span data-ttu-id="76824-131">Cliquez avec le bouton droit sur la base de données et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="76824-131">Right-click the database and select **Properties**.</span></span> <span data-ttu-id="76824-132">Recherchez le dossier de base de données et notez l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="76824-132">Find the database folder and note the location.</span></span> <span data-ttu-id="76824-133">Un emplacement de stockage de base de données vide indique que le dossier de base de données se trouve dans le dossier de données de serveur.</span><span class="sxs-lookup"><span data-stu-id="76824-133">An empty database storage location indicates that the database folder is located in the server data folder.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="76824-134">Dès que la base de données est détachée, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] ne peut plus vous aider à obtenir l'emplacement de base de données.</span><span class="sxs-lookup"><span data-stu-id="76824-134">As soon as the database is detached, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] can no longer help you obtain the database location.</span></span>  
  
3.  <span data-ttu-id="76824-135">Ouvrez un nouvel onglet XMLA dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76824-135">Open a new XMLA tab in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
4.  <span data-ttu-id="76824-136">Copiez le modèle de script suivant pour XMLA :</span><span class="sxs-lookup"><span data-stu-id="76824-136">Copy the following script template for XMLA:</span></span>  
  
 `<Detach xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">`  
  
 `<Object>`  
  
 `<DatabaseID>%dbName%</DatabaseID>`  
  
 `<Password>%password%</Password>`  
  
 `</Object>`  
  
 `</Detach>`  
  
1.  <span data-ttu-id="76824-137">Remplacez `%dbName%` par le nom de la base de données et `%password%` par le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="76824-137">Replace `%dbName%` with the name of the database and `%password%` with the password.</span></span> <span data-ttu-id="76824-138">Les caractères % font partie du modèle et doivent être supprimés.</span><span class="sxs-lookup"><span data-stu-id="76824-138">The % characters are part of the template and must be removed.</span></span>  
  
2.  <span data-ttu-id="76824-139">Exécutez la commande XMLA.</span><span class="sxs-lookup"><span data-stu-id="76824-139">Execute the XMLA command.</span></span>  
  
3.  <span data-ttu-id="76824-140">Copiez le modèle de script suivant pour XMLA dans un nouvel onglet XMLA.</span><span class="sxs-lookup"><span data-stu-id="76824-140">Copy the following script template for XMLA in a new XMLA tab</span></span>  
  
 <span data-ttu-id="76824-141">`<Attach xmlns="https://schemas.microsoft.com/analysisservices/2003` `/engine` `">`</span><span class="sxs-lookup"><span data-stu-id="76824-141">`<Attach xmlns="https://schemas.microsoft.com/analysisservices/2003` `/engine` `">`</span></span>  
  
 `<Folder>%dbFolder%</Folder>`  
  
 `<ReadWriteMode xmlns="https://schemas.microsoft.com/analysisservices/2008/engine/100">%ReadOnlyMode%</ReadWriteMode>`  
  
 `</Attach>`  
  
1.  <span data-ttu-id="76824-142">Remplacez `%dbFolder%` par le chemin UNC complet du dossier de base de données, `%ReadOnlyMode%` par la valeur `ReadOnly` correspondante ou `ReadWrite`, et `%password%` par le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="76824-142">Replace `%dbFolder%` with the complete UNC path of the database folder, `%ReadOnlyMode%` with the corresponding value `ReadOnly` or `ReadWrite`, and `%password%` with the password.</span></span> <span data-ttu-id="76824-143">Les caractères % font partie du modèle et doivent être supprimés.</span><span class="sxs-lookup"><span data-stu-id="76824-143">The % characters are part of the template and must be removed.</span></span>  
  
2.  <span data-ttu-id="76824-144">Exécutez la commande XMLA.</span><span class="sxs-lookup"><span data-stu-id="76824-144">Execute the XMLA command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76824-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="76824-145">See Also</span></span>  
 <xref:Microsoft.AnalysisServices.Server.Attach%2A>   
 <span data-ttu-id="76824-146">[Microsoft. AnalysisServices. Database. Detach \*](/dotnet/api/microsoft.analysisservices.core.database.detach) </span><span class="sxs-lookup"><span data-stu-id="76824-146">[Microsoft.AnalysisServices.Database.Detach\*](/dotnet/api/microsoft.analysisservices.core.database.detach) </span></span>  
 <span data-ttu-id="76824-147">[Attacher et détacher des bases de données Analysis Services](attach-and-detach-analysis-services-databases.md) </span><span class="sxs-lookup"><span data-stu-id="76824-147">[Attach and Detach Analysis Services Databases](attach-and-detach-analysis-services-databases.md) </span></span>  
 <span data-ttu-id="76824-148">[Emplacement de stockage de base de données](database-storage-location.md) </span><span class="sxs-lookup"><span data-stu-id="76824-148">[Database Storage Location](database-storage-location.md) </span></span>  
 <span data-ttu-id="76824-149">[ReadWriteModes de base de données](database-readwritemodes.md) </span><span class="sxs-lookup"><span data-stu-id="76824-149">[Database ReadWriteModes](database-readwritemodes.md) </span></span>  
 <span data-ttu-id="76824-150">[Élément Attach](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/attach-element) </span><span class="sxs-lookup"><span data-stu-id="76824-150">[Attach Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/attach-element) </span></span>  
 <span data-ttu-id="76824-151">[Détacher l’élément](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/detach-element) </span><span class="sxs-lookup"><span data-stu-id="76824-151">[Detach Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/detach-element) </span></span>  
 <span data-ttu-id="76824-152">[Élément ReadWriteMode](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/readwritemode-element) </span><span class="sxs-lookup"><span data-stu-id="76824-152">[ReadWriteMode Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/readwritemode-element) </span></span>  
 [<span data-ttu-id="76824-153">DbStorageLocation, élément</span><span class="sxs-lookup"><span data-stu-id="76824-153">DbStorageLocation Element</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/dbstoragelocation-element)  
  
  
