---
title: Masquage et désactivation des hiérarchies d’attributs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 095039c2-7104-414c-a9a6-327b03ce79df
author: minewiskan
ms.author: owend
ms.openlocfilehash: cc043c68d2a83424a14707799fd90bf893abc12d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709992"
---
# <a name="hiding-and-disabling-attribute-hierarchies"></a><span data-ttu-id="8b2fb-102">Masquage et désactivation des hiérarchies d'attributs</span><span class="sxs-lookup"><span data-stu-id="8b2fb-102">Hiding and Disabling Attribute Hierarchies</span></span>
  <span data-ttu-id="8b2fb-103">Par défaut, une hiérarchie d'attribut est créée pour chaque attribut dans une dimension, et chaque hiérarchie est disponible pour dimensionner les données de faits.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-103">By default, an attribute hierarchy is created for every attribute in a dimension, and each hierarchy is available for dimensioning fact data.</span></span> <span data-ttu-id="8b2fb-104">Cette hiérarchie se compose d'un niveau « All » et d'un niveau de détail contenant tous les membres de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-104">This hierarchy consists of an "All" level and a detail level containing all members of the hierarchy.</span></span> <span data-ttu-id="8b2fb-105">Comme vous l'avez déjà appris, vous pouvez organiser les attributs en hiérarchies définies par l'utilisateur pour fournir les chemins de navigation dans un cube.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-105">As you have already learned, you can organize attributes into user-defined hierarchies to provide navigation paths in a cube.</span></span> <span data-ttu-id="8b2fb-106">Dans certaines circonstances, vous pouvez être amené à choisir de désactiver ou de masquer certains attributs et leurs hiérarchies.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-106">Under certain circumstances, you may want to disable or hide some attributes and their hierarchies.</span></span> <span data-ttu-id="8b2fb-107">Par exemple, certains attributs, tels que les numéros de sécurité sociale ou les numéros de carte d'identité, les taux de rémunération, les dates de naissance et les informations de connexion ne sont pas des attributs par lesquels les utilisateurs pourront dimensionner les informations d'un cube.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-107">For example, certain attributes such as social security numbers or national identification numbers, pay rates, birth dates, and login information are not attributes by which users will dimension cube information.</span></span> <span data-ttu-id="8b2fb-108">Ces informations sont au contraire généralement affichées uniquement comme détails d'un membre d'attribut spécifique.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-108">Instead, this information is generally only viewed as details of a particular attribute member.</span></span> <span data-ttu-id="8b2fb-109">Vous pouvez choisir de masquer ces hiérarchies d'attributs, ce qui permet de laisser les attributs affichés uniquement en tant que propriétés de membre d'un attribut spécifique.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-109">You may want to hide these attribute hierarchies, leaving the attributes visible only as member properties of a specific attribute.</span></span> <span data-ttu-id="8b2fb-110">Vous pouvez également choisir d'afficher les membres d'autres attributs, tels que les noms de clients ou les codes postaux, uniquement lorsqu'ils sont visualisés via une hiérarchie utilisateur et non indépendamment via une hiérarchie d'attributs.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-110">You may also want to make members of other attributes, such as customer names or postal codes, visible only when they are viewed through a user hierarchy instead of independently through an attribute hierarchy.</span></span> <span data-ttu-id="8b2fb-111">L'une des raisons qui amène à procéder ainsi est le nombre même de membres distincts dans la hiérarchie d'attributs.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-111">One reason to do so may be the sheer number of distinct members in the attribute hierarchy.</span></span> <span data-ttu-id="8b2fb-112">Enfin, pour améliorer les performances de traitement, vous devez désactiver les hiérarchies d'attributs auxquelles les utilisateurs ne feront pas appel pour l'exploration.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-112">Finally, to improve processing performance, you should disable attribute hierarchies that users will not use for browsing.</span></span>

 <span data-ttu-id="8b2fb-113">La valeur de la propriété **AttributeHierarchyEnabled** détermine la création d'une hiérarchie d'attributs.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-113">The value of the **AttributeHierarchyEnabled** property determines whether an attribute hierarchy is created.</span></span> <span data-ttu-id="8b2fb-114">Si la valeur de cette propriété est **False**, la hiérarchie d'attributs n'est pas créée et l'attribut ne peut pas être utilisé comme niveau dans une hiérarchie utilisateur : la hiérarchie d'attributs existe uniquement en tant que propriété de membre.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-114">If this property is set to **False**, the attribute hierarchy is not created and the attribute cannot be used as a level in a user hierarchy; the attribute hierarchy exists as a member property only.</span></span> <span data-ttu-id="8b2fb-115">Toutefois, il est toujours possible d'utiliser une hiérarchie d'attributs désactivée pour classer les membres d'un autre attribut.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-115">However, a disabled attribute hierarchy can still be used to order the members of another attribute.</span></span> <span data-ttu-id="8b2fb-116">Si la valeur de la propriété **AttributeHierarchyEnabled** est **True**, la valeur de la propriété **AttributeHierarchyVisible** détermine si la hiérarchie d’attributs est visible indépendamment de son utilisation dans une hiérarchie définie par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-116">If the value of the **AttributeHierarchyEnabled** property is set to **True**, the value of the **AttributeHierarchyVisible** property determines whether the attribute hierarchy is visible independent of its use in a user-defined hierarchy.</span></span>

 <span data-ttu-id="8b2fb-117">Lorsqu'une hiérarchie d'attributs est activée, vous pouvez spécifier des valeurs pour les trois autres propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="8b2fb-117">When an attribute hierarchy is enabled, you may want to specify values for the following three additional properties:</span></span>

-   <span data-ttu-id="8b2fb-118">**IsAggregatable**</span><span class="sxs-lookup"><span data-stu-id="8b2fb-118">**IsAggregatable**</span></span>

     <span data-ttu-id="8b2fb-119">Par défaut, un niveau (All) est défini pour toutes les hiérarchies d'attributs.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-119">By default, an (All) level is defined for all attribute hierarchies.</span></span> <span data-ttu-id="8b2fb-120">Pour désactiver le niveau (All) d’une hiérarchie d’attributs activée, affectez la valeur **False**à cette propriété.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-120">To disable the (All) level for an enabled attribute hierarchy, set the value for this property to **False**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="8b2fb-121">Un attribut dont la propriété **IsAggregatable** a la valeur false peut être utilisé uniquement comme racine d’une hiérarchie définie par l’utilisateur et doit avoir un membre par défaut spécifié (sinon, le moteur [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] en choisit un à votre place).</span><span class="sxs-lookup"><span data-stu-id="8b2fb-121">An attribute that has its **IsAggregatable** property set to false can only be used as the root of a user-defined hierarchy and must have a default member specified (otherwise, one will be chosen for you by the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] engine).</span></span>

-   <span data-ttu-id="8b2fb-122">**AttributeHierarchyOrdered**</span><span class="sxs-lookup"><span data-stu-id="8b2fb-122">**AttributeHierarchyOrdered**</span></span>

     <span data-ttu-id="8b2fb-123">Par défaut, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] classe les membres des hiérarchies d'attributs activées au cours du traitement, puis stocke les membres en fonction de la valeur de la propriété **OrderBy** . Par exemple, en fonction de la valeur Name ou Key.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-123">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] orders the members of enabled attribute hierarchies during processing, and then stores the members by the value of the **OrderBy** property, such as by Name or Key.</span></span> <span data-ttu-id="8b2fb-124">Si le classement ne présente pas d'intérêt pour vous, affectez à cette propriété la valeur **False**pour augmenter les performances de traitement.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-124">If you do not care about ordering, you can increase processing performance by setting the value of this property to **False**.</span></span>

-   <span data-ttu-id="8b2fb-125">**AttributeHierarchyOptimizedState**</span><span class="sxs-lookup"><span data-stu-id="8b2fb-125">**AttributeHierarchyOptimizedState**</span></span>

     <span data-ttu-id="8b2fb-126">Par défaut, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] crée un index pour chaque hiérarchie d'attributs activée au cours du traitement pour améliorer les performances des requêtes.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-126">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] creates an index for each enabled attribute hierarchy during processing, to improve query performance.</span></span> <span data-ttu-id="8b2fb-127">Si vous envisagez de ne pas utiliser de hiérarchies d'attributs pour l'exploration, vous pouvez augmenter les performances de traitement en affectant à cette propriété la valeur **NotOptimized**.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-127">If you do not plan to use an attribute hierarchy for browsing, you can increase processing performance by setting the value of this property to **NotOptimized**.</span></span> <span data-ttu-id="8b2fb-128">Cependant, si vous utilisez une hiérarchie masquée comme attribut clé de la dimension, le fait de créer un index des membres d'attribut permet d'améliorer les performances.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-128">However, if you use a hidden hierarchy as the key attribute for the dimension, creating an index of the attribute members will still improve performance.</span></span>

 <span data-ttu-id="8b2fb-129">Ces propriétés ne peuvent pas être utilisées lorsque la hiérarchie d'attributs est désactivée.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-129">These properties do not apply if an attribute hierarchy is disabled.</span></span>

 <span data-ttu-id="8b2fb-130">Au cours des tâches de cette rubrique, vous allez désactiver les numéros de sécurité sociale et d'autres attributs dans la dimension Employee qui ne seront pas utilisés pour l'exploration.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-130">In the tasks in this topic, you will disable social security numbers and other attributes in the Employee dimension that will not be used for browsing.</span></span> <span data-ttu-id="8b2fb-131">Vous allez ensuite masquer les hiérarchies d'attributs relatives aux noms de clients et aux codes postaux dans la dimension Customer.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-131">You will then hide the customer name and postal code attribute hierarchies in the Customer dimension.</span></span> <span data-ttu-id="8b2fb-132">En raison du grand nombre de membres d'attribut dans ces hiérarchies, leur exploration est relativement lente, indépendamment d'une hiérarchie utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-132">The large number of attribute members in these hierarchies will make browsing these hierarchies very slow independent of a user hierarchy.</span></span>

## <a name="setting-attribute-hierarchy-properties-in-the-employee-dimension"></a><span data-ttu-id="8b2fb-133">Définition des propriétés des hiérarchies d'attributs de la dimension Employee</span><span class="sxs-lookup"><span data-stu-id="8b2fb-133">Setting Attribute Hierarchy Properties in the Employee Dimension</span></span>

1.  <span data-ttu-id="8b2fb-134">Affichez le Concepteur de dimensions pour la dimension Employee, puis cliquez sur l'onglet **Navigateur** .</span><span class="sxs-lookup"><span data-stu-id="8b2fb-134">Switch to Dimension Designer for the Employee dimension, and then click the **Browser** tab.</span></span>

2.  <span data-ttu-id="8b2fb-135">Vérifiez si les hiérarchies d'attributs suivantes apparaissent dans la liste **Hiérarchie** :</span><span class="sxs-lookup"><span data-stu-id="8b2fb-135">Verify that the following attribute hierarchies appear in the **Hierarchy** list:</span></span>

    -   <span data-ttu-id="8b2fb-136">**Base Rate**</span><span class="sxs-lookup"><span data-stu-id="8b2fb-136">**Base Rate**</span></span>

    -   <span data-ttu-id="8b2fb-137">**Birth Date**</span><span class="sxs-lookup"><span data-stu-id="8b2fb-137">**Birth Date**</span></span>

    -   <span data-ttu-id="8b2fb-138">**Nom d'accès**</span><span class="sxs-lookup"><span data-stu-id="8b2fb-138">**Login ID**</span></span>

    -   <span data-ttu-id="8b2fb-139">**Manager SSN**</span><span class="sxs-lookup"><span data-stu-id="8b2fb-139">**Manager SSN**</span></span>

    -   <span data-ttu-id="8b2fb-140">**N**</span><span class="sxs-lookup"><span data-stu-id="8b2fb-140">**SSN**</span></span>

3.  <span data-ttu-id="8b2fb-141">Affichez l'onglet **Structure de dimension** , puis sélectionnez les attributs suivants dans le volet **Attributs** .</span><span class="sxs-lookup"><span data-stu-id="8b2fb-141">Switch to the **Dimension Structure** tab, and then select the following attributes in the **Attributes** pane.</span></span> <span data-ttu-id="8b2fb-142">Vous pouvez sélectionner plusieurs mesures en cliquant sur chacune d'elles tout en maintenant enfoncée la touche CTRL :</span><span class="sxs-lookup"><span data-stu-id="8b2fb-142">You can select multiple measures by clicking each while holding down the CTRL key:</span></span>

    -   <span data-ttu-id="8b2fb-143">**Base Rate**</span><span class="sxs-lookup"><span data-stu-id="8b2fb-143">**Base Rate**</span></span>

    -   <span data-ttu-id="8b2fb-144">**Birth Date**</span><span class="sxs-lookup"><span data-stu-id="8b2fb-144">**Birth Date**</span></span>

    -   <span data-ttu-id="8b2fb-145">**Nom d'accès**</span><span class="sxs-lookup"><span data-stu-id="8b2fb-145">**Login ID**</span></span>

    -   <span data-ttu-id="8b2fb-146">**Manager SSN**</span><span class="sxs-lookup"><span data-stu-id="8b2fb-146">**Manager SSN**</span></span>

    -   <span data-ttu-id="8b2fb-147">**N**</span><span class="sxs-lookup"><span data-stu-id="8b2fb-147">**SSN**</span></span>

4.  <span data-ttu-id="8b2fb-148">Dans la fenêtre des propriétés, affectez la valeur **False** à la propriété **AttributeHierarchyEnabled** pour les attributs sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-148">In the Properties window, set the value of the **AttributeHierarchyEnabled** property to **False** for the selected attributes.</span></span>

     <span data-ttu-id="8b2fb-149">Notez, dans le volet **Attributs** , que l'icône de chaque attribut change pour indiquer que l'attribut n'est pas activé.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-149">Notice in the **Attributes** pane that the icon for each attribute has changed to indicate that the attribute is not enabled.</span></span>

     <span data-ttu-id="8b2fb-150">L'illustration suivante montre la propriété **AttributeHierarchyEnabled** avec la valeur False pour les attributs sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-150">The following image shows the **AttributeHierarchyEnabled** property set to False for the selected attributes.</span></span>

     <span data-ttu-id="8b2fb-151">![Propriété AttributeHierarchyEnabled avec la valeur False](../../2014/tutorials/media/l4-hierarchyenabled-1.gif "Propriété AttributeHierarchyEnabled avec la valeur False")</span><span class="sxs-lookup"><span data-stu-id="8b2fb-151">![AttributeHierarchyEnabled property set to False](../../2014/tutorials/media/l4-hierarchyenabled-1.gif "AttributeHierarchyEnabled property set to False")</span></span>

5.  <span data-ttu-id="8b2fb-152">Dans le menu **Générer** , cliquez sur **Déployer Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-152">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>

6.  <span data-ttu-id="8b2fb-153">Une fois le traitement terminé, affichez l'onglet **Navigateur** , cliquez sur **Reconnexion**, puis essayez d'explorer chaque hiérarchie d'attribut modifiée.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-153">When processing has successfully completed, switch to the **Browser** tab, click **Reconnect**, and then try to browse the modified attribute hierarchies.</span></span>

     <span data-ttu-id="8b2fb-154">Notez que les membres des attributs modifiés ne sont pas disponibles dans la liste **Hiérarchie** et ne peuvent pas faire l'objet d'une exploration en tant que hiérarchies d'attributs.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-154">Notice that the members of the modified attributes are not available for browsing as attribute hierarchies in the **Hierarchy** list.</span></span> <span data-ttu-id="8b2fb-155">Si vous tentez d'ajouter l'une des hiérarchies d'attributs désactivées en tant que niveau dans une hiérarchie utilisateur, vous recevrez un message d'erreur signalant que la hiérarchie d'attributs doit être activée pour faire partie d'une hiérarchie définie par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-155">If you try to add one of the disabled attribute hierarchies as a level in a user hierarchy, you will receive an error notifying you that the attribute hierarchy must be enabled to participate in a user-defined hierarchy.</span></span>

## <a name="setting-attribute-hierarchy-properties-in-the-customer-dimension"></a><span data-ttu-id="8b2fb-156">Définition des propriétés des hiérarchies d'attributs de la dimension Customer</span><span class="sxs-lookup"><span data-stu-id="8b2fb-156">Setting Attribute Hierarchy Properties in the Customer Dimension</span></span>

1.  <span data-ttu-id="8b2fb-157">Affichez le Concepteur de dimensions pour la dimension Customer, puis cliquez sur l'onglet **Navigateur** .</span><span class="sxs-lookup"><span data-stu-id="8b2fb-157">Switch to Dimension Designer for the Customer dimension, and then click the **Browser** tab.</span></span>

2.  <span data-ttu-id="8b2fb-158">Vérifiez si les hiérarchies d'attributs suivantes apparaissent dans la liste **Hiérarchie** :</span><span class="sxs-lookup"><span data-stu-id="8b2fb-158">Verify that the following attribute hierarchies appear in the **Hierarchy** list:</span></span>

    -   <span data-ttu-id="8b2fb-159">**Nom complet**</span><span class="sxs-lookup"><span data-stu-id="8b2fb-159">**Full Name**</span></span>

    -   <span data-ttu-id="8b2fb-160">**Postal Code**</span><span class="sxs-lookup"><span data-stu-id="8b2fb-160">**Postal Code**</span></span>

3.  <span data-ttu-id="8b2fb-161">Affichez l'onglet **Structure de dimension** , puis sélectionnez les attributs suivants dans le volet **Attributs** . Pour cela, utilisez la touche CTRL pour sélectionner plusieurs attributs en même temps :</span><span class="sxs-lookup"><span data-stu-id="8b2fb-161">Switch to the **Dimension Structure** tab, and then select the following attributes in the **Attributes** pane by using the CTRL key to select multiple attributes at the same time:</span></span>

    -   <span data-ttu-id="8b2fb-162">**Nom complet**</span><span class="sxs-lookup"><span data-stu-id="8b2fb-162">**Full Name**</span></span>

    -   <span data-ttu-id="8b2fb-163">**Postal Code**</span><span class="sxs-lookup"><span data-stu-id="8b2fb-163">**Postal Code**</span></span>

4.  <span data-ttu-id="8b2fb-164">Dans la fenêtre des propriétés, affectez la valeur **False** à la propriété **AttributeHierarchyVisible** pour les attributs sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-164">In the Properties window, set the value of the **AttributeHierarchyVisible** property to **False** for the selected attributes.</span></span>

     <span data-ttu-id="8b2fb-165">Étant donné que les membres de ces hiérarchies d'attributs seront utilisés pour dimensionner les données de faits, le fait de classer et d'optimiser ces membres permettra d'améliorer les performances.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-165">Because the members of these attribute hierarchies will be used for dimensioning fact data, ordering and optimizing the members of these attribute hierarchies will improve performance.</span></span> <span data-ttu-id="8b2fb-166">Les propriétés de ces attributs ne doivent par conséquent pas être modifiées.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-166">Therefore, the properties of these attributes should not be changed.</span></span>

     <span data-ttu-id="8b2fb-167">L'illustration suivante montre la propriété **AttributeHierarchyVisible** avec la valeur False.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-167">The following image shows the **AttributeHierarchyVisible** property set to False.</span></span>

     <span data-ttu-id="8b2fb-168">![Propriété AttributeHierarchyVisible avec la valeur False](../../2014/tutorials/media/l4-hierarchyvisible-1.gif "Propriété AttributeHierarchyVisible avec la valeur False")</span><span class="sxs-lookup"><span data-stu-id="8b2fb-168">![AttributeHierarchyVisible property set to False](../../2014/tutorials/media/l4-hierarchyvisible-1.gif "AttributeHierarchyVisible property set to False")</span></span>

5.  <span data-ttu-id="8b2fb-169">Faites glisser l'attribut **Postal Code** du volet **Attributs** vers la hiérarchie utilisateur **Customer Geography** du volet **Hiérarchies et niveaux** , immédiatement sous le niveau **City** .</span><span class="sxs-lookup"><span data-stu-id="8b2fb-169">Drag the **Postal Code** attribute from the **Attributes** pane into the **Customer Geography** user hierarchy in the **Hierarchies and Levels** pane, immediately under the **City** level.</span></span>

     <span data-ttu-id="8b2fb-170">Notez qu'il est toujours possible de transformer un attribut masqué en niveau dans une hiérarchie utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-170">Notice that a hidden attribute can still become a level in a user hierarchy.</span></span>

6.  <span data-ttu-id="8b2fb-171">Dans le menu **Générer** , cliquez sur **Déployer Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-171">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>

7.  <span data-ttu-id="8b2fb-172">Une fois le déploiement terminé, cliquez sur l'onglet **Navigateur** de la dimension Customer, puis cliquez sur **Reconnexion**.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-172">When deployment has successfully completed, switch to the **Browser** tab for the Customer dimension, and then click **Reconnect**.</span></span>

8.  <span data-ttu-id="8b2fb-173">Essayez de sélectionner l'une ou l'autre des hiérarchies d'attribut modifiées dans la liste **Hiérarchie** .</span><span class="sxs-lookup"><span data-stu-id="8b2fb-173">Try to select either of the modified attribute hierarchies from the **Hierarchy** list.</span></span>

     <span data-ttu-id="8b2fb-174">Notez qu'aucune hiérarchie d'attributs modifiée n'apparaît dans la liste **Hiérarchie** .</span><span class="sxs-lookup"><span data-stu-id="8b2fb-174">Notice that neither of the modified attribute hierarchies appears in the **Hierarchy** list.</span></span>

9. <span data-ttu-id="8b2fb-175">Dans la liste **Hiérarchie** , sélectionnez **Customer Geography**, puis explorez chaque niveau dans le volet Navigateur.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-175">In the **Hierarchy** list, select **Customer Geography**, and then browse each level in the browser pane.</span></span>

     <span data-ttu-id="8b2fb-176">Notez que les niveaux masqués, **Postal Code** et **Full Name**, sont visibles dans la hiérarchie définie par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8b2fb-176">Notice that the hidden levels, **Postal Code** and **Full Name**, are visible in the user-defined hierarchy.</span></span>

## <a name="next-task-in-lesson"></a><span data-ttu-id="8b2fb-177">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="8b2fb-177">Next Task in Lesson</span></span>
 [<span data-ttu-id="8b2fb-178">Tri des membres d’attribut sur la base d’un attribut secondaire</span><span class="sxs-lookup"><span data-stu-id="8b2fb-178">Sorting Attribute Members Based on a Secondary Attribute</span></span>](lesson-4-5-sorting-attribute-members-based-on-a-secondary-attribute.md)


