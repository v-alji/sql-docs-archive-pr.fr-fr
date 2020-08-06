---
title: Définir le classement d’une dimension | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- OrderBy property
- dimensions [Analysis Services], ordering
- Business Intelligence enhancements [Analysis Services], ordering
- dimensions [Analysis Services], Business Intelligence enhancements
- ordering dimensions [Analysis Services]
- OrderByAttributeID property
ms.assetid: c42fbd58-244d-4e0a-b715-6f919cbc3ad9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8cd5ea148e374c18c530ba0a15c80dbb23983020
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603113"
---
# <a name="define-the-ordering-for-a-dimension"></a><span data-ttu-id="5b4a2-102">Définir le classement d'une dimension</span><span class="sxs-lookup"><span data-stu-id="5b4a2-102">Define the Ordering for a Dimension</span></span>
  <span data-ttu-id="5b4a2-103">Ajoutez la fonctionnalité de classement des attributs à un cube ou à une dimension pour spécifier comment les membres d'un attribut sont classés.</span><span class="sxs-lookup"><span data-stu-id="5b4a2-103">Add the attribute ordering enhancement to a cube or dimension to specify how the members of an attribute are ordered.</span></span> <span data-ttu-id="5b4a2-104">Les membres peuvent être classés d'après le nom ou la clé de l'attribut, ou d'après le nom ou la clé d'un autre attribut (en fonction d'une relation d'attribut).</span><span class="sxs-lookup"><span data-stu-id="5b4a2-104">Members can be ordered by the name or the key of the attribute, or by the name or the key of another attribute (based on an attribute relationship).</span></span> <span data-ttu-id="5b4a2-105">Par défaut, les membres sont classés d'après le nom de l'attribut.</span><span class="sxs-lookup"><span data-stu-id="5b4a2-105">By default, members are ordered by the name.</span></span> <span data-ttu-id="5b4a2-106">Cette fonctionnalité modifie les paramètres de propriété `OrderBy` et `OrderByAttributeID` des attributs d'une dimension.</span><span class="sxs-lookup"><span data-stu-id="5b4a2-106">This enhancement changes the `OrderBy` and `OrderByAttributeID` property settings for attributes in a dimension.</span></span>  
  
 <span data-ttu-id="5b4a2-107">Pour ajouter la fonctionnalité de classement des attributs, utilisez l'Assistant Business Intelligence et sélectionnez l'option **Spécifier l'ordre des attributs** dans la page **Choisir des améliorations** .</span><span class="sxs-lookup"><span data-stu-id="5b4a2-107">To add attribute ordering, you use the Business Intelligence Wizard, and select the **Specify attribute ordering** option on the **Choose Enhancement** page.</span></span> <span data-ttu-id="5b4a2-108">Cet Assistant vous guide ensuite dans la procédure à suivre pour sélectionner la dimension à laquelle vous voulez appliquer le classement des attributs et pour spécifier le classement à utiliser pour les attributs de la dimension sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5b4a2-108">This wizard then guides you through the steps of selecting a dimension to which you want to apply attribute ordering and specifying how to order the attributes for the selected dimension.</span></span>  
  
## <a name="selecting-a-dimension"></a><span data-ttu-id="5b4a2-109">Sélection d'une dimension</span><span class="sxs-lookup"><span data-stu-id="5b4a2-109">Selecting a Dimension</span></span>  
 <span data-ttu-id="5b4a2-110">Dans la première page **Spécifier l'ordre des attributs** de l'Assistant, vous spécifiez la dimension à laquelle vous voulez appliquer le classement des attributs.</span><span class="sxs-lookup"><span data-stu-id="5b4a2-110">On the first **Specify Attribute Ordering** page of the wizard, you specify the dimension to which you want to apply attribute ordering.</span></span> <span data-ttu-id="5b4a2-111">L'ajout de la fonctionnalité de classement des attributs à la dimension sélectionnée apportera des modifications à cette dimension.</span><span class="sxs-lookup"><span data-stu-id="5b4a2-111">The attribute ordering enhancement added to this selected dimension will result in changes to the dimension.</span></span> <span data-ttu-id="5b4a2-112">Ces modifications seront héritées par tous les cubes contenant la dimension sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5b4a2-112">These changes will be inherited by all cubes that include the selected dimension.</span></span>  
  
## <a name="specifying-ordering"></a><span data-ttu-id="5b4a2-113">Spécification du classement</span><span class="sxs-lookup"><span data-stu-id="5b4a2-113">Specifying Ordering</span></span>  
 <span data-ttu-id="5b4a2-114">Dans la deuxième page **Spécifier l'ordre des attributs** de l'Assistant, vous spécifiez comment tous les attributs de la dimension vont être classés.</span><span class="sxs-lookup"><span data-stu-id="5b4a2-114">On the second **Specify Attribute Ordering** page of the wizard, you specify how all the attributes in the dimension will be ordered.</span></span>  
  
 <span data-ttu-id="5b4a2-115">Dans la colonne **Attribut de classement** , vous pouvez modifier l'attribut utilisé pour effectuer le classement.</span><span class="sxs-lookup"><span data-stu-id="5b4a2-115">In the **Ordering Attribute** column, you can change the attribute used to do the ordering.</span></span> <span data-ttu-id="5b4a2-116">Si l’attribut que vous souhaitez utiliser pour ordonner des membres ne figure pas dans la liste, faites défiler la liste vers le dessous, puis sélectionnez **\<New attribute...>** pour ouvrir la boîte de dialogue **Sélectionner une colonne** , dans laquelle vous pouvez sélectionner une colonne dans une table de dimension.</span><span class="sxs-lookup"><span data-stu-id="5b4a2-116">If the attribute that you want to use to order members is not in the list, scroll down the list, and then select **\<New attribute...>** to open the **Select a Column** dialog box, where you can select a column in a dimension table.</span></span> <span data-ttu-id="5b4a2-117">En sélectionnant une colonne à l'aide de la boîte de dialogue **Sélectionner une colonne** , vous allez créer un attribut supplémentaire qui servira à classer les membres d'un attribut.</span><span class="sxs-lookup"><span data-stu-id="5b4a2-117">Selecting a column by using the **Select a Column** dialog box creates an additional attribute with which to order members of an attribute.</span></span>  
  
 <span data-ttu-id="5b4a2-118">Dans la colonne **Critères** , vous pouvez ensuite choisir si les membres de l'attribut doivent être classés par **Clé** ou par **Nom**.</span><span class="sxs-lookup"><span data-stu-id="5b4a2-118">In the **Criteria** column, you can then select whether to order the members of the attribute by either **Key** or **Name**.</span></span>  
  
  
