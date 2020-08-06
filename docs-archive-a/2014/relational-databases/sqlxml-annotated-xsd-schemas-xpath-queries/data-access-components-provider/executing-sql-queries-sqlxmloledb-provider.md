---
title: Exécution de requêtes SQL (fournisseur SQLXMLOLEDB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- queries [SQLXML], SQLXMLOLEDB Provider
- xml root property [SQLXML]
- SQLXMLOLEDB Provider, executing SQL queries
- SQL queries [SQLXML]
ms.assetid: 50334cf5-9c87-4c00-9beb-e08577c4fa82
author: rothja
ms.author: jroth
ms.openlocfilehash: a1e2cc87f90700e3b81a5a2ec3dd80f219a9b1d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611704"
---
# <a name="executing-sql-queries-sqlxmloledb-provider"></a><span data-ttu-id="221a4-102">Exécution de requêtes SQL (fournisseur SQLXMLOLEDB)</span><span class="sxs-lookup"><span data-stu-id="221a4-102">Executing SQL Queries (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="221a4-103">Cet exemple illustre l'utilisation des propriétés suivantes spécifiques au fournisseur SQLXMLOLEDB :</span><span class="sxs-lookup"><span data-stu-id="221a4-103">This example illustrates the use of the following SQLXMLOLEDB Provider-specific properties:</span></span>  
  
-   <span data-ttu-id="221a4-104">ClientSideXML</span><span class="sxs-lookup"><span data-stu-id="221a4-104">ClientSideXML</span></span>  
  
-   <span data-ttu-id="221a4-105">xml root</span><span class="sxs-lookup"><span data-stu-id="221a4-105">xml root</span></span>  
  
 <span data-ttu-id="221a4-106">Dans cet exemple d'application ADO côté client, une requête SQL simple est exécutée sur le client.</span><span class="sxs-lookup"><span data-stu-id="221a4-106">In this client-side ADO sample application, a simple SQL query is executed on the client.</span></span> <span data-ttu-id="221a4-107">Étant donné que la propriété ClientSideXML a la valeur true, l’instruction SELECT sans la clause FOR XML est envoyée au serveur.</span><span class="sxs-lookup"><span data-stu-id="221a4-107">Because the ClientSideXML property is set to True, the SELECT statement without the FOR XML clause is sent to the server.</span></span> <span data-ttu-id="221a4-108">Le serveur exécute la requête et retourne un ensemble de lignes au client.</span><span class="sxs-lookup"><span data-stu-id="221a4-108">The server executes the query and returns a rowset to the client.</span></span> <span data-ttu-id="221a4-109">Le client applique ensuite la transformation FOR XML à l'ensemble de lignes et génère un document XML.</span><span class="sxs-lookup"><span data-stu-id="221a4-109">The client then applies the FOR XML transformation to the rowset and produces an XML document.</span></span>  
  
 <span data-ttu-id="221a4-110">La propriété racine XML fournit l’élément racine de niveau supérieur unique pour le document XML généré.</span><span class="sxs-lookup"><span data-stu-id="221a4-110">The xml root property provides the single top-level root element for the XML document that is generated.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="221a4-111">Dans le code, vous devez fournir le nom de l'instance de Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="221a4-111">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="221a4-112">En outre, cet exemple spécifie l'utilisation de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) comme fournisseur de données, ce qui requiert l'installation d'un logiciel client réseau supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="221a4-112">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) for the data provider, which requires additional network client software to be installed.</span></span> <span data-ttu-id="221a4-113">Pour plus d’informations, consultez [Configuration système requise pour SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="221a4-113">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
Sub main()  
Dim oTestStream As New ADODB.Stream  
Dim oTestConnection As New ADODB.Connection  
Dim oTestCommand As New ADODB.Command  
  
oTestConnection.Open "provider=SQLXMLOLEDB.4.0;data provider=SQLNCLI11;data source=SqlServerName;initial catalog=AdventureWorks;Integrated Security=SSPI ;"  
oTestCommand.ActiveConnection = oTestConnection  
oTestCommand.Properties("ClientSideXML") = True  
oTestCommand.CommandText = "SELECT TOP 10 FirstName, LastName FROM Person.Contact FOR XML AUTO"  
oTestStream.Open  
oTestCommand.Properties("Output Stream").Value = oTestStream  
oTestCommand.Properties("xml root") = "root"  
oTestCommand.Execute , , adExecuteStream  
  
oTestStream.Position = 0  
oTestStream.Charset = "utf-8"  
Debug.Print oTestStream.ReadText(adReadAll)  
End Sub  
Sub Form_Load()  
 main  
End Sub  
```  
  
  
