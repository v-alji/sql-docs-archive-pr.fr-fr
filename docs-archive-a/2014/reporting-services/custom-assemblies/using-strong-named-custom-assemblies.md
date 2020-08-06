---
title: Utilisation d’assemblys personnalisés avec noms forts | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- AllowPartiallyTrustedCallersAttribute attribute
- strong-named custom assemblies [Reporting Services]
- strong names [Reporting Services]
- assemblies [Reporting Services], strong names
- custom assemblies [Reporting Services], strong-named
ms.assetid: ca9f19d7-6e86-46f2-b9ad-9bf807eaa52e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5e685ecda39e0487eb4b469920820fa6e4a10daa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600660"
---
# <a name="using-strong-named-custom-assemblies"></a><span data-ttu-id="f6ec9-102">Utilisation d'assemblys personnalisés avec noms forts</span><span class="sxs-lookup"><span data-stu-id="f6ec9-102">Using Strong-Named Custom Assemblies</span></span>
  <span data-ttu-id="f6ec9-103">Un nom fort identifie un assembly et comprend le nom de l'assembly, le numéro de version en quatre parties, les informations de culture (si fournies), une clé publique et une signature numérique stockée dans le manifeste de l'assembly.</span><span class="sxs-lookup"><span data-stu-id="f6ec9-103">A strong name identifies an assembly and includes the assembly's text name, four-part version number, culture information (if provided), a public key, and a digital signature stored in the assembly's manifest.</span></span> <span data-ttu-id="f6ec9-104">Un nom fort identifie de façon unique un assembly dans le Common Language Runtime (CLR) et garantit l'intégrité binaire.</span><span class="sxs-lookup"><span data-stu-id="f6ec9-104">A strong name uniquely identifies an assembly to the common language runtime (CLR) and ensures binary integrity.</span></span>  
  
## <a name="using-allowpartiallytrustedcallersattribute"></a><span data-ttu-id="f6ec9-105">Utilisation de l'attribut AllowPartiallyTrustedCallersAttribute</span><span class="sxs-lookup"><span data-stu-id="f6ec9-105">Using AllowPartiallyTrustedCallersAttribute</span></span>  
 <span data-ttu-id="f6ec9-106">Pour utiliser des assemblys avec noms forts avec des rapports, vous devez autoriser votre assembly avec nom fort à être appelé par du code d’un niveau de confiance partiel à l’aide de l’attribut **AllowPartiallyTrustedCallers** de l’assembly.</span><span class="sxs-lookup"><span data-stu-id="f6ec9-106">To use strong-named assemblies with reports, you must allow your strong-named assembly to be called by partially trusted code using the assembly's **AllowPartiallyTrustedCallers** attribute.</span></span> <span data-ttu-id="f6ec9-107">Vous pouvez utiliser l’attribut **AllowPartiallyTrustedCallersAttribute** pour autoriser des assemblys avec noms forts à être appelés par le Concepteur de rapports ou le serveur de rapports dans des expressions de rapport.</span><span class="sxs-lookup"><span data-stu-id="f6ec9-107">You can use **AllowPartiallyTrustedCallersAttribute** to allow strong-named assemblies to be called by Report Designer or the report server in report expressions.</span></span> <span data-ttu-id="f6ec9-108">Pour permettre à du code d'un niveau de confiance partiel d'appeler des assemblys avec noms forts, ajoutez l'attribut de niveau assembly suivant au fichier d'attribut de votre assembly.</span><span class="sxs-lookup"><span data-stu-id="f6ec9-108">To allow partially trusted code to call strong-named assemblies, add the following assembly-level attribute to your assembly attribute file.</span></span>  
  
```vb  
<assembly:AllowPartiallyTrustedCallers>  
```  
  
```csharp  
[assembly:AllowPartiallyTrustedCallers]  
```  
  
 <span data-ttu-id="f6ec9-109">L’attribut **AllowPartiallyTrustedCallersAttribute** est uniquement efficace quand il est appliqué au niveau de l’assembly par un assembly avec nom fort.</span><span class="sxs-lookup"><span data-stu-id="f6ec9-109">**AllowPartiallyTrustedCallersAttribute** is effective only when applied by a strong-named assembly at the assembly level.</span></span> <span data-ttu-id="f6ec9-110">Pour plus d’informations sur l’application d’attributs au niveau de l’assembly, consultez « application des attributs » dans la [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] documentation du kit de développement logiciel (SDK).</span><span class="sxs-lookup"><span data-stu-id="f6ec9-110">For more information about applying attributes at the assembly level, see "Applying Attributes" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="f6ec9-111">Quand l’attribut **AllowPartiallyTrustedCallersAttribute** est présent, les vérifications de sécurité **FullTrustLinkDemand** par défaut sont empêchées, ce qui rend l’assembly appelable à partir de tout autre assembly d’un niveau de confiance partiel.</span><span class="sxs-lookup"><span data-stu-id="f6ec9-111">When **AllowPartiallyTrustedCallersAttribute** is present, the default **FullTrustLinkDemand** security checks are prevented, making the assembly callable from any other partially trusted assembly.</span></span> <span data-ttu-id="f6ec9-112">Toutes les vérifications de sécurité, notamment les attributs de sécurité déclaratifs au niveau de la classe ou de la méthode, doivent être déclarées explicitement.</span><span class="sxs-lookup"><span data-stu-id="f6ec9-112">All security checks, including class-level or method-level declarative security attributes, must be explicitly stated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6ec9-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f6ec9-113">See Also</span></span>  
 [<span data-ttu-id="f6ec9-114">Utilisation d'assemblys personnalisés avec des rapports</span><span class="sxs-lookup"><span data-stu-id="f6ec9-114">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
