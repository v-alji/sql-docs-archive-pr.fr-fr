---
title: Créer et gérer des perspectives (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.perspectivedb.f1
ms.assetid: 2a411c2b-2820-4086-ad7f-ce6a941fefc7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6d0029ff61aa05e2e83f34833c3d0af17ddb3beb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601747"
---
# <a name="create-and-manage-perspectives-ssas-tabular"></a><span data-ttu-id="50cf4-102">Créer et gérer des perspectives (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="50cf4-102">Create and Manage Perspectives (SSAS Tabular)</span></span>
  <span data-ttu-id="50cf4-103">Les perspectives définissent des sous-ensembles visualisables d'un modèle et des points de vue du modèle focalisés sur un domaine d'activité ou sur une application.</span><span class="sxs-lookup"><span data-stu-id="50cf4-103">Perspectives define viewable subsets of a model that provide focused, business-specific, or application-specific viewpoints of the model.</span></span> <span data-ttu-id="50cf4-104">Les tâches de cette rubrique décrivent comment créer et gérer des perspectives à l'aide de la boîte de dialogue **Perspectives** dans le générateur de modèles.</span><span class="sxs-lookup"><span data-stu-id="50cf4-104">The tasks in this topic describe how to create and manage perspectives by using the **Perspectives** dialog box in the model designer.</span></span>  
  
 <span data-ttu-id="50cf4-105">Cette rubrique inclut les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="50cf4-105">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="50cf4-106">Pour ajouter une perspective</span><span class="sxs-lookup"><span data-stu-id="50cf4-106">To add a perspective</span></span>](#bkmk_add)  
  
-   [<span data-ttu-id="50cf4-107">Pour modifier une perspective</span><span class="sxs-lookup"><span data-stu-id="50cf4-107">To edit a perspective</span></span>](#bkmk_edit)  
  
-   [<span data-ttu-id="50cf4-108">Pour renommer une perspective</span><span class="sxs-lookup"><span data-stu-id="50cf4-108">To rename a perspective</span></span>](#bkmk_rename)  
  
-   [<span data-ttu-id="50cf4-109">Pour supprimer une perspective</span><span class="sxs-lookup"><span data-stu-id="50cf4-109">To delete a perspective</span></span>](#bkmk_delete)  
  
-   [<span data-ttu-id="50cf4-110">Pour copier une perspective</span><span class="sxs-lookup"><span data-stu-id="50cf4-110">To copy a perspective</span></span>](#bkmk_copy)  
  
## <a name="tasks"></a><span data-ttu-id="50cf4-111">Tâches</span><span class="sxs-lookup"><span data-stu-id="50cf4-111">Tasks</span></span>  
 <span data-ttu-id="50cf4-112">Pour créer des perspectives, vous allez utiliser la boîte de dialogue **Perspectives** , dans laquelle vous pouvez ajouter, modifier, supprimer, copier et afficher des perspectives.</span><span class="sxs-lookup"><span data-stu-id="50cf4-112">To create perspectives, you will use the **Perspectives** dialog box, where you can add, edit, delete, copy, and view perspectives.</span></span> <span data-ttu-id="50cf4-113">Pour consulter la boîte de dialogue **Perspectives** , dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], cliquez sur le menu **Modèle** , puis sur **Perspectives**.</span><span class="sxs-lookup"><span data-stu-id="50cf4-113">To view the **Perspectives** dialog box, in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click on the **Model** menu, and then click **Perspectives**.</span></span>  
  
###  <a name="to-add-a-perspective"></a><a name="bkmk_add"></a> <span data-ttu-id="50cf4-114">Pour ajouter une perspective</span><span class="sxs-lookup"><span data-stu-id="50cf4-114">To add a perspective</span></span>  
  
-   <span data-ttu-id="50cf4-115">Pour ajouter une nouvelle perspective, cliquez sur **Nouvelle perspective**.</span><span class="sxs-lookup"><span data-stu-id="50cf4-115">To add a new perspective, click **New Perspective**.</span></span> <span data-ttu-id="50cf4-116">Vous pouvez ensuite activer et désactiver les objets de champ de votre choix pour les inclure ou les exclure et ensuite donner un nom à la nouvelle perspective.</span><span class="sxs-lookup"><span data-stu-id="50cf4-116">You can then check and uncheck field objects to be included and provide a name for the new perspective.</span></span>  
  
     <span data-ttu-id="50cf4-117">Si vous créez une perspective vide avec tous les champs d'objet, un utilisateur utilisant cette perspective verra une liste de champs vide.</span><span class="sxs-lookup"><span data-stu-id="50cf4-117">If you create an empty perspective with all of the field object fields, then a user using this perspective will see an empty Field List.</span></span> <span data-ttu-id="50cf4-118">Les perspectives doivent contenir au moins une table et une colonne.</span><span class="sxs-lookup"><span data-stu-id="50cf4-118">Perspectives should contain at least one table and column.</span></span>  
  
###  <a name="to-edit-a-perspective"></a><a name="bkmk_edit"></a><span data-ttu-id="50cf4-119">Pour modifier une perspective</span><span class="sxs-lookup"><span data-stu-id="50cf4-119">To edit a perspective</span></span>  
  
-   <span data-ttu-id="50cf4-120">Pour modifier une perspective, activez et désactivez les champs de la colonne perspective, qui ajoute et supprime les objets champ de la perspective.</span><span class="sxs-lookup"><span data-stu-id="50cf4-120">To modify a perspective, check and uncheck fields in the perspective's column, which adds and removes field objects from the perspective.</span></span>  
  
###  <a name="to-rename-a-perspective"></a><a name="bkmk_rename"></a><span data-ttu-id="50cf4-121">Pour renommer une perspective</span><span class="sxs-lookup"><span data-stu-id="50cf4-121">To rename a perspective</span></span>  
  
-   <span data-ttu-id="50cf4-122">Lorsque vous placez le pointeur de la souris sur l’en-tête de colonne d’une perspective (le nom de la perspective), le bouton **Renommer** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="50cf4-122">When you hover over a perspective's column header (the name of the perspective), the **Rename** button appears.</span></span> <span data-ttu-id="50cf4-123">Pour renommer la perspective, cliquez sur **Renommer**, puis entrez un nouveau nom ou modifiez le nom existant.</span><span class="sxs-lookup"><span data-stu-id="50cf4-123">To rename the perspective, click **Rename**, and then enter a new name or edit the existing name.</span></span>  
  
###  <a name="to-delete-a-perspective"></a><a name="bkmk_delete"></a><span data-ttu-id="50cf4-124">Pour supprimer une perspective</span><span class="sxs-lookup"><span data-stu-id="50cf4-124">To delete a perspective</span></span>  
  
-   <span data-ttu-id="50cf4-125">Lorsque vous placez le pointeur de la souris sur l’en-tête de colonne d’une perspective (le nom de la perspective), le bouton **supprimer** apparaît.</span><span class="sxs-lookup"><span data-stu-id="50cf4-125">When you hover over a perspective's column header (the name of the perspective), the **Delete** button appears.</span></span> <span data-ttu-id="50cf4-126">Pour supprimer la perspective, cliquez sur le bouton **Supprimer** , puis cliquez sur **Oui** dans la fenêtre de confirmation.</span><span class="sxs-lookup"><span data-stu-id="50cf4-126">To delete the perspective, click the **Delete** button, and then click **Yes** in the confirmation window.</span></span>  
  
###  <a name="to-copy-a-perspective"></a><a name="bkmk_copy"></a><span data-ttu-id="50cf4-127">Pour copier une perspective</span><span class="sxs-lookup"><span data-stu-id="50cf4-127">To copy a perspective</span></span>  
  
-   <span data-ttu-id="50cf4-128">Lorsque vous placez le pointeur de la souris sur l’en-tête de colonne d’une perspective, le bouton **copier** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="50cf4-128">When you hover over a perspective's column header, the **Copy** button appears.</span></span> <span data-ttu-id="50cf4-129">Pour créer une copie de cette perspective, cliquez sur le bouton **Copier** .</span><span class="sxs-lookup"><span data-stu-id="50cf4-129">To create a copy of that perspective, click the **Copy** button.</span></span> <span data-ttu-id="50cf4-130">Une copie de la perspective sélectionnée est ajoutée en tant que nouvelle perspective à droite des perspectives existantes.</span><span class="sxs-lookup"><span data-stu-id="50cf4-130">A copy of the selected perspective is added as a new perspective to the right of existing perspectives.</span></span> <span data-ttu-id="50cf4-131">La nouvelle perspective hérite du nom de la perspective copiée et une annotation *- Copier* est ajoutée à la fin du nom.</span><span class="sxs-lookup"><span data-stu-id="50cf4-131">The new perspective inherits the name of the copied perspective and a *- Copy* annotation is appended to the end of the name.</span></span> <span data-ttu-id="50cf4-132">Par exemple, si une copie de la perspective *ventes* est créée, la nouvelle perspective est appelée *ventes-copie*.</span><span class="sxs-lookup"><span data-stu-id="50cf4-132">For example, if a copy of the *Sales* perspective is created, the new perspective is called *Sales - Copy*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50cf4-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="50cf4-133">See Also</span></span>  
 <span data-ttu-id="50cf4-134">[Perspectives &#40;&#41;tabulaire SSAS](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="50cf4-134">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="50cf4-135">Hiérarchies &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="50cf4-135">Hierarchies &#40;SSAS Tabular&#41;</span></span>](hierarchies-ssas-tabular.md)  
  
  
