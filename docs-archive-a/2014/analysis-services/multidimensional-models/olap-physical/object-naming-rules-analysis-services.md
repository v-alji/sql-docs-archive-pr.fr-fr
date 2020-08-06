---
title: Règles d’affectation des noms d’objets (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- objects [Analysis Services], naming
ms.assetid: b338a60d-4802-4b68-862a-6dc6a3f75e48
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6adfd4b23b6fe9129641271fc3c2381e161119ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612545"
---
# <a name="object-naming-rules-analysis-services"></a><span data-ttu-id="b4650-102">Règles d'attribution de noms aux objets (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="b4650-102">Object Naming Rules (Analysis Services)</span></span>
  <span data-ttu-id="b4650-103">Cette rubrique décrit les conventions d'attribution de noms aux objets, ainsi que les caractères et les mots réservés qui ne peuvent pas être utilisés dans un nom d'objet, dans le code ou dans un script dans [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4650-103">This topic describes object naming conventions, as well as the reserved words and characters that cannot be used in any object name, in code or script in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>  
  
##  <a name="naming-conventions"></a><a name="bkmk_Names"></a><span data-ttu-id="b4650-104">Conventions d’affectation des noms</span><span class="sxs-lookup"><span data-stu-id="b4650-104">Naming Conventions</span></span>  
 <span data-ttu-id="b4650-105">Chaque objet a une propriété `Name` et `ID` qui doit être unique dans l'étendue de la collection parente.</span><span class="sxs-lookup"><span data-stu-id="b4650-105">Every object has a `Name` and `ID` property that must be unique within the scope of the parent collection.</span></span> <span data-ttu-id="b4650-106">Par exemple, deux dimensions peuvent porter le même nom dans la mesure où chacune réside dans une base de données différente.</span><span class="sxs-lookup"><span data-stu-id="b4650-106">For example, two dimensions can have same name as long as each one resides in a different database.</span></span>  
  
 <span data-ttu-id="b4650-107">Bien que vous puissiez le spécifier manuellement, l'`ID` est en principe généré automatiquement lorsque l'objet est créé.</span><span class="sxs-lookup"><span data-stu-id="b4650-107">Although you can specify it manually, the `ID` is typically auto-generated when the object is created.</span></span> <span data-ttu-id="b4650-108">Vous ne devez jamais modifier l'`ID` une fois que vous avez démarré la création d'un modèle.</span><span class="sxs-lookup"><span data-stu-id="b4650-108">You should never change the `ID` once you have begun building a model.</span></span> <span data-ttu-id="b4650-109">Toutes les références d'objet d'un modèle sont basées sur l'`ID`.</span><span class="sxs-lookup"><span data-stu-id="b4650-109">All object references throughout a model are based on the `ID`.</span></span> <span data-ttu-id="b4650-110">Par conséquent, modifier un `ID` peut facilement provoquer une altération du modèle.</span><span class="sxs-lookup"><span data-stu-id="b4650-110">Thus, changing an `ID` can easily result in model corruption.</span></span>  
  
 <span data-ttu-id="b4650-111">Pour les objets `DataSource` et `DataSourceView`, des exceptions notables aux conventions d'affectation de noms s'appliquent.</span><span class="sxs-lookup"><span data-stu-id="b4650-111">`DataSource` and `DataSourceView` objects have notable exceptions to naming conventions.</span></span> <span data-ttu-id="b4650-112">L'ID `DataSource` peut être défini comme un seul point (.), non unique, comme référence à la base de données active.</span><span class="sxs-lookup"><span data-stu-id="b4650-112">`DataSource` ID can be set to a single dot (.), which is not unique, as a reference to the current database.</span></span> <span data-ttu-id="b4650-113">Une seconde exception concerne `DataSourceView`, qui adhère aux conventions d'affectation de noms définies pour les objets `DataSet` dans le .NET Framework, où `Name` est utilisé comme identifiant.</span><span class="sxs-lookup"><span data-stu-id="b4650-113">A second exception is `DataSourceView`, which adheres to the naming conventions defined for `DataSet` objects in the .NET Framework, where the `Name` is used as the identifier.</span></span>  
  
 <span data-ttu-id="b4650-114">Les règles suivantes s'appliquent aux propriétés `Name` et `ID`.</span><span class="sxs-lookup"><span data-stu-id="b4650-114">The following rules apply to `Name` and `ID` properties.</span></span>  
  
-   <span data-ttu-id="b4650-115">Les noms ne respectent pas la casse.</span><span class="sxs-lookup"><span data-stu-id="b4650-115">Names are case insensitive.</span></span> <span data-ttu-id="b4650-116">Vous ne pouvez pas avoir un cube nommé « ventes » et un autre nommé « ventes » dans la même base de données.</span><span class="sxs-lookup"><span data-stu-id="b4650-116">You cannot have a cube named "sales" and another named "Sales" in the same database.</span></span>  
  
-   <span data-ttu-id="b4650-117">Aucun espace de début ou de fin n'est autorisé dans un nom d'objet, bien que vous puissiez inclure des espaces dans un nom.</span><span class="sxs-lookup"><span data-stu-id="b4650-117">No leading or trailing spaces allowed in an object name, although you can embed spaces within a name.</span></span> <span data-ttu-id="b4650-118">Les espaces de début ou de fin sont tronqués implicitement.</span><span class="sxs-lookup"><span data-stu-id="b4650-118">Leading and trailing spaces are implicitly trimmed.</span></span> <span data-ttu-id="b4650-119">Cela s'applique à la fois à `Name` et à l'`ID` d'un objet.</span><span class="sxs-lookup"><span data-stu-id="b4650-119">This applies to both the `Name` and `ID` of an object.</span></span>  
  
-   <span data-ttu-id="b4650-120">Le nombre maximal de caractères autorisé est de 100.</span><span class="sxs-lookup"><span data-stu-id="b4650-120">The maximum number of characters is 100.</span></span>  
  
-   <span data-ttu-id="b4650-121">Il n'y a aucune spécification spéciale pour le premier caractère d'un identificateur.</span><span class="sxs-lookup"><span data-stu-id="b4650-121">There is no special requirement for the first character of an identifier.</span></span> <span data-ttu-id="b4650-122">Le premier caractère peut être tout caractère valide.</span><span class="sxs-lookup"><span data-stu-id="b4650-122">The first character may be any valid character.</span></span>  
  
##  <a name="reserved-words-and-characters"></a><a name="bkmk_reserved"></a><span data-ttu-id="b4650-123">Mots et caractères réservés</span><span class="sxs-lookup"><span data-stu-id="b4650-123">Reserved Words and Characters</span></span>  
 <span data-ttu-id="b4650-124">Les mots réservés sont en anglais et s'appliquent aux noms d'objet, pas aux légendes.</span><span class="sxs-lookup"><span data-stu-id="b4650-124">Reserved words are in English, and apply to object names, not Captions.</span></span> <span data-ttu-id="b4650-125">Si vous utilisez accidentellement un mot réservé dans un nom d'objet, une erreur de validation se produit.</span><span class="sxs-lookup"><span data-stu-id="b4650-125">If you inadvertently use a reserved word in an object name, a validation error will occur.</span></span> <span data-ttu-id="b4650-126">Pour les modèles d'exploration de données et multidimensionnels, les mots réservés décrits ci-dessous ne peuvent jamais être utilisés dans un nom d'objet.</span><span class="sxs-lookup"><span data-stu-id="b4650-126">For multidimensional and data mining models, the reserved words described below cannot be used in any object name, at any time.</span></span>  
  
 <span data-ttu-id="b4650-127">Pour les modèles tabulaires, où la compatibilité de la base de données est définie sur 1103, les règles de validation ont été assouplies pour certains objets et ne sont pas conformes aux critères de caractères étendus et de conventions d'attribution de noms de certaines applications clientes.</span><span class="sxs-lookup"><span data-stu-id="b4650-127">For tabular models, where the database compatibility is set to 1103, validation rules have been relaxed for certain objects, out of compliance for the extended character requirements and naming conventions of certain client applications.</span></span> <span data-ttu-id="b4650-128">Les bases de données qui répondent à ces critères sont soumises à des règles de validation moins rigoureuses.</span><span class="sxs-lookup"><span data-stu-id="b4650-128">Databases that meet these criteria are subject to less stringent validation rules.</span></span> <span data-ttu-id="b4650-129">Dans ce cas, un nom d'objet peut éventuellement inclure un caractère restreint et néanmoins être validé.</span><span class="sxs-lookup"><span data-stu-id="b4650-129">In this case, it's possible for an object name to include a restricted character and still pass validation.</span></span>  
  
 <span data-ttu-id="b4650-130">**Mots réservés**</span><span class="sxs-lookup"><span data-stu-id="b4650-130">**Reserved Words**</span></span>  
  
-   <span data-ttu-id="b4650-131">AUX</span><span class="sxs-lookup"><span data-stu-id="b4650-131">AUX</span></span>  
  
-   <span data-ttu-id="b4650-132">CLOCK$</span><span class="sxs-lookup"><span data-stu-id="b4650-132">CLOCK$</span></span>  
  
-   <span data-ttu-id="b4650-133">COM1 à COM9 (COM1, COM2, COM3, et ainsi de suite)</span><span class="sxs-lookup"><span data-stu-id="b4650-133">COM1 through COM9 (COM1, COM2, COM3, and so on)</span></span>  
  
-   <span data-ttu-id="b4650-134">CON</span><span class="sxs-lookup"><span data-stu-id="b4650-134">CON</span></span>  
  
-   <span data-ttu-id="b4650-135">LPT1 à LPT9 (LPT1, LPT2, LPT3, et ainsi de suite)</span><span class="sxs-lookup"><span data-stu-id="b4650-135">LPT1 through LPT9 (LPT1, LPT2, LPT3, and so on)</span></span>  
  
-   <span data-ttu-id="b4650-136">NUL</span><span class="sxs-lookup"><span data-stu-id="b4650-136">NUL</span></span>  
  
-   <span data-ttu-id="b4650-137">PRN</span><span class="sxs-lookup"><span data-stu-id="b4650-137">PRN</span></span>  
  
-   <span data-ttu-id="b4650-138">NULL n'est autorisé comme caractère dans aucune chaîne au sein de XML</span><span class="sxs-lookup"><span data-stu-id="b4650-138">NULL is not allowed as a character in any string within the XML</span></span>  
  
 <span data-ttu-id="b4650-139">**Caractères réservés**</span><span class="sxs-lookup"><span data-stu-id="b4650-139">**Reserved Characters**</span></span>  
  
 <span data-ttu-id="b4650-140">Le tableau ci-dessous répertorie les caractères non valides pour les objets spécifiques.</span><span class="sxs-lookup"><span data-stu-id="b4650-140">The following table lists invalid characters for specific objects.</span></span>  
  
|<span data-ttu-id="b4650-141">Object</span><span class="sxs-lookup"><span data-stu-id="b4650-141">Object</span></span>|<span data-ttu-id="b4650-142">Caractères non valides</span><span class="sxs-lookup"><span data-stu-id="b4650-142">Invalid characters</span></span>|  
|------------|------------------------|  
|`Server`|<span data-ttu-id="b4650-143">Suivez les conventions d'attribution des noms de serveur Windows lorsque vous nommez un objet serveur.</span><span class="sxs-lookup"><span data-stu-id="b4650-143">Follow Windows server naming conventions when naming a server object.</span></span> <span data-ttu-id="b4650-144">Pour plus d'informations, consultez [Conventions d'attribution des noms (Windows)](/windows/desktop/DNS/naming-conventions) .</span><span class="sxs-lookup"><span data-stu-id="b4650-144">See [Naming Conventions (Windows)](/windows/desktop/DNS/naming-conventions) for details.</span></span>|  
|`DataSource`| `: / \ * \| ? " () [] {} <>` |  
|<span data-ttu-id="b4650-145">`Level` ou `Attribute`</span><span class="sxs-lookup"><span data-stu-id="b4650-145">`Level` or `Attribute`</span></span>|````. , ; ' ` : / \ * & \| ? " & % $ ! + = [] {} < >````|  
|<span data-ttu-id="b4650-146">`Dimension` ou `Hierarchy`</span><span class="sxs-lookup"><span data-stu-id="b4650-146">`Dimension` or `Hierarchy`</span></span>|````. , ; ' ` : / \ * \| ? " & % $ ! + = () [] {} <,>````|  
|<span data-ttu-id="b4650-147">Tous les autres objets</span><span class="sxs-lookup"><span data-stu-id="b4650-147">All other objects</span></span>|````. , ; ' ` : / \ * \| ? " & % $ ! + = () [] {} < >````|  
  
 <span data-ttu-id="b4650-148">**Exceptions : Cas où les caractères réservés sont autorisés**</span><span class="sxs-lookup"><span data-stu-id="b4650-148">**Exceptions: When Reserved Characters are Allowed**</span></span>  
  
 <span data-ttu-id="b4650-149">Comme indiqué, les bases de données d'une modalité et d'un niveau de compatibilité spécifiques peuvent avoir des noms d'objet qui contiennent des caractères réservés.</span><span class="sxs-lookup"><span data-stu-id="b4650-149">As noted, databases of a specific modality and compatibility level can have object names that include reserved characters.</span></span> <span data-ttu-id="b4650-150">Un attribut de dimension, une hiérarchie, un niveau, une mesure et des noms d'objets d'indicateur de performance clé (KPI) peuvent comprendre des caractères réservés, pour les bases de données tabulaires (avec niveau de compatibilité supérieur ou égal à 1103) qui autorisent l'utilisation de caractères étendus :</span><span class="sxs-lookup"><span data-stu-id="b4650-150">Dimension attribute, hierarchy, level, measure and KPI object names can include reserved characters, for tabular databases (1103 or higher) that allow the use of extended characters:</span></span>  
  
|<span data-ttu-id="b4650-151">Mode serveur et niveau de compatibilité de la base de données</span><span class="sxs-lookup"><span data-stu-id="b4650-151">Server mode and database compatibility level</span></span>|<span data-ttu-id="b4650-152">Caractères réservés autorisés ?</span><span class="sxs-lookup"><span data-stu-id="b4650-152">Reserved characters allowed?</span></span>|  
|--------------------------------------------------|----------------------------------|  
|<span data-ttu-id="b4650-153">MOLAP (toutes les versions)</span><span class="sxs-lookup"><span data-stu-id="b4650-153">MOLAP (all versions)</span></span>|<span data-ttu-id="b4650-154">Non</span><span class="sxs-lookup"><span data-stu-id="b4650-154">No</span></span>|  
|<span data-ttu-id="b4650-155">Tabulaire - 1050</span><span class="sxs-lookup"><span data-stu-id="b4650-155">Tabular - 1050</span></span>|<span data-ttu-id="b4650-156">Non</span><span class="sxs-lookup"><span data-stu-id="b4650-156">No</span></span>|  
|<span data-ttu-id="b4650-157">Tabulaire - 1100</span><span class="sxs-lookup"><span data-stu-id="b4650-157">Tabular - 1100</span></span>|<span data-ttu-id="b4650-158">Non</span><span class="sxs-lookup"><span data-stu-id="b4650-158">No</span></span>|  
|<span data-ttu-id="b4650-159">Tabulaire-1130 et versions ultérieures</span><span class="sxs-lookup"><span data-stu-id="b4650-159">Tabular - 1130 and higher</span></span>|<span data-ttu-id="b4650-160">Oui</span><span class="sxs-lookup"><span data-stu-id="b4650-160">Yes</span></span>|  
  
 <span data-ttu-id="b4650-161">Les bases de données peuvent avoir un ModelType par défaut.</span><span class="sxs-lookup"><span data-stu-id="b4650-161">Databases can have a ModelType of default.</span></span> <span data-ttu-id="b4650-162">La valeur par défaut est équivalente à celle du mode multidimensionnel et ne prend donc pas en charge l'utilisation de caractères réservés dans les noms de colonnes.</span><span class="sxs-lookup"><span data-stu-id="b4650-162">Default is equivalent to multidimensional, and thus does not support the use of reserved characters in column names.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4650-163">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b4650-163">See Also</span></span>  
 <span data-ttu-id="b4650-164">[Mots réservés MDX](/sql/mdx/mdx-reserved-words) </span><span class="sxs-lookup"><span data-stu-id="b4650-164">[MDX Reserved Words](/sql/mdx/mdx-reserved-words) </span></span>  
 <span data-ttu-id="b4650-165">[Traductions &#40;Analysis Services&#41;](/analysis-services/translation-support-in-analysis-services) </span><span class="sxs-lookup"><span data-stu-id="b4650-165">[Translations &#40;Analysis Services&#41;](/analysis-services/translation-support-in-analysis-services) </span></span>  
 [<span data-ttu-id="b4650-166">Compatibilité XML for Analysis &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="b4650-166">XML for Analysis Compliance &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-compliance-xmla)  
  
  
