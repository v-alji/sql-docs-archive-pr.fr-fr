---
title: Utilisation de l’API SOAP dans une application web | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- SOAP [Reporting Services], Web applications
- impersonation [Reporting Services]
- user impersonation [Reporting Services]
- report servers [Reporting Services], SOAP
- Web applications [Reporting Services]
ms.assetid: e8ca4455-0dc3-4741-8872-3636114938ad
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e228f01915df633f50b23bf93e892446863c28ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696508"
---
# <a name="using-the-soap-api-in-a-web-application"></a><span data-ttu-id="d201d-102">Utilisation de l'API SOAP dans une application Web</span><span class="sxs-lookup"><span data-stu-id="d201d-102">Using the SOAP API in a Web Application</span></span>
  <span data-ttu-id="d201d-103">Vous pouvez accéder aux fonctionnalités complètes du serveur de rapports via l'API SOAP de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="d201d-103">You can access the full functionality of the report server through the Reporting Services SOAP API.</span></span> <span data-ttu-id="d201d-104">Étant donné qu'il s'agit d'un service Web, l'API SOAP est facilement accessible afin de fournir des fonctionnalités de création de rapports d'entreprise à vos applications de gestion personnalisées.</span><span class="sxs-lookup"><span data-stu-id="d201d-104">Because it's a Web service, the SOAP API can be easily accessed to provide enterprise reporting features to your custom business applications.</span></span> <span data-ttu-id="d201d-105">Vous accédez au service Web Report Server à partir d'une application Web à peu près de la même manière que vous accédez à l'API SOAP à partir d'une application [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="d201d-105">You access the Report Server Web service from a Web application in much the same way that you access the SOAP API from a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application.</span></span> <span data-ttu-id="d201d-106">À l’aide de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] , vous pouvez générer une classe proxy qui expose les propriétés et les méthodes du service Web Report Server et vous permet d’utiliser une infrastructure et des outils familiers pour créer des applications métier sur la [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] technologie.</span><span class="sxs-lookup"><span data-stu-id="d201d-106">Using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], you can generate a proxy class that exposes the properties and methods of the Report Server Web service and enables you to use a familiar infrastructure and tools to build business applications on [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] technology.</span></span>  
  
 <span data-ttu-id="d201d-107">Les fonctionnalités de gestion de rapports [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] sont tout aussi faciles d'accès à partir d'une application Web qu'à partir d'une application Windows.</span><span class="sxs-lookup"><span data-stu-id="d201d-107">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report management functionality is just as easily accessed from a Web application as from a Windows application.</span></span> <span data-ttu-id="d201d-108">À partir d'une application Web, vous pouvez ajouter et supprimer des éléments dans la base de données du serveur de rapports, définir la sécurité des éléments, modifier les éléments de la base de données du serveur de rapports, gérer la planification et la remise, etc.</span><span class="sxs-lookup"><span data-stu-id="d201d-108">From a Web application, you can add and remove items from the report server database, set item security, modify report server database items, manage scheduling and delivery, and more.</span></span>  
  
## <a name="enabling-impersonation"></a><span data-ttu-id="d201d-109">Activation de l'emprunt d'identité</span><span class="sxs-lookup"><span data-stu-id="d201d-109">Enabling Impersonation</span></span>  
 <span data-ttu-id="d201d-110">La première étape de la configuration de votre application Web consiste à activer l'emprunt d'identité à partir du client de service Web.</span><span class="sxs-lookup"><span data-stu-id="d201d-110">The first step in configuring your Web application is to enable impersonation from the Web service client.</span></span> <span data-ttu-id="d201d-111">Avec l'emprunt d'identité, les applications [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] peuvent s'exécuter avec l'identité du client au nom duquel elles s'exécutent.</span><span class="sxs-lookup"><span data-stu-id="d201d-111">With impersonation, [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] applications can execute with the identity of the client on whose behalf they are operating.</span></span> [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] <span data-ttu-id="d201d-112">compte sur les services Internet (IIS) de [!INCLUDE[msCoName](../../includes/msconame-md.md)] pour authentifier l'utilisateur et passer soit un jeton authentifié à l'application [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)], soit un jeton non authentifié en cas d'incapacité à authentifier l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d201d-112">relies on [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) to authenticate the user and either pass an authenticated token to the [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] application or, if unable to authenticate the user, pass an unauthenticated token.</span></span> <span data-ttu-id="d201d-113">Dans les deux cas, l'application [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] emprunte l'identité de n'importe quel jeton reçu si l'emprunt d'identité est activé.</span><span class="sxs-lookup"><span data-stu-id="d201d-113">In either case, the [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] application impersonates whichever token is received if impersonation is enabled.</span></span> <span data-ttu-id="d201d-114">Vous pouvez activer l'emprunt d'identité sur le client, en modifiant le fichier Web.config de l'application cliente comme suit :</span><span class="sxs-lookup"><span data-stu-id="d201d-114">You can enable impersonation on the client, by modifying the Web.config file of the client application as follows:</span></span>  
  
```  
<!-- Web.config file. -->  
<identity impersonate="true"/>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="d201d-115">L'emprunt d'identité est désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="d201d-115">Impersonation is disabled by default.</span></span>  
  
 <span data-ttu-id="d201d-116">Pour plus d’informations sur [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] l’emprunt d’identité, consultez la [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] documentation du kit de développement logiciel (SDK).</span><span class="sxs-lookup"><span data-stu-id="d201d-116">For more information about [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] impersonation, see the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
## <a name="managing-the-report-server-using-soap-api"></a><span data-ttu-id="d201d-117">Gestion du serveur de rapports à l'aide de l'API SOAP</span><span class="sxs-lookup"><span data-stu-id="d201d-117">Managing the Report Server using SOAP API</span></span>  
 <span data-ttu-id="d201d-118">Vous pouvez également utiliser votre application Web pour gérer un serveur de rapports et son contenu.</span><span class="sxs-lookup"><span data-stu-id="d201d-118">You can also use your Web application to manage a report server and its contents.</span></span> <span data-ttu-id="d201d-119">Le Gestionnaire de rapports, inclus dans [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], est un exemple d'application Web complètement créée à l'aide de [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] et de l'API SOAP de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="d201d-119">Report Manager, included with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], is an example of a Web application that is completely built using [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] and the Reporting Services SOAP API.</span></span> <span data-ttu-id="d201d-120">Vous pouvez ajouter les fonctionnalités de gestion de rapports du Gestionnaire de rapports à vos applications Web personnalisées.</span><span class="sxs-lookup"><span data-stu-id="d201d-120">You can add the report management functionality of Report Manager to your custom Web applications.</span></span> <span data-ttu-id="d201d-121">Par exemple, vous souhaiterez peut-être retourner une liste des rapports disponibles dans la base de données du serveur de rapports et les afficher dans un [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] `Listbox` contrôle pour permettre à vos utilisateurs de choisir.</span><span class="sxs-lookup"><span data-stu-id="d201d-121">For example, you might want to return a list of available reports in the report server database and display them in a [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] `Listbox` control for your users to choose from.</span></span> <span data-ttu-id="d201d-122">Le code suivant permet de se connecter à la base de données du serveur de rapports et de retourner la liste des éléments contenus dans la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="d201d-122">The following code connects to the report server database and returns a list of items in the report server database.</span></span> <span data-ttu-id="d201d-123">Les rapports disponibles sont alors ajoutés à un contrôle ListBox, lequel affiche le chemin d'accès de chaque rapport.</span><span class="sxs-lookup"><span data-stu-id="d201d-123">The available reports are then added to a Listbox control, which displays the path of each report.</span></span>  
  
```vb  
Private Sub Page_Load(sender As Object, e As System.EventArgs)  
   ' Create a Web service proxy object and set credentials  
   Dim rs As New ReportingService2005()  
   rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
  
   ' Return a list of catalog items in the report server database  
   Dim items As CatalogItem() = rs.ListChildren("/", True)  
  
   ' For each report, display the path of the report in a Listbox  
   Dim ci As CatalogItem  
   For Each ci In  items  
      If ci.Type = ItemTypeEnum.Report Then  
         catalogListBox.Items.Add(ci.Path)  
      End If  
   Next ci  
End Sub ' Page_Load   
```  
  
```csharp  
private void Page_Load(object sender, System.EventArgs e)  
{  
   // Create a Web service proxy object and set credentials  
   ReportingService2005 rs = new ReportingService2005();  
   rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
  
   // Return a list of catalog items in the report server database  
   CatalogItem[] items = rs.ListChildren("/", true);  
  
   // For each report, display the path of the report in a Listbox  
   foreach(CatalogItem ci in items)  
   {  
      if (ci.Type == ItemTypeEnum.Report)  
         catalogListBox.Items.Add(ci.Path);  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="d201d-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d201d-124">See Also</span></span>  
 <span data-ttu-id="d201d-125">[Création d’applications à l’aide du service web et du .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="d201d-125">[Building Applications Using the Web Service and the .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="d201d-126">[Intégration de Reporting Services dans des applications](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="d201d-126">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 <span data-ttu-id="d201d-127">[Gestionnaire de rapports &#40;SSRS en mode natif&#41;](../report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="d201d-127">[Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="d201d-128">Utilisation de l'API SOAP dans une application Windows</span><span class="sxs-lookup"><span data-stu-id="d201d-128">Using the SOAP API in a Windows Application</span></span>](integrating-reporting-services-using-soap-windows-application.md)  
  
  
