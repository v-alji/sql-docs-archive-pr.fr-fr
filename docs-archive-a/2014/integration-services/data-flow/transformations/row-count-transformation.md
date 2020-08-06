---
title: Calcul du nombre de lignes, transformation | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rowcounttrans.f1
helpviewer_keywords:
- updating variables
- Row Count transformation
- number of rows
- variables [Integration Services], updating
- counting rows
ms.assetid: b68293b9-a68c-40be-9d81-77342da1be29
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1b0940d608aeaa96b7ec43fa4486944ce0f887e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710772"
---
# <a name="row-count-transformation"></a><span data-ttu-id="9b008-102">transformation de calcul du nombre de lignes</span><span class="sxs-lookup"><span data-stu-id="9b008-102">Row Count Transformation</span></span>
  <span data-ttu-id="9b008-103">La transformation de calcul du nombre de lignes compte les lignes à mesure qu'elles passent par un flux de données et stocke le nombre final dans une variable.</span><span class="sxs-lookup"><span data-stu-id="9b008-103">The Row Count transformation counts rows as they pass through a data flow and stores the final count in a variable.</span></span>  
  
 <span data-ttu-id="9b008-104">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] peut utiliser les nombres de lignes pour mettre à jour les variables utilisées dans des scripts, des expressions et des expressions de propriétés.</span><span class="sxs-lookup"><span data-stu-id="9b008-104">A [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] package can use row counts to update the variables used in scripts, expressions, and property expressions.</span></span> <span data-ttu-id="9b008-105">(Par exemple, la variable qui stocke le nombre de lignes peut mettre à jour le texte d'un message électronique avec ce nombre.) La variable utilisée par la transformation de calcul du nombre de lignes doit déjà exister et figurer dans l'étendue de la tâche de flux de données à laquelle appartient le flux de données avec la transformation de calcul du nombre de lignes.</span><span class="sxs-lookup"><span data-stu-id="9b008-105">(For example, the variable that stores the row count can update the message text in an e-mail message to include the number of rows.) The variable that the Row Count transformation uses must already exist, and it must be in the scope of the Data Flow task to which the data flow with the Row Count transformation belongs.</span></span>  
  
 <span data-ttu-id="9b008-106">La transformation stocke la valeur de nombre de lignes dans la variable uniquement après que la dernière ligne est passée par la transformation.</span><span class="sxs-lookup"><span data-stu-id="9b008-106">The transformation stores the row count value in the variable only after the last row has passed through the transformation.</span></span> <span data-ttu-id="9b008-107">Par conséquent, la valeur de la variable n'est pas mise à jour à temps pour utiliser la valeur mise à jour dans le flux de données qui contient la transformation Nombre de lignes.</span><span class="sxs-lookup"><span data-stu-id="9b008-107">Therefore, the value of the variable is not updated in time to use the updated value in the data flow that contains the Row Count transformation.</span></span> <span data-ttu-id="9b008-108">Vous pouvez utiliser la variable mise à jour dans un flux de données distinct.</span><span class="sxs-lookup"><span data-stu-id="9b008-108">You can use the updated variable in a separate data flow.</span></span>  
  
 <span data-ttu-id="9b008-109">Cette transformation a une entrée et une sortie.</span><span class="sxs-lookup"><span data-stu-id="9b008-109">This transformation has one input and one output.</span></span> <span data-ttu-id="9b008-110">Elle ne prend pas en charge de sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="9b008-110">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-row-count-transformation"></a><span data-ttu-id="9b008-111">Configuration de la transformation du calcul du nombre de lignes</span><span class="sxs-lookup"><span data-stu-id="9b008-111">Configuration of the Row Count Transformation</span></span>  
 <span data-ttu-id="9b008-112">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="9b008-112">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="9b008-113">La boîte de dialogue **Éditeur avancé** reflète les propriétés qui peuvent être définies par programmation.</span><span class="sxs-lookup"><span data-stu-id="9b008-113">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="9b008-114">Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur avancé** ou par programmation, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="9b008-114">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="9b008-115">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="9b008-115">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="9b008-116">Propriétés personnalisées des transformations</span><span class="sxs-lookup"><span data-stu-id="9b008-116">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="9b008-117">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="9b008-117">Related Tasks</span></span>  
 <span data-ttu-id="9b008-118">Pour plus d’informations sur la définition des propriétés de ce composant, consultez [Définir les propriétés d’un composant de flux de données](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="9b008-118">For information about how to set the properties of this component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b008-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9b008-119">See Also</span></span>  
 <span data-ttu-id="9b008-120">[Variables Integration Services &#40;SSIS&#41;](../../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="9b008-120">[Integration Services &#40;SSIS&#41; Variables](../../integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="9b008-121">[Flux de données](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="9b008-121">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="9b008-122">Transformations Integration Services</span><span class="sxs-lookup"><span data-stu-id="9b008-122">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
