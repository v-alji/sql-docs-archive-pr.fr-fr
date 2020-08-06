---
title: Utilisation de l’instruction DRILLTHROUGH pour récupérer des données sources (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- DRILLTHROUGH statement
- retrieving data
- queries [MDX], DRILLTHROUGH statement
- data retrieval [MDX]
ms.assetid: fe0ab170-25a9-45a8-a377-f71a67f77018
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5601a3ddfa7075ed53330e12c260af88648db990
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605806"
---
# <a name="using-drillthrough-to-retrieve-source-data-mdx"></a><span data-ttu-id="0aec1-102">Utilisation de l'instruction DRILLTHROUGH pour récupérer des données sources (MDX)</span><span class="sxs-lookup"><span data-stu-id="0aec1-102">Using DRILLTHROUGH to Retrieve Source Data (MDX)</span></span>
  <span data-ttu-id="0aec1-103">L’instruction MDX (Multidimensional Expressions) utilise l’instruction [DRILLTHROUGH](/sql/mdx/mdx-data-manipulation-drillthrough)pour récupérer un ensemble de lignes à partir des données sources d’une cellule d’un cube.</span><span class="sxs-lookup"><span data-stu-id="0aec1-103">Multidimensional Expressions (MDX) uses the [DRILLTHROUGH](/sql/mdx/mdx-data-manipulation-drillthrough)statement to retrieve a rowset from the source data for a cube cell.</span></span>  
  
 <span data-ttu-id="0aec1-104">Pour exécuter une instruction `DRILLTHROUGH` sur un cube, une action d'extraction doit être définie pour ce dernier.</span><span class="sxs-lookup"><span data-stu-id="0aec1-104">In order to run a `DRILLTHROUGH` statement on a cube, a drillthrough action must be defined for that cube.</span></span> <span data-ttu-id="0aec1-105">Pour définir une action d’extraction, dans [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], dans le Concepteur de cube, dans la barre d’outils du volet **Actions** , cliquez sur **Nouvelle action d’extraction**.</span><span class="sxs-lookup"><span data-stu-id="0aec1-105">To define a drillthrough action, in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], in Cube Designer, on the **Actions** pane, on the toolbar, click **New Drillthrough Action**.</span></span> <span data-ttu-id="0aec1-106">Dans la nouvelle action d'extraction, spécifiez le nom de l'action, la cible, la condition et les colonnes retournées par une instruction `DRILLTHROUGH`.</span><span class="sxs-lookup"><span data-stu-id="0aec1-106">In the new drillthrough action, specify the action name, target, condition, and the columns that are returned by a `DRILLTHROUGH` statement.</span></span>  
  
## <a name="drillthrough-statement-syntax"></a><span data-ttu-id="0aec1-107">Syntaxe de l'instruction DRILLTHROUGH</span><span class="sxs-lookup"><span data-stu-id="0aec1-107">DRILLTHROUGH Statement Syntax</span></span>  
 <span data-ttu-id="0aec1-108">L'instruction `DRILLTHROUGH` utilise la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="0aec1-108">The `DRILLTHROUGH` statement uses the following syntax:</span></span>  
  
```  
<drillthrough> ::= DRILLTHROUGH [<Max_Rows>] [<First_Rowset>] <MDX select> [<Return_Columns>]  
   < Max_Rows> ::= MAXROWS <positive number>  
   <First_Rowset> ::= FIRSTROWSET <positive number>  
   <Return_Columns> ::= RETURN <member or attribute> [, <member or attribute>]  
```  
  
 <span data-ttu-id="0aec1-109">La clause `SELECT` identifie la cellule du cube qui contient les données sources à récupérer.</span><span class="sxs-lookup"><span data-stu-id="0aec1-109">The `SELECT` clause identifies the cube cell that contains the source data to be retrieved.</span></span> <span data-ttu-id="0aec1-110">Cette clause `SELECT` est identique à une instruction MDX `SELECT` ordinaire, à la différence qu'un seul membre peut être spécifié sur chaque axe dans la clause `SELECT`.</span><span class="sxs-lookup"><span data-stu-id="0aec1-110">This `SELECT` clause is the same to an ordinary MDX `SELECT` statement, except that in the `SELECT` clause only one member can be specified on each axis.</span></span> <span data-ttu-id="0aec1-111">Si plusieurs membres sont spécifiés sur un axe, une erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="0aec1-111">If more than one member is specified on an axis, an error occurs.</span></span>  
  
 <span data-ttu-id="0aec1-112">La syntaxe `<Max_Rows>` spécifie le nombre maximum de lignes de chaque ensemble de lignes retourné.</span><span class="sxs-lookup"><span data-stu-id="0aec1-112">The `<Max_Rows>` syntax specifies the maximum number of the rows in each returned rowset.</span></span> <span data-ttu-id="0aec1-113">Si le fournisseur OLE DB utilisé pour la connexion à la source de données ne prend pas en charge `DBPROP_MAXROWS`, le paramètre `<Max_Rows>` est ignoré.</span><span class="sxs-lookup"><span data-stu-id="0aec1-113">If the OLE DB provider that is used to connect to the data source does not support `DBPROP_MAXROWS`, the `<Max_Rows>` setting is ignored.</span></span>  
  
 <span data-ttu-id="0aec1-114">La syntaxe `<First_Rowset>` identifie la partition d’où l’ensemble de lignes est d’abord retourné.</span><span class="sxs-lookup"><span data-stu-id="0aec1-114">The `<First_Rowset>` syntax identifies the partition whose rowset is returned first.</span></span>  
  
 <span data-ttu-id="0aec1-115">La syntaxe `<Return_Columns>` identifie les colonnes de la base de données sous-jacente à retourner.</span><span class="sxs-lookup"><span data-stu-id="0aec1-115">The `<Return_Columns>` syntax identifies the underlying database columns to be returned.</span></span>  
  
## <a name="drillthrough-statement-example"></a><span data-ttu-id="0aec1-116">Exemple d'instruction DRILLTHROUGH</span><span class="sxs-lookup"><span data-stu-id="0aec1-116">DRILLTHROUGH Statement Example</span></span>  
 <span data-ttu-id="0aec1-117">L'exemple suivant illustre l'utilisation de l'instruction `DRILLTHROUGH`.</span><span class="sxs-lookup"><span data-stu-id="0aec1-117">The following example demonstrates the use of the `DRILLTHROUGH` statement.</span></span> <span data-ttu-id="0aec1-118">Dans cet exemple, l'instruction DRILLTHROUGH interroge les feuilles des dimensions Store, Product et Time le long de la dimension Stores (axe de découpage), puis retourne le groupe de mesures du service, l'ID de service et le prénom de l'employé.</span><span class="sxs-lookup"><span data-stu-id="0aec1-118">In this example, the DRILLTHROUGH statement queries the leaves of the Store, Product, and Time dimensions along the Stores dimension (the slicer axis), and then returns the department measure group, department ID, and employee's first name.</span></span>  
  
```  
DRILLTHROUGH  
Select {Leaves(Store), Leaves(Product), Leaves(Time),*} on 0  
From Stores  
RETURN [Department MeasureGroup].[Department Id], [Employee].[First Name]  
```  
  
## <a name="see-also"></a><span data-ttu-id="0aec1-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0aec1-119">See Also</span></span>  
 [<span data-ttu-id="0aec1-120">Manipulation de données &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="0aec1-120">Manipulating Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-manipulating-data.md)  
  
  
