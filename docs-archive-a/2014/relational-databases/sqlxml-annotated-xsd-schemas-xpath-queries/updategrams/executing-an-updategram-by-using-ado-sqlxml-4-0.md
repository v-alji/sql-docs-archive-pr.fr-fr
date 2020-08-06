---
title: Exécution d’un mise à jour à l’aide d’ADO (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- ADO [SQLXML]
- updategrams [SQLXML], ADO
- executing updategrams [SQLXML]
ms.assetid: 78610ca0-f763-45fc-ac64-da5c192cc3e5
author: rothja
ms.author: jroth
ms.openlocfilehash: d8bc00406705e73eb6c9a4f2474ac1865344a8bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612726"
---
# <a name="executing-an-updategram-by-using-ado-sqlxml-40"></a><span data-ttu-id="36def-102">Exécution d'un code de mise à jour (updategram) à l'aide d'ADO (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="36def-102">Executing an Updategram by Using ADO (SQLXML 4.0)</span></span>
  <span data-ttu-id="36def-103">Cette application [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic utilise ADO pour établir une connexion à une instance de Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], puis exécute un code de mise à jour (updategram).</span><span class="sxs-lookup"><span data-stu-id="36def-103">This [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic application uses ADO to establish a connection to an instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and execute an updategram.</span></span> <span data-ttu-id="36def-104">Le code de mise à jour (updategram) met à jour le nom d'un employé spécifique.</span><span class="sxs-lookup"><span data-stu-id="36def-104">The updategram updates the last name of a specific employee.</span></span> <span data-ttu-id="36def-105">Cet exemple utilise l’exemple de base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="36def-105">This example uses the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="36def-106">Dans cet exemple d'application :</span><span class="sxs-lookup"><span data-stu-id="36def-106">In this sample application:</span></span>  
  
-   <span data-ttu-id="36def-107">Objet **conn** (**ADODB. Connexion**) établit une connexion à une instance en cours d’exécution de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sur un ordinateur serveur spécifique.</span><span class="sxs-lookup"><span data-stu-id="36def-107">The **conn** object (**ADODB.Connection**) establishes a connection to a running instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on a specific server computer.</span></span>  
  
-   <span data-ttu-id="36def-108">L’objet **cmd** (**ADODB. Command**) s’exécute sur la connexion établie.</span><span class="sxs-lookup"><span data-stu-id="36def-108">The **cmd** object (**ADODB.Command**) executes on the established connection.</span></span>  
  
-   <span data-ttu-id="36def-109">Le dialecte de la commande est défini sur DBGUID_MSSQLXML.</span><span class="sxs-lookup"><span data-stu-id="36def-109">The command dialect is set to DBGUID_MSSQLXML.</span></span>  
  
-   <span data-ttu-id="36def-110">Le mise à jour est copié dans le flux de commande (**strmIn**).</span><span class="sxs-lookup"><span data-stu-id="36def-110">The updategram is copied to the command stream (**strmIn**).</span></span>  
  
-   <span data-ttu-id="36def-111">Le flux de sortie de la commande est défini sur l’objet **StrmOut** (**ADODB. Stream**) pour recevoir toutes les données retournées.</span><span class="sxs-lookup"><span data-stu-id="36def-111">The command's output stream is set to the **StrmOut** object (**ADODB.Stream**) to receive any returned data.</span></span>  
  
-   <span data-ttu-id="36def-112">Enfin, la commande (code de mise à jour (updategram)) est exécutée.</span><span class="sxs-lookup"><span data-stu-id="36def-112">Finally the command (updategram) is executed.</span></span>  
  
 <span data-ttu-id="36def-113">Voici l'exemple de code :</span><span class="sxs-lookup"><span data-stu-id="36def-113">Here is the sample code:</span></span>  
  
```vb  
Private Sub Form_Load()  
  
  Dim cmd As New ADODB.Command  
  Dim conn As New ADODB.Connection  
  Dim strmIn As New ADODB.Stream  
  Dim strmOut As New ADODB.Stream  
  Dim SQLxml As String  
  
  ' Open a connection to the instance of SQL Server.  
  conn.Provider = "SQLOLEDB"  
  conn.Open "server=(local); database=AdventureWorks; Integrated Security=SSPI; "  
  conn.Properties("SQLXML Version") = "SQLXML.4.0"  
  Set cmd.ActiveConnection = conn  
  
  ' Build the command string in the form of an XML template.  
    SQLxml = "<ROOT xmlns:updg='urn:schemas-microsoft-com:xml-updategram' >"  
    SQLxml = SQLxml & "  <updg:sync updg:nullvalue='IsNULL'>"  
    SQLxml = SQLxml & "    <updg:before>"  
    SQLxml = SQLxml & "       <Person.Contact ContactID='64' Title='IsNULL'/>"  
    SQLxml = SQLxml & "    </updg:before>"  
    SQLxml = SQLxml & "    <updg:after>"  
    SQLxml = SQLxml & "       <Person.Contact ContactID='64' Title='Mr.'/>"  
    SQLxml = SQLxml & "    </updg:after>"  
    SQLxml = SQLxml & "  </updg:sync>"  
    SQLxml = SQLxml & "</ROOT>"  
  
  ' Set the command dialect to DBGUID_MSSQLXML.  
  cmd.Dialect = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
  
  ' Open the command stream and write our template to it.  
  strmIn.Open  
  strmIn.WriteText SQLxml  
  strmIn.Position = 0  
  
  Set cmd.CommandStream = strmIn  
  
  ' Execute the command, open the return stream, and read the result.  
  strmOut.Open  
  strmOut.LineSeparator = adCRLF  
  cmd.Properties("Output Stream").Value = strmOut  
  cmd.Properties("Output Encoding").Value = "UTF-8"  
  cmd.Execute , , adExecuteStream  
  strmOut.Position = 0  
  Debug.Print strmOut.ReadText  
  strmOut.Close  
  strmIn.Close  
  
End Sub  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="36def-114">Si vous utilisez SQLXML d'ADO pour exécuter les codes de mise à jour (updategram) qui spécifient un schéma XSD, vous devez définir la propriété "`SQLXML Version`" avec la valeur "`SQLXML.4.0`" sur l'objet de connexion, comme illustré dans l'exemple de ligne de code suivant :</span><span class="sxs-lookup"><span data-stu-id="36def-114">If you're using SQLXML from ADO to execute updategrams that specify an XSD schema, you must set the "`SQLXML Version`" property to "`SQLXML.4.0`" on the connection object, as shown in the following example line of code:</span></span>  
>   
>  `conn.Properties("SQLXML Version") = "SQLXML.4.0"`  
  
## <a name="specifying-a-mapping-schema-for-the-updategram"></a><span data-ttu-id="36def-115">Spécification d'un schéma de mappage pour le code de mise à jour (updategram)</span><span class="sxs-lookup"><span data-stu-id="36def-115">Specifying a Mapping Schema for the Updategram</span></span>  
 <span data-ttu-id="36def-116">Cet exemple illustre comment spécifier et utiliser un schéma de mappage dans un code de mise à jour (updategram).</span><span class="sxs-lookup"><span data-stu-id="36def-116">This example illustrates how to specify and use a mapping schema in an updategram.</span></span>  
  
 <span data-ttu-id="36def-117">Enregistrez le schéma XSD suivant (EmpSchema.xml) sur votre disque et veillez à mettre à jour le chemin d'accès spécifié dans le code sur l'emplacement du schéma de mappage de votre disque.</span><span class="sxs-lookup"><span data-stu-id="36def-117">Save the following XSD schema (EmpSchema.xml) to your disk, and be sure to update the path that is specified in the code to the location of the mapping schema on your disk.</span></span> <span data-ttu-id="36def-118">Le code présume que le schéma est enregistré sur le lecteur C: du dossier Schémas.</span><span class="sxs-lookup"><span data-stu-id="36def-118">The code assumes that the schema is saved on the C: drive in the Schemas folder.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Contact" sql:relation="Person.Contact" >  
   <xsd:complexType>  
        <xsd:attribute name="CID"    
                       sql:field="ContactID"   
                       type="xsd:string" />   
        <xsd:attribute name="MName"    
                       sql:field="MiddleName"    
                       type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="36def-119">Comme les schémas XSD et XDR peuvent être spécifiés, voici le schéma XDR équivalent :</span><span class="sxs-lookup"><span data-stu-id="36def-119">Because both XSD and XDR schemas can be specified, this is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
   <Schema xmlns="urn:schemas-microsoft-com:xml-data"   
         xmlns:dt="urn:schemas-microsoft-com:datatypes"   
         xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
     <ElementType name="Contact" sql:relation="Person.Contact" >  
       <AttributeType name="CID" />  
       <AttributeType name="MName" />  
  
       <attribute type="CID" sql:field="ContactID" />  
       <attribute type="MName" sql:field="MiddleName" />  
     </ElementType>  
   </Schema>   
```  
  
 <span data-ttu-id="36def-120">Voici le code Visual Basic pour exécuter un code de mise à jour (updategram) possédant un schéma de mappage associé.</span><span class="sxs-lookup"><span data-stu-id="36def-120">This is the Visual Basic code to execute an updategram that has an associated mapping schema.</span></span> <span data-ttu-id="36def-121">Le code de mise à jour (updategram) met à jour le deuxième prénom du contact 1 dans la table Person.Contact.</span><span class="sxs-lookup"><span data-stu-id="36def-121">The updategram updates the middle name for contact 1 in the Person.Contact table.</span></span>  
  
```vb  
Private Sub Form_Load()  
    Dim cmd As New ADODB.Command  
    Dim conn As New ADODB.Connection  
    Dim strmIn As New ADODB.Stream  
    Dim strmOut As New ADODB.Stream  
  
    ' Open a connection to the SQL Server.  
    conn.Provider = "SQLOLEDB"  
    conn.Open "server=(local); database=AdventureWorks; Integrated Security='SSPI' ;"  
    conn.Properties("SQLXML Version") = "SQLXML.4.0"  
    Set cmd.ActiveConnection = conn  
  
    ' Open the command stream and write the template to it.  
    strmIn.Open  
    strmIn.WriteText "<ROOT xmlns:updg='urn:schemas-microsoft-com:xml-updategram' >"  
    strmIn.WriteText "  <updg:sync mapping-schema='C:\Schemas\EmpSchema.xml' >"  
    strmIn.WriteText "      <updg:before>"  
    strmIn.WriteText "          <Contact CID='1' />"  
    strmIn.WriteText "      </updg:before>"  
    strmIn.WriteText "      <updg:after>"  
    strmIn.WriteText "          <Contact MName='M.'/>"  
    strmIn.WriteText "      </updg:after>"  
    strmIn.WriteText "  </updg:sync>"  
    strmIn.WriteText "</ROOT>"  
  
    ' Set the command dialect to XML.  
    cmd.Dialect = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
    strmIn.Position = 0  
    Set cmd.CommandStream = strmIn  
  
    ' Execute the command, open the return stream, and read the result.  
    strmOut.Open  
    strmOut.LineSeparator = adCRLF  
    cmd.Properties("Output Stream").Value = strmOut  
    cmd.Execute , , adExecuteStream  
    strmOut.Position = 0  
    Debug.Print strmOut.ReadText  
    strmOut.Close  
    strmIn.Close  
    conn.Close  
End Sub  
```  
  
## <a name="passing-parameters"></a><span data-ttu-id="36def-122">Passage de paramètres</span><span class="sxs-lookup"><span data-stu-id="36def-122">Passing Parameters</span></span>  
 <span data-ttu-id="36def-123">Dans les applications Visual Basic fournies précédemment, les paramètres ne sont pas transmis.</span><span class="sxs-lookup"><span data-stu-id="36def-123">In the Visual Basic applications provided earlier, parameters are not passed.</span></span> <span data-ttu-id="36def-124">Dans cette application, les valeurs **ContactID** et **MiddleName** sont passées comme entrée paramétrable à mise à jour.</span><span class="sxs-lookup"><span data-stu-id="36def-124">In this application, the **ContactID** and **MiddleName** values are passed as parameterized input to the updategram.</span></span>  
  
```vb  
Private Sub Form_Load()  
  
  Dim cmd As New ADODB.Command  
  Dim conn As New ADODB.Connection  
  Dim strmIn As New ADODB.Stream  
  Dim strmOut As New ADODB.Stream  
  Dim InputContactID As String  
  Dim InputMiddleName As String  
  
  InputContactID = "1"  
  InputMiddleName = "Q."  
  
  ' Open a connection to the instance of SQL Server.  
  conn.Provider = "SQLOLEDB"  
  conn.Open "server=(local); database=AdventureWorks; Integrated Security=SSPI; "  
  conn.Properties("SQLXML Version") = "SQLXML.4.0"  
  Set cmd.ActiveConnection = conn  
  
  ' Build the command string in the form of an XML template.  
  SQLxml = "<ROOT xmlns:updg='urn:schemas-microsoft-com:xml-updategram' >"  
  SQLxml = SQLxml & "<updg:header>"  
  SQLxml = SQLxml & "<updg:param name='ContactID'/>"  
  SQLxml = SQLxml & "<updg:param name='MiddleName' />"  
  SQLxml = SQLxml & "</updg:header>"  
  SQLxml = SQLxml & "<updg:sync >"  
  SQLxml = SQLxml & " <updg:before>"  
  SQLxml = SQLxml & "   <Person.Contact ContactID='$ContactID' />"  
  SQLxml = SQLxml & "</updg:before>"  
  SQLxml = SQLxml & "<updg:after>"  
  SQLxml = SQLxml & "<Person.Contact MiddleName='$MiddleName' />"  
  SQLxml = SQLxml & "</updg:after>"  
  SQLxml = SQLxml & "</updg:sync>"  
  SQLxml = SQLxml & "</ROOT>"  
  
  ' Set the command dialect to XML.  
  cmd.Dialect = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
  
  ' Open the command stream and write the template to it.  
  strmIn.Open  
  strmIn.WriteText SQLxml  
  strmIn.Position = 0  
  
  Set cmd.CommandStream = strmIn  
  
  ' Execute the command, open the return stream, and read the result.  
  strmOut.Open  
  strmOut.LineSeparator = adCRLF  
  cmd.NamedParameters = True  
  cmd.Parameters.Append cmd.CreateParameter("@ContactID", adBSTR, adParamInput, 1, InputContactID)  
  cmd.Parameters.Append cmd.CreateParameter("@MiddleName", adBSTR, adParamInput, 7, InputMiddleName)  
  cmd.Properties("Output Stream").Value = strmOut  
  cmd.Execute , , adExecuteStream  
  strmOut.Position = 0  
  Debug.Print strmOut.ReadText  
  
End Sub  
```  
  
  
