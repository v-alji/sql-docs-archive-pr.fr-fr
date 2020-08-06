---
title: Définir des relations logiques dans une vue de source de données (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- adding relationships
- relationships [Analysis Services], data source views
- data source views [Analysis Services], relationships
ms.assetid: a20d6dae-e769-4131-8a59-7ef56f174220
author: minewiskan
ms.author: owend
ms.openlocfilehash: c46c2b360a4528aeb0eb88348d0d1242b22d8ef5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605834"
---
# <a name="define-logical-relationships-in-a-data-source-view-analysis-services"></a><span data-ttu-id="8522a-102">Définir des relations logiques dans une vue de source de données (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="8522a-102">Define Logical Relationships in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="8522a-103">L'Assistant Vue de source de données et le Concepteur de vue de source de données définissent automatiquement les relations entre les tables ajoutées à une vue de source de données (DSV), en fonction des relations de la base de données sous-jacente ou des critères de correspondance de noms que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="8522a-103">The Data Source View Wizard and Data Source View Designer automatically define relationships between tables added to a data source view (DSV) based on underlying database relationships or name matching criteria you specify.</span></span>  
  
 <span data-ttu-id="8522a-104">Dans les cas où vous utilisez des données de plusieurs sources de données, vous devrez peut-être définir manuellement des relations logiques dans la vue DSV afin de compléter ces relations définies automatiquement.</span><span class="sxs-lookup"><span data-stu-id="8522a-104">In cases where you are working with data from multiple data sources, you may need to manually define logical relationships in the DSV to supplement those relationships that are defined automatically.</span></span> <span data-ttu-id="8522a-105">Des relations sont requises dans [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] pour identifier les tables de faits et de dimension, pour créer des requêtes pour la récupération de données et de métadonnées à partir de sources de données sous-jacentes, et pour tirer parti des fonctionnalités Business Intelligence avancées.</span><span class="sxs-lookup"><span data-stu-id="8522a-105">Relationships are required in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to identify fact and dimension tables, to construct queries for retrieving data and metadata from underlying data sources, and to take advantage of advanced business intelligence features.</span></span>  
  
 <span data-ttu-id="8522a-106">Vous pouvez définir les types de relations suivants dans le Concepteur de vue de source de données :</span><span class="sxs-lookup"><span data-stu-id="8522a-106">You can define the following types of relationships in Data Source View Designer:</span></span>  
  
-   <span data-ttu-id="8522a-107">Une relation d'une table à une autre table dans la même source de données.</span><span class="sxs-lookup"><span data-stu-id="8522a-107">A relationship from one table to another table in the same data source.</span></span>  
  
-   <span data-ttu-id="8522a-108">Une relation d'une table à elle-même, comme dans une relation parent-enfant.</span><span class="sxs-lookup"><span data-stu-id="8522a-108">A relationship from one table to itself, as in a parent-child relationship.</span></span>  
  
-   <span data-ttu-id="8522a-109">Une relation d'une table dans une source de données à une autre table dans une autre source de données.</span><span class="sxs-lookup"><span data-stu-id="8522a-109">A relationship from one table in a data source to another table in a different data source.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8522a-110">Les relations définies dans une vue DSV sont logiques et peuvent ne pas refléter les relations réelles définies dans la source de données sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="8522a-110">The relationships defined in a DSV are logical and may not reflect the actual relationships defined in the underlying data source.</span></span> <span data-ttu-id="8522a-111">Vous pouvez créer des relations dans le Concepteur de vues de source de données, qui n'existent pas dans la source de données sous-jacente, et supprimer des relations créées par le Concepteur de vues de source de données à partir de relations de clé étrangère existantes dans la source de données sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="8522a-111">You can create relationships in Data Source View Designer that do not exist in the underlying data source, and remove relationships created by Data Source View Designer from existing foreign key relationships in the underlying data source.</span></span>  
  
 <span data-ttu-id="8522a-112">Les relations sont dirigées.</span><span class="sxs-lookup"><span data-stu-id="8522a-112">Relationships are directed.</span></span> <span data-ttu-id="8522a-113">Pour chaque valeur dans la colonne source, il existe une valeur correspondante dans la colonne de destination.</span><span class="sxs-lookup"><span data-stu-id="8522a-113">For every value in the source column, there is a corresponding value in the destination column.</span></span> <span data-ttu-id="8522a-114">Dans un diagramme de vue de source de données, tel que les diagrammes affichés dans le volet **Diagramme** , une flèche placée sur la ligne entre deux tables indique le sens de la relation.</span><span class="sxs-lookup"><span data-stu-id="8522a-114">In a data source view diagram, such as the diagrams displayed in the **Diagram** pane, an arrow on the line between two tables indicates the direction of the relationship.</span></span>  
  
 <span data-ttu-id="8522a-115">Cette rubrique contient les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="8522a-115">This topic includes the following sections:</span></span>  
  
 [<span data-ttu-id="8522a-116">Pour ajouter une relation entre des tables, des requêtes nommées ou des vues</span><span class="sxs-lookup"><span data-stu-id="8522a-116">To add a relationship between tables, named queries, or views</span></span>](#bkmk_addRel)  
  
 [<span data-ttu-id="8522a-117">Pour afficher ou modifier une relation dans le volet Diagramme</span><span class="sxs-lookup"><span data-stu-id="8522a-117">To view or modify a relationship in the Diagram pane</span></span>](#bkmk_diagrampane)  
  
 [<span data-ttu-id="8522a-118">Pour afficher ou modifier une relation dans le volet Tables</span><span class="sxs-lookup"><span data-stu-id="8522a-118">To view or modify a relationship in the Tables pane</span></span>](#bkmk_tablespane)  
  
##  <a name="to-add-a-relationship-between-tables-named-queries-or-views"></a><a name="bkmk_addRel"></a><span data-ttu-id="8522a-119">Pour ajouter une relation entre des tables, des requêtes nommées ou des vues</span><span class="sxs-lookup"><span data-stu-id="8522a-119">To add a relationship between tables, named queries, or views</span></span>  
  
1.  <span data-ttu-id="8522a-120">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le projet ou connectez-vous à la base de données qui contient la vue de source de données dans laquelle vous souhaitez ajouter une relation logique.</span><span class="sxs-lookup"><span data-stu-id="8522a-120">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you wish to add a logical relationship.</span></span>  
  
2.  <span data-ttu-id="8522a-121">Dans l’Explorateur de solutions, développez le dossier **Vues des sources de données** , puis double-cliquez sur la vue de source de données afin de l’ouvrir dans le **Concepteur de vue de source de données**.</span><span class="sxs-lookup"><span data-stu-id="8522a-121">In Solution Explorer, expand the **Data Source Views** folder, then double-click the data source view to open it in **Data Source View Designer**.</span></span>  
  
3.  <span data-ttu-id="8522a-122">Cliquez avec le bouton droit sur la table, la requête nommée ou la vue à laquelle vous voulez ajouter une relation dans le volet **Tables** , puis sélectionnez **Nouvelle relation**.</span><span class="sxs-lookup"><span data-stu-id="8522a-122">Right-click the table, named query or view to which you want to add a relationship in either the **Tables** pane and then click **New Relationship**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8522a-123">Pour rechercher une table, une vue ou une requête nommée, vous pouvez utiliser l’option **Rechercher une table** en cliquant sur le menu **Vue de source de données** ou en cliquant avec le bouton droit dans une zone ouverte du volet **Tables** ou **Diagramme** .</span><span class="sxs-lookup"><span data-stu-id="8522a-123">To locate a table, view or named query, you can use the **Find Table** option by either clicking the **Data Source View** menu or right-clicking in an open area of the **Tables** or **Diagram** panes.</span></span>  
  
4.  <span data-ttu-id="8522a-124">Dans la boîte de dialogue **Spécifier la relation** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="8522a-124">In the **Specify Relationship** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="8522a-125">Sélectionnez la table, la requête nommée ou la vue appropriée dans la liste **Table source (clé étrangère)** .</span><span class="sxs-lookup"><span data-stu-id="8522a-125">Select the appropriate table, named query, or view in the **Source (foreign key) table** list.</span></span>  
  
    2.  <span data-ttu-id="8522a-126">Sélectionnez la table, la requête nommée ou la vue appropriée dans la liste **Table de destination (clé primaire)** .</span><span class="sxs-lookup"><span data-stu-id="8522a-126">Select the appropriate table, named query, or view in the **Destination (primary key) table** lists.</span></span>  
  
    3.  <span data-ttu-id="8522a-127">Sélectionnez des colonnes dans les listes **Colonnes sources** et **Colonnes de destination** pour créer une relation entre les deux tables.</span><span class="sxs-lookup"><span data-stu-id="8522a-127">Select columns from the **Source Columns** and **Destination Columns** lists to create a relationship between the two tables.</span></span>  
  
         <span data-ttu-id="8522a-128">Si [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] détecte, pendant l’échantillonnage des données dans la requête nommée, la vue ou la table sous-jacente, que vous avez défini la relation dans une direction incorrecte (de la clé primaire vers la clé étrangère plutôt que l’inverse), vous êtes invité à en inverser le sens.</span><span class="sxs-lookup"><span data-stu-id="8522a-128">If [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] detects, by sampling the data in the underlying table, view, or named query, that you have defined the relationship in the wrong direction (from the primary key to the foreign key rather than from the foreign key to the primary key), you will be prompted to reverse the order.</span></span> <span data-ttu-id="8522a-129">Pour inverser rapidement le sens, cliquez sur **Inverser**.</span><span class="sxs-lookup"><span data-stu-id="8522a-129">To quickly reverse the order, click **Reverse**.</span></span>  
  
         <span data-ttu-id="8522a-130">Si [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] détecte qu’une relation existe déjà pour les colonnes sélectionnées, vous recevez un message.</span><span class="sxs-lookup"><span data-stu-id="8522a-130">If [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] detects that a relationship already exists for the columns you have selected, you will be prompted.</span></span> <span data-ttu-id="8522a-131">Vous ne pouvez pas définir des relations en double.</span><span class="sxs-lookup"><span data-stu-id="8522a-131">You cannot define duplicate relationships.</span></span>  
  
    4.  <span data-ttu-id="8522a-132">Si vous le souhaitez, dans la zone **Description** , tapez la description de la relation.</span><span class="sxs-lookup"><span data-stu-id="8522a-132">Optionally, in the **Description** box, type a description for the relationship.</span></span>  
  
##  <a name="to-view-or-modify-a-relationship-in-the-diagram-pane"></a><a name="bkmk_diagrampane"></a><span data-ttu-id="8522a-133">Pour afficher ou modifier une relation dans le volet Diagramme</span><span class="sxs-lookup"><span data-stu-id="8522a-133">To view or modify a relationship in the Diagram pane</span></span>  
  
-   <span data-ttu-id="8522a-134">Dans le volet **Diagramme** , dans **Concepteur de vue de source de données**, cliquez avec le bouton droit sur la relation que vous souhaitez afficher, puis sélectionnez **Modifier la relation** (ou double-cliquez simplement sur la flèche représentant la relation).</span><span class="sxs-lookup"><span data-stu-id="8522a-134">In the **Diagram** pane in **Data Source View Designer**, right-click the relationship that you want to view and click **Edit Relationship** (or simply double-click the relationship arrow).</span></span>  <span data-ttu-id="8522a-135">Utilisez la boîte de dialogue **Modifier la relation** pour modifier la relation.</span><span class="sxs-lookup"><span data-stu-id="8522a-135">Use the **Edit Relationship** dialog box to modify the relationship.</span></span>  
  
##  <a name="to-view-or-modify-a-relationship-in-the-tables-pane"></a><a name="bkmk_tablespane"></a><span data-ttu-id="8522a-136">Pour afficher ou modifier une relation dans le volet Tables</span><span class="sxs-lookup"><span data-stu-id="8522a-136">To view or modify a relationship in the Tables pane</span></span>  
  
1.  <span data-ttu-id="8522a-137">Dans le volet **Tables** dans **Concepteur de vue de source de données**, développez la table, la vue ou la requête nommée contenant la relation que vous souhaitez afficher ou modifier.</span><span class="sxs-lookup"><span data-stu-id="8522a-137">In the **Tables** pane in **Data Source View Designer**, locate and then expand the table, view or named query containing the relationship that you wish to view or modify.</span></span>  
  
2.  <span data-ttu-id="8522a-138">Développez le dossier **Relations** .</span><span class="sxs-lookup"><span data-stu-id="8522a-138">Expand the **Relationships** folder.</span></span>  <span data-ttu-id="8522a-139">Les relations entre la table, la vue ou la requête nommée sélectionnée et les autres tables, vues ou requêtes nommées s'affichent dans la colonne des relations.</span><span class="sxs-lookup"><span data-stu-id="8522a-139">The relationships between the selected table, view or named query and other tables, views and named queries appear with the relationship column listed.</span></span>  
  
3.  <span data-ttu-id="8522a-140">Cliquez avec le bouton droit sur la relation que vous souhaitez modifier, puis sélectionnez **Modifier la relation**.</span><span class="sxs-lookup"><span data-stu-id="8522a-140">Right-click the relationship you want to modify, and then click **Edit Relationship**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8522a-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8522a-141">See Also</span></span>  
 [<span data-ttu-id="8522a-142">Vues de sources de données dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="8522a-142">Data Source Views in Multidimensional Models</span></span>](data-source-views-in-multidimensional-models.md)  
  
  
