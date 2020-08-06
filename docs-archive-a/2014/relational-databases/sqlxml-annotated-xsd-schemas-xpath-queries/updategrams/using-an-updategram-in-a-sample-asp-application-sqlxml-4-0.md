---
title: Utilisation d’un mise à jour dans un exemple d’application ASP (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- ASP applications [SQLXML]
- Active Server Pages
- updategrams [SQLXML], ASP applications
ms.assetid: 10eff799-4c39-4b52-8b38-7ea6f68454a8
author: rothja
ms.author: jroth
ms.openlocfilehash: 50dce61e5bd3111244defe9cc18e808580687185
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611687"
---
# <a name="using-an-updategram-in-a-sample-asp-application-sqlxml-40"></a><span data-ttu-id="62489-102">Utilisation d'un code de mise à jour (updategram) dans un exemple d'application ASP (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="62489-102">Using an Updategram in a Sample ASP Application (SQLXML 4.0)</span></span>
  <span data-ttu-id="62489-103">Cette application ASP (Active Server Pages) vous permet de mettre à jour des informations client dans la table Person.Contact dans l'exemple de base de données AdventureWorks dans Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62489-103">This Active Server Pages (ASP) application allows you to update customer information in the Person.Contact table in the AdventureWorks sample database in Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="62489-104">L'application effectue les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="62489-104">The application does the following:</span></span>  
  
-   <span data-ttu-id="62489-105">Elle invite l'utilisateur à entrer un ID de contact.</span><span class="sxs-lookup"><span data-stu-id="62489-105">Asks the user to enter a contact ID.</span></span>  
  
-   <span data-ttu-id="62489-106">Elle utilise cette valeur d'ID de client pour exécuter un modèle afin d'extraire des informations de contact de la table Person.Contact.</span><span class="sxs-lookup"><span data-stu-id="62489-106">Uses this customer ID value to execute a template to retrieve contact information from the Person.Contact table.</span></span>  
  
-   <span data-ttu-id="62489-107">Elle affiche ces informations en utilisant un formulaire HTML.</span><span class="sxs-lookup"><span data-stu-id="62489-107">Displays this information by using an HTML form.</span></span>  
  
 <span data-ttu-id="62489-108">L'utilisateur peut alors mettre à jour les informations de contact mais pas l'ID de contact (car ContactID est la clé primaire).</span><span class="sxs-lookup"><span data-stu-id="62489-108">The user can then update contact information but not the contact ID (because the ContactID is the primary key).</span></span> <span data-ttu-id="62489-109">Après que l'utilisateur a soumis les informations, un code de mise à jour (updategram) est exécuté et tous les paramètres du formulaire sont passés au code de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="62489-109">After the user submits the information, an updategram is executed and all the form parameters are passed to the updategram.</span></span>  
  
 <span data-ttu-id="62489-110">Le modèle suivant est le premier modèle (GetContact.xml).</span><span class="sxs-lookup"><span data-stu-id="62489-110">The following template is the first template (GetContact.xml).</span></span> <span data-ttu-id="62489-111">Enregistrez ce modèle dans le répertoire associé au nom virtuel de type `template`.</span><span class="sxs-lookup"><span data-stu-id="62489-111">Save this template in the directory that is associated with the virtual name of `template` type.</span></span>  
  
```  
<root xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
   <sql:header>  
      <sql:param name="cid"></sql:param>  
   </sql:header>  
   <sql:query>  
      SELECT  *   
      FROM    Person.Contact  
      WHERE   ContactID=@cid   
      FOR XML AUTO  
   </sql:query>  
</root>  
```  
  
 <span data-ttu-id="62489-112">Le modèle suivant est le deuxième modèle (UpdateContact.xml).</span><span class="sxs-lookup"><span data-stu-id="62489-112">The following template is the second template (UpdateContact.xml).</span></span> <span data-ttu-id="62489-113">Enregistrez ce modèle dans le répertoire associé au nom virtuel de type `template`.</span><span class="sxs-lookup"><span data-stu-id="62489-113">Save this template in the directory that is associated with the virtual name of `template` type.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:header>  
   <updg:param name="cid"/>  
   <updg:param name="title" />  
   <updg:param name="firstname" />  
   <updg:param name="lastname" />  
   <updg:param name="emailaddress" />  
   <updg:param name="phone" />  
</updg:header>  
<updg:sync >  
   <updg:before>  
      <Person.Contact ContactID="$cid" />   
   </updg:before>  
   <updg:after>  
      <Person.Contact ContactID="$cid"   
       Title="$title"  
       FirstName="$firstname"  
       LastName="$lastname"  
       EmailAddress="$emailaddress"  
       Phone="$phone"/>  
   </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="62489-114">Le code suivant est l'application ASP (SampleASP.asp).</span><span class="sxs-lookup"><span data-stu-id="62489-114">The following code is the ASP application (SampleASP.asp).</span></span> <span data-ttu-id="62489-115">Enregistrez-le dans le répertoire associé à une racine virtuelle que vous créez à l'aide de l'utilitaire Gestionnaire des services Internet.</span><span class="sxs-lookup"><span data-stu-id="62489-115">Save it in the directory that is associated with a virtual root that you create by using the Internet Services Manager utility.</span></span> <span data-ttu-id="62489-116">(Cette racine virtuelle n'est pas créée à l'aide d'IIS Virtual Directory Management pour l'utilitaire [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] car IIS Virtual Directory Management pour [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ne peut pas identifier ou accéder à des applications ASP.)</span><span class="sxs-lookup"><span data-stu-id="62489-116">(This virtual root is not created by using the IIS Virtual Directory Management for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utility because IIS Virtual Directory Management for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] cannot access or identify ASP applications.).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="62489-117">Dans le code, vous devez remplacer le « ServerName » par le nom du serveur exécutant les services Internet (Microsoft Internet Information Services (IIS)).</span><span class="sxs-lookup"><span data-stu-id="62489-117">In the code, you must replace "ServerName" with the name of the server running Microsoft Internet Information Services (IIS).</span></span>  
  
```  
<% LANGUAGE=VBSCRIPT %>  
<%  
  Dim ContactID  
  ContactID=Request.Form("cid")  
%>  
<html>  
<body>  
<%  
  'If a ContactID value is not yet provided, display this form.  
  if ContactID="" then  
%>  
<!-- If the ContactID has not been specified, display the form that allows users to enter an ID. -->  
<form action="AdventureWorksContacts.asp" method="POST">  
<br>  
Enter ContactID: <input type=text name="cid"><br>  
<input type=submit value="Submit this ID" ><br><br>  
<-- Otherwise, if a ContactID is entered, display the second part of the form where the user can change customer information. -->  
<%  
  else  
%>  
<form name="Contacts" action="http://localhost/AdventureWorks/Template/UpdateContact.xml" method="POST">  
You may update customer information below.<br><br>  
<!-- A comment goes here to separate the parts of the application or page. -->  
<br>  
<%  
  ' Load the document in the parser and extract the values to populate the form.  
    Set objXML=Server.CreateObject("MSXML2.DomDocument")  
    ObjXML.setProperty "ServerHTTPRequest", TRUE  
  
    objXML.async=False  
    objXML.Load("http://localhost/AdventureWorks/Template/GetContact.xml?cid=" & ContactID)  
    set objCustomer=objXML.documentElement.childNodes.Item(0)  
  
  ' In retrieving data from the database, if a value in the column is NULL there  
  '  is no attribute for the corresponding element. In this case,  
  ' skip the error generation and go to the next attribute.  
  
  On Error Resume Next  
  
  Response.Write "Contact ID: <input type=text readonly=true style='background-color:silver' name=cid value="""  
  Response.Write objCustomer.attributes(0).value  
  Response.Write """><br><br>"  
  
  Response.Write "Title: <input type=text name=title value="""  
  Response.Write objCustomer.attributes(1).value  
  Response.Write """><br><br>"  
  
  Response.Write "First Name: <input type=text name=firstname value="""  
  Response.Write objCustomer.attributes(2).value  
  Response.Write """><br>"  
  
  Response.Write "Last Name: <input type=text name=lastname value="""  
  Response.Write objCustomer.attributes(3).value  
  Response.Write """><br><br>"  
  
  Response.Write "Email Address: <input type=text name=emailaddress value="""  
  Response.Write objCustomer.attributes(4).value  
  Response.Write """><br><br>"  
  
  Response.Write "Phone: <input type=text name=phone value="""  
  Response.Write objCustomer.attributes(9).value  
  Response.Write """><br><br>"  
  
  set objCustomer=Nothing  
  Set objXML=Nothing  
%>  
<input type="submit" value="Submit this change" ><br><br>  
<input type=hidden name="contenttype" value="text/xml">  
<input type=hidden name="eeid" value="<%=ContactID%>"><br><br>  
<% end if %>  
  
</form>  
</body>  
</html>  
```  
  
## <a name="see-also"></a><span data-ttu-id="62489-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="62489-118">See Also</span></span>  
 [<span data-ttu-id="62489-119">Considérations sur la sécurité mise à jour &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="62489-119">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
