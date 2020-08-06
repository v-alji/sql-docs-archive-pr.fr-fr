---
title: Représentation de la mesure calculée (tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 4cb9fea5-1616-467b-a539-d051e5833aea
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6b630fa075ae07b84e4886ad8bc115611da8e2d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612486"
---
# <a name="calculated-measure-representation-tabular"></a><span data-ttu-id="70ebf-102">Représentation de la mesure calculée (tabulaire)</span><span class="sxs-lookup"><span data-stu-id="70ebf-102">Calculated Measure Representation (Tabular)</span></span>
  <span data-ttu-id="70ebf-103">Une mesure calculée est une expression DAX nommée évaluée chaque fois qu'elle est utilisée.</span><span class="sxs-lookup"><span data-stu-id="70ebf-103">A calculated measure is a named DAX expression evaluated every time it is used.</span></span>  
  
## <a name="calculated-measure-representation"></a><span data-ttu-id="70ebf-104">Représentation de la mesure calculée</span><span class="sxs-lookup"><span data-stu-id="70ebf-104">Calculated Measure Representation</span></span>  
  
### <a name="calculated-measure-in-amo"></a><span data-ttu-id="70ebf-105">Mesure calculée dans AMO</span><span class="sxs-lookup"><span data-stu-id="70ebf-105">Calculated Measure in AMO</span></span>  
 <span data-ttu-id="70ebf-106">Lorsque vous utilisez AMO pour traiter une mesure calculée de modèle tabulaire, il existe une correspondance linéaire entre l'objet de mesure calculée logique et une mesure définie dans un objet <xref:Microsoft.AnalysisServices.Command> de l'objet <xref:Microsoft.AnalysisServices.MdxScript>.</span><span class="sxs-lookup"><span data-stu-id="70ebf-106">When using AMO to manage a tabular model calculated measure, there is a one-to-one match between the logical Calculated Measure object and a measure defined in a <xref:Microsoft.AnalysisServices.Command> object of the <xref:Microsoft.AnalysisServices.MdxScript> object.</span></span> <span data-ttu-id="70ebf-107">Chaque **mesure calculée** est définie en tant qu' `CREATE MEASURE` expression à l’intérieur d’un <xref:Microsoft.AnalysisServices.Command> objet et séparée par un point-virgule.</span><span class="sxs-lookup"><span data-stu-id="70ebf-107">Each **Calculated Measure** is defined as a `CREATE MEASURE` expression inside a <xref:Microsoft.AnalysisServices.Command> object and separated by a semicolon.</span></span> <span data-ttu-id="70ebf-108">Toutes les mesures calculées dans un modèle tabulaire correspondent à la chaîne `CREATE MEASURE` de collection dans un objet de commande dans un objet <xref:Microsoft.AnalysisServices.MdxScript>.</span><span class="sxs-lookup"><span data-stu-id="70ebf-108">All calculated measures in a tabular model correspond to the collection `CREATE MEASURE` string in one command object in a <xref:Microsoft.AnalysisServices.MdxScript> object.</span></span> <span data-ttu-id="70ebf-109">Pour chaque mesure calculée, il existe un mappage un-à-un avec un <xref:Microsoft.AnalysisServices.CalculationProperty>.</span><span class="sxs-lookup"><span data-stu-id="70ebf-109">For each calculated measure, there is one-to-one mapping with a <xref:Microsoft.AnalysisServices.CalculationProperty>.</span></span>  
  
 <span data-ttu-id="70ebf-110">L'extrait de code suivant montre comment créer une mesure calculée.</span><span class="sxs-lookup"><span data-stu-id="70ebf-110">The following code snippet shows how to create a calculated measure.</span></span>  
  
```  
  
private void addCalculatedMeasure(  
                   AMO.Cube modelCube  
                 , string cmTableName  
                 , string cmName  
                 , string newCalculatedMeasureExpression  
             )  
{  
    //Verify input requirements  
    if (string.IsNullOrEmpty(cmName) || string.IsNullOrWhiteSpace(cmName))  
    {  
        MessageBox.Show(String.Format("Calculated Measure name is not defined."), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
        return;  
    }  
    if (string.IsNullOrEmpty(newCalculatedMeasureExpression) || string.IsNullOrWhiteSpace(newCalculatedMeasureExpression))  
    {  
        MessageBox.Show(String.Format("Calculated Measure expression is not defined."), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
        return;  
    }  
  
    StringBuilder measuresCommand = new StringBuilder();  
  
    AMO.MdxScript mdxScript = modelCube.MdxScripts["MdxScript"];  
  
    //ToDo: Verify if measure already exits and ask user what wants to do next  
  
    if (mdxScript.Commands.Count == 1)  
    {  
        measuresCommand.AppendLine("-------------------------------------------------------------");  
        measuresCommand.AppendLine("-- Tabular Model measures command (do not modify manually) --");  
        measuresCommand.AppendLine("-------------------------------------------------------------");  
        measuresCommand.AppendLine();  
        measuresCommand.AppendLine();  
        mdxScript.Commands.Add(new AMO.Command(measuresCommand.ToString()));  
  
    }  
    else  
    {  
        measuresCommand.Append(mdxScript.Commands[1].Text);  
    }  
    measuresCommand.AppendLine(string.Format("CREATE MEASURE '{0}'[{1}]={2};", cmTableName, cmName, newCalculatedMeasureExpression));  
  
    mdxScript.Commands[1].Text = measuresCommand.ToString();  
  
    if (!mdxScript.CalculationProperties.Contains(cmName))  
    {  
        AMO.CalculationProperty cp = new AMO.CalculationProperty(cmName, AMO.CalculationType.Member);  
        cp.FormatString = ""; // ToDo: Get formatting attributes for the member  
        cp.Visible = true;  
        mdxScript.CalculationProperties.Add(cp);  
    }  
  
    try  
    {  
        modelCube.Update(AMO.UpdateOptions.ExpandFull, AMO.UpdateMode.UpdateOrCreate);  
        MessageBox.Show(String.Format("Calculated Measure successfully defined."), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Information);  
    }  
    catch (AMO.OperationException amoOpXp)  
    {  
        MessageBox.Show(String.Format("Calculated Measure expression contains syntax errors, or references undefined or missspelled elements.\nError message: {0}", amoOpXp.Message), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Warning);  
        return;  
    }  
    catch (AMO.AmoException amoXp)  
    {  
        MessageBox.Show(String.Format("AMO exception accessing the server.\nError message: {0}", amoXp.Message), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Warning);  
        return;  
    }  
    catch (Exception)  
    {  
        throw;  
    }  
}  
  
```  
  
  
