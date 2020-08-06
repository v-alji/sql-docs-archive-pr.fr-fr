---
title: Interroger des données spatiales au sujet du plus proche voisin | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 7af4ad5d-484e-45b4-aa16-83c33b358bb6
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 644b3e5cfdaeff7457639bc2da77260b64011735
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613910"
---
# <a name="query-spatial-data-for-nearest-neighbor"></a><span data-ttu-id="70190-102">Interroger des données spatiales au sujet du plus proche voisin</span><span class="sxs-lookup"><span data-stu-id="70190-102">Query Spatial Data for Nearest Neighbor</span></span>
  <span data-ttu-id="70190-103">Une requête courante utilisée avec les données spatiales est la requête Plus proche voisin.</span><span class="sxs-lookup"><span data-stu-id="70190-103">A common query used with spatial data is the Nearest Neighbor query.</span></span> <span data-ttu-id="70190-104">Les requêtes Plus proche voisin sont utilisées pour trouver les objets spatiaux les plus proches d'un objet spatial spécifique.</span><span class="sxs-lookup"><span data-stu-id="70190-104">Nearest Neighbor queries are used to find the closest spatial objects to a specific spatial object.</span></span> <span data-ttu-id="70190-105">Par exemple, le localisateur de magasin d'un site Web doit souvent trouver les magasins les plus proches de l'emplacement d'un client.</span><span class="sxs-lookup"><span data-stu-id="70190-105">For example a store locater for a Web site often must find the closest store locations to a customer location.</span></span>  
  
 <span data-ttu-id="70190-106">Une requête Plus proche voisin peut être écrite dans divers formats de requête valides, mais pour qu'elle utilise un index spatial, la syntaxe suivante doit être utilisée.</span><span class="sxs-lookup"><span data-stu-id="70190-106">A Nearest Neighbor query can be written in a variety of valid query formats, but for the Nearest Neighbor query to use a spatial index the following syntax must be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70190-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="70190-107">Syntax</span></span>  
  
```vb  
SELECT TOP ( number )  
        [ WITH TIES ]  
        [ * | expression ]   
        [, ...]  
    FROM spatial_table_reference, ...   
        [ WITH   
            (   
                [ INDEX ( index_ref ) ]   
                [ , SPATIAL_WINDOW_MAX_CELLS = <value>]   
                [ ,... ]   
            )   
        ]  
    WHERE   
        column_ref.STDistance ( @spatial_ object )   
            {   
                [ IS NOT NULL ] | [ < const ] | [ > const ]   
                | [ <= const ] | [ >= const ] | [ <> const ] ]   
            }  
            [ AND { other_predicate } ]   
    }  
    ORDER BY column_ref.STDistance ( @spatial_ object ) [ ,...n ]  
[ ; ]  
  
```  
  
## <a name="nearest-neighbor-query-and-spatial-indexes"></a><span data-ttu-id="70190-108">Requête Plus proche voisin et index spatiaux</span><span class="sxs-lookup"><span data-stu-id="70190-108">Nearest Neighbor Query and Spatial Indexes</span></span>  
 <span data-ttu-id="70190-109">Dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], les clauses `TOP` et `ORDER BY` sont utilisées pour effectuer une requête Plus proche voisin sur les colonnes de données spatiales.</span><span class="sxs-lookup"><span data-stu-id="70190-109">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], `TOP` and `ORDER BY` clauses are used to perform a Nearest Neighbor query on spatial data columns.</span></span> <span data-ttu-id="70190-110">La clause `ORDER BY` contient un appel à la méthode `STDistance()` pour le type de données de colonne spatial.</span><span class="sxs-lookup"><span data-stu-id="70190-110">The `ORDER BY` clause contains a call to the `STDistance()` method for the spatial column data type.</span></span> <span data-ttu-id="70190-111">La clause `TOP` indique le nombre d'objets à retourner pour la requête.</span><span class="sxs-lookup"><span data-stu-id="70190-111">The `TOP` clause indicates the number of objects to return for the query.</span></span>  
  
 <span data-ttu-id="70190-112">Les conditions suivantes doivent être respectées pour qu'une requête Plus proche voisin utilise un index spatial :</span><span class="sxs-lookup"><span data-stu-id="70190-112">The following requirements must be met for a Nearest Neighbor query to use a spatial index:</span></span>  
  
1.  <span data-ttu-id="70190-113">Un index spatial doit être présent sur l'une des colonnes spatiales et la méthode `STDistance()` doit utiliser cette colonne dans les clauses `WHERE` et `ORDER BY`.</span><span class="sxs-lookup"><span data-stu-id="70190-113">A spatial index must be present on one of the spatial columns and the `STDistance()` method must use that column in the `WHERE` and `ORDER BY` clauses.</span></span>  
  
2.  <span data-ttu-id="70190-114">La clause `TOP` ne peut pas contenir d'instruction `PERCENT`.</span><span class="sxs-lookup"><span data-stu-id="70190-114">The `TOP` clause cannot contain a `PERCENT` statement.</span></span>  
  
3.  <span data-ttu-id="70190-115">La clause `WHERE` doit contenir une méthode `STDistance()`.</span><span class="sxs-lookup"><span data-stu-id="70190-115">The `WHERE` clause must contain a `STDistance()` method.</span></span>  
  
4.  <span data-ttu-id="70190-116">S'il existe plusieurs prédicats dans la clause `WHERE`, le prédicat qui contient la méthode `STDistance()` doit être connecté par une conjonction `AND` aux autres prédicats.</span><span class="sxs-lookup"><span data-stu-id="70190-116">If there are multiple predicates in the `WHERE` clause then the predicate containing `STDistance()` method must be connected by an `AND` conjunction to the other predicates.</span></span> <span data-ttu-id="70190-117">La méthode `STDistance()` ne doit pas se trouver dans une partie facultative de la clause `WHERE`.</span><span class="sxs-lookup"><span data-stu-id="70190-117">The `STDistance()` method cannot be in an optional part of the `WHERE` clause.</span></span>  
  
5.  <span data-ttu-id="70190-118">La première expression dans la clause `ORDER BY` doit utiliser la méthode `STDistance()`.</span><span class="sxs-lookup"><span data-stu-id="70190-118">The first expression in the `ORDER BY` clause must use the `STDistance()` method.</span></span>  
  
6.  <span data-ttu-id="70190-119">L'ordre de tri de la première expression `STDistance()` dans la clause `ORDER BY` doit être `ASC`.</span><span class="sxs-lookup"><span data-stu-id="70190-119">Sort order for the first `STDistance()` expression in the `ORDER BY` clause must be `ASC`.</span></span>  
  
7.  <span data-ttu-id="70190-120">Toutes les lignes pour lesquelles `STDistance` retourne `NULL` doivent être éliminées par filtrage.</span><span class="sxs-lookup"><span data-stu-id="70190-120">All the rows for which `STDistance` returns `NULL` must be filtered out.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="70190-121">Les méthodes qui prennent les types de données `geography` ou `geometry` comme arguments retourneront `NULL` si les SRID ne sont pas les mêmes pour les types.</span><span class="sxs-lookup"><span data-stu-id="70190-121">Methods that take `geography` or `geometry` data types as arguments will return `NULL` if the SRIDs are not the same for the types.</span></span>  
  
 <span data-ttu-id="70190-122">Il est recommandé d'utiliser les nouveaux pavages d'index spatial pour les index utilisés dans les requêtes Plus proche voisin.</span><span class="sxs-lookup"><span data-stu-id="70190-122">It is recommended that the new spatial index tessellations be used for indexes used in Nearest Neighbor queries.</span></span> <span data-ttu-id="70190-123">Pour plus d’informations sur les pavages d’index spatial, consultez [Données spatiales &#40;SQL Server&#41;](spatial-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="70190-123">For more information on spatial index tessellations, see [Spatial Data &#40;SQL Server&#41;](spatial-data-sql-server.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="70190-124">Exemple</span><span class="sxs-lookup"><span data-stu-id="70190-124">Example</span></span>  
 <span data-ttu-id="70190-125">L'exemple de code suivant montre une requête Plus proche voisin qui peut utiliser un index spatial.</span><span class="sxs-lookup"><span data-stu-id="70190-125">The following code example shows a Nearest Neighbor query that can use a spatial index.</span></span> <span data-ttu-id="70190-126">L'exemple utilise la table `Person.Address` dans la base de données `AdventureWorks2012` .</span><span class="sxs-lookup"><span data-stu-id="70190-126">The example uses the `Person.Address` table in `AdventureWorks2012` database.</span></span>  
  
```  
USE AdventureWorks2012  
GO  
DECLARE @g geography = 'POINT(-121.626 47.8315)';  
SELECT TOP(7) SpatialLocation.ToString(), City FROM Person.Address  
WHERE SpatialLocation.STDistance(@g) IS NOT NULL  
ORDER BY SpatialLocation.STDistance(@g);  
  
```  
  
 <span data-ttu-id="70190-127">Créez un index spatial sur la colonne SpatialLocation pour voir comment une requête Plus proche voisin utilise un index spatial.</span><span class="sxs-lookup"><span data-stu-id="70190-127">Create a spatial index on the column SpatialLocation to see how a Nearest Neighbor query uses a spatial index.</span></span> <span data-ttu-id="70190-128">Pour plus d'informations sur la création d'index spatiaux, consultez [Create, Modify, and Drop Spatial Indexes](create-modify-and-drop-spatial-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="70190-128">For more information on creating spatial indexes, see [Create, Modify, and Drop Spatial Indexes](create-modify-and-drop-spatial-indexes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="70190-129">Exemple</span><span class="sxs-lookup"><span data-stu-id="70190-129">Example</span></span>  
 <span data-ttu-id="70190-130">L'exemple de code suivant montre une requête Plus proche voisin qui ne peut pas utiliser un index spatial.</span><span class="sxs-lookup"><span data-stu-id="70190-130">The following code example shows a Nearest Neighbor query that cannot use a spatial index.</span></span>  
  
```  
USE AdventureWorks2012  
GO  
DECLARE @g geography = 'POINT(-121.626 47.8315)';  
SELECT TOP(7) SpatialLocation.ToString(), City FROM Person.Address  
ORDER BY SpatialLocation.STDistance(@g);  
  
```  
  
 <span data-ttu-id="70190-131">La requête n'a pas de clause `WHERE` qui utilise `STDistance()` au format spécifié dans la section Syntaxe ; la requête ne peut donc pas utiliser d'index spatial.</span><span class="sxs-lookup"><span data-stu-id="70190-131">The query lacks a `WHERE` clause that uses `STDistance()` in a form specified in the syntax section so the query cannot use a spatial index.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70190-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="70190-132">See Also</span></span>  
 [<span data-ttu-id="70190-133">Données spatiales &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="70190-133">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
