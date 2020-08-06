---
title: REPLACENULL (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 70db7832-b5a0-4db5-a8ad-42ad8630d8e8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f10bb6ef6102076fe7b1cc236461e2358ad96372
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701418"
---
# <a name="replacenull-ssis-expression"></a><span data-ttu-id="f4546-102">REPLACENULL (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="f4546-102">REPLACENULL (SSIS Expression)</span></span>
  <span data-ttu-id="f4546-103">Retourne la valeur du paramètre de la seconde expression si la valeur du paramètre de la première expression est NULL ; sinon, retourne la valeur de la première expression.</span><span class="sxs-lookup"><span data-stu-id="f4546-103">Returns the value of second expression parameter if the value of first expression parameter is NULL; otherwise, returns the value of first expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4546-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f4546-104">Syntax</span></span>  
  
```vb  
REPLACENULL(expression 1,expression 2)  
```  
  
## <a name="arguments"></a><span data-ttu-id="f4546-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="f4546-105">Arguments</span></span>  
 <span data-ttu-id="f4546-106">*expression 1*</span><span class="sxs-lookup"><span data-stu-id="f4546-106">*expression 1*</span></span>  
 <span data-ttu-id="f4546-107">Le résultat de cette expression est comparé à NULL.</span><span class="sxs-lookup"><span data-stu-id="f4546-107">The result of this expression is checked against NULL.</span></span>  
  
 <span data-ttu-id="f4546-108">*expression 2*</span><span class="sxs-lookup"><span data-stu-id="f4546-108">*expression 2*</span></span>  
 <span data-ttu-id="f4546-109">Le résultat de cette expression est retourné si la première expression renvoie la valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="f4546-109">The result of this expression is returned if the first expression evaluates to NULL.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="f4546-110">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="f4546-110">Result Types</span></span>  
 <span data-ttu-id="f4546-111">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="f4546-111">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4546-112">Notes</span><span class="sxs-lookup"><span data-stu-id="f4546-112">Remarks</span></span>  
  
-   <span data-ttu-id="f4546-113">La longueur de l'argument *expression 2* peut être égale à zéro.</span><span class="sxs-lookup"><span data-stu-id="f4546-113">The length of *expression 2* may be zero.</span></span>  
  
-   <span data-ttu-id="f4546-114">La fonction REPLACENULL renvoie un résultat NULL si un argument est NULL.</span><span class="sxs-lookup"><span data-stu-id="f4546-114">REPLACENULL returns a null result if any argument is null.</span></span>  
  
-   <span data-ttu-id="f4546-115">Les colonnes BLOB (DT_TEXT, DT_NTEXT, DT_IMAGE) ne sont pas prises en charge pour l'un ou l'autre paramètre.</span><span class="sxs-lookup"><span data-stu-id="f4546-115">BLOB columns (DT_TEXT, DT_NTEXT, DT_IMAGE) are not supported for either parameter.</span></span>  
  
-   <span data-ttu-id="f4546-116">Il est prévu que les deux expressions aient le même type de retour.</span><span class="sxs-lookup"><span data-stu-id="f4546-116">The two expressions are expected to have the same return type.</span></span> <span data-ttu-id="f4546-117">Dans le cas contraire, la fonction tente d'effectuer un cast de la seconde expression en type de retour de la première expression, ce qui peut se traduire par une erreur si les types de données sont incompatibles.</span><span class="sxs-lookup"><span data-stu-id="f4546-117">If they do not, the function attempts to cast the 2nd expression to the return type of the 1st expression, which may result in an error if the data types are incompatible.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="f4546-118">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="f4546-118">Expression Examples</span></span>  
 <span data-ttu-id="f4546-119">L'exemple suivant remplace toute valeur NULL dans une colonne de base de données par une chaîne (1900-01-01).</span><span class="sxs-lookup"><span data-stu-id="f4546-119">The following example replaces any NULL value in a database column with a string (1900-01-01).</span></span> <span data-ttu-id="f4546-120">Cette fonction est particulièrement utilisée dans les modèles de colonne dérivée courants où vous souhaitez remplacer les valeurs NULL par autre chose.</span><span class="sxs-lookup"><span data-stu-id="f4546-120">This function is especially used in common Derived Column patterns where you want to replace NULL values with something else.</span></span>  
  
```  
REPLACENULL(MyColumn, "1900-01-01")  
```  
  
> [!NOTE]  
>  <span data-ttu-id="f4546-121">Vous trouverez ci-après un exemple d’utilisation dans [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)]/[!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4546-121">The following example shows how it was done in [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)]/[!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)].</span></span>  
  
```  
(DT_DBTIMESTAMP) (ISNULL(MyColumn) ? "1900-01-01" : MyColumn)   
```  
  
  
