---
title: Boîte de dialogue Tables et colonnes (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.tablesandcolumns
ms.assetid: 8cf27be1-e66d-4735-a428-9ab4b33af4f5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 28e0c52b74413a3a5a4122412c6028b34e974b09
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613251"
---
# <a name="tables-and-columns-dialog-box-visual-database-tools"></a><span data-ttu-id="5fa05-102">Boîte de dialogue Tables et colonnes (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="5fa05-102">Tables and Columns Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="5fa05-103">Utilisez cette boîte de dialogue pour mapper une clé primaire dans une table à une clé étrangère dans une autre.</span><span class="sxs-lookup"><span data-stu-id="5fa05-103">Use this dialog box to map a primary key in one table to a foreign key in another.</span></span> <span data-ttu-id="5fa05-104">Pour accéder à cette boîte de dialogue, dans le menu **Concepteur de tables** , cliquez sur **Relations**.</span><span class="sxs-lookup"><span data-stu-id="5fa05-104">To access this dialog box, from the **Table Designer** menu, click **Relationships**.</span></span> <span data-ttu-id="5fa05-105">Dans la boîte de dialogue **Relations de clé étrangère**, cliquez sur le champ **Spécification de tables et colonnes**, puis cliquez sur le bouton de sélection **(…)** situé à droite de la propriété.</span><span class="sxs-lookup"><span data-stu-id="5fa05-105">In the **Foreign Key Relationships** dialog box, click the **Tables and Columns Specification** field, and then click the ellipses **(...)** to the right of the property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5fa05-106">Si la table est publiée pour réplication, vous devez apporter vos modifications au schéma à l’aide de l’instruction Transact-SQL [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) ou de SMO (SQL Server Management Objects).</span><span class="sxs-lookup"><span data-stu-id="5fa05-106">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="5fa05-107">Lorsque les modifications sont apportées au diagramme à l’aide du Concepteur de tables ou du Concepteur de diagrammes de base de données, celui-ci tente d’abandonner la table et de la recréer.</span><span class="sxs-lookup"><span data-stu-id="5fa05-107">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="5fa05-108">Toutefois, il est impossible d'abandonner les objets publiés, par conséquent les modifications du schéma échoueront.</span><span class="sxs-lookup"><span data-stu-id="5fa05-108">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5fa05-109">Options</span><span class="sxs-lookup"><span data-stu-id="5fa05-109">Options</span></span>  
 <span data-ttu-id="5fa05-110">**Nom de la relation**</span><span class="sxs-lookup"><span data-stu-id="5fa05-110">**Relationship name**</span></span>  
 <span data-ttu-id="5fa05-111">Indique le nom de la relation.</span><span class="sxs-lookup"><span data-stu-id="5fa05-111">Shows the name of the relationship.</span></span>  
  
 <span data-ttu-id="5fa05-112">**Table de clé primaire**</span><span class="sxs-lookup"><span data-stu-id="5fa05-112">**Primary Key Table**</span></span>  
 <span data-ttu-id="5fa05-113">Répertorie les tables contenues dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="5fa05-113">Lists the tables in the database.</span></span> <span data-ttu-id="5fa05-114">Choisissez la table qui se trouvera du côté clé primaire de la relation.</span><span class="sxs-lookup"><span data-stu-id="5fa05-114">Choose the table that will be on the primary-key side of the relationship.</span></span>  
  
 <span data-ttu-id="5fa05-115">**Table de clé étrangère**</span><span class="sxs-lookup"><span data-stu-id="5fa05-115">**Foreign Key Table**</span></span>  
 <span data-ttu-id="5fa05-116">Affiche la table située du côté clé étrangère de la relation.</span><span class="sxs-lookup"><span data-stu-id="5fa05-116">Shows the table on the foreign key side of the relationship.</span></span> <span data-ttu-id="5fa05-117">Il s'agit de la table actuellement sélectionnée dans le Concepteur de tables.</span><span class="sxs-lookup"><span data-stu-id="5fa05-117">This is the table currently selected in Table Designer.</span></span>  
  
 <span data-ttu-id="5fa05-118">**Grille sous la table de clé primaire**</span><span class="sxs-lookup"><span data-stu-id="5fa05-118">**Grid beneath Primary Key Table**</span></span>  
 <span data-ttu-id="5fa05-119">Répertorie les colonnes de la table sélectionnées dans la liste **Table de clé primaire** .</span><span class="sxs-lookup"><span data-stu-id="5fa05-119">List the columns of the table selected in the **Primary Key Table** list.</span></span> <span data-ttu-id="5fa05-120">Entrez les colonnes qui contribuent à la clé primaire de cette table.</span><span class="sxs-lookup"><span data-stu-id="5fa05-120">Enter the columns contributing to that table's primary key.</span></span>  
  
 <span data-ttu-id="5fa05-121">**Grille sous la table de clé étrangère**</span><span class="sxs-lookup"><span data-stu-id="5fa05-121">**Grid beneath Foreign Key Table**</span></span>  
 <span data-ttu-id="5fa05-122">Répertorie les colonnes de la table sélectionnées dans la liste **Table de clé étrangère** .</span><span class="sxs-lookup"><span data-stu-id="5fa05-122">List the columns of the table selected in the **Foreign Key Table** list.</span></span> <span data-ttu-id="5fa05-123">Entrez la colonne clé étrangère de la table de clé étrangère qui correspond à la colonne clé primaire.</span><span class="sxs-lookup"><span data-stu-id="5fa05-123">Enter the foreign-key column of the foreign-key table that corresponds to the primary key column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5fa05-124">Les colonnes que vous choisissez pour la clé étrangère doivent posséder le même type de données que les colonnes primaires auxquelles elles correspondent.</span><span class="sxs-lookup"><span data-stu-id="5fa05-124">The columns you choose for the foreign key must have the same data type of the primary columns they correspond to.</span></span> <span data-ttu-id="5fa05-125">Il doit exister un nombre égal de colonnes dans chacune des clés.</span><span class="sxs-lookup"><span data-stu-id="5fa05-125">There must be an equal number of columns in each of the keys.</span></span> <span data-ttu-id="5fa05-126">Par exemple, si la clé primaire de la table située du côté clé primaire de la relation est composée de deux colonnes, vous devez faire correspondre chacune de ces colonnes à une colonne de la table située du côté clé étrangère de la relation.</span><span class="sxs-lookup"><span data-stu-id="5fa05-126">For example, if the primary key of the table on the primary side of the relationship is made up of two columns, you will need to match each of those columns with a column in the table for the foreign key side of the relationship.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fa05-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5fa05-127">See Also</span></span>  
 [<span data-ttu-id="5fa05-128">Créer des relations de clé étrangère</span><span class="sxs-lookup"><span data-stu-id="5fa05-128">Create Foreign Key Relationships</span></span>](../../relational-databases/tables/create-foreign-key-relationships.md)  
  
  
