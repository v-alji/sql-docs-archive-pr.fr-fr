---
title: Tableau croisé dynamique, transformation | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.pivottrans.f1
helpviewer_keywords:
- Pivot transformation
- normalized data [Integration Services]
- PivotUsage property
- datasets [Integration Services], normalized data
- less normalized data set [Integration Services]
ms.assetid: 55f5db6e-6777-435f-8a06-b68c129f8437
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 43bdc5be709ea00d4be4601f52c38e96fe3f1ce4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710771"
---
# <a name="pivot-transformation"></a><span data-ttu-id="d7e44-102">transformation de tableau croisé dynamique</span><span class="sxs-lookup"><span data-stu-id="d7e44-102">Pivot Transformation</span></span>
  <span data-ttu-id="d7e44-103">La transformation de tableau croisé dynamique transforme un dataset normalisé en une version moins normalisée mais plus compacte en croisant dynamiquement les données d'entrée sur une valeur de colonne.</span><span class="sxs-lookup"><span data-stu-id="d7e44-103">The Pivot transformation makes a normalized data set into a less normalized but more compact version by pivoting the input data on a column value.</span></span> <span data-ttu-id="d7e44-104">Par exemple, un dataset **Commandes** normalisé comprenant le nom de client, le produit et la quantité achetée contient généralement plusieurs lignes pour un même client ayant acheté plusieurs produits ; chaque ligne indiquant les détails de commande d’un produit différent.</span><span class="sxs-lookup"><span data-stu-id="d7e44-104">For example, a normalized **Orders** data set that lists customer name, product, and quantity purchased typically has multiple rows for any customer who purchased multiple products, with each row for that customer showing order details for a different product.</span></span> <span data-ttu-id="d7e44-105">En croisant dynamiquement le dataset sur la colonne de produit, la transformation de tableau croisé dynamique peut sortir un dataset contenant une seule ligne par client.</span><span class="sxs-lookup"><span data-stu-id="d7e44-105">By pivoting the data set on the product column, the Pivot transformation can output a data set with a single row per customer.</span></span> <span data-ttu-id="d7e44-106">Cette ligne unique indique tous les achats du client ; le nom des produits est indiqué sous forme de nom de colonne et la quantité sous forme de valeur de la colonne de produit.</span><span class="sxs-lookup"><span data-stu-id="d7e44-106">That single row lists all the purchases by the customer, with the product names shown as column names, and the quantity shown as a value in the product column.</span></span> <span data-ttu-id="d7e44-107">Dans la mesure où tous les clients n'achètent pas chacun des produits, de nombreuses colonnes peuvent contenir des valeurs null.</span><span class="sxs-lookup"><span data-stu-id="d7e44-107">Because not every customer purchases every product, many columns may contain null values.</span></span>  
  
 <span data-ttu-id="d7e44-108">Lorsqu'un dataset est croisé dynamiquement, les colonnes d'entrée jouent des rôles différents dans le processus de croisement dynamique.</span><span class="sxs-lookup"><span data-stu-id="d7e44-108">When a dataset is pivoted, input columns perform different roles in the pivoting process.</span></span> <span data-ttu-id="d7e44-109">Une colonne peut jouer les rôles suivants :</span><span class="sxs-lookup"><span data-stu-id="d7e44-109">A column can participate in the following ways:</span></span>  
  
-   <span data-ttu-id="d7e44-110">La colonne est transmise à la sortie sans subir aucune modification.</span><span class="sxs-lookup"><span data-stu-id="d7e44-110">The column is passed through unchanged to the output.</span></span> <span data-ttu-id="d7e44-111">De nombreuses lignes d'entrées pouvant se traduire par une seule ligne de sortie, la transformation copie uniquement la première valeur d'entrée de la colonne.</span><span class="sxs-lookup"><span data-stu-id="d7e44-111">Because many input rows can result only in one output row, the transformation copies only the first input value for the column.</span></span>  
  
-   <span data-ttu-id="d7e44-112">La colonne joue le rôle de clé ou de partie de la clé qui identifie un ensemble d'enregistrements.</span><span class="sxs-lookup"><span data-stu-id="d7e44-112">The column acts as the key or part of the key that identifies a set of records.</span></span>  
  
-   <span data-ttu-id="d7e44-113">La colonne définit le tableau croisé dynamique.</span><span class="sxs-lookup"><span data-stu-id="d7e44-113">The column defines the pivot.</span></span> <span data-ttu-id="d7e44-114">Les valeurs de cette colonne sont associées aux colonnes du dataset croisé dynamiquement.</span><span class="sxs-lookup"><span data-stu-id="d7e44-114">The values in this column are associated with columns in the pivoted dataset.</span></span>  
  
-   <span data-ttu-id="d7e44-115">La colonne contient des valeurs qui sont placées dans les colonnes créées par le tableau croisé dynamique.</span><span class="sxs-lookup"><span data-stu-id="d7e44-115">The column contains values that are placed in the columns that the pivot creates.</span></span>  
  
 <span data-ttu-id="d7e44-116">Cette transformation a une entrée, une sortie standard et une sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="d7e44-116">This transformation has one input, one regular output, and one error output.</span></span>  
  
## <a name="sort-and-duplicate-rows"></a><span data-ttu-id="d7e44-117">Trier et dupliquer les lignes</span><span class="sxs-lookup"><span data-stu-id="d7e44-117">Sort and Duplicate Rows</span></span>  
 <span data-ttu-id="d7e44-118">Pour une plus grande efficacité du croisement dynamique des données, autrement dit pour créer aussi peu d'enregistrements dans le dataset de sortie que possible, les données d'entrée doivent être triées sur la colonne tableau croisé dynamique.</span><span class="sxs-lookup"><span data-stu-id="d7e44-118">To pivot data efficiently, which means creating as few records in the output dataset as possible, the input data must be sorted on the pivot column.</span></span> <span data-ttu-id="d7e44-119">Si les données ne sont pas triées, la transformation de tableau croisé dynamique risque de générer plusieurs enregistrements pour chaque valeur de la clé d'ensemble, qui est la colonne définissant l'appartenance à l'ensemble.</span><span class="sxs-lookup"><span data-stu-id="d7e44-119">If the data is not sorted, the Pivot transformation might generate multiple records for each value in the set key, which is the column that defines set membership.</span></span> <span data-ttu-id="d7e44-120">Par exemple, si un dataset est croisé dynamiquement sur une colonne **Nom** , mais que les noms ne sont pas triés, le dataset de sortie risque de contenir plus d’une ligne pour chaque client car un croisement dynamique est effectué chaque fois que la valeur de la colonne **Nom** change.</span><span class="sxs-lookup"><span data-stu-id="d7e44-120">For example, if a dataset is pivoted on a **Name** column but the names are not sorted, the output dataset could have more than one row for each customer, because a pivot occurs every time that the value in **Name** changes.</span></span>  
  
 <span data-ttu-id="d7e44-121">Les données d'entrée peuvent contenir des lignes en double, ce qui entraîne l'échec de la transformation de tableau croisé dynamique.</span><span class="sxs-lookup"><span data-stu-id="d7e44-121">The input data might contain duplicate rows, which will cause the Pivot transformation to fail.</span></span> <span data-ttu-id="d7e44-122">L'expression « lignes en double » désigne des lignes qui ont les mêmes valeurs dans les colonnes clés d'ensemble et dans les colonnes tableau croisé dynamique.</span><span class="sxs-lookup"><span data-stu-id="d7e44-122">"Duplicate rows" means rows that have the same values in the set key columns and the pivot columns.</span></span> <span data-ttu-id="d7e44-123">Pour éviter cet échec, vous pouvez soit configurer la transformation de manière à rediriger les lignes d'erreur vers une sortie d'erreur, soit préagréger les valeurs de manière à ce qu'il n'y ait pas de lignes en double.</span><span class="sxs-lookup"><span data-stu-id="d7e44-123">To avoid failure, you can either configure the transformation to redirect error rows to an error output or you can pre-aggregate values to ensure there are no duplicate rows.</span></span>  
  
##  <a name="options-in-the-pivot-dialog-box"></a><a name="options"></a> <span data-ttu-id="d7e44-124">Options de la boîte de dialogue Tableau croisé dynamique</span><span class="sxs-lookup"><span data-stu-id="d7e44-124">Options in the Pivot Dialog Box</span></span>  
 <span data-ttu-id="d7e44-125">Configurez l’opération d’ajout de tableau croisé dynamique en définissant les options de la boîte de dialogue **Tableau croisé dynamique** .</span><span class="sxs-lookup"><span data-stu-id="d7e44-125">You configure the pivot operation by setting the options in the **Pivot** dialog box.</span></span> <span data-ttu-id="d7e44-126">Pour ouvrir la boîte de dialogue **Tableau croisé dynamique** , ajoutez la transformation de tableau croisé dynamique au package dans [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], puis cliquez avec le bouton droit sur le composant et cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="d7e44-126">To open the **Pivot** dialog box, add the Pivot transformation to the package in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], and then right-click the component and click **Edit**.</span></span>  
  
 <span data-ttu-id="d7e44-127">La liste suivante décrit les options de la boîte de dialogue **Tableau croisé dynamique** .</span><span class="sxs-lookup"><span data-stu-id="d7e44-127">The following list describes the options in the **Pivot** dialog box.</span></span>  
  
 <span data-ttu-id="d7e44-128">**Clé de tableau croisé dynamique**</span><span class="sxs-lookup"><span data-stu-id="d7e44-128">**Pivot Key**</span></span>  
 <span data-ttu-id="d7e44-129">Spécifie la colonne à utiliser pour les valeurs de la ligne supérieure (ligne d'en-tête) du tableau.</span><span class="sxs-lookup"><span data-stu-id="d7e44-129">Specifies the column to use for values across the top row (header row) of the table.</span></span>  
  
 <span data-ttu-id="d7e44-130">**Définir la clé**</span><span class="sxs-lookup"><span data-stu-id="d7e44-130">**Set Key**</span></span>  
 <span data-ttu-id="d7e44-131">Spécifie la colonne à utiliser pour les valeurs de la colonne gauche du tableau.</span><span class="sxs-lookup"><span data-stu-id="d7e44-131">Specifies the column to use for values in the left column of the table.</span></span> <span data-ttu-id="d7e44-132">La date d'entrée doit être triée sur cette colonne.</span><span class="sxs-lookup"><span data-stu-id="d7e44-132">The input date must be sorted on this column.</span></span>  
  
 <span data-ttu-id="d7e44-133">**Valeur de tableau croisé dynamique**</span><span class="sxs-lookup"><span data-stu-id="d7e44-133">**Pivot Value**</span></span>  
 <span data-ttu-id="d7e44-134">Spécifie la colonne à utiliser pour les valeurs du tableau, à l'exception des valeurs de la ligne d'en-tête et de la colonne gauche.</span><span class="sxs-lookup"><span data-stu-id="d7e44-134">Specifies the column to use for the table values, other than the values in the header row and the left column.</span></span>  
  
 <span data-ttu-id="d7e44-135">**Ignorer les valeurs clés de tableau croisé dynamique sans correspondance et les signaler après l'exécution de DataFlow**</span><span class="sxs-lookup"><span data-stu-id="d7e44-135">**Ignore un-matched Pivot Key values and report them after DataFlow execution**</span></span>  
 <span data-ttu-id="d7e44-136">Sélectionnez cette option pour configurer la transformation de tableau croisé dynamique afin d’ignorer les lignes contenant des valeurs non reconnues dans la colonne **Clé de tableau croisé dynamique** et de générer toutes les valeurs clés de tableau croisé dynamique dans un message de journal, lorsque le package est exécuté.</span><span class="sxs-lookup"><span data-stu-id="d7e44-136">Select this option to configure the Pivot transformation to ignore rows containing unrecognized values in the **Pivot Key** column and to output all of the pivot key values to a log message, when the package is run.</span></span>  
  
 <span data-ttu-id="d7e44-137">Vous pouvez également configurer la transformation pour générer les valeurs en affectant à la propriété personnalisée `PassThroughUnmatchedPivotKeys` la valeur `True`.</span><span class="sxs-lookup"><span data-stu-id="d7e44-137">You can also configure the transformation to output the values by setting the `PassThroughUnmatchedPivotKeys` custom property to `True`.</span></span>  
  
 <span data-ttu-id="d7e44-138">**Générer des colonnes de sortie de tableau croisé dynamique à partir de valeurs**</span><span class="sxs-lookup"><span data-stu-id="d7e44-138">**Generate pivot output columns from values**</span></span>  
 <span data-ttu-id="d7e44-139">Entrez les valeurs clés de tableau croisé dynamique dans cette zone pour permettre à la transformation de tableau croisé dynamique de créer des colonnes de sortie pour chaque valeur.</span><span class="sxs-lookup"><span data-stu-id="d7e44-139">Enter the pivot key values in this box to enable the Pivot transformation to create output columns for each value.</span></span> <span data-ttu-id="d7e44-140">Vous pouvez soit entrer les valeurs avant d'exécuter le package, soit procéder comme suit.</span><span class="sxs-lookup"><span data-stu-id="d7e44-140">You can either enter the values prior to running the package, or do the following.</span></span>  
  
1.  <span data-ttu-id="d7e44-141">Sélectionnez l’option **Ignorer les valeurs clés de tableau croisé dynamique sans correspondance et les signaler après l’exécution de DataFlow** , puis cliquez sur **OK** dans la boîte de dialogue **Tableau croisé dynamique** pour enregistrer les modifications apportées à la transformation de tableau croisé dynamique.</span><span class="sxs-lookup"><span data-stu-id="d7e44-141">Select the **Ignore un-matched Pivot Key values and report them after DataFlow execution** option, and then click **OK** in the **Pivot** dialog box to save the changes to the Pivot transformation.</span></span>  
  
2.  <span data-ttu-id="d7e44-142">Exécutez le package.</span><span class="sxs-lookup"><span data-stu-id="d7e44-142">Run the package.</span></span>  
  
3.  <span data-ttu-id="d7e44-143">Une fois l’exécution du package réussie, cliquez sur l’onglet **Progression** et recherchez le message de journal des informations à partir de la transformation de tableau croisé dynamique qui contient les valeurs clés de tableau croisé dynamique.</span><span class="sxs-lookup"><span data-stu-id="d7e44-143">When the package succeeds, click the **Progress** tab and look for the information log message from the Pivot transformation that contains the pivot key values.</span></span>  
  
4.  <span data-ttu-id="d7e44-144">Cliquez avec le bouton droit sur le message, puis cliquez sur **Copier le texte du message**.</span><span class="sxs-lookup"><span data-stu-id="d7e44-144">Right-click the message and click **Copy Message Text**.</span></span>  
  
5.  <span data-ttu-id="d7e44-145">Cliquez sur **Arrêter le débogage** dans le menu **Débogage** pour basculer en mode design.</span><span class="sxs-lookup"><span data-stu-id="d7e44-145">Click **Stop Debugging** on the **Debug** menu to switch to the design mode.</span></span>  
  
6.  <span data-ttu-id="d7e44-146">Cliquez avec le bouton droit sur la transformation de tableau croisé dynamique, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="d7e44-146">Right-click the Pivot transformation, and then click **Edit**.</span></span>  
  
7.  <span data-ttu-id="d7e44-147">Désactivez l’option **Ignorer les valeurs clés de tableau croisé dynamique sans correspondance et les signaler après l’exécution de DataFlow** , puis collez les valeurs clés de tableau croisé dynamique dans la zone **Générer des colonnes de sortie de tableau croisé dynamique à partir de valeurs** en utilisant le format suivant.</span><span class="sxs-lookup"><span data-stu-id="d7e44-147">Uncheck the **Ignore un-matched Pivot Key values and report them after DataFlow execution** option, and then paste the pivot key values in the **Generate pivot output columns from values** box using the following format.</span></span>  
  
     <span data-ttu-id="d7e44-148">[valeur1],[valeur2],[valeur3]</span><span class="sxs-lookup"><span data-stu-id="d7e44-148">[value1],[value2],[value3]</span></span>  
  
 <span data-ttu-id="d7e44-149">**Générer des colonnes maintenant**</span><span class="sxs-lookup"><span data-stu-id="d7e44-149">**Generate Columns Now**</span></span>  
 <span data-ttu-id="d7e44-150">Cliquez pour créer une colonne de sortie pour chaque valeur clé de tableau croisé dynamique listée dans la zone **Générer des colonnes de sortie de tableau croisé dynamique à partir de valeurs** .</span><span class="sxs-lookup"><span data-stu-id="d7e44-150">Click to create an output column for each pivot key value that is listed in the **Generate pivot output columns from values** box.</span></span>  
  
 <span data-ttu-id="d7e44-151">Les colonnes de sortie apparaissent dans la zone **Colonnes de sorties croisées dynamiquement existantes** .</span><span class="sxs-lookup"><span data-stu-id="d7e44-151">The output columns appear in the **Existing pivoted output columns** box.</span></span>  
  
 <span data-ttu-id="d7e44-152">**Colonnes de sorties croisées dynamiquement existantes**</span><span class="sxs-lookup"><span data-stu-id="d7e44-152">**Existing pivoted output columns**</span></span>  
 <span data-ttu-id="d7e44-153">Liste les colonnes de sortie des valeurs clés de tableau croisé dynamique</span><span class="sxs-lookup"><span data-stu-id="d7e44-153">Lists the output columns for the pivot key values</span></span>  
  
 <span data-ttu-id="d7e44-154">Le tableau suivant illustre un jeu de données avant que les données n’aient été croisées dynamiquement dans la colonne **Year** .</span><span class="sxs-lookup"><span data-stu-id="d7e44-154">The following table shows a data set before the data is pivoted on the **Year** column.</span></span>  
  
|<span data-ttu-id="d7e44-155">Year</span><span class="sxs-lookup"><span data-stu-id="d7e44-155">Year</span></span>|<span data-ttu-id="d7e44-156">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="d7e44-156">Product Name</span></span>|<span data-ttu-id="d7e44-157">Total</span><span class="sxs-lookup"><span data-stu-id="d7e44-157">Total</span></span>|  
|----------|------------------|-----------|  
|<span data-ttu-id="d7e44-158">2004</span><span class="sxs-lookup"><span data-stu-id="d7e44-158">2004</span></span>|<span data-ttu-id="d7e44-159">HL Mountain Tire</span><span class="sxs-lookup"><span data-stu-id="d7e44-159">HL Mountain Tire</span></span>|<span data-ttu-id="d7e44-160">1504884.15</span><span class="sxs-lookup"><span data-stu-id="d7e44-160">1504884.15</span></span>|  
|<span data-ttu-id="d7e44-161">2003</span><span class="sxs-lookup"><span data-stu-id="d7e44-161">2003</span></span>|<span data-ttu-id="d7e44-162">Road Tire Tube</span><span class="sxs-lookup"><span data-stu-id="d7e44-162">Road Tire Tube</span></span>|<span data-ttu-id="d7e44-163">35920.50</span><span class="sxs-lookup"><span data-stu-id="d7e44-163">35920.50</span></span>|  
|<span data-ttu-id="d7e44-164">2004</span><span class="sxs-lookup"><span data-stu-id="d7e44-164">2004</span></span>|<span data-ttu-id="d7e44-165">Water Bottle - 30 oz.</span><span class="sxs-lookup"><span data-stu-id="d7e44-165">Water Bottle - 30 oz.</span></span>|<span data-ttu-id="d7e44-166">2805.00</span><span class="sxs-lookup"><span data-stu-id="d7e44-166">2805.00</span></span>|  
|<span data-ttu-id="d7e44-167">2002</span><span class="sxs-lookup"><span data-stu-id="d7e44-167">2002</span></span>|<span data-ttu-id="d7e44-168">Touring Tire</span><span class="sxs-lookup"><span data-stu-id="d7e44-168">Touring Tire</span></span>|<span data-ttu-id="d7e44-169">62364.225</span><span class="sxs-lookup"><span data-stu-id="d7e44-169">62364.225</span></span>|  
  
 <span data-ttu-id="d7e44-170">Le tableau suivant illustre un jeu de données après que les données ont été croisées dynamiquement dans la colonne **Year** .</span><span class="sxs-lookup"><span data-stu-id="d7e44-170">The following table shows a data set after the data has been pivoted on the **Year** column.</span></span>  
  
||<span data-ttu-id="d7e44-171">2002</span><span class="sxs-lookup"><span data-stu-id="d7e44-171">2002</span></span>|<span data-ttu-id="d7e44-172">2003</span><span class="sxs-lookup"><span data-stu-id="d7e44-172">2003</span></span>|<span data-ttu-id="d7e44-173">2004</span><span class="sxs-lookup"><span data-stu-id="d7e44-173">2004</span></span>|  
|-|----------|----------|----------|  
|<span data-ttu-id="d7e44-174">HL Mountain Tire</span><span class="sxs-lookup"><span data-stu-id="d7e44-174">HL Mountain Tire</span></span>|<span data-ttu-id="d7e44-175">141164.10</span><span class="sxs-lookup"><span data-stu-id="d7e44-175">141164.10</span></span>|<span data-ttu-id="d7e44-176">446297.775</span><span class="sxs-lookup"><span data-stu-id="d7e44-176">446297.775</span></span>|<span data-ttu-id="d7e44-177">1504884.15</span><span class="sxs-lookup"><span data-stu-id="d7e44-177">1504884.15</span></span>|  
|<span data-ttu-id="d7e44-178">Road Tire Tube</span><span class="sxs-lookup"><span data-stu-id="d7e44-178">Road Tire Tube</span></span>|<span data-ttu-id="d7e44-179">3592.05</span><span class="sxs-lookup"><span data-stu-id="d7e44-179">3592.05</span></span>|<span data-ttu-id="d7e44-180">35920.50</span><span class="sxs-lookup"><span data-stu-id="d7e44-180">35920.50</span></span>|<span data-ttu-id="d7e44-181">89801.25</span><span class="sxs-lookup"><span data-stu-id="d7e44-181">89801.25</span></span>|  
|<span data-ttu-id="d7e44-182">Water Bottle - 30 oz.</span><span class="sxs-lookup"><span data-stu-id="d7e44-182">Water Bottle - 30 oz.</span></span>|<span data-ttu-id="d7e44-183">*NULL*</span><span class="sxs-lookup"><span data-stu-id="d7e44-183">*NULL*</span></span>|<span data-ttu-id="d7e44-184">*NULL*</span><span class="sxs-lookup"><span data-stu-id="d7e44-184">*NULL*</span></span>|<span data-ttu-id="d7e44-185">2805.00</span><span class="sxs-lookup"><span data-stu-id="d7e44-185">2805.00</span></span>|  
|<span data-ttu-id="d7e44-186">Touring Tire</span><span class="sxs-lookup"><span data-stu-id="d7e44-186">Touring Tire</span></span>|<span data-ttu-id="d7e44-187">62364.225</span><span class="sxs-lookup"><span data-stu-id="d7e44-187">62364.225</span></span>|<span data-ttu-id="d7e44-188">375051.60</span><span class="sxs-lookup"><span data-stu-id="d7e44-188">375051.60</span></span>|<span data-ttu-id="d7e44-189">1041810.00</span><span class="sxs-lookup"><span data-stu-id="d7e44-189">1041810.00</span></span>|  
  
 <span data-ttu-id="d7e44-190">Pour croiser dynamiquement les données de la colonne **Year** , comme indiqué ci-dessus, vous devez définir les options suivantes dans la boîte de dialogue **Tableau croisé dynamique** .</span><span class="sxs-lookup"><span data-stu-id="d7e44-190">To pivot the data on the **Year** column, as shown above, the following options are set in the **Pivot** dialog box.</span></span>  
  
-   <span data-ttu-id="d7e44-191">Year est sélectionné dans la zone de liste **Clé de tableau croisé dynamique** .</span><span class="sxs-lookup"><span data-stu-id="d7e44-191">Year is selected in the **Pivot Key** list box.</span></span>  
  
-   <span data-ttu-id="d7e44-192">Product Name est sélectionné dans la zone de liste **Définir la clé** .</span><span class="sxs-lookup"><span data-stu-id="d7e44-192">Product Name is selected in the **Set Key** list box.</span></span>  
  
-   <span data-ttu-id="d7e44-193">Total est sélectionné dans la zone de liste **Valeur de tableau croisé dynamique** .</span><span class="sxs-lookup"><span data-stu-id="d7e44-193">Total is selected in the **Pivot Value** list box.</span></span>  
  
-   <span data-ttu-id="d7e44-194">Les valeurs suivantes sont entrées dans la zone **Générer des colonnes de sortie de tableau croisé dynamique à partir de valeurs** .</span><span class="sxs-lookup"><span data-stu-id="d7e44-194">The following values are entered in the **Generate pivot output columns from values** box.</span></span>  
  
     <span data-ttu-id="d7e44-195">[2002],[2003],[2004]</span><span class="sxs-lookup"><span data-stu-id="d7e44-195">[2002],[2003],[2004]</span></span>  
  
## <a name="configuration-of-the-pivot-transformation"></a><span data-ttu-id="d7e44-196">Configuration de la transformation Pivot</span><span class="sxs-lookup"><span data-stu-id="d7e44-196">Configuration of the Pivot Transformation</span></span>  
 <span data-ttu-id="d7e44-197">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="d7e44-197">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="d7e44-198">Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur avancé** , cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="d7e44-198">For more information about the properties that you can set in the **Advanced Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="d7e44-199">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="d7e44-199">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="d7e44-200">Propriétés personnalisées des transformations</span><span class="sxs-lookup"><span data-stu-id="d7e44-200">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-content"></a><span data-ttu-id="d7e44-201">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="d7e44-201">Related Content</span></span>  
 <span data-ttu-id="d7e44-202">Pour plus d’informations sur la définition des propriétés de ce composant, consultez [Définir les propriétés d’un composant de flux de données](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="d7e44-202">For information about how to set the properties of this component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7e44-203">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d7e44-203">See Also</span></span>  
 <span data-ttu-id="d7e44-204">[Transformation Unpivot](pivot-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="d7e44-204">[Unpivot Transformation](pivot-transformation.md) </span></span>  
 <span data-ttu-id="d7e44-205">[Flux de données](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="d7e44-205">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="d7e44-206">Transformations Integration Services</span><span class="sxs-lookup"><span data-stu-id="d7e44-206">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
