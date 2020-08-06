---
title: Publication de données (Complément MDS pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: ea84a9aa-aeec-411b-ab8d-bc1b14f864a3
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ab37a353469d1902394a3e2cd8060d9be82abb40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704284"
---
# <a name="publishing-data-mds-add-in-for-excel"></a><span data-ttu-id="3aa59-102">Publication des données (Complément MDS pour Excel)</span><span class="sxs-lookup"><span data-stu-id="3aa59-102">Publishing Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="3aa59-103">Dans le [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], publiez les données dans le référentiel MDS lorsque vous souhaitez les partager avec d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3aa59-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], publish data to the MDS repository when you want to share it with other users.</span></span> <span data-ttu-id="3aa59-104">Dès que les données sont publiées, elles peuvent être téléchargées par les autres utilisateurs du complément.</span><span class="sxs-lookup"><span data-stu-id="3aa59-104">As soon as data is published, it is available for other users of the Add-in to download.</span></span>  
  
 <span data-ttu-id="3aa59-105">Quand vous publiez des données, toutes celles que vous avez ajoutées ou mises à jour sont publiées dans le référentiel MDS.</span><span class="sxs-lookup"><span data-stu-id="3aa59-105">When you publish data, any data you've added or updated is published to the MDS repository.</span></span> <span data-ttu-id="3aa59-106">Les données que vous avez supprimées ne sont pas publiées, vous devez les supprimer séparément.</span><span class="sxs-lookup"><span data-stu-id="3aa59-106">Data you've deleted is not published-you must delete data separately.</span></span> <span data-ttu-id="3aa59-107">Pour plus d’informations, consultez [Supprimer une ligne &#40;Complément MDS pour Excel&#41;](delete-a-row-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="3aa59-107">For more information, see [Delete a Row &#40;MDS Add-in for Excel&#41;](delete-a-row-mds-add-in-for-excel.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3aa59-108">La publication ne peut pas être utilisée pour créer une entité.</span><span class="sxs-lookup"><span data-stu-id="3aa59-108">Publishing cannot be used to create a new entity.</span></span> <span data-ttu-id="3aa59-109">Pour plus d’informations sur la création d’entités, consultez [Créer une entité &#40;Complément MDS pour Excel&#41;](create-an-entity-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="3aa59-109">For more information about creating entities, see [Create an Entity &#40;MDS Add-in for Excel&#41;](create-an-entity-mds-add-in-for-excel.md).</span></span>  
  
## <a name="when-multiple-users-publish-at-the-same-time"></a><span data-ttu-id="3aa59-110">Lorsque plusieurs utilisateurs publient en même temps</span><span class="sxs-lookup"><span data-stu-id="3aa59-110">When Multiple Users Publish at the Same Time</span></span>  
 <span data-ttu-id="3aa59-111">Plusieurs utilisateurs peuvent publier des mises à jour sur les mêmes données.</span><span class="sxs-lookup"><span data-stu-id="3aa59-111">Multiple users can publish updates to the same data.</span></span> <span data-ttu-id="3aa59-112">Lorsqu'un utilisateur publie, la mise à jour est enregistrée dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="3aa59-112">As each user publishes, the update is saved to the database.</span></span> <span data-ttu-id="3aa59-113">Cela signifie qu'un utilisateur qui ne travaille pas sur des données récemment mises à jour peut toujours modifier leurs valeurs lorsqu'il les publie.</span><span class="sxs-lookup"><span data-stu-id="3aa59-113">This means that a user who was not working with the most recently-updated data can still change the value when he or she publishes.</span></span>  
  
 <span data-ttu-id="3aa59-114">Seules les modifications que vous apportez sont publiées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="3aa59-114">Only the updates you make are published to the database.</span></span> <span data-ttu-id="3aa59-115">Aucune donnée obsolète dans la feuille de calcul n'est publiée.</span><span class="sxs-lookup"><span data-stu-id="3aa59-115">Any out-of-date data in the worksheet is not published.</span></span>  
  
## <a name="transactions-and-annotations"></a><span data-ttu-id="3aa59-116">Transactions et annotations</span><span class="sxs-lookup"><span data-stu-id="3aa59-116">Transactions and Annotations</span></span>  
 <span data-ttu-id="3aa59-117">Chaque modification publiée est enregistrée comme une transaction.</span><span class="sxs-lookup"><span data-stu-id="3aa59-117">Each published change is saved as a transaction.</span></span> <span data-ttu-id="3aa59-118">Si vous le souhaitez, vous pouvez ajouter des annotations (commentaires) à une transaction, pour expliquer pourquoi vous avez effectué la modification.</span><span class="sxs-lookup"><span data-stu-id="3aa59-118">If you choose, you can add annotations (comments) to a transaction, to explain why you made the change.</span></span>  
  
-   <span data-ttu-id="3aa59-119">Vous ne pouvez pas annoter les suppressions, bien que celles-ci soient enregistrées en tant que transactions qui peuvent être inversées par un administrateur.</span><span class="sxs-lookup"><span data-stu-id="3aa59-119">You cannot annotate deletions, although deletions are saved as transactions that can be reversed by an administrator.</span></span>  
  
-   <span data-ttu-id="3aa59-120">Si vous modifiez la valeur de **code** d’un membre, celle-ci n’est pas enregistrée en tant que transaction et toutes les transactions précédentes pour le membre ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="3aa59-120">If you change the **Code** value for a member, it is not recorded as a transaction, and all previous transactions for the member are unavailable.</span></span>  
  
-   <span data-ttu-id="3aa59-121">Vous pouvez afficher les transactions effectuées sur un membre par d'autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3aa59-121">You can view transactions made to a member by other users.</span></span> <span data-ttu-id="3aa59-122">Vous pouvez également afficher toutes les transactions que vous avez effectuées sur un membre, même si vous n’avez plus l’autorisation d’accès aux attributs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="3aa59-122">You can also view all transactions you've made to a member, even if you no longer have permission to specific attributes.</span></span>  
  
 <span data-ttu-id="3aa59-123">Vous pouvez afficher toutes les transactions effectuées sur un membre.</span><span class="sxs-lookup"><span data-stu-id="3aa59-123">You can view all transactions made to a member.</span></span> <span data-ttu-id="3aa59-124">Pour plus d’informations, consultez [Afficher toutes les annotations ou transactions pour un membre &#40;Complément MDS pour Excel&#41;](view-all-annotations-or-transactions-for-a-member-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="3aa59-124">For more information, see [View All Annotations or Transactions for a Member &#40;MDS Add-in for Excel&#41;](view-all-annotations-or-transactions-for-a-member-mds-add-in-for-excel.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3aa59-125">Si vous entrez une annotation de plus de 500 caractères, elle sera automatiquement tronquée.</span><span class="sxs-lookup"><span data-stu-id="3aa59-125">If you enter an annotation of more than 500 characters, the annotation is automatically truncated.</span></span>  
  
## <a name="business-rule-and-other-validation"></a><span data-ttu-id="3aa59-126">Règle d'entreprise et autres validations</span><span class="sxs-lookup"><span data-stu-id="3aa59-126">Business Rule and Other Validation</span></span>  
 <span data-ttu-id="3aa59-127">Quand vous publiez des données, une validation est exécutée pour garantir que les données sont exactes avant d’être ajoutées au référentiel MDS.</span><span class="sxs-lookup"><span data-stu-id="3aa59-127">When you publish data, validation is performed to ensure data is accurate before it's added to the MDS repository.</span></span> <span data-ttu-id="3aa59-128">Si les données ne répondent pas aux critères spécifiés, elles ne seront pas publiées dans le référentiel.</span><span class="sxs-lookup"><span data-stu-id="3aa59-128">If the data does not meet specified criteria, it will not be published to the repository.</span></span> <span data-ttu-id="3aa59-129">Pour plus d’informations, consultez [Validation des données &#40;Complément MDS pour Excel&#41;](validating-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="3aa59-129">For more information, see [Validating Data &#40;MDS Add-in for Excel&#41;](validating-data-mds-add-in-for-excel.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="3aa59-130">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="3aa59-130">Related Tasks</span></span>  
  
|<span data-ttu-id="3aa59-131">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="3aa59-131">Task Description</span></span>|<span data-ttu-id="3aa59-132">Rubrique</span><span class="sxs-lookup"><span data-stu-id="3aa59-132">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="3aa59-133">Publiez des données à partir de la feuille de calcul active vers le référentiel MDS.</span><span class="sxs-lookup"><span data-stu-id="3aa59-133">Publish data from the active worksheet back to the MDS repository.</span></span>|[<span data-ttu-id="3aa59-134">Publier des données d’Excel dans MDS &#40;Complément MDS pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="3aa59-134">Publish Data from Excel to MDS &#40;MDS Add-in for Excel&#41;</span></span>](import-data-from-excel-to-master-data-services-mds-add-in-for-excel.md)|  
|<span data-ttu-id="3aa59-135">Supprimez une ligne du référentiel MDS et de la feuille de calcul en même temps.</span><span class="sxs-lookup"><span data-stu-id="3aa59-135">Delete a row from the MDS repository and from the worksheet at the same time.</span></span>|[<span data-ttu-id="3aa59-136">Supprimer une ligne &#40;Complément MDS pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="3aa59-136">Delete a Row &#40;MDS Add-in for Excel&#41;</span></span>](delete-a-row-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="3aa59-137">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="3aa59-137">Related Content</span></span>  
  
-   [<span data-ttu-id="3aa59-138">Actualisation des données &#40;Complément MDS pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="3aa59-138">Refreshing Data &#40;MDS Add-in for Excel&#41;</span></span>](refreshing-data-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="3aa59-139">Complément Master Data Services pour Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="3aa59-139">Master Data Services Add-in for Microsoft Excel</span></span>](master-data-services-add-in-for-microsoft-excel.md)  
  
  
