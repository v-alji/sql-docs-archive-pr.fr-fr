---
title: Créer une dimension en générant une table non temporelle dans la source de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data sources [Analysis Services], dimensions without data source
- dimensions [Analysis Services], standard
- dimensions [Analysis Services], creating without data source
- standard dimensions [Analysis Services]
ms.assetid: a37f7a46-7451-4582-ba19-2595196d97bc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 49dbfb0c1fc15c1cbf703514e0fc693dfabf1e9d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705616"
---
# <a name="create-a-dimension-by-generating-a-non-time-table-in-the-data-source"></a><span data-ttu-id="977e8-102">Créer une dimension en générant une table non temporelle dans la source de données</span><span class="sxs-lookup"><span data-stu-id="977e8-102">Create a Dimension by Generating a Non-Time Table in the Data Source</span></span>
  <span data-ttu-id="977e8-103">Dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , vous pouvez utiliser l’Assistant dimension dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] pour créer une dimension sans utiliser de source de données existante.</span><span class="sxs-lookup"><span data-stu-id="977e8-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you can use the Dimension Wizard in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to create a dimension without using an existing data source.</span></span> <span data-ttu-id="977e8-104">Pour ce faire, sélectionnez l’option **Générer une table non temporelle dans la source de données** de la page **Sélectionner une méthode de création** de l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="977e8-104">You do this by selecting the **Generate a non-time table in the data source** option of the **Select Creation Method** page of the wizard.</span></span> <span data-ttu-id="977e8-105">Pour créer une table de dimension dans la source de données sous-jacente, vous devez avoir l'autorisation de créer des objets dans la source de données sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="977e8-105">To create a new dimension table in the underlying data source, you must have permission to create objects in the underlying data source.</span></span> <span data-ttu-id="977e8-106">Si vous définissez une dimension sans vue de source de données prédéfinie, vous pouvez la définir entièrement ou utiliser un modèle de dimension.</span><span class="sxs-lookup"><span data-stu-id="977e8-106">When defining a dimension without a predefined data source view, you can either define the dimension from scratch or use a dimension template.</span></span>  
  
 <span data-ttu-id="977e8-107">L'Assistant Dimension fournit des exemples de modèles de dimension à partir desquels vous pouvez générer un type de dimension fréquemment utilisé.</span><span class="sxs-lookup"><span data-stu-id="977e8-107">The Dimension Wizard provides sample dimension templates from which you can build a common dimension type.</span></span> <span data-ttu-id="977e8-108">Vous pouvez sélectionner l'un des types de dimensions suivants :</span><span class="sxs-lookup"><span data-stu-id="977e8-108">You can select from the following types of dimensions:</span></span>  
  
-   <span data-ttu-id="977e8-109">Compte</span><span class="sxs-lookup"><span data-stu-id="977e8-109">Account</span></span>  
  
-   <span data-ttu-id="977e8-110">Customer</span><span class="sxs-lookup"><span data-stu-id="977e8-110">Customer</span></span>  
  
-   <span data-ttu-id="977e8-111">Date</span><span class="sxs-lookup"><span data-stu-id="977e8-111">Date</span></span>  
  
-   <span data-ttu-id="977e8-112">department</span><span class="sxs-lookup"><span data-stu-id="977e8-112">Department</span></span>  
  
-   <span data-ttu-id="977e8-113">Devise de destination</span><span class="sxs-lookup"><span data-stu-id="977e8-113">Destination Currency</span></span>  
  
-   <span data-ttu-id="977e8-114">Employee</span><span class="sxs-lookup"><span data-stu-id="977e8-114">Employee</span></span>  
  
-   <span data-ttu-id="977e8-115">Geography</span><span class="sxs-lookup"><span data-stu-id="977e8-115">Geography</span></span>  
  
-   <span data-ttu-id="977e8-116">Détails des commandes client sur Internet</span><span class="sxs-lookup"><span data-stu-id="977e8-116">Internet Sales Order Details</span></span>  
  
-   <span data-ttu-id="977e8-117">Organisation</span><span class="sxs-lookup"><span data-stu-id="977e8-117">Organization</span></span>  
  
-   <span data-ttu-id="977e8-118">Produit</span><span class="sxs-lookup"><span data-stu-id="977e8-118">Product</span></span>  
  
-   <span data-ttu-id="977e8-119">Promotion</span><span class="sxs-lookup"><span data-stu-id="977e8-119">Promotion</span></span>  
  
-   <span data-ttu-id="977e8-120">Détails des commandes client du revendeur</span><span class="sxs-lookup"><span data-stu-id="977e8-120">Reseller Sales Order Details</span></span>  
  
-   <span data-ttu-id="977e8-121">Reseller</span><span class="sxs-lookup"><span data-stu-id="977e8-121">Reseller</span></span>  
  
-   <span data-ttu-id="977e8-122">Canal de vente</span><span class="sxs-lookup"><span data-stu-id="977e8-122">Sales Channel</span></span>  
  
-   <span data-ttu-id="977e8-123">Motif de vente</span><span class="sxs-lookup"><span data-stu-id="977e8-123">Sales Reason</span></span>  
  
-   <span data-ttu-id="977e8-124">Détails des commandes récapitulatives client</span><span class="sxs-lookup"><span data-stu-id="977e8-124">Sales Summary Order Details</span></span>  
  
-   <span data-ttu-id="977e8-125">Sales Territory</span><span class="sxs-lookup"><span data-stu-id="977e8-125">Sales Territory</span></span>  
  
-   <span data-ttu-id="977e8-126">Scénario</span><span class="sxs-lookup"><span data-stu-id="977e8-126">Scenario</span></span>  
  
-   <span data-ttu-id="977e8-127">Devise source</span><span class="sxs-lookup"><span data-stu-id="977e8-127">Source Currency</span></span>  
  
 <span data-ttu-id="977e8-128">Chaque modèle standard prend en charge les attributs que vous pouvez choisir d'inclure dans la dimension.</span><span class="sxs-lookup"><span data-stu-id="977e8-128">Each of the standard templates supports attributes that you can choose to include in the dimension.</span></span> <span data-ttu-id="977e8-129">Vous pouvez également ajouter vos propres fichiers modèles de dimension pour les dimensions qui sont fréquemment utilisées avec vos données.</span><span class="sxs-lookup"><span data-stu-id="977e8-129">You can also add your own template files for dimensions that are commonly used with your data.</span></span> <span data-ttu-id="977e8-130">Les modèles de dimension sont dans le dossier suivant :</span><span class="sxs-lookup"><span data-stu-id="977e8-130">The dimension templates are located in the following folder:</span></span>  
  
 `C:\Program Files\Microsoft SQL Server\100\Tools\Templates\olap\1033\Dimension Templates`  
  
 <span data-ttu-id="977e8-131">Vous pouvez utiliser le Concepteur de dimensions après avoir terminé l'Assistant Dimension pour ajouter, supprimer et configurer des attributs et des hiérarchies dans la dimension.</span><span class="sxs-lookup"><span data-stu-id="977e8-131">You can use Dimension Designer after you complete the Dimension Wizard to add, remove, and configure attributes and hierarchies in the dimension.</span></span>  
  
 <span data-ttu-id="977e8-132">Lorsque vous créez une dimension non temporelle sans utiliser de source de données, l'Assistant Dimension vous guide à travers les étapes de la spécification du type de dimension et de l'identification de l'attribut de clé et des dimensions à variation lente.</span><span class="sxs-lookup"><span data-stu-id="977e8-132">When you are creating a non-time dimension without using a data source, the Dimension Wizard guides you through the steps of specifying the dimension type, and identifying the key attribute and slowly changing dimensions.</span></span>  
  
## <a name="specify-dimension-type"></a><span data-ttu-id="977e8-133">Spécification du type de dimension</span><span class="sxs-lookup"><span data-stu-id="977e8-133">Specify Dimension Type</span></span>  
 <span data-ttu-id="977e8-134">Dans la page **Spécifier le type de dimension** de l’Assistant Dimension, vous pouvez spécifier le type de dimension.</span><span class="sxs-lookup"><span data-stu-id="977e8-134">On the **Specify Dimension Type** page of the Dimension Wizard, you can specify the dimension type.</span></span> <span data-ttu-id="977e8-135">Si vous générez la dimension d'après un modèle, le type de dimension est défini automatiquement.</span><span class="sxs-lookup"><span data-stu-id="977e8-135">If you are building the dimension based on a template, the dimension type is defined for you.</span></span> <span data-ttu-id="977e8-136">Sur cette page, vous pouvez également sélectionner des attributs standard pour le type de dimension spécifié, s'ils sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="977e8-136">On this page, you can also select standard attributes for the specified dimension type if any are available.</span></span>  
  
 <span data-ttu-id="977e8-137">Si vous avez sélectionné un modèle qui correspond à un type de dimension, cette page est remplie avec les options de ce type de dimension.</span><span class="sxs-lookup"><span data-stu-id="977e8-137">If you selected a template that corresponds to a dimension type, this page is populated with the options for that dimension type.</span></span> <span data-ttu-id="977e8-138">Si vous n’avez pas sélectionné de modèle ou qu’il n’existe aucun type de dimension correspondant, le type de dimension par défaut est **Normal**.</span><span class="sxs-lookup"><span data-stu-id="977e8-138">If you did not select a template, or if there is no corresponding dimension type, the default dimension type is **Regular**.</span></span> <span data-ttu-id="977e8-139">Si un type de dimension n'est pas déjà sélectionné, choisissez le type le plus approprié à la dimension que vous créez.</span><span class="sxs-lookup"><span data-stu-id="977e8-139">If a dimension type is not already selected, select the most appropriate type for the dimension that you are creating.</span></span> <span data-ttu-id="977e8-140">Si aucun type approprié n’est répertorié pour **Type de dimension**, choisissez **Normal**.</span><span class="sxs-lookup"><span data-stu-id="977e8-140">If no appropriate type is listed for **Dimension type**, use **Regular**.</span></span>  
  
 <span data-ttu-id="977e8-141">Quand vous sélectionnez un type de dimension, l’Assistant répertorie les types d’attributs qui s’appliquent à cette dimension sous **Attributs de dimension**.</span><span class="sxs-lookup"><span data-stu-id="977e8-141">When you select a dimension type, the wizard lists the attribute types that apply to this dimension under **Dimension attributes**.</span></span> <span data-ttu-id="977e8-142">Pour sélectionner un type d’attribut, cochez la case **Inclure** en regard du type d’attribut, puis tapez le nom de l’attribut sous **Attribut de dimension**.</span><span class="sxs-lookup"><span data-stu-id="977e8-142">To select an attribute type, select the **Include** check box next to the attribute type, and type the name for the attribute under **Dimension Attribute**.</span></span> <span data-ttu-id="977e8-143">Le nom par défaut est le même que dans **Type d’attribut**.</span><span class="sxs-lookup"><span data-stu-id="977e8-143">The default name is the same as **Attribute Type**.</span></span>  
  
## <a name="identify-key-attribute-and-changing-dimensions"></a><span data-ttu-id="977e8-144">Identifier l'attribut clé et les dimensions variables</span><span class="sxs-lookup"><span data-stu-id="977e8-144">Identify Key Attribute and Changing Dimensions</span></span>  
 <span data-ttu-id="977e8-145">Dans la page **Spécifier la clé et le type de la dimension** , sélectionnez l’attribut de votre choix comme attribut clé de la dimension.</span><span class="sxs-lookup"><span data-stu-id="977e8-145">On the **Specify Dimension Key and Type** page, select the attribute that you want to be the key attribute for the dimension.</span></span> <span data-ttu-id="977e8-146">En règle générale, l'attribut correspond à la colonne clé primaire de la table de dimension principale et il indexe les membres feuille de la dimension.</span><span class="sxs-lookup"><span data-stu-id="977e8-146">The key attribute typically corresponds to the primary key column in the main dimension table, and it typically indexes the leaf members of the dimension.</span></span>  
  
 <span data-ttu-id="977e8-147">Si vous avez sélectionné un modèle et qu'un attribut clé est défini dans le modèle, cet attribut est l'attribut clé par défaut.</span><span class="sxs-lookup"><span data-stu-id="977e8-147">If you selected a template, and a key attribute is defined in the template, that attribute is the default key attribute.</span></span> <span data-ttu-id="977e8-148">Si vous avez sélectionné un modèle et qu'aucun attribut de clé dans celui-ci, l'attribut de clé par défaut est le premier attribut de la liste.</span><span class="sxs-lookup"><span data-stu-id="977e8-148">If you selected a template but no key attribute is defined in the template, the default is the first attribute in the list.</span></span> <span data-ttu-id="977e8-149">La liste contient tous les attributs que vous avez sélectionnés dans la page **Spécifier le type de dimension** .</span><span class="sxs-lookup"><span data-stu-id="977e8-149">The list contains all the attributes that you selected on the **Specify Dimension Type** page.</span></span> <span data-ttu-id="977e8-150">L’attribut de clé peut être n’importe quel attribut parmi ceux que vous avez sélectionnés dans la page **Spécifier le type de dimension** .</span><span class="sxs-lookup"><span data-stu-id="977e8-150">You can select any one of the attributes that you selected on the **Specify Dimension Type** page to be the key attribute.</span></span> <span data-ttu-id="977e8-151">Si vous n'avez sélectionné aucun attribut, l'Assistant crée automatiquement un attribut clé et le nomme en concaténant le nom et l'ID de la dimension.</span><span class="sxs-lookup"><span data-stu-id="977e8-151">If you did not select any attributes, the wizard automatically creates a key attribute and names it by concatenating the dimension name and "ID".</span></span>  
  
 <span data-ttu-id="977e8-152">Enfin, spécifiez si cette dimension est une dimension variable.</span><span class="sxs-lookup"><span data-stu-id="977e8-152">Finally, specify whether this dimension is a changing dimension.</span></span> <span data-ttu-id="977e8-153">Dans le temps, les membres d'une dimension variable se déplacent dans la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="977e8-153">Members in a changing dimension move over time to different locations in the hierarchy.</span></span> <span data-ttu-id="977e8-154">L'Assistant génère des colonnes supplémentaires et crée des attributs qui correspondent à ces colonnes.</span><span class="sxs-lookup"><span data-stu-id="977e8-154">The wizard generates additional columns and creates attributes that correspond to those columns.</span></span> <span data-ttu-id="977e8-155">Ces colonnes permettront aux utilisateurs d'interroger la dimension de façon à tenir compte de la modification.</span><span class="sxs-lookup"><span data-stu-id="977e8-155">These columns will let users query the dimension in such a way as to factor in the change.</span></span> <span data-ttu-id="977e8-156">Tous les packages que vous créerez ultérieurement avec l'Assistant Génération de schéma géreront les clés de substitution à partir des caractéristiques de dimension à variation lente de la dimension.</span><span class="sxs-lookup"><span data-stu-id="977e8-156">Any packages that you subsequently create with the Schema Generation Wizard manage surrogate keys based on slowly changing dimension characteristics of the dimension.</span></span>  
  
 <span data-ttu-id="977e8-157">Quand vous cochez la case **Il s’agit d’une dimension variable** , l’Assistant Dimension définit les attributs indiqués dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="977e8-157">When you select the **This is a changing dimension** check box, the Dimension Wizard defines the attributes indicated in the following table:</span></span>  
  
|<span data-ttu-id="977e8-158">Attribut</span><span class="sxs-lookup"><span data-stu-id="977e8-158">Attribute</span></span>|<span data-ttu-id="977e8-159">Type</span><span class="sxs-lookup"><span data-stu-id="977e8-159">Type</span></span>|  
|---------------|----------|  
|<span data-ttu-id="977e8-160">SCD OriginalID</span><span class="sxs-lookup"><span data-stu-id="977e8-160">SCD OriginalID</span></span>|<span data-ttu-id="977e8-161">SCDOriginalID</span><span class="sxs-lookup"><span data-stu-id="977e8-161">SCDOriginalID</span></span>|  
|<span data-ttu-id="977e8-162">SCD End Date</span><span class="sxs-lookup"><span data-stu-id="977e8-162">SCD End Date</span></span>|<span data-ttu-id="977e8-163">SCDEndDate</span><span class="sxs-lookup"><span data-stu-id="977e8-163">SCDEndDate</span></span>|  
|<span data-ttu-id="977e8-164">SCD Start Date</span><span class="sxs-lookup"><span data-stu-id="977e8-164">SCD Start Date</span></span>|<span data-ttu-id="977e8-165">SCDStartDate</span><span class="sxs-lookup"><span data-stu-id="977e8-165">SCDStartDate</span></span>|  
|<span data-ttu-id="977e8-166">SCD Status</span><span class="sxs-lookup"><span data-stu-id="977e8-166">SCD Status</span></span>|<span data-ttu-id="977e8-167">SCDStatus</span><span class="sxs-lookup"><span data-stu-id="977e8-167">SCDStatus</span></span>|  
  
 <span data-ttu-id="977e8-168">La case **Il s’agit d’une dimension variable** est cochée par défaut si vous utilisez un modèle pour lequel ces attributs de dimension à variation lente sont définis.</span><span class="sxs-lookup"><span data-stu-id="977e8-168">By default, the **This is a changing dimension** check box is selected if you use a template that has these slowly changing dimension attributes defined.</span></span> <span data-ttu-id="977e8-169">Si vous la désactivez, les attributs de dimension à variation lente sont supprimés de la dimension.</span><span class="sxs-lookup"><span data-stu-id="977e8-169">If you clear the check box, the slowly changing dimension attributes are removed from the dimension.</span></span>  
  
 <span data-ttu-id="977e8-170">Vous pouvez utiliser le Concepteur de dimensions pour configurer les propriétés d'une dimension à variation lente.</span><span class="sxs-lookup"><span data-stu-id="977e8-170">You can use Dimension Designer to configure properties for a slowly changing dimension.</span></span>  
  
## <a name="completing-the-dimension-wizard"></a><span data-ttu-id="977e8-171">Fin de l'Assistant Dimension</span><span class="sxs-lookup"><span data-stu-id="977e8-171">Completing the Dimension Wizard</span></span>  
 <span data-ttu-id="977e8-172">Dans la page **Fin de l’Assistant** , tapez le nom de la nouvelle dimension et affichez sa structure.</span><span class="sxs-lookup"><span data-stu-id="977e8-172">On the **Completing the Wizard** page, type a name for the new dimension and view the dimension structure.</span></span> <span data-ttu-id="977e8-173">Cochez la case **Créer le schéma maintenant** pour lancer l’Assistant Génération de schéma une fois que vous avez cliqué sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="977e8-173">Select the **Generate schema now** check box to start the Schema Generation Wizard after you click **Finish**.</span></span> <span data-ttu-id="977e8-174">En règle générale, vous ne devez pas activer cette case à cocher si vous prévoyez de créer des objets supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="977e8-174">In most cases, you should not select this check box if you plan to create additional objects.</span></span> <span data-ttu-id="977e8-175">Si vous n'activez pas cette case à cocher, vous pourrez utiliser le Concepteur de dimensions pour générer le schéma ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="977e8-175">If you do not select this check box, you can use Dimension Designer to generate the schema later.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="977e8-176">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="977e8-176">See Also</span></span>  
 <span data-ttu-id="977e8-177">[Créer une dimension de temps en générant une table de temps](create-a-time-dimension-by-generating-a-time-table.md) </span><span class="sxs-lookup"><span data-stu-id="977e8-177">[Create a Time Dimension by Generating a Time Table](create-a-time-dimension-by-generating-a-time-table.md) </span></span>  
 [<span data-ttu-id="977e8-178">Create a Time Dimension by Generating a Time Table</span><span class="sxs-lookup"><span data-stu-id="977e8-178">Create a Time Dimension by Generating a Time Table</span></span>](create-a-time-dimension-by-generating-a-time-table.md)  
  
  
