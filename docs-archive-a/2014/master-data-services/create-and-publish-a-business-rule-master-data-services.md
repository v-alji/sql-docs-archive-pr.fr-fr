---
title: Créer et publier une règle d’entreprise (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], creating
- creating business rules [Master Data Services]
ms.assetid: 6961d636-4d69-468e-81f7-8d0be6a4a039
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4dfca5613a1f328e02b3fd2c7337885a23889207
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612995"
---
# <a name="create-and-publish-a-business-rule-master-data-services"></a><span data-ttu-id="a5833-102">Créer et publier une règle d'entreprise (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="a5833-102">Create and Publish a Business Rule (Master Data Services)</span></span>
  <span data-ttu-id="a5833-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], créez une règle d'entreprise pour garantir l'exactitude de vos données de référence.</span><span class="sxs-lookup"><span data-stu-id="a5833-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a business rule to ensure the accuracy of your master data.</span></span> <span data-ttu-id="a5833-104">Après avoir créé une règle, vous devez la publier avant de pouvoir l'appliquer aux données.</span><span class="sxs-lookup"><span data-stu-id="a5833-104">After you create a rule, you must publish it before you can apply it to data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a5833-105">Prérequis</span><span class="sxs-lookup"><span data-stu-id="a5833-105">Prerequisites</span></span>  
 <span data-ttu-id="a5833-106">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="a5833-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="a5833-107">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .</span><span class="sxs-lookup"><span data-stu-id="a5833-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="a5833-108">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="a5833-108">You must be a model administrator.</span></span> <span data-ttu-id="a5833-109">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a5833-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-and-publish-a-business-rule"></a><span data-ttu-id="a5833-110">Pour créer et publier une règle d'entreprise</span><span class="sxs-lookup"><span data-stu-id="a5833-110">To create and publish a business rule</span></span>  
  
1.  <span data-ttu-id="a5833-111">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="a5833-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="a5833-112">Dans la barre de menus, pointez sur **Gérer** et cliquez sur **Règles d'entreprise**.</span><span class="sxs-lookup"><span data-stu-id="a5833-112">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="a5833-113">Dans la page **Maintenance des règles d’entreprise** , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="a5833-113">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="a5833-114">Dans la liste **Entité** , sélectionnez une entité.</span><span class="sxs-lookup"><span data-stu-id="a5833-114">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="a5833-115">Dans la liste **Type de membre** , sélectionnez un type de membre auquel appliquer la règle d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="a5833-115">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="a5833-116">Dans la liste **Attribut** , sélectionnez un attribut ou conservez l’option par défaut **Tout**.</span><span class="sxs-lookup"><span data-stu-id="a5833-116">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="a5833-117">Cliquez sur **Ajouter une règle d’entreprise**.</span><span class="sxs-lookup"><span data-stu-id="a5833-117">Click **Add business rule**.</span></span>  
  
8.  <span data-ttu-id="a5833-118">Cliquez sur **Modifier la règle d’entreprise sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="a5833-118">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="a5833-119">Dans le volet **Composants** , développez le nœud **Conditions** .</span><span class="sxs-lookup"><span data-stu-id="a5833-119">In the **Components** pane, expand the **Conditions** node.</span></span>  
  
10. <span data-ttu-id="a5833-120">Cliquez sur une condition et faites-la glisser vers l’étiquette **conditions** du volet **If** .</span><span class="sxs-lookup"><span data-stu-id="a5833-120">Click a condition and drag it to the **IF** pane's **Conditions** label.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="a5833-121">Vous pouvez supprimer des éléments de votre règle d’entreprise en cliquant avec le bouton droit et en choisissant **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="a5833-121">You can delete items from your business rule by right-clicking and choosing **Delete**.</span></span>  
  
11. <span data-ttu-id="a5833-122">Dans le volet **attributs** , cliquez sur un attribut et faites-le glisser vers l’étiquette **Sélectionner un attribut** du volet **modifier la condition** .</span><span class="sxs-lookup"><span data-stu-id="a5833-122">In the **Attributes** pane, click an attribute and drag it to the **Edit Condition** pane's **Select attribute** label.</span></span>  
  
12. <span data-ttu-id="a5833-123">Dans le volet **modifier la condition** , complétez tous les champs obligatoires.</span><span class="sxs-lookup"><span data-stu-id="a5833-123">In the **Edit Condition** pane, complete any required fields.</span></span>  
  
13. <span data-ttu-id="a5833-124">Dans le volet **Modifier la condition** , cliquez sur **Enregistrer l’élément**.</span><span class="sxs-lookup"><span data-stu-id="a5833-124">In the **Edit Condition** pane, click **Save item**.</span></span>  
  
14. <span data-ttu-id="a5833-125">Dans le volet **Composants** , développez le nœud **Actions** .</span><span class="sxs-lookup"><span data-stu-id="a5833-125">In the **Components** pane, expand the **Actions** node.</span></span>  
  
15. <span data-ttu-id="a5833-126">Cliquez sur une action et faites-la glisser vers l’étiquette **Action** du volet **THEN** .</span><span class="sxs-lookup"><span data-stu-id="a5833-126">Click an action and drag it to the **THEN** pane's **Action** label.</span></span>  
  
16. <span data-ttu-id="a5833-127">Dans le volet **Attributs** , cliquez sur un attribut et faites-le glisser vers l’étiquette **Sélectionner un attribut** du volet **Modifier l’action** .</span><span class="sxs-lookup"><span data-stu-id="a5833-127">In the **Attributes** pane, click an attribute and drag it to the **Edit Action** pane's **Select attribute** label.</span></span>  
  
17. <span data-ttu-id="a5833-128">Dans le volet **Modifier l’action** , remplissez tous les champs obligatoires.</span><span class="sxs-lookup"><span data-stu-id="a5833-128">In the **Edit Action** pane, complete any required fields.</span></span>  
  
18. <span data-ttu-id="a5833-129">Dans le volet **Modifier l’action** , cliquez sur **Enregistrer l’élément**.</span><span class="sxs-lookup"><span data-stu-id="a5833-129">In the **Edit Action** pane, click **Save item**.</span></span>  
  
19. <span data-ttu-id="a5833-130">Éventuellement, ajoutez plusieurs conditions à la règle.</span><span class="sxs-lookup"><span data-stu-id="a5833-130">Optionally, add multiple conditions to the rule.</span></span> <span data-ttu-id="a5833-131">Pour plus d’informations, consultez [Ajouter plusieurs conditions à une règle d’entreprise &#40;Master Data Services&#41;](../../2014/master-data-services/add-multiple-conditions-to-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a5833-131">For more information, see [Add Multiple Conditions to a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/add-multiple-conditions-to-a-business-rule-master-data-services.md).</span></span>  
  
20. <span data-ttu-id="a5833-132">Cliquez sur **Précédent**.</span><span class="sxs-lookup"><span data-stu-id="a5833-132">Click **Back**.</span></span>  
  
21. <span data-ttu-id="a5833-133">(Facultatif) Dans la page **Maintenance des règles d’entreprise** , sur la ligne qui contient votre règle d’entreprise, double-cliquez sur une cellule dans la colonne **Nom**, **Description**ou **Notification** pour mettre à jour la valeur.</span><span class="sxs-lookup"><span data-stu-id="a5833-133">Optionally, on the **Business Rules Maintenance** page, for the row that contains your business rule, double-click a cell in the **Name**, **Description**, or **Notification** column to update the value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a5833-134">Des notifications sont envoyées uniquement pour les règles qui incluent une action de validation.</span><span class="sxs-lookup"><span data-stu-id="a5833-134">Notifications are sent only for rules that include a validation action.</span></span>  
  
22. <span data-ttu-id="a5833-135">Cliquez sur **Publier les règles d’entreprise**.</span><span class="sxs-lookup"><span data-stu-id="a5833-135">Click **Publish business rules**.</span></span>  
  
23. <span data-ttu-id="a5833-136">Dans la boîte de dialogue de confirmation, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5833-136">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="a5833-137">L’état de la règle devient **Actif**.</span><span class="sxs-lookup"><span data-stu-id="a5833-137">The rule's status changes to **Active**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a5833-138">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="a5833-138">Next Steps</span></span>  
  
-   <span data-ttu-id="a5833-139">Appliquez des règles d'entreprise aux données en suivant l'une de ces procédures :</span><span class="sxs-lookup"><span data-stu-id="a5833-139">Apply business rules to data by following one of these procedures:</span></span>  
  
    -   [<span data-ttu-id="a5833-140">Valider des membres spécifiques par rapport aux règles d’entreprise &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a5833-140">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
    -   [<span data-ttu-id="a5833-141">Valider une version par rapport aux règles d’entreprise &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a5833-141">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="a5833-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a5833-142">See Also</span></span>  
 <span data-ttu-id="a5833-143">[Configurez des règles d’entreprise pour envoyer des notifications &#40;Master Data Services&#41;](../../2014/master-data-services/configure-business-rules-to-send-notifications-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a5833-143">[Configure Business Rules to Send Notifications &#40;Master Data Services&#41;](../../2014/master-data-services/configure-business-rules-to-send-notifications-master-data-services.md) </span></span>  
 <span data-ttu-id="a5833-144">[Modifier le nom d’une règle d’entreprise &#40;Master Data Services&#41;](../../2014/master-data-services/change-a-business-rule-name-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a5833-144">[Change a Business Rule Name &#40;Master Data Services&#41;](../../2014/master-data-services/change-a-business-rule-name-master-data-services.md) </span></span>  
 [<span data-ttu-id="a5833-145">Ajouter plusieurs conditions à une règle d’entreprise &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a5833-145">Add Multiple Conditions to a Business Rule &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-multiple-conditions-to-a-business-rule-master-data-services.md)  
  
  
