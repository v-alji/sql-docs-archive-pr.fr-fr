---
title: 'Didacticiel : utilisation de la source OData [SSIS] | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 2c64cf8b-5edb-48df-8ffe-697096258f71
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a13b04494ed00251774b490b1cc929769a869acb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613031"
---
# <a name="tutorial-using-the-odata-source-ssis"></a><span data-ttu-id="f167c-102">Didacticiel : Utiliser la source OData [SSIS]</span><span class="sxs-lookup"><span data-stu-id="f167c-102">Tutorial: Using the OData Source [SSIS]</span></span>
  <span data-ttu-id="f167c-103">Ce tutoriel vous guide dans le processus d’extraction de la collection **Employees** de l’exemple de service OData **Northwind** (http://services.odata.org/V3/Northwind/Northwind.svc/) ), puis de son chargement dans un fichier plat.</span><span class="sxs-lookup"><span data-stu-id="f167c-103">This tutorial walks you through the process to extract the **Employees** collection from the sample **Northwind** OData service (http://services.odata.org/V3/Northwind/Northwind.svc/), and then load it into a flat file.</span></span>  
  
## <a name="1-create-an-integration-services-project"></a><span data-ttu-id="f167c-104">1. Créer un projet Integration Services</span><span class="sxs-lookup"><span data-stu-id="f167c-104">1. Create an Integration Services Project</span></span>  
  
1.  <span data-ttu-id="f167c-105">Lancez **SQL Server Data Tools** ou [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f167c-105">Launch **SQL Server Data Tools** or [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span>  
  
2.  <span data-ttu-id="f167c-106">Cliquez sur **Fichier**, pointez le curseur de la souris sur **Nouveau**, puis cliquez sur **Projet**.</span><span class="sxs-lookup"><span data-stu-id="f167c-106">Click **File**, point to **New**, and click **Project**.</span></span>  
  
3.  <span data-ttu-id="f167c-107">Dans la boîte de dialogue **Nouveau projet** , développez **Installé**, puis **Modèles**, **Business Intelligence**, et cliquez sur **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="f167c-107">In the **New Project** dialog box, expand **Installed**, expand **Templates**, expand **Business Intelligence**, and click **Integration Services**.</span></span>  
  
4.  <span data-ttu-id="f167c-108">Sélectionnez **Projet Integration Services** pour le type de projet.</span><span class="sxs-lookup"><span data-stu-id="f167c-108">Select **Integration Services Project** for the type of project.</span></span>  
  
5.  <span data-ttu-id="f167c-109">Entrez un **nom** et sélectionnez un **emplacement** pour le projet, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f167c-109">Enter a **name** and select a **location** for the project, and click **OK**.</span></span>  
  
## <a name="2-add-and-configure-odata-source-to-the-ssis-package"></a><span data-ttu-id="f167c-110">2. Ajouter et configurer la source OData sur le package SSIS</span><span class="sxs-lookup"><span data-stu-id="f167c-110">2. Add and Configure OData Source to the SSIS Package</span></span>  
  
1.  <span data-ttu-id="f167c-111">Glissez-déplacez une **Tâche de flux de données** de la **Boîte à outil SSIS** vers l’aire de conception de flux de contrôle pour votre package SSIS.</span><span class="sxs-lookup"><span data-stu-id="f167c-111">Drag-drop a **Data Flow Task** from the **SSIS Toolbox** on to the control flow design surface of your SSIS package.</span></span>  
  
2.  <span data-ttu-id="f167c-112">Cliquez sur l'onglet **Flux de données** , ou cliquez sur la **Tâche de flux de données** que vous venez d'ajouter pour lancer l' **Aire de conception de flux de données**.</span><span class="sxs-lookup"><span data-stu-id="f167c-112">Click the **Data Flow** tab, or double click on the newly added **Data Flow Task** to launch the **Data Flow design surface**.</span></span>  
  
3.  <span data-ttu-id="f167c-113">Glissez-déplacez la **Source OData** du groupe **Commun** dans la **Boîte à outil SSIS**.</span><span class="sxs-lookup"><span data-stu-id="f167c-113">Drag-drop **OData Source** from the **Common** group in the **SSIS Toolbox**.</span></span> <span data-ttu-id="f167c-114">Lorsque la **Source OData** est installée pour la première fois, elle s'affiche sous le groupe **Commun** dans la **Boîte à outil SSIS**.</span><span class="sxs-lookup"><span data-stu-id="f167c-114">When the **OData Source** is first installed, it will appear under the **Common** group in the **SSIS Toolbox**.</span></span>  
  
4.  <span data-ttu-id="f167c-115">Double-cliquez sur le composant **Source OData** pour ouvrir la boîte de dialogue **Éditeur de source OData** .</span><span class="sxs-lookup"><span data-stu-id="f167c-115">Double click the **OData Source** component to launch the **OData Source Editor** dialog box.</span></span>  
  
5.  <span data-ttu-id="f167c-116">Cliquez sur **Nouveau...** pour ajouter un nouveau gestionnaire de connexions OData.</span><span class="sxs-lookup"><span data-stu-id="f167c-116">Click **New...** to add a new OData Connection Manager.</span></span>  
  
6.  <span data-ttu-id="f167c-117">Entrez l'URL du service OData pour l' **Emplacement du document de service**.</span><span class="sxs-lookup"><span data-stu-id="f167c-117">Enter the OData service URL for **Service document location**.</span></span> <span data-ttu-id="f167c-118">Il peut s'agir de l'URL qui renvoie au document de service, ou bien à un flux ou à une entité spécifique.</span><span class="sxs-lookup"><span data-stu-id="f167c-118">This can be the URL to the service document, or to a specific feed or entity.</span></span> <span data-ttu-id="f167c-119">Pour les besoins de ce didacticiel, tapez [http://services.odata.org/V3/Northwind/Northwind.svc/](http://services.odata.org/V3/Northwind/Northwind.svc/) .</span><span class="sxs-lookup"><span data-stu-id="f167c-119">For the purpose of this tutorial, type [http://services.odata.org/V3/Northwind/Northwind.svc/](http://services.odata.org/V3/Northwind/Northwind.svc/).</span></span>  
  
7.  <span data-ttu-id="f167c-120">Assurez-vous que l' **Authentification Windows** est sélectionnée pour l' **authentification** à utiliser pour accéder au service OData.</span><span class="sxs-lookup"><span data-stu-id="f167c-120">Confirm that **Windows Authentication** is selected for the **authentication** to use to access the OData Service.</span></span> <span data-ttu-id="f167c-121">L'**Authentification Windows** est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="f167c-121">**Windows Authentication** is selected by default.</span></span> <span data-ttu-id="f167c-122">Pour utiliser l'authentification de base, sélectionnez **Utiliser ce nom d'utilisateur et ce mot de passe**.</span><span class="sxs-lookup"><span data-stu-id="f167c-122">To use basic authentication, select **Use this user name and password**.</span></span>  
  
8.  <span data-ttu-id="f167c-123">Cliquez sur **Tester la connexion** à la connexion, puis cliquez sur **OK** pour créer une instance du gestionnaire de connexions OData.</span><span class="sxs-lookup"><span data-stu-id="f167c-123">Click **Test Connection** to the connection, and click **OK** to create an instance of OData Connection Manager.</span></span>  
  
9. <span data-ttu-id="f167c-124">Dans la boîte de dialogue **Éditeur de source OData** , assurez-vous que **Collection** est sélectionné pour l'option **Utiliser la collection sur le chemin d'accès de la ressource** .</span><span class="sxs-lookup"><span data-stu-id="f167c-124">In the **OData Source Editor** Dialog Box, confirm that **Collection** is selected for **Use collection on resource path** option.</span></span>  
  
10. <span data-ttu-id="f167c-125">Dans la liste déroulante **Collection** , sélectionnez **Employés**.</span><span class="sxs-lookup"><span data-stu-id="f167c-125">From the **Collection** drop down list, select **Employees**.</span></span>  
  
11. <span data-ttu-id="f167c-126">Entrez toutes les options ou filtres de requête OData supplémentaires pour **Options de requête**.</span><span class="sxs-lookup"><span data-stu-id="f167c-126">Enter any additional OData query options or filters for **Query Options**.</span></span> <span data-ttu-id="f167c-127">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="f167c-127">Ex.</span></span> <span data-ttu-id="f167c-128">$orderby=CompanyName&$top=100.</span><span class="sxs-lookup"><span data-stu-id="f167c-128">$orderby=CompanyName&$top=100.</span></span> <span data-ttu-id="f167c-129">Pour les besoins de ce didacticiel, entrez **$top=5**.</span><span class="sxs-lookup"><span data-stu-id="f167c-129">For the purpose of this tutorial, enter **$top=5**.</span></span>  
  
12. <span data-ttu-id="f167c-130">Cliquez sur **Aperçu** pour afficher un aperçu des données.</span><span class="sxs-lookup"><span data-stu-id="f167c-130">Click **Preview** to preview the data.</span></span>  
  
13. <span data-ttu-id="f167c-131">Cliquez sur **Colonnes** dans le volet de navigation gauche pour basculer vers la page **Colonnes** .</span><span class="sxs-lookup"><span data-stu-id="f167c-131">Click **Columns** in the left navigation pane to switch to the **Columns** page.</span></span>  
  
14. <span data-ttu-id="f167c-132">Sélectionnez **EmployeeID**, **FirstName**, **LastName** et **Colonnes externes disponibles** en activant les cases à cocher.</span><span class="sxs-lookup"><span data-stu-id="f167c-132">Select **EmployeeID**, **FirstName**, and **LastName** from **Available External Columns** by checking the check boxes.</span></span>  
  
15. <span data-ttu-id="f167c-133">Cliquez sur **OK** pour fermer la boîte de dialogue **Éditeur de source OData** .</span><span class="sxs-lookup"><span data-stu-id="f167c-133">Click **OK** to close the **OData Source Editor** dialog box.</span></span>  
  
## <a name="3-add-flat-file-destination-and-test-the-solution"></a><span data-ttu-id="f167c-134">3. Ajouter une destination de fichier plat et tester la solution</span><span class="sxs-lookup"><span data-stu-id="f167c-134">3. Add Flat File Destination and Test the Solution</span></span>  
  
1.  <span data-ttu-id="f167c-135">Glissez-déplacez une **Destination de fichier plat** de la **Boîte à outil SSIS** vers l’aire de conception du flux de données sous le composant **Source OData** .</span><span class="sxs-lookup"><span data-stu-id="f167c-135">Now, drag-drop a **Flat File Destination** from **SSIS Toolbox** to the Data Flow design surface below the **OData Source** component.</span></span>  
  
2.  <span data-ttu-id="f167c-136">Connectez le composant **Source OData** au composant **Destination de fichier plat** avec la flèche bleue.</span><span class="sxs-lookup"><span data-stu-id="f167c-136">Connect **OData Source** component with the **Flat File Destination** component using blue arrow.</span></span>  
  
3.  <span data-ttu-id="f167c-137">Double-cliquez sur **Destination de fichier plat**.</span><span class="sxs-lookup"><span data-stu-id="f167c-137">Double-click on **Flat File Destination**.</span></span> <span data-ttu-id="f167c-138">Vous devez voir s'afficher la boîte de dialogue **Éditeur de destination de fichier plat** .</span><span class="sxs-lookup"><span data-stu-id="f167c-138">You should see the **Flat File Destination Editor** dialog box.</span></span>  
  
4.  <span data-ttu-id="f167c-139">Dans la boîte de dialogue **Éditeur de destination de fichier plat** , cliquez sur **Nouveau** pour créer un nouveau gestionnaire de connexions de fichiers plats.</span><span class="sxs-lookup"><span data-stu-id="f167c-139">In the **Flat File Destination Editor** dialog box, click **New** to create a new flat file connection manager.</span></span>  
  
5.  <span data-ttu-id="f167c-140">Dans la boîte de dialogue **Format de fichier plat** , sélectionnez **Délimité**.</span><span class="sxs-lookup"><span data-stu-id="f167c-140">In the **Flat File Format** dialog box, select **Delimited**.</span></span> <span data-ttu-id="f167c-141">Vous devez voir s'afficher la boîte de dialogue **Éditeur du gestionnaire de connexions de fichiers plats** .</span><span class="sxs-lookup"><span data-stu-id="f167c-141">You should see the **Flat File Connection Manager Editor** dialog box.</span></span>  
  
6.  <span data-ttu-id="f167c-142">Dans la boîte de dialogue **Éditeur du gestionnaire de connexions de fichiers plats** , pour **Nom de fichier**, entrez **c:\Employees.txt**.</span><span class="sxs-lookup"><span data-stu-id="f167c-142">In the **Flat File Connection Manager Editor** dialog box, for the **File name**, enter **c:\Employees.txt**.</span></span>  
  
7.  <span data-ttu-id="f167c-143">Cliquez sur **Colonnes**dans le volet de navigation gauche.</span><span class="sxs-lookup"><span data-stu-id="f167c-143">In the left navigation pane, click **Columns**.</span></span> <span data-ttu-id="f167c-144">Vous pouvez définir les données de cette page.</span><span class="sxs-lookup"><span data-stu-id="f167c-144">You can preview the data on this page.</span></span>  
  
8.  <span data-ttu-id="f167c-145">Cliquez sur OK pour fermer la boîte de dialogue **Éditeur du gestionnaire de connexions de fichiers plats** .</span><span class="sxs-lookup"><span data-stu-id="f167c-145">Click OK to close the **Flat File Connection Manager** Editor dialog box.</span></span>  
  
9. <span data-ttu-id="f167c-146">Dans la boîte de dialogue **Éditeur de destination de fichier plat** , cliquez sur **Mappages** dans le volet de navigation gauche.</span><span class="sxs-lookup"><span data-stu-id="f167c-146">In the **Flat File Destination Editor** dialog box, click **Mappings** in the left navigation pane.</span></span> <span data-ttu-id="f167c-147">Vérifiez les mappages.</span><span class="sxs-lookup"><span data-stu-id="f167c-147">Review the mappings.</span></span>  
  
10. <span data-ttu-id="f167c-148">Cliquez sur OK pour fermer la boîte de dialogue **Éditeur de destination de fichier plat** .</span><span class="sxs-lookup"><span data-stu-id="f167c-148">Click OK to close the **Flat File Destination Editor** dialog box.</span></span>  
  
11. <span data-ttu-id="f167c-149">Compilez et exécutez le package SSIS.</span><span class="sxs-lookup"><span data-stu-id="f167c-149">Compile and execute the SSIS package.</span></span> <span data-ttu-id="f167c-150">Vérifiez que le fichier de sortie est créé avec l'ID, le prénom et le nom de 5 employés du flux OData.</span><span class="sxs-lookup"><span data-stu-id="f167c-150">Verify that the output file is created with ID, First Name, and Last Name for 5 employees from the OData feed.</span></span>  
  
  
