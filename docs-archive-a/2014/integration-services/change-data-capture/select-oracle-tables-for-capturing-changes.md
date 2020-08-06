---
title: Sélectionner des tables Oracle pour capturer des modifications | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- selOraTabDia
ms.assetid: 2e295dc8-999d-4c4d-96cc-1519674b47a4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e9064789dce83ff7d3917ed026c861743142e048
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704343"
---
# <a name="select-oracle-tables-for-capturing-changes"></a><span data-ttu-id="a1586-102">Sélectionner des tables Oracle pour capturer des modifications</span><span class="sxs-lookup"><span data-stu-id="a1586-102">Select Oracle Tables for Capturing Changes</span></span>
  <span data-ttu-id="a1586-103">Cette boîte de dialogue permet de sélectionner les tables incluses dans l'instance de capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="a1586-103">Use this dialog box to select the tables that are included in the CDC instance.</span></span> <span data-ttu-id="a1586-104">Les tables sélectionnées sont ajoutées à la liste dans la page **Sélectionner des tables et des colonnes** de l'Assistant Nouvelle instance.</span><span class="sxs-lookup"><span data-stu-id="a1586-104">The tables selected are added to the list in the **Select Tables and Columns** page of the New Instance wizard.</span></span> <span data-ttu-id="a1586-105">Cette boîte de dialogue permet d'effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a1586-105">You can do the following in this dialog box.</span></span>  
  
 <span data-ttu-id="a1586-106">Par défaut, aucune table n'est incluse dans la liste des tables de cette boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="a1586-106">By default, no tables are included in the list of tables in this dialog box.</span></span> <span data-ttu-id="a1586-107">Vous pouvez activer la case à cocher en haut de la colonne de case à cocher pour sélectionner toutes les tables ou rechercher des tables spécifiques.</span><span class="sxs-lookup"><span data-stu-id="a1586-107">You can select the check box at the top of the check box column to select all of the tables or search for specific tables.</span></span>  
  
 <span data-ttu-id="a1586-108">**Pour rechercher des tables spécifiques**</span><span class="sxs-lookup"><span data-stu-id="a1586-108">**To search for specific tables**</span></span>  
 <span data-ttu-id="a1586-109">Entrez les critères de recherche comme suit, puis cliquez sur **Rechercher**:</span><span class="sxs-lookup"><span data-stu-id="a1586-109">Enter search criteria as follows, and then click **Search**:</span></span>  
  
-   <span data-ttu-id="a1586-110">**Schéma**: dans la liste, sélectionnez un schéma de base de données.</span><span class="sxs-lookup"><span data-stu-id="a1586-110">**Schema**: Select a database schema from the list.</span></span> <span data-ttu-id="a1586-111">Seules les tables qui ont ce schéma seront incluses dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a1586-111">Only tables that have that schema will be included in the list.</span></span>  
  
-   <span data-ttu-id="a1586-112">**Modèle de nom de table**: entrez n'importe quelle chaîne de caractères.</span><span class="sxs-lookup"><span data-stu-id="a1586-112">**Table Name Pattern**: Enter any string of characters.</span></span> <span data-ttu-id="a1586-113">Seules les tables qui incluent la chaîne de caractères entrée s'affichent.</span><span class="sxs-lookup"><span data-stu-id="a1586-113">Only tables that include the character string entered are displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a1586-114">Vous pouvez entrer des critères dans un des deux champs ou dans les deux.</span><span class="sxs-lookup"><span data-stu-id="a1586-114">You can enter criteria in one or both of these fields.</span></span>  
  
-   <span data-ttu-id="a1586-115">**Afficher les 1 000 premières tables correspondantes**: par défaut cette case à cocher est activée.</span><span class="sxs-lookup"><span data-stu-id="a1586-115">**Display first 1000 matching tables**: By default this check box is selected.</span></span> <span data-ttu-id="a1586-116">Elle limite l'affichage aux 1 000 premières tables correspondantes.</span><span class="sxs-lookup"><span data-stu-id="a1586-116">It limits the display to the first 1000 matching tables.</span></span> <span data-ttu-id="a1586-117">Si vous désactivez la case à cocher, toutes les tables qui correspondent aux critères s'affichent.</span><span class="sxs-lookup"><span data-stu-id="a1586-117">If you clear the check box, all tables that match the criteria are displayed.</span></span> <span data-ttu-id="a1586-118">S'il existe un grand nombre de tables, l'affichage de la liste peut prendre beaucoup de temps.</span><span class="sxs-lookup"><span data-stu-id="a1586-118">If there are a large number of tables, it may take a long time to display the list.</span></span>  
  
 <span data-ttu-id="a1586-119">**Pour sélectionner les tables à inclure dans l'instance CDC**</span><span class="sxs-lookup"><span data-stu-id="a1586-119">**To select tables to include in the CDC instance**</span></span>  
 <span data-ttu-id="a1586-120">Cochez la case en regard d’une table à inclure, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="a1586-120">Click the check box next to any of the tables you want to include, and then click **Add**.</span></span> <span data-ttu-id="a1586-121">Les tables sont ajoutées à la liste dans la page **Sélectionner des tables et des colonnes** de l'Assistant Nouvelle instance.</span><span class="sxs-lookup"><span data-stu-id="a1586-121">The tables are added to the list in the New Instance Wizard **Select Tables and Columns** page.</span></span>  
  
 <span data-ttu-id="a1586-122">Cliquez sur **Fermer** pour fermer la boîte de dialogue sans ajouter de table supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="a1586-122">Click **Close** to close the dialog box without adding any additional tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a1586-123">Si vous sélectionnez une table qui inclut un type de données non pris en charge, un message d'erreur s'affiche et la table n'est pas incluse.</span><span class="sxs-lookup"><span data-stu-id="a1586-123">If you select a table that includes a non-supported data type, you will see an error message and the table will not be included.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1586-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a1586-124">See Also</span></span>  
 <span data-ttu-id="a1586-125">[Procédure : créer l'instance SQL Server de base de données de modifications](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="a1586-125">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="a1586-126">Sélectionner des tables et des colonnes Oracle</span><span class="sxs-lookup"><span data-stu-id="a1586-126">Select Oracle Tables and Columns</span></span>](select-oracle-tables-and-columns.md)  
  
  
