---
title: Démarrer des actions en fonction de modifications de valeurs d’attribut (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], tracking attribute changes
- change tracking groups [Master Data Services], initiating actions
ms.assetid: 5e4402ce-31db-4774-a2a1-552335f87693
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 50931b9f9c4bd5d08596d485ba695143b9c6594e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696912"
---
# <a name="initiate-actions-based-on-attribute-value-changes-master-data-services"></a><span data-ttu-id="d6105-102">Initier des actions en fonction de modifications de valeurs d'attribut (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d6105-102">Initiate Actions Based on Attribute Value Changes (Master Data Services)</span></span>
  <span data-ttu-id="d6105-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], créez une règle d’entreprise pour initier des actions en fonction des modifications apportées aux valeurs d’attribut.</span><span class="sxs-lookup"><span data-stu-id="d6105-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a business rule to initiate actions based on changes to attribute values.</span></span> <span data-ttu-id="d6105-104">Par exemple, lorsqu'une valeur d'attribut spécifique change, vous pouvez modifier une valeur, envoyer une notification, ou démarrer un flux de travail externe.</span><span class="sxs-lookup"><span data-stu-id="d6105-104">For example, when a specific attribute value changes, you may want to change a value, send a notification, or start an external workflow.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d6105-105">Prérequis</span><span class="sxs-lookup"><span data-stu-id="d6105-105">Prerequisites</span></span>  
 <span data-ttu-id="d6105-106">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="d6105-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="d6105-107">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .</span><span class="sxs-lookup"><span data-stu-id="d6105-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="d6105-108">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="d6105-108">You must be a model administrator.</span></span> <span data-ttu-id="d6105-109">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d6105-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="d6105-110">Vos attributs doivent se trouver dans un groupe de suivi des modifications.</span><span class="sxs-lookup"><span data-stu-id="d6105-110">Your attributes must be in a change tracking group.</span></span> <span data-ttu-id="d6105-111">Pour plus d’informations, consultez [Ajouter des attributs à un groupe de suivi des modifications &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) .</span><span class="sxs-lookup"><span data-stu-id="d6105-111">See [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) for more information.</span></span>  
  
### <a name="to-create-a-business-rule-to-initiate-actions-based-on-attribute-value-changes"></a><span data-ttu-id="d6105-112">Pour créer une règle d'entreprise afin d'initier des actions en fonction des modifications apportées aux valeurs d'attribut.</span><span class="sxs-lookup"><span data-stu-id="d6105-112">To create a business rule to initiate actions based on attribute value changes</span></span>  
  
1.  <span data-ttu-id="d6105-113">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="d6105-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="d6105-114">Dans la barre de menus, pointez sur **Gérer** et cliquez sur **Règles d'entreprise**.</span><span class="sxs-lookup"><span data-stu-id="d6105-114">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="d6105-115">Dans la page **Maintenance des règles d’entreprise** , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="d6105-115">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="d6105-116">Dans la liste **Entité** , sélectionnez une entité.</span><span class="sxs-lookup"><span data-stu-id="d6105-116">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="d6105-117">Dans la liste **Type de membre** , sélectionnez un type de membre auquel appliquer la règle d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="d6105-117">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="d6105-118">Dans la liste **Attribut** , sélectionnez un attribut ou conservez l’option par défaut **Tout**.</span><span class="sxs-lookup"><span data-stu-id="d6105-118">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="d6105-119">Cliquez sur **Ajouter une règle d’entreprise**.</span><span class="sxs-lookup"><span data-stu-id="d6105-119">Click **Add business rule**.</span></span>  
  
8.  <span data-ttu-id="d6105-120">Cliquez sur **Modifier la règle d’entreprise sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="d6105-120">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="d6105-121">Dans le volet **Composants** , développez le nœud **Conditions** .</span><span class="sxs-lookup"><span data-stu-id="d6105-121">In the **Components** pane, expand the **Conditions** node.</span></span>  
  
10. <span data-ttu-id="d6105-122">Sous le nœud **Comparaison de valeur** , faites glisser **a changé** vers l’étiquette **Conditions** du volet **IF** .</span><span class="sxs-lookup"><span data-stu-id="d6105-122">Under the **Value comparison** node, drag **has changed** to the **IF** pane's **Conditions** label.</span></span>  
  
11. <span data-ttu-id="d6105-123">Dans le volet **attributs** , cliquez sur un attribut et faites-le glisser vers l’étiquette **Sélectionner un attribut** du volet **modifier la condition** .</span><span class="sxs-lookup"><span data-stu-id="d6105-123">In the **Attributes** pane, click an attribute and drag it to the **Edit Condition** pane's **Select attribute** label.</span></span> <span data-ttu-id="d6105-124">Cet attribut n'a aucun effet sur la règle, vous pouvez donc sélectionner n'importe quel attribut disponible.</span><span class="sxs-lookup"><span data-stu-id="d6105-124">This attribute has no effect on the rule, so select any available attribute.</span></span>  
  
12. <span data-ttu-id="d6105-125">Dans le volet **Modifier la condition** , dans la zone **Groupe de suivi des modifications** , tapez le numéro du groupe de suivi des modifications que vous avez attribué comme l’un des composants requis.</span><span class="sxs-lookup"><span data-stu-id="d6105-125">In the **Edit Condition** pane, in the **Change tracking group** box, type the number of the change tracking group that you assigned as part of the prerequisites.</span></span>  
  
13. <span data-ttu-id="d6105-126">Dans le volet **Modifier la condition** , cliquez sur **Enregistrer l’élément**.</span><span class="sxs-lookup"><span data-stu-id="d6105-126">In the **Edit Condition** pane, click **Save item**.</span></span>  
  
14. <span data-ttu-id="d6105-127">Dans le volet **Composants** , développez le nœud **Actions** .</span><span class="sxs-lookup"><span data-stu-id="d6105-127">In the **Components** pane, expand the **Actions** node.</span></span>  
  
15. <span data-ttu-id="d6105-128">Cliquez sur une action et faites-la glisser vers l’étiquette **Action** du volet **THEN** .</span><span class="sxs-lookup"><span data-stu-id="d6105-128">Click an action and drag it to the **THEN** pane's **Action** label.</span></span>  
  
16. <span data-ttu-id="d6105-129">Dans le volet **Attributs** , cliquez sur un attribut et faites-le glisser vers l’étiquette **Sélectionner un attribut** du volet **Modifier l’action** .</span><span class="sxs-lookup"><span data-stu-id="d6105-129">In the **Attributes** pane, click an attribute and drag it to the **Edit Action** pane's **Select attribute** label.</span></span>  
  
17. <span data-ttu-id="d6105-130">Dans le volet **Modifier l’action** , remplissez tous les champs obligatoires.</span><span class="sxs-lookup"><span data-stu-id="d6105-130">In the **Edit Action** pane, complete any required fields.</span></span>  
  
18. <span data-ttu-id="d6105-131">Dans le volet **Modifier l’action** , cliquez sur **Enregistrer l’élément**.</span><span class="sxs-lookup"><span data-stu-id="d6105-131">In the **Edit Action** pane, click **Save item**.</span></span>  
  
19. <span data-ttu-id="d6105-132">Cliquez sur **Précédent**.</span><span class="sxs-lookup"><span data-stu-id="d6105-132">Click **Back**.</span></span>  
  
20. <span data-ttu-id="d6105-133">(Facultatif) Dans la page **Maintenance des règles d’entreprise** , sur la ligne qui contient votre règle d’entreprise, double-cliquez sur une cellule dans la colonne **Nom**, **Description**ou **Notification** pour mettre à jour la valeur.</span><span class="sxs-lookup"><span data-stu-id="d6105-133">Optionally, on the **Business Rules Maintenance** page, for the row that contains your business rule, double-click a cell in the **Name**, **Description**, or **Notification** column to update the value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d6105-134">Des notifications sont envoyées uniquement pour les règles qui incluent une action de validation.</span><span class="sxs-lookup"><span data-stu-id="d6105-134">Notifications are sent only for rules that include a validation action.</span></span>  
  
21. <span data-ttu-id="d6105-135">Cliquez sur **Publier les règles d’entreprise**.</span><span class="sxs-lookup"><span data-stu-id="d6105-135">Click **Publish business rules**.</span></span>  
  
22. <span data-ttu-id="d6105-136">Dans la boîte de dialogue de confirmation, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d6105-136">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="d6105-137">L’état de la règle devient **Actif**.</span><span class="sxs-lookup"><span data-stu-id="d6105-137">The rule's status changes to **Active**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d6105-138">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="d6105-138">Next Steps</span></span>  
  
-   <span data-ttu-id="d6105-139">Appliquez des règles d'entreprise aux données en suivant l'une de ces procédures :</span><span class="sxs-lookup"><span data-stu-id="d6105-139">Apply business rules to data by following one of these procedures:</span></span>  
  
    -   [<span data-ttu-id="d6105-140">Valider des membres spécifiques par rapport aux règles d’entreprise &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d6105-140">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
    -   [<span data-ttu-id="d6105-141">Valider une version par rapport aux règles d’entreprise &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d6105-141">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="d6105-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d6105-142">See Also</span></span>  
 <span data-ttu-id="d6105-143">[Ajouter des attributs à un groupe de Change Tracking &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d6105-143">[Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) </span></span>  
 [<span data-ttu-id="d6105-144">Règles d’entreprise &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d6105-144">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  
