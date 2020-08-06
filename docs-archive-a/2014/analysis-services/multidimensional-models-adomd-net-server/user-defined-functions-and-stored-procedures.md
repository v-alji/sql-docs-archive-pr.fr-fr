---
title: Fonctions définies par l’utilisateur et procédures stockées | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- stored procedures [ADOMD.NET]
- ADOMD.NET, user defined functions
- user defined functions [ADOMD.NET]
- ADOMD.NET, UDFs
- ADOMD.NET, stored procedures
ms.assetid: 07e8aa47-37d4-4bbc-8bff-49e422d12897
author: minewiskan
ms.author: owend
ms.openlocfilehash: a49aa41d158bf2c9fd1ebb1a711d6ff35c0df98b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694803"
---
# <a name="user-defined-functions-and-stored-procedures"></a><span data-ttu-id="586d0-102">Fonctions définies par l'utilisateur et procédures stockées</span><span class="sxs-lookup"><span data-stu-id="586d0-102">User Defined Functions and Stored Procedures</span></span>
  <span data-ttu-id="586d0-103">Avec les objets serveur ADOMD.net, vous pouvez créer des fonctions définies par l’utilisateur (UDF) ou des procédures stockées pour [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] qui interagissent avec les métadonnées et les données du serveur.</span><span class="sxs-lookup"><span data-stu-id="586d0-103">With ADOMD.NET server objects, you can create user defined function (UDF) or stored procedures for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that interact with metadata and data from the server.</span></span> <span data-ttu-id="586d0-104">Ces méthodes in-process sont appelées au moyen d'instructions MDX (Multidimensional Expressions) ou DMX (Data Mining Extensions) pour fournir des fonctionnalités supplémentaires sans les temps d'attente inhérents aux communications réseau.</span><span class="sxs-lookup"><span data-stu-id="586d0-104">These in-process methods are called through Multidimensional Expressions (MDX) or Data Mining Extensions (DMX) statements to provide added functionality without the latencies associated with network communications.</span></span>  
  
## <a name="udf-examples"></a><span data-ttu-id="586d0-105">Exemples de fonctions définies par l'utilisateur (UDF)</span><span class="sxs-lookup"><span data-stu-id="586d0-105">UDF Examples</span></span>  
 <span data-ttu-id="586d0-106">Une fonction définie par l'utilisateur est une méthode qui peut être appelée dans le contexte d'une instruction MDX ou DMX, qui peut prendre un nombre illimité de paramètres et qui peut retourner tout type de données.</span><span class="sxs-lookup"><span data-stu-id="586d0-106">A UDF is a method that can be called in the context of an MDX or DMX statement, can take any number of parameters, and can return any type of data.</span></span>  
  
 <span data-ttu-id="586d0-107">Une fonction définie par l'utilisateur créée à l'aide de MDX est semblable à une fonction définie par l'utilisateur créée pour DMX.</span><span class="sxs-lookup"><span data-stu-id="586d0-107">A UDF created using MDX is similar to one created for DMX.</span></span> <span data-ttu-id="586d0-108">La principale différence réside dans le fait que certaines propriétés de l’objet [Microsoft. AnalysisServices. AdomdServer. Context](/previous-versions/sql/sql-server-2014/ms143353(v=sql.120)) , telles que les propriétés [Microsoft. AnalysisServices. AdomdServer. Context. CurrentCube \*](/previous-versions/sql/sql-server-2014/ms137081(v=sql.120)) et [Microsoft. AnalysisServices. AdomdServer. Context. CurrentMiningModel \*](/previous-versions/sql/sql-server-2014/ms137178(v=sql.120)) , sont uniquement disponibles pour un langage de script ou l’autre.</span><span class="sxs-lookup"><span data-stu-id="586d0-108">The main difference is that certain properties of the [Microsoft.AnalysisServices.AdomdServer.Context](/previous-versions/sql/sql-server-2014/ms143353(v=sql.120)) object, such as the [Microsoft.AnalysisServices.AdomdServer.Context.CurrentCube\*](/previous-versions/sql/sql-server-2014/ms137081(v=sql.120)) and [Microsoft.AnalysisServices.AdomdServer.Context.CurrentMiningModel\*](/previous-versions/sql/sql-server-2014/ms137178(v=sql.120)) properties, are available only for one scripting language or the other.</span></span>  
  
 <span data-ttu-id="586d0-109">Les exemples suivants indiquent comment utiliser une fonction définie par l'utilisateur pour retourner une description de nœud, filtrer des tuples et appliquer un filtre à un tuple.</span><span class="sxs-lookup"><span data-stu-id="586d0-109">The following examples show how to use a UDF to return a node description, filter tuples, and apply a filter to a tuple.</span></span>  
  
### <a name="returning-a-node-description"></a><span data-ttu-id="586d0-110">Retour d'une description de nœud</span><span class="sxs-lookup"><span data-stu-id="586d0-110">Returning a Node Description</span></span>  
 <span data-ttu-id="586d0-111">L'exemple suivant crée une fonction définie par l'utilisateur chargée de retourner la description d'un nœud spécifié.</span><span class="sxs-lookup"><span data-stu-id="586d0-111">The following example creates a UDF that returns the node description for a specified node.</span></span> <span data-ttu-id="586d0-112">La fonction définie par l'utilisateur utilise le contexte dans lequel elle est exécutée et emploie une clause DMX FROM pour récupérer le nœud à partir du modèle d'exploration de données actif.</span><span class="sxs-lookup"><span data-stu-id="586d0-112">The UDF uses the current context in which it is being run, and uses a DMX FROM clause to retrieve the node from the current mining model.</span></span>  
  
```  
public string GetNodeDescription(string nodeUniqueName)  
{  
   return Context.CurrentMiningModel.GetNodeFromUniqueName(nodeUniqueName).Description;  
}  
```  
  
 <span data-ttu-id="586d0-113">Une fois déployée, la fonction définie par l'utilisateur de l'exemple précédent peut être appelée à l'aide de l'expression DMX ci-dessous, qui récupère le nœud de prédiction le plus probable.</span><span class="sxs-lookup"><span data-stu-id="586d0-113">Once deployed, the previous UDF example can be called by the following DMX expression, which retrieves the most-likely prediction node.</span></span> <span data-ttu-id="586d0-114">La description contient des informations qui décrivent les conditions rattachées au nœud de prédiction.</span><span class="sxs-lookup"><span data-stu-id="586d0-114">The description contains information that describes the conditions that make up the prediction node.</span></span>  
  
```  
select Cluster(), SampleAssembly.GetNodeDescription( PredictNodeId(Cluster()) ) FROM [Customer Clusters]  
```  
  
### <a name="returning-tuples"></a><span data-ttu-id="586d0-115">Retour de tuples</span><span class="sxs-lookup"><span data-stu-id="586d0-115">Returning Tuples</span></span>  
 <span data-ttu-id="586d0-116">En s'appuyant sur un ensemble et un nombre retourné, l'exemple suivant récupère aléatoirement des tuples de l'ensemble, retournant ainsi un sous-ensemble final :</span><span class="sxs-lookup"><span data-stu-id="586d0-116">The following example takes a set and a return count, and randomly retrieves tuples from the set, returning a final subset:</span></span>  
  
```  
public Set RandomSample(Set set, int returnCount)  
{  
   //Return the original set if there are fewer tuples  
   //in the set than the number requested.  
   if (set.Tuples.Count <= returnCount)  
      return set;  
  
   System.Random r = new System.Random();  
   SetBuilder returnSet = new SetBuilder();  
  
   //Retrieve random tuples until the return set is filled.  
   int i = set.Tuples.Count;  
   foreach (Tuple t in set.Tuples)  
   {  
      if (r.Next(i) < returnCount)  
      {  
         returnCount--;  
         returnSet.Add(t);  
      }  
      i--;  
      //Stop the loop if we have enough tuples.  
      if (returnCount == 0)  
         break;  
   }  
   return returnSet.ToSet();  
}  
```  
  
 <span data-ttu-id="586d0-117">L'exemple précédent est appelé dans l'exemple MDX suivant.</span><span class="sxs-lookup"><span data-stu-id="586d0-117">The previous example is called in the following MDX example.</span></span> <span data-ttu-id="586d0-118">Dans cet exemple MDX, cinq États ou provinces aléatoires sont récupérés à partir de la base de données **Adventure Works** .</span><span class="sxs-lookup"><span data-stu-id="586d0-118">In this MDX example, five random states or provinces are retrieved from the **Adventure Works** database.</span></span>  
  
```  
SELECT SampleAssembly.RandomSample([Geography].[State-Province].Members, 5) on ROWS,   
[Date].[Calendar].[Calendar Year] on COLUMNS  
FROM [Adventure Works]  
WHERE [Measures].[Reseller Freight Cost]  
```  
  
### <a name="applying-a-filter-to-a-tuple"></a><span data-ttu-id="586d0-119">Application d'un filtre à un tuple</span><span class="sxs-lookup"><span data-stu-id="586d0-119">Applying a Filter to a Tuple</span></span>  
 <span data-ttu-id="586d0-120">Dans l'exemple suivant, la fonction définie par l'utilisateur prend un ensemble et applique un filtre à chaque tuple de l'ensemble en utilisant l'objet Expression.</span><span class="sxs-lookup"><span data-stu-id="586d0-120">In the following example, a UDF is defined that takes a set, and applies a filter to each tuple in the set, using the Expression object.</span></span> <span data-ttu-id="586d0-121">Les tuples qui sont conformes au filtre sont ajoutés à l'ensemble retourné.</span><span class="sxs-lookup"><span data-stu-id="586d0-121">Any tuples that conform to the filter will be added to a set that is returned.</span></span>  
  
 [!code-csharp[Adomd.NetServer#FilterSet](../../snippets/csharp/SQL14/adomd.net/adomd.netserver/cs/class1.cs#filterset)]  
  
 <span data-ttu-id="586d0-122">L'exemple précédent est appelé dans l'exemple MDX ci-dessous, dont le filtre porte sur les noms de ville commençant par la lettre A.</span><span class="sxs-lookup"><span data-stu-id="586d0-122">The previous example is called in the following MDX example, which filters the set to cities with names beginning with 'A'.</span></span>  
  
```  
Select Measures.Members on Rows,  
SampleAssembly.FilterSet([Customer].[Customer Geography].[City], "[Customer].[Customer Geography].[City].CurrentMember.Name < 'B'") on Columns  
From [Adventure Works]  
```  
  
## <a name="stored-procedure-example"></a><span data-ttu-id="586d0-123">Exemple de procédure stockée</span><span class="sxs-lookup"><span data-stu-id="586d0-123">Stored Procedure Example</span></span>  
 <span data-ttu-id="586d0-124">Dans l'exemple suivant, une procédure stockée MDX utilise AMO pour créer, si nécessaire, des partitions pour Internet Sales.</span><span class="sxs-lookup"><span data-stu-id="586d0-124">In the following example, an MDX-based stored procedure uses AMO to create partitions, if needed, for Internet Sales.</span></span>  
  
 [!code-csharp[Adomd.NetServer#CreateInternetSalesMeasureGroupPartitions](../../snippets/csharp/SQL14/adomd.net/adomd.netserver/cs/class1.cs#createinternetsalesmeasuregrouppartitions)]  
  
  
