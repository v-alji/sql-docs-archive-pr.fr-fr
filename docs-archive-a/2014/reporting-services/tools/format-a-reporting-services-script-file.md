---
title: Mettre en forme un fichier de scripts Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- scripts [Reporting Services], formats
- formats [Reporting Services], script files
ms.assetid: 85a207dd-4e0f-4d40-a41e-0c75f65d719c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c98a2f6561c3242fec34f7ca11c8304286ccebae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700727"
---
# <a name="format-a-reporting-services-script-file"></a><span data-ttu-id="cca2f-102">Formater un fichier de script Reporting Services</span><span class="sxs-lookup"><span data-stu-id="cca2f-102">Format a Reporting Services Script File</span></span>
  <span data-ttu-id="cca2f-103">Un script [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] est un fichier de code [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET, écrit par rapport au proxy développé sur le service WSDL (Web Service Description Langage), qui définit l'API SOAP Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="cca2f-103">A [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] script is a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET code file, written against a proxy that is built on Web Service Description Language (WSDL), which defines the Reporting Services SOAP API.</span></span> <span data-ttu-id="cca2f-104">Un fichier de script est stocké comme fichier texte Unicode ou UTF-8 avec l'extension .rss.</span><span class="sxs-lookup"><span data-stu-id="cca2f-104">A script file is stored as a Unicode or UTF-8 text file with the extension .rss.</span></span>  
  
 <span data-ttu-id="cca2f-105">Le fichier de script agit comme un module [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] et peut contenir des procédures définies par l'utilisateur et des variables au niveau du module.</span><span class="sxs-lookup"><span data-stu-id="cca2f-105">The script file acts as a [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] module and can contain user-defined procedures and module-level variables.</span></span> <span data-ttu-id="cca2f-106">Pour que le fichier de script exécute avec succès, il doit contenir une procédure Main.</span><span class="sxs-lookup"><span data-stu-id="cca2f-106">For the script file to run successfully, it must contain a Main procedure.</span></span> <span data-ttu-id="cca2f-107">La procédure Main est la première procédure accédée lorsque votre fichier de script s'exécute.</span><span class="sxs-lookup"><span data-stu-id="cca2f-107">The Main procedure is the first procedure that is accessed when your script file runs.</span></span> <span data-ttu-id="cca2f-108">Cette procédure Main représente l'emplacement où vous pouvez ajouter vos opérations de service Web et exécuter vos sous-procédures définies par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cca2f-108">Main is where you can add your Web service operations and run your user defined subprocedures.</span></span> <span data-ttu-id="cca2f-109">L'exemple de code suivant crée une procédure Main :</span><span class="sxs-lookup"><span data-stu-id="cca2f-109">The following code creates a Main procedure:</span></span>  
  
```  
Public Sub Main()  
    ' Your code goes here.  
End Sub  
```  
  
 <span data-ttu-id="cca2f-110">L’environnement de script se connecte automatiquement au serveur de rapports, crée la classe proxy web et génère une variable de référence (*rs*) à l’objet proxy de service web.</span><span class="sxs-lookup"><span data-stu-id="cca2f-110">The script environment automatically connects to the report server, creates the Web proxy class, and generates a reference variable (*rs*) to the Web service proxy object.</span></span> <span data-ttu-id="cca2f-111">Les instructions individuelles que vous créez ont uniquement besoin de faire référence à la variable de niveau module *rs* pour effectuer les opérations de service web qui sont disponibles dans la bibliothèque de service web.</span><span class="sxs-lookup"><span data-stu-id="cca2f-111">Individual statements that you create need only refer to the *rs* module-level variable to perform any of the Web service operations that are available in the Web service library.</span></span> <span data-ttu-id="cca2f-112">Le code [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] suivant appelle la méthode <xref:ReportService2010.ReportingService2010.ListChildren%2A> du service web à partir d’un fichier de script :</span><span class="sxs-lookup"><span data-stu-id="cca2f-112">The following [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] code calls the Web service <xref:ReportService2010.ReportingService2010.ListChildren%2A> method from within a script file:</span></span>  
  
```  
Public Sub Main()  
    Dim items() As CatalogItem  
    items = rs.ListChildren("/", True)  
  
    Dim item As CatalogItem  
    For Each item In items  
        Console.WriteLine(item.Name)  
    Next item  
End Sub   
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cca2f-113">Les informations d'identification de l'utilisateur sont gérées par l'environnement de script et transmises à travers les arguments d'invite de commandes au moyen de RS.exe.</span><span class="sxs-lookup"><span data-stu-id="cca2f-113">User credentials are managed by the script environment and passed through command prompt arguments through the use of RS.exe.</span></span> <span data-ttu-id="cca2f-114">Bien que vous puissiez utiliser la variable *rs* pour définir l’authentification du service web, nous vous recommandons d’utiliser l’environnement de script.</span><span class="sxs-lookup"><span data-stu-id="cca2f-114">Although you can use the *rs* variable to set the authentication of the Web service, it is recommended that you use the script environment.</span></span> <span data-ttu-id="cca2f-115">Vous n'avez pas besoin d'authentifier le service Web dans le fichier de script lui-même.</span><span class="sxs-lookup"><span data-stu-id="cca2f-115">You do not need to authenticate the Web service in the script file itself.</span></span> <span data-ttu-id="cca2f-116">Pour plus d’informations sur l’authentification de l’environnement de script, consultez [Utilitaire RS.exe &#40;SSRS&#41;](rs-exe-utility-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="cca2f-116">For more information about authenticating the script environment, see [RS.exe Utility &#40;SSRS&#41;](rs-exe-utility-ssrs.md).</span></span>  
  
 <span data-ttu-id="cca2f-117">Vous ne déclarez pas d'espaces de noms dans le fichier de script.</span><span class="sxs-lookup"><span data-stu-id="cca2f-117">You do not declare namespaces within the script file.</span></span> <span data-ttu-id="cca2f-118">L’environnement de script met à votre disposition plusieurs espaces de noms [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] utiles : **System.Web.Services**, **System.Web.Services.Protocols**, **System.Xml** et **System.IO**.</span><span class="sxs-lookup"><span data-stu-id="cca2f-118">The scripting environment makes several useful [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] namespaces available to you: **System.Web.Services**, **System.Web.Services.Protocols**, **System.Xml**, and **System.IO**.</span></span>  
  
 <span data-ttu-id="cca2f-119">Pour des exemples de scripts, consultez [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889)(Exemples SQL Server Reporting Services).</span><span class="sxs-lookup"><span data-stu-id="cca2f-119">For script samples, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cca2f-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cca2f-120">See Also</span></span>  
 <span data-ttu-id="cca2f-121">[Service web Report Server](../report-server-web-service/report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="cca2f-121">[Report Server Web Service](../report-server-web-service/report-server-web-service.md) </span></span>  
 <span data-ttu-id="cca2f-122">[Informations techniques de référence &#40;SSRS&#41;](../technical-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="cca2f-122">[Technical Reference &#40;SSRS&#41;](../technical-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="cca2f-123">Utilitaire RS.exe &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="cca2f-123">RS.exe Utility &#40;SSRS&#41;</span></span>](rs-exe-utility-ssrs.md)  
  
  
