---
title: Énumération des packages disponibles par programmation | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- programmatically enumerate packages [SSIS]
- existence testing [Integration Services]
- enumerating packages [Integration Services]
ms.assetid: 254ec7ee-d3ff-4361-8995-46e9b9c4dc95
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 053f2e598b1cc18e68ee2182092188367ee7f10c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696916"
---
# <a name="enumerating-available-packages-programmatically"></a><span data-ttu-id="1364d-102">Énumération des packages disponibles par programme</span><span class="sxs-lookup"><span data-stu-id="1364d-102">Enumerating Available Packages Programmatically</span></span>
  <span data-ttu-id="1364d-103">Lors de l'utilisation de packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] par programme, vous pouvez déterminer si un package ou un dossier individuel existe, ou énumérer les packages enregistrés qui peuvent être chargés et exécutés.</span><span class="sxs-lookup"><span data-stu-id="1364d-103">As you work programmatically with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, you may want to determine whether an individual package or folder exists, or to enumerate the saved packages that are available to load and execute.</span></span> <span data-ttu-id="1364d-104">La classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> de l'espace de noms <xref:Microsoft.SqlServer.Dts.Runtime> fournit différentes méthodes pour répondre à ces impératifs.</span><span class="sxs-lookup"><span data-stu-id="1364d-104">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class of the <xref:Microsoft.SqlServer.Dts.Runtime> namespace provides a variety of methods to satisfy these requirements.</span></span>  
  
##  <a name="determining-whether-a-package-or-folder-exists"></a><a name="exists"></a> <span data-ttu-id="1364d-105">Détermination de l’existence d’un package ou dossier</span><span class="sxs-lookup"><span data-stu-id="1364d-105">Determining Whether a Package or Folder Exists</span></span>  
 <span data-ttu-id="1364d-106">Pour déterminer par programme si un package enregistré existe, appelez l'une des méthodes suivantes avant de tenter de le charger et l'exécuter :</span><span class="sxs-lookup"><span data-stu-id="1364d-106">To determine programmatically whether a saved package exists, call one of the following methods before attempting to load and run it:</span></span>  
  
|<span data-ttu-id="1364d-107">Emplacement de stockage</span><span class="sxs-lookup"><span data-stu-id="1364d-107">Storage Location</span></span>|<span data-ttu-id="1364d-108">Méthode à appeler</span><span class="sxs-lookup"><span data-stu-id="1364d-108">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="1364d-109">Magasin de packages SSIS</span><span class="sxs-lookup"><span data-stu-id="1364d-109">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.ExistsOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.ExistsOnSqlServer%2A>|  
  
 <span data-ttu-id="1364d-110">Pour déterminer par programme si un dossier existe avant de tenter de répertorier les packages stockés qu'il contient, appelez l'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="1364d-110">To determine programmatically whether a folder exists before attempting to list the packages stored in it, call one of the following methods:</span></span>  
  
|<span data-ttu-id="1364d-111">Emplacement de stockage</span><span class="sxs-lookup"><span data-stu-id="1364d-111">Storage Location</span></span>|<span data-ttu-id="1364d-112">Méthode à appeler</span><span class="sxs-lookup"><span data-stu-id="1364d-112">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="1364d-113">Magasin de packages SSIS</span><span class="sxs-lookup"><span data-stu-id="1364d-113">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.FolderExistsOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.FolderExistsOnSqlServer%2A>|  
  
 [<span data-ttu-id="1364d-114">Retour au début</span><span class="sxs-lookup"><span data-stu-id="1364d-114">Back to top</span></span>](#top)  
  
##  <a name="enumerating-available-packages"></a><a name="listing"></a> <span data-ttu-id="1364d-115">Énumération des packages disponibles</span><span class="sxs-lookup"><span data-stu-id="1364d-115">Enumerating Available Packages</span></span>  
 <span data-ttu-id="1364d-116">Pour obtenir par programme une liste des packages enregistrés, appelez l'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="1364d-116">To obtain a list of saved packages programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="1364d-117">Emplacement de stockage</span><span class="sxs-lookup"><span data-stu-id="1364d-117">Storage Location</span></span>|<span data-ttu-id="1364d-118">Méthode à appeler</span><span class="sxs-lookup"><span data-stu-id="1364d-118">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="1364d-119">Magasin de packages SSIS</span><span class="sxs-lookup"><span data-stu-id="1364d-119">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.GetDtsServerPackageInfos%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.GetPackageInfos%2A>|  
  
 <span data-ttu-id="1364d-120">Les exemples suivants sont des applications console qui illustrent l'utilisation de ces méthodes.</span><span class="sxs-lookup"><span data-stu-id="1364d-120">The following samples are console applications that demonstrate the use of these methods.</span></span>  
  
###  <a name="example-ssis-package-store"></a><a name="listing_store"></a> <span data-ttu-id="1364d-121">Exemple (magasin de packages SSIS)</span><span class="sxs-lookup"><span data-stu-id="1364d-121">Example (SSIS Package Store)</span></span>  
 <span data-ttu-id="1364d-122">Utilisez la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetDtsServerPackageInfos%2A> pour répertorier les packages stockés dans le magasin de packages SSIS.</span><span class="sxs-lookup"><span data-stu-id="1364d-122">Use the <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetDtsServerPackageInfos%2A> method to list packages stored in the SSIS Package Store.</span></span> <span data-ttu-id="1364d-123">File System et MSDB sont les emplacements de stockage par défaut gérés par le magasin de packages SSIS.</span><span class="sxs-lookup"><span data-stu-id="1364d-123">The default storage locations that are managed by the SSIS Package store are File System and MSDB.</span></span> <span data-ttu-id="1364d-124">Vous pouvez créer des dossiers logiques supplémentaires dans ces emplacements.</span><span class="sxs-lookup"><span data-stu-id="1364d-124">You can create additional logical folders within these locations.</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim sqlFolder As String  
    Dim sqlServer As String  
  
    Dim ssisApplication As Application  
    Dim sqlPackages As PackageInfos  
    Dim sqlPackage As PackageInfo  
  
    sqlServer = "."  
  
    ssisApplication = New Application()  
  
    ' Get packages stored in MSDB.  
    sqlFolder = "MSDB"  
    sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer)  
    If sqlPackages.Count > 0 Then  
      Console.WriteLine("Packages stored in MSDB:")  
      For Each sqlPackage In sqlPackages  
        Console.WriteLine(sqlPackage.Name)  
      Next  
      Console.WriteLine()  
    End If  
  
    ' Get packages stored in the File System.  
    sqlFolder = "File System"  
    sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer)  
    If sqlPackages.Count > 0 Then  
      Console.WriteLine("Packages stored in the File System:")  
      For Each sqlPackage In sqlPackages  
        Console.WriteLine(sqlPackage.Name)  
      Next  
    End If  
  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace EnumeratePackagesSSIS_CS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
  
      string sqlFolder;  
      string sqlServer;  
  
      Application ssisApplication;  
      PackageInfos sqlPackages;  
  
      sqlServer = ".";  
  
      ssisApplication = new Application();  
  
      // Get packages stored in MSDB.  
      sqlFolder = "MSDB";  
      sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer);  
      if (sqlPackages.Count > 0)  
      {  
        Console.WriteLine("Packages stored in MSDB:");  
        foreach (PackageInfo sqlPackage in sqlPackages)  
        {  
          Console.WriteLine(sqlPackage.Name);  
        }  
        Console.WriteLine();  
      }  
  
      // Get packages stored in the File System.  
      sqlFolder = "File System";  
      sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer);  
      if (sqlPackages.Count > 0)  
      {  
        Console.WriteLine("Packages stored in the File System:");  
        foreach (PackageInfo sqlPackage in sqlPackages)  
        {  
          Console.WriteLine(sqlPackage.Name);  
        }  
      }  
  
      Console.Read();  
  
    }  
  
  }  
  
}  
```  
  
 [<span data-ttu-id="1364d-125">Retour au début</span><span class="sxs-lookup"><span data-stu-id="1364d-125">Back to top</span></span>](#top)  
  
###  <a name="example-sql-server"></a><a name="listing_sql"></a> <span data-ttu-id="1364d-126">Exemple (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1364d-126">Example (SQL Server)</span></span>  
 <span data-ttu-id="1364d-127">Utilisez la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetPackageInfos%2A> pour répertorier les packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] stockés dans une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1364d-127">Use the <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetPackageInfos%2A> method to list [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages that are stored in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim sqlFolder As String  
    Dim sqlServer As String  
    Dim sqlUser As String  
    Dim sqlPassword As String  
  
    Dim ssisApplication As Application  
    Dim sqlPackages As PackageInfos  
    Dim sqlPackage As PackageInfo  
  
    sqlFolder = String.Empty  
    sqlServer = "(local)"  
    sqlUser = String.Empty  
    sqlPassword = String.Empty  
  
    ssisApplication = New Application()  
  
    sqlPackages = ssisApplication.GetPackageInfos(sqlFolder, sqlServer, sqlUser, sqlPassword)  
  
    For Each sqlPackage In sqlPackages  
      Console.WriteLine(sqlPackage.Name)  
    Next  
  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace EnumeratePackagesSql_CS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
  
      string sqlFolder;  
      string sqlServer;  
      string sqlUser;  
      string sqlPassword;  
  
      Application ssisApplication;  
      PackageInfos sqlPackages;  
  
      sqlFolder = String.Empty;  
      sqlServer = "(local)";  
      sqlUser = String.Empty;  
      sqlPassword = String.Empty;  
  
      ssisApplication = new Application();  
  
      sqlPackages = ssisApplication.GetPackageInfos(sqlFolder, sqlServer, sqlUser, sqlPassword);  
  
      foreach (PackageInfo sqlPackage in sqlPackages)  
      {  
        Console.WriteLine(sqlPackage.Name);  
      }  
  
      Console.Read();  
  
    }  
  }  
}  
```  
  
 [<span data-ttu-id="1364d-128">Retour au début</span><span class="sxs-lookup"><span data-stu-id="1364d-128">Back to top</span></span>](#top)  
  
<span data-ttu-id="1364d-129">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="1364d-129">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="1364d-130">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="1364d-130">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="1364d-131">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="1364d-131">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="1364d-132">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="1364d-132">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1364d-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1364d-133">See Also</span></span>  
 [<span data-ttu-id="1364d-134">Gestion de packages &#40;Service SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="1364d-134">Package Management &#40;SSIS Service&#41;</span></span>](../service/package-management-ssis-service.md)  
  
  
