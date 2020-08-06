---
title: TOKENCOUNT (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 1c0efed1-c2b3-4f20-a3a1-ad91283b7c0a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9068e4958570a0222bc8e1a4c90d34acc5bdf3dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701334"
---
# <a name="tokencount-ssis-expression"></a><span data-ttu-id="7da6b-102">TOKENCOUNT (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="7da6b-102">TOKENCOUNT (SSIS Expression)</span></span>
  <span data-ttu-id="7da6b-103">Retourne le nombre de jetons d'une chaîne qui contient des jetons séparés par les délimiteurs spécifiés.</span><span class="sxs-lookup"><span data-stu-id="7da6b-103">Returns the number of tokens in a string that contains tokens separated by the specified delimiters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7da6b-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="7da6b-104">Syntax</span></span>  
  
```  
TOKENCOUNT(character_expression, delimiter_string)  
```  
  
## <a name="arguments"></a><span data-ttu-id="7da6b-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="7da6b-105">Arguments</span></span>  
 <span data-ttu-id="7da6b-106">*expression_caractère*</span><span class="sxs-lookup"><span data-stu-id="7da6b-106">*character_expression*</span></span>  
 <span data-ttu-id="7da6b-107">Chaîne qui contient des jetons séparés par des délimiteurs.</span><span class="sxs-lookup"><span data-stu-id="7da6b-107">A string that contains tokens separated by delimiters.</span></span>  
  
 <span data-ttu-id="7da6b-108">*delimiter_string*</span><span class="sxs-lookup"><span data-stu-id="7da6b-108">*delimiter_string*</span></span>  
 <span data-ttu-id="7da6b-109">Chaîne qui contient les caractères de délimitation.</span><span class="sxs-lookup"><span data-stu-id="7da6b-109">A string that contains delimiter characters.</span></span> <span data-ttu-id="7da6b-110">Par exemple, « ; , » contient trois caractères de délimitation : le point-virgule, un espace vide et une virgule.</span><span class="sxs-lookup"><span data-stu-id="7da6b-110">For example, "; ," contains three delimiter characters semi-colon, a blank space, and a comma.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="7da6b-111">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="7da6b-111">Result Types</span></span>  
 <span data-ttu-id="7da6b-112">DT_I4</span><span class="sxs-lookup"><span data-stu-id="7da6b-112">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7da6b-113">Notes</span><span class="sxs-lookup"><span data-stu-id="7da6b-113">Remarks</span></span>  
 <span data-ttu-id="7da6b-114">Les remarques suivantes s'appliquent à la fonction TOKEN :</span><span class="sxs-lookup"><span data-stu-id="7da6b-114">The following remarks apply to the TOKEN function:</span></span>  
  
-   <span data-ttu-id="7da6b-115">La chaîne de délimitation peut contenir un ou plusieurs caractères de délimitation.</span><span class="sxs-lookup"><span data-stu-id="7da6b-115">The delimiter string can contain one or more delimiter characters.</span></span>  
  
-   <span data-ttu-id="7da6b-116">Les délimiteurs de début sont ignorés.</span><span class="sxs-lookup"><span data-stu-id="7da6b-116">Leading delimiters are skipped.</span></span>  
  
-   <span data-ttu-id="7da6b-117">TOKENCOUNT fonctionne uniquement avec le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="7da6b-117">TOKENCOUNT works only with the DT_WSTR data type.</span></span> <span data-ttu-id="7da6b-118">Un argument *character_expression* représentant un littéral de chaîne ou une colonne de données du type de données DT_STR est implicitement converti dans le type de données DT_WSTR avant que la fonction TOKEN ne soit exécutée.</span><span class="sxs-lookup"><span data-stu-id="7da6b-118">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before TOKEN performs its operation.</span></span> <span data-ttu-id="7da6b-119">Les autres types de données doivent être explicitement convertis vers le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="7da6b-119">Other data types must be explicitly cast to the DT_WSTR data type.</span></span>  
  
-   <span data-ttu-id="7da6b-120">TOKENCOUNT retourne 0 (zéro) si character_expression est Null.</span><span class="sxs-lookup"><span data-stu-id="7da6b-120">TOKENCOUNT returns 0 (zero) if the character_expression is null.</span></span>  
  
-   <span data-ttu-id="7da6b-121">Vous pouvez utiliser des variables et des colonnes en tant qu'arguments pour cette expression.</span><span class="sxs-lookup"><span data-stu-id="7da6b-121">You can use variables and columns as arguments for this expression.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="7da6b-122">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="7da6b-122">Expression Examples</span></span>  
 <span data-ttu-id="7da6b-123">Dans l’exemple suivant, la fonction TOKENCOUNT retourne 3, car la chaîne contient trois jetons : « 01 », « 12 », « 2011 ».</span><span class="sxs-lookup"><span data-stu-id="7da6b-123">In the following example, the TOKENCOUNT function returns 3 because the string contains three tokens: "01", "12", "2011".</span></span>  
  
```  
TOKENCOUNT("01/12/2011", "/")  
```  
  
 <span data-ttu-id="7da6b-124">Dans l’exemple suivant, la fonction TOKENCOUNT retourne 4, car il existe quatre jetons (« a », « little », « white », « dog »).</span><span class="sxs-lookup"><span data-stu-id="7da6b-124">In the following example, the TOKENCOUNT function returns 4 because there are four tokens ("a", "little", "white", "dog").</span></span>  
  
```  
TOKENCOUNT("a little white dog"," ")  
```  
  
 <span data-ttu-id="7da6b-125">Dans l’exemple suivant, la fonction TOKENCOUNT retourne 1.</span><span class="sxs-lookup"><span data-stu-id="7da6b-125">In the following example, the TOKENCOUNT function returns 1.</span></span> <span data-ttu-id="7da6b-126">La fonction analyse la chaîne d'entrée à la recherche de délimiteurs et comme il n'y en a pas dans la chaîne, elle ajoute simplement la chaîne entière en tant que premier jeton.</span><span class="sxs-lookup"><span data-stu-id="7da6b-126">The function parses the input string for delimiters and since there are none in the string, it just adds the entire string as the first token.</span></span>  
  
```  
TOKENCOUNT("a little white dog","|")  
```  
  
 <span data-ttu-id="7da6b-127">Dans l'exemple suivant, la fonction TOKENCOUNT retourne 4.</span><span class="sxs-lookup"><span data-stu-id="7da6b-127">In the following example, the TOKENCOUNT function returns 4.</span></span> <span data-ttu-id="7da6b-128">La chaîne de délimitation de cet exemple contient 5 délimiteurs.</span><span class="sxs-lookup"><span data-stu-id="7da6b-128">The delimiter string in this example contains 5 delimiters.</span></span> <span data-ttu-id="7da6b-129">La chaîne d’entrée contient 4 jetons : « a », « little », « white », « dog ».</span><span class="sxs-lookup"><span data-stu-id="7da6b-129">The input string contains 4 tokens: "a", "little", "white", "dog".</span></span>  
  
```  
TOKENCOUNT("a:little|white dog","| ,.:")  
```  
  
 <span data-ttu-id="7da6b-130">Dans l'exemple suivant, la fonction TOKENCOUNT retourne 4.</span><span class="sxs-lookup"><span data-stu-id="7da6b-130">In the following example, the TOKENCOUNT function returns 4.</span></span> <span data-ttu-id="7da6b-131">Elle ignore tous les espaces de début.</span><span class="sxs-lookup"><span data-stu-id="7da6b-131">It ignores all the leading space characters.</span></span>  
  
```  
TOKENCOUNT("        a little white dog", " ")  
```  
  
## <a name="see-also"></a><span data-ttu-id="7da6b-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7da6b-132">See Also</span></span>  
 [<span data-ttu-id="7da6b-133">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="7da6b-133">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
