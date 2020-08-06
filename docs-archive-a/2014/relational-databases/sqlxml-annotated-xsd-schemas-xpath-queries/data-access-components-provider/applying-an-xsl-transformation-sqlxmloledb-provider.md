---
title: Application d’une transformation XSL (fournisseur SQLXMLOLEDB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXMLOLEDB Provider, applying XSL transformations
- applying XSL transformations [SQLXML]
- xsl property
- Base Path property
- XSL Transformations [SQLXML]
ms.assetid: cb5e41ab-dd20-4873-af20-f417bd1bbf6d
author: rothja
ms.author: jroth
ms.openlocfilehash: 7fbb427a95d9f2308bf65724758a4a1563b42575
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610991"
---
# <a name="applying-an-xsl-transformation-sqlxmloledb-provider"></a><span data-ttu-id="83fb3-102">Application d'une transformation XSL (fournisseur SQLXMLOLEDB)</span><span class="sxs-lookup"><span data-stu-id="83fb3-102">Applying an XSL Transformation (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="83fb3-103">Dans cet exemple d'application ADO, une requête SQL est exécutée et le langage XSLT est appliqué au résultat.</span><span class="sxs-lookup"><span data-stu-id="83fb3-103">In this sample ADO application, an SQL query is executed, and an XSL transformation is applied to the result.</span></span> <span data-ttu-id="83fb3-104">L’affectation de la valeur true à la propriété ClientSideXML applique le traitement de l’ensemble de lignes côté client.</span><span class="sxs-lookup"><span data-stu-id="83fb3-104">Setting the ClientSideXML property to True enforces the processing of the rowset on the client side.</span></span> <span data-ttu-id="83fb3-105">Le dialecte de commande a pour valeur {5d531cb2-e6ed-11d2-b252-00c04f681b71} car la requête SQL est spécifiée dans un modèle et que ce dialecte doit être spécifié lors de l'exécution d'un modèle.</span><span class="sxs-lookup"><span data-stu-id="83fb3-105">The command dialect is set to {5d531cb2-e6ed-11d2-b252-00c04f681b71}, because the SQL query is specified in a template and this dialect must be specified when executing a template.</span></span> <span data-ttu-id="83fb3-106">La propriété XSL spécifie le fichier XSL à utiliser pour appliquer la transformation.</span><span class="sxs-lookup"><span data-stu-id="83fb3-106">The xsl property specifies the XSL file to use to apply the transformation.</span></span> <span data-ttu-id="83fb3-107">La valeur de la propriété chemin de base est utilisée pour rechercher le fichier XSL.</span><span class="sxs-lookup"><span data-stu-id="83fb3-107">The value of Base Path property is used to search for the XSL file.</span></span> <span data-ttu-id="83fb3-108">Si vous spécifiez un chemin d’accès dans la valeur de la propriété XSL, le chemin d’accès est relatif au chemin d’accès spécifié dans la propriété chemin d’accès de base.</span><span class="sxs-lookup"><span data-stu-id="83fb3-108">If you specify a path in the value of the xsl property, the path is relative to the path that is specified in the Base Path property.</span></span>  
  
 <span data-ttu-id="83fb3-109">Cet exemple indique comment utiliser les propriétés suivantes spécifiques au fournisseur SQLXMLOLEDB :</span><span class="sxs-lookup"><span data-stu-id="83fb3-109">This example shows how to use the following SQLXMLOLEDB Provider-specific properties:</span></span>  
  
-   <span data-ttu-id="83fb3-110">ClientSideXML</span><span class="sxs-lookup"><span data-stu-id="83fb3-110">ClientSideXML</span></span>  
  
-   <span data-ttu-id="83fb3-111">xsl</span><span class="sxs-lookup"><span data-stu-id="83fb3-111">xsl</span></span>  
  
 <span data-ttu-id="83fb3-112">Dans cet exemple d'application ADO côté client, un modèle XML contenant une requête SQL est exécuté sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="83fb3-112">In this client-side ADO sample application, an XML template that consists of an SQL query is executed on the server.</span></span>  
  
 <span data-ttu-id="83fb3-113">Étant donné que la propriété ClientSideXML a la valeur true, l’instruction SELECT sans la clause FOR XML est envoyée au serveur.</span><span class="sxs-lookup"><span data-stu-id="83fb3-113">Because the ClientSideXML property is set to True, the SELECT statement without the FOR XML clause is sent to the server.</span></span> <span data-ttu-id="83fb3-114">Le serveur exécute la requête et retourne un ensemble de lignes au client.</span><span class="sxs-lookup"><span data-stu-id="83fb3-114">The server executes the query and returns a rowset to the client.</span></span> <span data-ttu-id="83fb3-115">Le client applique ensuite la transformation FOR XML à l'ensemble de lignes et génère le document XML.</span><span class="sxs-lookup"><span data-stu-id="83fb3-115">The client then applies the FOR XML transformation to the rowset and produces the XML document.</span></span>  
  
 <span data-ttu-id="83fb3-116">La propriété XSL est spécifiée dans l’application ; par conséquent, la transformation XSL est appliquée au document XML généré sur le client, et le résultat est une table à deux colonnes.</span><span class="sxs-lookup"><span data-stu-id="83fb3-116">The xsl property is specified in the application; therefore, the XSL transformation is applied to the XML document that is generated on the client, and the result is a two-column table.</span></span>  
  
 <span data-ttu-id="83fb3-117">Pour exécuter la commande de modèle, vous devez spécifier le dialecte de modèle XML-{5d531cb2-e6ed-11d2-b252-00c04f681b71}.</span><span class="sxs-lookup"><span data-stu-id="83fb3-117">To execute the template command, the XML template dialect - {5d531cb2-e6ed-11d2-b252-00c04f681b71} - must be specified.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="83fb3-118">Dans le code, vous devez fournir le nom de l'instance de Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="83fb3-118">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="83fb3-119">En outre, cet exemple spécifie l'utilisation de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client comme fournisseur de données, ce qui requiert l'installation d'un logiciel client réseau supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="83fb3-119">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client for the data provider which requires additional network client software to be installed.</span></span> <span data-ttu-id="83fb3-120">Pour plus d’informations, consultez [Configuration système requise pour SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="83fb3-120">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
Sub main()  
Dim oTestStream As New ADODB.Stream  
Dim oTestConnection As New ADODB.Connection  
Dim oTestCommand As New ADODB.Command  
oTestConnection.Open "provider=SQLXMLOLEDB.4.0;data provider=SQLNCLI11;data source=SqlServerName;initial catalog=AdventureWorks;Integrated Security=SSPI;"  
Set oTestCommand.ActiveConnection = oTestConnection  
oTestCommand.Properties("ClientSideXML") = True  
oTestCommand.CommandText = _  
        "<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql' >" & _  
       " <sql:query> " & _  
        "   SELECT TOP 25 FirstName, LastName FROM Person.Contact FOR XML AUTO " & _  
        "   </sql:query> " & _  
        " </ROOT> "  
oTestStream.Open  
' You need the dialect if you are executing a template.  
oTestCommand.Dialect = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
oTestCommand.Properties("Output Stream").Value = oTestStream  
oTestCommand.Properties("Base Path").Value = "c:\Schemas\SQLXML4\ExecuteTemplateWithXSL\"  
oTestCommand.Properties("xsl").Value = "myxsl.xsl"  
oTestCommand.Execute , , adExecuteStream  
  
oTestStream.Position = 0  
oTestStream.Charset = "utf-8"  
Debug.Print oTestStream.ReadText(adReadAll)  
End Sub  
Sub Form_Load()  
 main  
End Sub  
```  
  
 <span data-ttu-id="83fb3-121">Le modèle XSL suit.</span><span class="sxs-lookup"><span data-stu-id="83fb3-121">The XSL template follows.</span></span> <span data-ttu-id="83fb3-122">Le résultat de l'application de ce modèle XSL est une table à deux colonnes.</span><span class="sxs-lookup"><span data-stu-id="83fb3-122">The result of applying this XSL template is a two-column table.</span></span>  
  
```  
<?xml version='1.0' encoding='UTF-8'?>            
 <xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">   
  
    <xsl:template match = 'Person.Contact'>  
       <TR>  
         <TD><xsl:value-of select = '@FirstName' /></TD>  
         <TD><B><xsl:value-of select = '@LastName' /></B></TD>  
       </TR>  
    </xsl:template>  
    <xsl:template match = '/'>  
      <HTML>  
        <HEAD>  
           <STYLE>th { background-color: #CCCCCC }</STYLE>  
        </HEAD>  
        <BODY>  
         <TABLE border='1' style='width:300;'>  
           <TR><TH colspan='2'>Contacts</TH></TR>  
           <TR>  
              <TH >First name</TH>  
              <TH>Last name</TH>  
           </TR>  
           <xsl:apply-templates select = 'ROOT' />  
         </TABLE>  
        </BODY>  
      </HTML>  
    </xsl:template>  
</xsl:stylesheet>  
```  
  
  
