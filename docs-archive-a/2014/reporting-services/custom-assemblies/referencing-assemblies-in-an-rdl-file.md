---
title: Référencement d’assemblys dans un fichier RDL | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- RDL [Reporting Services], referencing assemblies
- referencing custom assemblies
- custom assemblies [Reporting Services], referencing
- Report Definition Language, referencing assemblies
- report definition files [Reporting Services]
ms.assetid: 9a48e552-7d47-4243-9be1-894990c506d9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 14593717d2319d7d702fd0c414e0c24428006f51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696503"
---
# <a name="referencing-assemblies-in-an-rdl-file"></a><span data-ttu-id="23131-102">Référencement d'assemblys dans un Fichier RDL</span><span class="sxs-lookup"><span data-stu-id="23131-102">Referencing Assemblies in an RDL File</span></span>
  <span data-ttu-id="23131-103">Pour prendre en charge l’utilisation d’assemblys de code personnalisés dans les fichiers de définition de rapport, deux éléments RDL (Report Definition Language) sont inclus dans la spécification RDL : l’élément **CodeModules** et l’élément **Classes**.</span><span class="sxs-lookup"><span data-stu-id="23131-103">To support the use of custom code assemblies in report definition files, two Report Definition Language (RDL) elements are included in the RDL specification: the **CodeModules** element and the **Classes** element.</span></span>  
  
 <span data-ttu-id="23131-104">L’élément **CodeModules** vous permet de faire référence aux assemblys de code managé dans les expressions de rapport.</span><span class="sxs-lookup"><span data-stu-id="23131-104">The **CodeModules** element enables you to refer to managed code assemblies in report expressions.</span></span> <span data-ttu-id="23131-105">**CodeModules** est un élément de niveau supérieur qui contient la référence à l’assembly que vous utilisez dans vos fichiers de définition de rapport pour appeler des fonctions spécialisées.</span><span class="sxs-lookup"><span data-stu-id="23131-105">**CodeModules** is a top-level element that contains the reference to the assembly that you use in your report definition files to call specialized functions.</span></span> <span data-ttu-id="23131-106">Une entrée dans une définition de rapport qui prend en charge l'utilisation d'un assembly personnalisé peut ressembler aux éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="23131-106">An entry in a report definition that supports the use of a custom assembly might look like the following:</span></span>  
  
```  
<CodeModules>  
   <CodeModule>CurrencyConversion, Version=1.0.1363.31103, Culture=neutral, PublicKeyToken=null</CodeModule>  
</CodeModules>  
```  
  
 <span data-ttu-id="23131-107">Au lieu d’appeler <xref:System.Reflection.Assembly.Load%2A> de votre code personnalisé, enregistrez vos assemblys personnalisés en ajoutant manuellement des éléments **CodeModule** à votre fichier RDL ou en utilisant l’onglet **Références** de la boîte de dialogue **Propriétés de rapport**.</span><span class="sxs-lookup"><span data-stu-id="23131-107">Instead of calling <xref:System.Reflection.Assembly.Load%2A> from your custom code, register your custom assemblies by either manually adding **CodeModule** elements to your RDL file or by using the **References** tab of the **Report Properties** dialog.</span></span> <span data-ttu-id="23131-108">Pour plus d’informations, consultez [Code personnalisé et références d’assembly dans les expressions du Concepteur de rapports &#40;SSRS&#41;](../report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="23131-108">For more information, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](../report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
 <span data-ttu-id="23131-109">L’élément **Classes** prend en charge l’utilisation de membres d’instance dans une définition de rapport.</span><span class="sxs-lookup"><span data-stu-id="23131-109">The **Classes** element supports the use of instance members in a report definition.</span></span> <span data-ttu-id="23131-110">L’élément **Classes** est un élément de niveau supérieur qui contient une référence au nom de classe et un nom d’instance.</span><span class="sxs-lookup"><span data-stu-id="23131-110">**Classes** is a top-level element that contains a reference to the class name and an instance name.</span></span> <span data-ttu-id="23131-111">Une entrée dans une définition de rapport qui prend en charge l'utilisation de membres d'instance peut ressembler aux éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="23131-111">An entry in a report definition that supports the use of instance members might look like the following:</span></span>  
  
```  
<Classes>  
   <Class>  
      <ClassName>CurrencyConversion.DollarCurrencyConversion</ClassName>  
      <InstanceName>m_myDollarConversion</InstanceName>  
   </Class>  
</Classes>  
```  
  
 <span data-ttu-id="23131-112">Pour plus d’informations, consultez [Accès aux assemblys personnalisés par le biais d’expressions](accessing-custom-assemblies-through-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="23131-112">For more information, see [Accessing Custom Assemblies Through Expressions](accessing-custom-assemblies-through-expressions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23131-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="23131-113">See Also</span></span>  
 [<span data-ttu-id="23131-114">Utilisation d'assemblys personnalisés avec des rapports</span><span class="sxs-lookup"><span data-stu-id="23131-114">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
