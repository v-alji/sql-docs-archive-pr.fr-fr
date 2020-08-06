---
title: 'Leçon 8 : créer un filtre de données | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 19ccbdba-e3da-40a4-b652-32c628cf32e5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9c11d4cf83619e53cd7e8f00091c66cc8e50ad76
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601954"
---
# <a name="lesson-8-create-a-data-filter"></a><span data-ttu-id="d0427-102">Leçon 8 : créer un filtre de données</span><span class="sxs-lookup"><span data-stu-id="d0427-102">Lesson 8: Create a Data Filter</span></span>
  <span data-ttu-id="d0427-103">Après avoir ajouté une action d'extraction dans le rapport parent, l'étape suivante consiste à créer un filtre de données pour la table de données que vous avez définie pour le rapport enfant.</span><span class="sxs-lookup"><span data-stu-id="d0427-103">After you add a drillthrough action on the parent report, your next step is to create a data filter for the data table that you defined for the child report.</span></span>  
  
 <span data-ttu-id="d0427-104">Vous pouvez créer un filtre de table **ou** un filtre de requête pour le rapport d’extraction.</span><span class="sxs-lookup"><span data-stu-id="d0427-104">You can create a table-based filter **or** a query filter for the drillthrough report.</span></span> <span data-ttu-id="d0427-105">Cette leçon contient des instructions pour ces deux options.</span><span class="sxs-lookup"><span data-stu-id="d0427-105">This lesson provides instructions for both options.</span></span>  
  
## <a name="table-based-filter"></a><span data-ttu-id="d0427-106">Filtre de table</span><span class="sxs-lookup"><span data-stu-id="d0427-106">Table-Based Filter</span></span>  
 <span data-ttu-id="d0427-107">Vous devez effectuer les tâches suivantes pour implémenter un filtre de table.</span><span class="sxs-lookup"><span data-stu-id="d0427-107">You need to complete the following tasks to implement a table-based filter.</span></span>  
  
-   <span data-ttu-id="d0427-108">Ajoutez une expression de filtre dans le tableau matriciel du rapport enfant.</span><span class="sxs-lookup"><span data-stu-id="d0427-108">Add a filter expression to the tablix in the child report.</span></span>  
  
-   <span data-ttu-id="d0427-109">Créez une fonction qui sélectionne les données non filtrées dans la table `PurchaseOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="d0427-109">Create a function that selects unfiltered data from the `PurchaseOrderDetail` table.</span></span>  
  
-   <span data-ttu-id="d0427-110">Ajoutez un gestionnaire d'événements qui lie l'objet DataTable `PurchaseOrderDetail` au rapport enfant.</span><span class="sxs-lookup"><span data-stu-id="d0427-110">Add an event handler that binds the `PurchaseOrderDetail` DataTable to the child report.</span></span>  
  
#### <a name="to-add-a-filter-expression-to-the-tablix-in-the-child-report"></a><span data-ttu-id="d0427-111">Pour ajouter une expression de filtre dans le tableau matriciel du rapport enfant</span><span class="sxs-lookup"><span data-stu-id="d0427-111">To add a filter expression to the tablix in the child report</span></span>  
  
1.  <span data-ttu-id="d0427-112">Ouvrez le rapport enfant.</span><span class="sxs-lookup"><span data-stu-id="d0427-112">Open the child report.</span></span>  
  
2.  <span data-ttu-id="d0427-113">Sélectionnez un en-tête de colonne dans le tableau matriciel, cliquez avec le bouton droit sur la cellule grise qui se trouve au-dessus de l’en-tête de colonne, puis cliquez sur Propriétés du tableau **matriciel**.</span><span class="sxs-lookup"><span data-stu-id="d0427-113">Select a column heading in the tablix, right-click the gray cell that appears above the column heading, and then click **Tablix Properties**.</span></span>  
  
3.  <span data-ttu-id="d0427-114">Cliquez sur la page **filtres** , puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="d0427-114">Click on the **Filters** page, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="d0427-115">Dans l' **expression** classée, cliquez dans `ProductID` la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="d0427-115">In the **Expression** filed, click `ProductID` from the drop-down list.</span></span> <span data-ttu-id="d0427-116">Il s'agit de la colonne à laquelle vous appliquez le filtre.</span><span class="sxs-lookup"><span data-stu-id="d0427-116">This is the column to which you apply the filter.</span></span>  
  
5.  <span data-ttu-id="d0427-117">Cliquez sur l’opérateur EQUAL ( **=** ) dans la liste déroulante **opérateur** .</span><span class="sxs-lookup"><span data-stu-id="d0427-117">Click the equal (**=**) operator in the **Operator** drop-down list.</span></span>  
  
6.  <span data-ttu-id="d0427-118">Cliquez sur le bouton expression en regard du champ **valeur** , cliquez sur **paramètres** dans la zone **catégorie** , puis double-cliquez `productid` dans la zone **valeurs** .</span><span class="sxs-lookup"><span data-stu-id="d0427-118">Click the expression button next to the **Value** field, click **Parameters** in the **Category** area, and then double-click `productid` in the **Values** area.</span></span> <span data-ttu-id="d0427-119">Le champ **Définir l’expression pour : Valeur** doit maintenant contenir une expression semblable à **=Parameters!productid.Value**.</span><span class="sxs-lookup"><span data-stu-id="d0427-119">The **Set expression for: Value** field should now contain expression similar to **=Parameters!productid.Value**.</span></span>  
  
7.  <span data-ttu-id="d0427-120">Cliquez sur **OK,** puis de nouveau sur **OK** dans la boîte de dialogue Propriétés du tableau **matriciel** .</span><span class="sxs-lookup"><span data-stu-id="d0427-120">Click **OK,** and **OK** again in the **Tablix Properties** dialog box.</span></span>  
  
8.  <span data-ttu-id="d0427-121">Enregistrez le fichier .rdlc.</span><span class="sxs-lookup"><span data-stu-id="d0427-121">Save the .rdlc file.</span></span>  
  
#### <a name="to-create-a-function-that-selects-unfiltered-data-from-the-purchaseordedetail-table"></a><span data-ttu-id="d0427-122">Pour créer une fonction qui sélectionne les données non filtrées dans la table PurchaseOrdeDetail</span><span class="sxs-lookup"><span data-stu-id="d0427-122">To create a function that selects unfiltered data from the PurchaseOrdeDetail table</span></span>  
  
1.  <span data-ttu-id="d0427-123">Dans l'Explorateur de solutions, développez Default.aspx, puis double-cliquez sur Default.aspx.cs.</span><span class="sxs-lookup"><span data-stu-id="d0427-123">In Solution Explorer, expand Default.aspx, and then double click Default.aspx.cs.</span></span>  
  
2.  <span data-ttu-id="d0427-124">Créez une nouvelle fonction qui accepte un paramètre, `productid` , de type entier et retourne un `datatable` objet, puis effectue les opérations suivantes.</span><span class="sxs-lookup"><span data-stu-id="d0427-124">Create a new function that accepts a parameter, `productid`, of type Integer and returns a `datatable` object, and does the following.</span></span>  
  
    1.  <span data-ttu-id="d0427-125">Crée une instance du DataSet, `DataSet2` , qui a été créé à l’étape 2 de la [leçon 4 : définir une connexion de données et une table de données pour le rapport enfant](lesson-4-define-a-data-connection-and-data-table-for-child-report.md).</span><span class="sxs-lookup"><span data-stu-id="d0427-125">Creates an instance of the dataset, `DataSet2`, which was created in Step 2 of [Lesson 4: Define a Data Connection and Data Table for Child Report](lesson-4-define-a-data-connection-and-data-table-for-child-report.md).</span></span>  
  
    2.  <span data-ttu-id="d0427-126">Crée une connexion à la base de données SqlServer pour exécuter la requête définie dans la **Leçon 4 : Définir une connexion de données et une table de données pour le rapport enfant**.</span><span class="sxs-lookup"><span data-stu-id="d0427-126">Create a connection to the SqlServer database to execute the query defined in **Lesson 4: Define a Data Connection and DataTable for Child Report**.</span></span>  
  
    3.  <span data-ttu-id="d0427-127">La requête retourne des données non filtrées.</span><span class="sxs-lookup"><span data-stu-id="d0427-127">The query will return unfiltered data.</span></span>  
  
    4.  <span data-ttu-id="d0427-128">Remplissez l'instance de DataSet avec des données non filtrées en exécutant la requête.</span><span class="sxs-lookup"><span data-stu-id="d0427-128">Fill the DataSet instance with the unfiltered data by executing the query.</span></span>  
  
    5.  <span data-ttu-id="d0427-129">Retournez l'objet DataTable `PurchaseOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="d0427-129">Return the `PurchaseOrderDetail` DataTable.</span></span>  
  
         <span data-ttu-id="d0427-130">La fonction doit ressembler à celle ci-dessous. (Pour référence uniquement.</span><span class="sxs-lookup"><span data-stu-id="d0427-130">The function will look similar to the one below, (This is just for your reference.</span></span> <span data-ttu-id="d0427-131">Vous pouvez suivre le modèle de votre choix pour extraire les données nécessaires pour le rapport enfant.)</span><span class="sxs-lookup"><span data-stu-id="d0427-131">You can follow any pattern that you want, to fetch the necessary data for child report).</span></span>  
  
        ```  
        /// <summary>  
            /// Function to query PurchaseOrderDetail table, fetch the  
            /// unfiltered data and bind it with the Child report  
            /// </summary>  
            /// <returns>A dataTable of type PurchaseOrderDetail</returns>  
            private DataTable GetPurchaseOrderDetail()  
            {  
                try  
                {  
                    //Create the instance for the typed dataset, DataSet2 which will   
                    //hold the [PurchaseOrderDetail] table details.  
                    //The dataset was created as part of the tutorial in Step 4.  
                    DataSet2 ds = new DataSet2();  
  
                    //Create a SQL Connection to the AdventureWorks2008 database using Windows Authentication.  
                    using (SqlConnection sqlconn = new SqlConnection("Data Source=.;Initial Catalog=Adventureworks;Integrated Security=SSPI"))  
                    {  
                        //Building the dynamic query with the parameter ProductID.  
                        SqlDataAdapter adap = new SqlDataAdapter("SELECT PurchaseOrderID, PurchaseOrderDetailID, OrderQty, ProductID, ReceivedQty, RejectedQty, StockedQty FROM Purchasing.PurchaseOrderDetail ", sqlconn);  
                        //Executing the QUERY and fill the dataset with the PurchaseOrderDetail table data.  
                        adap.Fill(ds, "PurchaseOrderDetail");  
                    }  
  
                    //Return the PurchaseOrderDetail table for the Report Data Source.  
                    return ds.PurchaseOrderDetail;  
                }  
                catch  
                {  
                    throw;  
                }  
            }  
        ```  
  
#### <a name="to-add-an-event-handler-that-binds-the-purchaseorderdetail-datatable-to-the-child-report"></a><span data-ttu-id="d0427-132">Pour ajouter un gestionnaire d'événements qui lie l'objet DataTable PurchaseOrderDetail au rapport enfant</span><span class="sxs-lookup"><span data-stu-id="d0427-132">To add an event handler that binds the PurchaseOrderDetail DataTable to the child report</span></span>  
  
1.  <span data-ttu-id="d0427-133">Ouvrez Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="d0427-133">Open Default.aspx.</span></span>  
  
2.  <span data-ttu-id="d0427-134">Cliquez avec le bouton droit sur le contrôle ReportViewer, puis cliquez sur **Propriétés.**</span><span class="sxs-lookup"><span data-stu-id="d0427-134">Right click the ReportViewer control, and then click **Properties.**</span></span>  
  
3.  <span data-ttu-id="d0427-135">Sur la page **Propriétés** , cliquez sur l’icône **événements** .</span><span class="sxs-lookup"><span data-stu-id="d0427-135">On the **Properties** page, click the **Events** icon.</span></span>  
  
4.  <span data-ttu-id="d0427-136">Double-cliquez sur l’événement d' **extraction** .</span><span class="sxs-lookup"><span data-stu-id="d0427-136">Double click the **Drillthrough** event.</span></span>  
  
     <span data-ttu-id="d0427-137">Cette opération permet d'ajouter une section du gestionnaire d'événements dans le code, qui doit ressembler au bloc ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="d0427-137">This will add an event handler section in the code, which will look similar to the below block.</span></span>  
  
    ```  
    protected void ReportViewer1_Drillthrough(object sender, Microsoft.Reporting.WebForms.DrillthroughEventArgs e)  
    {  
    }  
    ```  
  
5.  <span data-ttu-id="d0427-138">Terminez l'exécution du gestionnaire d'événements.</span><span class="sxs-lookup"><span data-stu-id="d0427-138">Complete the event handler.</span></span> <span data-ttu-id="d0427-139">Il doit inclure les fonctionnalités suivantes.</span><span class="sxs-lookup"><span data-stu-id="d0427-139">It should include the following functionalty.</span></span>  
  
    1.  <span data-ttu-id="d0427-140">Extraire la référence d’objet de rapport enfant du paramètre *DrillthroughEventArgs* .</span><span class="sxs-lookup"><span data-stu-id="d0427-140">Fetch the child report object reference from the *DrillthroughEventArgs* parameter.</span></span>  
  
    2.  <span data-ttu-id="d0427-141">Appelez la fonction.`GetPurchaseOrderDetail`</span><span class="sxs-lookup"><span data-stu-id="d0427-141">Call the function, `GetPurchaseOrderDetail`</span></span>  
  
    3.  <span data-ttu-id="d0427-142">Liez l'objet DataTable `PurchaseOrderDetail` à la source de données correspondante du rapport.</span><span class="sxs-lookup"><span data-stu-id="d0427-142">Bind the `PurchaseOrderDetail` DataTable with the report's corresponding data source.</span></span>  
  
         <span data-ttu-id="d0427-143">Le code exécuté du gestionnaire d'événements doit ressembler à ce qui suit.</span><span class="sxs-lookup"><span data-stu-id="d0427-143">The completed event handler code will look similar to the following.</span></span>  
  
        ```  
        protected void ReportViewer1_Drillthrough(object sender, Microsoft.Reporting.WebForms.DrillthroughEventArgs e)  
            {  
                try  
                {  
                     //Get the instance of the Target report, in our case the JumpReport.rdlc.  
                    LocalReport report = (LocalReport)e.Report;  
  
                     //Binding the DataTable to the Child report dataset.  
                    //The name DataSet1 which can be located from,   
                    //Go to Design view of Child.rdlc, Click View menu -> Report Data  
                    //You'll see this name under DataSet2.  
                    report.DataSources.Add(new ReportDataSource("DataSet1", GetPurchaseOrderDetail()));  
                }  
                catch (Exception ex)  
                {  
                    Response.Write(ex.Message);  
                }  
            }  
        ```  
  
6.  <span data-ttu-id="d0427-144">Enregistrez le fichier .</span><span class="sxs-lookup"><span data-stu-id="d0427-144">Save the file.</span></span>  
  
## <a name="query-filter"></a><span data-ttu-id="d0427-145">Filtre de requête</span><span class="sxs-lookup"><span data-stu-id="d0427-145">Query Filter</span></span>  
 <span data-ttu-id="d0427-146">Vous devez effectuer les tâches suivantes pour implémenter un filtre de requête.</span><span class="sxs-lookup"><span data-stu-id="d0427-146">You need to complete the following tasks to implement a query filter.</span></span>  
  
-   <span data-ttu-id="d0427-147">Créez une fonction qui sélectionne les données filtrées dans la table `PurchaseOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="d0427-147">Create a function that selected filtered data from the `PurchaseOrderDetail` table.</span></span>  
  
-   <span data-ttu-id="d0427-148">Ajoutez un gestionnaire d'événements qui extrait les valeurs de paramètre et lie l'objet DataTable `PurchaseOrdeDetail` au rapport enfant.</span><span class="sxs-lookup"><span data-stu-id="d0427-148">Add an event handler that retrieves parameter values and binds the `PurchaseOrdeDetail` DataTable to the child report.</span></span>  
  
#### <a name="to-create-a-function-that-selects-filtered-data-from-the-purchaseorderdetail-table"></a><span data-ttu-id="d0427-149">Pour créer une fonction qui sélectionne les données filtrées dans la table PurchaseOrderDetail</span><span class="sxs-lookup"><span data-stu-id="d0427-149">To create a function that selects filtered data from the PurchaseOrderDetail table</span></span>  
  
1.  <span data-ttu-id="d0427-150">Dans l'Explorateur de solutions, développez Default.aspx, puis double-cliquez sur Default.aspx.cs.</span><span class="sxs-lookup"><span data-stu-id="d0427-150">In Solution Explorer, expand Default.aspx, and then double click Default.aspx.cs.</span></span>  
  
2.  <span data-ttu-id="d0427-151">Créez une fonction qui accepte un paramètre, `productid`, de type entier et retourne un objet `datatable`, puis procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d0427-151">Create a new function that accepts a parameter, `productid`, of type Integer and returns a `datatable` object and does the following.</span></span>  
  
    1.  <span data-ttu-id="d0427-152">Crée une instance du DataSet, `DataSet2` , qui a été créé à l’étape 2 de la [leçon 4 : définir une connexion de données et une table de données pour le rapport enfant](lesson-4-define-a-data-connection-and-data-table-for-child-report.md).</span><span class="sxs-lookup"><span data-stu-id="d0427-152">Creates an instance of the dataset, `DataSet2`, which was created in Step 2 of [Lesson 4: Define a Data Connection and Data Table for Child Report](lesson-4-define-a-data-connection-and-data-table-for-child-report.md).</span></span>  
  
    2.  <span data-ttu-id="d0427-153">Créez une connexion à la base de données SqlServer pour exécuter la requête définie dans la **Leçon 4 : Définir une connexion de données et une table de données pour le rapport enfant**.</span><span class="sxs-lookup"><span data-stu-id="d0427-153">Create a connection to the SqlServer database to execute the query defined **Lesson 4: Define a Data Connection and DataTable for Child Report**.</span></span>  
  
    3.  <span data-ttu-id="d0427-154">La requête inclut un paramètre, `productid`, pour vérifier que les données retournées sont filtrées en fonction de l'élément `ProductID` sélectionné dans le rapport parent.</span><span class="sxs-lookup"><span data-stu-id="d0427-154">The query will include a parameter, `productid`, to make sure the data returned is filtered based on the `ProductID` selected in the parent report.</span></span>  
  
    4.  <span data-ttu-id="d0427-155">Remplissez l'instance de DataSet avec les données filtrées en exécutant la requête.</span><span class="sxs-lookup"><span data-stu-id="d0427-155">Fill the DataSet instance with the filtered data by executing the query.</span></span>  
  
    5.  <span data-ttu-id="d0427-156">Retournez l'objet DataTable `PurchaseOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="d0427-156">Return the `PurchaseOrderDetail` DataTable.</span></span>  
  
         <span data-ttu-id="d0427-157">La fonction doit ressembler à celle ci-dessous. (Pour référence uniquement.</span><span class="sxs-lookup"><span data-stu-id="d0427-157">The function will look similar to the one below, (This is just for your reference.</span></span> <span data-ttu-id="d0427-158">Vous pouvez suivre le modèle de votre choix pour extraire les données nécessaires pour le rapport enfant.)</span><span class="sxs-lookup"><span data-stu-id="d0427-158">You can follow any pattern that you want, to fetch the necessary data for child report).</span></span>  
  
        ```  
        /// <summary>  
            /// Function to query PurchaseOrderDetail table and filter the  
            /// data for a specific ProductID selected in the Parent report.  
            /// </summary>  
            /// <param name="productid">Parameter passed from the Parent report to filter data.</param>  
            /// <returns>A dataTable of type PurchaseOrderDetail</returns>  
            private DataTable GetPurchaseOrderDetail(int productid)  
            {  
                try  
                {  
                    //Create the instance for the typed dataset, DataSet2 which will   
                    //hold the [PurchaseOrderDetail] table details.  
                    //The dataset was created as part of the tutorial in Step 4.  
                    DataSet2 ds = new DataSet2();  
  
                    //Create a SQL Connection to the AdventureWorks2008 database using Windows Authentication.  
                    using (SqlConnection sqlconn = new SqlConnection("Data Source=.;Initial Catalog=Adventureworks;Integrated Security=SSPI"))  
                    {  
                        //Building the dynamic query with the parameter ProductID.  
                        SqlDataAdapter adap = new SqlDataAdapter("SELECT PurchaseOrderID, PurchaseOrderDetailID, OrderQty, ProductID, ReceivedQty, RejectedQty, StockedQty FROM Purchasing.PurchaseOrderDetail where ProductID = " + productid, sqlconn);  
                        //Executing the QUERY and fill the dataset with the PurchaseOrderDetail table data.  
                        adap.Fill(ds, "PurchaseOrderDetail");  
                    }  
  
                    //Return the PurchaseOrderDetail table for the Report Data Source.  
                    return ds.PurchaseOrderDetail;  
                }  
                catch  
                {  
                    throw;  
                }  
            }  
        ```  
  
#### <a name="to-add-an-event-handler-that-retrieves-parameter-values-and-binds-the-purchaseordedetail-datatable-to-the-child-report"></a><span data-ttu-id="d0427-159">Pour ajouter un gestionnaire d'événements qui extrait les valeurs de paramètre et lie l'objet DataTable PurchaseOrderDetail au rapport enfant</span><span class="sxs-lookup"><span data-stu-id="d0427-159">To add an event handler that retrieves parameter values and binds the PurchaseOrdeDetail DataTable to the child report</span></span>  
  
1.  <span data-ttu-id="d0427-160">Ouvrez Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="d0427-160">Open Default.aspx.</span></span>  
  
2.  <span data-ttu-id="d0427-161">Cliquez avec le bouton droit sur le contrôle ReportViewer, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="d0427-161">Right-click the ReportViewer control, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="d0427-162">Dans le volet **Propriétés** , cliquez sur l’icône **événements** .</span><span class="sxs-lookup"><span data-stu-id="d0427-162">On the **Properties** pane, click the **Events** icon.</span></span>  
  
4.  <span data-ttu-id="d0427-163">Double-cliquez sur l’événement d' **extraction** .</span><span class="sxs-lookup"><span data-stu-id="d0427-163">Double click the **Drillthrough** event.</span></span>  
  
     <span data-ttu-id="d0427-164">Cette opération permet d'ajouter une section du gestionnaire d'événements dans le code, qui doit ressembler à ce qui suit.</span><span class="sxs-lookup"><span data-stu-id="d0427-164">This will add an event handler section in the code that will look similar to the following.</span></span>  
  
    ```  
    protected void ReportViewer1_Drillthrough(object sender, Microsoft.Reporting.WebForms.DrillthroughEventArgs e)  
    {  
    }  
    ```  
  
5.  <span data-ttu-id="d0427-165">Terminez l'exécution du gestionnaire d'événements.</span><span class="sxs-lookup"><span data-stu-id="d0427-165">Complete the event handler.</span></span> <span data-ttu-id="d0427-166">Il doit inclure la fonctionnalité suivante.</span><span class="sxs-lookup"><span data-stu-id="d0427-166">It should include the following functionality.</span></span>  
  
    1.  <span data-ttu-id="d0427-167">Extraire la référence d’objet de rapport enfant du paramètre *DrillthroughEventArgs* .</span><span class="sxs-lookup"><span data-stu-id="d0427-167">Fetch the Child report object reference from the *DrillthroughEventArgs* parameter.</span></span>  
  
    2.  <span data-ttu-id="d0427-168">Obtenez la liste des paramètres de rapport enfant de l'objet de rapport enfant extrait.</span><span class="sxs-lookup"><span data-stu-id="d0427-168">Get the child report parameter list from the child report object fetched.</span></span>  
  
    3.  <span data-ttu-id="d0427-169">Parcourez la collection du paramètre et récupérez la valeur du paramètre, `ProductID`, passée depuis le rapport parent.</span><span class="sxs-lookup"><span data-stu-id="d0427-169">Iterate through the parameter's collection and retrieve the value for the parameter, `ProductID`, passed from the parent report.</span></span>  
  
    4.  <span data-ttu-id="d0427-170">Appelez la fonction, `GetPurchaseOrderDetail`, puis passez la valeur pour le paramètre `ProductID`.</span><span class="sxs-lookup"><span data-stu-id="d0427-170">Call the function, `GetPurchaseOrderDetail`, and pass the value for parameter `ProductID`.</span></span>  
  
    5.  <span data-ttu-id="d0427-171">Liez le `PurchaseOrderDetail` DataTable à la source de données correspondante du rapport.</span><span class="sxs-lookup"><span data-stu-id="d0427-171">Bind the `PurchaseOrderDetail` DataTable with the Report's corresponding data source.</span></span>  
  
         <span data-ttu-id="d0427-172">Le code exécuté du gestionnaire d'événements doit ressembler à ce qui suit.</span><span class="sxs-lookup"><span data-stu-id="d0427-172">The completed event handler code will look similar to the following.</span></span>  
  
        ```  
        protected void ReportViewer1_Drillthrough(object sender, Microsoft.Reporting.WebForms.DrillthroughEventArgs e)  
            {  
                try  
                {  
                    //Variable to store the parameter value passed from the MainReport.  
                    int productid = 0;  
  
                    //Get the instance of the Target report, in our case the JumpReport.rdlc.  
                    LocalReport report = (LocalReport)e.Report;  
  
                    //Get all the parameters passed from the main report to the target report.  
                    //OriginalParametersToDrillthrough actually returns a Generic list of   
                    //type ReportParameter.  
                    IList<ReportParameter> list = report.OriginalParametersToDrillthrough;  
  
                    //Parse through each parameters to fetch the values passed along with them.  
                    foreach (ReportParameter param in list)  
                    {  
                        //Since we know the report has only one parameter and it is not a multivalued,   
                        //we can directly fetch the first value from the Values array.  
                        productid = Convert.ToInt32(param.Values[0].ToString());  
                    }  
  
                    //Binding the DataTable to the Child report dataset.  
                    //The name DataSet1 which can be located from,   
                    //Go to Design view of Child.rdlc, Click View menu -> Report Data  
                    //You'll see this name under DataSet2.  
                    report.DataSources.Add(new ReportDataSource("DataSet1", GetPurchaseOrderDetail(productid)));  
                }  
                catch (Exception ex)  
                {  
                    Response.Write(ex.Message);  
                }  
            }  
        ```  
  
6.  <span data-ttu-id="d0427-173">Enregistrez le fichier .</span><span class="sxs-lookup"><span data-stu-id="d0427-173">Save the file.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="d0427-174">Tâche suivante</span><span class="sxs-lookup"><span data-stu-id="d0427-174">Next Task</span></span>  
 <span data-ttu-id="d0427-175">Vous venez de créer un filtre de données pour la table de données que vous avez définie pour le rapport enfant.</span><span class="sxs-lookup"><span data-stu-id="d0427-175">You have successfully created a data filter for the data table that you defined for the child report.</span></span> <span data-ttu-id="d0427-176">Vous allez à présent générer et exécuter l'application de site Web.</span><span class="sxs-lookup"><span data-stu-id="d0427-176">Next, you will build and run the website application.</span></span>  
  
  
