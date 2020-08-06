---
title: Création du proxy de service web | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Report Server Web service, proxies
- proxies [Reporting Services]
- XML Web service [Reporting Services], proxies
- Web service [Reporting Services], proxies
- Web references [Reporting Services]
ms.assetid: b1217843-8d3d-49f3-a0d2-d35b0db5b2df
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0d080b96fa29e906c044561a684d58275af9f61e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697499"
---
# <a name="creating-the-web-service-proxy"></a><span data-ttu-id="752e3-102">Création du proxy de service Web</span><span class="sxs-lookup"><span data-stu-id="752e3-102">Creating the Web Service Proxy</span></span>
  <span data-ttu-id="752e3-103">Un client et un service Web peuvent communiquer à l'aide de messages SOAP qui encapsulent les paramètres d'entrée et de sortie au format XML.</span><span class="sxs-lookup"><span data-stu-id="752e3-103">A client and a Web service can communicate using SOAP messages, which encapsulate the input and output parameters as XML.</span></span> <span data-ttu-id="752e3-104">Une classe proxy mappe des paramètres aux éléments XML puis envoie les messages SOAP sur un réseau.</span><span class="sxs-lookup"><span data-stu-id="752e3-104">A proxy class maps parameters to XML elements and then sends the SOAP messages over a network.</span></span> <span data-ttu-id="752e3-105">De cette manière, la classe proxy vous évite de devoir communiquer avec le service Web au niveau SOAP et vous permet d'appeler des méthodes de service Web dans tout environnement de développement qui prend en charge les proxies de service Web et SOAP.</span><span class="sxs-lookup"><span data-stu-id="752e3-105">In this way, the proxy class frees you from having to communicate with the Web service at the SOAP level and allows you to invoke Web service methods in any development environment that supports SOAP and Web service proxies.</span></span>  
  
 <span data-ttu-id="752e3-106">Il existe deux façons d’ajouter une classe proxy à votre projet de développement à l’aide de l' [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] : avec l’outil WSDL dans le [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] , et en ajoutant une référence Web dans [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="752e3-106">There are two ways to add a proxy class to your development project using the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]: with the WSDL tool in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], and by adding a Web reference in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="752e3-107">Les sections suivantes approfondissent ce sujet.</span><span class="sxs-lookup"><span data-stu-id="752e3-107">The following sections discuss this subject in further detail.</span></span>  
  
## <a name="adding-the-proxy-using-the-wsdl-tool"></a><span data-ttu-id="752e3-108">Ajout du proxy à l'aide de l'outil WSDL</span><span class="sxs-lookup"><span data-stu-id="752e3-108">Adding the Proxy Using the WSDL Tool</span></span>  
 <span data-ttu-id="752e3-109">Le Kit de développement logiciel (SDK) [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] inclut l'outil Web Services Description Language (Wsdl.exe) qui vous permet de générer un proxy de service Web pour une utilisation dans l'environnement de développement [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="752e3-109">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK includes the Web Services Description Language tool (Wsdl.exe), which enables you to generate a Web service proxy for use in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] development environment.</span></span> <span data-ttu-id="752e3-110">La méthode la plus courante pour créer un proxy client dans les langages qui prennent en charge des services Web (actuellement C# et [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] ) est d’utiliser l’outil Wsdl.</span><span class="sxs-lookup"><span data-stu-id="752e3-110">The most common way to create a client proxy in languages that support Web services (currently C# and [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) is to use the WSDL tool.</span></span>  
  
 <span data-ttu-id="752e3-111">**Pour ajouter une classe proxy à votre projet à l’aide de Wsdl.exe**</span><span class="sxs-lookup"><span data-stu-id="752e3-111">**To add a proxy class to your project using Wsdl.exe**</span></span>  
  
1.  <span data-ttu-id="752e3-112">À partir d'une invite de commandes, utilisez Wsdl.exe pour créer une classe proxy en spécifiant (au minimum) l'URL du service Web Report Server.</span><span class="sxs-lookup"><span data-stu-id="752e3-112">From a command prompt, use Wsdl.exe to create a proxy class, specifying (at a minimum) the URL to the Report Server Web service.</span></span>  
  
     <span data-ttu-id="752e3-113">Par exemple, l'instruction d'invite de commandes suivante spécifie une URL pour le point de terminaison de gestion du service Web Report Server :</span><span class="sxs-lookup"><span data-stu-id="752e3-113">For example, the following command prompt statement specifies a URL for the management endpoint of the Report Server Web service:</span></span>  
  
    ```  
    wsdl /language:CS /n:"Microsoft.SqlServer.ReportingServices2010" http://<Server Name>/reportserver/reportservice2010.asmx?wsdl  
    ```  
  
     <span data-ttu-id="752e3-114">L'outil WSDL accepte plusieurs arguments d'invite de commandes pour générer un proxy.</span><span class="sxs-lookup"><span data-stu-id="752e3-114">The WSDL tool accepts a number of command-prompt arguments for generating a proxy.</span></span> <span data-ttu-id="752e3-115">L'exemple précédent spécifie le langage C#, un espace de noms suggéré à utiliser dans le proxy (évite la collision de nom en présence de plusieurs points de terminaison de service Web), et génère un fichier C# appelé ReportingService2010.cs.</span><span class="sxs-lookup"><span data-stu-id="752e3-115">The preceding example specifies the language C#, a suggested namespace to use in the proxy (to prevent name collision if using more than one Web service endpoint), and generates a C# file called ReportingService2010.cs.</span></span> <span data-ttu-id="752e3-116">Si l'exemple avait spécifié [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], l'exemple aurait généré un fichier proxy avec le nom ReportingService2010.vb.</span><span class="sxs-lookup"><span data-stu-id="752e3-116">If the example had specified [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], the example would have generated a proxy file with the name ReportingService2010.vb.</span></span> <span data-ttu-id="752e3-117">Ce fichier est créé dans le répertoire à partir duquel vous exécutez la commande.</span><span class="sxs-lookup"><span data-stu-id="752e3-117">This file is created in the directory from which you run the command.</span></span>  
  
2.  <span data-ttu-id="752e3-118">Compilez la classe proxy dans un fichier d'assembly (avec l'extension .dll) et référencez-la dans votre projet ou ajoutez la classe comme un élément de projet.</span><span class="sxs-lookup"><span data-stu-id="752e3-118">Compile the proxy class into an assembly file (with the extension .dll) and reference it in your project, or add the class as a project item.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="752e3-119">Lorsque vous ajoutez manuellement une classe proxy à votre projet, vous devez ajouter une référence à System.Web.Services.dll.</span><span class="sxs-lookup"><span data-stu-id="752e3-119">When you add a proxy class to your project manually, you need to add a reference to System.Web.Services.dll.</span></span> <span data-ttu-id="752e3-120">Si vous ajoutez le proxy à l'aide d'une référence Web dans Visual Studio .NET, la référence est créée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="752e3-120">If you add the proxy using a Web reference in Visual Studio .NET, the reference is automatically created for you.</span></span> <span data-ttu-id="752e3-121">Pour plus d'informations, consultez « Ajout du proxy à l'aide d'une référence Web dans Visual Studio » plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="752e3-121">For more information, see "Adding the Proxy Using a Web Reference in Visual Studio" later in this topic.</span></span>  
  
     <span data-ttu-id="752e3-122">Après avoir ajouté la classe proxy comme un élément à votre projet, le fichier associé s'affiche dans l'Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="752e3-122">After you add the proxy class as an item to your project, the associated file appears in Solution Explorer.</span></span>  
  
3.  <span data-ttu-id="752e3-123">Pour appeler le service par programme, créez une instance de la classe proxy.</span><span class="sxs-lookup"><span data-stu-id="752e3-123">To call the service programmatically, create an instance of the proxy class.</span></span>  
  
     <span data-ttu-id="752e3-124">L'exemple de code suivant affiche la syntaxe permettant de créer une instance de la classe proxy <xref:ReportService2010.ReportingService2010> dans un projet :</span><span class="sxs-lookup"><span data-stu-id="752e3-124">The following code example shows the syntax for creating an instance of the <xref:ReportService2010.ReportingService2010> proxy class in a project:</span></span>  
  
```vb  
Dim service As New ReportingService2010()  
```  
  
```csharp  
ReportingService2010 service = new ReportingService2010();  
  
```  
  
 <span data-ttu-id="752e3-125">Pour plus d'informations sur l'outil Wsdl.exe, y compris sa syntaxe complète, consultez la rubrique « Web Services Description Language Tool » dans la documentation du Kit de développement logiciel (SDK) [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="752e3-125">For more information about the Wsdl.exe tool, including its full syntax, see "Web Services Description Language Tool" in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK documentation.</span></span> <span data-ttu-id="752e3-126">Pour une explication complète des proxies de service Web, consultez « Création d'un proxy de service Web XML » dans la documentation du Kit de développement logiciel (SDK) [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="752e3-126">For a full explanation of Web service proxies, see "Creating an XML Web Service Proxy" in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
## <a name="adding-the-proxy-using-a-web-reference-in-visual-studio"></a><span data-ttu-id="752e3-127">Ajout du proxy à l'aide d'une référence Web dans Visual Studio</span><span class="sxs-lookup"><span data-stu-id="752e3-127">Adding the Proxy Using a Web Reference in Visual Studio</span></span>  
 <span data-ttu-id="752e3-128">Une référence Web permet à un projet de faire appel à un ou plusieurs services Web</span><span class="sxs-lookup"><span data-stu-id="752e3-128">A Web reference enables a project to consume one or more Web services.</span></span> [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] <span data-ttu-id="752e3-129">permet aux utilisateurs d'ajouter des références de service Web aux projets en suivant quelques étapes simples.</span><span class="sxs-lookup"><span data-stu-id="752e3-129">enables users to add Web service references to projects by following a few simple steps.</span></span>  
  
 <span data-ttu-id="752e3-130">**Pour ajouter une référence web à un projet**</span><span class="sxs-lookup"><span data-stu-id="752e3-130">**To add a Web reference to a project**</span></span>  
  
1.  <span data-ttu-id="752e3-131">Dans l’**Explorateur de solutions**, sélectionnez le projet qui fera appel au service web.</span><span class="sxs-lookup"><span data-stu-id="752e3-131">In **Solution Explorer**, select the project that will consume the Web service.</span></span>  
  
2.  <span data-ttu-id="752e3-132">Dans le menu **Projet**, cliquez sur **Ajouter une référence web**.</span><span class="sxs-lookup"><span data-stu-id="752e3-132">On the **Project** menu, click **Add Web Reference**.</span></span>  
  
     <span data-ttu-id="752e3-133">La boîte de dialogue **Ajouter une référence web** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="752e3-133">The **Add Web Reference** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="752e3-134">Dans le champ **URL**, entrez le chemin complet du service web Report Server.</span><span class="sxs-lookup"><span data-stu-id="752e3-134">In the **URL** field, enter the complete path to the Report Server Web service.</span></span>  
  
     <span data-ttu-id="752e3-135">Voici une URL simplifiée pour le point de terminaison d'exécution du rapport du service Web Report Server :</span><span class="sxs-lookup"><span data-stu-id="752e3-135">A simplified URL for the report execution endpoint of the Report Server Web service might look like this:</span></span>  
  
    ```  
    http://<Server Name>/reportserver/reportexecution2005.asmx  
    ```  
  
     <span data-ttu-id="752e3-136">L'URL contient le domaine de déploiement du service Web Report Server, le nom du dossier qui contient le service, et le nom du fichier de découverte pour le service.</span><span class="sxs-lookup"><span data-stu-id="752e3-136">The URL contains the domain in which the Report Server Web service is deployed, the name of the folder containing the service, and the name of the discovery file for the service.</span></span> <span data-ttu-id="752e3-137">Pour obtenir une description complète des différents éléments de l’URL, consultez [Accès à l’API SOAP](../accessing-the-soap-api.md).</span><span class="sxs-lookup"><span data-stu-id="752e3-137">For a complete description of the different URL elements, see [Accessing the SOAP API](../accessing-the-soap-api.md).</span></span>  
  
     <span data-ttu-id="752e3-138">Une description des méthodes et propriétés fournies par le service Web apparaît dans le volet Navigateur sur la gauche.</span><span class="sxs-lookup"><span data-stu-id="752e3-138">A description of the methods and properties provided by the Web service appears in the Browser pane on the left.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="752e3-139">Pour plus d’informations sur les éléments associés au service web Report Server, consultez [Méthodes du service web Report Server](../methods/report-server-web-service-methods.md).</span><span class="sxs-lookup"><span data-stu-id="752e3-139">For more information about the items associated with the Report Server Web service, see [Report Server Web Service Methods](../methods/report-server-web-service-methods.md).</span></span>  
  
4.  <span data-ttu-id="752e3-140">Vérifiez que votre projet peut utiliser le service Web Report Server, et que vous avez l'autorisation appropriée d'accéder au serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="752e3-140">Verify that your project can use the Report Server Web service, and that you have appropriate permission to access the report server.</span></span>  
  
5.  <span data-ttu-id="752e3-141">Dans le champ **Nom de la référence web**, entrez un nom que vous utiliserez dans votre code pour accéder par programmation au service web Report Server sélectionné.</span><span class="sxs-lookup"><span data-stu-id="752e3-141">In the **Web reference name** field, enter a name that you will use in your code to access the Report Server Web service programmatically.</span></span>  
  
6.  <span data-ttu-id="752e3-142">Sélectionnez le bouton **Ajouter une référence** pour créer une référence dans votre application destinée au service web.</span><span class="sxs-lookup"><span data-stu-id="752e3-142">Select the **Add Reference** button to create a reference in your application to the Web service.</span></span>  
  
     <span data-ttu-id="752e3-143">La nouvelle référence est affichée dans l’**Explorateur de solutions** sous le nœud Références web du projet actif ; elle est nommée en fonction des informations spécifiées dans le champ **Nom de la référence web**.</span><span class="sxs-lookup"><span data-stu-id="752e3-143">The new reference appears in **Solution Explorer** under the Web References node for the active project, named as specified in the **Web reference name** field.</span></span>  
  
7.  <span data-ttu-id="752e3-144">Dans l’**Explorateur de solutions**, développez le dossier Références web pour noter l’espace de noms des classes de la référence web qui sont disponibles pour les éléments de votre projet.</span><span class="sxs-lookup"><span data-stu-id="752e3-144">In **Solution Explorer**, expand the Web References folder to note the namespace for the Web reference classes that are available to the items in your project.</span></span>  
  
     <span data-ttu-id="752e3-145">Après avoir ajouté une référence web à votre projet, les fichiers associés sont affichés dans un dossier au sein du dossier Références web de l’**Explorateur de solutions**.</span><span class="sxs-lookup"><span data-stu-id="752e3-145">After adding a Web reference to your project, the associated files are displayed in a folder within the Web References folder of **Solution Explorer**.</span></span>  
  
 <span data-ttu-id="752e3-146">Après avoir ajouté la référence Web, utilisez la syntaxe suivante pour créer une instance de la classe proxy :</span><span class="sxs-lookup"><span data-stu-id="752e3-146">After you add the Web reference, use the following syntax to create an instance of the proxy class:</span></span>  
  
```vb  
Dim rs As New myNamespace.myReferenceName.ReportExecutionService()  
rs.Url = "http://<Server Name>/reportserver/reportexecution2005.asmx?wsdl"  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
```  
  
```csharp  
myNamespace.myReferenceName.ReportExecutionService rs = new myNamespace.myReferenceName.ReportExecutionService();  
rs.Url = "http://<Server Name>/reportserver/reportexecution2005.asmx?wsdl"  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
  
```  
  
 <span data-ttu-id="752e3-147">Vous pouvez également ajouter une directive **using** (**Import** en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) à la référence de service web Report Server.</span><span class="sxs-lookup"><span data-stu-id="752e3-147">You can also add a **using** (**Import** in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) directive to the Report Server Web service reference.</span></span> <span data-ttu-id="752e3-148">Si vous utilisez cette directive, il n'est pas nécessaire de qualifier complètement les types dans l'espace de noms.</span><span class="sxs-lookup"><span data-stu-id="752e3-148">If you use this directive, you do not need to fully qualify the types in the namespace.</span></span> <span data-ttu-id="752e3-149">Pour cela, ajoutez le code suivant à votre fichier :</span><span class="sxs-lookup"><span data-stu-id="752e3-149">To do this, add the following code to your file:</span></span>  
  
```vb  
Import myNamespace.myReferenceName  
```  
  
```csharp  
using myNamespace.myReferenceName;  
```  
  
## <a name="see-also"></a><span data-ttu-id="752e3-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="752e3-150">See Also</span></span>  
 <span data-ttu-id="752e3-151">[Service web Report Server](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="752e3-151">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="752e3-152">[Création d’applications à l’aide du service web et du .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="752e3-152">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="752e3-153">Informations techniques de référence &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="752e3-153">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
