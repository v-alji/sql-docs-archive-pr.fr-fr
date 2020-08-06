---
title: Ajouter du code à un rapport (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- code [Reporting Services]
- custom code [Reporting Services]
- expressions [Reporting Services], code
- adding code
- reports [Reporting Services], code
ms.assetid: 00ef8fc6-99fe-49b2-8a22-7eb475881dc4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c1964e69d00e1a27da29ce8cfb73b7bee1bece7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702487"
---
# <a name="add-code-to-a-report-ssrs"></a><span data-ttu-id="8745b-102">Ajouter du code à un rapport (SSRS)</span><span class="sxs-lookup"><span data-stu-id="8745b-102">Add Code to a Report (SSRS)</span></span>
  <span data-ttu-id="8745b-103">Dans toute expression, vous pouvez appeler votre propre code personnalisé.</span><span class="sxs-lookup"><span data-stu-id="8745b-103">In any expression, you can call your own custom code.</span></span> <span data-ttu-id="8745b-104">Vous pouvez fournir du code des deux manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="8745b-104">You can provide code in the following two ways:</span></span>  
  
-   <span data-ttu-id="8745b-105">Incorporez du code écrit en [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] directement dans votre rapport.</span><span class="sxs-lookup"><span data-stu-id="8745b-105">Embed code written in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] directly in your report.</span></span> <span data-ttu-id="8745b-106">Si votre code fait référence à un élément [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] qui n’est pas <xref:System.Math> ni <xref:System.Convert>, vous devez ajouter la référence au rapport.</span><span class="sxs-lookup"><span data-stu-id="8745b-106">If your code refers to a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] that is not <xref:System.Math> or <xref:System.Convert>, you must add the reference to the report.</span></span> <span data-ttu-id="8745b-107">Pour plus d’informations, consultez [Ajouter une référence d’assembly à un rapport &#40;SSRS&#41;](add-an-assembly-reference-to-a-report-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8745b-107">For more information, see [Add an Assembly Reference to a Report &#40;SSRS&#41;](add-an-assembly-reference-to-a-report-ssrs.md).</span></span> <span data-ttu-id="8745b-108">Pour plus d’informations sur les autres références au code possibles, consultez [Code personnalisé et références d’assembly dans les expressions du Concepteur de rapports &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8745b-108">For more information about other references you can make from your code, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
-   <span data-ttu-id="8745b-109">Fournissez un assembly de code personnalisé en utilisant le [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8745b-109">Provide a custom code assembly by using the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="8745b-110">Si vous fournissez un assembly personnalisé, vous devez l'installer à la fois sur l'ordinateur où vous créez le rapport et sur le serveur de rapports où vous affichez le rapport.</span><span class="sxs-lookup"><span data-stu-id="8745b-110">If you provide a custom assembly, you must install it on both the computer where you author the report and the report server where you view the report.</span></span> <span data-ttu-id="8745b-111">Pour plus d’informations, consultez [Utilisation d’assemblys personnalisés avec des rapports](../custom-assemblies/using-custom-assemblies-with-reports.md).</span><span class="sxs-lookup"><span data-stu-id="8745b-111">For more information, see [Using Custom Assemblies with Reports](../custom-assemblies/using-custom-assemblies-with-reports.md).</span></span>  
  
### <a name="to-add-embedded-code-to-a-report"></a><span data-ttu-id="8745b-112">Pour ajouter du code incorporé à un rapport</span><span class="sxs-lookup"><span data-stu-id="8745b-112">To add embedded code to a report</span></span>  
  
1.  <span data-ttu-id="8745b-113">En mode **Conception** , cliquez avec le bouton droit sur l’aire de conception à l’extérieur de la bordure du rapport et cliquez sur **Propriétés du rapport**.</span><span class="sxs-lookup"><span data-stu-id="8745b-113">In **Design** view, right-click the design surface outside the border of the report and click **Report Properties**.</span></span>  
  
2.  <span data-ttu-id="8745b-114">Cliquez sur **Code**.</span><span class="sxs-lookup"><span data-stu-id="8745b-114">Click **Code**.</span></span>  
  
3.  <span data-ttu-id="8745b-115">Dans **Code personnalisé**, tapez le code.</span><span class="sxs-lookup"><span data-stu-id="8745b-115">In **Custom code**, type the code.</span></span> <span data-ttu-id="8745b-116">Des erreurs de code génèrent des avertissements lorsque le rapport s'exécute.</span><span class="sxs-lookup"><span data-stu-id="8745b-116">Errors in the code produce warnings when the report runs.</span></span> <span data-ttu-id="8745b-117">L'exemple suivant crée une fonction personnalisée nommée `ChangeWord` qui remplace le mot «`Bike`» par «`Bicycle`».</span><span class="sxs-lookup"><span data-stu-id="8745b-117">The following example creates a custom function named `ChangeWord` that replaces the word "`Bike`" with "`Bicycle`".</span></span>  
  
    ```  
    Public Function ChangeWord(ByVal s As String) As String  
       Dim strBuilder As New System.Text.StringBuilder(s)  
       If s.Contains("Bike") Then  
          strBuilder.Replace("Bike", "Bicycle")  
          Return strBuilder.ToString()  
          Else : Return s  
       End If  
    End Function  
    ```  
  
4.  <span data-ttu-id="8745b-118">L'exemple suivant montre comment transmettre un champ de dataset nommé Category à cette fonction dans une expression :</span><span class="sxs-lookup"><span data-stu-id="8745b-118">The following example shows how to pass a dataset field named Category to this function in an expression:</span></span>  
  
    ```  
    =Code.ChangeWord(Fields!Category.Value)  
    ```  
  
     <span data-ttu-id="8745b-119">Si vous ajoutez cette expression à une cellule de table qui affiche des valeurs de catégorie, chaque fois que le mot « Bike » est dans le champ de dataset pour cette ligne, la valeur de cellule de table affiche à la place le mot « Bicycle ».</span><span class="sxs-lookup"><span data-stu-id="8745b-119">If you add this expression to a table cell that displays category values, whenever the word "Bike" is in the dataset field for that row, the table cell value displays the word "Bicycle" instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8745b-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8745b-120">See Also</span></span>  
 <span data-ttu-id="8745b-121">[Boîte de dialogue Propriétés du rapport, Code](../report-properties-dialog-box-code.md) </span><span class="sxs-lookup"><span data-stu-id="8745b-121">[Report Properties Dialog Box, Code](../report-properties-dialog-box-code.md) </span></span>  
 <span data-ttu-id="8745b-122">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8745b-122">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="8745b-123">Références à la collection Parameters &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8745b-123">Parameters Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-parameters-collection-references-report-builder.md)  
  
  
