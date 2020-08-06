---
title: Ajouter plusieurs conditions à une règle d’entreprise (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], multiple conditions
ms.assetid: 5f0f6958-6cf2-444b-bdcd-05b887637a0b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c62b8dfa4f459958d12bd384b85aa74bef382b21
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611849"
---
# <a name="add-multiple-conditions-to-a-business-rule-master-data-services"></a><span data-ttu-id="0b6dc-102">Ajouter plusieurs conditions à une règle d'entreprise (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0b6dc-102">Add Multiple Conditions to a Business Rule (Master Data Services)</span></span>
  <span data-ttu-id="0b6dc-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], ajoutez plusieurs conditions **AND** ou **OR** à une règle d'entreprise lorsque vous souhaitez une règle plus complexe.</span><span class="sxs-lookup"><span data-stu-id="0b6dc-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], add multiple **AND** or **OR** conditions to a business rule when you want a more complex rule.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0b6dc-104">Si vous créez une règle d'entreprise qui utilise l'opérateur **OR** , créez une règle distincte pour chaque instruction conditionnelle qui peut être évaluée indépendamment.</span><span class="sxs-lookup"><span data-stu-id="0b6dc-104">If you create a business rule that uses the **OR** operator, consider creating a separate rule for each conditional statement that can be evaluated independently.</span></span> <span data-ttu-id="0b6dc-105">Vous pouvez alors exclure des règles si nécessaire, ce qui offre plus de souplesse et facilite la résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="0b6dc-105">You can then exclude rules as needed, providing more flexibility and easier troubleshooting.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0b6dc-106">Prérequis</span><span class="sxs-lookup"><span data-stu-id="0b6dc-106">Prerequisites</span></span>  
 <span data-ttu-id="0b6dc-107">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="0b6dc-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="0b6dc-108">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .</span><span class="sxs-lookup"><span data-stu-id="0b6dc-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="0b6dc-109">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="0b6dc-109">You must be a model administrator.</span></span> <span data-ttu-id="0b6dc-110">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0b6dc-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="0b6dc-111">Une règle d'entreprise doit exister.</span><span class="sxs-lookup"><span data-stu-id="0b6dc-111">A business rule must exist.</span></span> <span data-ttu-id="0b6dc-112">Pour plus d’informations, consultez [Créer et publier une règle d’entreprise &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0b6dc-112">For more information, see [Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span></span>  
  
### <a name="to-add-multiple-conditions-to-a-business-rule"></a><span data-ttu-id="0b6dc-113">Pour ajouter plusieurs conditions à une règle d'entreprise</span><span class="sxs-lookup"><span data-stu-id="0b6dc-113">To add multiple conditions to a business rule</span></span>  
  
1.  <span data-ttu-id="0b6dc-114">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="0b6dc-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="0b6dc-115">Dans la barre de menus, pointez sur **Gérer** et cliquez sur **Règles d'entreprise**.</span><span class="sxs-lookup"><span data-stu-id="0b6dc-115">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="0b6dc-116">Dans la page **Maintenance des règles d’entreprise** , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="0b6dc-116">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="0b6dc-117">Dans la liste **Entité** , sélectionnez une entité.</span><span class="sxs-lookup"><span data-stu-id="0b6dc-117">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="0b6dc-118">Dans la liste **type de membre** , sélectionnez un type de membre.</span><span class="sxs-lookup"><span data-stu-id="0b6dc-118">From the **Member Type** list, select a type of member.</span></span>  
  
6.  <span data-ttu-id="0b6dc-119">Dans la liste **Attribut** , sélectionnez un attribut ou conservez l’option par défaut **Tout**.</span><span class="sxs-lookup"><span data-stu-id="0b6dc-119">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="0b6dc-120">Cliquez sur la ligne de la règle d'entreprise à modifier.</span><span class="sxs-lookup"><span data-stu-id="0b6dc-120">Click the row for the business rule you want to edit.</span></span>  
  
8.  <span data-ttu-id="0b6dc-121">Cliquez sur **Modifier la règle d’entreprise sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="0b6dc-121">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="0b6dc-122">Dans le volet **composants** , développez le nœud **opérateurs logiques** .</span><span class="sxs-lookup"><span data-stu-id="0b6dc-122">In the **Components** pane, expand the **Logical Operators** node.</span></span>  
  
10. <span data-ttu-id="0b6dc-123">Cliquez sur **et** ou **ou** , puis faites-le glisser vers l’étiquette **et** le du volet **If** .</span><span class="sxs-lookup"><span data-stu-id="0b6dc-123">Click **AND** or **OR** and drag it to the **IF** pane's **AND** label.</span></span>  
  
11. <span data-ttu-id="0b6dc-124">Dans le volet **Composants** , développez le nœud **Conditions** .</span><span class="sxs-lookup"><span data-stu-id="0b6dc-124">In the **Components** pane, expand the **Conditions** node.</span></span>  
  
12. <span data-ttu-id="0b6dc-125">Cliquez sur une condition et faites-la glisser vers le volet **If** , vers l’étiquette **et** **ou ou à** partir de l’étape 10.</span><span class="sxs-lookup"><span data-stu-id="0b6dc-125">Click a condition and drag it to **IF** pane, to the **AND** or **OR** label from step 10.</span></span>  
  
13. <span data-ttu-id="0b6dc-126">Dans le volet **attributs** , cliquez sur un attribut et faites-le glisser vers l’étiquette **Sélectionner un attribut** du volet **modifier la condition** .</span><span class="sxs-lookup"><span data-stu-id="0b6dc-126">In the **Attributes** pane, click an attribute and drag it to the **Edit Condition** pane's **Select attribute** label.</span></span>  
  
14. <span data-ttu-id="0b6dc-127">Dans le volet **modifier la condition** , complétez tous les champs obligatoires.</span><span class="sxs-lookup"><span data-stu-id="0b6dc-127">In the **Edit Condition** pane, complete any required fields.</span></span>  
  
15. <span data-ttu-id="0b6dc-128">Dans le volet **Modifier la condition** , cliquez sur **Enregistrer l’élément**.</span><span class="sxs-lookup"><span data-stu-id="0b6dc-128">In the **Edit Condition** pane, click **Save item**.</span></span>  
  
16. <span data-ttu-id="0b6dc-129">Si vous le souhaitez, pour ajouter d’autres conditions, à partir du volet **composants** , faites glisser **and** ou **or** vers Any **et** or **ou** dans le volet **If** .</span><span class="sxs-lookup"><span data-stu-id="0b6dc-129">Optionally, to add more conditions, from the **Components** pane, drag **AND** or **OR** to any **AND** or **OR** in the **IF** pane.</span></span> <span data-ttu-id="0b6dc-130">Suivez ensuite les étapes 13 à 15.</span><span class="sxs-lookup"><span data-stu-id="0b6dc-130">Then follow steps 13-15.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="0b6dc-131">Pour supprimer une condition, cliquez sur le nom de la condition, puis dans le volet **modifier la condition** , cliquez sur **Supprimer l’élément**.</span><span class="sxs-lookup"><span data-stu-id="0b6dc-131">To delete a condition, click the name of the condition and in the **Edit Condition** pane, click **Delete item**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b6dc-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0b6dc-132">See Also</span></span>  
 <span data-ttu-id="0b6dc-133">[&#40;des règles d’entreprise Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="0b6dc-133">[Business Rules &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span></span>  
 <span data-ttu-id="0b6dc-134">[Modifier le nom d’une règle d’entreprise &#40;Master Data Services&#41;](../../2014/master-data-services/change-a-business-rule-name-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="0b6dc-134">[Change a Business Rule Name &#40;Master Data Services&#41;](../../2014/master-data-services/change-a-business-rule-name-master-data-services.md) </span></span>  
 [<span data-ttu-id="0b6dc-135">Configurer des règles d’entreprise pour envoyer des notifications &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0b6dc-135">Configure Business Rules to Send Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-business-rules-to-send-notifications-master-data-services.md)  
  
  
