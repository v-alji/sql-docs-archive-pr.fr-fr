---
title: Utiliser des résultats FOR XML dans le code de l’application | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, application code usage
- XML [SQL Server], FOR XML clause
- ASP.NET [SQL Server]
- .NET Framework [SQL Server], FOR XML data
- ADO [SQL Server]
- XML data islands [SQL Server]
- data islands [SQL Server]
ms.assetid: 41ae67bd-ece9-49ea-8062-c8d658ab4154
author: rothja
ms.author: jroth
ms.openlocfilehash: 3cabe7e65cb53a28a370615ed84e38ba2b8db44c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613340"
---
# <a name="use-for-xml-results-in-application-code"></a><span data-ttu-id="f7f52-102">Utiliser des résultats FOR XML dans le code de l'application</span><span class="sxs-lookup"><span data-stu-id="f7f52-102">Use FOR XML Results in Application Code</span></span>
  <span data-ttu-id="f7f52-103">En utilisant des clauses FOR XML avec des requêtes SQL, vous pouvez récupérer et même convertir les résultats de la requête en données XML.</span><span class="sxs-lookup"><span data-stu-id="f7f52-103">By using FOR XML clauses with SQL queries, you can retrieve and even cast query results as XML data.</span></span> <span data-ttu-id="f7f52-104">Dès lors que les résultats d'une requête FOR XML peuvent être utilisés dans le code de l'application XML, vous pouvez notamment effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f7f52-104">This functionality allows you to do the following when FOR XML query results can be used in XML application code:</span></span>  
  
-   <span data-ttu-id="f7f52-105">Interroger des tables SQL pour des instances de valeurs de [Données XML &#40;SQL Server&#41;](xml-data-sql-server.md)</span><span class="sxs-lookup"><span data-stu-id="f7f52-105">Query SQL tables for instances of [XML Data &#40;SQL Server&#41;](xml-data-sql-server.md) values</span></span>  
  
-   <span data-ttu-id="f7f52-106">Appliquer la [TYPE Directive in FOR XML Queries](type-directive-in-for-xml-queries.md) pour renvoyer les résultats des requêtes contenant des données de type texte ou image au format XML</span><span class="sxs-lookup"><span data-stu-id="f7f52-106">Apply the [TYPE Directive in FOR XML Queries](type-directive-in-for-xml-queries.md) to return the result of queries that contain text or image typed data as XML</span></span>  
  
 <span data-ttu-id="f7f52-107">Cette rubrique donne des exemples expliquant ces approches.</span><span class="sxs-lookup"><span data-stu-id="f7f52-107">This topic provides examples that demonstrate these approaches.</span></span>  
  
## <a name="retrieving-for-xml-data-with-ado-and-xml-data-islands"></a><span data-ttu-id="f7f52-108">Récupération des données FOR XML avec des îlots de données ADO et XML</span><span class="sxs-lookup"><span data-stu-id="f7f52-108">Retrieving FOR XML Data with ADO and XML Data Islands</span></span>  
 <span data-ttu-id="f7f52-109">L'objet ADO `Stream` ainsi que d'autres objets prenant en charge l'interface COM `IStream`, tels que les objets Active Server Pages (ASP) `Request` et `Response`, peuvent servir à contenir les résultats en cas d'utilisation de requêtes FOR XML.</span><span class="sxs-lookup"><span data-stu-id="f7f52-109">The ADO `Stream` object or other objects that support the COM `IStream` interface, such as the Active Server Pages (ASP) `Request` and `Response` objects, can be used to contain the results when you are working with FOR XML queries.</span></span>  
  
 <span data-ttu-id="f7f52-110">Le code ASP suivant, par exemple, montre les résultats d'une requête lancée sur la colonne de type `xml` Demographics de la table Sales.Store de la base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="f7f52-110">For example, the following ASP code shows the results of querying an `xml` data type column, Demographics, in the Sales.Store table of the AdventureWorks sample database.</span></span> <span data-ttu-id="f7f52-111">La requête recherche plus particulièrement la valeur d'instance de cette colonne pour la ligne où CustomerID est égal à 3.</span><span class="sxs-lookup"><span data-stu-id="f7f52-111">Specifically, the query looks for the instance value of this column for the row where the CustomerID is equal to 3.</span></span>  
  
```  
<!-- BeginRecordAndStreamVBS -->  
<%@ LANGUAGE = VBScript %>  
<!-- %  Option Explicit      % -->  
<!-- 'Request.ServerVariables("SERVER_NAME") & ";" & _ -->  
<HTML>  
<HEAD>  
<META NAME="GENERATOR" Content="Microsoft Developer Studio"/>  
<META HTTP-EQUIV="Content-Type" content="text/html"; charset="iso-8859-1">  
<TITLE>FOR XML Query Example</TITLE>  
<STYLE>  
   BODY  
   {  
      FONT-FAMILY: Tahoma;  
      FONT-SIZE: 8pt;  
      OVERFLOW: auto  
   }  
   H3  
   {  
      FONT-FAMILY: Tahoma;  
      FONT-SIZE: 8pt;  
      OVERFLOW: auto  
   }  
</STYLE>  
  
<!-- #include file="adovbs.inc" -->  
<%  
   Response.Write "<H3>Server-side processing</H3>"  
   Response.Write "Page Generated @ " & Now() & "<BR/>"  
   Dim adoConn  
   Set adoConn = Server.CreateObject("ADODB.Connection")  
   Dim sConn  
   sConn = "Provider=SQLOLEDB;Data Source=(local);" & _  
            "Initial Catalog=AdventureWorks;Integrated Security=SSPI;"  
   Response.write "Connect String = " & sConn & "<BR/>"  
   adoConn.ConnectionString = sConn  
   adoConn.CursorLocation = adUseClient  
   adoConn.Open  
   Response.write "ADO Version = " & adoConn.Version & "<BR/>"  
   Response.write "adoConn.State = " & adoConn.State & "<BR/>"  
   Dim adoCmd  
   Set adoCmd = Server.CreateObject("ADODB.Command")  
   Set adoCmd.ActiveConnection = adoConn  
   Dim sQuery  
   sQuery = "<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql'><sql:query>SELECT Demographics from Sales.Store WHERE CustomerID = 3 FOR XML AUTO</sql:query></ROOT>"  
   Response.write "Query String = " & sQuery & "<BR/>"  
   Dim adoStreamQuery  
   Set adoStreamQuery = Server.CreateObject("ADODB.Stream")  
   adoStreamQuery.Open  
   adoStreamQuery.WriteText sQuery, adWriteChar  
   adoStreamQuery.Position = 0  
   adoCmd.CommandStream = adoStreamQuery  
   adoCmd.Dialect = "{5D531CB2-E6Ed-11D2-B252-00C04F681B71}"  
   Response.write "Pushing XML to client for processing "  & "<BR/>"  
   adoCmd.Properties("Output Stream") = Response  
   Response.write "<XML ID='MyDataIsle'>"  
   adoCmd.Execute , , 1024  
   Response.write "</XML>"  
%>  
<SCRIPT language="VBScript" For="window" Event="onload">  
   Dim xmlDoc  
   Set xmlDoc = MyDataIsle.XMLDocument  
   Dim root  
   Set root = xmlDoc.documentElement.childNodes.Item(0).childNodes.Item(0).childNodes.Item(0)  
   For each child in root.childNodes  
      dim OutputXML  
      OutputXML = document.all("log").innerHTML  
      document.all("log").innerHTML = OutputXML & "<LI><B>" & child.nodeName &  ":</B>  " & child.Text  & "</LI>"  
   Next  
   MsgBox xmlDoc.xml  
</SCRIPT>  
</HEAD>  
<BODY>  
   <H3>Client-side processing of XML Document MyDataIsle</H3>  
   <UL id=log>  
   </UL>  
</BODY>  
</HTML>  
<!-- EndRecordAndStreamVBS -->  
```  
  
 <span data-ttu-id="f7f52-112">Cet exemple de page ASP contient le code VBScript côté serveur qui utilise ADO pour exécuter la requête FOR XML et renvoyer les résultats XML dans l'îlot de données XML MyDataIsle.</span><span class="sxs-lookup"><span data-stu-id="f7f52-112">This example ASP page contains server-side VBScript that uses ADO to execute the FOR XML query and return the XML results in an XML data island, MyDataIsle.</span></span> <span data-ttu-id="f7f52-113">Cet îlot de données XML est ensuite renvoyé dans le navigateur en vue d'un traitement supplémentaire côté client.</span><span class="sxs-lookup"><span data-stu-id="f7f52-113">This XML data island is then returned in the browser for additional client-side processing.</span></span> <span data-ttu-id="f7f52-114">Côté client, le code VBScript supplémentaire sert ensuite à traiter le contenu de l'îlot de données XML.</span><span class="sxs-lookup"><span data-stu-id="f7f52-114">Additional client-side VBScript code is then used to process the contents of the XML data island.</span></span> <span data-ttu-id="f7f52-115">Ce processus a lieu avant l'affichage du contenu sous forme DHTML et avant l'ouverture d'une boîte de message afin de montrer le contenu prétraité de l'îlot de données XML.</span><span class="sxs-lookup"><span data-stu-id="f7f52-115">This process is performed before displaying the contents as part of the resultant DHTML and opening a message box to show the preprocessed contents of the XML data island.</span></span>  
  
#### <a name="to-test-this-example"></a><span data-ttu-id="f7f52-116">Pour tester cet exemple</span><span class="sxs-lookup"><span data-stu-id="f7f52-116">To test this example</span></span>  
  
1.  <span data-ttu-id="f7f52-117">Vérifiez que les services Internet (IIS) sont installés et que l'exemple de base de données AdventureWorks a bien été installé pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f7f52-117">Verify that IIS is installed and that the AdventureWorks sample database for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been installed.</span></span>  
  
     <span data-ttu-id="f7f52-118">Cet exemple requiert l'installation de Internet Information Services (IIS) version 5.0 ou ultérieure et l'activation de la prise en charge ASP.</span><span class="sxs-lookup"><span data-stu-id="f7f52-118">This example requires that Internet Information Services (IIS) version 5.0, or later versions, are installed with ASP support enabled.</span></span> <span data-ttu-id="f7f52-119">De plus, l'exemple de base de données AdventureWorks doit être installé.</span><span class="sxs-lookup"><span data-stu-id="f7f52-119">Also, the AdventureWorks sample database has to be installed.</span></span>  
  
2.  <span data-ttu-id="f7f52-120">Copiez l'exemple de code précédemment fourni et collez-le dans l'éditeur XML ou de texte que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="f7f52-120">Copy the code example that was previously provided and paste it into the XML or text editor that you use.</span></span> <span data-ttu-id="f7f52-121">Enregistrez le fichier sous RetrieveResults.asp dans le répertoire racine utilisé pour IIS.</span><span class="sxs-lookup"><span data-stu-id="f7f52-121">Save the file as RetrieveResults.asp in the root directory that is used for IIS.</span></span> <span data-ttu-id="f7f52-122">Il s'agit généralement de C:Inetpub\wwwroot.</span><span class="sxs-lookup"><span data-stu-id="f7f52-122">Typically, this is C:Inetpub\wwwroot.</span></span>  
  
3.  <span data-ttu-id="f7f52-123">Ouvrez la page ASP dans une fenêtre du navigateur en utilisant l'URL qui suit.</span><span class="sxs-lookup"><span data-stu-id="f7f52-123">Open the ASP page in a browser window by using the following URL.</span></span> <span data-ttu-id="f7f52-124">Premièrement, remplacez « MyServer » par « localhost » ou par le nom réel du serveur sur lequel résident [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et les services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="f7f52-124">First, replace 'MyServer' with either "localhost" or the actual name of the server where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and IIS are installed.</span></span>  
  
    ```  
    http://MyServer/RetrieveResults.asp  
    ```  
  
 <span data-ttu-id="f7f52-125">La page HTML générée qui en résulte et qui apparaît ressemblera à l'exemple de sortie suivant :</span><span class="sxs-lookup"><span data-stu-id="f7f52-125">The generated HTML page results that appear will be similar to the following sample output:</span></span>  
  
##### <a name="server-side-processing"></a><span data-ttu-id="f7f52-126">Traitement côté serveur</span><span class="sxs-lookup"><span data-stu-id="f7f52-126">Server-side processing</span></span>  
 <span data-ttu-id="f7f52-127">Page Generated \@ 3/11/2006 3:36:02 PM</span><span class="sxs-lookup"><span data-stu-id="f7f52-127">Page Generated \@ 3/11/2006 3:36:02 PM</span></span>  
  
 <span data-ttu-id="f7f52-128">Connect String = Provider=SQLOLEDB;Data Source=MyServer;Initial Catalog=AdventureWorks;Integrated Security=SSPI;</span><span class="sxs-lookup"><span data-stu-id="f7f52-128">Connect String = Provider=SQLOLEDB;Data Source=MyServer;Initial Catalog=AdventureWorks;Integrated Security=SSPI;</span></span>  
  
 <span data-ttu-id="f7f52-129">ADO Version = 2.8</span><span class="sxs-lookup"><span data-stu-id="f7f52-129">ADO Version = 2.8</span></span>  
  
 <span data-ttu-id="f7f52-130">adoConn.State = 1</span><span class="sxs-lookup"><span data-stu-id="f7f52-130">adoConn.State = 1</span></span>  
  
 <span data-ttu-id="f7f52-131">Query String = SELECT Demographics from Sales.Store WHERE CustomerID = 3 FOR XML AUTO</span><span class="sxs-lookup"><span data-stu-id="f7f52-131">Query String = SELECT Demographics from Sales.Store WHERE CustomerID = 3 FOR XML AUTO</span></span>  
  
 <span data-ttu-id="f7f52-132">Envoi du code XML au client en vue du traitement</span><span class="sxs-lookup"><span data-stu-id="f7f52-132">Pushing XML to client for processing</span></span>  
  
##### <a name="client-side-processing-of-xml-document-mydataisle"></a><span data-ttu-id="f7f52-133">Traitement côté client du document XML MyDataIsle</span><span class="sxs-lookup"><span data-stu-id="f7f52-133">Client-side processing of XML Document MyDataIsle</span></span>  
  
-   <span data-ttu-id="f7f52-134">**AnnualSales:** 1500000</span><span class="sxs-lookup"><span data-stu-id="f7f52-134">**AnnualSales:** 1500000</span></span>  
  
-   <span data-ttu-id="f7f52-135">**AnnualRevenue:** 150000</span><span class="sxs-lookup"><span data-stu-id="f7f52-135">**AnnualRevenue:** 150000</span></span>  
  
-   <span data-ttu-id="f7f52-136">**BankName:** Primary International</span><span class="sxs-lookup"><span data-stu-id="f7f52-136">**BankName:** Primary International</span></span>  
  
-   <span data-ttu-id="f7f52-137">**BusinessType:** Système d''exploitation</span><span class="sxs-lookup"><span data-stu-id="f7f52-137">**BusinessType:** OS</span></span>  
  
-   <span data-ttu-id="f7f52-138">**YearOpened:** 1974</span><span class="sxs-lookup"><span data-stu-id="f7f52-138">**YearOpened:** 1974</span></span>  
  
-   <span data-ttu-id="f7f52-139">**Specialty:** Route</span><span class="sxs-lookup"><span data-stu-id="f7f52-139">**Specialty:** Road</span></span>  
  
-   <span data-ttu-id="f7f52-140">**SquareFeet:** 38000</span><span class="sxs-lookup"><span data-stu-id="f7f52-140">**SquareFeet:** 38000</span></span>  
  
-   <span data-ttu-id="f7f52-141">**Brands:** 3</span><span class="sxs-lookup"><span data-stu-id="f7f52-141">**Brands:** 3</span></span>  
  
-   <span data-ttu-id="f7f52-142">**Internet:** DSL</span><span class="sxs-lookup"><span data-stu-id="f7f52-142">**Internet:** DSL</span></span>  
  
-   <span data-ttu-id="f7f52-143">**NumberEmployees:** 40</span><span class="sxs-lookup"><span data-stu-id="f7f52-143">**NumberEmployees:** 40</span></span>  
  
 <span data-ttu-id="f7f52-144">La boîte de message VBScript affichera ensuite le contenu original et non filtré de l'îlot de données XML qui a été renvoyé par les résultats de la requête FOR XML.</span><span class="sxs-lookup"><span data-stu-id="f7f52-144">The VBScript message box will then show the following original, unfiltered XML data island contents that were returned by the FOR XML query results.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Sales.Store>  
    <Demographics>  
      <StoreSurvey xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/StoreSurvey">  
        <AnnualSales>1500000</AnnualSales>  
        <AnnualRevenue>150000</AnnualRevenue>  
        <BankName>Primary International</BankName>  
        <BusinessType>OS</BusinessType>  
        <YearOpened>1974</YearOpened>  
        <Specialty>Road</Specialty>  
        <SquareFeet>38000</SquareFeet>  
        <Brands>3</Brands>  
        <Internet>DSL</Internet>  
        <NumberEmployees>40</NumberEmployees>  
      </StoreSurvey>  
    </Demographics>  
  </Sales.Store>  
</ROOT>  
```  
  
## <a name="retrieving-for-xml-data-with-aspnet-and-the-net-framework"></a><span data-ttu-id="f7f52-145">Récupération des données FOR XML avec ASP.NET et .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f7f52-145">Retrieving FOR XML Data with ASP.NET and the .NET Framework</span></span>  
 <span data-ttu-id="f7f52-146">Comme dans l'exemple précédent, le code ASP suivant montre les résultats d'une requête lancée sur une colonne de type `xml`, Demographics, de la table Sales.Store de la base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="f7f52-146">As in the previous example, the following ASP.NET code shows the results of querying an `xml` data type column, Demographics, in the Sales.Store table of the AdventureWorks sample database.</span></span> <span data-ttu-id="f7f52-147">Comme dans l'exemple précédent, la requête recherche plus particulièrement la valeur d'instance de cette colonne pour la ligne où CustomerID est égal à 3.</span><span class="sxs-lookup"><span data-stu-id="f7f52-147">As in the previous example, the query looks for the instance value of this column for the row where the CustomerID is equal to 3.</span></span>  
  
 <span data-ttu-id="f7f52-148">Dans cet exemple, les API gérées Microsoft .NET Framework sont chargées de renvoyer et de rendre les résultats de la requête FOR XML :</span><span class="sxs-lookup"><span data-stu-id="f7f52-148">In this example, the following Microsoft .NET Framework managed APIs are used to accomplish the return and rendering of the FOR XML query results:</span></span>  
  
1.  <span data-ttu-id="f7f52-149">`SqlConnection` est utilisé pour ouvrir une connexion à SQL Server en fonction du contenu d'une variable de chaîne de connexion spécifiée strConn.</span><span class="sxs-lookup"><span data-stu-id="f7f52-149">`SqlConnection` is used to open a connection to SQL Server, based on the contents of a specified connection string variable, strConn.</span></span>  
  
2.  <span data-ttu-id="f7f52-150">`SqlDataAdapter` est ensuite utilisé en tant qu'adaptateur de données et utilise la connexion SQL et une chaîne de requête SQL spécifiée pour exécuter la requête FOR XML.</span><span class="sxs-lookup"><span data-stu-id="f7f52-150">`SqlDataAdapter` is then used as the data adapter and it uses the SQL connection and a specified SQL query string to execute the FOR XML query.</span></span>  
  
3.  <span data-ttu-id="f7f52-151">Une fois la requête exécutée, la méthode `SqlDataAdapter.Fill` est appelée et reçoit une instance d'un `DataSet,` MyDataSet, afin de remplir le dataset avec le résultat de la requête FOR XML.</span><span class="sxs-lookup"><span data-stu-id="f7f52-151">After the query has executed, the `SqlDataAdapter.Fill` method is then called and passed an instance of a `DataSet,` MyDataSet, in order to fill the data set with the output of the FOR XML query.</span></span>  
  
4.  <span data-ttu-id="f7f52-152">La méthode `DataSet.GetXml` est alors appelée pour renvoyer les résultats de la requête sous forme de chaîne à afficher dans la page HTML générée par le serveur.</span><span class="sxs-lookup"><span data-stu-id="f7f52-152">The `DataSet.GetXml` method is then called to return the query results as a string that can be displayed in the server-generated HTML page.</span></span>  
  
    ```  
    <%@ Page Language="VB" %>  
    <HTML>  
    <HEAD>  
    <TITLE>FOR XML Query Example</TITLE>  
    <STYLE>  
       BODY  
       {  
          FONT-FAMILY: Tahoma;  
          FONT-SIZE: 8pt;  
          OVERFLOW: auto  
       }  
       H3  
       {  
          FONT-FAMILY: Tahoma;  
          FONT-SIZE: 8pt;  
          OVERFLOW: auto  
       }  
    </STYLE>  
    </HEAD>  
    <BODY>  
    <%  
    Dim s as String  
    s = "<H3>Server-side processing</H3>" & _  
        "Page Generated @ " & Now() & "<BR/>"  
  
    Dim SQL As String   
    SQL = "SELECT Demographics from Sales.Store WHERE CustomerID = 3 FOR XML AUTO"  
  
    Dim strConn As String   
    strConn = "Server=(local);Database=AdventureWorks;Integrated Security=SSPI;"  
  
    Dim MySqlConn As New System.Data.SqlClient.SqlConnection(strConn)  
    Dim MySqlAdapter As New System.Data.SqlClient.SqlDataAdapter(SQL,MySqlConn)  
    Dim MyDataSet As New System.Data.DataSet  
  
    MySqlConn.Open()  
    s = s & "<P>SqlConnection opened.</P>"   
  
    MySqlAdapter.Fill(MyDataSet)  
    s = s & "<P>" & MyDataSet.GetXml  & "</P>"  
  
    MySqlConn.Close()  
    s = s & "<P>SqlConnection closed.</P>"   
  
    Message.InnerHtml=s  
    %>  
    <SPAN id="Message" runat=server />  
    </BODY>  
    </HTML>  
    ```  
  
#### <a name="to-test-this-example"></a><span data-ttu-id="f7f52-153">Pour tester cet exemple</span><span class="sxs-lookup"><span data-stu-id="f7f52-153">To test this example</span></span>  
  
1.  <span data-ttu-id="f7f52-154">Vérifiez que les services Internet (IIS) sont installés et que l'exemple de base de données AdventureWorks a bien été installé pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f7f52-154">Verify that IIS is installed and that the AdventureWorks sample database for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been installed.</span></span>  
  
     <span data-ttu-id="f7f52-155">Cet exemple requiert l'installation de Internet Information Services (IIS) version 5.0 ou ultérieure et l'activation de la prise en charge ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="f7f52-155">This example requires that Internet Information Services (IIS) version 5.0, or later versions, are installed with ASP.NET support enabled.</span></span> <span data-ttu-id="f7f52-156">De plus, l'exemple de base de données AdventureWorks doit être installé.</span><span class="sxs-lookup"><span data-stu-id="f7f52-156">Also, the AdventureWorks sample database has to be installed.</span></span>  
  
2.  <span data-ttu-id="f7f52-157">Copiez le code précédemment fourni et collez-le dans l'éditeur XML ou de texte que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="f7f52-157">Copy the code that was previously provided and paste it into the XML or text editor that you use.</span></span> <span data-ttu-id="f7f52-158">Enregistrez le fichier sous RetrieveResults.aspx dans le répertoire racine utilisé pour IIS.</span><span class="sxs-lookup"><span data-stu-id="f7f52-158">Save the file as RetrieveResults.aspx in the root directory used for IIS.</span></span> <span data-ttu-id="f7f52-159">Il s'agit généralement de C:Inetpub\wwwroot.</span><span class="sxs-lookup"><span data-stu-id="f7f52-159">Typically, this is C:Inetpub\wwwroot.</span></span>  
  
3.  <span data-ttu-id="f7f52-160">Ouvrez la page ASP.NET dans une fenêtre du navigateur en utilisant l'URL qui suit.</span><span class="sxs-lookup"><span data-stu-id="f7f52-160">Open the ASP.NET page in a browser window using the following URL.</span></span> <span data-ttu-id="f7f52-161">Premièrement, remplacez « MyServer » par « localhost » ou par le nom réel du serveur sur lequel résident [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et les services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="f7f52-161">First, replace 'MyServer' with either "localhost" or the actual name of the server where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and IIS are installed.</span></span>  
  
    ```  
    http://MyServer/RetrieveResults.aspx  
    ```  
  
 <span data-ttu-id="f7f52-162">La page HTML générée qui en résulte et qui apparaît ressemblera à l'exemple de sortie suivant :</span><span class="sxs-lookup"><span data-stu-id="f7f52-162">The generated HTML page results that appear will be similar to the following sample output:</span></span>  
  
##### <a name="server-side-processing"></a><span data-ttu-id="f7f52-163">Traitement côté serveur</span><span class="sxs-lookup"><span data-stu-id="f7f52-163">Server-side processing</span></span>  
  
```  
Page Generated @ 3/11/2006 3:36:02 PM  
  
SqlConnection opened.  
  
<Sales.Store><Demographics><StoreSurvey xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/StoreSurvey"><AnnualSales>1500000</AnnualSales><AnnualRevenue>150000</AnnualRevenue><BankName>Primary International</BankName><BusinessType>OS</BusinessType><YearOpened>1974</YearOpened><Specialty>Road</Specialty><SquareFeet>38000</SquareFeet><Brands>3</Brands><Internet>DSL</Internet><NumberEmployees>40</NumberEmployees></StoreSurvey></Demographics></Sales.Store>  
  
SqlConnection closed.  
```  
  
> [!NOTE]  
>  <span data-ttu-id="f7f52-164">La [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `xml` prise en charge du type de données vous permet de demander que le résultat d’une requête for XML soit retourné en tant que `xml` type de données, et non sous forme de données de type chaîne ou image, en spécifiant la [directive type](type-directive-in-for-xml-queries.md).</span><span class="sxs-lookup"><span data-stu-id="f7f52-164">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]`xml` data type support lets you request that the result of a FOR XML query be returned as `xml` data type, instead of as string or image typed data, by specifying the [TYPE directive](type-directive-in-for-xml-queries.md).</span></span> <span data-ttu-id="f7f52-165">L’emploi d’une directive TYPE dans les requêtes FOR XML donne automatiquement accès à des résultats FOR XML très similaires à ceux qui sont présentés dans [Utiliser des données XML dans les applications](use-xml-data-in-applications.md).</span><span class="sxs-lookup"><span data-stu-id="f7f52-165">When the TYPE directive is used in FOR XML queries, it provides programmatic access to the FOR XML results similar to that shown in [Use XML Data in Applications](use-xml-data-in-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7f52-166">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f7f52-166">See Also</span></span>  
 [<span data-ttu-id="f7f52-167">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f7f52-167">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
