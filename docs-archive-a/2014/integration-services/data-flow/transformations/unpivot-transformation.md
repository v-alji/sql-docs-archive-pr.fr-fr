---
title: Unpivot, transformation | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.unpivottrans.f1
helpviewer_keywords:
- Unpivot transformation
- more normalized data set [Integration Services]
- normalized data [Integration Services]
- datasets [Integration Services], normalized data
ms.assetid: f635c64b-a9c5-4f11-9c40-9cd9d5298c5d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e605dc4827a885b5dc65fbb680cce8a434b89fd5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613036"
---
# <a name="unpivot-transformation"></a><span data-ttu-id="16a2f-102">Transformation Unpivot</span><span class="sxs-lookup"><span data-stu-id="16a2f-102">Unpivot Transformation</span></span>
  <span data-ttu-id="16a2f-103">La transformation Unpivot convertit un dataset non normalisé en version plus normalisée en étendant les valeurs de plusieurs colonnes d'un enregistrement dans plusieurs enregistrements avec les mêmes valeurs dans une colonne unique.</span><span class="sxs-lookup"><span data-stu-id="16a2f-103">The Unpivot transformation makes an unnormalized dataset into a more normalized version by expanding values from multiple columns in a single record into multiple records with the same values in a single column.</span></span> <span data-ttu-id="16a2f-104">Par exemple, un dataset qui répertorie des noms de clients possède une ligne pour chaque client, avec les produits et la quantité achetée mentionnés dans les colonnes sur la ligne.</span><span class="sxs-lookup"><span data-stu-id="16a2f-104">For example, a dataset that lists customer names has one row for each customer, with the products and the quantity purchased shown in columns in the row.</span></span> <span data-ttu-id="16a2f-105">Après que la transformation Unpivot a normalisé le dataset, celui-ci contient une ligne différente pour chaque produit que le client a acheté.</span><span class="sxs-lookup"><span data-stu-id="16a2f-105">After the Unpivot transformation normalizes the data set, the data set contains a different row for each product that the customer purchased.</span></span>  
  
 <span data-ttu-id="16a2f-106">Le schéma suivant illustre un dataset avant que les données n'aient été transformées dans la colonne Product.</span><span class="sxs-lookup"><span data-stu-id="16a2f-106">The following diagram shows a data set before the data is unpivoted on the Product column.</span></span>  
  
 <span data-ttu-id="16a2f-107">![Dataset après la suppression du tableau croisé dynamique](../../media/mw-dts-18.gif "Dataset après la suppression du tableau croisé dynamique")</span><span class="sxs-lookup"><span data-stu-id="16a2f-107">![Dataset after it is unpivoted](../../media/mw-dts-18.gif "Dataset after it is unpivoted")</span></span>  
  
 <span data-ttu-id="16a2f-108">Le schéma suivant illustre un dataset après transformation de la colonne Product.</span><span class="sxs-lookup"><span data-stu-id="16a2f-108">The following diagram shows a data set after it has been unpivoted on the Product column.</span></span>  
  
 <span data-ttu-id="16a2f-109">![Dataset avant la suppression du tableau croisé dynamique](../../media/mw-dts-17.gif "Dataset avant la suppression du tableau croisé dynamique")</span><span class="sxs-lookup"><span data-stu-id="16a2f-109">![Dataset before it is unpivoted](../../media/mw-dts-17.gif "Dataset before it is unpivoted")</span></span>  
  
 <span data-ttu-id="16a2f-110">Dans certaines circonstances, les résultats de la suppression du tableau croisé dynamique peuvent contenir des lignes aux valeurs inattendues.</span><span class="sxs-lookup"><span data-stu-id="16a2f-110">Under some circumstances, the unpivot results may contain rows with unexpected values.</span></span> <span data-ttu-id="16a2f-111">Par exemple, si les exemples de données du diagramme qui doivent être supprimées du tableau croisé dynamique possèdent des valeurs Null dans toutes les colonnes Qty pour Fred, la sortie ne comprend qu'une ligne pour Fred, au lieu de cinq.</span><span class="sxs-lookup"><span data-stu-id="16a2f-111">For example, if the sample data to unpivot shown in the diagram had null values in all the Qty columns for Fred, then the output would include only one row for Fred, not five.</span></span> <span data-ttu-id="16a2f-112">La colonne Qty contient Null ou zéro, suivant le type de données de la colonne.</span><span class="sxs-lookup"><span data-stu-id="16a2f-112">The Qty column would contain either null or zero, depending on the column data type.</span></span>  
  
## <a name="configuration-of-the-unpivot-transformation"></a><span data-ttu-id="16a2f-113">Configuration de la transformation Unpivot</span><span class="sxs-lookup"><span data-stu-id="16a2f-113">Configuration of the Unpivot Transformation</span></span>  
 <span data-ttu-id="16a2f-114">La transformation Unpivot inclut la propriété personnalisée `PivotKeyValue`.</span><span class="sxs-lookup"><span data-stu-id="16a2f-114">The Unpivot transformation includes the `PivotKeyValue` custom property.</span></span> <span data-ttu-id="16a2f-115">La propriété peut être mise à jour par une expression de propriété lors du chargement du package.</span><span class="sxs-lookup"><span data-stu-id="16a2f-115">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="16a2f-116">Pour plus d’informations, consultez [Expressions Integration Services &#40;SSIS&#41; ](../../expressions/integration-services-ssis-expressions.md), [Expressions de propriété dans des packages](../../expressions/use-property-expressions-in-packages.md) et [Propriétés personnalisées des transformations](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="16a2f-116">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md), and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="16a2f-117">Cette transformation a une entrée et une sortie.</span><span class="sxs-lookup"><span data-stu-id="16a2f-117">This transformation has one input and one output.</span></span> <span data-ttu-id="16a2f-118">Elle ne possède aucune sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="16a2f-118">It has no error output.</span></span>  
  
 <span data-ttu-id="16a2f-119">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="16a2f-119">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="16a2f-120">Pour plus d’informations sur les propriétés définissables dans la boîte de dialogue **Éditeur de transformation UnPivot** , cliquez sur l’une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="16a2f-120">For more information about the properties that you can set in the **Unpivot Transformation Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="16a2f-121">Éditeur de transformation UnPivot</span><span class="sxs-lookup"><span data-stu-id="16a2f-121">Unpivot Transformation Editor</span></span>](../../unpivot-transformation-editor.md)  
  
 <span data-ttu-id="16a2f-122">Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur avancé** ou par programmation, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="16a2f-122">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="16a2f-123">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="16a2f-123">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="16a2f-124">Propriétés personnalisées des transformations</span><span class="sxs-lookup"><span data-stu-id="16a2f-124">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="16a2f-125">Pour plus d’informations sur la façon de définir des propriétés, consultez [Définir les propriétés d’un composant de flux de données](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="16a2f-125">For more information about how to set the properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
