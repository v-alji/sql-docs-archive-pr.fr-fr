---
title: Copie de colonne, transformation | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.copycolumntrans.f1
helpviewer_keywords:
- columns [Integration Services], copying
- copying columns
- Copy Column transformation
ms.assetid: 1c72a313-9026-46bc-a57f-c6b3f47346f8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fd2745070a92ab71e89f3bfa9edd8673b676632b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611193"
---
# <a name="copy-column-transformation"></a><span data-ttu-id="3b262-102">copie de colonnes (transformation)</span><span class="sxs-lookup"><span data-stu-id="3b262-102">Copy Column Transformation</span></span>
  <span data-ttu-id="3b262-103">La transformation de copie de colonne crée de nouvelles colonnes en copiant des colonnes d'entrée et en ajoutant les nouvelles colonnes à la sortie de la transformation.</span><span class="sxs-lookup"><span data-stu-id="3b262-103">The Copy Column transformation creates new columns by copying input columns and adding the new columns to the transformation output.</span></span> <span data-ttu-id="3b262-104">Ultérieurement dans le flux de données, différentes transformations peuvent être appliquées aux copies de colonne.</span><span class="sxs-lookup"><span data-stu-id="3b262-104">Later in the data flow, different transformations can be applied to the column copies.</span></span> <span data-ttu-id="3b262-105">Par exemple, vous pouvez utiliser la transformation de copie de colonne pour créer une copie d'une colonne, puis convertir les données copiées en caractères majuscules à l'aide de la transformation de la table des caractères, ou appliquer des agrégations à la nouvelle colonne à l'aide de la transformation d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="3b262-105">For example, you can use the Copy Column transformation to create a copy of a column and then convert the copied data to uppercase characters by using the Character Map transformation, or apply aggregations to the new column by using the Aggregate transformation.</span></span>  
  
## <a name="configuration-of-the-copy-column-transformation"></a><span data-ttu-id="3b262-106">Configuration de la transformation de copie de colonne</span><span class="sxs-lookup"><span data-stu-id="3b262-106">Configuration of the Copy Column Transformation</span></span>  
 <span data-ttu-id="3b262-107">Vous configurez la transformation de copie de colonne en spécifiant les colonnes d'entrée à copier.</span><span class="sxs-lookup"><span data-stu-id="3b262-107">You configure the Copy Column transformation by specifying the input columns to copy.</span></span> <span data-ttu-id="3b262-108">Vous pouvez créer plusieurs copies d'une colonne ou générer des copies de plusieurs colonnes en une même opération.</span><span class="sxs-lookup"><span data-stu-id="3b262-108">You can create multiple copies of a column, or create copies of multiple columns in one operation.</span></span>  
  
 <span data-ttu-id="3b262-109">Cette transformation a une entrée et une sortie.</span><span class="sxs-lookup"><span data-stu-id="3b262-109">This transformation has one input and one output.</span></span> <span data-ttu-id="3b262-110">Elle ne prend pas en charge de sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="3b262-110">It does not support an error output.</span></span>  
  
 <span data-ttu-id="3b262-111">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou par programme.</span><span class="sxs-lookup"><span data-stu-id="3b262-111">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="3b262-112">Pour plus d’informations sur les propriétés définissables dans la boîte de dialogue **Éditeur de transformation de copie de colonne** , consultez [Éditeur de transformation de copie de colonne](../../copy-column-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="3b262-112">For more information about the properties that you can set in the **Copy Column Transformation Editor** dialog box, see [Copy Column Transformation Editor](../../copy-column-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="3b262-113">La boîte de dialogue **Éditeur avancé** reflète les propriétés qui peuvent être définies par programmation.</span><span class="sxs-lookup"><span data-stu-id="3b262-113">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="3b262-114">Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur avancé** ou par programmation, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="3b262-114">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="3b262-115">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="3b262-115">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="3b262-116">Propriétés personnalisées des transformations</span><span class="sxs-lookup"><span data-stu-id="3b262-116">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="3b262-117">Pour plus d’informations sur la façon de définir les propriétés, consultez [Définir les propriétés d’un composant de flux de données](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="3b262-117">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b262-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3b262-118">See Also</span></span>  
 <span data-ttu-id="3b262-119">[Flux de données](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="3b262-119">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="3b262-120">Transformations Integration Services</span><span class="sxs-lookup"><span data-stu-id="3b262-120">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
