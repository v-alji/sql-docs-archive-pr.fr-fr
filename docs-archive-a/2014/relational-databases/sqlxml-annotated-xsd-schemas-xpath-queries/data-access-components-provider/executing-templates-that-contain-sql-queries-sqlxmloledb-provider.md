---
title: Exécution de modèles contenant des requêtes SQL (fournisseur SQLXMLOLEDB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- templates [SQLXML]
- SQLXMLOLEDB Provider, executing template files
- templates [SQLXML], SQL queries
- XML templates [SQLXML]
- SQL queries [SQLXML]
ms.assetid: ff2bc36f-e3fb-4d8f-8e3a-2680a39eda11
author: rothja
ms.author: jroth
ms.openlocfilehash: c3d3bc340612286e211d85f52a3d914d1d1b6b9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610990"
---
# <a name="executing-templates-that-contain-sql-queries-sqlxmloledb-provider"></a><span data-ttu-id="36b8e-102">Exécution de modèles contenant des requêtes SQL (fournisseur SQLXMLOLEDB)</span><span class="sxs-lookup"><span data-stu-id="36b8e-102">Executing Templates That Contain SQL Queries (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="36b8e-103">Cet exemple illustre l’utilisation de la propriété SQLXMLOLEDB spécifique au fournisseur ClientSideXML.</span><span class="sxs-lookup"><span data-stu-id="36b8e-103">This example illustrates the use of the SQLXMLOLEDB Provider-specific property ClientSideXML.</span></span> <span data-ttu-id="36b8e-104">Dans cet exemple d'application ADO côté client, un modèle XML contenant une requête SQL est exécuté sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="36b8e-104">In this client-side ADO sample application, an XML template that consists of an SQL query is executed on the server.</span></span>  
  
 <span data-ttu-id="36b8e-105">Étant donné que la propriété ClientSideXML a la valeur true, l’instruction SELECT sans la clause FOR XML est envoyée au serveur.</span><span class="sxs-lookup"><span data-stu-id="36b8e-105">Because the ClientSideXML property is set to True, the SELECT statement without the FOR XML clause is sent to the server.</span></span> <span data-ttu-id="36b8e-106">Le serveur exécute la requête et retourne un ensemble de lignes au client.</span><span class="sxs-lookup"><span data-stu-id="36b8e-106">The server executes the query and returns a rowset to the client.</span></span> <span data-ttu-id="36b8e-107">Le client applique ensuite la transformation FOR XML à l'ensemble de lignes et génère un document XML.</span><span class="sxs-lookup"><span data-stu-id="36b8e-107">The client then applies the FOR XML transformation to the rowset and produces an XML document.</span></span>  
  
 <span data-ttu-id="36b8e-108">Le modèle XML fournit un seul élément racine de niveau supérieur ( \<ROOT> ) pour le document XML qui est généré ; par conséquent, la propriété racine XML n’est pas fournie.</span><span class="sxs-lookup"><span data-stu-id="36b8e-108">The XML template provides a single top-level root element (\<ROOT>) for the XML document that is generated; therefore, the xml root property is not provided.</span></span>  
  
 <span data-ttu-id="36b8e-109">Pour exécuter des modèles XML, le dialecte {5d531cb2-e6ed-11d2-b252-00c04f681b71} doit être spécifié.</span><span class="sxs-lookup"><span data-stu-id="36b8e-109">To execute XML templates, the dialect {5d531cb2-e6ed-11d2-b252-00c04f681b71} must be specified.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="36b8e-110">Dans le code, vous devez fournir le nom de l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="36b8e-110">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="36b8e-111">En outre, cet exemple spécifie l’utilisation de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) pour le fournisseur de données qui requiert l’installation d’un logiciel client réseau supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="36b8e-111">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) for the data provider which requires additional network client software to be installed.</span></span> <span data-ttu-id="36b8e-112">Pour plus d’informations, consultez [Configuration système requise pour SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="36b8e-112">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
  
Sub Main()  
  Dim oTestStream As New ADODB.Stream  
  Dim oTestConnection As New ADODB.Connection  
  Dim oTestCommand As New ADODB.Command  
  oTestConnection.Open "Provider=SQLXMLOLEDB.4.0;Data Provider=SQLNCLI11;Data Source=SqlServerName;Initial Catalog=AdventureWorks;Integrated Security=SSPI;"  
  
  Set oTestCommand.ActiveConnection = oTestConnection  
  oTestCommand.Properties("ClientSideXML") = True  
  oTestCommand.CommandText = "<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql'> " & _  
        " <sql:query> " & _  
        "   SELECT TOP 10 FirstName, LastName FROM Person.Contact FOR XML AUTO " & _  
        "   </sql:query> " & _  
        " </ROOT> "  
  oTestStream.Open  
  ' You need the dialect if you are executing   
  ' XML templates (not for SQL queries).  
  oTestCommand.Dialect = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
  oTestCommand.Properties("Output Stream").Value = oTestStream  
  oTestCommand.Execute , , adExecuteStream  
  
  oTestStream.Position = 0  
  oTestStream.Charset = "utf-8"  
  Debug.Print oTestStream.ReadText(adReadAll)  
End Sub  
  
Sub Form_Load()  
  Main  
End Sub  
```  
  
  
