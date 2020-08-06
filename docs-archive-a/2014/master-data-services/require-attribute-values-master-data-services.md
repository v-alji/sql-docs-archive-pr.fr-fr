---
title: Requérir des valeurs d’attribut (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], requiring attribute values
- attributes [Master Data Services], requiring values
ms.assetid: a360ef13-0c34-43b8-a87e-2f5d8732d30e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 42b412fc42138c5e186c6c7ad42373f20e35f3cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602870"
---
# <a name="require-attribute-values-master-data-services"></a><span data-ttu-id="a3c8f-102">Requérir des valeurs d'attribut (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="a3c8f-102">Require Attribute Values (Master Data Services)</span></span>
  <span data-ttu-id="a3c8f-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], requérez des valeurs d'attribut lorsque vous souhaitez vérifier que vos données de référence sont complètes.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], require attribute values when you want to ensure your master data is complete.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a3c8f-104">Les membres sans valeurs d'attribut basé sur un domaine ne sont pas affichés dans les hiérarchies dérivées basées sur ces relations.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-104">Members that are missing domain-based attribute values are not displayed in derived hierarchies that are based on those relationships.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a3c8f-105">Prérequis</span><span class="sxs-lookup"><span data-stu-id="a3c8f-105">Prerequisites</span></span>  
 <span data-ttu-id="a3c8f-106">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="a3c8f-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="a3c8f-107">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .</span><span class="sxs-lookup"><span data-stu-id="a3c8f-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="a3c8f-108">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-108">You must be a model administrator.</span></span> <span data-ttu-id="a3c8f-109">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a3c8f-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-require-attribute-values"></a><span data-ttu-id="a3c8f-110">Pour requérir des valeurs d'attribut</span><span class="sxs-lookup"><span data-stu-id="a3c8f-110">To require attribute values</span></span>  
  
1.  <span data-ttu-id="a3c8f-111">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="a3c8f-112">Dans la barre de menus, pointez sur **Gérer** et cliquez sur **Règles d'entreprise**.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-112">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="a3c8f-113">Dans la page **Maintenance des règles d’entreprise** , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-113">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="a3c8f-114">Dans la liste **Entité** , sélectionnez une entité.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-114">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="a3c8f-115">Dans la liste **Type de membre** , sélectionnez un type de membre auquel appliquer la règle d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-115">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="a3c8f-116">Dans la liste **Attribut** , sélectionnez un attribut ou conservez l’option par défaut **Tout**.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-116">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="a3c8f-117">Cliquez sur **Ajouter une règle d’entreprise**.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-117">Click **Add business rule**.</span></span>  
  
8.  <span data-ttu-id="a3c8f-118">Cliquez sur **Modifier la règle d’entreprise sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-118">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="a3c8f-119">Dans le volet **Composants** , développez le nœud **Actions** .</span><span class="sxs-lookup"><span data-stu-id="a3c8f-119">In the **Components** pane, expand the **Actions** node.</span></span>  
  
10. <span data-ttu-id="a3c8f-120">Cliquez sur **est requis** et faites-le glisser vers l’étiquette **action** du volet **Then** .</span><span class="sxs-lookup"><span data-stu-id="a3c8f-120">Click **is required** and drag it to the **THEN** pane's **Action** label.</span></span>  
  
11. <span data-ttu-id="a3c8f-121">Dans le volet **Attributs** , cliquez sur un attribut et faites-le glisser vers l’étiquette **Sélectionner un attribut** du volet **Modifier l’action** .</span><span class="sxs-lookup"><span data-stu-id="a3c8f-121">In the **Attributes** pane, click an attribute and drag it to the **Edit Action** pane's **Select attribute** label.</span></span>  
  
12. <span data-ttu-id="a3c8f-122">Dans le volet **Modifier l’action** , cliquez sur **Enregistrer l’élément**.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-122">In the **Edit Action** pane, click **Save item**.</span></span>  
  
13. <span data-ttu-id="a3c8f-123">Cliquez sur **Précédent**.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-123">Click **Back**.</span></span>  
  
14. <span data-ttu-id="a3c8f-124">(Facultatif) Dans la page **Maintenance des règles d’entreprise** , sur la ligne qui contient votre règle d’entreprise, double-cliquez sur une cellule dans la colonne **Nom**, **Description**ou **Notification** pour mettre à jour la valeur.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-124">Optionally, on the **Business Rules Maintenance** page, for the row that contains your business rule, double-click a cell in the **Name**, **Description**, or **Notification** column to update the value.</span></span>  
  
15. <span data-ttu-id="a3c8f-125">Cliquez sur **Publier les règles d’entreprise**.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-125">Click **Publish business rules**.</span></span>  
  
16. <span data-ttu-id="a3c8f-126">Dans la boîte de dialogue de confirmation, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-126">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="a3c8f-127">L’état de la règle devient **Actif**.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-127">The rule's status changes to **Active**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a3c8f-128">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="a3c8f-128">Next Steps</span></span>  
  
-   <span data-ttu-id="a3c8f-129">Appliquez des règles d'entreprise aux données en suivant l'une de ces procédures :</span><span class="sxs-lookup"><span data-stu-id="a3c8f-129">Apply business rules to data by following one of these procedures:</span></span>  
  
    -   [<span data-ttu-id="a3c8f-130">Valider des membres spécifiques par rapport aux règles d’entreprise &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a3c8f-130">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
    -   [<span data-ttu-id="a3c8f-131">Valider une version par rapport aux règles d’entreprise &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a3c8f-131">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="a3c8f-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a3c8f-132">See Also</span></span>  
 <span data-ttu-id="a3c8f-133">[&#40;des règles d’entreprise Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a3c8f-133">[Business Rules &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span></span>  
 [<span data-ttu-id="a3c8f-134">Hiérarchies dérivées &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a3c8f-134">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)  
  
  
