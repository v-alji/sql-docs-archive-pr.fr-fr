---
title: Créer un attribut de date (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating date attributes [Master Data Services]
- attributes [Master Data Services], creating date attributes
ms.assetid: 22a8f1a3-b4f2-4cfa-8495-7daad5ce9d12
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 93797b90ff03c6a2b60ce8e015897a46a7448aad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600130"
---
# <a name="create-a-date-attribute-master-data-services"></a><span data-ttu-id="dbd43-102">Créer un attribut de date (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="dbd43-102">Create a Date Attribute (Master Data Services)</span></span>
  <span data-ttu-id="dbd43-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], vous pouvez créer un attribut date lorsque vous souhaitez que les utilisateurs entrent une date comme valeur d'attribut.</span><span class="sxs-lookup"><span data-stu-id="dbd43-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a date attribute when you want users to enter a date as an attribute value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dbd43-104">L'attribut est appelée DateTime, mais les valeurs d'heure ne sont pas prises en charge.</span><span class="sxs-lookup"><span data-stu-id="dbd43-104">The attribute is called DateTime, but time values are not supported.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="dbd43-105">Prérequis</span><span class="sxs-lookup"><span data-stu-id="dbd43-105">Prerequisites</span></span>  
 <span data-ttu-id="dbd43-106">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="dbd43-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="dbd43-107">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .</span><span class="sxs-lookup"><span data-stu-id="dbd43-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="dbd43-108">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="dbd43-108">You must be a model administrator.</span></span> <span data-ttu-id="dbd43-109">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="dbd43-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="dbd43-110">Vous devez avoir une entité pour laquelle créer l'attribut.</span><span class="sxs-lookup"><span data-stu-id="dbd43-110">You must have an entity to create the attribute for.</span></span> <span data-ttu-id="dbd43-111">Pour plus d’informations, consultez [créer une entité &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="dbd43-111">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-date-attribute"></a><span data-ttu-id="dbd43-112">Pour créer un attribut de date</span><span class="sxs-lookup"><span data-stu-id="dbd43-112">To create a date attribute</span></span>  
  
1.  <span data-ttu-id="dbd43-113">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="dbd43-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="dbd43-114">Dans la page **Vue du modèle** , dans la barre de menus, pointez sur **Gérer** , puis cliquez sur **Entités**.</span><span class="sxs-lookup"><span data-stu-id="dbd43-114">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="dbd43-115">Dans la page **Maintenance de l'entité** , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="dbd43-115">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="dbd43-116">Sélectionnez la ligne de l'entité pour laquelle vous souhaitez créer un attribut.</span><span class="sxs-lookup"><span data-stu-id="dbd43-116">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="dbd43-117">Cliquez sur **Modifier l'entité sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="dbd43-117">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="dbd43-118">Dans la page **Modifier l'entité** :</span><span class="sxs-lookup"><span data-stu-id="dbd43-118">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="dbd43-119">Si l'attribut est destiné à des membres feuille, dans le volet **Attributs de membre feuille** , cliquez sur **Ajouter un attribut feuille**.</span><span class="sxs-lookup"><span data-stu-id="dbd43-119">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="dbd43-120">Si l'attribut est destiné à des membres consolidés, dans le volet **Attributs de membre consolidé** , cliquez sur **Ajouter un attribut consolidé**.</span><span class="sxs-lookup"><span data-stu-id="dbd43-120">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="dbd43-121">Si l'attribut est destiné à des collections, dans le volet **Attributs de collection** , cliquez sur **Ajouter un attribut de collection**.</span><span class="sxs-lookup"><span data-stu-id="dbd43-121">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="dbd43-122">Dans la page **Ajouter un attribut** , sélectionnez l'option **Forme libre** .</span><span class="sxs-lookup"><span data-stu-id="dbd43-122">On the **Add Attribute** page, select the **Free-form** option.</span></span>  
  
8.  <span data-ttu-id="dbd43-123">Dans la zone **Nom** , tapez un nom pour l'attribut.</span><span class="sxs-lookup"><span data-stu-id="dbd43-123">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="dbd43-124">Pour obtenir la liste des mots qui ne doivent pas être utilisés comme noms d’attribut, consultez la section [Mots réservés &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="dbd43-124">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="dbd43-125">Dans la zone **Largeur d'affichage en pixels** , tapez la largeur de la colonne d'attribut à afficher dans la grille **Explorateur** .</span><span class="sxs-lookup"><span data-stu-id="dbd43-125">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="dbd43-126">Dans la liste **Type de données** , sélectionnez **DateTime**.</span><span class="sxs-lookup"><span data-stu-id="dbd43-126">From the **Data type** list, select **DateTime**.</span></span>  
  
11. <span data-ttu-id="dbd43-127">Dans la liste **Masque d’entrée** , sélectionnez un format pour les dates.</span><span class="sxs-lookup"><span data-stu-id="dbd43-127">From the **Input mask** list, select a format for dates.</span></span>  
  
12. <span data-ttu-id="dbd43-128">Sélectionnez éventuellement **Activer le suivi des modifications** pour effectuer le suivi des modifications apportées aux groupes d'attributs.</span><span class="sxs-lookup"><span data-stu-id="dbd43-128">Optionally, select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="dbd43-129">Pour plus d’informations, consultez [Ajouter des attributs à un groupe de suivi des modifications &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="dbd43-129">For more information, see [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span></span>  
  
13. <span data-ttu-id="dbd43-130">Cliquez sur **Enregistrer l'attribut**.</span><span class="sxs-lookup"><span data-stu-id="dbd43-130">Click **Save attribute**.</span></span>  
  
14. <span data-ttu-id="dbd43-131">Dans la page **Maintenance de l'entité** , cliquez sur **Enregistrer l'entité**.</span><span class="sxs-lookup"><span data-stu-id="dbd43-131">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="to-display-the-time-portion-of-a-datetime-value"></a><span data-ttu-id="dbd43-132">Pour afficher la partie heure d'une valeur datetime</span><span class="sxs-lookup"><span data-stu-id="dbd43-132">To display the time portion of a datetime value</span></span>  
 <span data-ttu-id="dbd43-133">Pour que l'interface utilisateur affiche la partie heure d'une valeur datetime, vous devez sélectionner un masque de saisie approprié pour l'attribut.</span><span class="sxs-lookup"><span data-stu-id="dbd43-133">To have the user interface display the time portion of a datetime value, you must select an appropriate input mask for the attribute.</span></span> <span data-ttu-id="dbd43-134">Aucun des masques intégrés des attributs Datetime ne le permet, mais vous avez la possibilité d'ajouter un nouveau masque grâce auquel vous pourrez afficher l'heure.</span><span class="sxs-lookup"><span data-stu-id="dbd43-134">None of the built-in masks for Datetime attributes do this, but you can add a new mask that will allow you to display time.</span></span> <span data-ttu-id="dbd43-135">Pour ce faire, ajoutez une ligne dans la table mdm.tblList de la base de données MDS, dans laquelle sont stockés les masques intégrés.</span><span class="sxs-lookup"><span data-stu-id="dbd43-135">To do so, add a row in the mdm.tblList table of the MDS database, where the built-in masks are stored.</span></span> <span data-ttu-id="dbd43-136">La ligne doit contenir les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="dbd43-136">The row should have the following values:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dbd43-137">ListCode</span><span class="sxs-lookup"><span data-stu-id="dbd43-137">ListCode</span></span>|<span data-ttu-id="dbd43-138">lstInputMask</span><span class="sxs-lookup"><span data-stu-id="dbd43-138">lstInputMask</span></span>|  
|<span data-ttu-id="dbd43-139">ListName</span><span class="sxs-lookup"><span data-stu-id="dbd43-139">ListName</span></span>|<span data-ttu-id="dbd43-140">Masque d’entrée</span><span class="sxs-lookup"><span data-stu-id="dbd43-140">Input Mask</span></span>|  
|<span data-ttu-id="dbd43-141">Seq</span><span class="sxs-lookup"><span data-stu-id="dbd43-141">Seq</span></span>|<span data-ttu-id="dbd43-142">19</span><span class="sxs-lookup"><span data-stu-id="dbd43-142">19</span></span>|  
|<span data-ttu-id="dbd43-143">Option de liste</span><span class="sxs-lookup"><span data-stu-id="dbd43-143">List Option</span></span>|<span data-ttu-id="dbd43-144">jj/MM/aaaa hh:mm:ss tt</span><span class="sxs-lookup"><span data-stu-id="dbd43-144">dd/MM/yyyy hh:mm:ss tt</span></span>|  
|<span data-ttu-id="dbd43-145">ID d'option</span><span class="sxs-lookup"><span data-stu-id="dbd43-145">Option ID</span></span>|<span data-ttu-id="dbd43-146">19</span><span class="sxs-lookup"><span data-stu-id="dbd43-146">19</span></span>|  
|<span data-ttu-id="dbd43-147">EstVisible</span><span class="sxs-lookup"><span data-stu-id="dbd43-147">IsVisible</span></span>|<span data-ttu-id="dbd43-148">1</span><span class="sxs-lookup"><span data-stu-id="dbd43-148">1</span></span>|  
|<span data-ttu-id="dbd43-149">Group_ID</span><span class="sxs-lookup"><span data-stu-id="dbd43-149">Group_ID</span></span>|<span data-ttu-id="dbd43-150">3</span><span class="sxs-lookup"><span data-stu-id="dbd43-150">3</span></span>|  
  
 <span data-ttu-id="dbd43-151">Une fois que vous avez entré une ligne comportant les valeurs ci-dessus dans la table mdm.tblList, le masque « jj/MMM/aaaa hh:mm:ss tt » devient disponible dans la zone de liste de masque de saisie.</span><span class="sxs-lookup"><span data-stu-id="dbd43-151">After you enter a row with the above values in the mdm.tblList table, the "dd/MM/yyyy hh:mm:ss tt" mask will be available in the Input mask list box.</span></span> <span data-ttu-id="dbd43-152">Vous pouvez alors sélectionner ce masque afin d'afficher la date et l'heure dans la colonne d'attribut datetime d'une entité dans l'Explorateur MDS.</span><span class="sxs-lookup"><span data-stu-id="dbd43-152">You can then select that mask to display the date and time in a datetime attribute column of an entity in the MDS Explorer.</span></span>  
  
 <span data-ttu-id="dbd43-153">Le masque de saisie est une chaîne au format DateTime .NET personnalisée.</span><span class="sxs-lookup"><span data-stu-id="dbd43-153">The Input Mask is a custom .NET DateTime format string.</span></span> <span data-ttu-id="dbd43-154">Pour plus d’informations, consultez [Chaînes de format de date et d’heure personnalisées](https://msdn.microsoft.com/library/8kb3ddd4\(v=vs.110\).aspx).</span><span class="sxs-lookup"><span data-stu-id="dbd43-154">For more information, see [Custom Date and Time Format Strings](https://msdn.microsoft.com/library/8kb3ddd4\(v=vs.110\).aspx)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbd43-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dbd43-155">See Also</span></span>  
 <span data-ttu-id="dbd43-156">[Attributs &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="dbd43-156">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="dbd43-157">[Modifier le nom d’un attribut &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="dbd43-157">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 <span data-ttu-id="dbd43-158">[Créer un attribut basé sur un domaine &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="dbd43-158">[Create a Domain-Based Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="dbd43-159">Créer un attribut de fichier &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dbd43-159">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)  
  
  
