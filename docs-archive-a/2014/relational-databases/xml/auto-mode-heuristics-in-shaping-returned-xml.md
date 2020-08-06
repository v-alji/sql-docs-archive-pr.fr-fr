---
title: Heuristique du mode AUTO permettant de définir la forme des données XML renvoyées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- AUTO FOR XML mode, heuristics in shaping returned XML
ms.assetid: 6c5cb6c1-2921-4ba1-8100-0bf8074f9103
author: rothja
ms.author: jroth
ms.openlocfilehash: 7a64cda8989e1e45d4ad869f8883e1c9d65f4b7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600698"
---
# <a name="auto-mode-heuristics-in-shaping-returned-xml"></a><span data-ttu-id="50375-102">Heuristique du mode AUTO permettant de définir la forme des données XML renvoyées</span><span class="sxs-lookup"><span data-stu-id="50375-102">AUTO Mode Heuristics in Shaping Returned XML</span></span>
  <span data-ttu-id="50375-103">Le mode AUTO détermine la forme des données XML renvoyées en fonction de la requête.</span><span class="sxs-lookup"><span data-stu-id="50375-103">AUTO mode determines the shape of returned XML based on the query.</span></span> <span data-ttu-id="50375-104">Lors de la définition de l'imbrication des éléments, l'heuristique du mode AUTO compare les valeurs de colonnes de lignes adjacentes.</span><span class="sxs-lookup"><span data-stu-id="50375-104">In determining how elements are to be nested, AUTO mode heuristics compare column values in adjacent rows.</span></span> <span data-ttu-id="50375-105">Les colonnes de tous les types, sauf **ntext**, **text**, **image**et **xml**, sont comparées.</span><span class="sxs-lookup"><span data-stu-id="50375-105">Columns of all types, except **ntext**, **text**, **image**, and **xml**, are compared.</span></span> <span data-ttu-id="50375-106">Les colonnes de type **(n)varchar(max)** et **varbinary(max)** sont comparées.</span><span class="sxs-lookup"><span data-stu-id="50375-106">Columns of type **(n)varchar(max)** and **varbinary(max)** are compared.</span></span>  
  
 <span data-ttu-id="50375-107">L'exemple suivant illustre l'heuristique du mode AUTO qui détermine la forme des données XML obtenues :</span><span class="sxs-lookup"><span data-stu-id="50375-107">The following example illustrates the AUTO mode heuristics that determine the shape of the resulting XML:</span></span>  
  
```  
SELECT T1.Id, T2.Id, T1.Name  
FROM   T1, T2  
WHERE ...  
FOR XML AUTO  
ORDER BY T1.Id  
```  
  
 <span data-ttu-id="50375-108">Pour déterminer à quel endroit commence un nouvel élément <`T1`>, toutes les valeurs de colonne de T1, sauf **ntext**, **text**, **image** et **xml**, sont comparées si la clé de la table T1 n’est pas spécifiée.</span><span class="sxs-lookup"><span data-stu-id="50375-108">To determine where a new <`T1`> element starts, all column values of T1, except **ntext**, **text**, **image** and **xml**, are compared if the key on the table T1 is not specified.</span></span> <span data-ttu-id="50375-109">Ensuite, supposons que la colonne **Name** soit de type **nvarchar(40)** et que l’instruction SELECT renvoie l’ensemble de lignes suivant :</span><span class="sxs-lookup"><span data-stu-id="50375-109">Next, assume that the **Name** column is **nvarchar(40)** and the SELECT statement returns this rowset:</span></span>  
  
```  
T1.Id  T1.Name  T2.Id  
-----------------------  
1       Andrew    2  
1       Andrew    3  
1       Nancy     4  
```  
  
 <span data-ttu-id="50375-110">L'heuristique du mode AUTO compare toutes les valeurs de la table T1, les colonnes Id et Name.</span><span class="sxs-lookup"><span data-stu-id="50375-110">The AUTO mode heuristics compare all the values of table T1, the Id and Name columns.</span></span> <span data-ttu-id="50375-111">Étant donné que les deux premières lignes contiennent les mêmes valeurs pour les colonnes Id et Name, un élément \<T1> possédant deux éléments enfants \<T2> est ajouté au résultat.</span><span class="sxs-lookup"><span data-stu-id="50375-111">Because the first two rows have the same values for the Id and Name columns, one \<T1> element having two \<T2> child elements is added in the result.</span></span>  
  
 <span data-ttu-id="50375-112">Voici le document XML renvoyé :</span><span class="sxs-lookup"><span data-stu-id="50375-112">Following is the XML that is returned:</span></span>  
  
```  
<T1 Id="1" Name="Andrew">  
    <T2 Id="2" />  
    <T2 Id="3" />  
</T1>  
<T1 Id="1" Name="Nancy" >  
      <T2 Id="4" />  
</T>  
```  
  
 <span data-ttu-id="50375-113">Supposons maintenant que la colonne Name soit de type **text** .</span><span class="sxs-lookup"><span data-stu-id="50375-113">Now assume that the Name column is of **text** type.</span></span> <span data-ttu-id="50375-114">L'heuristique du mode AUTO ne compare pas les valeurs de ce type.</span><span class="sxs-lookup"><span data-stu-id="50375-114">The AUTO mode heuristics do not compare the values for this type.</span></span> <span data-ttu-id="50375-115">Au lieu de cela, elle considère que les valeurs ne sont pas identiques.</span><span class="sxs-lookup"><span data-stu-id="50375-115">Instead, it assumes that the values are not the same.</span></span> <span data-ttu-id="50375-116">Cela aboutit à la génération de données XML suivante :</span><span class="sxs-lookup"><span data-stu-id="50375-116">This results in XML generation as shown in the following:</span></span>  
  
```  
<T1 Id="1" Name="Andrew" >  
  <T2 Id="2" />  
</T1>  
<T1 Id="1" Name="Andrew" >  
  <T2 Id="3" />  
</T1>  
<T1 Id="1" Name="Nancy" >  
  <T2 Id="4" />  
</T1>  
```  
  
## <a name="see-also"></a><span data-ttu-id="50375-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="50375-117">See Also</span></span>  
 [<span data-ttu-id="50375-118">Utiliser le mode AUTO avec FOR XML</span><span class="sxs-lookup"><span data-stu-id="50375-118">Use AUTO Mode with FOR XML</span></span>](use-auto-mode-with-for-xml.md)  
  
  
