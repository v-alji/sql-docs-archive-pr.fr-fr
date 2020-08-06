---
title: Correspondance de noms (Assistant vue de source de données) (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.datasourceviewwizard.namematchingcriteria.f1
ms.assetid: 7f811e02-0fe6-45c9-a7b7-29c61032d96b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 50cc46db7f582e0aea1570dadc956336ef8be074
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605793"
---
# <a name="name-matching-data-source-view-wizard-analysis-services"></a><span data-ttu-id="90d37-102">Correspondance de noms (Assistant Vue de source de données) (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="90d37-102">Name Matching (Data Source View Wizard) (Analysis Services)</span></span>
  <span data-ttu-id="90d37-103">Utilisez la page **Correspondance de noms** pour sélectionner le critère à utiliser pour détecter les relations possibles entre les tables que vous sélectionnez pour la vue de source de données et les autres tables du schéma.</span><span class="sxs-lookup"><span data-stu-id="90d37-103">Use the **Name Matching** page to select the criterion to use for detecting possible relationships between the tables that you select for the data source view and the other tables in the schema.</span></span> <span data-ttu-id="90d37-104">Si aucune relation de clé étrangère n'existe entre les tables, ce critère permet d'identifier et d'ajouter les tables associées à la vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="90d37-104">If no physical foreign key relationships exist between the tables, this criterion helps you identify and add related tables to the data source view.</span></span> <span data-ttu-id="90d37-105">Les relations logiques identifiées par une correspondance de noms sont également ajoutées à la vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="90d37-105">The logical relationships that are identified by name matching are also added to the data source view.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="90d37-106">Cette page apparaît uniquement si vous sélectionnez une source de données qui dispose de plusieurs tables, mais pas de relations de clés étrangères entre les tables.</span><span class="sxs-lookup"><span data-stu-id="90d37-106">This page appears only if you select a data source that has multiple tables but no foreign key relationships between any one of the tables.</span></span>  
  
## <a name="options"></a><span data-ttu-id="90d37-107">Options</span><span class="sxs-lookup"><span data-stu-id="90d37-107">Options</span></span>  
 <span data-ttu-id="90d37-108">**Créer des relations logiques en faisant correspondre des colonnes**</span><span class="sxs-lookup"><span data-stu-id="90d37-108">**Create logical relationships by matching columns**</span></span>  
 <span data-ttu-id="90d37-109">Sélectionnez cette option pour utiliser un critère de correspondance de noms pour détecter les dépendances logiques et les relations possibles entre les tables que vous sélectionnez pour les inclure dans la vue de source de données et les autres tables du schéma.</span><span class="sxs-lookup"><span data-stu-id="90d37-109">Select to use a name-matching criterion to detect possible logical dependencies and relationships between the tables that you select to include in the data source view and the other tables in the schema.</span></span> <span data-ttu-id="90d37-110">Si vous désactivez cette case à cocher, aucun critère de correspondance de noms n'est utilisé pour identifier les relations logiques entre les tables dans la source de données.</span><span class="sxs-lookup"><span data-stu-id="90d37-110">If you clear this check box, no name-matching criterion is used to identify logical relationships between tables in the data source.</span></span>  
  
 <span data-ttu-id="90d37-111">**Correspondances de clés étrangères**</span><span class="sxs-lookup"><span data-stu-id="90d37-111">**Foreign key matches**</span></span>  
 <span data-ttu-id="90d37-112">Sélectionnez le critère à utiliser pour créer des relations logiques entre les tables et les vues dans la source de données.</span><span class="sxs-lookup"><span data-stu-id="90d37-112">Select the criterion to use for creating logical relationships between tables and views in the data source.</span></span> <span data-ttu-id="90d37-113">Les caractères non alphanumériques sont ignorés dans les chaînes de correspondance.</span><span class="sxs-lookup"><span data-stu-id="90d37-113">Non-alphanumeric characters are ignored in matching strings.</span></span> <span data-ttu-id="90d37-114">Par exemple, « ID Client », « ID_Client », « IDClient » correspondent tous.</span><span class="sxs-lookup"><span data-stu-id="90d37-114">For example, "Customer ID", "Customer_ID", "CustomerID" all match.</span></span> <span data-ttu-id="90d37-115">Sélectionnez l'une des options suivantes dans le tableau ci-dessous pour créer des relations dans les cas indiqués.</span><span class="sxs-lookup"><span data-stu-id="90d37-115">Select one of the options in the following table to create relationships under the specified conditions.</span></span>  
  
|<span data-ttu-id="90d37-116">Sélectionnez</span><span class="sxs-lookup"><span data-stu-id="90d37-116">Select</span></span>|<span data-ttu-id="90d37-117">Élément créé</span><span class="sxs-lookup"><span data-stu-id="90d37-117">To create</span></span>|  
|------------|---------------|  
|<span data-ttu-id="90d37-118">**Nom identique à la clé primaire**</span><span class="sxs-lookup"><span data-stu-id="90d37-118">**Same name as primary key**</span></span>|<span data-ttu-id="90d37-119">Relation logique à une table avec un nom de colonne qui correspond au nom de la colonne clé primaire d'une table sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="90d37-119">A logical relationship to any table with a column name that matches the name of the primary key column in a selected table.</span></span>|  
|<span data-ttu-id="90d37-120">**Nom identique à celui de la table de destination**</span><span class="sxs-lookup"><span data-stu-id="90d37-120">**Same name as destination table name**</span></span>|<span data-ttu-id="90d37-121">Relation logique à une table avec un nom de colonne qui correspond au nom de la table sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="90d37-121">A logical relationship to any table with a column name that matches the name of a selected table.</span></span>|  
|<span data-ttu-id="90d37-122">**Nom de la table de destination + nom de la clé primaire**</span><span class="sxs-lookup"><span data-stu-id="90d37-122">**Destination table name + primary key name**</span></span>|<span data-ttu-id="90d37-123">Relation logique à une table dans laquelle un nom de colonne correspond au nom de la table sélectionné concaténé avec le nom de la colonne clé primaire de la table sélectionnée (dans cet ordre).</span><span class="sxs-lookup"><span data-stu-id="90d37-123">A logical relationship to any table in which a column name matches the selected table name concatenated with the name of the primary key column for the selected table, in that order.</span></span> <span data-ttu-id="90d37-124">Les caractères non alphanumériques dans la concaténation sont ignorés (par exemple, « ID Produit », « ID_Produit » et « IDProduit » correspondent tous).</span><span class="sxs-lookup"><span data-stu-id="90d37-124">Non-alphanumeric characters within the concatenation are ignored (for example, "Product ID", "Product_ID" and "ProductID" all match).</span></span>|  
  
 <span data-ttu-id="90d37-125">**Description et exemple**</span><span class="sxs-lookup"><span data-stu-id="90d37-125">**Description and sample**</span></span>  
 <span data-ttu-id="90d37-126">Affichage de la description et d'un exemple du critère sélectionné.</span><span class="sxs-lookup"><span data-stu-id="90d37-126">View a description and a sample of the selected criterion.</span></span>  
  
  
