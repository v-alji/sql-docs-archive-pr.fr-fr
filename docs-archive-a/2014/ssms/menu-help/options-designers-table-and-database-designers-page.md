---
title: Options (concepteurs-page concepteurs de tables et de bases de données) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Designers.Table_Designer
ms.assetid: b43f4b97-17b9-4004-a824-f77b9e145741
author: stevestein
ms.author: sstein
ms.openlocfilehash: d8a1218b4ea1ae9c6f9cf734bb33a2a4bebcb167
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612057"
---
# <a name="options-designers-table-and-database-designers-page"></a><span data-ttu-id="710ce-102">Options (concepteurs-page concepteurs de bases de données et de tables)</span><span class="sxs-lookup"><span data-stu-id="710ce-102">Options (Designers-Table and Database Designers Page)</span></span>
  <span data-ttu-id="710ce-103">Utilisez cette page pour déterminer le comportement par défaut du concepteur.</span><span class="sxs-lookup"><span data-stu-id="710ce-103">Use this page to determine the default behavior of the designer.</span></span> <span data-ttu-id="710ce-104">Pour accéder aux paramètres, dans le menu **Outils** , cliquez sur **Options**, développez le dossier **Concepteurs** , puis cliquez sur **Concepteur de bases de données et de tables**.</span><span class="sxs-lookup"><span data-stu-id="710ce-104">To access the settings, on the **Tools** menu, click **Options**, expand the **Designers** folder, and click **Table Designer**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="710ce-105">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="710ce-105">UI element list</span></span>  
 <span data-ttu-id="710ce-106">**Remplacer la valeur du délai d'attente de la chaîne de connexion pour les mises à jour du Concepteur de tables**</span><span class="sxs-lookup"><span data-stu-id="710ce-106">**Override connection string time-out value for table designer updates**</span></span>  
 <span data-ttu-id="710ce-107">Permet de définir une nouvelle valeur de délai d'attente pour les actions du Concepteur de tables.</span><span class="sxs-lookup"><span data-stu-id="710ce-107">Permits a new time-out value to be set for the actions of the table designer.</span></span> <span data-ttu-id="710ce-108">Cette option peut s'avérer utile lorsque le Concepteur de tables affecte une table volumineuse et nécessite un délai supplémentaire pour terminer la modification de la table.</span><span class="sxs-lookup"><span data-stu-id="710ce-108">This can be useful when the table designer affects a large table and requires extra time to complete the table modification.</span></span>  
  
 <span data-ttu-id="710ce-109">**Délai d'expiration de la transaction après**</span><span class="sxs-lookup"><span data-stu-id="710ce-109">**Transaction time-out after**</span></span>  
 <span data-ttu-id="710ce-110">Définit une valeur de délai d'expiration pour le Concepteur de bases de données et de tables.</span><span class="sxs-lookup"><span data-stu-id="710ce-110">Sets a time-out value for the table designer.</span></span>  
  
 <span data-ttu-id="710ce-111">**Générer automatiquement des scripts de modification**</span><span class="sxs-lookup"><span data-stu-id="710ce-111">**Auto generate change scripts**</span></span>  
 <span data-ttu-id="710ce-112">Crée automatiquement un script pour implémenter les modifications définies dans le Concepteur de bases de données et de tables.</span><span class="sxs-lookup"><span data-stu-id="710ce-112">Automatically creates a script to implement the changes defined in the table designer.</span></span>  
  
 <span data-ttu-id="710ce-113">**Avertir en cas de clés primaires Null**</span><span class="sxs-lookup"><span data-stu-id="710ce-113">**Warn on null primary keys**</span></span>  
 <span data-ttu-id="710ce-114">Affiche une boîte de dialogue d'avertissement lorsqu'un champ sélectionné pour une clé primaire peut contenir des valeurs Null.</span><span class="sxs-lookup"><span data-stu-id="710ce-114">Provides a warning dialog box when a field that is selected for a primary key can contain null values.</span></span>  
  
 <span data-ttu-id="710ce-115">**Signaler les différences de détection**</span><span class="sxs-lookup"><span data-stu-id="710ce-115">**Warn about difference detection**</span></span>  
 <span data-ttu-id="710ce-116">Si vous activez cette case à cocher, lorsque vous enregistrerez vos modifications, un message dressera la liste des conflits entre vos modifications et les modifications apportées par un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="710ce-116">If you check this box, when you save the changes, a message box will list any conflicts between your changes and changes that were made by another user.</span></span>  
  
 <span data-ttu-id="710ce-117">**Signaler les tables affectées**</span><span class="sxs-lookup"><span data-stu-id="710ce-117">**Warn about tables affected**</span></span>  
 <span data-ttu-id="710ce-118">Affiche une boîte de dialogue d'avertissement répertoriant les tables affectées par l'action et demande une confirmation de votre part.</span><span class="sxs-lookup"><span data-stu-id="710ce-118">Provides a warning dialog box that lists the tables to be affected by the action and prompts for confirmation.</span></span>  
  
 <span data-ttu-id="710ce-119">**Empêcher l'enregistrement de modifications qui nécessitent une recréation de la table**</span><span class="sxs-lookup"><span data-stu-id="710ce-119">**Prevent saving changes that require table re-creation**</span></span>  
 <span data-ttu-id="710ce-120">Empêche un utilisateur d'apporter des modifications qui requièrent la récréation de la table.</span><span class="sxs-lookup"><span data-stu-id="710ce-120">Prevents a user from making changes that require re-creating the table.</span></span> <span data-ttu-id="710ce-121">Les actions suivantes peuvent nécessiter la recréation d'une table :</span><span class="sxs-lookup"><span data-stu-id="710ce-121">The following actions might require a table to be re-created:</span></span>  
  
-   <span data-ttu-id="710ce-122">Ajout d'une nouvelle colonne au milieu de la table</span><span class="sxs-lookup"><span data-stu-id="710ce-122">Adding a new column to the middle of the table</span></span>  
  
-   <span data-ttu-id="710ce-123">Suppression d'une colonne</span><span class="sxs-lookup"><span data-stu-id="710ce-123">Dropping a column</span></span>  
  
-   <span data-ttu-id="710ce-124">Modification de la possibilité de valeur nulle d'une colonne</span><span class="sxs-lookup"><span data-stu-id="710ce-124">Changing column nullability</span></span>  
  
-   <span data-ttu-id="710ce-125">Modification de l'ordre des colonnes</span><span class="sxs-lookup"><span data-stu-id="710ce-125">Changing the order of the columns</span></span>  
  
-   <span data-ttu-id="710ce-126">Modification du type de données d'une colonne</span><span class="sxs-lookup"><span data-stu-id="710ce-126">Changing the data type of a column</span></span>  
  
 <span data-ttu-id="710ce-127">**Vue de table par défaut**</span><span class="sxs-lookup"><span data-stu-id="710ce-127">**Default table view**</span></span>  
 <span data-ttu-id="710ce-128">Sélectionnez le mode d'affichage des tables dans les concepteurs :</span><span class="sxs-lookup"><span data-stu-id="710ce-128">Select the way you want to see tables in the designers:</span></span>  
  
-   <span data-ttu-id="710ce-129">**Standard**</span><span class="sxs-lookup"><span data-stu-id="710ce-129">**Standard**</span></span>  
  
     <span data-ttu-id="710ce-130">Affiche l'en-tête de la table, tous les noms des colonnes, les types de données et le paramètre Autoriser les valeurs NULL.</span><span class="sxs-lookup"><span data-stu-id="710ce-130">Shows the table header, all column names, data types, and the Allow Nulls setting.</span></span>  
  
-   <span data-ttu-id="710ce-131">**Noms de colonnes**</span><span class="sxs-lookup"><span data-stu-id="710ce-131">**Column Names**</span></span>  
  
     <span data-ttu-id="710ce-132">Affiche les noms des colonnes.</span><span class="sxs-lookup"><span data-stu-id="710ce-132">Shows the column names.</span></span>  
  
-   <span data-ttu-id="710ce-133">**Clé**</span><span class="sxs-lookup"><span data-stu-id="710ce-133">**Key**</span></span>  
  
     <span data-ttu-id="710ce-134">Affiche l'en-tête de la table et les colonnes clés primaires.</span><span class="sxs-lookup"><span data-stu-id="710ce-134">Shows the table header and the primary key columns.</span></span>  
  
-   <span data-ttu-id="710ce-135">**Nom uniquement**</span><span class="sxs-lookup"><span data-stu-id="710ce-135">**Name Only**</span></span>  
  
     <span data-ttu-id="710ce-136">Affiche uniquement l'en-tête de la table avec son nom.</span><span class="sxs-lookup"><span data-stu-id="710ce-136">Shows only the table header with it's name.</span></span>  
  
-   <span data-ttu-id="710ce-137">**Personnalisée**</span><span class="sxs-lookup"><span data-stu-id="710ce-137">**Custom**</span></span>  
  
     <span data-ttu-id="710ce-138">Permet de choisir les colonnes à afficher.</span><span class="sxs-lookup"><span data-stu-id="710ce-138">Allows you to choose which columns to view.</span></span>  
  
 <span data-ttu-id="710ce-139">**Lancer la boîte de dialogue Ajouter une table sur Nouveau schéma**</span><span class="sxs-lookup"><span data-stu-id="710ce-139">**Launch add table dialog on new diagram**</span></span>  
 <span data-ttu-id="710ce-140">Ouvre automatiquement la boîte de dialogue **Ajouter une table** à l’ouverture des concepteurs.</span><span class="sxs-lookup"><span data-stu-id="710ce-140">Automatically opens the **Add Table** dialog box when the designers open.</span></span>  
  
  
