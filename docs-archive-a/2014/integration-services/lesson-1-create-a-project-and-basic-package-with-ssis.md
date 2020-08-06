---
title: 'Leçon 1 : création du package de base et du projet | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 84d0b877-603f-4f8e-bb6b-671558ade5c2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1a9ddc36ef242cc4e4b146e90dfa9de470e68d83
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605571"
---
# <a name="lesson-1-creating-the-project-and-basic-package"></a><span data-ttu-id="d68f6-102">Leçon 1 : Création du package de base et du package du projet</span><span class="sxs-lookup"><span data-stu-id="d68f6-102">Lesson 1: Creating the Project and Basic Package</span></span>
  <span data-ttu-id="d68f6-103">Au cours de cette leçon, vous allez créer un package ETL simple qui extrait des données d'une seule source de fichier plat, transforme ces données en utilisant deux composants de transformation de recherche et les écrit dans la table de faits **FactCurrency** de la base de données **AdventureWorksDW2012**.</span><span class="sxs-lookup"><span data-stu-id="d68f6-103">In this lesson, you will create a simple ETL package that extracts data from a single flat file source, transforms the data using two lookup transformation components, and writes that data to the **FactCurrency** fact table in **AdventureWorksDW2012**.</span></span> <span data-ttu-id="d68f6-104">Dans le cadre de cette leçon, vous allez apprendre à créer de nouveaux packages, ajouter et configurer des sources de données et des destinations et enfin, à utiliser le nouveau flux de contrôle et les composants de flux de données.</span><span class="sxs-lookup"><span data-stu-id="d68f6-104">As part of this lesson, you will learn how to create new packages, add and configure data source and destination connections, and work with new control flow and data flow components.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d68f6-105">Pour suivre ce didacticiel, vous devez disposer de l'exemple de base de données **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="d68f6-105">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="d68f6-106">Pour plus d’informations sur l’installation et le déploiement de **AdventureWorksDW2012**, consultez [Microsoft SQL Server des exemples de produits : Reporting Services](https://archive.codeplex.com/?p=msftrsprodsamples).</span><span class="sxs-lookup"><span data-stu-id="d68f6-106">For more information on installing and deploying **AdventureWorksDW2012**, see [Microsoft SQL Server Product Samples: Reporting Services](https://archive.codeplex.com/?p=msftrsprodsamples).</span></span>  
  
## <a name="understanding-the-package-requirements"></a><span data-ttu-id="d68f6-107">Connaissances préalables à la création d'un package</span><span class="sxs-lookup"><span data-stu-id="d68f6-107">Understanding the Package Requirements</span></span>  
 <span data-ttu-id="d68f6-108">Ce didacticiel nécessite Microsoft SQL Server Data Tools.</span><span class="sxs-lookup"><span data-stu-id="d68f6-108">This tutorial requires Microsoft SQL Server Data Tools.</span></span>  
  
 <span data-ttu-id="d68f6-109">Pour plus d’informations sur l’installation de SQL Server Data Tools, consultez [Télécharger SSDT (SQL Server Data Tools)](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt?view=sql-server-2017).</span><span class="sxs-lookup"><span data-stu-id="d68f6-109">For more information on installing the SQL Server Data Tools see [SQL Server Data Tools Download](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt?view=sql-server-2017).</span></span>  
  
 <span data-ttu-id="d68f6-110">Avant de créer un package, vous devez maîtriser les connaissances relatives au formatage utilisé pour les données sources et la destination.</span><span class="sxs-lookup"><span data-stu-id="d68f6-110">Before creating a package, you need a good understanding of the formatting used in both the source data and the destination.</span></span> <span data-ttu-id="d68f6-111">Une fois ces connaissances maîtrisées, vous êtes prêt à définir les transformations nécessaires pour mapper les données source avec les données de destination.</span><span class="sxs-lookup"><span data-stu-id="d68f6-111">Once you understand both of these data formats, you will be ready to define the transformations necessary to map the source data to the destination.</span></span>  
  
### <a name="looking-at-the-source"></a><span data-ttu-id="d68f6-112">Étude de la source</span><span class="sxs-lookup"><span data-stu-id="d68f6-112">Looking at the Source</span></span>  
 <span data-ttu-id="d68f6-113">Dans le cadre de ce didacticiel, les données sources sont représentées par un ensemble de données monétaires d'historique contenu dans le fichier plat SampleCurrencyData.txt.</span><span class="sxs-lookup"><span data-stu-id="d68f6-113">For this tutorial, the source data is a set of historical currency data contained in the flat file, SampleCurrencyData.txt.</span></span> <span data-ttu-id="d68f6-114">Les données sources contiennent les quatre colonnes suivantes : le taux moyen de la devise, une clé de devise, une clé de date et le taux de clôture.</span><span class="sxs-lookup"><span data-stu-id="d68f6-114">The source data has the following four columns: the average rate of the currency, a currency key, a date key, and the end-of-day rate.</span></span>  
  
 <span data-ttu-id="d68f6-115">Voici un exemple des données sources contenues dans le fichier SampleCurrencyData.txt :</span><span class="sxs-lookup"><span data-stu-id="d68f6-115">Here is an example of the source data contained in the SampleCurrencyData.txt file:</span></span>  
  
 `1.00070049USD9/3/05 0:001.001201442`  
  
 `1.00020004USD9/4/05 0:001`  
  
 `1.00020004USD9/5/05 0:001.001201442`  
  
 `1.00020004USD9/6/05 0:001`  
  
 `1.00020004USD9/7/05 0:001.00070049`  
  
 `1.00070049USD9/8/05 0:000.99980004`  
  
 `1.00070049USD9/9/05 0:001.001502253`  
  
 `1.00070049USD9/10/05 0:000.99990001`  
  
 `1.00020004USD9/11/05 0:001.001101211`  
  
 `1.00020004USD9/12/05 0:000.99970009`  
  
 <span data-ttu-id="d68f6-116">Pour bien utiliser des données sources issues d'un fichier plat, il est important de comprendre comment le Gestionnaire de connexions de fichiers plats interprète les données du fichier plat.</span><span class="sxs-lookup"><span data-stu-id="d68f6-116">When working with flat file source data, it is important to understand how the Flat File connection manager interprets the flat file data.</span></span> <span data-ttu-id="d68f6-117">Si la source du fichier plat est au format Unicode, le gestionnaire de connexions de fichiers plats définit toutes les colonnes avec le type [DT_WSTR] et une largeur par défaut égale à 50.</span><span class="sxs-lookup"><span data-stu-id="d68f6-117">If the flat file source is Unicode, the Flat File connection manager defines all columns as [DT_WSTR] with a default column width of 50.</span></span> <span data-ttu-id="d68f6-118">Si la source du fichier plat est au format ANSI, les colonnes sont définies avec le type [DT_STR] et une largeur égale à 50.</span><span class="sxs-lookup"><span data-stu-id="d68f6-118">If the flat file source is ANSI-encoded, the columns are defined as [DT_STR] with a column width of 50.</span></span> <span data-ttu-id="d68f6-119">Il vous faudra probablement modifier ces valeurs par défaut pour affecter aux colonnes des types String plus appropriés à vos données.</span><span class="sxs-lookup"><span data-stu-id="d68f6-119">You will probably have to change these defaults to make the string column types more appropriate for your data.</span></span> <span data-ttu-id="d68f6-120">Pour cela, vous allez examiner le type de données de la destination dans laquelle les données seront enregistrées, puis choisir le type de données qui convient dans le Gestionnaire de connexions de fichiers plats.</span><span class="sxs-lookup"><span data-stu-id="d68f6-120">To do this, you will need to look at the data type of the destination where the data will be written to and then choose the correct type within the Flat File connection manager.</span></span>  
  
### <a name="looking-at-the-destination"></a><span data-ttu-id="d68f6-121">Étude de la destination</span><span class="sxs-lookup"><span data-stu-id="d68f6-121">Looking at the Destination</span></span>  
 <span data-ttu-id="d68f6-122">La destination finale des données sources est la table de faits **FactCurrency** dans la base de données **AdventureWorksDW**.</span><span class="sxs-lookup"><span data-stu-id="d68f6-122">The ultimate destination for the source data is the **FactCurrency** fact table in **AdventureWorksDW**.</span></span> <span data-ttu-id="d68f6-123">La table de faits **FactCurrency** contient quatre colonnes et des relations avec deux tables de dimension, comme illustré ci-après.</span><span class="sxs-lookup"><span data-stu-id="d68f6-123">The **FactCurrency** fact table has four columns, and has relationships to two dimension tables, as shown in the following table.</span></span>  
  
|<span data-ttu-id="d68f6-124">Nom de la colonne</span><span class="sxs-lookup"><span data-stu-id="d68f6-124">Column Name</span></span>|<span data-ttu-id="d68f6-125">Type de données</span><span class="sxs-lookup"><span data-stu-id="d68f6-125">Data Type</span></span>|<span data-ttu-id="d68f6-126">Table de recherche</span><span class="sxs-lookup"><span data-stu-id="d68f6-126">Lookup Table</span></span>|<span data-ttu-id="d68f6-127">colonne de recherche</span><span class="sxs-lookup"><span data-stu-id="d68f6-127">Lookup Column</span></span>|  
|-----------------|---------------|------------------|-------------------|  
|<span data-ttu-id="d68f6-128">AverageRate</span><span class="sxs-lookup"><span data-stu-id="d68f6-128">AverageRate</span></span>|<span data-ttu-id="d68f6-129">float</span><span class="sxs-lookup"><span data-stu-id="d68f6-129">float</span></span>|<span data-ttu-id="d68f6-130">None</span><span class="sxs-lookup"><span data-stu-id="d68f6-130">None</span></span>|<span data-ttu-id="d68f6-131">None</span><span class="sxs-lookup"><span data-stu-id="d68f6-131">None</span></span>|  
|<span data-ttu-id="d68f6-132">CurrencyKey</span><span class="sxs-lookup"><span data-stu-id="d68f6-132">CurrencyKey</span></span>|<span data-ttu-id="d68f6-133">int (FK)</span><span class="sxs-lookup"><span data-stu-id="d68f6-133">int (FK)</span></span>|<span data-ttu-id="d68f6-134">DimCurrency</span><span class="sxs-lookup"><span data-stu-id="d68f6-134">DimCurrency</span></span>|<span data-ttu-id="d68f6-135">CurrencyKey (PK)</span><span class="sxs-lookup"><span data-stu-id="d68f6-135">CurrencyKey (PK)</span></span>|  
|<span data-ttu-id="d68f6-136">DateKey</span><span class="sxs-lookup"><span data-stu-id="d68f6-136">DateKey</span></span>|<span data-ttu-id="d68f6-137">int (FK)</span><span class="sxs-lookup"><span data-stu-id="d68f6-137">Int (FK)</span></span>|<span data-ttu-id="d68f6-138">DimDate</span><span class="sxs-lookup"><span data-stu-id="d68f6-138">DimDate</span></span>|<span data-ttu-id="d68f6-139">DateKey (PK)</span><span class="sxs-lookup"><span data-stu-id="d68f6-139">DateKey (PK)</span></span>|  
|<span data-ttu-id="d68f6-140">EndOfDayRate</span><span class="sxs-lookup"><span data-stu-id="d68f6-140">EndOfDayRate</span></span>|<span data-ttu-id="d68f6-141">float</span><span class="sxs-lookup"><span data-stu-id="d68f6-141">float</span></span>|<span data-ttu-id="d68f6-142">None</span><span class="sxs-lookup"><span data-stu-id="d68f6-142">None</span></span>|<span data-ttu-id="d68f6-143">None</span><span class="sxs-lookup"><span data-stu-id="d68f6-143">None</span></span>|  
  
### <a name="mapping-source-data-to-be-compatible-with-the-destination"></a><span data-ttu-id="d68f6-144">Mappage des données sources pour la compatibilité avec la destination</span><span class="sxs-lookup"><span data-stu-id="d68f6-144">Mapping Source Data to be Compatible with the Destination</span></span>  
 <span data-ttu-id="d68f6-145">L'analyse du format des données sources et de destination indique que des recherches seront nécessaires pour les valeurs **CurrencyKey** et **DateKey** .</span><span class="sxs-lookup"><span data-stu-id="d68f6-145">Analysis of the source and destination data formats indicates that lookups will be necessary for the **CurrencyKey** and **DateKey** values.</span></span> <span data-ttu-id="d68f6-146">Les transformations qui effectueront ces recherches obtiendront les valeurs **CurrencyKey** et **DateKey** en utilisant les autres clés des tables de dimension **DimCurrency** et **DimDate** .</span><span class="sxs-lookup"><span data-stu-id="d68f6-146">The transformations that will perform these lookups will obtain the **CurrencyKey** and **DateKey** values by using the alternate keys from **DimCurrency** and **DimDate** dimension tables.</span></span>  
  
|<span data-ttu-id="d68f6-147">Colonne de fichier plat</span><span class="sxs-lookup"><span data-stu-id="d68f6-147">Flat File Column</span></span>|<span data-ttu-id="d68f6-148">Nom de la table</span><span class="sxs-lookup"><span data-stu-id="d68f6-148">Table Name</span></span>|<span data-ttu-id="d68f6-149">Nom de la colonne</span><span class="sxs-lookup"><span data-stu-id="d68f6-149">Column Name</span></span>|<span data-ttu-id="d68f6-150">Type de données</span><span class="sxs-lookup"><span data-stu-id="d68f6-150">Data Type</span></span>|  
|----------------------|----------------|-----------------|---------------|  
|<span data-ttu-id="d68f6-151">0</span><span class="sxs-lookup"><span data-stu-id="d68f6-151">0</span></span>|<span data-ttu-id="d68f6-152">FactCurrency</span><span class="sxs-lookup"><span data-stu-id="d68f6-152">FactCurrency</span></span>|<span data-ttu-id="d68f6-153">AverageRate</span><span class="sxs-lookup"><span data-stu-id="d68f6-153">AverageRate</span></span>|<span data-ttu-id="d68f6-154">float</span><span class="sxs-lookup"><span data-stu-id="d68f6-154">float</span></span>|  
|<span data-ttu-id="d68f6-155">1</span><span class="sxs-lookup"><span data-stu-id="d68f6-155">1</span></span>|<span data-ttu-id="d68f6-156">DimCurrency</span><span class="sxs-lookup"><span data-stu-id="d68f6-156">DimCurrency</span></span>|<span data-ttu-id="d68f6-157">CurrencyAlternateKey</span><span class="sxs-lookup"><span data-stu-id="d68f6-157">CurrencyAlternateKey</span></span>|<span data-ttu-id="d68f6-158">nchar (3)</span><span class="sxs-lookup"><span data-stu-id="d68f6-158">nchar (3)</span></span>|  
|<span data-ttu-id="d68f6-159">2</span><span class="sxs-lookup"><span data-stu-id="d68f6-159">2</span></span>|<span data-ttu-id="d68f6-160">DimDate</span><span class="sxs-lookup"><span data-stu-id="d68f6-160">DimDate</span></span>|<span data-ttu-id="d68f6-161">FullDateAlternateKey</span><span class="sxs-lookup"><span data-stu-id="d68f6-161">FullDateAlternateKey</span></span>|<span data-ttu-id="d68f6-162">Date</span><span class="sxs-lookup"><span data-stu-id="d68f6-162">date</span></span>|  
|<span data-ttu-id="d68f6-163">3</span><span class="sxs-lookup"><span data-stu-id="d68f6-163">3</span></span>|<span data-ttu-id="d68f6-164">FactCurrency</span><span class="sxs-lookup"><span data-stu-id="d68f6-164">FactCurrency</span></span>|<span data-ttu-id="d68f6-165">EndOfDayRate</span><span class="sxs-lookup"><span data-stu-id="d68f6-165">EndOfDayRate</span></span>|<span data-ttu-id="d68f6-166">float</span><span class="sxs-lookup"><span data-stu-id="d68f6-166">float</span></span>|  
  
## <a name="lesson-tasks"></a><span data-ttu-id="d68f6-167">Tâches de la leçon</span><span class="sxs-lookup"><span data-stu-id="d68f6-167">Lesson Tasks</span></span>  
 <span data-ttu-id="d68f6-168">Cette leçon contient les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="d68f6-168">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="d68f6-169">Étape 1 : Création d’un nouveau projet Integration Services</span><span class="sxs-lookup"><span data-stu-id="d68f6-169">Step 1: Creating a New Integration Services Project</span></span>](lesson-1-1-creating-a-new-integration-services-project.md)  
  
-   [<span data-ttu-id="d68f6-170">Étape 2 : Ajout et configuration d’un Gestionnaire de connexions de fichiers plats</span><span class="sxs-lookup"><span data-stu-id="d68f6-170">Step 2: Adding and Configuring a Flat File Connection Manager</span></span>](lesson-1-2-adding-and-configuring-a-flat-file-connection-manager.md)  
  
-   [<span data-ttu-id="d68f6-171">Étape 3 : Ajout et configuration d’un Gestionnaire de connexions OLE DB</span><span class="sxs-lookup"><span data-stu-id="d68f6-171">Step 3: Adding and Configuring an OLE DB Connection Manager</span></span>](lesson-1-3-adding-and-configuring-an-ole-db-connection-manager.md)  
  
-   [<span data-ttu-id="d68f6-172">Étape 4 : Ajout d’une tâche de flux de données au package</span><span class="sxs-lookup"><span data-stu-id="d68f6-172">Step 4: Adding a Data Flow Task to the Package</span></span>](lesson-1-4-adding-a-data-flow-task-to-the-package.md)  
  
-   [<span data-ttu-id="d68f6-173">Étape 5 : Ajout et configuration de la source de fichier plat</span><span class="sxs-lookup"><span data-stu-id="d68f6-173">Step 5: Adding and Configuring the Flat File Source</span></span>](lesson-1-5-adding-and-configuring-the-flat-file-source.md)  
  
-   [<span data-ttu-id="d68f6-174">Étape 6 : Ajout et configuration des transformations de recherche</span><span class="sxs-lookup"><span data-stu-id="d68f6-174">Step 6: Adding and Configuring the Lookup Transformations</span></span>](lesson-1-6-adding-and-configuring-the-lookup-transformations.md)  
  
-   [<span data-ttu-id="d68f6-175">Étape 7 : Ajout et configuration de la destination OLE DB</span><span class="sxs-lookup"><span data-stu-id="d68f6-175">Step 7: Adding and Configuring the OLE DB Destination</span></span>](lesson-1-7-adding-and-configuring-the-ole-db-destination.md)  
  
-   [<span data-ttu-id="d68f6-176">Étape 8 : Comment rendre le package de la leçon 1 plus facile à assimiler</span><span class="sxs-lookup"><span data-stu-id="d68f6-176">Step 8: Making the Lesson 1 Package Easier to Understand</span></span>](lesson-1-8-making-the-lesson-1-package-easier-to-understand.md)  
  
-   [<span data-ttu-id="d68f6-177">Étape 9 : Test du package du tutoriel de la leçon 1</span><span class="sxs-lookup"><span data-stu-id="d68f6-177">Step 9: Testing the Lesson 1 Tutorial Package</span></span>](lesson-1-9-testing-the-lesson-1-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="d68f6-178">Démarrer la leçon</span><span class="sxs-lookup"><span data-stu-id="d68f6-178">Start the Lesson</span></span>  
 [<span data-ttu-id="d68f6-179">Étape 1 : Création d’un nouveau projet Integration Services</span><span class="sxs-lookup"><span data-stu-id="d68f6-179">Step 1: Creating a New Integration Services Project</span></span>](lesson-1-1-creating-a-new-integration-services-project.md)  
  
  
