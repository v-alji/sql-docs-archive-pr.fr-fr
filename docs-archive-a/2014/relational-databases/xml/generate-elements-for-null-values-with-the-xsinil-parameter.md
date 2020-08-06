---
title: Générer des éléments pour des valeurs NULL avec le paramètre XSINIL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, null values
- null values [SQL Server], XML
- ELEMENTS directive
- XSINIL parameter
ms.assetid: 2dbc4e48-1cae-4d83-b371-3265da9687cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 602de12b5aa9be8997fbd49a2f23e0b73444aac0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710423"
---
# <a name="generate-elements-for-null-values-with-the-xsinil-parameter"></a><span data-ttu-id="eec88-102">Générer des éléments pour des valeurs NULL avec le paramètre XSINIL</span><span class="sxs-lookup"><span data-stu-id="eec88-102">Generate Elements for NULL Values with the XSINIL Parameter</span></span>
  <span data-ttu-id="eec88-103">La directive **ELEMENTS** construit du code XML dans lequel chaque valeur de colonne est mappée à un élément du code XML.</span><span class="sxs-lookup"><span data-stu-id="eec88-103">The **ELEMENTS** directive constructs XML in which each column value maps to an element in the XML.</span></span> <span data-ttu-id="eec88-104">Si la valeur de colonne est NULL, aucun élément n'est ajouté.</span><span class="sxs-lookup"><span data-stu-id="eec88-104">If the column value is NULL, no element is added.</span></span> <span data-ttu-id="eec88-105">En spécifiant le paramètre facultatif **XSINIL** sur la directive ELEMENTS, vous pouvez demander qu’un élément soit également créé pour la valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="eec88-105">By specifying the optional **XSINIL** parameter on the ELEMENTS directive, you can request that an element also be created for the NULL value.</span></span> <span data-ttu-id="eec88-106">Dans ce cas, un élément dont l’attribut **xsi:nil** a la valeur TRUE est retourné pour chaque valeur de colonne NULL.</span><span class="sxs-lookup"><span data-stu-id="eec88-106">In this case, an element that has the **xsi:nil** attribute set to TRUE is returned for each NULL column value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eec88-107">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eec88-107">See Also</span></span>  
 [<span data-ttu-id="eec88-108">Utiliser le mode RAW avec FOR XML</span><span class="sxs-lookup"><span data-stu-id="eec88-108">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
