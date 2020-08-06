---
title: Définir une relation régulière et des propriétés de relation régulière | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- granularity attribute
- relationships [Analysis Services], regular relationships
ms.assetid: 840280d8-20c3-46c0-99ea-62479469c36b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9b4f49e219a85d5577fb1acddfe14e7afd3b105d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613653"
---
# <a name="define-a-regular-relationship-and-regular-relationship-properties"></a><span data-ttu-id="b46e0-102">Définir une relation régulière et des propriétés de relation régulière</span><span class="sxs-lookup"><span data-stu-id="b46e0-102">Define a Regular Relationship and Regular Relationship Properties</span></span>
  <span data-ttu-id="b46e0-103">Quand vous définissez une nouvelle dimension de cube ou un nouveau groupe de mesures, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] tente de détecter si une relation régulière existe et affecte le paramètre d'utilisation de la dimension de la valeur `Regular`.</span><span class="sxs-lookup"><span data-stu-id="b46e0-103">When you define a new cube dimension or a new measure group, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will try to detect if a regular relationship exists and then set the dimension usage setting to `Regular`.</span></span> <span data-ttu-id="b46e0-104">Vous pouvez afficher ou modifier une relation de dimension régulière sous l’onglet **Utilisation de la dimension** du Concepteur de cube.</span><span class="sxs-lookup"><span data-stu-id="b46e0-104">You can view or edit a regular dimension relationship on the **Dimension Usage** tab of Cube Designer.</span></span>  
  
 <span data-ttu-id="b46e0-105">Quand vous définissez la relation d'une dimension de cube avec un groupe de mesures, vous spécifiez également l'attribut de granularité de cette relation.</span><span class="sxs-lookup"><span data-stu-id="b46e0-105">When you define the relationship of a cube dimension to a measure group, you also specify the granularity attribute for that relationship.</span></span> <span data-ttu-id="b46e0-106">L'attribut de granularité définit le niveau de détail le plus bas disponible dans le cube pour cette dimension, qui est généralement l'attribut clé de la dimension.</span><span class="sxs-lookup"><span data-stu-id="b46e0-106">The granularity attribute defines the lowest level of detail available in the cube for that dimension, which is generally the key attribute for the dimension.</span></span> <span data-ttu-id="b46e0-107">Cependant, vous souhaitez parfois définir la granularité d'une dimension de cube particulière d'un groupe de mesures à un grain différent.</span><span class="sxs-lookup"><span data-stu-id="b46e0-107">However, sometimes you may want to set the granularity of a particular cube dimension in a particular measure group to a different grain.</span></span> <span data-ttu-id="b46e0-108">Par exemple, vous souhaitez définir la granularité de la dimension Time (Temps) avec l'attribut Month (Mois) plutôt qu'avec l'attribut Day (Jour), si vous utilisez un groupe de mesures de quotas de ventes ou de budget.</span><span class="sxs-lookup"><span data-stu-id="b46e0-108">For example, you may want to set the granularity attribute for the Time dimension to the Month attribute instead of to the Day attribute, if you are using a Sales Quotas or a Budget measure group.</span></span> <span data-ttu-id="b46e0-109">Si vous spécifiez que l'attribut de granularité doit être un autre attribut que l'attribut clé, vous devez vérifier que tous les autres attributs de la dimension sont directement ou indirectement liés à cet autre attribut via des relations d'attributs.</span><span class="sxs-lookup"><span data-stu-id="b46e0-109">When you specify the granularity attribute to be an attribute other than the key attribute, you must guarantee that all other attributes in the dimension are directly or indirectly linked to this other attribute through attribute relationships.</span></span> <span data-ttu-id="b46e0-110">Si ce n'est pas le cas, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ne peut pas agréger les données correctement.</span><span class="sxs-lookup"><span data-stu-id="b46e0-110">If not, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will be unable to aggregate data correctly.</span></span>  
  
  
