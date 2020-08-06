---
title: 'Procédure pas à pas : ajouter et modifier un diagramme de base de données | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- database diagrams [SQL Server], about database diagrams
- database diagrams [SQL Server], designing
- database diagrams [SQL Server], creating
ms.assetid: 228caa0d-8f24-46ab-86d1-b6d8631322bc
author: stevestein
ms.author: sstein
ms.openlocfilehash: c35eb3674c817e98a25a74cd0309fc7376fe2f58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601246"
---
# <a name="walkthrough-adding-and-changing-a-database-diagram"></a><span data-ttu-id="0b140-102">Procédure pas à pas : ajout et modification d’un diagramme de base de données</span><span class="sxs-lookup"><span data-stu-id="0b140-102">Walkthrough: Adding and Changing a Database Diagram</span></span>
  <span data-ttu-id="0b140-103">Cette procédure pas à pas montre comment créer et modifier un diagramme de base de données et apporter des modifications à la base de données par l’intermédiaire du composant des diagrammes de base de données.</span><span class="sxs-lookup"><span data-stu-id="0b140-103">This walkthrough illustrates how to create and modify a database diagram and make changes to the database through the database diagrams component.</span></span> <span data-ttu-id="0b140-104">Vous apprendrez à ajouter des tables aux schémas, à créer des relations entre les tables, créer des contraintes et des index sur des colonnes et modifier le niveau des informations qui s'affichent pour chaque table.</span><span class="sxs-lookup"><span data-stu-id="0b140-104">You will see how to add tables to diagrams, create relationships between tables, create constraints and indexes on columns, and change the level of information you see for each table.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0b140-105">Conditions préalables requises</span><span class="sxs-lookup"><span data-stu-id="0b140-105">Prerequisites</span></span>  
 <span data-ttu-id="0b140-106">Pour réaliser cette procédure pas à pas, vous aurez besoin des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="0b140-106">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="0b140-107">Accès à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avec l'exemple de base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0b140-107">Access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database</span></span>  
  
-   <span data-ttu-id="0b140-108">Un compte avec des privilèges `dbo` de propriétaire de base de données</span><span class="sxs-lookup"><span data-stu-id="0b140-108">An account with database owner `dbo` privileges</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0b140-109">Si vous tentez d'apporter des changements lorsque vous utilisez un compte sans privilèges suffisants pour modifier les tables, un message d'erreur s'affiche.</span><span class="sxs-lookup"><span data-stu-id="0b140-109">If you attempt to make changes when using an account without sufficient privileges to make changes to tables, then an error message appears.</span></span>  
  
## <a name="creating-a-diagram"></a><span data-ttu-id="0b140-110">Création d'un schéma</span><span class="sxs-lookup"><span data-stu-id="0b140-110">Creating a Diagram</span></span>  
  
#### <a name="to-create-a-new-database-diagram"></a><span data-ttu-id="0b140-111">Pour créer un nouveau diagramme de base de données</span><span class="sxs-lookup"><span data-stu-id="0b140-111">To create a new database diagram</span></span>  
  
1.  <span data-ttu-id="0b140-112">Dans le menu **Affichage** , cliquez sur **Explorateur d’objets**.</span><span class="sxs-lookup"><span data-stu-id="0b140-112">On the **View** menu, click **Object Explorer**.</span></span>  
  
2.  <span data-ttu-id="0b140-113">Ouvrez le nœud Bases de données puis le nœud [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0b140-113">Open the Databases node and then open the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] node.</span></span>  
  
3.  <span data-ttu-id="0b140-114">Cliquez avec le bouton droit sur le nœud Diagrammes de base de données et sélectionnez **Nouveau diagramme de base de données**.</span><span class="sxs-lookup"><span data-stu-id="0b140-114">Right-click the Database Diagrams node and choose **New Database Diagram**.</span></span>  
  
     <span data-ttu-id="0b140-115">Si la base de données n’a pas les objets nécessaires pour créer des diagrammes, le message suivant s’affiche : **Cette base de données ne dispose pas d’au moins un des objets de prise en charge nécessaires pour la fonctionnalité de diagrammes de base de données. Voulez-vous les créer ?**</span><span class="sxs-lookup"><span data-stu-id="0b140-115">If the database does not have objects necessary to create diagrams, the following message appears: **This database does not have one or more of the support objects required to use database diagramming. Do you wish to create them?**</span></span> <span data-ttu-id="0b140-116">Choisissez **Oui**.</span><span class="sxs-lookup"><span data-stu-id="0b140-116">Choose **Yes**.</span></span>  
  
     <span data-ttu-id="0b140-117">La boîte de dialogue **Ajouter une table** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="0b140-117">The **Add Table** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="0b140-118">Sélectionnez **Type d’adresse (Personne)** et **Adresse (Personne)** et cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="0b140-118">Select **AddressType (Person)** and **Address (Person)** and click **Add**.</span></span>  
  
     <span data-ttu-id="0b140-119">Deux tables sont ajoutées au schéma.</span><span class="sxs-lookup"><span data-stu-id="0b140-119">Two tables are added to the diagram.</span></span>  
  
5.  <span data-ttu-id="0b140-120">Fermez la boîte de dialogue **Ajouter une table** .</span><span class="sxs-lookup"><span data-stu-id="0b140-120">Close the **Add Table** dialog box.</span></span>  
  
#### <a name="to-view-different-column-data"></a><span data-ttu-id="0b140-121">Pour afficher différentes données de colonne</span><span class="sxs-lookup"><span data-stu-id="0b140-121">To view different column data</span></span>  
  
1.  <span data-ttu-id="0b140-122">Cliquez avec le bouton droit sur la table `Address` .</span><span class="sxs-lookup"><span data-stu-id="0b140-122">Right-click the `Address` table.</span></span> <span data-ttu-id="0b140-123">Dans le menu contextuel, pointez sur **Vue Table**, puis cliquez sur **Standard**.</span><span class="sxs-lookup"><span data-stu-id="0b140-123">On the shortcut menu, point to **Table View**, and then click **Standard**.</span></span>  
  
     <span data-ttu-id="0b140-124">La grille de table affiche trois colonnes : **Nom de la colonne**, **Type de données**et **Autoriser les valeurs NULL**.</span><span class="sxs-lookup"><span data-stu-id="0b140-124">The table grid shows three columns: **Column Name**, **Data Type**, and **Allow Nulls**.</span></span>  
  
2.  <span data-ttu-id="0b140-125">Cliquez avec le bouton droit sur la table `Address` , cliquez sur **Vue Table** et sélectionnez **Clés**.</span><span class="sxs-lookup"><span data-stu-id="0b140-125">Right-click the `Address` table, click **Table View** and select **Keys**.</span></span>  
  
     <span data-ttu-id="0b140-126">La grille de table affiche une colonne et les noms de colonne-table.</span><span class="sxs-lookup"><span data-stu-id="0b140-126">The table grid shows one column, with the table-column names.</span></span> <span data-ttu-id="0b140-127">Seules les colonnes actives dans les index s'affichent.</span><span class="sxs-lookup"><span data-stu-id="0b140-127">Only those columns participating in indexes appear.</span></span>  
  
## <a name="creating-new-tables"></a><span data-ttu-id="0b140-128">Création de nouvelles tables</span><span class="sxs-lookup"><span data-stu-id="0b140-128">Creating New Tables</span></span>  
  
#### <a name="to-create-tables-within-diagram-designer"></a><span data-ttu-id="0b140-129">Pour créer des tables dans le Concepteur de schémas</span><span class="sxs-lookup"><span data-stu-id="0b140-129">To create tables within Diagram Designer</span></span>  
  
1.  <span data-ttu-id="0b140-130">Cliquez avec le bouton droit sur le Concepteur de schémas en dehors des tables existantes et choisissez **Nouvelle table**.</span><span class="sxs-lookup"><span data-stu-id="0b140-130">Right-click the Diagram Designer outside the existing tables and choose **New Table**.</span></span>  
  
2.  <span data-ttu-id="0b140-131">Dans la boîte de dialogue **choisir un nom** , cliquez sur **OK** pour accepter le nom par défaut `Table1` .</span><span class="sxs-lookup"><span data-stu-id="0b140-131">In the **Choose Name** dialog box, click **OK** to accept the default name `Table1`.</span></span>  
  
     <span data-ttu-id="0b140-132">Une nouvelle grille de table s’affiche avec trois colonnes : **Nom de la colonne**, **Type de données**et **Autoriser les valeurs NULL**.</span><span class="sxs-lookup"><span data-stu-id="0b140-132">A new table grid appears with three columns: **Column Name**, **Data Type**, and **Allow Nulls**.</span></span>  
  
3.  <span data-ttu-id="0b140-133">Ajoutez les informations suivantes à `Table1` :</span><span class="sxs-lookup"><span data-stu-id="0b140-133">Add the following information to `Table1`:</span></span>  
  
    |<span data-ttu-id="0b140-134">**Nom de la colonne**</span><span class="sxs-lookup"><span data-stu-id="0b140-134">**Column Name**</span></span>|<span data-ttu-id="0b140-135">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="0b140-135">**Data Type**</span></span>|<span data-ttu-id="0b140-136">**Null autorisé**</span><span class="sxs-lookup"><span data-stu-id="0b140-136">**Allow Nulls**</span></span>|  
    |---------------------|-------------------|---------------------|  
    |`T1col1`|`int`|<span data-ttu-id="0b140-137">cochée</span><span class="sxs-lookup"><span data-stu-id="0b140-137">checked</span></span>|  
    |`T1col2`|`varchar(50)`|<span data-ttu-id="0b140-138">cochée</span><span class="sxs-lookup"><span data-stu-id="0b140-138">checked</span></span>|  
    |`T1col3`|`float`|<span data-ttu-id="0b140-139">cochée</span><span class="sxs-lookup"><span data-stu-id="0b140-139">checked</span></span>|  
  
4.  <span data-ttu-id="0b140-140">Cliquez avec le bouton droit sur `T1col1` , puis sélectionnez **Définir la clé primaire**.</span><span class="sxs-lookup"><span data-stu-id="0b140-140">Right-click `T1col1` and select **Set Primary Key**.</span></span>  
  
     <span data-ttu-id="0b140-141">L'icône d'une clé s'affiche en regard du nom de la colonne.</span><span class="sxs-lookup"><span data-stu-id="0b140-141">A key icon will appear beside the column name.</span></span>  
  
5.  <span data-ttu-id="0b140-142">Dans le menu **Fichier** , cliquez sur **Enregistrer Diagram1**.</span><span class="sxs-lookup"><span data-stu-id="0b140-142">From the **File** menu, click **Save Diagram1**.</span></span>  
  
6.  <span data-ttu-id="0b140-143">Dans la boîte de dialogue **choisir un nom** , cliquez sur **OK** pour accepter le nom par défaut `Diagram1` .</span><span class="sxs-lookup"><span data-stu-id="0b140-143">In the **Choose Name** dialog box, click **OK** to accept the default name `Diagram1`.</span></span>  
  
7.  <span data-ttu-id="0b140-144">La boîte de dialogue **Enregistrer** s’affiche avec un message indiquant que `Table1` sera enregistré dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="0b140-144">The **Save** dialog box appears with a message that `Table1` will be saved to the database.</span></span> <span data-ttu-id="0b140-145">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="0b140-145">Click **Yes**.</span></span>  
  
## <a name="modifying-table-structure"></a><span data-ttu-id="0b140-146">Modification de la structure de la table</span><span class="sxs-lookup"><span data-stu-id="0b140-146">Modifying Table Structure</span></span>  
 <span data-ttu-id="0b140-147">Vous pouvez ajouter des contraintes de validation et établir des relations entre les tables dans le Concepteur de schémas.</span><span class="sxs-lookup"><span data-stu-id="0b140-147">You can add check constraints and make relationships between tables in Diagram Designer.</span></span>  
  
#### <a name="to-create-check-constraints"></a><span data-ttu-id="0b140-148">Pour créer des contraintes de validation</span><span class="sxs-lookup"><span data-stu-id="0b140-148">To create check constraints</span></span>  
  
1.  <span data-ttu-id="0b140-149">Dans `Table1`, cliquez avec le bouton droit sur la ligne `T1col3` et cliquez sur **Contraintes de validation**.</span><span class="sxs-lookup"><span data-stu-id="0b140-149">In `Table1`, right-click the `T1col3` row and choose **Check Constraints**.</span></span>  
  
     <span data-ttu-id="0b140-150">La boîte de dialogue **Contraintes de validation** apparaît.</span><span class="sxs-lookup"><span data-stu-id="0b140-150">The **Check Constraints** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="0b140-151">Cliquez sur **Add**.</span><span class="sxs-lookup"><span data-stu-id="0b140-151">Click **Add**.</span></span>  
  
     <span data-ttu-id="0b140-152">Une nouvelle contrainte s’affiche dans la liste **Contrainte de validation sélectionnée** avec le nom par défaut `CK_Table1`.</span><span class="sxs-lookup"><span data-stu-id="0b140-152">A new constraint appears in the **Selected Check Constraint** list, with the default name `CK_Table1`.</span></span>  
  
3.  <span data-ttu-id="0b140-153">Sélectionnez la ligne **Expression** dans la grille et cliquez sur le bouton de sélection.</span><span class="sxs-lookup"><span data-stu-id="0b140-153">Select the **Expression** row in the grid and click the ellipsis button.</span></span>  
  
     <span data-ttu-id="0b140-154">La boîte de dialogue **Expression de contrainte de validation** apparaît.</span><span class="sxs-lookup"><span data-stu-id="0b140-154">The **Check Constraint Expression** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="0b140-155">Tapez `T1col3 > 5` puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b140-155">Type `T1col3 > 5` and click **OK**.</span></span>  
  
     <span data-ttu-id="0b140-156">`Table1` contient à présent une contrainte selon laquelle toutes les valeurs entrées dans `T1col3` doivent être supérieures à 5.</span><span class="sxs-lookup"><span data-stu-id="0b140-156">`Table1` now has a constraint that all values entered into `T1col3` must be greater than 5.</span></span>  
  
5.  <span data-ttu-id="0b140-157">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="0b140-157">Click **Close**.</span></span>  
  
#### <a name="to-create-relationships-between-tables"></a><span data-ttu-id="0b140-158">Pour créer des relations entres des tables</span><span class="sxs-lookup"><span data-stu-id="0b140-158">To create relationships between tables</span></span>  
  
1.  <span data-ttu-id="0b140-159">Créez une nouvelle table dans le Concepteur de schémas nommée `Table2` et contenant les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="0b140-159">Create a new table in Diagram designer named `Table2` with the following columns:</span></span>  
  
    |<span data-ttu-id="0b140-160">**Nom de la colonne**</span><span class="sxs-lookup"><span data-stu-id="0b140-160">**Column Name**</span></span>|<span data-ttu-id="0b140-161">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="0b140-161">**Data Type**</span></span>|<span data-ttu-id="0b140-162">**Null autorisé**</span><span class="sxs-lookup"><span data-stu-id="0b140-162">**Allow Nulls**</span></span>|  
    |---------------------|-------------------|---------------------|  
    |`T2col1`|`int`|<span data-ttu-id="0b140-163">non validé</span><span class="sxs-lookup"><span data-stu-id="0b140-163">not checked</span></span>|  
    |`T2col2`|`varchar(50)`|<span data-ttu-id="0b140-164">cochée</span><span class="sxs-lookup"><span data-stu-id="0b140-164">checked</span></span>|  
    |`T2col3`|`xml`|<span data-ttu-id="0b140-165">cochée</span><span class="sxs-lookup"><span data-stu-id="0b140-165">checked</span></span>|  
  
    > [!NOTE]  
    >  <span data-ttu-id="0b140-166">Les colonnes situées du côté clé primaire d'une relation de clé étrangère doivent faire partie d'une clé primaire ou d'une contrainte unique.</span><span class="sxs-lookup"><span data-stu-id="0b140-166">The columns on the primary key side of a foreign key relationship must participate in either a Primary Key or a Unique Constraint.</span></span>  
  
2.  <span data-ttu-id="0b140-167">Faites glisser `T2col1` vers `T1col1`.</span><span class="sxs-lookup"><span data-stu-id="0b140-167">Drag `T2col1` to `T1col1`.</span></span>  
  
     <span data-ttu-id="0b140-168">Deux boîtes de dialogue apparaissent : **Relation de clé étrangère** en arrière-plan et **Tables et colonnes** au premier plan.</span><span class="sxs-lookup"><span data-stu-id="0b140-168">Two dialog boxes appear: **Foreign Key Relationship** in the background and **Tables and Columns** in the foreground.</span></span>  
  
3.  <span data-ttu-id="0b140-169">Cliquez sur **OK** pour enregistrer la nouvelle relation.</span><span class="sxs-lookup"><span data-stu-id="0b140-169">Click **OK** to save the new relationship.</span></span>  
  
4.  <span data-ttu-id="0b140-170">Cliquez à nouveau sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b140-170">Click **OK** again.</span></span>  
  
## <a name="creating-indexes"></a><span data-ttu-id="0b140-171">Création des index</span><span class="sxs-lookup"><span data-stu-id="0b140-171">Creating Indexes</span></span>  
 <span data-ttu-id="0b140-172">Vous pouvez créer des index sur la plupart des types de données, y compris les données XML.</span><span class="sxs-lookup"><span data-stu-id="0b140-172">You can create indexes on most types of data, including XML.</span></span>  
  
#### <a name="to-create-a-standard-index"></a><span data-ttu-id="0b140-173">Pour créer un index standard</span><span class="sxs-lookup"><span data-stu-id="0b140-173">To create a standard index</span></span>  
  
1.  <span data-ttu-id="0b140-174">Cliquez avec le bouton droit sur `Table1` et choisissez **Index/clés**.</span><span class="sxs-lookup"><span data-stu-id="0b140-174">Right-click `Table1` and choose **Indexes/Keys**.</span></span>  
  
     <span data-ttu-id="0b140-175">La boîte de dialogue **Index/Clés** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="0b140-175">The **Indexes/Keys** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="0b140-176">Cliquez sur **Add**.</span><span class="sxs-lookup"><span data-stu-id="0b140-176">Click **Add**.</span></span>  
  
     <span data-ttu-id="0b140-177">Un nouvel index s’affiche dans la liste **Selected Primary/Unique Key or Index** (Clé ou index primaire/unique sélectionné) avec un nom par défaut similaire à `IX_Table1`.</span><span class="sxs-lookup"><span data-stu-id="0b140-177">A new index appears in the **Selected Primary/Unique Key or Index** list, with a default name similar to `IX_Table1`.</span></span>  
  
3.  <span data-ttu-id="0b140-178">Sélectionnez la ligne **Colonnes** et cliquez sur le bouton de sélection.</span><span class="sxs-lookup"><span data-stu-id="0b140-178">Select the **Columns** row and click the ellipsis button.</span></span>  
  
     <span data-ttu-id="0b140-179">La boîte de dialogue **Colonnes d’index** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="0b140-179">The **Index Columns** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="0b140-180">Cliquez sur la flèche de déroulement sous **Nom de la colonne** et sélectionnez `T1col2`.</span><span class="sxs-lookup"><span data-stu-id="0b140-180">Click the drop-down arrow under **Column Name** and select `T1col2`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0b140-181">Vous pouvez ajouter des colonnes supplémentaires à cet index en sélectionnant la cellule sous `T1col2` et en choisissant un autre nom de colonne.</span><span class="sxs-lookup"><span data-stu-id="0b140-181">You may add additional columns to this index by selecting the cell below `T1col2` and choosing another column name.</span></span>  
  
5.  <span data-ttu-id="0b140-182">Cliquez sur **OK** pour enregistrer cet index.</span><span class="sxs-lookup"><span data-stu-id="0b140-182">Click **OK** to save this index.</span></span>  
  
6.  <span data-ttu-id="0b140-183">Cliquez sur **Fermer** dans la boîte de dialogue **Index/Clés** .</span><span class="sxs-lookup"><span data-stu-id="0b140-183">Click **Close** in the **Indexes/Keys** dialog box.</span></span>  
  
#### <a name="to-create-an-xml-index"></a><span data-ttu-id="0b140-184">Pour créer un index XML</span><span class="sxs-lookup"><span data-stu-id="0b140-184">To create an XML index</span></span>  
  
1.  <span data-ttu-id="0b140-185">Cliquez avec le bouton droit sur `T2col1` et sélectionnez **Définir la clé primaire**.</span><span class="sxs-lookup"><span data-stu-id="0b140-185">Right-click `T2col1` and choose **Set Primary Key**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0b140-186">L'ajout d'un index XML nécessite qu'une autre colonne de la table soit définie comme clé cluster primaire.</span><span class="sxs-lookup"><span data-stu-id="0b140-186">Adding an XML index requires that another column in the table be set as a clustered primary key.</span></span>  
  
2.  <span data-ttu-id="0b140-187">Cliquez avec le bouton droit sur la ligne `T2col3` dans `Table2` , et cliquez sur **Index XML**.</span><span class="sxs-lookup"><span data-stu-id="0b140-187">Right-click the `T2col3` row in `Table2` and select **XML Indexes**.</span></span>  
  
     <span data-ttu-id="0b140-188">La boîte de dialogue **Index XML** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="0b140-188">The **XML Indexes** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="0b140-189">Cliquez sur **Add**.</span><span class="sxs-lookup"><span data-stu-id="0b140-189">Click **Add**.</span></span>  
  
     <span data-ttu-id="0b140-190">Un index XML contenant des valeurs par défaut sera ajouté à la liste **Index XML sélectionné** .</span><span class="sxs-lookup"><span data-stu-id="0b140-190">An XML index with default values will be added to the **Selected XML Index** list.</span></span>  
  
4.  <span data-ttu-id="0b140-191">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="0b140-191">Click **Close**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0b140-192">Les index XML sont créés par colonne.</span><span class="sxs-lookup"><span data-stu-id="0b140-192">XML indexes are created per-column.</span></span> <span data-ttu-id="0b140-193">Le premier index XML est primaire et les index supplémentaires sont secondaires.</span><span class="sxs-lookup"><span data-stu-id="0b140-193">The first XML index is primary; any additional indexes are secondary.</span></span>  
  
## <a name="saving-the-diagram"></a><span data-ttu-id="0b140-194">Enregistrement du schéma</span><span class="sxs-lookup"><span data-stu-id="0b140-194">Saving the Diagram</span></span>  
 <span data-ttu-id="0b140-195">Toutes les modifications apportées au schéma ne sont publiées dans la base de données qu'une fois celle-ci enregistrée.</span><span class="sxs-lookup"><span data-stu-id="0b140-195">All of the changes you make to a diagram are not posted to the database until you save it.</span></span> <span data-ttu-id="0b140-196">En cas de problèmes ou de conflits, une boîte de dialogue s'affiche avec plus d'informations.</span><span class="sxs-lookup"><span data-stu-id="0b140-196">If there are problems or conflicts, a dialog box appears with more information.</span></span>  
  
#### <a name="to-save-a-database-diagram"></a><span data-ttu-id="0b140-197">Pour enregistrer un diagramme de base de données</span><span class="sxs-lookup"><span data-stu-id="0b140-197">To save a database diagram</span></span>  
  
1.  <span data-ttu-id="0b140-198">Dans le menu **Fichier** , sélectionnez **Enregistrer Diagram1**.</span><span class="sxs-lookup"><span data-stu-id="0b140-198">On the **File** menu, select **Save Diagram1**.</span></span>  
  
     <span data-ttu-id="0b140-199">La boîte de dialogue **Enregistrer** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="0b140-199">The **Save** dialog box appears.</span></span> <span data-ttu-id="0b140-200">Si **Signaler les tables affectées** est activé, les informations sur les tables nouvelles ou modifiées s’affichent.</span><span class="sxs-lookup"><span data-stu-id="0b140-200">If **Warn about Tables Affected** is selected, information about new or changed tables is listed.</span></span>  
  
2.  <span data-ttu-id="0b140-201">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b140-201">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="0b140-202">En cas d’erreurs, la boîte de dialogue **Notifications post-enregistrement** affiche les erreurs et leurs origines.</span><span class="sxs-lookup"><span data-stu-id="0b140-202">If any errors occurred, the **Post-Save Notifications** dialog box appears with the errors and their causes.</span></span> <span data-ttu-id="0b140-203">Corrigez les erreurs et réenregistrez le schéma.</span><span class="sxs-lookup"><span data-stu-id="0b140-203">Fix the errors and save the diagram again.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0b140-204">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="0b140-204">Next Steps</span></span>  
 <span data-ttu-id="0b140-205">Il s'agit d'un schéma de base contenant deux nouvelles tables et deux tables existantes, mais il illustre la possibilité de créer un schéma d'une base de données existante ou de créer un nouveau schéma visuel.</span><span class="sxs-lookup"><span data-stu-id="0b140-205">This is a basic diagram with just two existing and two new tables, but it illustrates the potential for diagramming an existing database or creating a new schema visually.</span></span> <span data-ttu-id="0b140-206">Suggestions pour des recherches approfondies :</span><span class="sxs-lookup"><span data-stu-id="0b140-206">Suggestions for more exploration include:</span></span>  
  
-   <span data-ttu-id="0b140-207">Créer des nouveaux schémas contenant des groupes de tables associées</span><span class="sxs-lookup"><span data-stu-id="0b140-207">Create new diagrams containing groups of related tables</span></span>  
  
-   <span data-ttu-id="0b140-208">Personnaliser la quantité d'informations affichées dans chaque table</span><span class="sxs-lookup"><span data-stu-id="0b140-208">Customize the amount of information shown for each table</span></span>  
  
-   <span data-ttu-id="0b140-209">Modifier la présentation et ajouter des annotations</span><span class="sxs-lookup"><span data-stu-id="0b140-209">Change the layout and add annotations</span></span>  
  
-   <span data-ttu-id="0b140-210">Copier le schéma dans un bitmap</span><span class="sxs-lookup"><span data-stu-id="0b140-210">Copy the diagram to a bitmap</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b140-211">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0b140-211">See Also</span></span>  
 <span data-ttu-id="0b140-212">[Personnaliser la quantité d’informations affichées dans les schémas &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0b140-212">[Customize the Amount of Information Displayed in Diagrams &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="0b140-213">[Configurer le concepteur de schémas de base de données &#40;Visual Database Tools&#41;](set-up-database-diagram-designer-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0b140-213">[Set Up Database Diagram Designer &#40;Visual Database Tools&#41;](set-up-database-diagram-designer-visual-database-tools.md) </span></span>  
 <span data-ttu-id="0b140-214">[Ajouter des tables à des schémas &#40;Visual Database Tools&#41;](add-tables-to-diagrams-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0b140-214">[Add Tables to Diagrams &#40;Visual Database Tools&#41;](add-tables-to-diagrams-visual-database-tools.md) </span></span>  
 <span data-ttu-id="0b140-215">[Créer des relations entre des tables sur un diagramme &#40;Visual Database Tools&#41;](create-relationships-between-tables-on-a-diagram-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0b140-215">[Create Relationships Between Tables on a Diagram &#40;Visual Database Tools&#41;](create-relationships-between-tables-on-a-diagram-visual-database-tools.md) </span></span>  
 <span data-ttu-id="0b140-216">[Créer des index XML](../../relational-databases/xml/create-xml-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="0b140-216">[Create XML Indexes](../../relational-databases/xml/create-xml-indexes.md) </span></span>  
 <span data-ttu-id="0b140-217">[Copier une image d’un schéma de base de données dans le presse-papiers &#40;Visual Database Tools&#41;](copy-an-image-of-a-database-diagram-to-the-clipboard-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0b140-217">[Copy an Image of a Database Diagram to the Clipboard &#40;Visual Database Tools&#41;](copy-an-image-of-a-database-diagram-to-the-clipboard-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="0b140-218">Utiliser une disposition de schémas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="0b140-218">Work with Diagram Layout &#40;Visual Database Tools&#41;</span></span>](work-with-diagram-layout-visual-database-tools.md)  
  
  
