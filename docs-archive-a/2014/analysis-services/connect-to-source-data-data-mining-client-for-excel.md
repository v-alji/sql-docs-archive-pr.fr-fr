---
title: Se connecter aux données sources (client d’exploration de données pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- connections
ms.assetid: 548672ce-e403-4aca-b67a-c2c797f053dd
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4b4759d94043fdccacdf5b285de50697a18965e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602447"
---
# <a name="connect-to-source-data-data-mining-client-for-excel"></a><span data-ttu-id="d92a9-102">Connexion à une source de données (Client d'exploration de données pour Excel)</span><span class="sxs-lookup"><span data-stu-id="d92a9-102">Connect to Source Data (Data Mining Client for Excel)</span></span>
  <span data-ttu-id="d92a9-103">Cette rubrique décrit comment créer et utiliser les connexions utilisées pour stocker des modèles d'exploration de données et pour accéder aux données externes stockées dans [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d92a9-103">This topic describes how to create and use connections used for storing data mining models, and for accessing external data stored in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="d92a9-104">**Connexions d'exploration de données.**</span><span class="sxs-lookup"><span data-stu-id="d92a9-104">**Data mining connections.**</span></span> <span data-ttu-id="d92a9-105">La connexion initiale que vous créez lorsque vous lancez les compléments permet d'accéder aux algorithmes, d'analyser les données et de stocker les modèles et structures d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="d92a9-105">The initial connection that you create when you start the add-ins is used to access algorithms, analyze data, and store mining structure and models.</span></span>  
  
 <span data-ttu-id="d92a9-106">Une connexion à une instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] est nécessaire pour utiliser les outils de modélisation et de visualisation des compléments, car ces derniers dépendent d'algorithmes et de structures de données qui sont fournis par [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d92a9-106">A connection to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] is required to use the modeling and visualization tools in the add-ins, because the add-ins depend on algorithms and data structures that are provided by [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="d92a9-107">**Connexions à des sources de données externes.**</span><span class="sxs-lookup"><span data-stu-id="d92a9-107">**Connections to external data sources.**</span></span> <span data-ttu-id="d92a9-108">Vous pouvez également créer des connexions à des données externes lorsque vous créez des modèles ou enregistrez les résultats.</span><span class="sxs-lookup"><span data-stu-id="d92a9-108">You can also create connections to external data as you are building models or saving the results.</span></span> <span data-ttu-id="d92a9-109">Par exemple, vous pouvez créer un modèle d'exploration de données sur un serveur, puis exécuter une requête de prédiction par rapport au modèle d'exploration de données à l'aide de données stockées dans une autre instance d'[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], dans un tableau de données Excel, ou dans une source de données externes telle que [!INCLUDE[msCoName](../includes/msconame-md.md)] Access.</span><span class="sxs-lookup"><span data-stu-id="d92a9-109">For example, you can create a data mining model on one server, and then perform a prediction query against the data mining model by using data stored in another instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], in an Excel data table, or in an external data source such as [!INCLUDE[msCoName](../includes/msconame-md.md)] Access.</span></span> <span data-ttu-id="d92a9-110">À chaque fois que vous accédez à une nouvelle source de données, le système vous demande de créer une connexion à l'aide d'une boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d92a9-110">Each time that you access a new data source, you will be prompted to create a connection by using a dialog box.</span></span>  
  
##  <a name="prerequisites"></a><a name="bkmk_prereq2"></a> <span data-ttu-id="d92a9-111">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="d92a9-111">Prerequisites</span></span>  
 <span data-ttu-id="d92a9-112">Cette version des compléments nécessite que votre instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] soit SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="d92a9-112">This version of the add-ins requires that your instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] be SQL Server 2012.</span></span> <span data-ttu-id="d92a9-113">Une version séparée des compléments est disponible si vous souhaitez vous connecter à une version antérieure d'[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d92a9-113">A separate version of the add-ins is available if you want to connect to an earlier version of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="d92a9-114">Il existe des versions des compléments qui prennent en charge SQL Server 2005, SQL Server 2008 et SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="d92a9-114">There are versions of the add-ins that support SQL Server 2005, SQL Server 2008, and SQL Server 2008 R2.</span></span>  
  
 <span data-ttu-id="d92a9-115">Pour vous connecter à une base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], vous devez disposer des autorisations d'accès au serveur de base de données.</span><span class="sxs-lookup"><span data-stu-id="d92a9-115">To connect to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, you must have permissions to access the database server.</span></span> <span data-ttu-id="d92a9-116">De plus, les sessions d'exploration de données doivent être activées, et vous devez disposer des autorisations de lecture ou de lecture/écriture sur des objets de base de données stockés sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="d92a9-116">Moreover, data mining sessions must be enabled, and you must have read or read/write permissions on database objects stored on the server.</span></span>  
  
##  <a name="creating-data-mining-server-connections"></a><a name="bkmk_connect"></a><span data-ttu-id="d92a9-117">Création de connexions au serveur d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="d92a9-117">Creating Data Mining Server Connections</span></span>  
 <span data-ttu-id="d92a9-118">Le groupe **connexions** dans le client d’exploration de données pour Excel et les outils d’analyse de table pour Excel fournit des outils pour gérer les connexions à une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d92a9-118">The **Connections** group in the Data Mining Client for Excel and the Table Analysis Tools for Excel provides tools for managing connections to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="d92a9-119">Vous pouvez créer la connexion lorsque vous installez le complément, ou vous pouvez ajouter une connexion par la suite.</span><span class="sxs-lookup"><span data-stu-id="d92a9-119">You can create the connection when you install the add-in, or you can add a connection later.</span></span>  
  
-   <span data-ttu-id="d92a9-120">Vous pouvez créer plusieurs connexions et les modifier à tout moment, sauf si vous est en train de créer ou d'interroger un modèle.</span><span class="sxs-lookup"><span data-stu-id="d92a9-120">You can create multiple connections, and change connections at any time, unless you are in the process of creating or querying a model.</span></span>  
  
     <span data-ttu-id="d92a9-121">Ne modifiez pas ou ne désactivez pas une connexion lors du traitement d'un modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="d92a9-121">Do not change or close a connection when a data mining model is being processed.</span></span> <span data-ttu-id="d92a9-122">Le modèle d'exploration de données peut perdre des données ou devenir inutilisable.</span><span class="sxs-lookup"><span data-stu-id="d92a9-122">The data mining model might lose data, or the model might become unusable.</span></span>  
  
-   <span data-ttu-id="d92a9-123">Une seule connexion peut être active à un moment donné.</span><span class="sxs-lookup"><span data-stu-id="d92a9-123">Only one connection can be active at a particular time.</span></span>  
  
### <a name="connections-in-the-excel-add-ins"></a><span data-ttu-id="d92a9-124">Connexions dans les compléments Excel</span><span class="sxs-lookup"><span data-stu-id="d92a9-124">Connections in the Excel Add-ins</span></span>  
 <span data-ttu-id="d92a9-125">Le groupe **connexions** dans le client d’exploration de données pour Excel et les outils d’analyse de table pour Excel est l’emplacement où vous gérez les connexions à une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d92a9-125">The **Connections** group in the Data Mining Client for Excel and the Table Analysis Tools for Excel is where you manage connections to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
##### <a name="create-a-new-server-connection-in-the-excel-add-ins"></a><span data-ttu-id="d92a9-126">Créer une nouvelle connexion au serveur dans les compléments Excel</span><span class="sxs-lookup"><span data-stu-id="d92a9-126">Create a new server connection in the Excel add-ins</span></span>  
  
1.  <span data-ttu-id="d92a9-127">Cliquez sur le bouton **connexion** dans le ruban **analyse** ou **exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="d92a9-127">Click the **Connection** button on the **Analyze** or **Data Mining** ribbon.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d92a9-128">Le texte du bouton indique si une connexion existe.</span><span class="sxs-lookup"><span data-stu-id="d92a9-128">The text of the button indicates if a connection exists.</span></span> <span data-ttu-id="d92a9-129">Quand aucune connexion n’a été établie dans la feuille de calcul, le bouton contient le texte « \<No connection> . » Si une connexion a déjà été établie dans le classeur, le nom de cette connexion s’affiche dans le bouton.</span><span class="sxs-lookup"><span data-stu-id="d92a9-129">When no connection has been made in the worksheet, the button contains the text "\<No connection>." If a connection was previously made in the workbook, the name of that connection appears in the button.</span></span>  
  
2.  <span data-ttu-id="d92a9-130">Dans la boîte de dialogue **Analysis Services les connexions** , cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d92a9-130">In the **Analysis Services Connections** dialog box, click **New**.</span></span>  
  
3.  <span data-ttu-id="d92a9-131">Dans la boîte de dialogue **nouvelle connexion Analysis Services** , tapez le nom du serveur.</span><span class="sxs-lookup"><span data-stu-id="d92a9-131">In the **New Analysis Services Connection** dialog box, type the name of the server.</span></span>  
  
4.  <span data-ttu-id="d92a9-132">Spécifiez la méthode d'authentification.</span><span class="sxs-lookup"><span data-stu-id="d92a9-132">Specify the authentication method.</span></span>  
  
5.  <span data-ttu-id="d92a9-133">Sélectionnez une base de données dans la liste déroulante **nom du catalogue** .</span><span class="sxs-lookup"><span data-stu-id="d92a9-133">Select a database from the **Catalog name** drop-down list.</span></span> <span data-ttu-id="d92a9-134">Si aucune base de données n’existe sur l’instance, sélectionnez **(par défaut)**.</span><span class="sxs-lookup"><span data-stu-id="d92a9-134">If no database exists on the instance, select **(default)**.</span></span>  
  
6.  <span data-ttu-id="d92a9-135">Tapez un nom convivial pour la connexion.</span><span class="sxs-lookup"><span data-stu-id="d92a9-135">Type a friendly name for the connection.</span></span>  
  
7.  <span data-ttu-id="d92a9-136">Cliquez sur **tester la connexion** pour vérifier que le serveur et la base de données sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="d92a9-136">Click **Test Connection** to verify that the server and database are available.</span></span>  
  
8.  <span data-ttu-id="d92a9-137">Cliquez sur **OK**, puis sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="d92a9-137">Click **OK**, and then click **Close**.</span></span>  
  
### <a name="connections-using-a-web-service"></a><span data-ttu-id="d92a9-138">Connexions à l'aide d'un service Web</span><span class="sxs-lookup"><span data-stu-id="d92a9-138">Connections using a Web Service</span></span>  
 <span data-ttu-id="d92a9-139">Si vous utilisez une architecture de client léger pour permettre l’exploration des [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cubes et des données, vous pouvez également configurer une connexion à un [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] serveur via des services Web.</span><span class="sxs-lookup"><span data-stu-id="d92a9-139">If you are using a thin-client architecture to enable browsing of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cubes and data, you can also configure a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server through Web services.</span></span> <span data-ttu-id="d92a9-140">Pour obtenir des informations sur la manière de définir un client Web, consultez la documentation en ligne de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d92a9-140">For information about how to define a Web-based client, see [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="d92a9-141">Si vous avez accès à un serveur qui a été configuré pour des services Web, vous pouvez spécifier le type de connexion lorsque vous créez celle-ci pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="d92a9-141">If you have access to a server that has been configured for Web services, you can specify the connection type when you first create the connection.</span></span>  
  
##### <a name="create-an-http-connection-to-analysis-services"></a><span data-ttu-id="d92a9-142">Créer une connexion HTTP à Analysis Services</span><span class="sxs-lookup"><span data-stu-id="d92a9-142">Create an HTTP connection to Analysis Services</span></span>  
  
1.  <span data-ttu-id="d92a9-143">Ouvrez la boîte **de dialogue Nouvelle connexion Analysis Services** .</span><span class="sxs-lookup"><span data-stu-id="d92a9-143">Open the **New Analysis Services Connection** dialog box.</span></span>  
  
2.  <span data-ttu-id="d92a9-144">Pour le nom du serveur, tapez http:// suivi de l'URL affecté au serveur [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d92a9-144">For the server name, type http:// followed by the URL assigned to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server.</span></span>  
  
3.  <span data-ttu-id="d92a9-145">Tapez le nom d'utilisateur et le mot de passe qui sont nécessaires pour accéder au service Web.</span><span class="sxs-lookup"><span data-stu-id="d92a9-145">Type the user name and the password that is required to access the Web service.</span></span>  
  
### <a name="connections-in-the-visio-add-in"></a><span data-ttu-id="d92a9-146">Connexions dans le complément Visio</span><span class="sxs-lookup"><span data-stu-id="d92a9-146">Connections in the Visio Add-In</span></span>  
 <span data-ttu-id="d92a9-147">Contrairement à Excel, Visio ne fournit pas un ruban outil et il n'y a pas de boutons destinés à la création ou au contrôle des connexions.</span><span class="sxs-lookup"><span data-stu-id="d92a9-147">Unlike Excel, Visio does not provide a tool ribbon, and there are no buttons specifically for creating or monitoring connections.</span></span> <span data-ttu-id="d92a9-148">En revanche, la connexion de données est créée lorsque vous choisissez une forme d'exploration de données pour la première fois et que vous la déposez sur une page Visio.</span><span class="sxs-lookup"><span data-stu-id="d92a9-148">Instead, the data connection is created when you first select a data mining shape and drop it onto a Visio page.</span></span> <span data-ttu-id="d92a9-149">Un Assistant vous invitera à sélectionner le modèle pour la forme et à définir d'autres options.</span><span class="sxs-lookup"><span data-stu-id="d92a9-149">A wizard will prompt you to select the model for the shape and to set other options.</span></span>  
  
 <span data-ttu-id="d92a9-150">Si vous avez déjà utilisé une connexion à une [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] source de données dans Excel, ces connexions sont répertoriées comme sources de données possibles à partir desquelles sélectionner.</span><span class="sxs-lookup"><span data-stu-id="d92a9-150">If you have previously used a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source in Excel, these connections are listed as possible data sources from which to select.</span></span>  
  
##### <a name="create-a-connection-for-a-visio-shape"></a><span data-ttu-id="d92a9-151">Créer une connexion pour une forme Visio</span><span class="sxs-lookup"><span data-stu-id="d92a9-151">Create a connection for a Visio shape</span></span>  
  
1.  <span data-ttu-id="d92a9-152">Ouvrez le modèle d'exploration de données et sélectionnez une des formes d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="d92a9-152">Open the Data Mining Template, and select one of the data mining shapes.</span></span>  
  
2.  <span data-ttu-id="d92a9-153">Effectuez un glisser-déplacer de la forme vers une page vide.</span><span class="sxs-lookup"><span data-stu-id="d92a9-153">Drag and drop the shape to a blank page.</span></span>  
  
3.  <span data-ttu-id="d92a9-154">Dans la boîte de dialogue **Sélectionner une source de données** , sélectionnez une source de données dans la liste ou cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d92a9-154">In the **Select a data source** dialog box, select a data source from the list, or click **New**.</span></span>  
  
4.  <span data-ttu-id="d92a9-155">Si vous sélectionnez **nouveau**, suivez la procédure décrite précédemment pour spécifier un nom de serveur et de catalogue, ou pour vous connecter par le biais d’un service Web.</span><span class="sxs-lookup"><span data-stu-id="d92a9-155">If you select **New**, follow the procedure that is described earlier to specify a server and catalog name, or to connect through a Web service.</span></span>  
  
##  <a name="changing-connections"></a><a name="bkmk_change"></a><span data-ttu-id="d92a9-156">Modification des connexions</span><span class="sxs-lookup"><span data-stu-id="d92a9-156">Changing Connections</span></span>  
 <span data-ttu-id="d92a9-157">Vous pouvez créer plusieurs connexions dans la même feuille de calcul mais une seule connexion peut être active à la fois.</span><span class="sxs-lookup"><span data-stu-id="d92a9-157">You can create multiple connections in the same worksheet, but only one connection can be active at a time.</span></span> <span data-ttu-id="d92a9-158">Le nom de la connexion actuelle est affiché dans le bouton de **connexion** .</span><span class="sxs-lookup"><span data-stu-id="d92a9-158">The name of the current connection is displayed in the **Connection** button.</span></span>  
  
 <span data-ttu-id="d92a9-159">Dans le client d’exploration de données pour Excel, vous pouvez également vérifier la chaîne de connexion et l’état de la connexion actuelle en cliquant sur **trace** , puis sur **connexion actuelle**.</span><span class="sxs-lookup"><span data-stu-id="d92a9-159">In the Data Mining Client for Excel, you can also verify the connection string and status for the current connection by clicking **Trace** and then clicking **Current Connection**.</span></span>  
  
#### <a name="use-a-different-server-connection"></a><span data-ttu-id="d92a9-160">Utiliser une connexion différente à un serveur</span><span class="sxs-lookup"><span data-stu-id="d92a9-160">Use a different server connection</span></span>  
  
1.  <span data-ttu-id="d92a9-161">Cliquez sur **connexion**.</span><span class="sxs-lookup"><span data-stu-id="d92a9-161">Click **Connection**.</span></span>  
  
2.  <span data-ttu-id="d92a9-162">Dans le volet **connexions Analysis Services** , sélectionnez une connexion dans la liste **autres connexions** , puis cliquez sur **mettre en cours**.</span><span class="sxs-lookup"><span data-stu-id="d92a9-162">In the **Analysis Services Connections** pane, select a connection from the **Other Connections** list, and click **Make Current**.</span></span>  
  
3.  <span data-ttu-id="d92a9-163">Cliquez sur **tester la connexion** pour vérifier que la connexion est disponible.</span><span class="sxs-lookup"><span data-stu-id="d92a9-163">Click **Test Connection** to verify that the connection is available.</span></span>  
  
 <span data-ttu-id="d92a9-164">Au terme du traitement d'un modèle d'exploration de données, les résultats sont stockés localement et les données ne subissent aucun impact si vous interrompez la connexion à un serveur pour vous connecter à un autre serveur.</span><span class="sxs-lookup"><span data-stu-id="d92a9-164">After a mining model has finished processing, the results are stored locally, and there is no effect on the data if you close the connection to one server and then connect to another server.</span></span> <span data-ttu-id="d92a9-165">Cependant, il est recommandé d'éviter de changer les connexions ou de perdre la connexion pendant le traitement d'un modèle d'exploration de données, vous risquez d'endommager les données.</span><span class="sxs-lookup"><span data-stu-id="d92a9-165">However, you should avoid changing connections or losing the connection when a data mining model is being processed, because this could corrupt data.</span></span>  
  
#### <a name="modify-an-existing-server-connection"></a><span data-ttu-id="d92a9-166">Modifier une connexion à un serveur existante</span><span class="sxs-lookup"><span data-stu-id="d92a9-166">Modify an existing server connection</span></span>  
  
1.  <span data-ttu-id="d92a9-167">Vous ne pouvez pas modifier une connexion existante ; si vous voulez vous connecter à une base de données ou à un serveur différent, vous devez créer une nouvelle connexion.</span><span class="sxs-lookup"><span data-stu-id="d92a9-167">You cannot modify an existing connection; if you want to connect to a different database or a different server, you should create a new connection.</span></span>  
  
2.  <span data-ttu-id="d92a9-168">Si vous devez modifier la chaîne de connexion afin d'augmenter le délai de requête ou ajouter d'autres paramètres spécifiques à l'instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], il est possible de modifier le fichier .dmc où la chaîne de connexion est stockée.</span><span class="sxs-lookup"><span data-stu-id="d92a9-168">If you must modify the connection string to increase the query timeout or add other parameters specific to your instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], one option is to edit the .dmc file, where the connection string is stored.</span></span>  
  
     <span data-ttu-id="d92a9-169">\<drive:>\Utilisateurs \\<\> complément d’exploration de données myusername \AppData\Local\Microsoft\Data</span><span class="sxs-lookup"><span data-stu-id="d92a9-169">\<drive:>\Users\\<myusername\>\AppData\Local\Microsoft\Data Mining Add-in</span></span>  
  
##  <a name="connecting-to-external-data-sources"></a><a name="bkmk_extconnections"></a><span data-ttu-id="d92a9-170">Connexion à des sources de données externes</span><span class="sxs-lookup"><span data-stu-id="d92a9-170">Connecting to External Data Sources</span></span>  
 <span data-ttu-id="d92a9-171">Tandis que les outils du ruban **analyser** fonctionnent exclusivement avec les données dans Excel, les outils du ruban **exploration de données** vous permettent de vous connecter directement à des sources de données externes à utiliser comme entrées pour votre modèle ou pour l’échantillonnage.</span><span class="sxs-lookup"><span data-stu-id="d92a9-171">Whereas the tools in the **Analyze** ribbon work exclusively with data in Excel, the tools in the **Data Mining** ribbon let you connect directly to external data sources to use as inputs for your model, or for sampling.</span></span>  
  
 <span data-ttu-id="d92a9-172">Les outils suivants de ces compléments prennent en charge l'utilisation de données externes pour l'exploration de données :</span><span class="sxs-lookup"><span data-stu-id="d92a9-172">The following tools in these add-ins support use of external data for data mining:</span></span>  
  
-   [<span data-ttu-id="d92a9-173">Exemples de données &#40;SQL Server des compléments d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="d92a9-173">Sample Data &#40;SQL Server Data Mining Add-ins&#41;</span></span>](sample-data-sql-server-data-mining-add-ins.md)  
  
-   [<span data-ttu-id="d92a9-174">Assistant classification &#40;compléments d’exploration de données pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="d92a9-174">Classify Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](classify-wizard-data-mining-add-ins-for-excel.md)  
  
-   [<span data-ttu-id="d92a9-175">Assistant estimation &#40;des compléments d’exploration de données pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="d92a9-175">Estimate Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](estimate-wizard-data-mining-add-ins-for-excel.md)  
  
-   [<span data-ttu-id="d92a9-176">Assistant de cluster &#40;des compléments d’exploration de données pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="d92a9-176">Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](cluster-wizard-data-mining-add-ins-for-excel.md)  
  
-   [<span data-ttu-id="d92a9-177">Assistant Prévision &#40;des compléments d’exploration de données pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="d92a9-177">Forecast Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](forecast-wizard-data-mining-add-ins-for-excel.md)  
  
-   [<span data-ttu-id="d92a9-178">Créer des &#40;de structure d’exploration de données SQL Server des compléments d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="d92a9-178">Create Mining Structure &#40;SQL Server Data Mining Add-ins&#41;</span></span>](create-mining-structure-sql-server-data-mining-add-ins.md)  
  
-   [<span data-ttu-id="d92a9-179">Graphique d’analyse de précision &#40;SQL Server les compléments d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="d92a9-179">Accuracy Chart &#40;SQL Server Data Mining Add-ins&#41;</span></span>](accuracy-chart-sql-server-data-mining-add-ins.md)  
  
-   [<span data-ttu-id="d92a9-180">Graphique des bénéfices &#40;les compléments d’exploration de données SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d92a9-180">Profit Chart &#40;SQL Server Data Mining Add-ins&#41;</span></span>](profit-chart-sql-server-data-mining-add-ins.md)  
  
-   [<span data-ttu-id="d92a9-181">&#40;de matrices de classification SQL Server des compléments d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="d92a9-181">Classification Matrix &#40;SQL Server Data Mining Add-ins&#41;</span></span>](classification-matrix-sql-server-data-mining-add-ins.md)  
  
### <a name="using-analysis-services-as-a-data-source"></a><span data-ttu-id="d92a9-182">Utilisation d'Analysis Services comme source de données</span><span class="sxs-lookup"><span data-stu-id="d92a9-182">Using Analysis Services as a Data Source</span></span>  
 <span data-ttu-id="d92a9-183">Vous ne pouvez pas accéder directement aux données stockées dans un modèle tabulaire ou un cube [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d92a9-183">You cannot directly access data stored in an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube or tabular model.</span></span> <span data-ttu-id="d92a9-184">À la place, créez dans Excel une connexion au serveur [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] et utilisez les données pour créer un modèle.</span><span class="sxs-lookup"><span data-stu-id="d92a9-184">Instead, create a connection in Excel to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server, and use the data to create a model.</span></span>  
  
### <a name="relational-data-sources"></a><span data-ttu-id="d92a9-185">Sources de données relationnelles</span><span class="sxs-lookup"><span data-stu-id="d92a9-185">Relational Data Sources</span></span>  
 <span data-ttu-id="d92a9-186">Si vous souhaitez utiliser des données d'une source relationnelle comme entrées à votre modèle, vous pouvez vous connecter aux versions suivantes de SQL Server :</span><span class="sxs-lookup"><span data-stu-id="d92a9-186">If you want to use data from a relational source as input to your model, you can connect to the following versions of SQL Server:</span></span>  
  
-   <span data-ttu-id="d92a9-187">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="d92a9-187">SQL Server 2008</span></span>  
  
-   <span data-ttu-id="d92a9-188">SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="d92a9-188">SQL Server 2008 R2</span></span>  
  
-   <span data-ttu-id="d92a9-189">SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="d92a9-189">SQL Server 2012</span></span>  
  
 <span data-ttu-id="d92a9-190">Vous pouvez également obtenir des données de toute autre source de données relationnelle prise en charge comme source de données par [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d92a9-190">You can also get data from any other relational data source that is supported as a data source by [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="d92a9-191">Pour plus d’informations sur les sources de données prises en charge, consultez [sources de données dans les modèles multidimensionnels](multidimensional-models/data-sources-in-multidimensional-models.md)</span><span class="sxs-lookup"><span data-stu-id="d92a9-191">For information about supported data sources, see [Data Sources in Multidimensional Models](multidimensional-models/data-sources-in-multidimensional-models.md)</span></span>  
  
 <span data-ttu-id="d92a9-192">Notez que les types de données suivants ne peuvent pas être utilisés pour l'exploration de données et généreront une erreur s'ils sont présent lorsque vous créez un modèle :</span><span class="sxs-lookup"><span data-stu-id="d92a9-192">Note that the following data types cannot be used for data mining and will result in an error if included when you build a model:</span></span>  
  
-   <span data-ttu-id="d92a9-193">ntext</span><span class="sxs-lookup"><span data-stu-id="d92a9-193">ntext</span></span>  
  
-   <span data-ttu-id="d92a9-194">binary</span><span class="sxs-lookup"><span data-stu-id="d92a9-194">binary</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d92a9-195">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d92a9-195">See Also</span></span>  
 [<span data-ttu-id="d92a9-196">Trace &#40;client d’exploration de données pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="d92a9-196">Trace &#40;Data Mining Client for Excel&#41;</span></span>](trace-data-mining-client-for-excel.md)  
  
  
