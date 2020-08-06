---
title: Table de caractères, transformation | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.charactertrans.f1
helpviewer_keywords:
- mutually exclusive mapping [Integration Services]
- mapping data [Integration Services]
- string functions
- Character Map transformation [Integration Services]
ms.assetid: e0f50eb6-b893-400f-bb8c-fb3072cc2620
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b5fc31e1a3500a7a7b023e43a968e70e5b438dec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611199"
---
# <a name="character-map-transformation"></a><span data-ttu-id="a5993-102">Transformation de la table de caractères</span><span class="sxs-lookup"><span data-stu-id="a5993-102">Character Map Transformation</span></span>
  <span data-ttu-id="a5993-103">La transformation de la table de caractères applique des fonctions de chaîne, telles que la conversion de minuscules en majuscules, à des données de type caractère.</span><span class="sxs-lookup"><span data-stu-id="a5993-103">The Character Map transformation applies string functions, such as conversion from lowercase to uppercase, to character data.</span></span> <span data-ttu-id="a5993-104">Cette transformation fonctionne seulement sur les données de colonne de type de données chaîne.</span><span class="sxs-lookup"><span data-stu-id="a5993-104">This transformation operates only on column data with a string data type.</span></span>  
  
 <span data-ttu-id="a5993-105">La transformation de la table de caractères peut convertir les données de colonne sur place ou ajouter une colonne à la sortie de transformation et y insérer les données converties.</span><span class="sxs-lookup"><span data-stu-id="a5993-105">The Character Map transformation can convert column data in place or add a column to the transformation output and put the converted data in the new column.</span></span> <span data-ttu-id="a5993-106">Vous pouvez appliquer différents ensembles d'opérations de mappage à la même colonne d'entrée et placer les résultats dans des colonnes différentes.</span><span class="sxs-lookup"><span data-stu-id="a5993-106">You can apply different sets of mapping operations to the same input column and put the results in different columns.</span></span> <span data-ttu-id="a5993-107">Par exemple, vous pouvez convertir la même colonne en majuscules et en minuscules, puis placer les résultats dans deux colonnes différentes.</span><span class="sxs-lookup"><span data-stu-id="a5993-107">For example, you can convert the same column to uppercase and lowercase and put the results in two different columns.</span></span>  
  
 <span data-ttu-id="a5993-108">Dans certaines circonstances, le mappage peut provoquer une troncation des données.</span><span class="sxs-lookup"><span data-stu-id="a5993-108">Mapping can, under some circumstances, cause data to be truncated.</span></span> <span data-ttu-id="a5993-109">Par exemple, la troncation peut se produire lorsque des caractères codés sur un octet sont mappés avec des caractères représentés sur plusieurs octets.</span><span class="sxs-lookup"><span data-stu-id="a5993-109">For example, truncation can occur when single-byte characters are mapped to characters with a multibyte representation.</span></span> <span data-ttu-id="a5993-110">La transformation de la table de caractères comprend une sortie d'erreur, qui permet de diriger les données tronquées vers une sortie distincte.</span><span class="sxs-lookup"><span data-stu-id="a5993-110">The Character Map transformation includes an error output, which can be used to direct truncated data to separate output.</span></span> <span data-ttu-id="a5993-111">Pour plus d’informations, consultez [Gestion des erreurs dans les données](../error-handling-in-data.md).</span><span class="sxs-lookup"><span data-stu-id="a5993-111">For more information, see [Error Handling in Data](../error-handling-in-data.md).</span></span>  
  
 <span data-ttu-id="a5993-112">Cette transformation a une entrée, une sortie et une sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="a5993-112">This transformation has one input, one output, and one error output.</span></span>  
  
## <a name="mapping-operations"></a><span data-ttu-id="a5993-113">Opérations de mappage</span><span class="sxs-lookup"><span data-stu-id="a5993-113">Mapping Operations</span></span>  
 <span data-ttu-id="a5993-114">Le tableau suivant décrit les opérations de mappage prises en charge par la transformation de la table de caractères.</span><span class="sxs-lookup"><span data-stu-id="a5993-114">The following table describes the mapping operations that the Character Map transformation supports.</span></span>  
  
|<span data-ttu-id="a5993-115">Opération</span><span class="sxs-lookup"><span data-stu-id="a5993-115">Operation</span></span>|<span data-ttu-id="a5993-116">Description</span><span class="sxs-lookup"><span data-stu-id="a5993-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a5993-117">Inversion d'octet</span><span class="sxs-lookup"><span data-stu-id="a5993-117">Byte reversal</span></span>|<span data-ttu-id="a5993-118">Inverse l'ordre des octets.</span><span class="sxs-lookup"><span data-stu-id="a5993-118">Reverses byte order.</span></span>|  
|<span data-ttu-id="a5993-119">Pleine chasse</span><span class="sxs-lookup"><span data-stu-id="a5993-119">Full width</span></span>|<span data-ttu-id="a5993-120">Mappe des caractères à demi-chasse avec des caractères à pleine chasse.</span><span class="sxs-lookup"><span data-stu-id="a5993-120">Maps half-width characters to full-width characters.</span></span>|  
|<span data-ttu-id="a5993-121">Demi-chasse</span><span class="sxs-lookup"><span data-stu-id="a5993-121">Half width</span></span>|<span data-ttu-id="a5993-122">Mappe des caractères à pleine chasse avec des caractères à demi-chasse.</span><span class="sxs-lookup"><span data-stu-id="a5993-122">Maps full-width characters to half-width characters.</span></span>|  
|<span data-ttu-id="a5993-123">Hiragana</span><span class="sxs-lookup"><span data-stu-id="a5993-123">Hiragana</span></span>|<span data-ttu-id="a5993-124">Mappe des caractères katakana avec des caractères hiragana.</span><span class="sxs-lookup"><span data-stu-id="a5993-124">Maps katakana characters to hiragana characters.</span></span>|  
|<span data-ttu-id="a5993-125">Katakana</span><span class="sxs-lookup"><span data-stu-id="a5993-125">Katakana</span></span>|<span data-ttu-id="a5993-126">Mappe des caractères hiragana avec des caractères katakana.</span><span class="sxs-lookup"><span data-stu-id="a5993-126">Maps hiragana characters to katakana characters.</span></span>|  
|<span data-ttu-id="a5993-127">Casse linguistique</span><span class="sxs-lookup"><span data-stu-id="a5993-127">Linguistic casing</span></span>|<span data-ttu-id="a5993-128">Applique une casse linguistique à la place des règles système.</span><span class="sxs-lookup"><span data-stu-id="a5993-128">Applies linguistic casing instead of the system rules.</span></span> <span data-ttu-id="a5993-129">La casse linguistique fait référence aux fonctionnalités fournies par le mappage de casse simple API Win32 pour Unicode du turc et d'autres paramètres régionaux.</span><span class="sxs-lookup"><span data-stu-id="a5993-129">Linguistic casing refers to functionality provided by the Win32 API for Unicode simple case mapping of Turkic and other locales.</span></span>|  
|<span data-ttu-id="a5993-130">Minuscules</span><span class="sxs-lookup"><span data-stu-id="a5993-130">Lowercase</span></span>|<span data-ttu-id="a5993-131">Convertit des caractères en minuscules.</span><span class="sxs-lookup"><span data-stu-id="a5993-131">Converts characters to lowercase.</span></span>|  
|<span data-ttu-id="a5993-132">Chinois simplifié</span><span class="sxs-lookup"><span data-stu-id="a5993-132">Simplified Chinese</span></span>|<span data-ttu-id="a5993-133">Mappe des caractères en chinois traditionnel avec des caractères en chinois simplifié.</span><span class="sxs-lookup"><span data-stu-id="a5993-133">Maps traditional Chinese characters to simplified Chinese characters.</span></span>|  
|<span data-ttu-id="a5993-134">Chinois traditionnel</span><span class="sxs-lookup"><span data-stu-id="a5993-134">Traditional Chinese</span></span>|<span data-ttu-id="a5993-135">Mappe des caractères en chinois simplifié avec des caractères en chinois traditionnel.</span><span class="sxs-lookup"><span data-stu-id="a5993-135">Maps simplified Chinese characters to traditional Chinese characters.</span></span>|  
|<span data-ttu-id="a5993-136">Majuscules</span><span class="sxs-lookup"><span data-stu-id="a5993-136">Uppercase</span></span>|<span data-ttu-id="a5993-137">Convertit des caractères en majuscules.</span><span class="sxs-lookup"><span data-stu-id="a5993-137">Converts characters to uppercase.</span></span>|  
  
## <a name="mutually-exclusive-mapping-operations"></a><span data-ttu-id="a5993-138">Opérations de mappage s'excluant mutuellement</span><span class="sxs-lookup"><span data-stu-id="a5993-138">Mutually Exclusive Mapping Operations</span></span>  
 <span data-ttu-id="a5993-139">Plusieurs opérations peuvent être réalisées dans une transformation.</span><span class="sxs-lookup"><span data-stu-id="a5993-139">More than one operation can be performed in a transformation.</span></span> <span data-ttu-id="a5993-140">Toutefois, certaines opérations de mappage s'excluent mutuellement.</span><span class="sxs-lookup"><span data-stu-id="a5993-140">However, some mapping operations are mutually exclusive.</span></span> <span data-ttu-id="a5993-141">Le tableau suivant décrit les restrictions applicables à l'utilisation de plusieurs opérations sur la même colonne.</span><span class="sxs-lookup"><span data-stu-id="a5993-141">The following table lists restrictions that apply when you use multiple operations on the same column.</span></span> <span data-ttu-id="a5993-142">Les opérations dans les colonnes Opération A et Opération B s'excluent mutuellement.</span><span class="sxs-lookup"><span data-stu-id="a5993-142">Operations in the columns Operation A and Operation B are mutually exclusive.</span></span>  
  
|<span data-ttu-id="a5993-143">Opération A</span><span class="sxs-lookup"><span data-stu-id="a5993-143">Operation A</span></span>|<span data-ttu-id="a5993-144">Opération B</span><span class="sxs-lookup"><span data-stu-id="a5993-144">Operation B</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="a5993-145">Minuscules</span><span class="sxs-lookup"><span data-stu-id="a5993-145">Lowercase</span></span>|<span data-ttu-id="a5993-146">Majuscules</span><span class="sxs-lookup"><span data-stu-id="a5993-146">Uppercase</span></span>|  
|<span data-ttu-id="a5993-147">Hiragana</span><span class="sxs-lookup"><span data-stu-id="a5993-147">Hiragana</span></span>|<span data-ttu-id="a5993-148">Katakana</span><span class="sxs-lookup"><span data-stu-id="a5993-148">Katakana</span></span>|  
|<span data-ttu-id="a5993-149">Demi-chasse</span><span class="sxs-lookup"><span data-stu-id="a5993-149">Half width</span></span>|<span data-ttu-id="a5993-150">Pleine chasse</span><span class="sxs-lookup"><span data-stu-id="a5993-150">Full width</span></span>|  
|<span data-ttu-id="a5993-151">Chinois traditionnel</span><span class="sxs-lookup"><span data-stu-id="a5993-151">Traditional Chinese</span></span>|<span data-ttu-id="a5993-152">Chinois simplifié</span><span class="sxs-lookup"><span data-stu-id="a5993-152">Simplified Chinese</span></span>|  
|<span data-ttu-id="a5993-153">Minuscules</span><span class="sxs-lookup"><span data-stu-id="a5993-153">Lowercase</span></span>|<span data-ttu-id="a5993-154">Hiragana, katakana, demi-chasse, pleine chasse</span><span class="sxs-lookup"><span data-stu-id="a5993-154">Hiragana, katakana, half width, full width</span></span>|  
|<span data-ttu-id="a5993-155">Majuscules</span><span class="sxs-lookup"><span data-stu-id="a5993-155">Uppercase</span></span>|<span data-ttu-id="a5993-156">Hiragana, katakana, demi-chasse, pleine chasse</span><span class="sxs-lookup"><span data-stu-id="a5993-156">Hiragana, katakana, half width, full width</span></span>|  
  
## <a name="configuration-of-the-character-map-transformation"></a><span data-ttu-id="a5993-157">Configuration de la transformation de la table de caractères</span><span class="sxs-lookup"><span data-stu-id="a5993-157">Configuration of the Character Map Transformation</span></span>  
 <span data-ttu-id="a5993-158">Vous pouvez configurer la transformation de la table de caractères comme suit :</span><span class="sxs-lookup"><span data-stu-id="a5993-158">You configure the Character Map transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="a5993-159">Spécifiez les colonnes à convertir.</span><span class="sxs-lookup"><span data-stu-id="a5993-159">Specify the columns to convert.</span></span>  
  
-   <span data-ttu-id="a5993-160">Spécifiez les opérations à appliquer à chaque colonne.</span><span class="sxs-lookup"><span data-stu-id="a5993-160">Specify the operations to apply to each column.</span></span>  
  
 <span data-ttu-id="a5993-161">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="a5993-161">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="a5993-162">Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur de transformation de la table des caractères** , consultez [Character Map Transformation Editor](../../character-map-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="a5993-162">For more information about the properties that you can set in the **Character Map Transformation Editor** dialog box, see [Character Map Transformation Editor](../../character-map-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="a5993-163">La boîte de dialogue **Éditeur avancé** reflète les propriétés qui peuvent être définies par programmation.</span><span class="sxs-lookup"><span data-stu-id="a5993-163">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="a5993-164">Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur avancé** ou par programmation, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="a5993-164">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="a5993-165">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="a5993-165">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="a5993-166">Propriétés personnalisées des transformations</span><span class="sxs-lookup"><span data-stu-id="a5993-166">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="a5993-167">Pour plus d'informations sur la définition des propriétés, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="a5993-167">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="a5993-168">Définir les propriétés d’un composant de flux de données</span><span class="sxs-lookup"><span data-stu-id="a5993-168">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
-   [<span data-ttu-id="a5993-169">Trier des données pour les transformations de fusion et de jointure de fusion</span><span class="sxs-lookup"><span data-stu-id="a5993-169">Sort Data for the Merge and Merge Join Transformations</span></span>](sort-data-for-the-merge-and-merge-join-transformations.md)  
  
  
