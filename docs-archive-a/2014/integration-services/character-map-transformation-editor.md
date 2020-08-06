---
title: Éditeur de transformation de la table des caractères | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.charactermaptransformation.f1
helpviewer_keywords:
- Character Map Transformation Editor
ms.assetid: 3f1dbcf9-9cca-4606-bdcc-7ea6ad48cdf3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c6cdcdba448dafc6ccf03774d4f611dee704b823
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602956"
---
# <a name="character-map-transformation-editor"></a><span data-ttu-id="57280-102">Éditeur de transformation de la table des caractères</span><span class="sxs-lookup"><span data-stu-id="57280-102">Character Map Transformation Editor</span></span>
  <span data-ttu-id="57280-103">Utilisez la boîte de dialogue **Éditeur de transformation de la table des caractères** pour sélectionner les fonctions de chaîne à appliquer aux données de colonne, et indiquer si le mappage est une modification sur place ou s’il est ajouté sous la forme d’une nouvelle colonne.</span><span class="sxs-lookup"><span data-stu-id="57280-103">Use the **Character Map Transformation Editor** dialog box to select the string functions to apply to column data and to specify whether mapping is an in-place change or added as a new column.</span></span>  
  
 <span data-ttu-id="57280-104">Pour en savoir plus sur la transformation de la table des caractères, consultez [Character Map Transformation](data-flow/transformations/character-map-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="57280-104">To learn more about the Character Map transformation, see [Character Map Transformation](data-flow/transformations/character-map-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="57280-105">Options</span><span class="sxs-lookup"><span data-stu-id="57280-105">Options</span></span>  
 <span data-ttu-id="57280-106">**Colonnes d'entrée disponibles**</span><span class="sxs-lookup"><span data-stu-id="57280-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="57280-107">Activez les cases à cocher pour sélectionner les colonnes à transformer en utilisant des fonctions de chaîne.</span><span class="sxs-lookup"><span data-stu-id="57280-107">Use the check boxes to select the columns to transform using string functions.</span></span> <span data-ttu-id="57280-108">Vos sélections figurent dans le tableau ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="57280-108">Your selections appear in the table below.</span></span>  
  
 <span data-ttu-id="57280-109">**Colonne d'entrée**</span><span class="sxs-lookup"><span data-stu-id="57280-109">**Input Column**</span></span>  
 <span data-ttu-id="57280-110">Affiche les colonnes d'entrée sélectionnées dans le tableau ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="57280-110">View input columns selected from the table above.</span></span> <span data-ttu-id="57280-111">Vous pouvez également changer ou supprimer une sélection en utilisant la liste des colonnes d'entrée disponibles.</span><span class="sxs-lookup"><span data-stu-id="57280-111">You can also change or remove a selection by using the list of available input columns.</span></span>  
  
 <span data-ttu-id="57280-112">**Destination**</span><span class="sxs-lookup"><span data-stu-id="57280-112">**Destination**</span></span>  
 <span data-ttu-id="57280-113">Indiquez si vous voulez enregistrer le résultat des opérations de chaîne sur place en utilisant la colonne existante, ou enregistrer les données modifiées sous la forme d'une nouvelle colonne.</span><span class="sxs-lookup"><span data-stu-id="57280-113">Specify whether to save the results of the string operations in place, using the existing column, or to save the modified data as a new column.</span></span>  
  
|<span data-ttu-id="57280-114">Valeur</span><span class="sxs-lookup"><span data-stu-id="57280-114">Value</span></span>|<span data-ttu-id="57280-115">Description</span><span class="sxs-lookup"><span data-stu-id="57280-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="57280-116">Nouvelle colonne</span><span class="sxs-lookup"><span data-stu-id="57280-116">New column</span></span>|<span data-ttu-id="57280-117">Enregistre les données dans une nouvelle colonne.</span><span class="sxs-lookup"><span data-stu-id="57280-117">Save the data in a new column.</span></span> <span data-ttu-id="57280-118">Définissez le nom de la colonne sous **Alias de sortie**.</span><span class="sxs-lookup"><span data-stu-id="57280-118">Assign the column name under **Output Alias**.</span></span>|  
|<span data-ttu-id="57280-119">Modification sur place</span><span class="sxs-lookup"><span data-stu-id="57280-119">In-place change</span></span>|<span data-ttu-id="57280-120">Enregistre les données modifiées dans la colonne existante.</span><span class="sxs-lookup"><span data-stu-id="57280-120">Save the modified data in the existing column.</span></span>|  
  
 <span data-ttu-id="57280-121">**Opération**</span><span class="sxs-lookup"><span data-stu-id="57280-121">**Operation**</span></span>  
 <span data-ttu-id="57280-122">Dans la liste, sélectionnez les fonctions de chaîne à appliquer aux données de la colonne.</span><span class="sxs-lookup"><span data-stu-id="57280-122">Select from the list the string functions to apply to column data.</span></span>  
  
|<span data-ttu-id="57280-123">Valeur</span><span class="sxs-lookup"><span data-stu-id="57280-123">Value</span></span>|<span data-ttu-id="57280-124">Description</span><span class="sxs-lookup"><span data-stu-id="57280-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="57280-125">Minuscules</span><span class="sxs-lookup"><span data-stu-id="57280-125">Lowercase</span></span>|<span data-ttu-id="57280-126">Convertit les caractères en minuscules.</span><span class="sxs-lookup"><span data-stu-id="57280-126">Convert to lower case.</span></span>|  
|<span data-ttu-id="57280-127">Majuscules</span><span class="sxs-lookup"><span data-stu-id="57280-127">Uppercase</span></span>|<span data-ttu-id="57280-128">Convertit les caractères en majuscules</span><span class="sxs-lookup"><span data-stu-id="57280-128">Convert to upper case.</span></span>|  
|<span data-ttu-id="57280-129">Inversion d'octet</span><span class="sxs-lookup"><span data-stu-id="57280-129">Byte reversal</span></span>|<span data-ttu-id="57280-130">Convertit en inversant l'ordre d'octet.</span><span class="sxs-lookup"><span data-stu-id="57280-130">Convert by reversing byte order.</span></span>|  
|<span data-ttu-id="57280-131">Hiragana</span><span class="sxs-lookup"><span data-stu-id="57280-131">Hiragana</span></span>|<span data-ttu-id="57280-132">Convertit les caractères japonais katakana en caractères hiragana.</span><span class="sxs-lookup"><span data-stu-id="57280-132">Convert Japanese katakana characters to hiragana.</span></span>|  
|<span data-ttu-id="57280-133">Katakana</span><span class="sxs-lookup"><span data-stu-id="57280-133">Katakana</span></span>|<span data-ttu-id="57280-134">Convertit les caractères japonais hiragana en caractères katakana.</span><span class="sxs-lookup"><span data-stu-id="57280-134">Convert Japanese hiragana characters to katakana.</span></span>|  
|<span data-ttu-id="57280-135">Demi-chasse</span><span class="sxs-lookup"><span data-stu-id="57280-135">Half width</span></span>|<span data-ttu-id="57280-136">Convertit les caractères pleine chasse en caractères demi-chasse.</span><span class="sxs-lookup"><span data-stu-id="57280-136">Convert full-width characters to half width.</span></span>|  
|<span data-ttu-id="57280-137">Pleine chasse</span><span class="sxs-lookup"><span data-stu-id="57280-137">Full width</span></span>|<span data-ttu-id="57280-138">Convertit les caractères demi-chasse en caractères pleine chasse.</span><span class="sxs-lookup"><span data-stu-id="57280-138">Convert half-width characters to full width.</span></span>|  
|<span data-ttu-id="57280-139">Casse linguistique</span><span class="sxs-lookup"><span data-stu-id="57280-139">Linguistic casing</span></span>|<span data-ttu-id="57280-140">Applique des règles de casse linguistique (mappage de casse simple Unicode pour le turc et d'autres paramètres locaux) à la place des règles système.</span><span class="sxs-lookup"><span data-stu-id="57280-140">Apply linguistic rules of casing (Unicode simple case mapping for Turkic and other locales) instead of the system rules.</span></span>|  
|<span data-ttu-id="57280-141">Chinois simplifié</span><span class="sxs-lookup"><span data-stu-id="57280-141">Simplified Chinese</span></span>|<span data-ttu-id="57280-142">Convertit les caractères chinois traditionnels en caractères chinois simplifié.</span><span class="sxs-lookup"><span data-stu-id="57280-142">Convert traditional Chinese characters to simplified Chinese.</span></span>|  
|<span data-ttu-id="57280-143">Chinois traditionnel</span><span class="sxs-lookup"><span data-stu-id="57280-143">Traditional Chinese</span></span>|<span data-ttu-id="57280-144">Convertit les caractères chinois simplifié en caractères chinois traditionnel.</span><span class="sxs-lookup"><span data-stu-id="57280-144">Convert simplified Chinese characters to traditional Chinese.</span></span>|  
  
 <span data-ttu-id="57280-145">**Alias de sortie**</span><span class="sxs-lookup"><span data-stu-id="57280-145">**Output Alias**</span></span>  
 <span data-ttu-id="57280-146">Permet de saisir un alias pour chaque colonne de sortie.</span><span class="sxs-lookup"><span data-stu-id="57280-146">Type an alias for each output column.</span></span> <span data-ttu-id="57280-147">La valeur par défaut est **Copie de** suivi du nom de la colonne d'entrée. Toutefois, vous pouvez choisir n'importe quel nom descriptif unique.</span><span class="sxs-lookup"><span data-stu-id="57280-147">The default is **Copy of** followed by the input column name; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="57280-148">**Configurer la sortie d’erreur**</span><span class="sxs-lookup"><span data-stu-id="57280-148">**Configure Error Output**</span></span>  
 <span data-ttu-id="57280-149">Utilisez la boîte de dialogue [Configurer la sortie d’erreur](../../2014/integration-services/configure-error-output.md) pour définir les options de gestion des erreurs de cette transformation.</span><span class="sxs-lookup"><span data-stu-id="57280-149">Use the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box to specify error handling options for this transformation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57280-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="57280-150">See Also</span></span>  
 [<span data-ttu-id="57280-151">Guide de référence des erreurs et des messages propres à Integration Services</span><span class="sxs-lookup"><span data-stu-id="57280-151">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
