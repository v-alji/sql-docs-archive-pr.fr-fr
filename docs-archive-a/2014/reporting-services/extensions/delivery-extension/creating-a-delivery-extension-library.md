---
title: Création d’une bibliothèque d’extensions de remise | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], namespace assignments
- library [Reporting Services]
- assigning namespaces to extensions
ms.assetid: 63b32f93-4bab-4b07-bd72-39a47aca1cda
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c9891c2b0c1bb9c7d495b3ab1f8f2267ce04b79f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708931"
---
# <a name="creating-a-delivery-extension-library"></a><span data-ttu-id="d56f7-102">Création d'une bibliothèque d'extensions de remise</span><span class="sxs-lookup"><span data-stu-id="d56f7-102">Creating a Delivery Extension Library</span></span>
  <span data-ttu-id="d56f7-103">Chaque extension de remise [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] que vous créez doit être assignée à un espace de noms unique et intégrée à une bibliothèque ou à un fichier d'assembly.</span><span class="sxs-lookup"><span data-stu-id="d56f7-103">Each [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension you create should be assigned to a unique namespace and built into a library or assembly file.</span></span> <span data-ttu-id="d56f7-104">Le nom exact de l'espace de noms n'est pas important, mais il doit être unique et ne pas être partagé avec une autre extension.</span><span class="sxs-lookup"><span data-stu-id="d56f7-104">The exact name of the namespace is not important, but it must be unique and not shared with any other extension.</span></span> <span data-ttu-id="d56f7-105">Vous devez créer vos propres espaces de noms uniques pour les extensions de remise de votre société.</span><span class="sxs-lookup"><span data-stu-id="d56f7-105">You should create your own unique namespaces for your company's delivery extensions.</span></span>  
  
 <span data-ttu-id="d56f7-106">L'exemple suivant montre le début du code d'une extension de remise [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] qui utilise les espaces de noms contenant les interfaces de remise et toute classe utilitaire.</span><span class="sxs-lookup"><span data-stu-id="d56f7-106">The following example shows the code to begin a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension, which uses the namespaces that contain the delivery interfaces and any utility classes.</span></span>  
  
```vb  
Imports System  
Imports Microsoft.ReportingServices.Interfaces  
  
Namespace CompanyName.ExtensionName  
   ...  
```  
  
```csharp  
using System;  
using Microsoft.ReportingServices.Interfaces;  
  
namespace CompanyName.ExtensionName  
{  
   ...  
```  
  
 <span data-ttu-id="d56f7-107">Lors de la compilation d'une extension de remise [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], vous devez fournir au compilateur une référence au fichier Microsoft.ReportingServices.Interfaces.dll, car celui-ci contient les interfaces et les classes de l'extension de remise.</span><span class="sxs-lookup"><span data-stu-id="d56f7-107">When compiling a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension, you must supply to the compiler a reference to Microsoft.ReportingServices.Interfaces.dll, because the delivery extension interfaces and classes are contained there.</span></span> <span data-ttu-id="d56f7-108">L'espace de noms <xref:Microsoft.ReportingServices.Interfaces> est nécessaire pour implémenter l'interface <xref:Microsoft.ReportingServices.Interfaces.IExtension>, l'interface <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension>, ainsi que d'autres interfaces.</span><span class="sxs-lookup"><span data-stu-id="d56f7-108">The <xref:Microsoft.ReportingServices.Interfaces> namespace is needed to implement the <xref:Microsoft.ReportingServices.Interfaces.IExtension> interface, the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> interface, and more.</span></span> <span data-ttu-id="d56f7-109">Par exemple, si tous les fichiers contenant le code utilisé pour implémenter une extension de remise [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] écrite en C# sont réunis dans un répertoire unique portant l’extension .cs, la commande suivante est émise depuis ce répertoire pour compiler les fichiers stockés dans CompanyName.ExtensionName.dll.</span><span class="sxs-lookup"><span data-stu-id="d56f7-109">For example, if all the files containing the code to implement a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension written in C# were in a single directory with the extension .cs, the following command would be issued from that directory to compile the files stored in CompanyName.ExtensionName.dll.</span></span>  
  
```csharp  
csc /t:library /out:CompanyName.ExtensionName.dll *.cs /r:System.dll   
/r:Microsoft.ReportingServices.Interfaces.dll  
```  
  
 <span data-ttu-id="d56f7-110">L’exemple de code suivant affiche la commande utilisée pour les fichiers [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] avec l’extension .vb.</span><span class="sxs-lookup"><span data-stu-id="d56f7-110">The following code example shows the command that would be used for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] files with the extension .vb.</span></span>  
  
```vb  
vbc /t:library /out:CompanyName.ExtensionName.dll *.vb /r:System.dll   
/r:Microsoft.ReportingServices.Interfaces.dll  
```  
  
> [!NOTE]  
>  <span data-ttu-id="d56f7-111">Vous pouvez également concevoir, développer et générer votre extension de remise à l'aide de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d56f7-111">You can also design, develop, and build your delivery extension using [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="d56f7-112">Pour plus d'informations sur le développement des assemblys dans [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], consultez votre documentation [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d56f7-112">For more information about developing assemblies in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], see your [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d56f7-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d56f7-113">See Also</span></span>  
 <span data-ttu-id="d56f7-114">[Extensions Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="d56f7-114">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="d56f7-115">[Implémentation d’une extension de remise](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="d56f7-115">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="d56f7-116">Bibliothèque d'extensions Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d56f7-116">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
