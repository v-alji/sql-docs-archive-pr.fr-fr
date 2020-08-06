---
title: Définir une relation référencée et des propriétés de relation référencées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- referenced dimension relationship
- relationships [Analysis Services], referenced dimensions
ms.assetid: 5bb44b41-635b-4398-8fe9-0bfbb142553e
author: minewiskan
ms.author: owend
ms.openlocfilehash: a84cf2ed95ab3660c5a6b3c039dc58351dc43264
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700380"
---
# <a name="define-a-referenced-relationship-and-referenced-relationship-properties"></a><span data-ttu-id="4f74d-102">Définir une relation référencée et des propriétés de relation référencée</span><span class="sxs-lookup"><span data-stu-id="4f74d-102">Define a Referenced Relationship and Referenced Relationship Properties</span></span>
  <span data-ttu-id="4f74d-103">Vous pouvez définir une relation de dimension de référence sous l’onglet **Utilisation de la dimension** du Concepteur de cube.</span><span class="sxs-lookup"><span data-stu-id="4f74d-103">A reference dimension relationship is defined on the **Dimension Usage** tab of Cube Designer.</span></span> <span data-ttu-id="4f74d-104">Pour définir la relation de dimension de référence, spécifiez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="4f74d-104">The reference dimension relationship is defined by specifying the following:</span></span>  
  
-   <span data-ttu-id="4f74d-105">La dimension intermédiaire à joindre.</span><span class="sxs-lookup"><span data-stu-id="4f74d-105">The intermediate dimension to which to join.</span></span> <span data-ttu-id="4f74d-106">Il peut s'agir d'une dimension régulière ou d'une autre dimension de référence.</span><span class="sxs-lookup"><span data-stu-id="4f74d-106">This can be a regular dimension or another reference dimension.</span></span>  
  
-   <span data-ttu-id="4f74d-107">Attribut de dimension de référence qui définit le niveau le plus bas où la dimension est disponible pour l'agrégation par rapport au groupe de mesures.</span><span class="sxs-lookup"><span data-stu-id="4f74d-107">A reference dimension attribute that defines the lowest level that the dimension is available for aggregation with regard to the measure group.</span></span>  
  
-   <span data-ttu-id="4f74d-108">L'attribut (clé étrangère) dans la dimension intermédiaire qui correspond à l'attribut de dimension de référence.</span><span class="sxs-lookup"><span data-stu-id="4f74d-108">The (foreign key) attribute in the intermediate dimension that corresponds to the reference dimension attribute.</span></span>  
  
 <span data-ttu-id="4f74d-109">Notez que la colonne qui lie la dimension de référence à la table de faits, qui est généralement l'attribut clé dans la dimension de référence, doit aussi être définie en tant qu'attribut dans la dimension intermédiaire.</span><span class="sxs-lookup"><span data-stu-id="4f74d-109">Notice that the column that links the reference dimension to the fact table, which is generally the key attribute in the reference dimension, must also be defined as an attribute in the intermediate dimension.</span></span> <span data-ttu-id="4f74d-110">Lorsque vous créez une chaîne de dimensions de référence, commencez par créer la relation régulière entre la première dimension de la chaîne et le groupe de mesures.</span><span class="sxs-lookup"><span data-stu-id="4f74d-110">When you create a chain of reference dimensions, start by creating the regular relationship between the first dimension in the chain and the measure group.</span></span> <span data-ttu-id="4f74d-111">Créez ensuite chaque relation référencée additionnelle dans l'ordre.</span><span class="sxs-lookup"><span data-stu-id="4f74d-111">Then create each additional referenced relationship in order.</span></span> <span data-ttu-id="4f74d-112">Une relation référencée ne peut être créée qu'avec une dimension ayant une relation existante avec le groupe de mesures.</span><span class="sxs-lookup"><span data-stu-id="4f74d-112">A referenced relationship can only be made to a dimension that has an existing relationship to the measure group.</span></span>  
  
 <span data-ttu-id="4f74d-113">Quand vous créez une relation de dimension de référence, le lien d'attribut de dimension est matérialisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="4f74d-113">When you create a reference dimension relationship, the dimension attribute link is materialized by default.</span></span> <span data-ttu-id="4f74d-114">La matérialisation d'un lien d'attribut de dimension fait que la valeur du lien entre la table de faits et la dimension de référence pour chaque ligne est matérialisée, ou stockée, dans la structure MOLAP de la dimension lors du traitement.</span><span class="sxs-lookup"><span data-stu-id="4f74d-114">Materializing a dimension attribute link causes the value of the link between the fact table and the reference dimension for each row to be materialized, or stored, in the MOLAP structure for the dimension during processing.</span></span> <span data-ttu-id="4f74d-115">Ceci a un effet mineur sur les performances du traitement et sur l'espace de stockage nécessaire, mais permet d'accroître les performances des requêtes.</span><span class="sxs-lookup"><span data-stu-id="4f74d-115">This will have a minor effect on processing performance and storage requirements, but will improve query performance.</span></span>  
  
 <span data-ttu-id="4f74d-116">Dans une dimension de référence, la granularité est spécifiée en identifiant l'attribut qui définit la relation entre une dimension de référence et le groupe de mesures correspondant à la table principale de la dimension.</span><span class="sxs-lookup"><span data-stu-id="4f74d-116">In a reference dimension, granularity is specified by identifying the attribute that defines the relationship between a reference dimension and the measure group corresponding to the main table of the dimension.</span></span> <span data-ttu-id="4f74d-117">Lorsque plusieurs dimensions de référence sont chaînées ensemble, les références définissent la relation entre la dimension la plus éloignée et le groupe de mesures.</span><span class="sxs-lookup"><span data-stu-id="4f74d-117">When multiple reference dimensions are chained together, the references define the relationship from the outermost dimension to the measure group.</span></span>  
  
  
