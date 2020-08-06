---
title: 'Leçon 4 : définir une connexion de données et une table de données pour le rapport enfant | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a6aa2c56-227c-43c5-a28e-c7104131ac5e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6d9144d960ad933afa65f9d4483e96b5f732d944
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601962"
---
# <a name="lesson-4-define-a-data-connection-and-data-table-for-child-report"></a><span data-ttu-id="3de5a-102">Leçon 4 : définir une connexion de données et une table de données pour le rapport enfant</span><span class="sxs-lookup"><span data-stu-id="3de5a-102">Lesson 4: Define a Data Connection and Data Table for Child Report</span></span>
  <span data-ttu-id="3de5a-103">Après avoir créé le rapport parent, l'étape suivante consiste à créer une connexion de données et une table de données pour le rapport enfant.</span><span class="sxs-lookup"><span data-stu-id="3de5a-103">After you design the parent report, you next step is to create a data connection and a data table for the child report.</span></span> <span data-ttu-id="3de5a-104">Dans ce didacticiel, la connexion de données doit s'établir avec la base de données AdventureWorks2008.</span><span class="sxs-lookup"><span data-stu-id="3de5a-104">In this tutorial the data connection is to the AdventureWorks2008 database.</span></span> <span data-ttu-id="3de5a-105">Vous avez également la possibilité de vous connecter à la base de données AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="3de5a-105">You also have the option of connecting to the AdventureWorks2012 database.</span></span>  
  
### <a name="to-define-a-data-connection-and-datatable-by-adding-a-dataset-for-child-report"></a><span data-ttu-id="3de5a-106">Pour définir une connexion de données et un objet DataTable en ajoutant un DataSet (pour le rapport enfant)</span><span class="sxs-lookup"><span data-stu-id="3de5a-106">To define a data connection and DataTable by adding a DataSet (for child report)</span></span>  
  
1.  <span data-ttu-id="3de5a-107">Dans le menu **site Web** , cliquez sur **Ajouter un nouvel élément**.</span><span class="sxs-lookup"><span data-stu-id="3de5a-107">On the **Website** menu, click **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="3de5a-108">Dans la boîte de dialogue **Ajouter un nouvel élément** , cliquez sur **DataSet** , puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="3de5a-108">In the **Add New Item** dialog box, click **DataSet** and then click **Add**.</span></span> <span data-ttu-id="3de5a-109">Lorsque vous y êtes invité, vous devez ajouter l’élément au dossier **App_Code** en cliquant sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="3de5a-109">When prompted, you should add the item to the **App_Code** folder by clicking **Yes**.</span></span>  
  
     <span data-ttu-id="3de5a-110">Vous ajoutez ainsi un nouveau fichier XSD **DataSet2.xsd** au projet et ouvrez le Concepteur de DataSet.</span><span class="sxs-lookup"><span data-stu-id="3de5a-110">This adds a new XSD file **DataSet2.xsd** to the project and opens the DataSet Designer.</span></span>  
  
3.  <span data-ttu-id="3de5a-111">À partir de la fenêtre Boîte à outils, faites glisser un contrôle **TableAdapter** dans l’aire de conception.</span><span class="sxs-lookup"><span data-stu-id="3de5a-111">From the Toolbox window, drag a **TableAdapter** control to the design surface.</span></span> <span data-ttu-id="3de5a-112">Cette opération permet de lancer l’Assistant de configuration de **TableAdapter** .</span><span class="sxs-lookup"><span data-stu-id="3de5a-112">This launches the **TableAdapter** Configuration Wizard.</span></span>  
  
4.  <span data-ttu-id="3de5a-113">Sur la page **choisir votre connexion de données** , cliquez sur **nouvelle connexion**.</span><span class="sxs-lookup"><span data-stu-id="3de5a-113">On the **Choose Your Data Connection** page, click **New Connection**.</span></span>  
  
5.  <span data-ttu-id="3de5a-114">Dans la boîte de dialogue **Ajouter une connexion** , effectuez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="3de5a-114">In the **Add Connection** dialog box, perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="3de5a-115">Dans la zone **nom du serveur** , entrez le serveur sur lequel se trouve la base de données **AdventureWorks2008** .</span><span class="sxs-lookup"><span data-stu-id="3de5a-115">In the **Server name** box, enter the server where the **AdventureWorks2008** database is located.</span></span>  
  
         <span data-ttu-id="3de5a-116">L’instance SQL Server Express par défaut est **(local)\sqlexpress**.</span><span class="sxs-lookup"><span data-stu-id="3de5a-116">The default SQL Server Express instance is **(local)\sqlexpress**.</span></span>  
  
    2.  <span data-ttu-id="3de5a-117">Dans la section **Connexion au serveur** , sélectionnez l’option qui permet d’accéder aux données.</span><span class="sxs-lookup"><span data-stu-id="3de5a-117">In the **Log on to the server** section, select the option that provides you access to the data.</span></span> <span data-ttu-id="3de5a-118">**Utiliser l’authentification Windows** est la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="3de5a-118">**Use Windows Authentication** is the default.</span></span>  
  
    3.  <span data-ttu-id="3de5a-119">Dans la liste déroulante **Sélectionner ou entrer un nom de base de données** , cliquez sur **AdventureWorks2008**.</span><span class="sxs-lookup"><span data-stu-id="3de5a-119">From the **Select or enter a database name** drop-down list, click **AdventureWorks2008**.</span></span>  
  
    4.  <span data-ttu-id="3de5a-120">Cliquez sur **OK**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="3de5a-120">Click **OK**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="3de5a-121">Si vous avez sélectionné **Utiliser l’authentification SQL Server** à l’étape 5 (b), choisissez s’il faut inclure les données sensibles dans la chaîne ou définir les informations dans votre code d’application.</span><span class="sxs-lookup"><span data-stu-id="3de5a-121">If you selected **Use SQL Server Authentication** in Step 5 (b), select the option whether to include the sensitive data in the string or set the information in your application code.</span></span>  
  
7.  <span data-ttu-id="3de5a-122">Sur la page **enregistrer la chaîne de connexion dans le fichier de configuration de l’application** , tapez le nom de la chaîne de connexion ou acceptez le **AdventureWorks2008ConnectionString**par défaut.</span><span class="sxs-lookup"><span data-stu-id="3de5a-122">On the **Save the Connection String to the Application Configuration File** page, type in the name for the connection string or accept the default **AdventureWorks2008ConnectionString**.</span></span> <span data-ttu-id="3de5a-123">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="3de5a-123">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="3de5a-124">Dans la page **choisir un type de commande** , sélectionnez **utiliser des instructions SQL**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="3de5a-124">On the **Choose a Command Type** page, select **Use SQL Statements**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="3de5a-125">Dans la page **Entrez une instruction SQL** , entrez la requête Transact-SQL suivante pour récupérer des données de la base de données **AdventureWorks2008** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="3de5a-125">On the **Enter a SQL Statement** page, enter the following Transact-SQL query to retrieve data from the **AdventureWorks2008** database, and then click **Next**.</span></span>  
  
    ```  
    SELECT PurchaseOrderID, PurchaseOrderDetailID, OrderQty, ProductID, ReceivedQty, RejectedQty, StockedQty FROM Purchasing.PurchaseOrderDetail  
    ```  
  
     <span data-ttu-id="3de5a-126">Vous pouvez également créer la requête en cliquant sur **Générateur de requêtes**, puis vérifier la requête en cliquant sur le bouton **exécuter la requête** .</span><span class="sxs-lookup"><span data-stu-id="3de5a-126">You can also create the query by clicking **Query Builder**, and then verify the query by clicking **Execute Query** button.</span></span> <span data-ttu-id="3de5a-127">Si la requête ne retourne pas les données attendues, c'est peut-être que vous utilisez une version antérieure d'AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="3de5a-127">If the query does not return the expected data, you might be using an earlier version of AdventureWorks.</span></span> <span data-ttu-id="3de5a-128">Pour plus d’informations sur l’installation de la version **AdventureWorks2008** d’AdventureWorks, consultez [procédure pas à pas : installation de la base de données AdventureWorks](https://msdn.microsoft.com/library/aa992075\(v=vs.100\).aspx).</span><span class="sxs-lookup"><span data-stu-id="3de5a-128">For more information about installing the **AdventureWorks2008** version of AdventureWorks, see [Walkthrough: Installing the AdventureWorks Database](https://msdn.microsoft.com/library/aa992075\(v=vs.100\).aspx).</span></span>  
  
10. <span data-ttu-id="3de5a-129">Dans la page **choisir les méthodes à générer** , décochez **créer des méthodes pour envoyer des mises à jour directement à la base de données (GenerateDBDirectMethods)**, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="3de5a-129">On the **Choose Methods to Generate** page, uncheck **Create methods to send updates directly to the database (GenerateDBDirectMethods)**, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="3de5a-130">Vous avez maintenant terminé la configuration du [DataTable](https://msdn.microsoft.com/library/system.data.datatable\(v=vs.100\).aspx) ADO.net comme source de données pour votre rapport.</span><span class="sxs-lookup"><span data-stu-id="3de5a-130">You have now completed configuring the ADO.NET [DataTable](https://msdn.microsoft.com/library/system.data.datatable\(v=vs.100\).aspx) as data source for your report.</span></span> <span data-ttu-id="3de5a-131">Dans la page du Concepteur de DataSet dans Visual Studio, vous devez voir l’objet **DataTable** que vous avez ajouté, qui répertorie les colonnes spécifiées dans la requête.</span><span class="sxs-lookup"><span data-stu-id="3de5a-131">On the DataSet Designer page in Visual Studio, you should see the **DataTable** you added, listing the columns specified in the query.</span></span> <span data-ttu-id="3de5a-132">DataSet2 contient les données de la table PurchaseOrderDetail, en fonction de la requête.</span><span class="sxs-lookup"><span data-stu-id="3de5a-132">DataSet2 contains the data from the PurhcaseOrderDetail table, based on the query.</span></span>  
  
11. <span data-ttu-id="3de5a-133">Enregistrez le fichier .</span><span class="sxs-lookup"><span data-stu-id="3de5a-133">Save the file.</span></span>  
  
12. <span data-ttu-id="3de5a-134">Pour afficher un aperçu des données, cliquez sur **Aperçu** des données dans le menu **données** , puis cliquez sur **Aperçu**.</span><span class="sxs-lookup"><span data-stu-id="3de5a-134">To preview the data, click **Preview Data** on the **Data** menu, and then click **Preview**.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="3de5a-135">Tâche suivante</span><span class="sxs-lookup"><span data-stu-id="3de5a-135">Next Task</span></span>  
 <span data-ttu-id="3de5a-136">Vous venez de créer une connexion de données et une table de données pour le rapport enfant.</span><span class="sxs-lookup"><span data-stu-id="3de5a-136">You have successfully created a data connection and data table for the child report.</span></span> <span data-ttu-id="3de5a-137">Vous allez à présent concevoir le rapport enfant à l'aide de l'Assistant Rapport.</span><span class="sxs-lookup"><span data-stu-id="3de5a-137">Next, you will design the child report using the Report Wizard.</span></span>  
  
  
