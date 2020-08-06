---
title: Ajouter des attributs à un groupe de suivi des modifications (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- change tracking groups [Master Data Services]
- attributes [Master Data Services], change tracking groups
- change tracking groups [Master Data Services], adding attributes
ms.assetid: e153eb5f-70ca-4c6f-89d8-1f937ed3917d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c8a13dad3ca886668c96c1886f8cd238d9adad9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614151"
---
# <a name="add-attributes-to-a-change-tracking-group-master-data-services"></a><span data-ttu-id="c4718-102">Ajouter des attributs à un groupe de suivi des modifications (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c4718-102">Add Attributes to a Change Tracking Group (Master Data Services)</span></span>
  <span data-ttu-id="c4718-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], ajoutez des attributs à un groupe de suivi des modifications lorsque vous souhaitez effectuer le suivi des modifications apportées aux valeurs d'attribut.</span><span class="sxs-lookup"><span data-stu-id="c4718-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], add attributes to a change tracking group when you want to track changes to the attribute's values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c4718-104">Lorsque qu'un attribut est ajouté à un groupe de suivi des modifications et que ses valeurs changent, l'attribut est alors signalé comme modifié dans la base de données [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c4718-104">After you add an attribute to a change tracking group, when values for the attribute change, the attribute is flagged as changed in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="c4718-105">Créez une règle d'entreprise pour entreprendre une action basée sur la modification.</span><span class="sxs-lookup"><span data-stu-id="c4718-105">Create a business rule to take action based on the change.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c4718-106">Prérequis</span><span class="sxs-lookup"><span data-stu-id="c4718-106">Prerequisites</span></span>  
 <span data-ttu-id="c4718-107">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="c4718-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="c4718-108">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .</span><span class="sxs-lookup"><span data-stu-id="c4718-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="c4718-109">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="c4718-109">You must be a model administrator.</span></span> <span data-ttu-id="c4718-110">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c4718-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="c4718-111">Les attributs doivent exister pour pouvoir être ajoutés au groupe de suivi des modifications.</span><span class="sxs-lookup"><span data-stu-id="c4718-111">Attributes must exist to add to the change tracking group.</span></span> <span data-ttu-id="c4718-112">Pour plus d’informations, consultez [Créer un attribut de texte &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c4718-112">For more information, see [Create a Text Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md).</span></span>  
  
### <a name="to-add-attributes-to-a-change-tracking-group"></a><span data-ttu-id="c4718-113">Pour ajouter des attributs à un groupe de suivi des modifications</span><span class="sxs-lookup"><span data-stu-id="c4718-113">To add attributes to a change tracking group</span></span>  
  
1.  <span data-ttu-id="c4718-114">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="c4718-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="c4718-115">Dans la page **Explorateur de modèles** , dans la barre de menus, pointez sur **gérer** , puis cliquez sur **entités**.</span><span class="sxs-lookup"><span data-stu-id="c4718-115">On the **Model Explorer** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="c4718-116">Dans la page **Maintenance de l'entité** , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="c4718-116">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="c4718-117">Sélectionnez la ligne de l'entité pour laquelle vous souhaitez effectuer le suivi des valeurs d'attribut.</span><span class="sxs-lookup"><span data-stu-id="c4718-117">Select the row for the entity that you want to track attribute values for.</span></span>  
  
5.  <span data-ttu-id="c4718-118">Cliquez sur **Modifier l'entité sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="c4718-118">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="c4718-119">Dans la page **Modifier l'entité** :</span><span class="sxs-lookup"><span data-stu-id="c4718-119">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="c4718-120">Si l’attribut concerne les membres feuille, dans le volet **attributs feuille** , sélectionnez l’attribut et cliquez sur **modifier l’attribut feuille**.</span><span class="sxs-lookup"><span data-stu-id="c4718-120">If the attribute is for leaf members, in the **Leaf attributes** pane, select the attribute and click **Edit leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="c4718-121">Si l’attribut est destiné à des membres consolidés, dans le volet **attributs consolidés** , sélectionnez l’attribut, puis cliquez sur **modifier l’attribut consolidé**.</span><span class="sxs-lookup"><span data-stu-id="c4718-121">If the attribute is for consolidated members, in the **Consolidated attributes** pane, select the attribute and click **Edit consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="c4718-122">Si l’attribut est destiné à des collections, dans le volet **attributs de collection** , sélectionnez l’attribut, puis cliquez sur modifier l' **attribut de collection**.</span><span class="sxs-lookup"><span data-stu-id="c4718-122">If the attribute is for collections, in the **Collection attributes** pane, select the attribute and click **Edit collection attribute**.</span></span>  
  
7.  <span data-ttu-id="c4718-123">Activez la case à cocher **Activer le suivi des modifications** .</span><span class="sxs-lookup"><span data-stu-id="c4718-123">Select the **Enable change tracking** check box.</span></span>  
  
8.  <span data-ttu-id="c4718-124">Dans la zone **Groupe de suivi des modifications** , tapez un numéro pour le groupe.</span><span class="sxs-lookup"><span data-stu-id="c4718-124">In the **Change tracking group** box, type a number for the group.</span></span>  
  
9. <span data-ttu-id="c4718-125">Cliquez sur **Enregistrer l'attribut**.</span><span class="sxs-lookup"><span data-stu-id="c4718-125">Click **Save attribute**.</span></span>  
  
10. <span data-ttu-id="c4718-126">Dans la page **Maintenance de l'entité** , cliquez sur **Enregistrer l'entité**.</span><span class="sxs-lookup"><span data-stu-id="c4718-126">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
11. <span data-ttu-id="c4718-127">Répétez cette procédure pour tous les attributs que vous souhaitez inclure dans le groupe.</span><span class="sxs-lookup"><span data-stu-id="c4718-127">Repeat this procedure for all attributes you want to include in the group.</span></span> <span data-ttu-id="c4718-128">Utilisez le même numéro de groupe de suivi des modifications pour chaque attribut dans le groupe.</span><span class="sxs-lookup"><span data-stu-id="c4718-128">Use the same change tracking group number for each attribute in the group.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c4718-129">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="c4718-129">Next Steps</span></span>  
  
-   [<span data-ttu-id="c4718-130">Initier des actions en fonction de modifications de valeurs d’attribut &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c4718-130">Initiate Actions Based on Attribute Value Changes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/initiate-actions-based-on-attribute-value-changes-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="c4718-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c4718-131">See Also</span></span>  
 <span data-ttu-id="c4718-132">[Créez un attribut de texte &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c4718-132">[Create a Text Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="c4718-133">Créer un attribut basé sur un domaine &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c4718-133">Create a Domain-Based Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md)  
  
  
