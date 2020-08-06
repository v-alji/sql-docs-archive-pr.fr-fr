---
title: Utilisation d'ADO pour exécuter des requêtes SQLXML 4.0
ms.custom: ''
ms.date: 12/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- query testers [SQLXML]
- test scripts
- ADO [SQLXML]
- queries [SQLXML], ADO
- SQLXML, ADO
ms.assetid: 3d54e3bb-7c5f-427e-82f8-1403a54c4f53
author: rothja
ms.author: jroth
ms.openlocfilehash: 169d20b4192e4a5b8e7b32839f2da255fc58d89c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696707"
---
# <a name="using-ado-to-execute-sqlxml-40-queries"></a><span data-ttu-id="8393b-102">Utilisation d'ADO pour exécuter des requêtes SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="8393b-102">Using ADO to Execute SQLXML 4.0 Queries</span></span>
  <span data-ttu-id="8393b-103">Dans les versions antérieures de SQLXML, l'exécution de requêtes basées sur le protocole HTTP était prise en charge à l'aide de répertoires virtuels IIS SQLXML et du filtre ISAPI SQLXML.</span><span class="sxs-lookup"><span data-stu-id="8393b-103">In previous versions of SQLXML, HTTP-based query execution was supported using SQLXML IIS virtual directories and the SQLXML ISAPI filter.</span></span> <span data-ttu-id="8393b-104">Dans SQLXML 4.0, ces composants ont été supprimés du fait que des fonctionnalités semblables et se chevauchant sont fournies avec les services Web XML natifs à compter de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8393b-104">In SQLXML 4.0, these components have been removed as similar and overlapping functionality is provided with native XML Web services beginning in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="8393b-105">Vous pouvez également exécuter des requêtes et utiliser SQLXML 4.0 avec vos applications COM en exploitant les extensions SQLXML aux objets ADO (ActiveX Data Objects) qui ont été introduites dans Microsoft Data Access Components (MDAC) 2.6 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="8393b-105">As an alternative, you can execute queries and use SQLXML 4.0 with your COM-based applications, by leveraging the SQLXML extensions to ActiveX Data Objects (ADO) that were first introduced in Microsoft Data Access Components (MDAC) 2.6 and later.</span></span>  
  
 <span data-ttu-id="8393b-106">Cette rubrique montre comment utiliser SQLXML et ADO dans le cadre d'une application Visual Basic Scripting Edition (VBScript), c'est-à-dire un script avec l'extension de fichier .vbs.</span><span class="sxs-lookup"><span data-stu-id="8393b-106">This topic demonstrates using SQLXML and ADO as part of a Visual Basic Scripting Edition (VBScript) application (a script with the .vbs file extension).</span></span> <span data-ttu-id="8393b-107">Elle fournit des procédures d'installation initiale pour vous aider à recréer et à tester des exemples de requête dans la documentation SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="8393b-107">It provides initial setup procedures to help you recreate and test query samples in the SQLXML 4.0 documentation.</span></span>  
  
## <a name="creating-the-sqlxml-40-test-script"></a><span data-ttu-id="8393b-108">Création du script de test SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="8393b-108">Creating the SQLXML 4.0 Test Script</span></span>  
 <span data-ttu-id="8393b-109">Dans cette procédure, vous créez un fichier VBScript (.vbs), Sqlxml4test.vbs, qui peut être utilisé pour exécuter des requêtes SQLXML en exploitant les extensions ADO SQLXML dans ADO 2.6 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="8393b-109">In this procedure, you create a VBScript (.vbs) file, Sqlxml4test.vbs, which can be used to execute SQLXML queries by leveraging the SQLXML ADO extensions in ADO 2.6 and later.</span></span>  
  
#### <a name="to-create-the-sqlxml-40-query-tester-using-ado-vbscript"></a><span data-ttu-id="8393b-110">Pour créer le testeur de requêtes SQLXML 4.0 à l'aide d'ADO (VBScript)</span><span class="sxs-lookup"><span data-stu-id="8393b-110">To create the SQLXML 4.0 query tester using ADO (VBScript).</span></span>  
  
1.  <span data-ttu-id="8393b-111">Copiez le code VBScript ci-dessous, puis collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="8393b-111">Copy the VBScript code below, and paste it into a text file.</span></span> <span data-ttu-id="8393b-112">Enregistrez le fichier sous Sqlxml4test.vbs.</span><span class="sxs-lookup"><span data-stu-id="8393b-112">Save the file as Sqlxml4test.vbs.</span></span>  
  
    ```vb
    WScript.Echo "Query process may take a few seconds to complete. Please be patient."  
  
    ' Note that for SQL Server Native Client to be used as the data provider,  
    ' it needs to be installed on the client computer first. Also, SQLXML extensions   
    ' for ADO are used and available in MDAC 2.6 or later.  
  
    'Set script variables.  
    inputFile = "@@FILE_NAME@@"  
    strServer = "@@SERVER_NAME@@"  
    strDatabase = "@@DATABASE_NAME@@"  
    dbGuid = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
  
    ' Establish ADO connection to SQL Server and   
    ' create an instance of the ADO Command object.  
    Set conn = CreateObject("ADODB.Connection")  
    Set cmd = CreateObject("ADODB.Command")  
    conn.Open "Provider=SQLXMLOLEDB.4.0;Data Provider=SQLNCLI11;Server=" & strServer & _  
              ";Database=" & strDatabase & ";Integrated Security=SSPI"  
    Set cmd.ActiveConnection = conn  
  
    ' Create the input stream as an instance of the ADO Stream object.  
    Set inStream = CreateObject("ADODB.Stream")  
    inStream.Open  
    inStream.Charset = "utf-8"  
    inStream.LoadFromFile inputFile  
  
    ' Set ADO Command instance to use input stream.  
    Set cmd.CommandStream = inStream  
  
    ' Set the command dialect.  
    cmd.Dialect = dbGuid  
  
    ' Set a second ADO Stream instance for use as a results stream.   
    Set outStream = CreateObject("ADODB.Stream")  
    outStream.Open  
  
    ' Set dynamic properties used by the SQLXML ADO command instance.   
    cmd.Properties("XML Root").Value = "ROOT"  
    cmd.Properties("Output Encoding").Value = "UTF-8"  
  
    ' Connect the results stream to the command instance and execute the command.  
    cmd.Properties("Output Stream").Value = outStream  
    cmd.Execute , , 1024  
  
    ' Echo cropped/partial results to console.  
    WScript.Echo Left(outStream.ReadText, 1023)  
  
    inStream.Close  
    outStream.Close  
    ```  
  
2.  <span data-ttu-id="8393b-113">Mettez à jour les valeurs de script suivantes pour l'exemple que vous essayez de tester et votre environnement de test.</span><span class="sxs-lookup"><span data-stu-id="8393b-113">Update the following script values for the sample you are trying to test and your test environment.</span></span>  
  
    -   <span data-ttu-id="8393b-114">Recherchez "`@@FILE_NAME@@`" et remplacez-le par le nom de votre fichier modèle.</span><span class="sxs-lookup"><span data-stu-id="8393b-114">Find "`@@FILE_NAME@@`" and replace it with the name of your template file.</span></span>  
  
    -   <span data-ttu-id="8393b-115">Recherchez "`@@SERVER_NAME@@`" et remplacez-le par le nom de votre instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (par exemple, "`(local)`" si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s'exécute localement).</span><span class="sxs-lookup"><span data-stu-id="8393b-115">Find "`@@SERVER_NAME@@`" and replace it with the name of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (for example, "`(local)`" if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running locally).</span></span>  
  
    -   <span data-ttu-id="8393b-116">Recherchez "`@@DATABASE_NAME@@`" et remplacez-le par le nom de la base de données (par exemple "`AdventureWorks2012`" ou "`tempdb`").</span><span class="sxs-lookup"><span data-stu-id="8393b-116">Find "`@@DATABASE_NAME@@`" and replace it with the name of the database (for example, either "`AdventureWorks2012`" or "`tempdb`").</span></span>  
  
     <span data-ttu-id="8393b-117">Mettez à jour toute autre valeur mentionnée dans les instructions spécifiques pour l'exemple que vous essayez de recréer localement sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="8393b-117">Update any other values if mentioned in the specific instructions for the example you are attempting to recreate locally on your computer.</span></span>  
  
3.  <span data-ttu-id="8393b-118">Enregistrez le fichier et fermez-le.</span><span class="sxs-lookup"><span data-stu-id="8393b-118">Save the file and close it.</span></span>  
  
4.  <span data-ttu-id="8393b-119">Vérifiez que vous avez créé tous les fichiers supplémentaires, tels que des modèles ou des schémas XML qui font partie de l'exemple que vous essayez de recréer localement sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="8393b-119">Verify that you have created any additional files, such as XML templates or schemas that are part of the sample you are attempting to recreate locally on your computer.</span></span> <span data-ttu-id="8393b-120">Ces fichiers doivent se trouver dans le répertoire où vous avez enregistré le fichier script de test (Sqlxml4test.vbs).</span><span class="sxs-lookup"><span data-stu-id="8393b-120">These files should be located in the same directory where you have saved the test script file (Sqlxml4test.vbs).</span></span>  
  
5.  <span data-ttu-id="8393b-121">Suivez les instructions dans la section suivante pour savoir comment utiliser le script de test SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="8393b-121">Follow the instructions in the next section for how to use the SQLXML 4.0 test script.</span></span>  
  
## <a name="using-the-sqlxml-40-test-script"></a><span data-ttu-id="8393b-122">Utilisation du script de test SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="8393b-122">Using the SQLXML 4.0 Test Script</span></span>  
 <span data-ttu-id="8393b-123">La procédure suivante décrit comment utiliser les fichiers Sqlxml4test.vbs pour tester les exemples de requêtes fournis dans cette documentation.</span><span class="sxs-lookup"><span data-stu-id="8393b-123">The following procedure describes how to use the Sqlxml4test.vbs files to test the example queries provided in this documentation.</span></span>  
  
#### <a name="to-use-the-sqlxml-40-query-tester"></a><span data-ttu-id="8393b-124">Pour utiliser le testeur de requêtes SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="8393b-124">To use the SQLXML 4.0 query tester</span></span>  
  
1.  <span data-ttu-id="8393b-125">Vérifiez que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client est installé, comme suit :</span><span class="sxs-lookup"><span data-stu-id="8393b-125">Verify that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client is installed, as follows:</span></span>  
  
    1.  <span data-ttu-id="8393b-126">Dans le menu **Démarrer** , pointez sur **paramètres**, puis cliquez sur **panneau**de configuration.</span><span class="sxs-lookup"><span data-stu-id="8393b-126">From the **Start** menu, point to **Settings**, and then click **Control Panel**.</span></span>  
  
    2.  <span data-ttu-id="8393b-127">Dans le panneau de configuration, ouvrez **Ajout/suppression de programmes** .</span><span class="sxs-lookup"><span data-stu-id="8393b-127">In Control Panel, open **Add or Remove Programs**</span></span>  
  
    3.  <span data-ttu-id="8393b-128">Dans la liste des programmes actuellement installés, vérifiez que **Microsoft SQL Server Native Client** apparaît dans la liste.</span><span class="sxs-lookup"><span data-stu-id="8393b-128">In the list of currently installed programs, verify that **Microsoft SQL Server Native Client** appears in the list.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="8393b-129">Si vous devez installer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, consultez [installation de SQL Server Native Client](../native-client/applications/installing-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="8393b-129">If you need to install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, see [Installing SQL Server Native Client](../native-client/applications/installing-sql-server-native-client.md).</span></span>  
  
2.  <span data-ttu-id="8393b-130">Vérifiez que MDAC 2.6 ou version ultérieure est installée sur l'ordinateur client.</span><span class="sxs-lookup"><span data-stu-id="8393b-130">Verify that the version of MDAC installed for the client computer is 2.6 or later.</span></span> <span data-ttu-id="8393b-131">Si vous avez besoin de vérifier les informations de version MDAC, vous pouvez utiliser l’outil de vérification de composant MDAC, fourni en téléchargement gratuit à partir du site Web de Microsoft [https://www.microsoft.com/](https://www.microsoft.com/) .</span><span class="sxs-lookup"><span data-stu-id="8393b-131">If you need to verify MDAC version information, you can use the MDAC Component Checker tool, which is provided as free download from the Microsoft Web site [https://www.microsoft.com/](https://www.microsoft.com/).</span></span> <span data-ttu-id="8393b-132">Pour plus d’informations, recherchez « MDAC Component Checker » sur le site Web de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8393b-132">For more information, search on "MDAC Component Checker" on the Microsoft Web site.</span></span>  
  
3.  <span data-ttu-id="8393b-133">Exécutez le script.</span><span class="sxs-lookup"><span data-stu-id="8393b-133">Execute the script.</span></span>  
  
     <span data-ttu-id="8393b-134">Vous pouvez exécuter le fichier VBScript à la ligne de commande à l'aide de Cscript.exe ou en double-cliquant sur le fichier Sqlxml4test.vbs pour appeler l'environnement d'exécution de scripts WSH (Windows Script Host) (WScript.exe).</span><span class="sxs-lookup"><span data-stu-id="8393b-134">You can execute the VBScript file either at the command line using Cscript.exe or by double-clicking Sqlxml4test.vbs file to invoke the Windows Script Host (WScript.exe).</span></span>  
  
     <span data-ttu-id="8393b-135">Lorsqu'il est exécuté, le script doit afficher un message pour vous alerter que l'exécution du script peut prendre quelques instants avant de retourner et d'afficher les résultats de la requête en tant que sortie de script.</span><span class="sxs-lookup"><span data-stu-id="8393b-135">When executed, the script should display a message to alert you that the script might take a few moments to execute before returning and displaying query results as script output.</span></span> <span data-ttu-id="8393b-136">Quand la sortie s'affiche, comparez son contenu aux résultats attendus pour l'exemple.</span><span class="sxs-lookup"><span data-stu-id="8393b-136">When the output appears, compare its contents to the expected results for the sample.</span></span>  
  
  
