---
title: Générer automatiquement un ensemble de filtres de jointure entre des Articles de fusion (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- automatic join filter generation
- join filters
ms.assetid: 7ef419f4-c17f-42a5-9068-174a3ec08941
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4bfdbf93aad134e4da873a6aade307754a2637e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599892"
---
# <a name="automatically-generate-a-set-of-join-filters-between-merge-articles-sql-server-management-studio"></a><span data-ttu-id="9cd66-102">générer automatiquement un ensemble de filtres de jointure entre des articles de fusion (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="9cd66-102">Automatically Generate a Set of Join Filters Between Merge Articles (SQL Server Management Studio)</span></span>
  <span data-ttu-id="9cd66-103">Générez automatiquement un ensemble de filtres de jointure dans la page **Filtrer les lignes de la table** de l’Assistant Nouvelle publication ou la page **Filtrer les lignes** de la boîte de dialogue **Propriétés de la publication - \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="9cd66-103">Automatically generate a set of join filters on the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="9cd66-104">Pour plus d’informations sur l’utilisation de l’Assistant et sur l’accès à la boîte de dialogue, consultez [Créer une publication](create-a-publication.md) et [Afficher et modifier les propriétés d’une publication](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="9cd66-104">For more information about using the wizard and accessing the dialog box, see [Create a Publication](create-a-publication.md) and [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9cd66-105">Si vous générez automatiquement un ensemble de filtres de jointure dans la boîte de dialogue **Propriétés de la publication - \<Publication>** une fois les abonnements à la publication initialisés, vous devez générer un nouvel instantané et réinitialiser tous les abonnements après avoir effectué la modification.</span><span class="sxs-lookup"><span data-stu-id="9cd66-105">If you automatically generate a set of join filters in the **Publication Properties - \<Publication>** dialog box after subscriptions to the publication have been initialized, you must generate a new snapshot and reinitialize all subscriptions after making the change.</span></span> <span data-ttu-id="9cd66-106">Pour plus d’informations sur les exigences relatives aux changements de propriétés, consultez [Changer les propriétés des publications et des articles](change-publication-and-article-properties.md).</span><span class="sxs-lookup"><span data-stu-id="9cd66-106">For more information about requirements for property changes, see [Change Publication and Article Properties](change-publication-and-article-properties.md).</span></span>  
  
 <span data-ttu-id="9cd66-107">Les filtres de jointure peuvent être créés manuellement pour un ensemble de tables, ou la réplication peut les générer automatiquement en fonction des relations de clé étrangère à clé primaire définies sur les tables.</span><span class="sxs-lookup"><span data-stu-id="9cd66-107">Join filters can be created manually for a set of tables, or replication can generate the filters automatically based on the foreign key to primary key relationships defined on the tables.</span></span> <span data-ttu-id="9cd66-108">Pour plus d’informations sur la création manuelle de filtres de jointure, consultez [Définir et modifier un filtre de jointure entre des articles de fusion](define-and-modify-a-join-filter-between-merge-articles.md).</span><span class="sxs-lookup"><span data-stu-id="9cd66-108">For more information about creating join filters manually, see [Define and Modify a Join Filter Between Merge Articles](define-and-modify-a-join-filter-between-merge-articles.md).</span></span>  
  
### <a name="to-automatically-generate-a-set-of-join-filters-between-merge-articles"></a><span data-ttu-id="9cd66-109">Pour générer automatiquement un ensemble de filtres de jointure entre articles de fusion</span><span class="sxs-lookup"><span data-stu-id="9cd66-109">To automatically generate a set of join filters between merge articles</span></span>  
  
1.  <span data-ttu-id="9cd66-110">Sur la page **Filtrer les lignes de la table** de l’Assistant Nouvelle publication, ou la page **Filtrer les lignes** de la boîte de dialogue **Propriétés de la Publication - \<Publication>** , cliquez sur **Ajouter**, puis sur **Générer automatiquement des filtres**.</span><span class="sxs-lookup"><span data-stu-id="9cd66-110">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, click **Add**, and then click **Automatically Generate Filters**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9cd66-111">La génération automatique de filtres supprime tout filtre de lignes ou de jointure existant dans la publication.</span><span class="sxs-lookup"><span data-stu-id="9cd66-111">Automatically generating filters deletes any existing row filters or join filters in the publication.</span></span> <span data-ttu-id="9cd66-112">Vous pouvez ajouter des filtres après avoir généré automatiquement un ensemble de filtres.</span><span class="sxs-lookup"><span data-stu-id="9cd66-112">You can add filters after automatically generating a set of filters.</span></span>  
  
2.  <span data-ttu-id="9cd66-113">Suivez le processus de la boîte de dialogue **Générer des filtres** pour créer un filtre de lignes.</span><span class="sxs-lookup"><span data-stu-id="9cd66-113">Follow the process in the **Generate Filters** dialog box to create a row filter.</span></span> <span data-ttu-id="9cd66-114">Le filtre de lignes est ensuite étendu aux tables associées à la table filtrée via les relations de clé primaire et de clé étrangère.</span><span class="sxs-lookup"><span data-stu-id="9cd66-114">The row filter is then extended to the tables related to the filtered table through primary key and foreign key relationships.</span></span>  
  
    1.  <span data-ttu-id="9cd66-115">Sélectionnez une table à filtrer dans la zone de liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="9cd66-115">Select a table to filter from the drop-down list box.</span></span>  
  
    2.  <span data-ttu-id="9cd66-116">Créez une instruction de filtrage dans la zone de texte **Instruction de filtrage** .</span><span class="sxs-lookup"><span data-stu-id="9cd66-116">Create a filter statement in the **Filter statement** text box.</span></span> <span data-ttu-id="9cd66-117">Vous pouvez taper directement dans la zone de texte, mais vous pouvez aussi faire glisser et déposer des colonnes depuis la zone de liste **Colonnes** .</span><span class="sxs-lookup"><span data-stu-id="9cd66-117">You can type directly in the text area, and you can also drag and drop columns from the **Columns** list box.</span></span>  
  
         <span data-ttu-id="9cd66-118">La zone de texte **Instruction de filtrage** comprend un texte par défaut, qui est de la forme suivante :</span><span class="sxs-lookup"><span data-stu-id="9cd66-118">The **Filter statement** text area includes the default text, which is in the form of:</span></span>  
  
        ```  
        SELECT <published_columns> FROM [tableowner].[tablename] WHERE  
        ```  
  
         <span data-ttu-id="9cd66-119">Il est impossible de modifier le texte par défaut ; tapez la clause de filtre pour un filtre de lignes statiques ou un filtrage des lignes paramétrable après le mot clé WHERE à l'aide de la syntaxe SQL standard.</span><span class="sxs-lookup"><span data-stu-id="9cd66-119">The default text cannot be changed; type the filter clause for a static row filter or a parameterized row filter after the WHERE keyword using standard SQL syntax.</span></span> <span data-ttu-id="9cd66-120">La clause de filtre complète pour un filtre de lignes paramétrable peut se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="9cd66-120">The complete filter clause for a parameterized row filter would look like:</span></span>  
  
        ```  
        SELECT <published_columns> FROM [HumanResources].[Employee] WHERE LoginID = SUSER_SNAME()  
        ```  
  
         <span data-ttu-id="9cd66-121">La clause WHERE doit utiliser un nommage en deux parties ; les nommages en trois et en quatre parties ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="9cd66-121">The WHERE clause should use two-part naming; three-part naming and four-part naming are not supported.</span></span>  
  
    3.  <span data-ttu-id="9cd66-122">Spécifiez les options de filtre.</span><span class="sxs-lookup"><span data-stu-id="9cd66-122">Specify filter options.</span></span>  
  
         <span data-ttu-id="9cd66-123">Sélectionnez l'option qui correspond aux données qui seront partagées entre des Abonnés : **Une ligne de cette table ira à plusieurs abonnements** or **Une ligne de cette table ira à un seul abonnement**.</span><span class="sxs-lookup"><span data-stu-id="9cd66-123">Select the option that matches how data will be shared among Subscribers: **A row from this table will go to multiple subscriptions** or **A row from this table will go to only one subscription**.</span></span> <span data-ttu-id="9cd66-124">Si vous sélectionnez **Filtre paramétré créant des partitions qui ne se chevauchent pas, avec un seul abonnement par partition**, la réplication de fusion peut optimiser les performances en stockant et en traitant moins de métadonnées.</span><span class="sxs-lookup"><span data-stu-id="9cd66-124">If you select **A row from this table will go to only one subscription**, merge replication can optimize performance by storing and processing less metadata.</span></span> <span data-ttu-id="9cd66-125">Cependant, vous devez vérifier que les données sont partitionnées de telle façon qu'une ligne ne peut pas être répliquée sur plus d'un Abonné.</span><span class="sxs-lookup"><span data-stu-id="9cd66-125">However, you must ensure that the data is partitioned in such a way that a row cannot be replicated to more than one Subscriber.</span></span> <span data-ttu-id="9cd66-126">Pour plus d'informations, consultez la section « Définition de « partition options » » dans la rubrique [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="9cd66-126">For more information, see the section "Setting 'partition options'" in the topic [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="9cd66-127">Le filtre que vous spécifiez est ensuite analysé et exécuté sur la table indiquée dans la clause SELECT.</span><span class="sxs-lookup"><span data-stu-id="9cd66-127">The filter you specified is parsed and run against the table in the SELECT clause.</span></span> <span data-ttu-id="9cd66-128">Si l'instruction de filtrage contient des erreurs de syntaxe ou d'autres erreurs, vous recevrez un message et pourrez modifier l'instruction de filtrage.</span><span class="sxs-lookup"><span data-stu-id="9cd66-128">If the filter statement contains syntax errors or other problems, you will be notified and will be able to edit the filter statement.</span></span>  
  
     <span data-ttu-id="9cd66-129">Une fois l'instruction analysée, la réplication crée les filtres de jointure nécessaires et les affiche dans le volet **Tables filtrées** sur la page **Filtrer les lignes de la table** ou **Filtrer les lignes** .</span><span class="sxs-lookup"><span data-stu-id="9cd66-129">After the statement is parsed, replication creates the necessary join filters and displays them in the **Filtered Tables** pane on the **Filter Table Rows** or **Filter Rows** page.</span></span> <span data-ttu-id="9cd66-130">Si vous générez des filtres à partir de l'Assistant Nouvelle publication et n'avez pas encore configuré le serveur de distribution pour le serveur de publication sur lequel cet Assistant est exécuté, il vous est demandé de le configurer.</span><span class="sxs-lookup"><span data-stu-id="9cd66-130">If you are generating filters from the New Publication Wizard and have not yet configured the Distributor for the Publisher against which this wizard is running, you are prompted to configure it.</span></span>  
  
4.  <span data-ttu-id="9cd66-131">Si vous êtes dans la boîte de dialogue **Propriétés de la publication - \<Publication>** , cliquez sur **OK** pour enregistrer et fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="9cd66-131">If you are in the **Publication Properties - \<Publication>** dialog box, click **OK** to save and close the dialog box.</span></span>  
  
### <a name="to-modify-a-filter-that-was-automatically-generated"></a><span data-ttu-id="9cd66-132">Pour modifier un filtre généré automatiquement</span><span class="sxs-lookup"><span data-stu-id="9cd66-132">To modify a filter that was automatically generated</span></span>  
  
1.  <span data-ttu-id="9cd66-133">Dans la page **Filtrer les lignes de la table** de l’Assistant Nouvelle publication ou dans la page **Filtrer les lignes** de la boîte de dialogue **Propriétés de la publication - \<Publication>** , sélectionnez un filtre dans le volet **Tables filtrées**, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="9cd66-133">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, select a filter in the **Filtered Tables** pane, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="9cd66-134">Modifiez le filtre dans la boîte de dialogue **Modifier le filtre** ou **Modifier une jointure** .</span><span class="sxs-lookup"><span data-stu-id="9cd66-134">In the **Edit Filter** or **Edit Join** dialog box, modify the filter.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-filter-that-was-automatically-generated"></a><span data-ttu-id="9cd66-135">Pour supprimer un filtre généré automatiquement</span><span class="sxs-lookup"><span data-stu-id="9cd66-135">To delete a filter that was automatically generated</span></span>  
  
1.  <span data-ttu-id="9cd66-136">Dans la page **Filtrer les lignes de la table** de l’Assistant Nouvelle publication ou dans la page **Filtrer les lignes** de la boîte de dialogue **Propriétés de la publication - \<Publication>** , sélectionnez un filtre dans le volet **Tables filtrées**, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="9cd66-136">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, select a filter in the **Filtered Tables** pane, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cd66-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9cd66-137">See Also</span></span>  
 <span data-ttu-id="9cd66-138">[Filtres de jointure](../merge/join-filters.md) </span><span class="sxs-lookup"><span data-stu-id="9cd66-138">[Join Filters](../merge/join-filters.md) </span></span>  
 [<span data-ttu-id="9cd66-139">Filtres de lignes paramétrés</span><span class="sxs-lookup"><span data-stu-id="9cd66-139">Parameterized Row Filters</span></span>](../merge/parameterized-filters-parameterized-row-filters.md)  
  
  
