---
title: Changer le type d’attribut (Complément MDS pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 9d3001d9-8d0f-4e4a-8e04-4f666bf0df69
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a55ca53fcf6923957e2196840aea2fb5914e1746
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698388"
---
# <a name="change-the-attribute-type-mds-add-in-for-excel"></a><span data-ttu-id="8fb1a-102">Modifier le type d'attribut (complément MDS pour Excel)</span><span class="sxs-lookup"><span data-stu-id="8fb1a-102">Change the Attribute Type (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="8fb1a-103">Dans [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], les administrateurs peuvent modifier le type d’attribut lorsque le type de données ou le nombre de caractères autorisé est incorrect.</span><span class="sxs-lookup"><span data-stu-id="8fb1a-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], administrators can change the attribute type when the data type or number of allowed characters is incorrect.</span></span>  
  
 <span data-ttu-id="8fb1a-104">Si vous souhaitez modifier le type d’attribut pour créer une liste contrainte (attribut basé sur un domaine), consultez [Créer un attribut basé sur un domaine &#40;Complément MDS pour Exce&#41;](create-a-domain-based-attribute-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="8fb1a-104">If you want to change the attribute type to create a constrained list (domain-based attribute), see [Create a Domain-based Attribute &#40;MDS Add-in for Excel&#41;](create-a-domain-based-attribute-mds-add-in-for-excel.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8fb1a-105"> Vous ne pouvez pas mettre à jour le type ou la longueur des colonnes **Nom** ou **Code** .</span><span class="sxs-lookup"><span data-stu-id="8fb1a-105">You cannot update the type or length of the **Name** or **Code** columns.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8fb1a-106">Prérequis</span><span class="sxs-lookup"><span data-stu-id="8fb1a-106">Prerequisites</span></span>  
 <span data-ttu-id="8fb1a-107">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="8fb1a-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="8fb1a-108">Vous devez avoir l'autorisation d'accéder aux zones fonctionnelles **Administration de système** et **Explorateur** .</span><span class="sxs-lookup"><span data-stu-id="8fb1a-108">You must have permission to access the **System Administration** and **Explorer** functional areas.</span></span>  
  
-   <span data-ttu-id="8fb1a-109">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="8fb1a-109">You must be a model administrator.</span></span> <span data-ttu-id="8fb1a-110">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8fb1a-110">For more information, see [Administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="8fb1a-111">Un modèle, une entité et un attribut doivent exister.</span><span class="sxs-lookup"><span data-stu-id="8fb1a-111">There must be an existing model, entity, and attribute.</span></span>  
  
### <a name="to-change-the-attribute-type"></a><span data-ttu-id="8fb1a-112">Pour modifier le type d'attribut</span><span class="sxs-lookup"><span data-stu-id="8fb1a-112">To change the attribute type</span></span>  
  
1.  <span data-ttu-id="8fb1a-113">Dans Excel, chargez l'entité qui contient la colonne (attribut) que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="8fb1a-113">In Excel, load the entity that contains the column (attribute) you want to change.</span></span> <span data-ttu-id="8fb1a-114">Pour plus d’informations, consultez [charger des données à partir de MDS dans Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8fb1a-114">For more information, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
2.  <span data-ttu-id="8fb1a-115">Cliquez sur une cellule de la colonne que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="8fb1a-115">Click any cell in the column you want to change.</span></span>  
  
3.  <span data-ttu-id="8fb1a-116">Dans le groupe **Modèle de build** , cliquez sur **Propriétés d'attribut**.</span><span class="sxs-lookup"><span data-stu-id="8fb1a-116">In the **Build Model** group, click **Attribute Properties**.</span></span>  
  
4.  <span data-ttu-id="8fb1a-117">Dans la boîte de dialogue **Propriétés d'attribut** , mettez à jour les paramètres si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="8fb1a-117">In the **Attribute Properties** dialog box, update settings as needed.</span></span>  
  
5.  <span data-ttu-id="8fb1a-118">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fb1a-118">Click **OK**.</span></span>  
  
## <a name="what-happens-when-you-change-the-attribute-type"></a><span data-ttu-id="8fb1a-119">Que se passe-t-il lorsque vous modifiez le type d'attribut ?</span><span class="sxs-lookup"><span data-stu-id="8fb1a-119">What happens when you change the attribute type?</span></span>  
 <span data-ttu-id="8fb1a-120">S'il existe une dépendance sur l'attribut, par exemple si l'attribut est référencé par une règle d'entreprise MDS ou si l'attribut est inclus dans une vue d'abonnement, et si vous modifiez le type de données d'un attribut, MDS va :</span><span class="sxs-lookup"><span data-stu-id="8fb1a-120">If there is any dependency on the attribute, such as the attribute is referenced by any MDS business rule or the attribute is included in a subscription view, and you change the data type of an attribute, MDS will:</span></span>  
  
-   <span data-ttu-id="8fb1a-121">Modifier le type de données de l'attribut.</span><span class="sxs-lookup"><span data-stu-id="8fb1a-121">Change the data type of the attribute.</span></span>  
  
-   <span data-ttu-id="8fb1a-122">Génère une copie de l’attribut avec le suffixe « _old » qui ne contient aucune valeur.</span><span class="sxs-lookup"><span data-stu-id="8fb1a-122">Generate a copy of the attribute with the suffix "_old" that does not contain any value.</span></span> <span data-ttu-id="8fb1a-123">C’est ce que l’on appelle un attribut **déconseillé** .</span><span class="sxs-lookup"><span data-stu-id="8fb1a-123">This is called a **deprecated** attribute.</span></span>  
  
 <span data-ttu-id="8fb1a-124">Cependant, toutes les dépendances existantes sur l'attribut d'origine pointeront vers l'attribut déconseillé, et non vers celui modifié.</span><span class="sxs-lookup"><span data-stu-id="8fb1a-124">However, all the existing dependencies on the original attribute will point to the deprecated attribute, and not to the changed one.</span></span>  
  
 <span data-ttu-id="8fb1a-125">Cela implique que :</span><span class="sxs-lookup"><span data-stu-id="8fb1a-125">This implies that:</span></span>  
  
-   <span data-ttu-id="8fb1a-126">Vous devez actualiser les règles d'entreprise pour indiquer l'attribut modifié car la logique peut ne pas être la même avec le nouveau type de données de l'attribut.</span><span class="sxs-lookup"><span data-stu-id="8fb1a-126">You must refresh the business rules to point to the changed attribute because the logic may not be the same given the new data type of the attribute.</span></span> <span data-ttu-id="8fb1a-127">Vous devrez modifier chaque règle affectée, puis retravailler les expressions pour supprimer les références de l'attribut déconseillé (_old) et utiliser l'attribut mis à jour.</span><span class="sxs-lookup"><span data-stu-id="8fb1a-127">You will have to edit each affected rule, and then rework the expressions to point to remove references from the deprecated attribute (_old) to point to the updated attribute.</span></span>  
  
-   <span data-ttu-id="8fb1a-128">Vous devez ouvrir toutes les vues d’abonnement dans la sélection gestion de l’intégration, sélectionner la ligne de vue, l’ouvrir pour la modifier en cliquant sur l’icône en forme de crayon, puis cliquer sur l’icône **enregistrer le disque** pour actualiser la définition de la vue.</span><span class="sxs-lookup"><span data-stu-id="8fb1a-128">You must open any subscription views under the Integration Management selection, select the view row, open it for editing by clicking the pencil icon, and then click the **Save disk** icon to refresh the view definition.</span></span> <span data-ttu-id="8fb1a-129">Aucune autre modification n'est nécessaire pour régénérer la syntaxe de la vue.</span><span class="sxs-lookup"><span data-stu-id="8fb1a-129">No other change is needed to regenerate the view syntax.</span></span>  
  
-   <span data-ttu-id="8fb1a-130">Les tables intermédiaires qui incluent l'attribut comprendront une colonne d'attribut déconseillé, ce qui signifie que votre code intermédiaire sera affecté.</span><span class="sxs-lookup"><span data-stu-id="8fb1a-130">Staging tables that include the attribute will have a deprecated attribute column added to them, which means that your staging code will be affected.</span></span> <span data-ttu-id="8fb1a-131">Pour vous débarrasser de l'attribut déconseillé, vous pouvez le supprimer après avoir mis à jour les règles d'entreprise et les vues d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="8fb1a-131">To get rid of the deprecated attribute, you can delete it after you have updated the business rules and subscription views.</span></span>  
  
 <span data-ttu-id="8fb1a-132">**Suppression de l'attribut déconseillé**</span><span class="sxs-lookup"><span data-stu-id="8fb1a-132">**Deleting the deprecated attribute**</span></span>  
  
 <span data-ttu-id="8fb1a-133">Avant de supprimer un attribut déconseillé, vous devez supprimer toutes les références à l'attribut, par exemple, en corrigeant les règles d'entreprise et en régénérant les vues d'abonnement comme décrit plus haut.</span><span class="sxs-lookup"><span data-stu-id="8fb1a-133">Before you delete any deprecated attribute, you must remove any references to the attribute such as fixing the business rules and regenerating subscription views as described earlier.</span></span> <span data-ttu-id="8fb1a-134">Sinon, vous obtiendrez une erreur dans la page Web Administration de système lorsque vous tenterez de supprimer l'attribut déconseillé, indiquant que l'attribut ne peut pas être supprimé car il est référencé par un objet.</span><span class="sxs-lookup"><span data-stu-id="8fb1a-134">Otherwise, you will get an error in the System Administration web page when you attempt to delete the deprecated attribute stating that the attribute cannot be deleted because it is referenced by an object.</span></span>  
  
 <span data-ttu-id="8fb1a-135">Pour supprimer un attribut, consultez [supprimer un attribut &#40;Master Data Services&#41;](../delete-an-attribute-master-data-services.md)</span><span class="sxs-lookup"><span data-stu-id="8fb1a-135">To delete an attribute, see [Delete an Attribute &#40;Master Data Services&#41;](../delete-an-attribute-master-data-services.md)</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="8fb1a-136">Modifier les types de données des attributs MDS qui incluent des données existantes et des entités associées est une opération lourde, notamment s'il existe une règle d'entreprise ou une vue d'abonnement déclarée qui dépend de l'entité.</span><span class="sxs-lookup"><span data-stu-id="8fb1a-136">It is cumbersome to change data types for MDS attributes that have existing data and related entities, especially if there is a business rule or subscription view declared which depends on the entity.</span></span> <span data-ttu-id="8fb1a-137">La méthode recommandée est de commencer à utiliser un type de données qui est suffisamment flexible pour contenir les valeurs requises.</span><span class="sxs-lookup"><span data-stu-id="8fb1a-137">The best practice is to start with a data type that is flexible enough to hold the necessary values.</span></span> <span data-ttu-id="8fb1a-138">Par exemple, les chaînes sont souvent courtes au début, mais il peut être nécessaire de les rallonger au fil du temps ; par conséquent, considérez le pire des scénarios.</span><span class="sxs-lookup"><span data-stu-id="8fb1a-138">For example, strings may start small, but may need to be lengthened over time, so consider the worst case scenarios.</span></span> <span data-ttu-id="8fb1a-139">Les chaînes de texte longues peuvent être fastidieuses à gérer (par exemple, il est difficile d'ajuster à l'écran des zones de texte longues dans l'interface utilisateur graphique) ; par conséquent, évitez les chaînes trop longues.</span><span class="sxs-lookup"><span data-stu-id="8fb1a-139">Extra text string length can be burdensome (for example, wide GUI text boxes are hard to fit on the screen), so avoid too long string length.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fb1a-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8fb1a-140">See Also</span></span>  
 <span data-ttu-id="8fb1a-141">[Attributs &#40;Master Data Services&#41;](../attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="8fb1a-141">[Attributes &#40;Master Data Services&#41;](../attributes-master-data-services.md) </span></span>  
 [<span data-ttu-id="8fb1a-142">Génération d’un modèle &#40;Complément MDS pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="8fb1a-142">Building a Model &#40;MDS Add-in for Excel&#41;</span></span>](building-a-model-mds-add-in-for-excel.md)  
  
  
