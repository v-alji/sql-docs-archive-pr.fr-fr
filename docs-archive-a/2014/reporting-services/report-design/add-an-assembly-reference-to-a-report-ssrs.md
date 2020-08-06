---
title: Ajouter une référence d’assembly à un rapport (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- code [Reporting Services]
- custom assemblies [Reporting Services], referencing
- custom code [Reporting Services]
- adding assembly references
- assemblies [Reporting Services], references
ms.assetid: 0a03939e-48ce-4c30-b227-98533f2e0ccb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 23dda0c65589e55849f906c621e42ce70f0d7ab5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612172"
---
# <a name="add-an-assembly-reference-to-a-report-ssrs"></a><span data-ttu-id="234a3-102">Ajouter une référence d'assembly à un rapport (SSRS)</span><span class="sxs-lookup"><span data-stu-id="234a3-102">Add an Assembly Reference to a Report (SSRS)</span></span>
  <span data-ttu-id="234a3-103">Lorsque vous incorporez du code personnalisé qui contient des références aux classes [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] qui ne sont pas dans <xref:System.Math> ou <xref:System.Convert>, vous devez fournir une référence d’assembly au rapport afin que le processeur de rapports puisse résoudre les noms.</span><span class="sxs-lookup"><span data-stu-id="234a3-103">When you embed custom code that contains references to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] classes that are not in <xref:System.Math> or <xref:System.Convert>, you must provide an assembly reference to the report so that the report processor can resolve the names.</span></span> <span data-ttu-id="234a3-104">Pour plus d’informations, consultez [Ajouter du code à un rapport &#40;SSRS&#41;](add-code-to-a-report-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="234a3-104">For more information, see [Add Code to a Report &#40;SSRS&#41;](add-code-to-a-report-ssrs.md).</span></span>  
  
### <a name="to-add-an-assembly-reference-to-a-report"></a><span data-ttu-id="234a3-105">Pour ajouter une référence d'assembly à un rapport</span><span class="sxs-lookup"><span data-stu-id="234a3-105">To add an assembly reference to a report</span></span>  
  
1.  <span data-ttu-id="234a3-106">En mode **Conception** , cliquez avec le bouton droit sur l’aire de conception à l’extérieur de la bordure du rapport et cliquez sur **Propriétés du rapport**.</span><span class="sxs-lookup"><span data-stu-id="234a3-106">In **Design** view, right-click the design surface outside the border of the report and click **Report Properties**.</span></span>  
  
2.  <span data-ttu-id="234a3-107">Cliquez sur **Références**.</span><span class="sxs-lookup"><span data-stu-id="234a3-107">Click **References**.</span></span>  
  
3.  <span data-ttu-id="234a3-108">Dans **Ajouter ou supprimer des assemblys**, cliquez sur **Ajouter** , puis sur le bouton de sélection pour accéder à l’assembly.</span><span class="sxs-lookup"><span data-stu-id="234a3-108">In **Add or remove assemblies**, click **Add** and then click the ellipsis button to browse to the assembly.</span></span>  
  
4.  <span data-ttu-id="234a3-109">Dans **Ajouter ou supprimer des classes**, cliquez sur **Ajouter** , puis tapez le nom de la classe et fournissez le nom d’une instance à utiliser dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="234a3-109">In **Add or remove classes**, click **Add** and then type name of the class and provide an instance name to use within the report.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="234a3-110">Spécifiez une classe et un nom d'instance uniquement pour les membres basés sur une instance.</span><span class="sxs-lookup"><span data-stu-id="234a3-110">Specify a class and instance name only for instance-based members.</span></span> <span data-ttu-id="234a3-111">Ne spécifiez pas de membres statiques dans la liste **Classes** .</span><span class="sxs-lookup"><span data-stu-id="234a3-111">Do not specify static members in the **Classes** list.</span></span> <span data-ttu-id="234a3-112">Pour plus d’informations, consultez [Code personnalisé et références d’assembly dans les expressions du Concepteur de rapports &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="234a3-112">For more information, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="234a3-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="234a3-113">See Also</span></span>  
 <span data-ttu-id="234a3-114">[Utilisation d'assemblys personnalisés avec des rapports](../custom-assemblies/using-custom-assemblies-with-reports.md) </span><span class="sxs-lookup"><span data-stu-id="234a3-114">[Using Custom Assemblies with Reports](../custom-assemblies/using-custom-assemblies-with-reports.md) </span></span>  
 [<span data-ttu-id="234a3-115">Boîte de dialogue Propriétés du rapport, Références</span><span class="sxs-lookup"><span data-stu-id="234a3-115">Report Properties Dialog Box, References</span></span>](../report-properties-dialog-box-references.md)  
  
  
