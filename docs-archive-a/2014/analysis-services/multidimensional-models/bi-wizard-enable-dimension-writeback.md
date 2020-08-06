---
title: Activer l’écriture différée de la dimension | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying dimensions
- writeback [Analysis Services], setting up
- dimensions [Analysis Services], Business Intelligence enhancements
- Business Intelligence enhancements [Analysis Services], writeback
- dimensions [Analysis Services], writeback
- writeback [Analysis Services]
- dimensions [Analysis Services], modifying
- manual dimension structure modifications
ms.assetid: a4b5eb5a-366d-4fc8-ad0d-5bdb8e7b4163
author: minewiskan
ms.author: owend
ms.openlocfilehash: cba4a54e8a51d022c6f84a4c81d32f359a95692a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603109"
---
# <a name="enable-dimension-writeback"></a><span data-ttu-id="a5b0d-102">Activer l'écriture différée de la dimension</span><span class="sxs-lookup"><span data-stu-id="a5b0d-102">Enable Dimension Writeback</span></span>
  <span data-ttu-id="a5b0d-103">Ajoutez la fonctionnalité d'écriture en différé de la dimension à un cube ou à une dimension afin de permettre aux utilisateurs de modifier manuellement la structure et les membres de la dimension.</span><span class="sxs-lookup"><span data-stu-id="a5b0d-103">Add the dimension writeback enhancement to a cube or dimension to allow users to manually modify the dimension structure and members.</span></span> <span data-ttu-id="a5b0d-104">Les mises à jour dans une dimension activée en écriture sont enregistrées directement dans la table de la dimension.</span><span class="sxs-lookup"><span data-stu-id="a5b0d-104">Updates to a write-enabled dimension are recorded directly in the dimension table.</span></span> <span data-ttu-id="a5b0d-105">Cette amélioration modifie la définition de la propriété `WriteEnabled` pour une dimension.</span><span class="sxs-lookup"><span data-stu-id="a5b0d-105">This enhancement changes the `WriteEnabled` property setting for a dimension.</span></span>  
  
 <span data-ttu-id="a5b0d-106">Pour ajouter l’écriture différée de la dimension, utilisez l’Assistant Business Intelligence, puis sélectionnez l’option **Activer l’écriture différée de la dimension** dans la page **Choisir des améliorations** .</span><span class="sxs-lookup"><span data-stu-id="a5b0d-106">To add dimension writeback, you use the Business Intelligence Wizard, and select the **Enable dimension writeback** option on the **Choose Enhancement** page.</span></span> <span data-ttu-id="a5b0d-107">Cet Assistant vous guide tout au long des étapes de sélection d'une dimension à laquelle vous souhaitez appliquer l'écriture en différé et de définition de cette option pour la dimension sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a5b0d-107">This wizard then guides you through the steps of selecting a dimension to which you want to apply dimension writeback and setting this option for the selected dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a5b0d-108">L'écriture différée est prise en charge uniquement pour les mini-Data Warehouse et les bases de données relationnelles SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a5b0d-108">Writeback is supported for SQL Server relational databases and data marts only.</span></span>  
  
## <a name="selecting-a-dimension"></a><span data-ttu-id="a5b0d-109">Sélection d'une dimension</span><span class="sxs-lookup"><span data-stu-id="a5b0d-109">Selecting a Dimension</span></span>  
 <span data-ttu-id="a5b0d-110">Dans la première page **Activer l’écriture différée de la dimension** de l’Assistant, vous spécifiez la dimension à laquelle vous souhaitez appliquer l’écriture différée.</span><span class="sxs-lookup"><span data-stu-id="a5b0d-110">On the first **Enable Dimension Writeback** page of the wizard, you specify the dimension to which you want to apply dimension writeback.</span></span> <span data-ttu-id="a5b0d-111">L'amélioration que constitue l'écriture différée ajoutée à cette dimension se traduit par des modifications de la dimension.</span><span class="sxs-lookup"><span data-stu-id="a5b0d-111">The dimension writeback enhancement added to this selected dimension will result in changes to the dimension.</span></span> <span data-ttu-id="a5b0d-112">Ces modifications seront héritées par tous les cubes contenant la dimension sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a5b0d-112">These changes will be inherited by all cubes that include the selected dimension.</span></span>  
  
## <a name="setting-dimension-writeback-capability"></a><span data-ttu-id="a5b0d-113">Définition de la fonctionnalité d'écriture en différé de la dimension</span><span class="sxs-lookup"><span data-stu-id="a5b0d-113">Setting Dimension Writeback Capability</span></span>  
 <span data-ttu-id="a5b0d-114">Dans la deuxième page **Activer l’écriture différée de la dimension** de l’Assistant, vous paramétrez réellement l’option **Activer l’écriture différée de la dimension** .</span><span class="sxs-lookup"><span data-stu-id="a5b0d-114">On the second **Enable Dimension Writeback** page of the wizard, you actually set the **Enable writeback in the dimension** option.</span></span> <span data-ttu-id="a5b0d-115">Lorsque cette option est automatiquement sélectionnée, la propriété `WriteEnabled` de la dimension a la valeur `True`.</span><span class="sxs-lookup"><span data-stu-id="a5b0d-115">Selecting this option automatically sets the `WriteEnabled` property of the dimension to `True`.</span></span> <span data-ttu-id="a5b0d-116">Lorsque cette option est automatiquement désactivée, la propriété a la valeur `False`.</span><span class="sxs-lookup"><span data-stu-id="a5b0d-116">Clearing this option automatically sets the property to `False`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5b0d-117">Notes</span><span class="sxs-lookup"><span data-stu-id="a5b0d-117">Remarks</span></span>  
 <span data-ttu-id="a5b0d-118">Lorsque vous créez un membre, vous devez inclure chaque attribut dans une dimension.</span><span class="sxs-lookup"><span data-stu-id="a5b0d-118">When you create a new member, you must include every attribute in a dimension.</span></span> <span data-ttu-id="a5b0d-119">Vous ne pouvez pas insérer un membre sans définir la valeur de l'attribut clé de la dimension.</span><span class="sxs-lookup"><span data-stu-id="a5b0d-119">You cannot insert a member without specifying a value for the key attribute of the dimension.</span></span> <span data-ttu-id="a5b0d-120">Par conséquent, la création de membres est soumise aux contraintes (telles que valeurs de clés non NULL) définies dans la table de dimension.</span><span class="sxs-lookup"><span data-stu-id="a5b0d-120">Therefore, creating members is subject to any constraints (such as non-null key values) that are defined on the dimension table.</span></span> <span data-ttu-id="a5b0d-121">Vous devez également tenir compte des colonnes éventuellement spécifiées par les propriétés de dimension, telles que les colonnes spécifiées dans les propriétés de dimension `CustomRollupColumn`, `CustomRollupPropertiesColumn` ou `UnaryOperatorColumn`.</span><span class="sxs-lookup"><span data-stu-id="a5b0d-121">You should also consider columns optionally specified by dimension properties, such as columns specified in the `CustomRollupColumn`, `CustomRollupPropertiesColumn` or the `UnaryOperatorColumn` dimension properties.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="a5b0d-122">Si vous utilisez SQL Azure comme source de données pour effectuer une écriture différée dans une base de données Analysis Services, l'opération échoue.</span><span class="sxs-lookup"><span data-stu-id="a5b0d-122">If you use SQL Azure as a data source to perform writeback into an Analysis Services database, the operation fails.</span></span> <span data-ttu-id="a5b0d-123">Il s'agit d'un comportement par défaut, car l'option de fournisseur qui active plusieurs jeux de résultats actifs MARS n'est pas activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="a5b0d-123">This is by design, because the provider option that enables multiple active result sets (MARS) is not turned on by default.</span></span>  
>   
>  <span data-ttu-id="a5b0d-124">La solution consiste à ajouter le paramètre suivant dans la chaîne de connexion, afin de prendre en charge MARS et d'activer l'écriture différée :</span><span class="sxs-lookup"><span data-stu-id="a5b0d-124">The workaround is to add the following setting in the connection string, to support MARS and to enable writeback:</span></span>  
>   
>  `"MultipleActiveResultSets=True"`  
>   
>  <span data-ttu-id="a5b0d-125">Pour plus d’informations, consultez [utilisation de plusieurs jeux de résultats actifs &#40;&#41;mars ](../../relational-databases/native-client/features/using-multiple-active-result-sets-mars.md).</span><span class="sxs-lookup"><span data-stu-id="a5b0d-125">For more information see [Using Multiple Active Result Sets &#40;MARS&#41;](../../relational-databases/native-client/features/using-multiple-active-result-sets-mars.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5b0d-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a5b0d-126">See Also</span></span>  
 [<span data-ttu-id="a5b0d-127">Dimensions activées en écriture</span><span class="sxs-lookup"><span data-stu-id="a5b0d-127">Write-Enabled Dimensions</span></span>](../multidimensional-models-olap-logical-dimension-objects/write-enabled-dimensions.md)  
  
  
