---
title: Définir des formules de membre personnalisées pour les attributs d’une dimension | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Business Intelligence enhancements [Analysis Services], custom member formulas
- member formulas [Analysis Services]
- dimensions [Analysis Services], Business Intelligence enhancements
- custom member formulas [Analysis Services]
- CustomRollupColumn property
ms.assetid: c4467b08-ce59-4de7-a2d9-c22e246bdd52
author: minewiskan
ms.author: owend
ms.openlocfilehash: 112f8944bd20b2b6a464b0d84fb8ac1a0e89d976
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603111"
---
# <a name="set-custom-member-formulas-for-attributes-in-a-dimension"></a><span data-ttu-id="3860c-102">Définir des formules de membre personnalisées pour les attributs d’une dimension</span><span class="sxs-lookup"><span data-stu-id="3860c-102">Set Custom Member Formulas for Attributes in a Dimension</span></span>
  <span data-ttu-id="3860c-103">Ajoutez une formule de membre personnalisée à un cube ou à une dimension pour remplacer l'agrégation par défaut qui est associée à un membre de dimension par les résultats d'une expression MDX (Multidimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="3860c-103">Add a custom member formula enhancement to a cube or dimension to replace the default aggregation that is associated with a dimension member with the results of a Multidimensional Expressions (MDX) expression.</span></span> <span data-ttu-id="3860c-104">(Cette fonctionnalité affecte à la propriété `CustomRollupColumn` un attribut spécifié dans une dimension.)</span><span class="sxs-lookup"><span data-stu-id="3860c-104">(This enhancement sets the `CustomRollupColumn` property on a specified attribute in a dimension.)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3860c-105">Les formules de membre personnalisées sont disponibles uniquement pour les dimensions basées sur des sources de données existantes.</span><span class="sxs-lookup"><span data-stu-id="3860c-105">A custom member formula is available only for dimensions that are based on existing data sources.</span></span> <span data-ttu-id="3860c-106">Pour les dimensions qui ont été créées sans source de données, vous devez exécuter l'Assistant Génération de schéma pour créer une vue de source de données avant d'ajouter une formule de membre personnalisée.</span><span class="sxs-lookup"><span data-stu-id="3860c-106">For dimensions that were created without using a data source, you must run the Schema Generation Wizard to create a data source view before adding a custom member formula.</span></span>  
  
 <span data-ttu-id="3860c-107">Pour ajouter une formule de membre personnalisée, utilisez l’Assistant Business Intelligence et sélectionnez l’option **Créer une formule de membre personnalisée** dans la page **Choisir des améliorations** .</span><span class="sxs-lookup"><span data-stu-id="3860c-107">To add a custom member formula, you use the Business Intelligence Wizard, and select the **Create a custom member formula** option on the **Choose Enhancement** page.</span></span> <span data-ttu-id="3860c-108">Cet Assistant vous guide ensuite dans la procédure à suivre pour sélectionner la dimension à laquelle vous voulez appliquer une formule de membre personnalisée et pour activer la formule de membre personnalisée.</span><span class="sxs-lookup"><span data-stu-id="3860c-108">This wizard then guides you through the steps of selecting a dimension to which you want to apply a custom member formula and enabling the custom member formula.</span></span>  
  
## <a name="selecting-a-dimension"></a><span data-ttu-id="3860c-109">Sélection d'une dimension</span><span class="sxs-lookup"><span data-stu-id="3860c-109">Selecting a Dimension</span></span>  
 <span data-ttu-id="3860c-110">Dans la première page **Créer une formule de membre personnalisée** de l’Assistant, vous spécifiez la dimension à laquelle vous voulez appliquer une formule de membre personnalisée.</span><span class="sxs-lookup"><span data-stu-id="3860c-110">On the first **Create a Custom Member Formula** page of the wizard, you specify the dimension to which you want to apply a custom member formula.</span></span> <span data-ttu-id="3860c-111">L'ajout de la formule de membre personnalisée à la dimension sélectionnée apportera des modifications à cette dimension.</span><span class="sxs-lookup"><span data-stu-id="3860c-111">The custom member formula enhancement added to this selected dimension will result in changes to the dimension.</span></span> <span data-ttu-id="3860c-112">Ces modifications seront héritées par tous les cubes contenant la dimension sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3860c-112">These changes will be inherited by all cubes that include the selected dimension.</span></span>  
  
## <a name="enabling-a-custom-member-formula"></a><span data-ttu-id="3860c-113">Activation d'une formule de membre personnalisée</span><span class="sxs-lookup"><span data-stu-id="3860c-113">Enabling a Custom Member Formula</span></span>  
 <span data-ttu-id="3860c-114">Dans la deuxième page **Créer une formule de membre personnalisée** de l’Assistant, vous associez la colonne source contenant la formule de membre personnalisée à un ou plusieurs attributs de la dimension.</span><span class="sxs-lookup"><span data-stu-id="3860c-114">On the second **Create a Custom Member Formula** page, you associate the source column that contains the custom member formula with one or more attributes in the dimension.</span></span> <span data-ttu-id="3860c-115">Dans la colonne **Attribut** , cochez la case en regard de l’attribut à associer à la colonne de la formule de membre personnalisée.</span><span class="sxs-lookup"><span data-stu-id="3860c-115">In the **Attribute** column, select the check box next to the attribute that you want to associate with the custom member formula column.</span></span> <span data-ttu-id="3860c-116">À chaque fois que vous sélectionnez un attribut, l’Assistant affiche la boîte de dialogue **Sélectionner une colonne** .</span><span class="sxs-lookup"><span data-stu-id="3860c-116">After you select each attribute, the wizard displays the **Select a Column** dialog box.</span></span> <span data-ttu-id="3860c-117">Dans cette boîte de dialogue, cliquez sur la colonne de la table de dimension qui contient la formule.</span><span class="sxs-lookup"><span data-stu-id="3860c-117">In this dialog box, click the column in the dimension table that contains the formula.</span></span> <span data-ttu-id="3860c-118">Si vous souhaitez modifier une sélection après avoir fermé la boîte de dialogue **Sélectionner une colonne** , cliquez sur la cellule **Colonne source** à modifier, puis cliquez sur les points de suspension (**...**) pour ouvrir à nouveau la boîte de dialogue **Sélectionner une colonne** .</span><span class="sxs-lookup"><span data-stu-id="3860c-118">If you want to change a selection after you close the **Select a Column** dialog box, click the **Source Column** cell that you want to change, and then click the ellipsis (**...**) to open the **Select a Column** dialog box again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3860c-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3860c-119">See Also</span></span>  
 [<span data-ttu-id="3860c-120">Utiliser l’Assistant Business Intelligence pour améliorer des dimensions</span><span class="sxs-lookup"><span data-stu-id="3860c-120">Use the Business Intelligence Wizard to Enhance Dimensions</span></span>](../use-the-business-intelligence-wizard-to-enhance-dimensions.md)  
  
  
