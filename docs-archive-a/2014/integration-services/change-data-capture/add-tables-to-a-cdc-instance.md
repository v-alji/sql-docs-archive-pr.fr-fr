---
title: Ajouter des tables à une instance CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- addTabs
ms.assetid: ad260e19-c021-4035-9311-c02fc96ceaea
author: chugugrace
ms.author: chugu
ms.openlocfilehash: edcd84db9e3c464334d407987cb3567f78edd44e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696004"
---
# <a name="add-tables-to-a-cdc-instance"></a><span data-ttu-id="21a83-102">Ajouter des tables à une instance de capture de données modifiées</span><span class="sxs-lookup"><span data-stu-id="21a83-102">Add Tables to a CDC Instance</span></span>
  <span data-ttu-id="21a83-103">Utilisez la boîte de dialogue Sélection de table pour ajouter des tables supplémentaires de la source Oracle à l'instance de capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="21a83-103">Use the Table Selection dialog box to add additional tables from the Oracle source to the CDC instance.</span></span> <span data-ttu-id="21a83-104">Les tables sélectionnées sont ajoutées à la liste sous l'onglet **Tables** de l'éditeur de propriétés.</span><span class="sxs-lookup"><span data-stu-id="21a83-104">The tables selected are added to the list in the **Tables** tab of the Properties editor.</span></span>  
  
 <span data-ttu-id="21a83-105">Par défaut, aucune table n'est incluse dans la liste des tables de cette boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="21a83-105">By default, no tables are included in the list of tables in this dialog box.</span></span> <span data-ttu-id="21a83-106">Vous pouvez cocher la case **(Sélectionner tout)** ou rechercher des tables spécifiques.</span><span class="sxs-lookup"><span data-stu-id="21a83-106">You can select the **(Select All)** check box or search for specific tables.</span></span>  
  
 <span data-ttu-id="21a83-107">**Pour rechercher des tables spécifiques**</span><span class="sxs-lookup"><span data-stu-id="21a83-107">**To search for specific tables**</span></span>  
 <span data-ttu-id="21a83-108">Entrez les critères de recherche comme suit, puis cliquez sur **Rechercher**:</span><span class="sxs-lookup"><span data-stu-id="21a83-108">Enter search criteria as follows, and then click **Search**:</span></span>  
  
-   <span data-ttu-id="21a83-109">**Schéma**: dans la liste, sélectionnez un schéma de base de données.</span><span class="sxs-lookup"><span data-stu-id="21a83-109">**Schema**: Select a database schema from the list.</span></span> <span data-ttu-id="21a83-110">Seules les tables qui ont ce schéma seront incluses dans la liste.</span><span class="sxs-lookup"><span data-stu-id="21a83-110">Only tables that have that schema will be included in the list.</span></span>  
  
-   <span data-ttu-id="21a83-111">**Modèle de nom de table**: entrez n'importe quelle chaîne de caractères.</span><span class="sxs-lookup"><span data-stu-id="21a83-111">**Table Name Pattern**: Enter any string of characters.</span></span> <span data-ttu-id="21a83-112">Seules les tables qui incluent la chaîne de caractères entrée s'affichent.</span><span class="sxs-lookup"><span data-stu-id="21a83-112">Only tables that include the character string entered are displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="21a83-113">Vous pouvez entrer des critères dans un des deux champs ou dans les deux.</span><span class="sxs-lookup"><span data-stu-id="21a83-113">You can enter criteria in one or both of these fields.</span></span>  
  
-   <span data-ttu-id="21a83-114">**Afficher les 1 000 premières tables correspondantes**: par défaut cette case à cocher est activée.</span><span class="sxs-lookup"><span data-stu-id="21a83-114">**Display first 1000 matching tables**: By default this check box is selected.</span></span> <span data-ttu-id="21a83-115">Elle limite l'affichage aux 1 000 premières tables correspondantes.</span><span class="sxs-lookup"><span data-stu-id="21a83-115">It limits the display to the first 1000 matching tables.</span></span> <span data-ttu-id="21a83-116">Si vous désactivez la case à cocher, toutes les tables qui correspondent aux critères s'affichent.</span><span class="sxs-lookup"><span data-stu-id="21a83-116">If you clear the check box, all tables that match the criteria are displayed.</span></span> <span data-ttu-id="21a83-117">S'il existe un grand nombre de tables, l'affichage de la liste peut prendre beaucoup de temps.</span><span class="sxs-lookup"><span data-stu-id="21a83-117">If there are a large number of tables, it may take a long time to display the list.</span></span>  
  
 <span data-ttu-id="21a83-118">**Pour sélectionner les tables à inclure dans l'instance CDC**</span><span class="sxs-lookup"><span data-stu-id="21a83-118">**To select tables to include in the CDC instance**</span></span>  
 <span data-ttu-id="21a83-119">Cochez la case en regard d’une table à inclure, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="21a83-119">Click the check box next to any of the tables you want to include, and then click **Add**.</span></span> <span data-ttu-id="21a83-120">Les tables sont ajoutées à la liste dans la page **Sélectionner des tables et des colonnes** de l'Assistant Nouvelle instance.</span><span class="sxs-lookup"><span data-stu-id="21a83-120">The tables are added to the list in the New Instance Wizard **Select Tables and Columns** page.</span></span>  
  
 <span data-ttu-id="21a83-121">Cliquez sur **Fermer** pour fermer la boîte de dialogue sans ajouter de table.</span><span class="sxs-lookup"><span data-stu-id="21a83-121">Click **Close** to close the dialog box without adding any tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="21a83-122">Si vous sélectionnez une table qui inclut un type de données non pris en charge, un message d'erreur s'affiche et la table n'est pas incluse.</span><span class="sxs-lookup"><span data-stu-id="21a83-122">If you select a table that includes a non-supported data type, you will see an error message and the table will not be included.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="21a83-123">Vous pouvez afficher la liste des tables dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="21a83-123">You can view the list of tables in the viewer.</span></span> <span data-ttu-id="21a83-124">Lorsque vous utilisez la visionneuse, les informations sont en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="21a83-124">When using the viewer the information is read only.</span></span> <span data-ttu-id="21a83-125">La visionneuse inclut également la liste des colonnes capturées dans la table.</span><span class="sxs-lookup"><span data-stu-id="21a83-125">The viewer also includes a list of the captured columns in the table.</span></span> <span data-ttu-id="21a83-126">Pour plus d'informations sur l'accès à la visionneuse, consultez [How to Manage a CDC Instance](manage-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="21a83-126">For information on how to access the viewer, see [How to Manage a CDC Instance](manage-a-cdc-instance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21a83-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="21a83-127">See Also</span></span>  
 <span data-ttu-id="21a83-128">[Procédure : modifier les propriétés d'une instance de capture de données modifiées](how-to-edit-the-cdc-instance-properties.md) </span><span class="sxs-lookup"><span data-stu-id="21a83-128">[How to Edit the CDC Instance Properties](how-to-edit-the-cdc-instance-properties.md) </span></span>  
 <span data-ttu-id="21a83-129">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span><span class="sxs-lookup"><span data-stu-id="21a83-129">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span></span>  
 [<span data-ttu-id="21a83-130">Sélectionner des tables Oracle pour capturer des modifications</span><span class="sxs-lookup"><span data-stu-id="21a83-130">Select Oracle Tables for Capturing Changes</span></span>](select-oracle-tables-for-capturing-changes.md)  
  
  
