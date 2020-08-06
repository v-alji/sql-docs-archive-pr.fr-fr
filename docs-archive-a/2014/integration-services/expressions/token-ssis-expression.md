---
title: TOKEN (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 9fdd06bf-5bc9-445c-95bf-709e0ca5989b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5c0598c3832e4bf6f838087be4fee541663c8bff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701346"
---
# <a name="token--ssis-expression"></a><span data-ttu-id="7a32f-102">TOKEN  (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="7a32f-102">TOKEN  (SSIS Expression)</span></span>
  <span data-ttu-id="7a32f-103">Retourne un jeton (sous-chaîne) à partir d'une chaîne en fonction des délimiteurs spécifiés qui séparent les jetons de la chaîne et du numéro de jeton qui indique le jeton à retourner.</span><span class="sxs-lookup"><span data-stu-id="7a32f-103">Returns a token (substring) from a string based on the specified delimiters that separate tokens in the string and the number of the token that denotes which token to be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a32f-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="7a32f-104">Syntax</span></span>  
  
```  
TOKEN(character_expression, delimiter_string, occurrence)  
```  
  
## <a name="arguments"></a><span data-ttu-id="7a32f-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="7a32f-105">Arguments</span></span>  
 <span data-ttu-id="7a32f-106">*expression_caractère*</span><span class="sxs-lookup"><span data-stu-id="7a32f-106">*character_expression*</span></span>  
 <span data-ttu-id="7a32f-107">Chaîne qui contient des jetons séparés par des délimiteurs.</span><span class="sxs-lookup"><span data-stu-id="7a32f-107">A string that contains tokens separated by delimiters.</span></span>  
  
 <span data-ttu-id="7a32f-108">*delimiter_string*</span><span class="sxs-lookup"><span data-stu-id="7a32f-108">*delimiter_string*</span></span>  
 <span data-ttu-id="7a32f-109">Chaîne qui contient les caractères de délimitation.</span><span class="sxs-lookup"><span data-stu-id="7a32f-109">A string that contains delimiter characters.</span></span> <span data-ttu-id="7a32f-110">Par exemple, « ; , » contient trois caractères de délimitation : le point-virgule, un espace vide et une virgule.</span><span class="sxs-lookup"><span data-stu-id="7a32f-110">For example, "; ," contains three delimiter characters semi-colon, a blank space, and a comma.</span></span>  
  
 <span data-ttu-id="7a32f-111">*occurrence*</span><span class="sxs-lookup"><span data-stu-id="7a32f-111">*occurrence*</span></span>  
 <span data-ttu-id="7a32f-112">Entier signé ou non signé qui spécifie le jeton à retourner.</span><span class="sxs-lookup"><span data-stu-id="7a32f-112">A signed or unsigned integer that specifies the token to be returned.</span></span> <span data-ttu-id="7a32f-113">Par exemple, si vous spécifiez 3 comme valeur pour ce paramètre, le troisième jeton de la chaîne est retourné.</span><span class="sxs-lookup"><span data-stu-id="7a32f-113">For example, if you specify 3 as a value for this parameter, the third token in the string is returned.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="7a32f-114">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="7a32f-114">Result Types</span></span>  
 <span data-ttu-id="7a32f-115">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="7a32f-115">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a32f-116">Notes</span><span class="sxs-lookup"><span data-stu-id="7a32f-116">Remarks</span></span>  
 <span data-ttu-id="7a32f-117">Cette fonction fractionne la chaîne <character_expression> en un ensemble de jetons séparés par les délimiteurs spécifiés dans la chaîne <delimiter_string>, puis retourne le N-ième jeton, où N est le nombre d’occurrences du jeton spécifié par le paramètre \<occurrence>.</span><span class="sxs-lookup"><span data-stu-id="7a32f-117">This function splits up the <character_expression> string into a set of tokens separated by the delimiters specified in the <delimiter_string> and then returns the Nth token where N is the number of occurrence of the token specified by the \<occurrence> parameter.</span></span> <span data-ttu-id="7a32f-118">Consultez la section Exemples pour obtenir des exemples d'utilisation de cette fonction.</span><span class="sxs-lookup"><span data-stu-id="7a32f-118">See Examples section for sample usages of this function.</span></span>  
  
 <span data-ttu-id="7a32f-119">Les remarques suivantes s'appliquent à la fonction TOKEN :</span><span class="sxs-lookup"><span data-stu-id="7a32f-119">The following remarks apply to the TOKEN function:</span></span>  
  
-   <span data-ttu-id="7a32f-120">La chaîne de délimitation peut contenir un ou plusieurs caractères de délimitation.</span><span class="sxs-lookup"><span data-stu-id="7a32f-120">The delimiter string can contain one or more delimiter characters.</span></span>  
  
-   <span data-ttu-id="7a32f-121">Si la valeur du paramètre \<occurrence> est supérieure au nombre total de jetons présents dans la chaîne, la fonction retourne NULL.</span><span class="sxs-lookup"><span data-stu-id="7a32f-121">If the value of \<occurrence> parameter is higher than the total number of tokens in the string, the function returns NULL.</span></span>  
  
-   <span data-ttu-id="7a32f-122">Les délimiteurs de début sont ignorés.</span><span class="sxs-lookup"><span data-stu-id="7a32f-122">Leading delimiters are skipped.</span></span>  
  
-   <span data-ttu-id="7a32f-123">La fonction TOKEN fonctionne seulement avec le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="7a32f-123">TOKEN works only with the DT_WSTR data type.</span></span> <span data-ttu-id="7a32f-124">Un argument *character_expression* représentant un littéral de chaîne ou une colonne de données du type de données DT_STR est implicitement converti dans le type de données DT_WSTR avant que la fonction TOKEN ne soit exécutée.</span><span class="sxs-lookup"><span data-stu-id="7a32f-124">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before TOKEN performs its operation.</span></span> <span data-ttu-id="7a32f-125">Les autres types de données doivent être explicitement convertis vers le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="7a32f-125">Other data types must be explicitly cast to the DT_WSTR data type.</span></span>  
  
-   <span data-ttu-id="7a32f-126">La fonction TOKEN retourne un résultat Null si l'argument character_expression est Null.</span><span class="sxs-lookup"><span data-stu-id="7a32f-126">TOKEN returns a null result if the character_expression is null.</span></span>  
  
-   <span data-ttu-id="7a32f-127">Vous pouvez utiliser des variables et des colonnes comme valeurs de tous les arguments de l'expression.</span><span class="sxs-lookup"><span data-stu-id="7a32f-127">You can use variables and columns as values of all arguments in the expression.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="7a32f-128">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="7a32f-128">Expression Examples</span></span>  
 <span data-ttu-id="7a32f-129">Dans l’exemple suivant, la fonction TOKEN retourne « a ».</span><span class="sxs-lookup"><span data-stu-id="7a32f-129">In the following example, the TOKEN function returns "a".</span></span> <span data-ttu-id="7a32f-130">La chaîne « a little white dog » comprend 4 jetons (« a », « little », « white », « dog ») séparés par le délimiteur «   » (espace).</span><span class="sxs-lookup"><span data-stu-id="7a32f-130">The string "a little white dog" has 4 tokens "a", "little", "white", "dog" separated by the delimiter " " (space character).</span></span> <span data-ttu-id="7a32f-131">Le deuxième argument, une chaîne de délimitation, spécifie un seul délimiteur, l'espace, à utiliser dans le fractionnement de la chaîne d'entrée en jetons.</span><span class="sxs-lookup"><span data-stu-id="7a32f-131">The second argument, a delimiter string, specifies only one delimiter, the space character, to be used in splitting the input string into tokens.</span></span> <span data-ttu-id="7a32f-132">Le dernier argument, 1, indique le premier jeton à retourner.</span><span class="sxs-lookup"><span data-stu-id="7a32f-132">The last argument, 1, specifies that the first token to be returned.</span></span> <span data-ttu-id="7a32f-133">Le premier jeton est « a » dans cet exemple de chaîne.</span><span class="sxs-lookup"><span data-stu-id="7a32f-133">The first token is "a" in this sample string.</span></span>  
  
```  
TOKEN("a little white dog"," ",1)  
```  
  
 <span data-ttu-id="7a32f-134">Dans l'exemple suivant, la fonction TOKEN retourne « dog ».</span><span class="sxs-lookup"><span data-stu-id="7a32f-134">In the following example, the TOKEN function returns "dog".</span></span> <span data-ttu-id="7a32f-135">La chaîne de délimitation de cet exemple contient 5 délimiteurs.</span><span class="sxs-lookup"><span data-stu-id="7a32f-135">The delimiter string in this example contains 5 delimiters.</span></span> <span data-ttu-id="7a32f-136">La chaîne d’entrée contient 4 jetons : « a », « little », « white », « dog ».</span><span class="sxs-lookup"><span data-stu-id="7a32f-136">The input string contains 4 tokens: "a", "little", "white", "dog".</span></span>  
  
```  
TOKEN("a:little|white dog","| ,.:",4)  
```  
  
 <span data-ttu-id="7a32f-137">Dans l'exemple suivant, la fonction TOKEN retourne «   » (une chaîne vide), car il n'y a pas 99 jetons dans la chaîne.</span><span class="sxs-lookup"><span data-stu-id="7a32f-137">In the following example, the TOKEN function returns "" (an empty string) because there are no 99 tokens in the string.</span></span>  
  
```  
TOKEN("a little white dog"," ",99)  
```  
  
 <span data-ttu-id="7a32f-138">Dans l'exemple suivant, la fonction TOKEN retourne la chaîne complète.</span><span class="sxs-lookup"><span data-stu-id="7a32f-138">In the following example, the TOKEN function returns the full string.</span></span> <span data-ttu-id="7a32f-139">La fonction analyse la chaîne d'entrée à la recherche de délimiteurs et comme il n'y en a pas dans la chaîne, elle ajoute simplement la chaîne entière en tant que premier jeton.</span><span class="sxs-lookup"><span data-stu-id="7a32f-139">The function parses the input string for delimiters and since there are none in the string, it just adds the entire string as the first token.</span></span>  
  
```  
TOKEN("a little white dog","|",1)  
```  
  
 <span data-ttu-id="7a32f-140">Dans l’exemple suivant, la fonction TOKEN retourne « a ».</span><span class="sxs-lookup"><span data-stu-id="7a32f-140">In the following example, the TOKEN function returns "a".</span></span> <span data-ttu-id="7a32f-141">Elle ignore tous les espaces de début.</span><span class="sxs-lookup"><span data-stu-id="7a32f-141">It ignores all the leading space characters.</span></span>  
  
```  
TOKEN("        a little white dog", " ", 1)  
```  
  
 <span data-ttu-id="7a32f-142">Dans l'exemple suivant, la fonction TOKEN retourne l'année spécifiée dans une chaîne de date.</span><span class="sxs-lookup"><span data-stu-id="7a32f-142">In the following example, the TOKEN function returns the year from a date string.</span></span>  
  
```  
TOKEN("2009/01/01", "/"), 1  
```  
  
 <span data-ttu-id="7a32f-143">Dans l'exemple suivant, la fonction TOKEN retourne le nom de fichier figurant dans le chemin d'accès spécifié.</span><span class="sxs-lookup"><span data-stu-id="7a32f-143">In the following example, the TOKEN function returns the file name from the specified path.</span></span> <span data-ttu-id="7a32f-144">Par exemple, si la valeur de User::Path est « c:\program files\data\myfile.txt », la fonction TOKEN retourne « myfile.txt ».</span><span class="sxs-lookup"><span data-stu-id="7a32f-144">For example, if the value of User::Path is "c:\program files\data\myfile.txt", the TOKEN function returns "myfile.txt".</span></span> <span data-ttu-id="7a32f-145">La fonction TOKENCOUNT retourne 4 et la fonction TOKEN retourne le 4ème jeton, « myfile.txt ».</span><span class="sxs-lookup"><span data-stu-id="7a32f-145">The TOKENCOUNT function returns 4 and the TOKEN function return the 4th token, "myfile.txt".</span></span>  
  
```  
TOKEN(@[User::Path], "\\", TOKENCOUNT(@[User::Path], "\\"))  
```  
  
## <a name="see-also"></a><span data-ttu-id="7a32f-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7a32f-146">See Also</span></span>  
 [<span data-ttu-id="7a32f-147">Fonctions &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="7a32f-147">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
