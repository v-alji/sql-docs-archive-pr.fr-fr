---
title: Déplacer une base de données Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- moving databases [Anlysis Services]
- moving databases
- operations [Analysis Services - multidimensional data]
ms.assetid: fa644e5d-e276-445e-98d9-673afcfb83fe
author: minewiskan
ms.author: owend
ms.openlocfilehash: bd9b099ad6765d9caccb9b0af6622eb4aa77d38c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707943"
---
# <a name="move-an-analysis-services-database"></a><span data-ttu-id="89c1a-102">Déplacer une base de données Analysis Services</span><span class="sxs-lookup"><span data-stu-id="89c1a-102">Move an Analysis Services Database</span></span>
  <span data-ttu-id="89c1a-103">Il existe souvent des situations où un administrateur de base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] souhaite déplacer une base de données de modèle multidimensionnel ou tabulaire à un emplacement différent.</span><span class="sxs-lookup"><span data-stu-id="89c1a-103">There are often situations when an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database administrator (dba) wants to move a multidimensional or tabular model database to a different location.</span></span> <span data-ttu-id="89c1a-104">Ces cas sont souvent motivés par des impératifs d’exploitation, tels que le déplacement de la base de données vers un autre disque afin d’obtenir de meilleures performances, le gain de place afin de permettre la croissance de la base de données, ou la mise à niveau d'un produit.</span><span class="sxs-lookup"><span data-stu-id="89c1a-104">These situations are often driven by business needs, such as moving the database to a different disk for better performance, gaining room for database growth, or to upgrade a product.</span></span>  
  
 <span data-ttu-id="89c1a-105">Une base de données peut être déplacée de différentes façons.</span><span class="sxs-lookup"><span data-stu-id="89c1a-105">A database can be moved in many ways.</span></span> <span data-ttu-id="89c1a-106">Ce document explique les scénarios courants suivants :</span><span class="sxs-lookup"><span data-stu-id="89c1a-106">This document explains the following common scenarios:</span></span>  
  
-   <span data-ttu-id="89c1a-107">Par interaction à l'aide de SSMS</span><span class="sxs-lookup"><span data-stu-id="89c1a-107">Interactively using SSMS</span></span>  
  
-   <span data-ttu-id="89c1a-108">Par programmation à l'aide d'AMO</span><span class="sxs-lookup"><span data-stu-id="89c1a-108">Programmatically using AMO</span></span>  
  
-   <span data-ttu-id="89c1a-109">Par script à l'aide de XMLA</span><span class="sxs-lookup"><span data-stu-id="89c1a-109">By script using XMLA</span></span>  
  
 <span data-ttu-id="89c1a-110">Tous les scénarios requièrent que l'utilisateur accède au dossier de base de données et utilise une méthode pour déplacer les fichiers vers la destination finale souhaitée.</span><span class="sxs-lookup"><span data-stu-id="89c1a-110">All scenarios require the user to access the database folder and to use a method for moving the files to the desired final destination.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89c1a-111">Détacher une base de données sans lui assigner un mot de passe laisse la base de données dans un état non protégé.</span><span class="sxs-lookup"><span data-stu-id="89c1a-111">Detaching a database without assigning a password to it leaves the database in an unsecured state.</span></span> <span data-ttu-id="89c1a-112">Nous recommandons d'assigner un mot de passe à la base de données pour protéger les informations confidentielles.</span><span class="sxs-lookup"><span data-stu-id="89c1a-112">We recommend assigning a password to the database to protect confidential information.</span></span> <span data-ttu-id="89c1a-113">De même, la sécurité d'accès correspondante doit s'appliquer au dossier de base de données, aux sous-dossiers et aux fichiers pour empêcher leur accès non autorisé.</span><span class="sxs-lookup"><span data-stu-id="89c1a-113">Also, the corresponding access security should be applied to the database folder, sub-folders, and files to prevent unauthorized access to them.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="89c1a-114">Procédures</span><span class="sxs-lookup"><span data-stu-id="89c1a-114">Procedures</span></span>  
  
#### <a name="moving-a-database-interactively-using-ssms"></a><span data-ttu-id="89c1a-115">Déplacement interactif d'une base de données à l'aide de SSMS</span><span class="sxs-lookup"><span data-stu-id="89c1a-115">Moving a database interactively using SSMS</span></span>  
  
1.  <span data-ttu-id="89c1a-116">Localisez la base de données à déplacer dans le volet gauche ou droit de SSMS.</span><span class="sxs-lookup"><span data-stu-id="89c1a-116">Locate the database to be moved in the left or right pane of SSMS.</span></span>  
  
2.  <span data-ttu-id="89c1a-117">Cliquez avec le bouton droit sur la base de données et sélectionnez **détacher...**</span><span class="sxs-lookup"><span data-stu-id="89c1a-117">Right-click on the database and select **Detach...**</span></span>  
  
3.  <span data-ttu-id="89c1a-118">Attribuez un mot de passe à la base de données à détacher, puis cliquez sur **OK** pour exécuter la commande de détachement.</span><span class="sxs-lookup"><span data-stu-id="89c1a-118">Assign a password to the database to be detached, then click **OK** to execute the detach command.</span></span>  
  
4.  <span data-ttu-id="89c1a-119">Utilisez tout mécanisme du système d'exploitation ou votre méthode standard de déplacement des fichiers pour déplacer le dossier de base de données vers le nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="89c1a-119">Use any operating system mechanism or your standard method for moving files to move the database folder to the new location.</span></span>  
  
5.  <span data-ttu-id="89c1a-120">Recherchez le dossier **Bases de données** dans le volet gauche ou droit de SSMS.</span><span class="sxs-lookup"><span data-stu-id="89c1a-120">Locate the **Databases** folder in the left or right pane of SSMS.</span></span>  
  
6.  <span data-ttu-id="89c1a-121">Cliquez avec le bouton droit sur le dossier **bases de données** , puis sélectionnez **attacher...**</span><span class="sxs-lookup"><span data-stu-id="89c1a-121">Right-click on the **Databases** folder and select **Attach...**</span></span>  
  
7.  <span data-ttu-id="89c1a-122">Dans la zone de texte **dossier** , tapez le nouvel emplacement du dossier de base de données.</span><span class="sxs-lookup"><span data-stu-id="89c1a-122">In the **folder** text box, type the new location of the database folder.</span></span> <span data-ttu-id="89c1a-123">Vous pouvez également utiliser le bouton Parcourir (**...**) pour rechercher le dossier de base de données.</span><span class="sxs-lookup"><span data-stu-id="89c1a-123">Alternatively, you can use the browse button (**...**) to locate the database folder.</span></span>  
  
8.  <span data-ttu-id="89c1a-124">Sélectionnez le `ReadWrite` mode de la base de données.</span><span class="sxs-lookup"><span data-stu-id="89c1a-124">Select the `ReadWrite` mode for the database.</span></span>  
  
9. <span data-ttu-id="89c1a-125">Entrez le mot de passe utilisé dans l'étape 3 et cliquez sur **OK** pour exécuter la commande d'attachement.</span><span class="sxs-lookup"><span data-stu-id="89c1a-125">Type the password used in step 3 and click **OK** to execute the attach command.</span></span>  
  
#### <a name="moving-a-database-programmatically-using-amo"></a><span data-ttu-id="89c1a-126">Déplacement par programmation d'une base de données à l'aide d'AMO</span><span class="sxs-lookup"><span data-stu-id="89c1a-126">Moving a database programmatically using AMO</span></span>  
  
1.  <span data-ttu-id="89c1a-127">Dans votre application C#, adaptez l'exemple de code suivant et complétez les tâches indiquées.</span><span class="sxs-lookup"><span data-stu-id="89c1a-127">In your C# application, adapt the following sample code and complete the indicated tasks.</span></span>  
  
 `private void MoveDb(Server server, string dbName,`  
  
 `string dbInitialLocation, string dbFinalLocation,`  
  
 `string dbPassword, ReadWriteMode dbReadWriteMode)`  
  
 `{`  
  
 `//Verify dbInitialLocation exists before continuing`  
  
 `if (server.Databases.ContainsName(dbName))`  
  
 `{`  
  
 `Database db;`  
  
 `//Save current cursor and change cursor to Cursors.WaitCursor`  
  
 `db = server.Databases[dbName];`  
  
 `db.Detach(dbPassword);`  
  
 `//Add your own code to copy the database files to the destination where you intend to attach the database`  
  
 `//Verify dbFinalLocation exists before continuing`  
  
 `server.Attach(dbFinalLocation, dbReadWriteMode, dbPassword);`  
  
 `//Restore cursor to its original`  
  
 `}`  
  
 `}`  
  
1.  <span data-ttu-id="89c1a-128">Dans votre application C#, appelez `MoveDb()` avec les paramètres nécessaires.</span><span class="sxs-lookup"><span data-stu-id="89c1a-128">In your C# application, invoke `MoveDb()` with the necessary parameters.</span></span>  
  
2.  <span data-ttu-id="89c1a-129">Compilez et exécutez le code pour déplacer la base de données.</span><span class="sxs-lookup"><span data-stu-id="89c1a-129">Compile and execute your code to move the database.</span></span>  
  
#### <a name="moving-a-database-by-script-using-xmla"></a><span data-ttu-id="89c1a-130">Déplacement d'une base de données par script à l'aide de XMLA</span><span class="sxs-lookup"><span data-stu-id="89c1a-130">Moving a database by script using XMLA</span></span>  
  
1.  <span data-ttu-id="89c1a-131">Ouvrez un nouvel onglet XMLA dans SSMS.</span><span class="sxs-lookup"><span data-stu-id="89c1a-131">Open a new XMLA tab in SSMS.</span></span>  
  
2.  <span data-ttu-id="89c1a-132">Copiez le modèle de script suivant pour XMLA :</span><span class="sxs-lookup"><span data-stu-id="89c1a-132">Copy the following script template for XMLA</span></span>  
  
 `<Detach xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">`  
  
 `<Object>`  
  
 `<DatabaseID>%dbName%</DatabaseID>`  
  
 `<Password>%password%</Password>`  
  
 `</Object>`  
  
 `</Detach>`  
  
1.  <span data-ttu-id="89c1a-133">Remplacez `%dbName%` par le nom de la base de données et `%password%` par le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="89c1a-133">Replace `%dbName%` with the name of the database and `%password%` with the password.</span></span> <span data-ttu-id="89c1a-134">Les caractères % font partie du modèle et doivent être supprimés.</span><span class="sxs-lookup"><span data-stu-id="89c1a-134">The % characters are part of the template and must be removed.</span></span>  
  
2.  <span data-ttu-id="89c1a-135">Exécutez la commande XMLA.</span><span class="sxs-lookup"><span data-stu-id="89c1a-135">Execute the XMLA command.</span></span>  
  
3.  <span data-ttu-id="89c1a-136">Utilisez tout mécanisme du système d'exploitation ou votre méthode standard de déplacement des fichiers pour déplacer le dossier de base de données vers le nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="89c1a-136">Use any operating system mechanism or your standard method for moving files to move the database folder to the new location.</span></span>  
  
4.  <span data-ttu-id="89c1a-137">Copiez le modèle de script suivant pour XMLA dans un nouvel onglet XMLA.</span><span class="sxs-lookup"><span data-stu-id="89c1a-137">Copy the following script template for XMLA in a new XMLA tab</span></span>  
  
 `<Attach xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">`  
  
 `<Folder>%dbFolder%</Folder>`  
  
 `<ReadWriteMode xmlns="https://schemas.microsoft.com/analysisservices/2008/engine/100">%ReadOnlyMode%</ReadWriteMode>`  
  
 `</Attach>`  
  
1.  <span data-ttu-id="89c1a-138">Remplacez `%dbFolder%` par le chemin UNC complet du dossier de base de données, `%ReadOnlyMode%` par la valeur `ReadOnly` correspondante ou `ReadWrite`, et `%password%` par le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="89c1a-138">Replace `%dbFolder%` with the complete UNC path of the database folder, `%ReadOnlyMode%` with the corresponding value `ReadOnly` or `ReadWrite`, and `%password%` with the password.</span></span> <span data-ttu-id="89c1a-139">Les caractères % font partie du modèle et doivent être supprimés.</span><span class="sxs-lookup"><span data-stu-id="89c1a-139">The % characters are part of the template and must be removed.</span></span>  
  
2.  <span data-ttu-id="89c1a-140">Exécutez la commande XMLA.</span><span class="sxs-lookup"><span data-stu-id="89c1a-140">Execute the XMLA command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89c1a-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="89c1a-141">See Also</span></span>  
 <xref:Microsoft.AnalysisServices.Server.Attach%2A>   
 <span data-ttu-id="89c1a-142">[Microsoft. AnalysisServices. Database. Detach \*](/dotnet/api/microsoft.analysisservices.core.database.detach) </span><span class="sxs-lookup"><span data-stu-id="89c1a-142">[Microsoft.AnalysisServices.Database.Detach\*](/dotnet/api/microsoft.analysisservices.core.database.detach) </span></span>  
 <span data-ttu-id="89c1a-143">[Attacher et détacher des bases de données Analysis Services](attach-and-detach-analysis-services-databases.md) </span><span class="sxs-lookup"><span data-stu-id="89c1a-143">[Attach and Detach Analysis Services Databases](attach-and-detach-analysis-services-databases.md) </span></span>  
 <span data-ttu-id="89c1a-144">[Emplacement de stockage de base de données](database-storage-location.md) </span><span class="sxs-lookup"><span data-stu-id="89c1a-144">[Database Storage Location](database-storage-location.md) </span></span>  
 <span data-ttu-id="89c1a-145">[ReadWriteModes de base de données](database-readwritemodes.md) </span><span class="sxs-lookup"><span data-stu-id="89c1a-145">[Database ReadWriteModes](database-readwritemodes.md) </span></span>  
 <span data-ttu-id="89c1a-146">[Élément Attach](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/attach-element) </span><span class="sxs-lookup"><span data-stu-id="89c1a-146">[Attach Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/attach-element) </span></span>  
 <span data-ttu-id="89c1a-147">[Détacher l’élément](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/detach-element) </span><span class="sxs-lookup"><span data-stu-id="89c1a-147">[Detach Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/detach-element) </span></span>  
 <span data-ttu-id="89c1a-148">[Élément ReadWriteMode](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/readwritemode-element) </span><span class="sxs-lookup"><span data-stu-id="89c1a-148">[ReadWriteMode Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/readwritemode-element) </span></span>  
 [<span data-ttu-id="89c1a-149">DbStorageLocation, élément</span><span class="sxs-lookup"><span data-stu-id="89c1a-149">DbStorageLocation Element</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/dbstoragelocation-element)  
  
  
