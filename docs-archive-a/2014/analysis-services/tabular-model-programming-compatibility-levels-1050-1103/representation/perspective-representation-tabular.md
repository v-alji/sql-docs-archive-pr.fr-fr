---
title: Représentation en perspective (tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 6d2636c4-dae4-448f-a1d4-dbee739e177c
author: minewiskan
ms.author: owend
ms.openlocfilehash: ca8a66d3134748fd524dc0c6b524d944213533e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603676"
---
# <a name="perspective-representation-tabular"></a><span data-ttu-id="ed96d-102">Représentation (tabulaire) d'une perspective</span><span class="sxs-lookup"><span data-stu-id="ed96d-102">Perspective Representation (Tabular)</span></span>
  <span data-ttu-id="ed96d-103">Une perspective permet de simplifier ou mettre l'accent sur une plus petite partie du modèle pour l'application cliente.</span><span class="sxs-lookup"><span data-stu-id="ed96d-103">A perspective is a mechanism to simplify or focus the model into a smaller portion of it for the client application.</span></span>  
  
 <span data-ttu-id="ed96d-104">Pour une explication détaillée sur la création et la manipulation de la représentation perspective, consultez [représentation en perspective (tabulaire)](perspective-representation-tabular.md) .</span><span class="sxs-lookup"><span data-stu-id="ed96d-104">See [Perspective Representation (Tabular)](perspective-representation-tabular.md) for a detailed explanation on how to create and manipulate the perspective representation.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="ed96d-105">Les perspectives ne sont pas un mécanisme de sécurité ; les objets en dehors de la perspective sont toujours accessibles à l'utilisateur via d'autres interfaces.</span><span class="sxs-lookup"><span data-stu-id="ed96d-105">Perspectives are not a security mechanism; objects outside the perspective can still be accessed by the user through other interfaces.</span></span>  
  
## <a name="perspective-representation"></a><span data-ttu-id="ed96d-106">Représentation d'une perspective</span><span class="sxs-lookup"><span data-stu-id="ed96d-106">Perspective Representation</span></span>  
 <span data-ttu-id="ed96d-107">En termes d'objets AMO, une représentation de perspective a une relation de mappage un-à-un avec <xref:Microsoft.AnalysisServices.Perspective> et aucun autre objet AMO principal n'est requis.</span><span class="sxs-lookup"><span data-stu-id="ed96d-107">In terms of AMO objects a perspective representation has a one to one mapping relationship with <xref:Microsoft.AnalysisServices.Perspective> and no other main AMO objects are required.</span></span>  
  
### <a name="perspective-in-amo"></a><span data-ttu-id="ed96d-108">Perspective dans AMO</span><span class="sxs-lookup"><span data-stu-id="ed96d-108">Perspective in AMO</span></span>  
 <span data-ttu-id="ed96d-109">L'extrait de code suivant montre comment créer une perspective dans un modèle tabulaire.</span><span class="sxs-lookup"><span data-stu-id="ed96d-109">The following code snippet shows how to create a perspective in a Tabular model.</span></span> <span data-ttu-id="ed96d-110">L'élément clé dans cet extrait de code est l'élément de perspective ; cet objet est une représentation graphique de tous les objets du modèle tabulaire accessibles à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ed96d-110">The key element in this piece of code is the perspectiveElements; this object is a graphical representation of all the objects in the tabular model that are exposed to the user.</span></span> <span data-ttu-id="ed96d-111">*perspective* contient 4 colonnes et, pour ce scénario, seules les colonnes 1, 2 et 3 sont pertinentes.</span><span class="sxs-lookup"><span data-stu-id="ed96d-111">*perspectiveElements* contains 4 columns and for this scenario only columns 1, 2 and 3 are relevant.</span></span> <span data-ttu-id="ed96d-112">La colonne 1 contient le type d'élément affiché (elementTypeValue) ; la colonne 2 contient le nom complet de l'élément (--), qui devra probablement être analysé pour entrer l'élément dans la perspective ; la colonne 3 contient un élément de case à cocher (checkedElement) qui indique si l'élément fait partie ou non de la perspective.</span><span class="sxs-lookup"><span data-stu-id="ed96d-112">Column 1 contains the type of element displayed -elementTypeValue-; column 2 contains the complete name of the element --, that probably will need to parsed to enter the element in the perspective; column 3 contains a checkbox item -checkedElement- that tells if the element is part of the perspective or not.</span></span>  
  
```  
  
private void updatePerspective_Click(  
                     AMO.Cube modelCube  
                  ,  DataGridView perspectiveElements  
                  ,  string updatedPerspectiveID  
             )  
{  
    //Update is done by delete first, create new and insert after  
    //if perspective doesn't exist then create first and insert after  
    updatedPerspectiveID = updatedPerspectiveID.Trim();  
    if (modelCube.Perspectives.Contains(updatedPerspectiveID))  
    {  
        modelCube.Perspectives.Remove(updatedPerspectiveID, true);  
        newDatabase.Update(AMO.UpdateOptions.ExpandFull, AMO.UpdateMode.UpdateOrCreate);  
    }  
    AMO.Perspective currentPerspective = modelCube.Perspectives.Add(updatedPerspectiveID, updatedPerspectiveID);  
  
    foreach (DataGridViewRow currentDGVRow in perspectiveElements.Rows)  
    {  
        bool checkedElement = (bool)currentDGVRow.Cells[3].Value;  
        if (checkedElement)  
        {  
            string elementTypeValue = currentDGVRow.Cells[1].Value.ToString();  
            string elementNameValue = currentDGVRow.Cells[2].Value.ToString();  
            switch (elementTypeValue)  
            {  
                case "Column: Attribute":  
                case "Column: Calculated Column":  
                    {  
                        string perspectiveDimensionName = Regex.Match(elementNameValue, @"(?<=')(.*?)(?=')").ToString();  
                        string perspectiveDimensionAttributeName = Regex.Match(elementNameValue, @"(?<=\[)(.*?)(?=\])").ToString();  
                        AMO.PerspectiveDimension currentPerspectiveDimension;  
                        if (!currentPerspective.Dimensions.Contains(perspectiveDimensionName))  
                        {  
                            currentPerspectiveDimension = currentPerspective.Dimensions.Add(perspectiveDimensionName);  
                        }  
                        else  
                        {  
                            currentPerspectiveDimension = currentPerspective.Dimensions[perspectiveDimensionName];  
                        }  
                        if (!currentPerspectiveDimension.Attributes.Contains(perspectiveDimensionAttributeName))  
                        {  
                            currentPerspectiveDimension.Attributes.Add(perspectiveDimensionAttributeName);  
                        }  
                    }  
                    break;  
                case "Hierarchy":  
                    {  
                        string perspectiveDimensionName = Regex.Match(elementNameValue, @"(?<=')(.*?)(?=')").ToString();  
                        string perspectiveDimensionHierarchyName = Regex.Match(elementNameValue, @"(?<=\[)(.*?)(?=\])").ToString();  
                        AMO.PerspectiveDimension currentPerspectiveDimension;  
                        if (!currentPerspective.Dimensions.Contains(perspectiveDimensionName))  
                        {  
                            currentPerspectiveDimension = currentPerspective.Dimensions.Add(perspectiveDimensionName);  
                        }  
                        else  
                        {  
                            currentPerspectiveDimension = currentPerspective.Dimensions[perspectiveDimensionName];  
                        }  
                        if (!currentPerspectiveDimension.Hierarchies.Contains(perspectiveDimensionHierarchyName))  
                        {  
                            currentPerspectiveDimension.Hierarchies.Add(perspectiveDimensionHierarchyName);  
                        }  
                    }  
                    break;  
                case "Measure":  
                    {  
                        string perspectiveMeasureGroupName = Regex.Match(elementNameValue, @"(?<=')(.*?)(?=')").ToString();  
                        string measureName = Regex.Match(elementNameValue, @"(?<=\[)(.*?)(?=\])").ToString();  
                        string perspectiveMeasureName = string.Format("[Measures].[{0}]", measureName);  
                        AMO.PerspectiveCalculation currentPerspectiveCalculation = new AMO.PerspectiveCalculation(perspectiveMeasureName, AMO.PerspectiveCalculationType.Member);  
                        if (!currentPerspective.Calculations.Contains(perspectiveMeasureName))  
                        {  
                            currentPerspective.Calculations.Add(currentPerspectiveCalculation);  
                        }  
                        if (modelCube.MdxScripts["MdxScript"].CalculationProperties.Contains(string.Format("KPIs.[{0}]", measureName)))  
                        {//Current Measure is also a KPI ==> will be added to the KPIs collection of the perspective  
                            AMO.PerspectiveKpi currentPerspectiveKpi = new AMO.PerspectiveKpi(perspectiveMeasureName);  
                            if (!currentPerspective.Kpis.Contains(perspectiveMeasureName))  
                            {  
                                currentPerspective.Kpis.Add(currentPerspectiveKpi);  
                            }  
                        }  
                    }  
                    break;  
                default:  
                    break;  
            }  
        }  
    }  
  
    newDatabase.Update(AMO.UpdateOptions.ExpandFull, AMO.UpdateMode.CreateOrReplace);  
    MessageBox.Show(String.Format("Perpective successfully updated."), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Information);  
}  
  
```  
  
## <a name="amo2tabular-sample"></a><span data-ttu-id="ed96d-113">Exemple AMO2Tabular</span><span class="sxs-lookup"><span data-stu-id="ed96d-113">AMO2Tabular sample</span></span>  
 <span data-ttu-id="ed96d-114">Toutefois, pour connaître la façon d'utiliser AMO pour créer et manipuler des représentations de perspective consultez le code source de l'exemple Objets AMO vers objets tabulaires.</span><span class="sxs-lookup"><span data-stu-id="ed96d-114">However, to have an understanding on how to use AMO to create and manipulate perspective representations see the source code of the AMO to Tabular sample.</span></span> <span data-ttu-id="ed96d-115">L'exemple est disponible sur Codeplex.</span><span class="sxs-lookup"><span data-stu-id="ed96d-115">The sample is available at Codeplex.</span></span> <span data-ttu-id="ed96d-116">Remarque importante à propos du code : le code est fourni uniquement comme un support aux concepts logiques expliqués ici et ne doit pas être utilisé dans un environnement de production, ni à des fins autres que pédagogiques.</span><span class="sxs-lookup"><span data-stu-id="ed96d-116">An important note about the code: the code is provided only as a support to the logical concepts explained here and should not be used in a production environment; nor should it be used for other purpose other than the pedagogical one.</span></span>  
  
  
