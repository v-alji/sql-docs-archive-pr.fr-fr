---
title: Appel de procédures stockées | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- calling stored procedures
- stored procedures [Analysis Services], calling
- MDX queries [Analysis Services]
- CALL statement
ms.assetid: 96a9660d-875b-4ee4-b339-90020b1d9895
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5c9da6edef576a6ab25c183cbc87ff95cc056845
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700440"
---
# <a name="calling-stored-procedures"></a><span data-ttu-id="a2e20-102">Appel des procédures stockées</span><span class="sxs-lookup"><span data-stu-id="a2e20-102">Calling Stored Procedures</span></span>
  <span data-ttu-id="a2e20-103">Les procédures stockées peuvent être appelées sur le serveur ou à partir d'une application cliente.</span><span class="sxs-lookup"><span data-stu-id="a2e20-103">Stored procedures can be called on the server or from client application.</span></span> <span data-ttu-id="a2e20-104">Dans les deux cas, les procédures stockées s'exécutent toujours sur le serveur, soit dans le contexte du serveur, soit dans le contexte d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="a2e20-104">In either case, stored procedures always run on the server, either the context of the server or of a database.</span></span> <span data-ttu-id="a2e20-105">Aucune autorisation spéciale n'est requise pour exécuter une procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="a2e20-105">There are no special permissions required to execute a stored procedure.</span></span> <span data-ttu-id="a2e20-106">Lorsqu'une procédure stockée est ajoutée par un assembly dans le contexte du serveur ou de la base de données, tous les utilisateurs peuvent l'exécuter, à condition que leur rôle autorise les actions qu'elle effectue.</span><span class="sxs-lookup"><span data-stu-id="a2e20-106">Once a stored procedure is added by an assembly to the server or database context, any user can execute the stored procedure as long as the role for the user permits the actions performed by the stored procedure.</span></span>  
  
 <span data-ttu-id="a2e20-107">L'appel d'une procédure stockée via MDX s'effectue de la même façon que l'appel d'une fonction MDX intrinsèque.</span><span class="sxs-lookup"><span data-stu-id="a2e20-107">Calling a stored procedure in MDX is done in the same manner as calling an intrinsic MDX function.</span></span> <span data-ttu-id="a2e20-108">Pour une procédure stockée n'acceptant pas de paramètres, le nom de la procédure et une paire de parenthèses vide sont utilisés, comme ci-après :</span><span class="sxs-lookup"><span data-stu-id="a2e20-108">For a stored procedure that takes no parameters, the name of the procedure and an empty pair of parentheses are used, as shown here:</span></span>  
  
```  
MyStoredProcedure()  
```  
  
 <span data-ttu-id="a2e20-109">Si la procédure stockée accepte un ou plusieurs paramètres, ces derniers sont fournis, dans l'ordre, séparés par des virgules.</span><span class="sxs-lookup"><span data-stu-id="a2e20-109">If the stored procedure takes one or more parameters, then the parameters are supplied, in order, separated by commas.</span></span> <span data-ttu-id="a2e20-110">L'exemple suivant montre un exemple de procédure stockée incluant trois paramètres :</span><span class="sxs-lookup"><span data-stu-id="a2e20-110">The following example demonstrates a sample stored procedure with three parameters:</span></span>  
  
```  
MyStoredProcedure("Parameter1", 2, 800)  
```  
  
## <a name="calling-stored-procedures-in-mdx-queries"></a><span data-ttu-id="a2e20-111">Appel de procédures stockées dans les requêtes MDX</span><span class="sxs-lookup"><span data-stu-id="a2e20-111">Calling Stored Procedures in MDX Queries</span></span>  
 <span data-ttu-id="a2e20-112">Dans toutes les requêtes MDX, la procédure stockée doit retourner le type correct du point de vue de la syntaxe requis par une expression MDX.</span><span class="sxs-lookup"><span data-stu-id="a2e20-112">In all MDX queries, the stored procedure must return the syntactically correct type required by an MDX expression.</span></span> <span data-ttu-id="a2e20-113">Si une procédure stockée ne retourne pas le type correct, une erreur MDX se produit.</span><span class="sxs-lookup"><span data-stu-id="a2e20-113">If a stored procedure does not return the correct type, an MDX error occurs.</span></span> <span data-ttu-id="a2e20-114">Les exemples suivants présentent des procédures stockées qui retournent un jeu, un membre et le résultat d'une opération mathématique.</span><span class="sxs-lookup"><span data-stu-id="a2e20-114">The following examples demonstrate stored procedures that return a set, a member, and the result of a mathematical operation.</span></span>  
  
### <a name="returning-a-set"></a><span data-ttu-id="a2e20-115">Retour d'un jeu</span><span class="sxs-lookup"><span data-stu-id="a2e20-115">Returning a Set</span></span>  
 <span data-ttu-id="a2e20-116">Les exemples suivants implémentent une procédure stockée, nommée MySproc, qui retourne un jeu.</span><span class="sxs-lookup"><span data-stu-id="a2e20-116">The following examples implement a stored procedure, called MySproc, that returns a set.</span></span> <span data-ttu-id="a2e20-117">Dans le premier exemple, MySproc retourne directement le jeu dans l'expression SELECT.</span><span class="sxs-lookup"><span data-stu-id="a2e20-117">In the first example, MySproc returns the set directly in the SELECT expression.</span></span> <span data-ttu-id="a2e20-118">Dans les deux autres exemples, MySproc retourne le jeu comme un argument pour les fonctions Crossjoin et DrilldownLevel.</span><span class="sxs-lookup"><span data-stu-id="a2e20-118">In the second two examples, MySproc returns the set as an argument for the Crossjoin and DrilldownLevel functions.</span></span>  
  
```  
SELECT MySetProcedure(a,b,c) ON 0 FROM Sales  
SELECT Crossjoin(MySetProcedure(a,b,c)) ON 0 FROM Sales  
SELECT DrilldownLevel(MySetProcedure(a,b,c)) ON 0 FROM Sales  
```  
  
### <a name="returning-a-member"></a><span data-ttu-id="a2e20-119">Retour d'un membre</span><span class="sxs-lookup"><span data-stu-id="a2e20-119">Returning a Member</span></span>  
 <span data-ttu-id="a2e20-120">L'exemple suivant montre une fonction MySproc qui retourne un membre :</span><span class="sxs-lookup"><span data-stu-id="a2e20-120">The following example shows a function MySproc function that returns a member:</span></span>  
  
```  
SELECT Descendants(MySproc(a,b,c),3) ON 0 FROM Sales  
```  
  
### <a name="returning-the-result-of-a-math-operation"></a><span data-ttu-id="a2e20-121">Retour du résultat d'une opération mathématique</span><span class="sxs-lookup"><span data-stu-id="a2e20-121">Returning the Result of a Math Operation</span></span>  
  
```  
SELECT Country.Members on 0, MySproc(Measures.Sales) ON 1 FROM Sales  
```  
  
## <a name="calling-stored-procedures-with-the-call-statement"></a><span data-ttu-id="a2e20-122">Appel de procédures stockées avec l'instruction Call</span><span class="sxs-lookup"><span data-stu-id="a2e20-122">Calling Stored Procedures with the Call Statement</span></span>  
 <span data-ttu-id="a2e20-123">Les procédures stockées peuvent être appelées en dehors du contexte d'une requête MDX à l'aide de l'instruction `Call` MDX.</span><span class="sxs-lookup"><span data-stu-id="a2e20-123">Stored procedures can be called outside of the context of an MDX query using the MDX `Call` statement.</span></span>  
  
 <span data-ttu-id="a2e20-124">Vous pouvez utiliser cette méthode pour instancier les effets secondaires d'une requête stockée ou pour que l'application obtienne les résultats d'une requête stockée.</span><span class="sxs-lookup"><span data-stu-id="a2e20-124">You can use this method to either instantiate the side effects of a stored query or for the application to get the results of a stored query.</span></span> <span data-ttu-id="a2e20-125">L'instruction `Call` est souvent utilisée pour que les objets AMO (Analysis Management Objects) effectuent les fonctions d'administration qui n'ont pas de résultat de retour.</span><span class="sxs-lookup"><span data-stu-id="a2e20-125">A common use of the `Call` statement would be to use Analysis Management Objects (AMO) to perform administrative functions that do not have a return result.</span></span> <span data-ttu-id="a2e20-126">Par exemple, la commande suivante appelle une procédure stockée :</span><span class="sxs-lookup"><span data-stu-id="a2e20-126">For example, the following command calls a stored procedure:</span></span>  
  
```  
Call MyStoredProcedure(a,b,c)  
```  
  
 <span data-ttu-id="a2e20-127">Le seul type pris en charge retourné à partir d'une procédure stockée dans une instruction `Call` est un ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="a2e20-127">The only supported type returned from stored procedure in a `Call` statement is a rowset.</span></span> <span data-ttu-id="a2e20-128">La sérialisation pour un ensemble de lignes est définie par XML for Analysis.</span><span class="sxs-lookup"><span data-stu-id="a2e20-128">The serialization for a rowset is defined by XML for Analysis.</span></span> <span data-ttu-id="a2e20-129">Si une procédure stockée dans une instruction `Call` retourne un autre type, il est ignoré et n'est pas retourné en XML à l'application appelante.</span><span class="sxs-lookup"><span data-stu-id="a2e20-129">If a stored procedure in a `Call` statement returns any other type, it is ignored and not returned in XML to the calling application.</span></span> <span data-ttu-id="a2e20-130">Pour plus d'informations sur les ensembles de lignes de XML for Analysis, consultez Ensembles de lignes de schéma XML for Analysis.</span><span class="sxs-lookup"><span data-stu-id="a2e20-130">For more information about XML for Analysis rowsets, see, XML for Analysis Schema Rowsets.</span></span>  
  
 <span data-ttu-id="a2e20-131">Si une procédure stockée retourne un ensemble de lignes .NET, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] convertit le résultat sur le serveur en ensemble de lignes XML for Analysis.</span><span class="sxs-lookup"><span data-stu-id="a2e20-131">If a stored procedure returns a .NET rowset, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] converts the result on the server to an XML for Analysis rowset.</span></span> <span data-ttu-id="a2e20-132">L'ensemble de lignes XML for Analysis est toujours retourné par une procédure stockée dans la fonction `Call`.</span><span class="sxs-lookup"><span data-stu-id="a2e20-132">The XML for Analysis rowset is always returned by a stored procedure in the `Call` function.</span></span> <span data-ttu-id="a2e20-133">Si un dataset contient des fonctionnalités qui ne peuvent pas être exprimées dans l'ensemble de lignes XML for Analysis, un échec se produit.</span><span class="sxs-lookup"><span data-stu-id="a2e20-133">If a dataset contains features that cannot be expressed in the XML for Analysis rowset, a failure results.</span></span>  
  
 <span data-ttu-id="a2e20-134">Les procédures qui retournent des valeurs void (par exemple, des sous-routines dans Visual Basic) peuvent également être employées avec le mot clé CALL.</span><span class="sxs-lookup"><span data-stu-id="a2e20-134">Procedures that return void values (for example, subroutines in Visual Basic) can also be employed with the CALL keyword.</span></span> <span data-ttu-id="a2e20-135">Si, par exemple, vous souhaitez utiliser la fonction MyVoidFunction() dans une instruction MDX, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="a2e20-135">If, for example, you wanted to use the function MyVoidFunction() in an MDX statement, the following syntax would be employed:</span></span>  
  
```  
CALL(MyVoidFunction)  
```  
  
## <a name="see-also"></a><span data-ttu-id="a2e20-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a2e20-136">See Also</span></span>  
 <span data-ttu-id="a2e20-137">[Gestion des assemblys de modèles multidimensionnels](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="a2e20-137">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="a2e20-138">Définition de procédures stockées</span><span class="sxs-lookup"><span data-stu-id="a2e20-138">Defining Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)  
  
  
