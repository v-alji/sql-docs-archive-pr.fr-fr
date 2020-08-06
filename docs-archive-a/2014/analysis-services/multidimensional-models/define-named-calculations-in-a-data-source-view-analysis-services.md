---
title: Définir des calculs nommés dans une vue de source de données (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying named calculations
- data source views [Analysis Services], named calculations
- named calculations [Analysis Services]
ms.assetid: 729e7b12-6185-4b73-8bcb-cfe459b15355
author: minewiskan
ms.author: owend
ms.openlocfilehash: ae901c340fe29c042430d928a4abaea8e8cfe84b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605829"
---
# <a name="define-named-calculations-in-a-data-source-view-analysis-services"></a><span data-ttu-id="1fef7-102">Définir des calculs nommés dans une vue de source de données (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="1fef7-102">Define Named Calculations in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="1fef7-103">Un calcul nommé est une expression SQL représentée sous la forme d'une colonne calculée.</span><span class="sxs-lookup"><span data-stu-id="1fef7-103">A named calculation is a SQL expression represented as a calculated column.</span></span> <span data-ttu-id="1fef7-104">Cette expression apparaît et se comporte comme une colonne dans la table.</span><span class="sxs-lookup"><span data-stu-id="1fef7-104">This expression appears and behaves as a column in the table.</span></span> <span data-ttu-id="1fef7-105">Un calcul nommé vous permet d'étendre le schéma relationnel des tables ou vues existantes dans une vue de source de données sans modifier les tables ou vues dans la source de données sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="1fef7-105">A named calculation lets you extend the relational schema of existing tables or views in a data source view without modifying the tables or views in the underlying data source.</span></span> <span data-ttu-id="1fef7-106">Voici quelques exemples :</span><span class="sxs-lookup"><span data-stu-id="1fef7-106">Consider the following examples:</span></span>

-   <span data-ttu-id="1fef7-107">Créez un seul calcul nommé dérivé de plusieurs colonnes dans une table de faits (par exemple, en créant le montant des taxes en multipliant un taux de taxe par un prix de vente).</span><span class="sxs-lookup"><span data-stu-id="1fef7-107">Create a single named calculation that is derived from multiple columns in a fact table (for example, creating Tax Amount by multiplying a tax rate by a sales price).</span></span>

-   <span data-ttu-id="1fef7-108">Construisez un nom convivial pour un membre de dimension.</span><span class="sxs-lookup"><span data-stu-id="1fef7-108">Construct a user friendly name for a dimension member.</span></span>

-   <span data-ttu-id="1fef7-109">À titre d'amélioration des performances des requêtes, créez un calcul nommé dans la vue DSV au lieu de créer un membre calculé dans un cube.</span><span class="sxs-lookup"><span data-stu-id="1fef7-109">As a query performance enhancement, create a named calculation in the DSV instead of creating a calculated member in a cube.</span></span> <span data-ttu-id="1fef7-110">Les calculs nommés sont calculés pendant le traitement alors que les membres calculés sont calculés lors de l'exécution de la requête.</span><span class="sxs-lookup"><span data-stu-id="1fef7-110">Named calculations are calculated during processing whereas calculated members are calculated at query time.</span></span>

## <a name="creating-named-calculations"></a><span data-ttu-id="1fef7-111">Création de calculs nommés</span><span class="sxs-lookup"><span data-stu-id="1fef7-111">Creating Named Calculations</span></span>

> [!NOTE]
>  <span data-ttu-id="1fef7-112">Vous ne pouvez pas ajouter un calcul nommé dans une requête nommée, ni baser une requête nommée sur une table contenant un calcul nommé.</span><span class="sxs-lookup"><span data-stu-id="1fef7-112">You cannot add a named calculation to a named query, nor can you base a named query on a table that contains a named calculation.</span></span>

 <span data-ttu-id="1fef7-113">Lorsque vous créez un calcul nommé, vous spécifiez un nom, l'expression SQL et éventuellement une description du calcul.</span><span class="sxs-lookup"><span data-stu-id="1fef7-113">When you create a named calculation, you specify a name, the SQL expression, and, optionally, a description of the calculation.</span></span> <span data-ttu-id="1fef7-114">L'expression SQL peut faire référence à d'autres tables dans la vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="1fef7-114">The SQL expression can refer to other tables in the data source view.</span></span> <span data-ttu-id="1fef7-115">Une fois le calcul nommé défini, l'expression contenue dans le calcul nommé est envoyée au fournisseur de la source de données et validée comme l'instruction SQL suivante dans laquelle `<Expression>` contient l'expression qui définit le calcul nommé.</span><span class="sxs-lookup"><span data-stu-id="1fef7-115">After the named calculation is defined, the expression in a named calculation is sent to the provider for the data source and validated as the following SQL statement in which `<Expression>` contains the expression that defines the named calculation.</span></span>

```
SELECT 
   <Table Name in Data Source>.*, 
   <Expression> AS <Column Name> 
FROM 
   <Table Name in Data Source> AS <Table Name in Data Source View>
```

 <span data-ttu-id="1fef7-116">Le type de données de la colonne est déterminé par le type de données de la valeur scalaire retournée par l'expression.</span><span class="sxs-lookup"><span data-stu-id="1fef7-116">The data type of the column is determined by the data type of the scalar value returned by the expression.</span></span> <span data-ttu-id="1fef7-117">Si le fournisseur ne trouve pas d'erreur dans l'expression, la colonne est ajoutée dans la table.</span><span class="sxs-lookup"><span data-stu-id="1fef7-117">If the provider does not find any errors in the expression, the column is added to the table.</span></span>

 <span data-ttu-id="1fef7-118">Les colonnes référencées dans l'expression ne doivent pas être qualifiées ou doivent être qualifiées par le nom de table uniquement.</span><span class="sxs-lookup"><span data-stu-id="1fef7-118">Columns referenced in the expression should not be qualified or should be qualified by the table name only.</span></span> <span data-ttu-id="1fef7-119">Par exemple, pour faire référence à la colonne SaleAmount dans une table, `SaleAmount` ou `Sales.SaleAmount` est valide, mais `dbo.Sales.SaleAmount` génère une erreur.</span><span class="sxs-lookup"><span data-stu-id="1fef7-119">For example, to refer to the SaleAmount column in a table, `SaleAmount` or `Sales.SaleAmount` is valid, but `dbo.Sales.SaleAmount` generates an error.</span></span>

 <span data-ttu-id="1fef7-120">L'expression n'est pas automatiquement placée entre parenthèses.</span><span class="sxs-lookup"><span data-stu-id="1fef7-120">The expression is not automatically enclosed between parentheses.</span></span> <span data-ttu-id="1fef7-121">Par conséquent, si une expression, telle qu’une instruction SELECT, nécessite des parenthèses, vous devez les taper dans la zone **Expression** .</span><span class="sxs-lookup"><span data-stu-id="1fef7-121">Therefore, if an expression, such as a SELECT statement, requires parentheses, you must type the parentheses in the **Expression** box.</span></span> <span data-ttu-id="1fef7-122">Par exemple, l'expression ci-dessous est valide uniquement si vous tapez les parenthèses.</span><span class="sxs-lookup"><span data-stu-id="1fef7-122">For example, the following expression is valid only if you type the parentheses.</span></span>

```
(SELECT Description FROM Categories WHERE Categories.CategoryID = CategoryID)
```

## <a name="add-or-edit-a-named-calculation"></a><span data-ttu-id="1fef7-123">Ajouter ou modifier un calcul nommé</span><span class="sxs-lookup"><span data-stu-id="1fef7-123">Add or Edit a Named Calculation</span></span>

1.  <span data-ttu-id="1fef7-124">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le projet ou connectez-vous à la base de données qui contient la vue de source de données dans laquelle vous souhaitez définir un calcul nommé.</span><span class="sxs-lookup"><span data-stu-id="1fef7-124">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you wish to define a named calculation.</span></span>

2.  <span data-ttu-id="1fef7-125">Dans l’Explorateur de solutions, développez le dossier **Vues des sources de données** , puis double-cliquez sur la vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="1fef7-125">In Solution Explorer, expand the **Data Source Views** folder, then double-click the data source view.</span></span>

3.  <span data-ttu-id="1fef7-126">Cliquez avec le bouton droit sur la table dans laquelle vous voulez définir le calcul nommé dans le volet **Tables** ou **Diagramme** , puis cliquez sur **Nouveau calcul nommé**.</span><span class="sxs-lookup"><span data-stu-id="1fef7-126">Right-click the table in which you wish to define the named calculation in either the **Tables** or the **Diagram** pane, and then click **New Named Calculation**.</span></span> <span data-ttu-id="1fef7-127">Veillez à cliquer avec le bouton droit sur le nom de la table, et non sur un attribut.</span><span class="sxs-lookup"><span data-stu-id="1fef7-127">Be sure to right-click on the table name, and not on an attribute.</span></span> <span data-ttu-id="1fef7-128">Le menu doit ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="1fef7-128">The menu should look like the following:</span></span>

     <span data-ttu-id="1fef7-129">![Capture d'écran du menu contextuel de l'espace de travail du diagramme](../media/ssas-olapdsv-diagram.gif "Capture d'écran du menu contextuel de l'espace de travail du diagramme")</span><span class="sxs-lookup"><span data-stu-id="1fef7-129">![Screenshot of diagram workspace, right-click menu](../media/ssas-olapdsv-diagram.gif "Screenshot of diagram workspace, right-click menu")</span></span>

    > [!NOTE]
    >  <span data-ttu-id="1fef7-130">Pour rechercher une table ou une vue, vous pouvez utiliser l’option **Rechercher une table** en cliquant sur le menu **Vue de source de données** ou en cliquant avec le bouton droit dans une zone ouverte du volet **Tables** ou **Diagramme** .</span><span class="sxs-lookup"><span data-stu-id="1fef7-130">To locate a table or view, you can use the **Find Table** option by either clicking the **Data Source View** menu or right-clicking in an open area of the **Tables** or **Diagram** panes.</span></span>

4.  <span data-ttu-id="1fef7-131">Dans la boîte de dialogue **Créer un calcul nommé** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="1fef7-131">In the **Create Named Calculations** dialog box, do the following:</span></span>

    -   <span data-ttu-id="1fef7-132">Dans la zone de texte **Nom de la colonne** , tapez le nom de la nouvelle colonne.</span><span class="sxs-lookup"><span data-stu-id="1fef7-132">In the **Column name** text box, type the name of the new column.</span></span>

    -   <span data-ttu-id="1fef7-133">Dans la zone de texte **Description** , tapez la description de la nouvelle colonne.</span><span class="sxs-lookup"><span data-stu-id="1fef7-133">In the **Description** text box type a description for the new column.</span></span>

    -   <span data-ttu-id="1fef7-134">Dans la zone de texte **Expression** , tapez l’expression qui génère le contenu de la nouvelle colonne dans le dialecte SQL approprié pour le fournisseur de données.</span><span class="sxs-lookup"><span data-stu-id="1fef7-134">In the **Expression** text box, type the expression that yields the content of the new column in the SQL dialect appropriate for the data provider.</span></span>

5.  <span data-ttu-id="1fef7-135">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1fef7-135">Click **OK**.</span></span>

     <span data-ttu-id="1fef7-136">La colonne du calcul nommé est la dernière colonne dans la table de la vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="1fef7-136">The named calculation column appears as the last column in the data source view table.</span></span> <span data-ttu-id="1fef7-137">Un symbole de calculateur indique que la colonne contient un calcul nommé.</span><span class="sxs-lookup"><span data-stu-id="1fef7-137">A calculator symbol indicates that the column contains a named calculation.</span></span>

## <a name="delete-a-named-calculation"></a><span data-ttu-id="1fef7-138">Supprimer un calcul nommé</span><span class="sxs-lookup"><span data-stu-id="1fef7-138">Delete a Named Calculation</span></span>
 <span data-ttu-id="1fef7-139">Lorsque vous supprimez un calcul nommé, la liste des objets définis dans le projet ou la base de données et qui ne seront plus valides après la suppression s'affichent.</span><span class="sxs-lookup"><span data-stu-id="1fef7-139">When you attempt to delete a named calculation, you are prompted with a list of the objects defined in the project or database that will be invalidated by the deletion.</span></span> <span data-ttu-id="1fef7-140">Examinez la liste soigneusement avant de supprimer le calcul.</span><span class="sxs-lookup"><span data-stu-id="1fef7-140">Review the list carefully before deleting the calculation.</span></span>

## <a name="see-also"></a><span data-ttu-id="1fef7-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1fef7-141">See Also</span></span>
 [<span data-ttu-id="1fef7-142">Définir des requêtes nommées dans une vue de source de données &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1fef7-142">Define Named Queries in a Data Source View &#40;Analysis Services&#41;</span></span>](define-named-queries-in-a-data-source-view-analysis-services.md)


