---
title: Utilisation du contrôle WebForms ReportViewer | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- ReportViewer controls
ms.assetid: 4c200f36-4012-4108-8095-370b426ccf8d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 077dbbf0e59fc61d5a2dae5c3453e7a75542ecc4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605284"
---
# <a name="using-the-webforms-reportviewer-control"></a><span data-ttu-id="5d8a7-102">Utilisation du contrôle WebForms ReportViewer</span><span class="sxs-lookup"><span data-stu-id="5d8a7-102">Using the WebForms ReportViewer Control</span></span>
  <span data-ttu-id="5d8a7-103">Pour consulter des rapports déployés sur un serveur de rapports ou situés sur le système de fichiers local, vous pouvez utiliser le contrôle WebForms ReportViewer afin de les afficher dans une application Windows.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-103">To view reports deployed to a report server or reports that exist on the local file system, you can use the WebForms ReportViewer control to render them in a Web application.</span></span>  
  
###### <a name="to-use-the-reportviewer-control-in-a-web-application"></a><span data-ttu-id="5d8a7-104">Pour utiliser le contrôle ReportViewer dans une application Web</span><span class="sxs-lookup"><span data-stu-id="5d8a7-104">To use the ReportViewer Control in a Web application</span></span>  
  
1.  <span data-ttu-id="5d8a7-105">Créez un nouveau [!INCLUDE[msCoName](../../includes/msconame-md.md)] site Web ASP.net à l’aide [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] de ou de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5d8a7-105">Create a new [!INCLUDE[msCoName](../../includes/msconame-md.md)] ASP.NET Web Site using either [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] or [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span></span>  
  
     <span data-ttu-id="5d8a7-106">\- Ou -</span><span class="sxs-lookup"><span data-stu-id="5d8a7-106">\- Or -</span></span>  
  
     <span data-ttu-id="5d8a7-107">Ouvrez un site Web ASP.NET existant et ajoutez un nouveau Web Form.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-107">Open an exiting ASP.NET Web Site and add a new Web Form.</span></span>  
  
2.  <span data-ttu-id="5d8a7-108">Localisez le contrôle **ScriptManager** dans le groupe **Extensions AJAX** de la fenêtre **Boîte à outils**, puis faites-le glisser sur l’aire de conception du formulaire web.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-108">Locate the **ScriptManager** control in the **AJAX Extensions** group in the **Toolbox** window, and drag it to the design surface of the Web form.</span></span>  
  
     <span data-ttu-id="5d8a7-109">Si la **Boîte à outils** n’est pas visible, vous pouvez y accéder à partir du menu **Affichage** en sélectionnant **Boîte à outils**.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-109">If the **Toolbox** is not visible, you can access it from the **View** menu by selecting **Toolbox**.</span></span>  
  
3.  <span data-ttu-id="5d8a7-110">Localisez le contrôle **ReportViewer** dans la **Boîte à outils** et faites-le glisser sur l’aire de conception sous le contrôle **ScriptManager**.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-110">Locate the **ReportViewer** control in the **Toolbox** and drag it to the design surface below the **ScriptManager** control.</span></span>  
  
     <span data-ttu-id="5d8a7-111">Le contrôle **ReportViewer** nommé reportViewer1 est ajouté au formulaire.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-111">The **ReportViewer** control named reportViewer1 is added to the form.</span></span>  
  
 <span data-ttu-id="5d8a7-112">Une fois le contrôle ajouté au formulaire, la balise active **Tâches ReportViewer** s’affiche et vous invite à sélectionner un rapport.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-112">After the control is added to the form the **ReportViewer Tasks** smart tag will appear prompting you to select a report.</span></span> <span data-ttu-id="5d8a7-113">Si le rapport que vous souhaitez afficher a été déployé sur un serveur de rapports, sélectionnez l' **\<Server Report>** option dans la liste déroulante **choisir un rapport** .</span><span class="sxs-lookup"><span data-stu-id="5d8a7-113">If the report you wish to view has been deployed to a report server select the **\<Server Report>** option from the **Choose Report** drop-down list.</span></span> <span data-ttu-id="5d8a7-114">Une fois l' **\<Server Report>** option sélectionnée, deux propriétés supplémentaires s’affichent : **URL du serveur de rapports** et **chemin d’accès au rapport**.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-114">Once the **\<Server Report>** option is selected two additional properties will appear, **Report Server Url** and **Report Path**.</span></span> <span data-ttu-id="5d8a7-115">**L’URL de Report Server** correspond à l’adresse du serveur de rapports et le **Chemin d’accès au rapport** correspond au chemin complet du rapport à afficher.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-115">The **Report Server Url** is the address to the report server and the **Report Path** is the full path to the report you want to render.</span></span>  
  
 <span data-ttu-id="5d8a7-116">Si vous souhaitez afficher un rapport en mode local, sélectionnez l’option **Concevoir un nouveau rapport** afin de lancer le Concepteur de rapports, ou sélectionnez un rapport déjà inclus dans le projet existant.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-116">If you want to view a report in local mode select either the **Design a new report** option to launch the report designer or select a report that is already part of the existing project.</span></span> <span data-ttu-id="5d8a7-117">Après avoir sélectionné un rapport, veillez à entrer le nom du fichier de définition de rapport RDLC dans la propriété **ReportPath** du contrôle ReportViewer.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-117">After you have selected a report, be sure to enter the name of the report RDLC file in the **ReportPath** property of the ReportViewer control.</span></span> <span data-ttu-id="5d8a7-118">Cette propriété apparaît sous le nœud **LocalReport** dans le volet **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-118">This property appears under the **LocalReport** node in the **Properties** pane.</span></span>  
  
 <span data-ttu-id="5d8a7-119">Vous avez l'option de masquer un ou plusieurs éléments dans la barre d'outils ReportViewer lorsque le rapport est rendu.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-119">You have the option of hiding one or more of the items on the ReportViewer toolbar when the report is rendered.</span></span> <span data-ttu-id="5d8a7-120">Par exemple, vous pouvez masquer le bouton d'impression.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-120">For example, you can hide the print button.</span></span> <span data-ttu-id="5d8a7-121">Pour masquer les éléments de la barre d’outils, définissez les propriétés ReportViewer suivantes sur `False` dans le volet **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="5d8a7-121">To hide toolbar items, set the following ReportViewer properties to `False` in the **Properties** pane.</span></span>  
  
-   `ShowBackButton`  
  
-   `ShowExportControls`  
  
-   `ShowFindControls`  
  
-   `ShowPageNavigationControls`  
  
-   `ShowPrintButton`  
  
-   `ShowRefreshButton`  
  
-   `ShowZoomControl`  
  
## <a name="viewing-reports-in-remote-processing-mode"></a><span data-ttu-id="5d8a7-122">Affichage de rapports en mode de traitement à distance</span><span class="sxs-lookup"><span data-stu-id="5d8a7-122">Viewing Reports in Remote Processing Mode</span></span>  
 <span data-ttu-id="5d8a7-123">L'exemple suivant montre comment effectuer un rendu d'un rapport qui a été déployé sur un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-123">The following example demonstrates how to render a report that has been deployed to a report server.</span></span> <span data-ttu-id="5d8a7-124">Cet exemple utilise le rapport Sales Order Detail inclus avec le projet d'exemples de rapports [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d8a7-124">This example uses the Sales Order Detail report that is included with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample reports project.</span></span>  
  
 <span data-ttu-id="5d8a7-125">L'exemple utilise l'authentification Windows intégrée. Vous devez par conséquent commencer par activer l'emprunt d'identité.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-125">The example uses integrated Windows Authentication so you first must enable impersonation.</span></span> <span data-ttu-id="5d8a7-126">Pour ce faire, insérez la ligne suivante dans le `web.config` fichier :</span><span class="sxs-lookup"><span data-stu-id="5d8a7-126">To do this insert the following line into the `web.config` file:</span></span>  
  
```  
<!-- Web.config file. -->  
<identity impersonate="true"/>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="5d8a7-127">L'emprunt d'identité est désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-127">Impersonation is disabled by default.</span></span>  
  
```csharp  
protected void Page_Init(object sender, EventArgs e)  
{  
    if (!Page.IsPostBack)  
    {  
        // Set the processing mode for the ReportViewer to Remote  
        reportViewer.ProcessingMode = ProcessingMode.Remote;  
  
        ServerReport serverReport = reportViewer.ServerReport;  
  
        // Set the report server URL and report path  
        serverReport.ReportServerUrl =  
            new Uri("http://<Server Name>/reportserver");  
        serverReport.ReportPath =  
            "/AdventureWorks Sample Reports/Sales Order Detail";  
  
        // Create the sales order number report parameter  
        ReportParameter salesOrderNumber = new ReportParameter();  
        salesOrderNumber.Name = "SalesOrderNumber";  
        salesOrderNumber.Values.Add("SO43661");  
  
        // Set the report parameters for the report  
        reportViewer.ServerReport.SetParameters(  
            new ReportParameter[] { salesOrderNumber });  
    }  
}  
```  
  
```vb  
Imports Microsoft.Reporting.WebForms  
  
Partial Class _Default  
    Inherits System.Web.UI.Page  
  
    Protected Sub Page_Init(ByVal sender As Object, _  
            ByVal e As System.EventArgs) Handles Me.Init  
  
        If Not Page.IsPostBack Then  
  
            'Set the processing mode for the ReportViewer to Remote  
            reportViewer.ProcessingMode = ProcessingMode.Remote  
  
            Dim serverReport As ServerReport  
            serverReport = reportViewer.ServerReport  
  
            'Set the report server URL and report path  
            serverReport.ReportServerUrl = _  
                New Uri("http://<Server Name>/reportserver")  
            serverReport.ReportPath = _  
                "/AdventureWorks Sample Reports/Sales Order Detail"  
  
            'Create the sales order number report parameter  
            Dim salesOrderNumber As New ReportParameter()  
            salesOrderNumber.Name = "SalesOrderNumber"  
            salesOrderNumber.Values.Add("SO43661")  
  
            'Set the report parameters for the report  
            Dim parameters() As ReportParameter = {salesOrderNumber}  
            serverReport.SetParameters(parameters)  
  
        End If  
  
    End Sub  
  
End Class  
```  
  
## <a name="viewing-reports-in-local-processing-mode"></a><span data-ttu-id="5d8a7-128">Affichage de rapports en mode de traitement local</span><span class="sxs-lookup"><span data-stu-id="5d8a7-128">Viewing Reports in Local Processing Mode</span></span>  
 <span data-ttu-id="5d8a7-129">L'exemple suivant montre comment effectuer le rendu d'un rapport qui fait partie de l'application Windows et qui n'a pas été déployé sur un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-129">The following example demonstrates how to render a report that is part of the Windows application and has not been deployed to a report server.</span></span>  
  
###### <a name="to-add-the-sales-order-detail-report-to-a-web-site"></a><span data-ttu-id="5d8a7-130">Pour ajouter le rapport Sales Order Detail à un site Web</span><span class="sxs-lookup"><span data-stu-id="5d8a7-130">To add the Sales Order Detail report to a Web Site</span></span>  
  
1.  <span data-ttu-id="5d8a7-131">Ouvrez le site Web auquel le rapport sera ajouté.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-131">Open the Web Site that the report will be added to.</span></span>  
  
2.  <span data-ttu-id="5d8a7-132">Dans le menu **Site Web**, sélectionnez **Ajouter un élément existant**.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-132">From the **Website** menu, select **Add Existing Item**.</span></span>  
  
3.  <span data-ttu-id="5d8a7-133">Accédez à l'emplacement où le projet AdventureWorks Report Samples est installé.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-133">Browse to the location where the AdventureWorks Report Samples project is installed.</span></span>  
  
     <span data-ttu-id="5d8a7-134">L'emplacement par défaut est C:\Program Files\Microsoft SQL Server\100\Samples\Reporting Services\Report Samples\AdventureWorks Sample Reports.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-134">The default location is C:\Program Files\Microsoft SQL Server\100\Samples\Reporting Services\Report Samples\AdventureWorks Sample Reports.</span></span>  
  
4.  <span data-ttu-id="5d8a7-135">Sélectionnez le fichier Sales Order Detail.rdl et cliquez sur le bouton **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-135">Select the Sales Order Detail.rdl file and click the **Add** button.</span></span>  
  
     <span data-ttu-id="5d8a7-136">Le fichier Sales Order Detail.rdl doit maintenant faire partie du projet.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-136">The Sales Order Detail.rdl file should now be part of the project.</span></span>  
  
5.  <span data-ttu-id="5d8a7-137">Cliquez avec le bouton droit sur le fichier Sales Order Detail.rdl dans l’Explorateur de solutions et sélectionnez **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-137">Right-click the Sales Order Detail.rdl file in Solution Explorer and select **Rename**.</span></span> <span data-ttu-id="5d8a7-138">Renommez le rapport en **Sales Order Detail.rdlc** et appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-138">Rename the report to **Sales Order Detail.rdlc** and press ENTER.</span></span>  
  
     <span data-ttu-id="5d8a7-139">Si Explorateur de solutions n’est pas visible, vous pouvez l’ouvrir à partir du menu **affichage** en sélectionnant Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-139">If Solution Explorer is not visible, you can open it from the **View** menu by selecting Solution Explorer.</span></span>  
  
 <span data-ttu-id="5d8a7-140">L'exemple de code suivant permet de créer un dataset pour les données de commande client et d'effectuer un rendu du rapport Sales Order Detail (détail de la commande) en mode local.</span><span class="sxs-lookup"><span data-stu-id="5d8a7-140">The following code example will create a dataset for the sales order data and then render the Sales Order Detail report in local mode.</span></span>  
  
```csharp  
protected void Page_Init(object sender, EventArgs e)  
{  
    if (!Page.IsPostBack)  
    {  
        // Set the processing mode for the ReportViewer to Local  
        reportViewer.ProcessingMode = ProcessingMode.Local;  
  
        LocalReport localReport = reportViewer.LocalReport;  
  
        localReport.ReportPath = "Sales Order Detail.rdlc";  
  
        DataSet dataset = new DataSet("Sales Order Detail");  
  
        string salesOrderNumber = "SO43661";  
  
        GetSalesOrderData(salesOrderNumber, ref dataset);  
  
        ReportDataSource dsSalesOrder = new ReportDataSource();  
        dsSalesOrder.Name = "SalesOrder";  
        dsSalesOrder.Value = dataset.Tables["SalesOrder"];  
  
        localReport.DataSources.Add(dsSalesOrder);  
  
        GetSalesOrderDetailData(salesOrderNumber, ref dataset);  
  
        ReportDataSource dsSalesOrderDetail = new ReportDataSource();  
        dsSalesOrderDetail.Name = "SalesOrderDetail";  
        dsSalesOrderDetail.Value = dataset.Tables["SalesOrderDetail"];  
  
        localReport.DataSources.Add(dsSalesOrderDetail);  
  
        // Create the sales order number report parameter  
        ReportParameter rpSalesOrderNumber = new ReportParameter();  
        rpSalesOrderNumber.Name = "SalesOrderNumber";  
        rpSalesOrderNumber.Values.Add("SO43661");  
  
        // Set the report parameters for the report  
        localReport.SetParameters(  
            new ReportParameter[] { rpSalesOrderNumber });  
    }  
}  
  
private void GetSalesOrderData(string salesOrderNumber,  
                           ref DataSet dsSalesOrder)  
{  
    string sqlSalesOrder =  
        "SELECT SOH.SalesOrderNumber, S.Name AS Store, " +  
        "       SOH.OrderDate, C.FirstName AS SalesFirstName, " +  
        "       C.LastName AS SalesLastName, E.Title AS " +  
        "       SalesTitle, SOH.PurchaseOrderNumber, " +  
        "       SM.Name AS ShipMethod, BA.AddressLine1 " +  
        "       AS BillAddress1, BA.AddressLine2 AS " +  
        "       BillAddress2, BA.City AS BillCity, " +  
        "       BA.PostalCode AS BillPostalCode, BSP.Name " +  
        "       AS BillStateProvince, BCR.Name AS " +  
        "       BillCountryRegion, SA.AddressLine1 AS " +  
        "       ShipAddress1, SA.AddressLine2 AS " +  
        "       ShipAddress2, SA.City AS ShipCity, " +  
        "       SA.PostalCode AS ShipPostalCode, SSP.Name " +  
        "       AS ShipStateProvince, SCR.Name AS " +  
        "       ShipCountryRegion, CC.Phone AS CustPhone, " +  
        "       CC.FirstName AS CustFirstName, CC.LastName " +  
        "       AS CustLastName " +  
        "FROM   Person.Address SA INNER JOIN " +  
        "       Person.StateProvince SSP ON " +  
        "       SA.StateProvinceID = SSP.StateProvinceID " +  
        "       INNER JOIN Person.CountryRegion SCR ON " +  
        "       SSP.CountryRegionCode = SCR.CountryRegionCode " +  
        "       RIGHT OUTER JOIN Sales.SalesOrderHeader SOH " +  
        "       LEFT OUTER JOIN  Person.Contact CC ON " +  
        "       SOH.ContactID = CC.ContactID LEFT OUTER JOIN" +  
        "       Person.Address BA INNER JOIN " +  
        "       Person.StateProvince BSP ON " +  
        "       BA.StateProvinceID = BSP.StateProvinceID " +  
        "       INNER JOIN Person.CountryRegion BCR ON " +  
        "       BSP.CountryRegionCode = " +  
        "       BCR.CountryRegionCode ON SOH.BillToAddressID " +  
        "       = BA.AddressID ON  SA.AddressID = " +  
        "       SOH.ShipToAddressID LEFT OUTER JOIN " +  
        "       Person.Contact C RIGHT OUTER JOIN " +  
        "       HumanResources.Employee E ON C.ContactID = " +  
        "       E.ContactID ON SOH.SalesPersonID = " +  
        "       E.EmployeeID LEFT OUTER JOIN " +  
        "       Purchasing.ShipMethod SM ON SOH.ShipMethodID " +  
        "       = SM.ShipMethodID LEFT OUTER JOIN Sales.Store" +  
        "        S ON SOH.CustomerID = S.CustomerID " +  
        "WHERE  (SOH.SalesOrderNumber = @SalesOrderNumber)";  
  
    SqlConnection connection = new  
        SqlConnection("Data Source=(local); " +  
                      "Initial Catalog=AdventureWorks; " +  
                      "Integrated Security=SSPI");  
  
    SqlCommand command =  
        new SqlCommand(sqlSalesOrder, connection);  
  
    command.Parameters.Add(  
        new SqlParameter("SalesOrderNumber",  
        salesOrderNumber));  
  
    SqlDataAdapter salesOrderAdapter = new  
        SqlDataAdapter(command);  
  
    salesOrderAdapter.Fill(dsSalesOrder, "SalesOrder");  
}  
  
private void GetSalesOrderDetailData(string salesOrderNumber,  
                       ref DataSet dsSalesOrder)  
{  
    string sqlSalesOrderDetail =  
        "SELECT  SOD.SalesOrderDetailID, SOD.OrderQty, " +  
        "        SOD.UnitPrice, CASE WHEN " +  
        "        SOD.UnitPriceDiscount IS NULL THEN 0 " +  
        "        ELSE SOD.UnitPriceDiscount END AS " +  
        "        UnitPriceDiscount, SOD.LineTotal, " +  
        "        SOD.CarrierTrackingNumber, " +  
        "        SOD.SalesOrderID, P.Name, P.ProductNumber " +  
        "FROM    Sales.SalesOrderDetail SOD INNER JOIN " +  
        "        Production.Product P ON SOD.ProductID = " +  
        "        P.ProductID INNER JOIN " +  
        "        Sales.SalesOrderHeader SOH ON " +  
        "        SOD.SalesOrderID = SOH.SalesOrderID " +  
        "WHERE   (SOH.SalesOrderNumber = @SalesOrderNumber) " +  
        "ORDER BY SOD.SalesOrderDetailID";  
  
    using (SqlConnection connection = new  
        SqlConnection("Data Source=(local); " +  
                      "Initial Catalog=AdventureWorks; " +  
                      "Integrated Security=SSPI"))  
    {  
  
        SqlCommand command =  
            new SqlCommand(sqlSalesOrderDetail, connection);  
  
        command.Parameters.Add(  
            new SqlParameter("SalesOrderNumber",  
            salesOrderNumber));  
  
        SqlDataAdapter salesOrderDetailAdapter = new  
            SqlDataAdapter(command);  
  
        salesOrderDetailAdapter.Fill(dsSalesOrder,  
            "SalesOrderDetail");  
    }  
}  
```  
  
```vb  
Imports System.Data  
Imports System.Data.SqlClient  
Imports Microsoft.Reporting.WebForms  
  
Partial Class _Default  
    Inherits System.Web.UI.Page  
  
    Protected Sub Page_Init(ByVal sender As Object, _  
                ByVal e As System.EventArgs) Handles Me.Init  
  
        If Not Page.IsPostBack Then  
  
            'Set the processing mode for the ReportViewer to Local  
            reportViewer.ProcessingMode = ProcessingMode.Local  
  
            Dim localReport As LocalReport  
            localReport = reportViewer.LocalReport  
  
            localReport.ReportPath = "Sales Order Detail.rdlc"  
  
            Dim dataset As New DataSet("Sales Order Detail")  
  
            Dim salesOrderNumber As String = "SO43661"  
  
            'Get the sales order data  
            GetSalesOrderData(salesOrderNumber, dataset)  
  
            'Create a report data source for the sales order data  
            Dim dsSalesOrder As New ReportDataSource()  
            dsSalesOrder.Name = "SalesOrder"  
            dsSalesOrder.Value = dataset.Tables("SalesOrder")  
  
            localReport.DataSources.Add(dsSalesOrder)  
  
            'Get the sales order detail data  
            GetSalesOrderDetailData(salesOrderNumber, dataset)  
  
            'Create a report data source for the sales   
            'order detail data  
            Dim dsSalesOrderDetail As New ReportDataSource()  
            dsSalesOrderDetail.Name = "SalesOrderDetail"  
            dsSalesOrderDetail.Value = _  
                dataset.Tables("SalesOrderDetail")  
  
            localReport.DataSources.Add(dsSalesOrderDetail)  
  
            'Create a report parameter for the sales order number   
            Dim rpSalesOrderNumber As New ReportParameter()  
            rpSalesOrderNumber.Name = "SalesOrderNumber"  
            rpSalesOrderNumber.Values.Add("SO43661")  
  
            'Set the report parameters for the report  
            Dim parameters() As ReportParameter = {rpSalesOrderNumber}  
            localReport.SetParameters(parameters)  
  
        End If  
  
    End Sub  
  
    Private Sub GetSalesOrderData(ByVal salesOrderNumber As String, _  
                               ByRef dsSalesOrder As DataSet)  
  
        Dim sqlSalesOrder As String = _  
            "SELECT SOH.SalesOrderNumber, S.Name AS Store, " & _  
            "       SOH.OrderDate, C.FirstName AS SalesFirstName, " & _  
            "       C.LastName AS SalesLastName, E.Title AS " & _  
            "       SalesTitle, SOH.PurchaseOrderNumber, " & _  
            "       SM.Name AS ShipMethod, BA.AddressLine1 " & _  
            "       AS BillAddress1, BA.AddressLine2 AS " & _  
            "       BillAddress2, BA.City AS BillCity, " & _  
            "       BA.PostalCode AS BillPostalCode, BSP.Name " & _  
            "       AS BillStateProvince, BCR.Name AS " & _  
            "       BillCountryRegion, SA.AddressLine1 AS " & _  
            "       ShipAddress1, SA.AddressLine2 AS " & _  
            "       ShipAddress2, SA.City AS ShipCity, " & _  
            "       SA.PostalCode AS ShipPostalCode, SSP.Name " & _  
            "       AS ShipStateProvince, SCR.Name AS " & _  
            "       ShipCountryRegion, CC.Phone AS CustPhone, " & _  
            "       CC.FirstName AS CustFirstName, CC.LastName " & _  
            "       AS CustLastName " & _  
            "FROM   Person.Address SA INNER JOIN " & _  
            "       Person.StateProvince SSP ON " & _  
            "       SA.StateProvinceID = SSP.StateProvinceID " & _  
            "       INNER JOIN Person.CountryRegion SCR ON " & _  
            "       SSP.CountryRegionCode = SCR.CountryRegionCode " & _  
            "       RIGHT OUTER JOIN Sales.SalesOrderHeader SOH " & _  
            "       LEFT OUTER JOIN  Person.Contact CC ON " & _  
            "       SOH.ContactID = CC.ContactID LEFT OUTER JOIN" & _  
            "       Person.Address BA INNER JOIN " & _  
            "       Person.StateProvince BSP ON " & _  
            "       BA.StateProvinceID = BSP.StateProvinceID " & _  
            "       INNER JOIN Person.CountryRegion BCR ON " & _  
            "       BSP.CountryRegionCode = " & _  
            "       BCR.CountryRegionCode ON SOH.BillToAddressID " & _  
            "       = BA.AddressID ON  SA.AddressID = " & _  
            "       SOH.ShipToAddressID LEFT OUTER JOIN " & _  
            "       Person.Contact C RIGHT OUTER JOIN " & _  
            "       HumanResources.Employee E ON C.ContactID = " & _  
            "       E.ContactID ON SOH.SalesPersonID = " & _  
            "       E.EmployeeID LEFT OUTER JOIN " & _  
            "       Purchasing.ShipMethod SM ON SOH.ShipMethodID " & _  
            "       = SM.ShipMethodID LEFT OUTER JOIN Sales.Store" & _  
            "        S ON SOH.CustomerID = S.CustomerID " & _  
            "WHERE  (SOH.SalesOrderNumber = @SalesOrderNumber)"  
  
        Using connection As New SqlConnection( _  
                      "Data Source=(local); " & _  
                      "Initial Catalog=AdventureWorks; " & _  
                      "Integrated Security=SSPI")  
  
            Dim command As New SqlCommand(sqlSalesOrder, connection)  
  
            Dim parameter As New SqlParameter("SalesOrderNumber", _  
                salesOrderNumber)  
            command.Parameters.Add(parameter)  
  
            Dim salesOrderAdapter As New SqlDataAdapter(command)  
  
            salesOrderAdapter.Fill(dsSalesOrder, "SalesOrder")  
  
        End Using  
  
    End Sub  
  
    Private Sub GetSalesOrderDetailData( _  
                           ByVal salesOrderNumber As String, _  
                           ByRef dsSalesOrder As DataSet)  
  
        Dim sqlSalesOrderDetail As String = _  
            "SELECT  SOD.SalesOrderDetailID, SOD.OrderQty, " & _  
            "        SOD.UnitPrice, CASE WHEN " & _  
            "        SOD.UnitPriceDiscount IS NULL THEN 0 " & _  
            "        ELSE SOD.UnitPriceDiscount END AS " & _  
            "        UnitPriceDiscount, SOD.LineTotal, " & _  
            "        SOD.CarrierTrackingNumber, " & _  
            "        SOD.SalesOrderID, P.Name, P.ProductNumber " & _  
            "FROM    Sales.SalesOrderDetail SOD INNER JOIN " & _  
            "        Production.Product P ON SOD.ProductID = " & _  
            "        P.ProductID INNER JOIN " & _  
            "        Sales.SalesOrderHeader SOH ON " & _  
            "        SOD.SalesOrderID = SOH.SalesOrderID " & _  
            "WHERE   (SOH.SalesOrderNumber = @SalesOrderNumber) " & _  
            "ORDER BY SOD.SalesOrderDetailID"  
  
        Using connection As New SqlConnection( _  
                      "Data Source=(local); " & _  
                      "Initial Catalog=AdventureWorks; " & _  
                      "Integrated Security=SSPI")  
  
            Dim command As New SqlCommand(sqlSalesOrderDetail, _  
                                          connection)  
  
            Dim parameter As New SqlParameter("SalesOrderNumber", _  
                salesOrderNumber)  
            command.Parameters.Add(parameter)  
  
            Dim salesOrderDetailAdapter As New SqlDataAdapter(command)  
  
            salesOrderDetailAdapter.Fill(dsSalesOrder, _  
                "SalesOrderDetail")  
  
        End Using  
  
    End Sub  
  
End Class  
```  
  
## <a name="see-also"></a><span data-ttu-id="5d8a7-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5d8a7-141">See Also</span></span>  
 [<span data-ttu-id="5d8a7-142">Intégration de Reporting Services à l'aide des contrôles ReportViewer</span><span class="sxs-lookup"><span data-stu-id="5d8a7-142">Integrating Reporting Services Using the ReportViewer Controls</span></span>](integrating-reporting-services-using-reportviewer-controls.md)  
  
  
