---
title: Sélectionner les attributs de la dimension (Assistant Dimension) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.dimensionattributes.f1
ms.assetid: f58a3e14-ab27-44d3-8c26-f5c9ee7583b0
author: minewiskan
ms.author: owend
ms.openlocfilehash: a4961092517ce1d38cfd4086ec083a939242652d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603091"
---
# <a name="select-dimension-attributes-dimension-wizard"></a><span data-ttu-id="8b25d-102">Sélectionner les attributs de la dimension (Assistant Dimension)</span><span class="sxs-lookup"><span data-stu-id="8b25d-102">Select Dimension Attributes (Dimension Wizard)</span></span>
  <span data-ttu-id="8b25d-103">Utilisez la page **Sélectionner les attributs de la dimension** pour sélectionner et modifier les attributs de la dimension à créer.</span><span class="sxs-lookup"><span data-stu-id="8b25d-103">Use the **Select Dimension Attributes** page to select and modify the attributes for the dimension to be created.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8b25d-104">Si vous avez des difficultés à lire les valeurs d'une colonne, agrandissez la fenêtre de l'Assistant et modifiez la largeur de chaque en-tête de colonne jusqu'à ce que les valeurs soient lisibles.</span><span class="sxs-lookup"><span data-stu-id="8b25d-104">If you cannot read the values for any column, maximize the wizard window and change the width of each column heading until you can read the values.</span></span>  
  
 <span data-ttu-id="8b25d-105">**Pour ouvrir l'Assistant Dimension**</span><span class="sxs-lookup"><span data-stu-id="8b25d-105">**To open the Dimension Wizard**</span></span>  
  
-   <span data-ttu-id="8b25d-106">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], dans **l’Explorateur de solutions**, cliquez avec le bouton droit sur le dossier **Dimensions** pour un projet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , puis cliquez sur **Nouvelle dimension**.</span><span class="sxs-lookup"><span data-stu-id="8b25d-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in **Solution Explorer**, right-click the **Dimensions** folder for an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then click **New Dimension**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8b25d-107">Options</span><span class="sxs-lookup"><span data-stu-id="8b25d-107">Options</span></span>  
 <span data-ttu-id="8b25d-108">(Colonne avec cases à cocher)</span><span class="sxs-lookup"><span data-stu-id="8b25d-108">(Column with check boxes)</span></span>  
 <span data-ttu-id="8b25d-109">Sélectionnez cette option pour inclure un attribut dans la dimension.</span><span class="sxs-lookup"><span data-stu-id="8b25d-109">Select to include an attribute in the dimension.</span></span>  
  
 <span data-ttu-id="8b25d-110">Pour inclure un attribut particulier, activez la case à cocher de cet attribut.</span><span class="sxs-lookup"><span data-stu-id="8b25d-110">To include a specific attribute, select the check box for that attribute.</span></span>  
  
 <span data-ttu-id="8b25d-111">Pour inclure tous les attributs, activez la case à cocher dans l'en-tête de la colonne.</span><span class="sxs-lookup"><span data-stu-id="8b25d-111">To include all attributes, select the check box in the column header.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8b25d-112">La case à cocher de l'attribut de clé ne peut pas être désactivée.</span><span class="sxs-lookup"><span data-stu-id="8b25d-112">The check box for the key attribute cannot be cleared.</span></span>  
  
 <span data-ttu-id="8b25d-113">**Nom de l’attribut**</span><span class="sxs-lookup"><span data-stu-id="8b25d-113">**Attribute Name**</span></span>  
 <span data-ttu-id="8b25d-114">Répertorie les attributs disponibles.</span><span class="sxs-lookup"><span data-stu-id="8b25d-114">Lists the available attributes.</span></span>  
  
 <span data-ttu-id="8b25d-115">Pour modifier le nom d'un attribut, cliquez sur son nom, puis tapez un nouveau nom.</span><span class="sxs-lookup"><span data-stu-id="8b25d-115">To change the name of an attribute, click the attribute name and type a new name for the attribute.</span></span>  
  
 <span data-ttu-id="8b25d-116">**Permettre la navigation**</span><span class="sxs-lookup"><span data-stu-id="8b25d-116">**Enable Browsing**</span></span>  
 <span data-ttu-id="8b25d-117">Sélectionnez cette option pour permettre à l'utilisateur final de parcourir et de filtrer les attributs.</span><span class="sxs-lookup"><span data-stu-id="8b25d-117">Select to make the attribute available to the end user for browsing and filtering.</span></span> <span data-ttu-id="8b25d-118">L'option**Permettre la navigation** doit être sélectionnée pour l'attribut de clé.</span><span class="sxs-lookup"><span data-stu-id="8b25d-118">**Enable Browsing** must be selected for the key attribute.</span></span> <span data-ttu-id="8b25d-119">Pour les attributs non-clés, l’option **Permettre la navigation** n’est pas sélectionnée par défaut, ce qui implique que les attributs non-clés sont affichés uniquement comme propriétés de membre.</span><span class="sxs-lookup"><span data-stu-id="8b25d-119">For non-key attributes, the default is not to have **Enable Browsing** selected, which causes the non-key attributes to be shown only as member properties.</span></span>  
  
 <span data-ttu-id="8b25d-120">Dans la plupart des cas, la navigation dans les attributs est activée ou désactivée en affectant respectivement la valeur `AttributeHierarchyEnabled` ou `True` à la propriété `False`.</span><span class="sxs-lookup"><span data-stu-id="8b25d-120">In most cases, the attribute is made available or not available for browsing by setting the `AttributeHierarchyEnabled` property to `True` or `False`, respectively.</span></span> <span data-ttu-id="8b25d-121">Toutefois, l'Assistant utilise des paramètres différents dans les trois cas suivants.</span><span class="sxs-lookup"><span data-stu-id="8b25d-121">However, in the following three cases, the wizard uses different settings.</span></span>  
  
|<span data-ttu-id="8b25d-122">Cas</span><span class="sxs-lookup"><span data-stu-id="8b25d-122">Case</span></span>|<span data-ttu-id="8b25d-123">Paramètres</span><span class="sxs-lookup"><span data-stu-id="8b25d-123">Settings</span></span>|  
|----------|--------------|  
|<span data-ttu-id="8b25d-124">Une dimension contient une hiérarchie parent-enfant et l’option **Permettre la navigation** n’est pas sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="8b25d-124">A dimension contains a parent-child hierarchy and **Enable Browsing** is not selected</span></span>|<span data-ttu-id="8b25d-125">L'Assistant conserve la valeur `AttributeHierarchyEnabled` pour la propriété `True` et affecte la valeur `AttributeHierarchyVisible` à l'attribut `False` pour l'attribut de clé.</span><span class="sxs-lookup"><span data-stu-id="8b25d-125">The wizard leaves the `AttributeHierarchyEnabled` property set to `True`, and sets the `AttributeHierarchyVisible` attribute to `False` for the key attribute.</span></span>|  
|<span data-ttu-id="8b25d-126">Une table dans une dimension contient une clé étrangère à une table qui n'est pas dans la dimension</span><span class="sxs-lookup"><span data-stu-id="8b25d-126">A table in a dimension contains a foreign key to a table that is not in the dimension</span></span>|<span data-ttu-id="8b25d-127">L'Assistant sélectionne la clé étrangère comme attribut à inclure, mais ne sélectionne pas **Permettre la navigation**.</span><span class="sxs-lookup"><span data-stu-id="8b25d-127">The wizard selects the foreign key as an attribute to be included, but will not select **Enable Browsing**.</span></span> <span data-ttu-id="8b25d-128">Si vous conservez ces paramètres, la propriété `AttributeHiearchyEnabled` de l'attribut aura la valeur `True` et la propriété `AttributeHierarchyVisible` aura la valeur `False`.</span><span class="sxs-lookup"><span data-stu-id="8b25d-128">If you keep these settings, the `AttributeHiearchyEnabled` property of the attribute will be set to `True`, and the `AttributeHierarchyVisible` property will be set to `False`.</span></span>|  
|<span data-ttu-id="8b25d-129">Une dimension contient des tables en flocon accessibles via des colonnes clés étrangères qui acceptent la valeur NULL</span><span class="sxs-lookup"><span data-stu-id="8b25d-129">A dimension contains snowflake tables that are reached through nullable foreign key columns</span></span><br /><br /> <span data-ttu-id="8b25d-130">-et-</span><span class="sxs-lookup"><span data-stu-id="8b25d-130">-and-</span></span><br /><br /> <span data-ttu-id="8b25d-131">L'option Permettre la navigation n'est pas sélectionnée pour l'attribut qui est basé sur la clé de la table en flocon</span><span class="sxs-lookup"><span data-stu-id="8b25d-131">Enable Browsing for the attribute that is based on the key of the snowflake table is not selected</span></span>|<span data-ttu-id="8b25d-132">L'Assistant créera le nouvel attribut dont la propriété `AttributeHiearchyEnabled` a la valeur `True` et dont la propriété `AttributeHierarchyVisible` a la valeur `False`.</span><span class="sxs-lookup"><span data-stu-id="8b25d-132">The wizard will create the new attribute that has the `AttributeHiearchyEnabled` property set to `True`, and the `AttributeHierarchyVisible` property set to `False`.</span></span>|  
  
 <span data-ttu-id="8b25d-133">**Type d’attribut**</span><span class="sxs-lookup"><span data-stu-id="8b25d-133">**Attribute Type**</span></span>  
 <span data-ttu-id="8b25d-134">(Facultatif) Définissez le type de l'attribut.</span><span class="sxs-lookup"><span data-stu-id="8b25d-134">(Optional) Set the type for the attribute.</span></span> <span data-ttu-id="8b25d-135">La valeur par défaut est **Regular**.</span><span class="sxs-lookup"><span data-stu-id="8b25d-135">The default value is **Regular**.</span></span> <span data-ttu-id="8b25d-136">Le type d'attribut apporte aux applications clientes des indications sur les informations que l'attribut peut contenir.</span><span class="sxs-lookup"><span data-stu-id="8b25d-136">The attribute type provides guidance to client applications on what information the attribute might contain.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b25d-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8b25d-137">See Also</span></span>  
 <span data-ttu-id="8b25d-138">[Aide (F1) de l’Assistant Dimension](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="8b25d-138">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="8b25d-139">[Dimensions &#40;Analysis Services-données multidimensionnelles&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="8b25d-139">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="8b25d-140">Dimensions dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="8b25d-140">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
