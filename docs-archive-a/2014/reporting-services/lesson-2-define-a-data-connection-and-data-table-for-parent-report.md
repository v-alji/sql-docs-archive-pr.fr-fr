---
title: 'Leçon 2 : définir une connexion de données et une table de données pour le rapport parent | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f02dee0c-85ad-45d4-b707-10e9e8541db9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 045ff576061bf12d163668cb9a57651e591768a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601283"
---
# <a name="lesson-2-define-a-data-connection-and-data-table-for-parent-report"></a><span data-ttu-id="8c524-102">Leçon 2 : définir une connexion de données et une table de données pour le rapport parent</span><span class="sxs-lookup"><span data-stu-id="8c524-102">Lesson 2: Define a Data Connection and Data Table for Parent Report</span></span>
  <span data-ttu-id="8c524-103">Après avoir créé un projet de site Web à l'aide du modèle de site Web ASP.NET pour Visual C#, l'étape suivante consiste à créer une connexion de données et une table de données pour le rapport parent.</span><span class="sxs-lookup"><span data-stu-id="8c524-103">After you create a new website project using the ASP.NET website template for Visual C#, your next step is to create a data connection and a data table for the parent report.</span></span> <span data-ttu-id="8c524-104">Dans ce didacticiel, la connexion de données doit s'établir avec la base de données AdventureWorks2008.</span><span class="sxs-lookup"><span data-stu-id="8c524-104">In this tutorial the data connection is to the AdventureWorks2008 database.</span></span> <span data-ttu-id="8c524-105">Vous avez également la possibilité de vous connecter à la base de données AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="8c524-105">You also have the option of connecting to the AdventureWorks2012 database.</span></span>  
  
### <a name="to-define-a-data-connection-and-data-table-by-adding-a-dataset-for-parent-report"></a><span data-ttu-id="8c524-106">Pour définir une connexion de données et une table de données en ajoutant un dataset (pour le rapport parent)</span><span class="sxs-lookup"><span data-stu-id="8c524-106">To define a data connection and Data Table by adding a DataSet (for parent report)</span></span>  
  
1.  <span data-ttu-id="8c524-107">Dans le menu **Site Web** , sélectionnez **Ajouter un nouvel élément**.</span><span class="sxs-lookup"><span data-stu-id="8c524-107">On the **Website** menu, select **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="8c524-108">Dans la boîte de dialogue **Ajouter un nouvel élément** , sélectionnez **DataSet** , puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="8c524-108">In the **Add New Item** dialog box, select **DataSet** and click **Add**.</span></span> <span data-ttu-id="8c524-109">Lorsque vous y êtes invité, vous devez ajouter l’élément au dossier **App_Code** en cliquant sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="8c524-109">When prompted you should add the item to the **App_Code** folder by clicking **Yes**.</span></span>  
  
     <span data-ttu-id="8c524-110">Ce faisant, vous ajoutez un nouveau fichier XSD **DataSet1.xsd** au projet et ouvrez le Concepteur de DataSet.</span><span class="sxs-lookup"><span data-stu-id="8c524-110">This adds a new XSD file **DataSet1.xsd** to the project and opens the DataSet Designer.</span></span>  
  
3.  <span data-ttu-id="8c524-111">À partir de la fenêtre boîte à outils, faites glisser un contrôle **[TableAdapter](https://msdn.microsoft.com/library/bz9tthwx\(v=vs.100\).aspx)** vers l’aire de conception.</span><span class="sxs-lookup"><span data-stu-id="8c524-111">From the Toolbox window, drag a **[TableAdapter](https://msdn.microsoft.com/library/bz9tthwx\(v=vs.100\).aspx)** control to the design surface.</span></span> <span data-ttu-id="8c524-112">Cette opération permet de lancer l’Assistant de configuration de **TableAdapter** .</span><span class="sxs-lookup"><span data-stu-id="8c524-112">This launches the **TableAdapter** Configuration Wizard.</span></span>  
  
4.  <span data-ttu-id="8c524-113">Sur la page **choisir votre connexion de données** , cliquez sur **nouvelle connexion**.</span><span class="sxs-lookup"><span data-stu-id="8c524-113">On the **Choose Your Data Connection** page, click **New Connection**.</span></span>  
  
5.  <span data-ttu-id="8c524-114">S’il s’agit de la première fois que vous avez créé une source de données dans Visual Studio, la page **choisir la source de données** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="8c524-114">If this is the first time you've created a data source in Visual Studio, you will see the **Choose Data Source** page.</span></span> <span data-ttu-id="8c524-115">Dans la zone **Source de données** , sélectionnez **Microsoft SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="8c524-115">In the **Data Source** box, select **Microsoft SQL Server**.</span></span>  
  
6.  <span data-ttu-id="8c524-116">Dans la boîte de dialogue **Ajouter une connexion** , effectuez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="8c524-116">In the **Add Connection** dialog box, perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="8c524-117">Dans la zone **nom du serveur** , entrez le serveur sur lequel se trouve la base de données **AdventureWorks2008** .</span><span class="sxs-lookup"><span data-stu-id="8c524-117">In the **Server name** box, enter the server where the **AdventureWorks2008** database is located.</span></span>  
  
         <span data-ttu-id="8c524-118">L’instance SQL Server Express par défaut est **(local)\sqlexpress**.</span><span class="sxs-lookup"><span data-stu-id="8c524-118">The default SQL Server Express instance is **(local)\sqlexpress**.</span></span>  
  
    2.  <span data-ttu-id="8c524-119">Dans la section **Connexion au serveur** , sélectionnez l’option qui permet d’accéder aux données.</span><span class="sxs-lookup"><span data-stu-id="8c524-119">In the **Log on to the server** section, select the option that provides you access to the data.</span></span> <span data-ttu-id="8c524-120">**Utiliser l’authentification Windows** est la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="8c524-120">**Use Windows Authentication** is the default.</span></span>  
  
    3.  <span data-ttu-id="8c524-121">Dans la liste déroulante **Sélectionner ou entrer un nom de base de données** , cliquez sur **AdventureWorks2008**.</span><span class="sxs-lookup"><span data-stu-id="8c524-121">From the **Select or enter a database name** drop-down list, click **AdventureWorks2008**.</span></span>  
  
    4.  <span data-ttu-id="8c524-122">Cliquez sur **OK**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="8c524-122">Click **OK**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="8c524-123">Si vous avez sélectionné **Utiliser l’authentification SQL Server** à l’étape 6 (b), déterminez s’il faut inclure les données sensibles dans la chaîne ou définir les informations dans votre code d’application.</span><span class="sxs-lookup"><span data-stu-id="8c524-123">If you selected **Use SQL Server Authentication** in the Step 6 (b), select the option whether to include the sensitive data in the string or set the information in your application code.</span></span>  
  
8.  <span data-ttu-id="8c524-124">Sur la page **enregistrer la chaîne de connexion dans le fichier de configuration de l’application** , tapez le nom de la chaîne de connexion ou acceptez le **AdventureWorks2008ConnectionString**par défaut.</span><span class="sxs-lookup"><span data-stu-id="8c524-124">On the **Save the Connection String to the Application Configuration File** page, type in the name for the connection string or accept the default **AdventureWorks2008ConnectionString**.</span></span> <span data-ttu-id="8c524-125">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="8c524-125">Click **Next**.</span></span>  
  
9. <span data-ttu-id="8c524-126">Dans la page **choisir un type de commande** , sélectionnez **utiliser des instructions SQL**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="8c524-126">On the **Choose a Command Type** page, select **Use SQL Statements**, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="8c524-127">Dans la page **Entrez une instruction SQL** , entrez la requête Transact-SQL suivante pour récupérer des données de la base de données **AdventureWorks2008** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="8c524-127">On the **Enter a SQL Statement** page, enter the following Transact-SQL query to retrieve data from the **AdventureWorks2008** database, and then click **Next**.</span></span>  
  
    ```  
    SELECT ProductID, Name, ProductNumber, SafetyStockLevel, ReorderPoint FROM  Production.Product Order By ProductID  
    ```  
  
     <span data-ttu-id="8c524-128">Vous pouvez également créer la requête en cliquant sur **Générateur de requêtes**, puis vérifier la requête en cliquant sur **exécuter la requête**.</span><span class="sxs-lookup"><span data-stu-id="8c524-128">You can also create the query by clicking **Query Builder**, and then verify the query by clicking **Execute Query**.</span></span> <span data-ttu-id="8c524-129">Si la requête ne retourne pas les données attendues, c'est peut-être que vous utilisez une version antérieure d'AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="8c524-129">If the query does not return the expected data, you might be using an earlier version of AdventureWorks.</span></span> <span data-ttu-id="8c524-130">Pour plus d’informations sur l’installation de la version **AdventureWorks2008** d’AdventureWorks, consultez [procédure pas à pas : installation de la base de données AdventureWorks](https://msdn.microsoft.com/library/aa992075\(v=vs.100\).aspx).</span><span class="sxs-lookup"><span data-stu-id="8c524-130">For more information about installing the **AdventureWorks2008** version of AdventureWorks, see [Walkthrough: Installing the AdventureWorks Database](https://msdn.microsoft.com/library/aa992075\(v=vs.100\).aspx).</span></span>  
  
11. <span data-ttu-id="8c524-131">Dans la page **choisir les méthodes à générer** , veillez à décocher **créer des méthodes pour envoyer des mises à jour directement à la base de données (GenerateDBDirectMethods)**, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="8c524-131">On the **Choose Methods to Generate** page, be sure to uncheck **Create methods to send updates directly to the database (GenerateDBDirectMethods)**, and then click **Finish**.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="8c524-132">Veillez à désactiver la création</span><span class="sxs-lookup"><span data-stu-id="8c524-132">Be sure to uncheck Create</span></span>  
  
     <span data-ttu-id="8c524-133">Vous venez de terminer la configuration de l'objet ADO.NET DataTable comme source de données pour votre rapport.</span><span class="sxs-lookup"><span data-stu-id="8c524-133">You have now completed configuring the ADO.NET DataTable object as the data source for your report.</span></span> <span data-ttu-id="8c524-134">Sur la page Concepteur de DataSet dans Visual Studio, vous devez voir l'objet DataTable que vous venez d'ajouter, répertoriant les colonnes spécifiées dans la requête.</span><span class="sxs-lookup"><span data-stu-id="8c524-134">On the DataSet Designer page in Visual Studio, you should see the DataTable object you added, listing the columns specified in the query.</span></span> <span data-ttu-id="8c524-135">DataSet1 contient les données de la table Product, en fonction de la requête.</span><span class="sxs-lookup"><span data-stu-id="8c524-135">DataSet1 contains the data from the Product table, based on the query.</span></span>  
  
12. <span data-ttu-id="8c524-136">Enregistrez le fichier .</span><span class="sxs-lookup"><span data-stu-id="8c524-136">Save the file.</span></span>  
  
13. <span data-ttu-id="8c524-137">Pour afficher un aperçu des données, cliquez sur **Aperçu** des données dans le menu **données** , puis cliquez sur **Aperçu**.</span><span class="sxs-lookup"><span data-stu-id="8c524-137">To preview the data, click **Preview Data** on the **Data** menu, and then click **Preview**.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="8c524-138">Tâche suivante</span><span class="sxs-lookup"><span data-stu-id="8c524-138">Next Task</span></span>  
 <span data-ttu-id="8c524-139">Vous venez de créer une connexion de données et une table de données pour le rapport parent.</span><span class="sxs-lookup"><span data-stu-id="8c524-139">You have successfully created a data connection and a data table for the parent report.</span></span> <span data-ttu-id="8c524-140">Vous allez à présent concevoir le rapport parent à l'aide de l'Assistant Rapport.</span><span class="sxs-lookup"><span data-stu-id="8c524-140">Next, you will design the parent report using the Report Wizard.</span></span>  
  
  
