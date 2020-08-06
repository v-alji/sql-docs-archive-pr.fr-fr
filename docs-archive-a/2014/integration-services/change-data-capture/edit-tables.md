---
title: Modifier des tables | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- tabProps
ms.assetid: fed8fada-2abc-45e2-8228-0656f9c599cb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8e8058a0c3e8b81814283f055e4c4ac2b08dd2fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601037"
---
# <a name="edit-tables"></a><span data-ttu-id="afff5-102">Modifier des tables</span><span class="sxs-lookup"><span data-stu-id="afff5-102">Edit Tables</span></span>
  <span data-ttu-id="afff5-103">Utilisez l'onglet **Tables** pour apporter des modifications aux tables et aux colonnes sélectionnées dans la base de données source Oracle.</span><span class="sxs-lookup"><span data-stu-id="afff5-103">Use the **Tables** tab to make changes to the tables and columns that you selected from the Oracle source database.</span></span> <span data-ttu-id="afff5-104">Cet onglet contient les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="afff5-104">This tab has the following elements:</span></span>  
  
 <span data-ttu-id="afff5-105">**Liste Table**</span><span class="sxs-lookup"><span data-stu-id="afff5-105">**Table list**</span></span>  
 <span data-ttu-id="afff5-106">La liste de tables comporte trois colonnes :</span><span class="sxs-lookup"><span data-stu-id="afff5-106">The table list has three columns:</span></span>  
  
-   <span data-ttu-id="afff5-107">**Nom de la table Oracle**: nom de la table, y compris du schéma de la table.</span><span class="sxs-lookup"><span data-stu-id="afff5-107">**Oracle Table Name**: The name of the table, including the table schema.</span></span>  
  
-   <span data-ttu-id="afff5-108">**Instance de capture**: nom de l’instance de capture utilisée pour nommer les objets de capture de données modifiées spécifiques à l’instance.</span><span class="sxs-lookup"><span data-stu-id="afff5-108">**Capture Instance**: The name of the capture instance used to name instance-specific change data capture objects.</span></span> <span data-ttu-id="afff5-109">L'instance de capture ne peut pas être NULL.</span><span class="sxs-lookup"><span data-stu-id="afff5-109">The capture instance cannot be NULL.</span></span> <span data-ttu-id="afff5-110">S'il n'est pas spécifié, le nom est dérivé du nom de schéma d'origine associé au nom de table source au format `<schema-name>_<table-name>.` . Le nom de l'instance de capture ne peut pas dépasser 100 caractères et doit être unique dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="afff5-110">If not specified, the name is derived from the source schema name plus the source table name in the format `<schema-name>_<table-name>.` The capture instance name cannot exceed 100 characters and must be unique within the database.</span></span> <span data-ttu-id="afff5-111">Vous pouvez cliquer dans n’importe quelle cellule de cette colonne pour modifier manuellement **capture_instance**.</span><span class="sxs-lookup"><span data-stu-id="afff5-111">You can click in any cell in this column to manually edit the **capture_instance**.</span></span>  
  
-   <span data-ttu-id="afff5-112">**Rôle de sécurité**: nom du rôle de base de données utilisé pour obtenir l'accès aux données modifiées.</span><span class="sxs-lookup"><span data-stu-id="afff5-112">**Security Role**: The name of the database role used to gain access to change data.</span></span> <span data-ttu-id="afff5-113">Vous pouvez cliquer dans n’importe quelle cellule de cette colonne pour modifier manuellement **security_role**.</span><span class="sxs-lookup"><span data-stu-id="afff5-113">You can click in any cell in this column to manually edit the **security_role**.</span></span>  
  
 <span data-ttu-id="afff5-114">**Ajouter des tables**</span><span class="sxs-lookup"><span data-stu-id="afff5-114">**Add Tables**</span></span>  
 <span data-ttu-id="afff5-115">Cliquez sur **Ajouter des tables** pour ouvrir la boîte de dialogue Sélection de table dans laquelle vous pouvez [ajouter des tables à une instance de capture de données modifiées](add-tables-to-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="afff5-115">Click **Add Tables** to open the Table Selection dialog box where you can [Add Tables to a CDC Instance](add-tables-to-a-cdc-instance.md).</span></span> <span data-ttu-id="afff5-116">Lorsque vous accédez pour la première fois à la base de données Oracle, vous devez [Connect to Oracle](connect-to-oracle.md).</span><span class="sxs-lookup"><span data-stu-id="afff5-116">The first time this session that you access the Oracle database, you must [Connect to Oracle](connect-to-oracle.md).</span></span>  
  
 <span data-ttu-id="afff5-117">**Modifier**</span><span class="sxs-lookup"><span data-stu-id="afff5-117">**Edit**</span></span>  
 <span data-ttu-id="afff5-118">Sélectionnez une table dans la liste et cliquez sur **Modifier** pour ouvrir la boîte de dialogue **Propriétés** de cette table dans laquelle vous pouvez [Modifier les propriétés d’une table](edit-the-table-properties.md).</span><span class="sxs-lookup"><span data-stu-id="afff5-118">Select a table from the list and select **Edit** to open the **Properties** dialog box for that table where you can [Edit the Table Properties](edit-the-table-properties.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="afff5-119">Vous ne pouvez pas modifier le mappage de type pour les tables qui possèdent déjà des tables miroir.</span><span class="sxs-lookup"><span data-stu-id="afff5-119">You cannot edit type mapping for tables that already have mirror tables.</span></span> <span data-ttu-id="afff5-120">Vous ne pouvez le faire que pour les nouvelles tables.</span><span class="sxs-lookup"><span data-stu-id="afff5-120">You can do this for new tables only.</span></span>  
  
 <span data-ttu-id="afff5-121">**Remove**</span><span class="sxs-lookup"><span data-stu-id="afff5-121">**Remove**</span></span>  
 <span data-ttu-id="afff5-122">Sélectionnez une table dans la liste et cliquez sur **Supprimer** pour supprimer la table de l’instance CDC.</span><span class="sxs-lookup"><span data-stu-id="afff5-122">Select a table from the list and click **Remove** to remove the table from the CDC instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afff5-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="afff5-123">See Also</span></span>  
 <span data-ttu-id="afff5-124">[Procédure : modifier les propriétés d'une instance de capture de données modifiées](how-to-edit-the-cdc-instance-properties.md) </span><span class="sxs-lookup"><span data-stu-id="afff5-124">[How to Edit the CDC Instance Properties](how-to-edit-the-cdc-instance-properties.md) </span></span>  
 [<span data-ttu-id="afff5-125">Sélectionner des tables et des colonnes Oracle</span><span class="sxs-lookup"><span data-stu-id="afff5-125">Select Oracle Tables and Columns</span></span>](select-oracle-tables-and-columns.md)  
  
  
