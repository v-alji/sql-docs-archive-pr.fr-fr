---
title: Utilisation de l’API SOAP dans une application Windows | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- rendered reports [Reporting Services]
- Windows applications [Reporting Services]
- Windows Forms [Reporting Services]
- SOAP [Reporting Services], Windows applications
ms.assetid: e4804792-20cd-4df2-9257-fb958ff447b4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 115ce02da69a8adb2c7a3de4175e528f281eb2b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599806"
---
# <a name="using-the-soap-api-in-a-windows-application"></a><span data-ttu-id="0ffb9-102">Utilisation de l'API SOAP dans une application Windows</span><span class="sxs-lookup"><span data-stu-id="0ffb9-102">Using the SOAP API in a Windows Application</span></span>
  <span data-ttu-id="0ffb9-103">Vous pouvez accéder aux fonctionnalités complètes du serveur de rapports via l'API SOAP de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="0ffb9-103">You can access the full functionality of the report server through the Reporting Services SOAP API.</span></span> <span data-ttu-id="0ffb9-104">L'API SOAP est un service Web et, en tant que tel, est facilement accessible afin de fournir des fonctionnalités de création de rapports d'entreprise à vos applications de gestion personnalisées.</span><span class="sxs-lookup"><span data-stu-id="0ffb9-104">The SOAP API is a Web service and, as such, can be easily accessed to provide enterprise reporting features to your custom business applications.</span></span> <span data-ttu-id="0ffb9-105">Pour accéder au service Web dans une application Windows, il suffit d'écrire un code qui permet d'appeler le service.</span><span class="sxs-lookup"><span data-stu-id="0ffb9-105">You can access the Web service in a Windows application simply by writing code that makes calls to the service.</span></span> <span data-ttu-id="0ffb9-106">À l’aide de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] , vous pouvez générer une classe proxy qui expose les propriétés et les méthodes du service Web et vous permet d’utiliser une infrastructure et des outils familiers pour créer des applications métier basées sur la [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] technologie.</span><span class="sxs-lookup"><span data-stu-id="0ffb9-106">Using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], you can generate a proxy class that exposes the properties and methods of the Web service and enables you to use a familiar infrastructure and tools to build business applications built on [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] technology.</span></span>  
  
## <a name="integrating-report-management-functionality-using-windows-forms"></a><span data-ttu-id="0ffb9-107">Intégration de fonctionnalités de gestion de rapports à l'aide de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0ffb9-107">Integrating Report Management Functionality Using Windows Forms</span></span>  
 <span data-ttu-id="0ffb9-108">Contrairement à l'accès URL, l'API SOAP expose le jeu complet des fonctions de gestion qui sont disponibles via le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="0ffb9-108">Unlike URL access, the SOAP API exposes the complete set of management functions that are available through the report server.</span></span> <span data-ttu-id="0ffb9-109">Cela signifie que toutes les fonctionnalités d'administration du Gestionnaire de rapports sont disponibles pour les développeurs via SOAP.</span><span class="sxs-lookup"><span data-stu-id="0ffb9-109">This means that the entire administrative functionality of Report Manager is available to developers through SOAP.</span></span> <span data-ttu-id="0ffb9-110">Ainsi, vous pouvez développer un outil de gestion et d'administration complet à l'aide de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="0ffb9-110">As such, you can develop a complete management and administration tool using Windows Forms.</span></span> <span data-ttu-id="0ffb9-111">Par exemple, dans votre application Windows, vous pouvez souhaiter permettre à vos utilisateurs d'extraire le contenu de l'espace de noms du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="0ffb9-111">For example, in your Windows application, you might want to enable your users to retrieve the contents of the report server namespace.</span></span> <span data-ttu-id="0ffb9-112">Pour cela, vous pouvez utiliser la méthode <xref:ReportService2010.ReportingService2010.ListChildren%2A> du service Web pour répertorier tous les éléments contenus dans la base de données du serveur de rapports, puis utiliser un contrôle ListView, TreeView ou ComboBox pour présenter ces éléments à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0ffb9-112">To do this, you could use the Web service <xref:ReportService2010.ReportingService2010.ListChildren%2A> method to list all the items in the report server database and then use a Listview, Treeview, or Combobox control to display those items to your users.</span></span> <span data-ttu-id="0ffb9-113">Vous pouvez utiliser le code de service Web suivant pour extraire la liste actuelle des rapports disponibles dans le dossier Mes rapports d'un utilisateur lorsqu'il clique sur un bouton sur un formulaire :</span><span class="sxs-lookup"><span data-stu-id="0ffb9-113">The following Web service code might be used to retrieve the current list of available reports in a user's My Reports folder when a user clicks a button on a form:</span></span>  
  
```vb  
' Button click event that retrieves a list of reports from  
' the My Reports folder and displays them in a combo box  
Private Sub listReportsButton_Click(sender As Object, e As System.EventArgs)  
   ' Create a new Web service object and set credentials  
   ' to Windows Authentication  
   Dim rs As New ReportingService2010()  
   rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
  
   ' Return the list of items in My Reports  
   Dim items As CatalogItem() = rs.ListChildren("/Adventureworks 2008 Sample Reports", False)  
  
   Dim ci As CatalogItem  
   For Each ci In  items  
      ' If the item is a report, add it to   
      ' a combo box  
      If ci.TypeName = "Report" Then  
         catalogComboBox.Items.Add(ci.Name)  
      End If  
   Next ci  
End Sub 'listReportsButton_Click  
```  
  
```csharp  
// Button click event that retrieves a list of reports from  
// the My Reports folder and displays them in a combo box  
private void listReportsButton_Click(object sender, System.EventArgs e)  
{  
   // Create a new Web service object and set credentials  
   // to Windows Authentication  
   ReportingService2010 rs = new ReportingService2010();  
   rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
  
   // Return the list of items in My Reports  
   CatalogItem[] items = rs.ListChildren("/Adventureworks 2008 Sample Reports", false);  
  
   foreach (CatalogItem ci in items)  
   {  
      // If the item is a report, add it to   
      // a combo box  
      if (ci.TypeName == "Report")  
         catalogComboBox.Items.Add(ci.Name);  
   }  
}  
```  
  
 <span data-ttu-id="0ffb9-114">À partir de là, vous pouvez permettre aux utilisateurs de sélectionner le rapport dans la liste déroulante afin de le prévisualiser sur le formulaire à l'aide d'un contrôle de navigateur Web ou d'un contrôle Image.</span><span class="sxs-lookup"><span data-stu-id="0ffb9-114">From there, you might enable users to select the report from the Combo box and preview the report on the form either using a Web browser control or an image control.</span></span>  
  
## <a name="enabling-report-viewing-and-navigation-using-windows-forms"></a><span data-ttu-id="0ffb9-115">Activation de la consultation des rapports et de la navigation à l'aide de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0ffb9-115">Enabling Report Viewing and Navigation Using Windows Forms</span></span>  
 <span data-ttu-id="0ffb9-116">Il existe deux méthodes disponibles pour intégrer des rapports dans vos applications Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="0ffb9-116">There are two methods available for integrating reports into your Windows Forms applications.</span></span>  
  
 <span data-ttu-id="0ffb9-117">Vous pouvez utiliser l'API SOAP pour effectuer le rendu des rapports dans tous les formats de rendu pris en charge à l'aide de la méthode <xref:ReportExecution2005.ReportExecutionService.Render%2A>.</span><span class="sxs-lookup"><span data-stu-id="0ffb9-117">You can use the SOAP API to render reports to any of the supported rendering formats using the <xref:ReportExecution2005.ReportExecutionService.Render%2A> method.</span></span> <span data-ttu-id="0ffb9-118">Il existe de légers inconvénients à l'activation de la consultation des rapports et de la navigation via SOAP :</span><span class="sxs-lookup"><span data-stu-id="0ffb9-118">There are slight disadvantages to enabling report viewing and navigation through SOAP:</span></span>  
  
-   <span data-ttu-id="0ffb9-119">Vous ne pouvez pas tirer parti des fonctionnalités intégrées de la barre d'outils Rapports incluse dans la Visionneuse HTML via l'accès URL.</span><span class="sxs-lookup"><span data-stu-id="0ffb9-119">You cannot take advantage of the built-in functionality of the report toolbar that is included with the HTML Viewer through URL access.</span></span>  
  
-   <span data-ttu-id="0ffb9-120">Si vous effectuez un rendu au format HTML, vous devez effectuer le rendu des images ou ressources séparément en tant que flux supplémentaires à l'aide de la méthode <xref:ReportExecution2005.ReportExecutionService.RenderStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="0ffb9-120">If you render to HTML, you must separately render any images or resources as additional streams using the <xref:ReportExecution2005.ReportExecutionService.RenderStream%2A> method.</span></span>  
  
-   <span data-ttu-id="0ffb9-121">Il existe un léger avantage, en termes de performances, en faveur du rendu de rapports à l'aide de l'accès URL plutôt qu'à l'aide de l'API SOAP.</span><span class="sxs-lookup"><span data-stu-id="0ffb9-121">There is a slight performance advantage to rendering reports using URL access over using the SOAP API.</span></span>  
  
 <span data-ttu-id="0ffb9-122">Toutefois, la méthode <xref:ReportExecution2005.ReportExecutionService.Render%2A> de l'API SOAP peut être utilisée pour effectuer le rendu de rapports et les enregistrer sous divers formats de sortie par programme.</span><span class="sxs-lookup"><span data-stu-id="0ffb9-122">However, the <xref:ReportExecution2005.ReportExecutionService.Render%2A> method of the SOAP API can be used to render reports and save them to various output formats programmatically.</span></span> <span data-ttu-id="0ffb9-123">Il s'agit d'un avantage par rapport à l'accès URL, qui requiert l'intervention de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0ffb9-123">This is an advantage over URL access, which requires user interaction.</span></span> <span data-ttu-id="0ffb9-124">Lorsque vous effectuez le rendu d'un rapport à l'aide de la méthode <xref:ReportExecution2005.ReportExecutionService.Render%2A> de l'API SOAP, vous pouvez le faire dans tous les formats de sortie pris en charge.</span><span class="sxs-lookup"><span data-stu-id="0ffb9-124">When you render a report using the SOAP API <xref:ReportExecution2005.ReportExecutionService.Render%2A> method, you can render to any of the supported output formats.</span></span>  
  
 <span data-ttu-id="0ffb9-125">Vous pouvez également utiliser les contrôles ReportViewer à distribution librement inclus dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ffb9-125">You can also use the freely distributable ReportViewer controls that are included with [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)].</span></span> <span data-ttu-id="0ffb9-126">Les contrôles ReportViewer facilitent l'incorporation de fonctionnalités [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] dans les applications personnalisées.</span><span class="sxs-lookup"><span data-stu-id="0ffb9-126">The ReportViewer controls make it easy to embed [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] functionality into custom applications.</span></span> <span data-ttu-id="0ffb9-127">Les contrôles ReportViewer sont destinés aux développeurs qui souhaitent fournir des rapports prédéfinis et entièrement créés dans un ensemble de fonctionnalités d'une application (par exemple, une application de gestion de sites Web peut contenir des rapports qui comportent une analyse du parcours des internautes sur les sites Web de sociétés).</span><span class="sxs-lookup"><span data-stu-id="0ffb9-127">The ReportViewer controls are intended for developers who want to provide predesigned, fully authored reports as part of an application feature set (for example, a Web site management application might include reports that show click-stream analysis on company Web sites).</span></span> <span data-ttu-id="0ffb9-128">L'incorporation des contrôles dans une application offre une solution plus rationnelle que l'ajout de composants serveur [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] dans le déploiement de votre application.</span><span class="sxs-lookup"><span data-stu-id="0ffb9-128">Embedding the controls in an application provides a streamlined alternative to including the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] server components in your application deployment.</span></span> <span data-ttu-id="0ffb9-129">Les contrôles offrent les fonctionnalités des rapports sans la prise en charge de la création, de la publication, de la distribution et de la fourniture qu'offre [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ffb9-129">The controls provide report functionality, but without the additional report authoring, publication, or distribution and delivery support that you find in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0ffb9-130">Il existe deux versions des contrôles ReportViewer : une version est destinée aux applications clientes Windows, l'autre aux applications [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ffb9-130">There are two versions of the ReportViewer controls, one for rich Windows client applications and one for [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] applications.</span></span> <span data-ttu-id="0ffb9-131">Les contrôles prennent en charge les modes de traitement local et distant.</span><span class="sxs-lookup"><span data-stu-id="0ffb9-131">The controls support both local processing and remote processing modes.</span></span> <span data-ttu-id="0ffb9-132">En mode de traitement local, votre application fournit la définition de rapport et les datasets et déclenche le traitement des rapports. </span><span class="sxs-lookup"><span data-stu-id="0ffb9-132">In local processing mode, your application provides the report definition and datasets and triggers report processing.</span></span> <span data-ttu-id="0ffb9-133">En mode de traitement distant, la récupération des données et le traitement des rapports sont effectués sur le serveur de rapports et le contrôle est utilisé à des fins d'affichage et de navigation dans les rapports.</span><span class="sxs-lookup"><span data-stu-id="0ffb9-133">In remote processing mode, data retrieval and report processing happen on the report server and the control is used for display and report navigation.</span></span> <span data-ttu-id="0ffb9-134">Ce modèle vous permet de créer des applications puissantes à l'échelle d'un Bureau ou d'une entreprise.</span><span class="sxs-lookup"><span data-stu-id="0ffb9-134">This model allows you to build rich applications that can be scaled from desktop to the enterprise.</span></span>  
  
 <span data-ttu-id="0ffb9-135">Les contrôles ReportViewer sont décrits dans l'aide en ligne de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ffb9-135">ReportViewer controls are documented in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] online Help.</span></span> <span data-ttu-id="0ffb9-136">Pour plus d'informations, consultez la documentation produit de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ffb9-136">For more information, see the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] product documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ffb9-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0ffb9-137">See Also</span></span>  
 <span data-ttu-id="0ffb9-138">[Création d’applications à l’aide du service web et du .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="0ffb9-138">[Building Applications Using the Web Service and the .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="0ffb9-139">[Intégration de Reporting Services dans des applications](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="0ffb9-139">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 [<span data-ttu-id="0ffb9-140">Utilisation de l'API SOAP dans une application Web</span><span class="sxs-lookup"><span data-stu-id="0ffb9-140">Using the SOAP API in a Web Application</span></span>](integrating-reporting-services-using-soap-web-application.md)  
  
  
