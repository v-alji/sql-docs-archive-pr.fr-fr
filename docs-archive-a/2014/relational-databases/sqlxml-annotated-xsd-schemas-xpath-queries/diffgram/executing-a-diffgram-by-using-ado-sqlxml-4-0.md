---
title: Exécution d’un DiffGram à l’aide d’ADO (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- providers [SQLXML], SQLOLEDB Provider
- ADO [SQLXML]
- SQLXMLOLEDB Provider, DiffGrams
- data providers [SQLXML], SQLOLEDB Provider
- DiffGrams [SQLXML], ADO
ms.assetid: 741fce82-de83-4923-86eb-30acb5b9a5e6
author: rothja
ms.author: jroth
ms.openlocfilehash: b96db25fd46b1ecbbc15c8acd912743e5560f178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610550"
---
# <a name="executing-a-diffgram-by-using-ado-sqlxml-40"></a><span data-ttu-id="c93e7-102">Exécution d'un DiffGram à l'aide d'ADO (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="c93e7-102">Executing a DiffGram by Using ADO (SQLXML 4.0)</span></span>
  <span data-ttu-id="c93e7-103">Cette application [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic utilise ADO pour établir une connexion à une instance de Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], puis exécute un DiffGram.</span><span class="sxs-lookup"><span data-stu-id="c93e7-103">This [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic application uses ADO to establish a connection to an instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and then executes a DiffGram.</span></span> <span data-ttu-id="c93e7-104">Dans cette application, le DiffGram et le schéma XSD sont stockés dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="c93e7-104">In this application, the DiffGram and the XSD schema are stored in a file.</span></span> <span data-ttu-id="c93e7-105">L'application charge le DiffGram à partir du fichier spécifié.</span><span class="sxs-lookup"><span data-stu-id="c93e7-105">The application loads the DiffGram from the specified file.</span></span> <span data-ttu-id="c93e7-106">Vous pouvez utiliser l’un des DiffGrams (et le schéma XSD associé) décrit dans [exemples DiffGram](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="c93e7-106">You can use any of the DiffGrams (and the associated XSD schema) described in [DiffGram Examples](diffgram-examples-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="c93e7-107">Voici le processus de l'exemple d'application :</span><span class="sxs-lookup"><span data-stu-id="c93e7-107">This is the process for the sample application:</span></span>  
  
-   <span data-ttu-id="c93e7-108">Objet **conn** (**ADODB. Connexion**) établit une connexion à une instance en cours d’exécution de SQL Server sur un serveur spécifique.</span><span class="sxs-lookup"><span data-stu-id="c93e7-108">The **conn** object (**ADODB.Connection**) establishes a connection to a running instance of SQL Server on a specific server.</span></span>  
  
-   <span data-ttu-id="c93e7-109">L’objet **cmd** (**ADODB. Command**) s’exécute sur la connexion établie.</span><span class="sxs-lookup"><span data-stu-id="c93e7-109">The **cmd** object (**ADODB.Command**) executes on the established connection.</span></span>  
  
-   <span data-ttu-id="c93e7-110">Le dialecte de la commande est défini sur DBGUID_MSSQLXML.</span><span class="sxs-lookup"><span data-stu-id="c93e7-110">The command dialect is set to DBGUID_MSSQLXML.</span></span>  
  
-   <span data-ttu-id="c93e7-111">Le DiffGram est copié dans le flux de commandes (**strmIn**) à partir d’un fichier.</span><span class="sxs-lookup"><span data-stu-id="c93e7-111">The DiffGram is copied to the command stream (**strmIn**) from a file.</span></span>  
  
-   <span data-ttu-id="c93e7-112">Le flux de sortie de la commande est défini sur l’objet **StrmOut** (**ADODB. Stream**) pour recevoir toutes les données retournées.</span><span class="sxs-lookup"><span data-stu-id="c93e7-112">The command's output stream is set to the **StrmOut** object (**ADODB.Stream**) to receive any returned data.</span></span>  
  
-   <span data-ttu-id="c93e7-113">Lorsque vous utilisez le fournisseur SQLOLEDB, par défaut, vous obtenez les fonctionnalités SQLXML de Microsoft fournies par Sqlxmlx.dll.</span><span class="sxs-lookup"><span data-stu-id="c93e7-113">When you are using the SQLOLEDB Provider, by default you will get the Microsoft SQLXML functionality provided by Sqlxmlx.dll.</span></span> <span data-ttu-id="c93e7-114">Pour utiliser Sqlxml4.dll avec le fournisseur SQLOLEDB, la propriété de **version SQLXML** doit être définie sur **SQLXML. 4.0** sur l’objet de **connexion** du fournisseur SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="c93e7-114">To use Sqlxml4.dll with the SQLOLEDB Provider, the **SQLXML Version** property must be set to **SQLXML.4.0** on the SQLOLEDB Provider **Connection** object.</span></span>  
  
-   <span data-ttu-id="c93e7-115">La commande (DiffGram) est exécutée.</span><span class="sxs-lookup"><span data-stu-id="c93e7-115">The command (DiffGram) is executed.</span></span>  
  
 <span data-ttu-id="c93e7-116">Le code suivant est celui de l'exemple d'application.</span><span class="sxs-lookup"><span data-stu-id="c93e7-116">The following code is the sample application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c93e7-117">Dans le code, vous devez fournir le nom de l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="c93e7-117">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
Private Sub Command1_Click()  
  Dim cmd As New ADODB.Command  
  Dim conn As New ADODB.Connection  
  Dim strmOut As New ADODB.Stream  
  Dim strmIn As New ADODB.Stream  
  
  'Open a connection to SQL Server.  
  conn.Provider = "SQLOLEDB"  
  conn.Open "server=SqlServerName; database=tempdb; Integrated Security=SSPI; "  
  conn.Properties("SQLXML Version") = "SQLXML.4.0"  
  Set cmd.ActiveConnection = conn  
  strmIn.Open  
  strmIn.Charset = "UTF-8"  
  strmIn.LoadFromFile "C:\SomeFilePath\SampleDiffGram.xml"  
  strmIn.Position = 0  
  Set cmd.CommandStream = strmIn  
  
  strmOut.Open  
  cmd.Properties("Output Stream").Value = strmOut  
  cmd.Properties("Output Encoding").Value = "UTF-8"  
  
  cmd.Dialect = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
  cmd.Properties("Mapping Schema") = "C:\SomeFilePath\SampleDiffGram.xml"  
  cmd.Execute , , adExecuteStream  
  strmOut.Position = 0  
  Set cmd = Nothing  
  strmOut.Charset = "UTF-8"  
  strmOut.SaveToFile "C:\DropIt.txt", adSaveCreateOverWrite  
  strmOut.Close  
  Set strmOut = Nothing  
  
End Sub  
```  
  
### <a name="to-test-the-diffgram"></a><span data-ttu-id="c93e7-118">Pour tester le DiffGram</span><span class="sxs-lookup"><span data-stu-id="c93e7-118">To test the DiffGram</span></span>  
  
1.  <span data-ttu-id="c93e7-119">Dans un dossier sur votre ordinateur, copiez l’un des DiffGrams et le schéma XSD correspondant dans l’un des exemples des [exemples DiffGram](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="c93e7-119">To a folder on your computer, copy any one of the DiffGrams and the corresponding XSD schema from one of the examples in [DiffGram Examples](diffgram-examples-sqlxml-4-0.md).</span></span>  
  
2.  <span data-ttu-id="c93e7-120">Ouvrez Visual Basic et créez un projet EXE standard.</span><span class="sxs-lookup"><span data-stu-id="c93e7-120">Open Visual Basic and create a Standard EXE project.</span></span>  
  
3.  <span data-ttu-id="c93e7-121">Ajoutez ces références au projet :</span><span class="sxs-lookup"><span data-stu-id="c93e7-121">Add these references to the project:</span></span>  
  
    ```  
    Microsoft ActiveX Data Objects 2.8 Library  
    ```  
  
4.  <span data-ttu-id="c93e7-122">Dans la boîte à outils, cliquez sur **CommandButton**, puis dessinez un bouton sur le formulaire.</span><span class="sxs-lookup"><span data-stu-id="c93e7-122">In the Toolbox, click **CommandButton**, and then draw a button on the form.</span></span>  
  
5.  <span data-ttu-id="c93e7-123">Double-cliquez sur le bouton pour modifier le code et ajoutez le code d'application fourni dans la rubrique.</span><span class="sxs-lookup"><span data-stu-id="c93e7-123">Double-click the button to edit the code, and add the application code that is provided in the topic.</span></span>  
  
6.  <span data-ttu-id="c93e7-124">Modifiez le code pour spécifier le DiffGram et les noms de fichier XSD.</span><span class="sxs-lookup"><span data-stu-id="c93e7-124">Edit the code to specify the DiffGram and XSD file names.</span></span> <span data-ttu-id="c93e7-125">Modifiez aussi la chaîne de connexion si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="c93e7-125">Also edit the connection string as appropriate.</span></span>  
  
7.  <span data-ttu-id="c93e7-126">Exécutez l'application.</span><span class="sxs-lookup"><span data-stu-id="c93e7-126">Execute the application.</span></span> <span data-ttu-id="c93e7-127">Le résultat de l'exécution dépend du DiffGram que vous exécutez.</span><span class="sxs-lookup"><span data-stu-id="c93e7-127">The result of the execution depends on what DiffGram you are executing.</span></span>  
  
  
