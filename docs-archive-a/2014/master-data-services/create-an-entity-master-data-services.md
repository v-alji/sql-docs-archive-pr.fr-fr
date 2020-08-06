---
title: Créer une entité (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- entities [Master Data Services], creating
- creating entities [Master Data Services]
ms.assetid: d9a6a51e-7b53-4785-a118-3baeb7ca2d48
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 7cefdedd07ee248f12b3b17337878934a2b1aa84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614143"
---
# <a name="create-an-entity-master-data-services"></a><span data-ttu-id="4cefd-102">Créer une entité (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="4cefd-102">Create an Entity (Master Data Services)</span></span>
  <span data-ttu-id="4cefd-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], créez une entité destinée à contenir des membres et leurs attributs.</span><span class="sxs-lookup"><span data-stu-id="4cefd-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create an entity to contain members and their attributes.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4cefd-104">Prérequis</span><span class="sxs-lookup"><span data-stu-id="4cefd-104">Prerequisites</span></span>  
 <span data-ttu-id="4cefd-105">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="4cefd-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="4cefd-106">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .</span><span class="sxs-lookup"><span data-stu-id="4cefd-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="4cefd-107">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="4cefd-107">You must be a model administrator.</span></span> <span data-ttu-id="4cefd-108">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4cefd-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="4cefd-109">Un modèle doit exister.</span><span class="sxs-lookup"><span data-stu-id="4cefd-109">A model must exist.</span></span> <span data-ttu-id="4cefd-110">Pour plus d’informations, consultez [Créer un modèle &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-model-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4cefd-110">For more information, see [Create a Model &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-model-master-data-services.md).</span></span>  
  
### <a name="to-create-an-entity"></a><span data-ttu-id="4cefd-111">Pour créer une entité</span><span class="sxs-lookup"><span data-stu-id="4cefd-111">To create an entity</span></span>  
  
1.  <span data-ttu-id="4cefd-112">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="4cefd-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="4cefd-113">Dans la page **Vue du modèle** , dans la barre de menus, pointez sur **Gérer** , puis cliquez sur **Entités**.</span><span class="sxs-lookup"><span data-stu-id="4cefd-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="4cefd-114">Dans la page **Maintenance de l'entité** , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="4cefd-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="4cefd-115">Cliquez sur **Ajouter une entité**.</span><span class="sxs-lookup"><span data-stu-id="4cefd-115">Click **Add entity**.</span></span>  
  
5.  <span data-ttu-id="4cefd-116">Dans la zone nom de l' **entité** , tapez le nom de l’entité.</span><span class="sxs-lookup"><span data-stu-id="4cefd-116">In the **Entity name** box, type the name of the entity.</span></span>  
  
6.  <span data-ttu-id="4cefd-117">Dans la zone **nom des tables de mise en lots** , tapez un nom pour la table de mise en lots.</span><span class="sxs-lookup"><span data-stu-id="4cefd-117">In the **Name for staging tables** box, type a name for the staging table.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="4cefd-118">Utilisez le nom du modèle dans le nom de la table de mise en lots, par exemple *NomModèle_NomEntité*.</span><span class="sxs-lookup"><span data-stu-id="4cefd-118">Use the model name as part of the staging table name, for example *Modelname_Entityname*.</span></span> <span data-ttu-id="4cefd-119">Cela facilite la recherche de tables dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="4cefd-119">This makes the tables easier to find in the database.</span></span> <span data-ttu-id="4cefd-120">Pour plus d’informations sur les tables de mise en lots, consultez [&#40;d’importation de données Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4cefd-120">For more information about the staging tables, see [Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md).</span></span>  
  
7.  <span data-ttu-id="4cefd-121">facultatif.</span><span class="sxs-lookup"><span data-stu-id="4cefd-121">Optional.</span></span> <span data-ttu-id="4cefd-122">Activez la case à cocher **Créer automatiquement les valeurs de code** .</span><span class="sxs-lookup"><span data-stu-id="4cefd-122">Select the **Create Code values automatically** check box.</span></span> <span data-ttu-id="4cefd-123">Pour plus d’informations, consultez [création automatique de Code &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4cefd-123">For more information, see [Automatic Code Creation &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md).</span></span>  
  
8.  <span data-ttu-id="4cefd-124">Dans la liste **activer les hiérarchies explicites et les regroupements** , sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="4cefd-124">From the **Enable explicit hierarchies and collections** list, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="4cefd-125">**Non**.</span><span class="sxs-lookup"><span data-stu-id="4cefd-125">**No**.</span></span> <span data-ttu-id="4cefd-126">Sélectionnez cette option si vous n'avez pas besoin d'activer l'entité pour les hiérarchies et les collections explicites.</span><span class="sxs-lookup"><span data-stu-id="4cefd-126">Select this option if you do not need to enable the entity for explicit hierarchies and collections.</span></span> <span data-ttu-id="4cefd-127">Vous pouvez changer ce paramètre ultérieurement si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="4cefd-127">You can change this later if needed.</span></span>  
  
    -   <span data-ttu-id="4cefd-128">**Oui**.</span><span class="sxs-lookup"><span data-stu-id="4cefd-128">**Yes**.</span></span> <span data-ttu-id="4cefd-129">Sélectionnez cette option lorsque vous souhaitez activer l'entité pour les hiérarchies et collections explicites.</span><span class="sxs-lookup"><span data-stu-id="4cefd-129">Select this option when you want to enable the entity for explicit hierarchies and collections.</span></span> <span data-ttu-id="4cefd-130">Dans la zone nom de la **hiérarchie explicite** , tapez un nom.</span><span class="sxs-lookup"><span data-stu-id="4cefd-130">In the **Explicit hierarchy name** box, type a name.</span></span> <span data-ttu-id="4cefd-131">Si vous le souhaitez, sélectionnez **hiérarchie obligatoire (tous les membres feuille sont inclus** pour transformer la hiérarchie explicite en hiérarchie obligatoire.</span><span class="sxs-lookup"><span data-stu-id="4cefd-131">Optionally, select **Mandatory hierarchy (all leaf members are included** to make the explicit hierarchy a mandatory hierarchy.</span></span>  
  
9. <span data-ttu-id="4cefd-132">Cliquez sur **enregistrer l’entité**.</span><span class="sxs-lookup"><span data-stu-id="4cefd-132">Click **Save entity**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4cefd-133">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="4cefd-133">Next Steps</span></span>  
  
-   [<span data-ttu-id="4cefd-134">Créer un attribut de texte &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="4cefd-134">Create a Text Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-text-attribute-master-data-services.md)  
  
-   [<span data-ttu-id="4cefd-135">Créer un attribut basé sur un domaine &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="4cefd-135">Create a Domain-Based Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md)  
  
-   [<span data-ttu-id="4cefd-136">Créer un attribut de fichier &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="4cefd-136">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="4cefd-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4cefd-137">See Also</span></span>  
 <span data-ttu-id="4cefd-138">[Entités &#40;Master Data Services&#41;](../../2014/master-data-services/entities-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="4cefd-138">[Entities &#40;Master Data Services&#41;](../../2014/master-data-services/entities-master-data-services.md) </span></span>  
 <span data-ttu-id="4cefd-139">[Hiérarchies explicites &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="4cefd-139">[Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span></span>  
 <span data-ttu-id="4cefd-140">[Modifier le nom d’une entité &#40;Master Data Services&#41;](edit-an-entity-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="4cefd-140">[Change an Entity Name &#40;Master Data Services&#41;](edit-an-entity-master-data-services.md) </span></span>  
 [<span data-ttu-id="4cefd-141">Supprimer une entité &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="4cefd-141">Delete an Entity &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-an-entity-master-data-services.md)  
  
  
