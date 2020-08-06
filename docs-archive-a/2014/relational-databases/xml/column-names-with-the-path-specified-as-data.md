---
title: Noms de colonnes avec le chemin spécifié sous la forme data() | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns with
ms.assetid: 0b738e44-6108-4417-a9a4-abeb7680d899
author: rothja
ms.author: jroth
ms.openlocfilehash: 61aa7f85c7ee2358ddcf99f81c87c1295fac8fb3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600686"
---
# <a name="column-names-with-the-path-specified-as-data"></a><span data-ttu-id="011cd-102">Noms de colonnes avec le chemin d'accès spécifié sous la forme data()</span><span class="sxs-lookup"><span data-stu-id="011cd-102">Column Names with the Path Specified as data()</span></span>
  <span data-ttu-id="011cd-103">Si le chemin d'accès spécifié comme nom de colonne est « data() », la valeur est traitée en tant que valeur atomique dans le document XML généré.</span><span class="sxs-lookup"><span data-stu-id="011cd-103">If the path specified as column name is "data()", the value is treated as an atomic value in the generated XML.</span></span> <span data-ttu-id="011cd-104">Un espace est ajouté au document XML si l'élément suivant dans la sérialisation est également une valeur atomique.</span><span class="sxs-lookup"><span data-stu-id="011cd-104">A space character is added to the XML if the next item in the serialization is also an atomic value.</span></span> <span data-ttu-id="011cd-105">Cela est utile lorsque vous créez une liste de valeurs d'élément et d'attribut de type liste.</span><span class="sxs-lookup"><span data-stu-id="011cd-105">This is useful when you are creating list typed element and attribute values.</span></span> <span data-ttu-id="011cd-106">La requête suivante extrait l'ID de modèle, le nom et la liste des produits pour le modèle concerné.</span><span class="sxs-lookup"><span data-stu-id="011cd-106">The following query retrieves the product model ID, name, and list of products in that product model.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID       AS "@ProductModelID",  
       Name                 AS "@ProductModelName",  
      (SELECT ProductID AS "data()"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
      FOR XML PATH (''))    AS "@ProductIDs"  
FROM  Production.ProductModel  
WHERE ProductModelID= 7   
FOR XML PATH('ProductModelData');  
```  
  
 <span data-ttu-id="011cd-107">L'instruction SELECT imbriquée extrait une liste d'ID de produit.</span><span class="sxs-lookup"><span data-stu-id="011cd-107">The nested SELECT retrieves a list of product IDs.</span></span> <span data-ttu-id="011cd-108">Elle spécifie « data() » comme nom de colonne pour les ID de produit.</span><span class="sxs-lookup"><span data-stu-id="011cd-108">It specifies "data()" as the column name for product IDs.</span></span> <span data-ttu-id="011cd-109">Étant donné que le mode PATH spécifie une chaîne vide pour le nom d'élément de ligne, aucun élément de ligne n'est généré.</span><span class="sxs-lookup"><span data-stu-id="011cd-109">Because PATH mode specifies an empty string for the row element name, there is no row element generated.</span></span> <span data-ttu-id="011cd-110">À la place, les valeurs sont renvoyées comme étant affectées à un attribut ProductIDs de l'élément de ligne <`ProductModelData`> de l'instruction SELECT parente.</span><span class="sxs-lookup"><span data-stu-id="011cd-110">Instead, the values are returned as assigned to a ProductIDs attribute of the <`ProductModelData`> row element of the parent SELECT.</span></span> <span data-ttu-id="011cd-111">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="011cd-111">This is the result:</span></span>  
  
 `<ProductModelData ProductModelID="7"`  
  
 `ProductModelName="HL Touring Frame"`  
  
 `ProductIDs="885 887 888 889 890 891 892 893" />`  
  
## <a name="see-also"></a><span data-ttu-id="011cd-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="011cd-112">See Also</span></span>  
 [<span data-ttu-id="011cd-113">Utiliser le mode PATH avec FOR XML</span><span class="sxs-lookup"><span data-stu-id="011cd-113">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
