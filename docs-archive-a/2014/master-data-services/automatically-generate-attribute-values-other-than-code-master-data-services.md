---
title: Générer automatiquement les valeurs des attributs autres que Code (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: b82f6f81-6e9c-4918-9ea9-4ab5f5d11b15
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8db6c89bdce2a11a5a54ed3a763a7bc41bd7f1be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613003"
---
# <a name="automatically-generate-attribute-values-other-than-code-master-data-services"></a><span data-ttu-id="70386-102">Générer automatiquement les valeurs des attributs autres que Code (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="70386-102">Automatically Generate Attribute Values Other Than Code (Master Data Services)</span></span>
  <span data-ttu-id="70386-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], générez automatiquement les valeurs des valeurs d’attribut d’une entité quand vous souhaitez qu’un entier soit attribué automatiquement comme valeur chaque fois que les règles d’entreprise sont appliquées.</span><span class="sxs-lookup"><span data-stu-id="70386-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], automatically generate values for an entity's attribute values when you want an integer to be automatically assigned as the value each time business rules are applied.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="70386-104">Prérequis</span><span class="sxs-lookup"><span data-stu-id="70386-104">Prerequisites</span></span>  
 <span data-ttu-id="70386-105">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="70386-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="70386-106">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .</span><span class="sxs-lookup"><span data-stu-id="70386-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="70386-107">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="70386-107">You must be a model administrator.</span></span> <span data-ttu-id="70386-108">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="70386-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="70386-109">Un attribut numérique doit exister.</span><span class="sxs-lookup"><span data-stu-id="70386-109">A numeric attribute must exist.</span></span> <span data-ttu-id="70386-110">Pour plus d’informations, consultez [Créer un attribut numérique &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-numeric-attribute-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="70386-110">For more information, see [Create a Numeric Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-numeric-attribute-master-data-services.md).</span></span>  
  
### <a name="to-automatically-generate-an-attribute-value"></a><span data-ttu-id="70386-111">Pour générer automatiquement une valeur d'attribut</span><span class="sxs-lookup"><span data-stu-id="70386-111">To automatically generate an attribute value</span></span>  
  
1.  <span data-ttu-id="70386-112">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="70386-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="70386-113">Dans la barre de menus, pointez sur **Gérer** et cliquez sur **Règles d'entreprise**.</span><span class="sxs-lookup"><span data-stu-id="70386-113">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="70386-114">Dans la page **Maintenance des règles d’entreprise** , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="70386-114">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="70386-115">Dans la liste **Entité** , sélectionnez une entité.</span><span class="sxs-lookup"><span data-stu-id="70386-115">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="70386-116">Dans la liste **Type de membre** , sélectionnez un type de membre auquel appliquer la règle d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="70386-116">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="70386-117">Dans la liste **Attribut** , conservez l’option par défaut **Tout**.</span><span class="sxs-lookup"><span data-stu-id="70386-117">From the **Attribute** list, leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="70386-118">Cliquez sur **Ajouter une règle d’entreprise**.</span><span class="sxs-lookup"><span data-stu-id="70386-118">Click **Add business rule**.</span></span>  
  
8.  <span data-ttu-id="70386-119">Cliquez sur **Modifier la règle d’entreprise sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="70386-119">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="70386-120">Dans le volet **Composants** , développez le nœud **Actions** .</span><span class="sxs-lookup"><span data-stu-id="70386-120">In the **Components** pane, expand the **Actions** node.</span></span>  
  
10. <span data-ttu-id="70386-121">Dans le nœud Valeur par défaut, cliquez sur **prend par défaut une valeur générée** et faites-la glisser vers le libellé **Actions** du volet **THEN**.</span><span class="sxs-lookup"><span data-stu-id="70386-121">In the Default Value node, click **defaults to a generated value** and drag it to the **THEN** pane's **Actions** label.</span></span>  
  
11. <span data-ttu-id="70386-122">Dans le volet **Attributs** , cliquez sur l’attribut avec la valeur à générer et faites-le glisser vers le libellé **Sélectionner un attribut** du volet **Modifier l’action** .</span><span class="sxs-lookup"><span data-stu-id="70386-122">In the **Attributes** pane, click the attribute with the value you want to generated and drag it to the **Edit Action** pane's **Select attribute** label.</span></span>  
  
12. <span data-ttu-id="70386-123">Tapez une valeur dans les zones **Démarrer avec** et **Incrémenter** .</span><span class="sxs-lookup"><span data-stu-id="70386-123">Type a value in the **Start with** and **Increment by** boxes.</span></span> <span data-ttu-id="70386-124">Si les membres existent déjà, la valeur sera définie en fonction de la valeur existante la plus élevée.</span><span class="sxs-lookup"><span data-stu-id="70386-124">If members already exist, the value will be set based on the highest existing value.</span></span> <span data-ttu-id="70386-125">Par exemple, si la valeur existante la plus élevée est 299 et que vous définissez **Incrémenter de** sur **1**, la valeur du membre suivant sera définie sur 300.</span><span class="sxs-lookup"><span data-stu-id="70386-125">For example, if the highest existing value is 299 and you set **Increment by** to **1**, the next member's value will be set to 300.</span></span>  
  
13. <span data-ttu-id="70386-126">Dans le volet **Modifier l’action** , cliquez sur **Enregistrer l’élément**.</span><span class="sxs-lookup"><span data-stu-id="70386-126">In the **Edit Action** pane, click **Save item**.</span></span>  
  
14. <span data-ttu-id="70386-127">Cliquez sur **Précédent**.</span><span class="sxs-lookup"><span data-stu-id="70386-127">Click **Back**.</span></span>  
  
15. <span data-ttu-id="70386-128">(Facultatif) Dans la page **Maintenance des règles d’entreprise** , sur la ligne qui contient votre règle d’entreprise, double-cliquez sur une cellule dans la colonne **Nom**, **Description**ou **Notification** pour mettre à jour la valeur.</span><span class="sxs-lookup"><span data-stu-id="70386-128">Optionally, on the **Business Rules Maintenance** page, for the row that contains your business rule, double-click a cell in the **Name**, **Description**, or **Notification** column to update the value.</span></span>  
  
16. <span data-ttu-id="70386-129">Cliquez sur **Publier les règles d’entreprise**.</span><span class="sxs-lookup"><span data-stu-id="70386-129">Click **Publish business rules**.</span></span>  
  
17. <span data-ttu-id="70386-130">Dans la boîte de dialogue de confirmation, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="70386-130">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="70386-131">L’état de la règle devient **Actif**.</span><span class="sxs-lookup"><span data-stu-id="70386-131">The rule's status changes to **Active**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="70386-132">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="70386-132">Next Steps</span></span>  
  
-   [<span data-ttu-id="70386-133">Valider des membres spécifiques par rapport aux règles d’entreprise &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="70386-133">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
-   [<span data-ttu-id="70386-134">Valider une version par rapport aux règles d’entreprise &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="70386-134">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="70386-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="70386-135">See Also</span></span>  
 <span data-ttu-id="70386-136">[Création automatique de code &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="70386-136">[Automatic Code Creation &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md) </span></span>  
 <span data-ttu-id="70386-137">[&#40;des règles d’entreprise Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="70386-137">[Business Rules &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span></span>  
 [<span data-ttu-id="70386-138">Validation &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="70386-138">Validation &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validation-master-data-services.md)  
  
  
