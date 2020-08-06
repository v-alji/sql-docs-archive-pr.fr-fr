---
title: Sélectionner des tables et des colonnes Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- selTabCol
ms.assetid: bf73f80e-a954-4c5f-874e-17fdd4082715
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d51e597f1210643b1543ed981045ade7b2fc2b62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603578"
---
# <a name="select-oracle-tables-and-columns"></a><span data-ttu-id="603b7-102">Sélectionner des tables et des colonnes Oracle</span><span class="sxs-lookup"><span data-stu-id="603b7-102">Select Oracle Tables and Columns</span></span>
  <span data-ttu-id="603b7-103">Utilisez la page Sélectionner des tables et des colonnes Oracle pour sélectionner les tables de la base de données source Oracle dans laquelle les modifications sont capturées.</span><span class="sxs-lookup"><span data-stu-id="603b7-103">Use the Select Oracle Tables and Columns page to select the tables from the Oracle source database where changes are captured.</span></span> <span data-ttu-id="603b7-104">Cette page contient les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="603b7-104">This page has the following elements:</span></span>  
  
## <a name="options"></a><span data-ttu-id="603b7-105">Options</span><span class="sxs-lookup"><span data-stu-id="603b7-105">Options</span></span>  
 <span data-ttu-id="603b7-106">**Liste Table**</span><span class="sxs-lookup"><span data-stu-id="603b7-106">**Table list**</span></span>  
 <span data-ttu-id="603b7-107">La liste de tables comporte trois colonnes :</span><span class="sxs-lookup"><span data-stu-id="603b7-107">The table list has three columns:</span></span>  
  
-   <span data-ttu-id="603b7-108">**Nom de la table Oracle**: nom de la table, y compris du schéma de la table.</span><span class="sxs-lookup"><span data-stu-id="603b7-108">**Oracle Table Name**: The name of the table, including the table schema.</span></span>  
  
-   <span data-ttu-id="603b7-109">**Instance de capture**: nom de l’instance de capture utilisée pour nommer les objets de capture de données modifiées spécifiques à l’instance.</span><span class="sxs-lookup"><span data-stu-id="603b7-109">**Capture Instance**: The name of the capture instance used to name instance-specific change data capture objects.</span></span> <span data-ttu-id="603b7-110">L'instance de capture ne peut pas être NULL.</span><span class="sxs-lookup"><span data-stu-id="603b7-110">The capture instance cannot be NULL.</span></span>  
  
     <span data-ttu-id="603b7-111">S'il n'est pas spécifié, le nom est dérivé du nom du schéma d'origine plus le nom de la table source au format `<schema-name>_<table-name>`.</span><span class="sxs-lookup"><span data-stu-id="603b7-111">If not specified, the name is derived from the source schema name plus the source table name in the format `<schema-name>_<table-name>`.</span></span> <span data-ttu-id="603b7-112">Le nom de l'instance de capture ne peut pas dépasser 100 caractères et doit être unique dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="603b7-112">The capture instance name cannot exceed 100 characters and must be unique within the database.</span></span>  
  
     <span data-ttu-id="603b7-113">Vous pouvez cliquer dans n’importe quelle cellule de cette colonne pour modifier manuellement **capture_instance**.</span><span class="sxs-lookup"><span data-stu-id="603b7-113">You can click in any cell in this column to manually edit the **capture_instance**.</span></span>  
  
-   <span data-ttu-id="603b7-114">**Rôle de sécurité**: nom du rôle de régulation de base de données utilisé pour contrôler l'accès aux données modifiées.</span><span class="sxs-lookup"><span data-stu-id="603b7-114">**Security Role**: The name of the database gating role used to control access to change data.</span></span>  
  
     <span data-ttu-id="603b7-115">Vous pouvez cliquer dans n’importe quelle cellule de cette colonne pour modifier manuellement **security_role**.</span><span class="sxs-lookup"><span data-stu-id="603b7-115">You can click in any cell in this column to manually edit the **security_role**.</span></span>  
  
 <span data-ttu-id="603b7-116">**Ajouter des tables**</span><span class="sxs-lookup"><span data-stu-id="603b7-116">**Add Tables**</span></span>  
 <span data-ttu-id="603b7-117">Cliquez sur **Ajouter des tables** pour ouvrir la boîte de dialogue Sélection de table dans laquelle vous pouvez [sélectionner des tables Oracle pour capturer des modifications](select-oracle-tables-for-capturing-changes.md).</span><span class="sxs-lookup"><span data-stu-id="603b7-117">Click **Add Tables** to open the Table Selection dialog box where you can [Select Oracle Tables for Capturing Changes](select-oracle-tables-for-capturing-changes.md).</span></span>  
  
 <span data-ttu-id="603b7-118">**Modifier**</span><span class="sxs-lookup"><span data-stu-id="603b7-118">**Edit**</span></span>  
 <span data-ttu-id="603b7-119">Sélectionnez une table dans la liste et cliquez sur **Modifier** pour ouvrir la boîte de dialogue **Propriétés** de cette table dans laquelle vous pouvez [apporter des modifications aux tables sélectionnées pour capturer les modifications](make-changes-to-the-tables-selected-for-capturing-changes.md).</span><span class="sxs-lookup"><span data-stu-id="603b7-119">Select a table from the list and select **Edit** to open the **Properties** dialog box for that table where you can [Make Changes to the Tables Selected for Capturing Changes](make-changes-to-the-tables-selected-for-capturing-changes.md).</span></span>  
  
 <span data-ttu-id="603b7-120">**Remove**</span><span class="sxs-lookup"><span data-stu-id="603b7-120">**Remove**</span></span>  
 <span data-ttu-id="603b7-121">Sélectionnez une table dans la liste et cliquez sur **Supprimer** pour supprimer la table de l’instance CDC.</span><span class="sxs-lookup"><span data-stu-id="603b7-121">Select a table from the list and click **Remove** to remove the table from the CDC instance.</span></span>  
  
 <span data-ttu-id="603b7-122">Après avoir [sélectionné des tables Oracle pour capturer des modifications](select-oracle-tables-for-capturing-changes.md) et/ou [apporté des modifications aux tables sélectionnées pour capturer les modifications](make-changes-to-the-tables-selected-for-capturing-changes.md) à l’aide des boîtes de dialogue appropriées, cliquez sur **Suivant** pour [générer et exécuter le script de journalisation supplémentaire](generate-and-run-the-supplemental-logging-script.md).</span><span class="sxs-lookup"><span data-stu-id="603b7-122">After you [Select Oracle Tables for Capturing Changes](select-oracle-tables-for-capturing-changes.md) and/or [Make Changes to the Tables Selected for Capturing Changes](make-changes-to-the-tables-selected-for-capturing-changes.md) using the correct dialog boxes, click **Next** to [Generate and Run the Supplemental Logging Script](generate-and-run-the-supplemental-logging-script.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="603b7-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="603b7-123">See Also</span></span>  
 <span data-ttu-id="603b7-124">[Procédure : créer l'instance SQL Server de base de données de modifications](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="603b7-124">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 <span data-ttu-id="603b7-125">[Modifier des tables](edit-tables.md) </span><span class="sxs-lookup"><span data-stu-id="603b7-125">[Edit Tables](edit-tables.md) </span></span>  
 <span data-ttu-id="603b7-126">[Ajouter des tables à une instance CDC](add-tables-to-a-cdc-instance.md) </span><span class="sxs-lookup"><span data-stu-id="603b7-126">[Add Tables to a CDC Instance](add-tables-to-a-cdc-instance.md) </span></span>  
 [<span data-ttu-id="603b7-127">Modifier les propriétés d’une table</span><span class="sxs-lookup"><span data-stu-id="603b7-127">Edit the Table Properties</span></span>](edit-the-table-properties.md)  
  
  
