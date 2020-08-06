---
title: Modifications détectées dans la base de données, boîte de dialogue (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.schema.databasechangesdetected
- vdtsql.chm:65543
- vdtsql.chm:65554
ms.assetid: 91f13086-371f-46a2-9f46-804c1415f3ed
author: stevestein
ms.author: sstein
ms.openlocfilehash: 91d58e812b93f207d592d245d094b0fbeddcce72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699066"
---
# <a name="database-changes-detected-dialog-box-visual-database-tools"></a><span data-ttu-id="7b23c-102">Modifications détectées dans la base de données, boîte de dialogue (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="7b23c-102">Database Changes Detected Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="7b23c-103">Cette boîte de dialogue apparaît si vous essayez d’enregistrer un diagramme de base de données ou des tables sélectionnées, mais certains des objets de la base de données qui seront affectés par l’action d’enregistrement sont devenus obsolètes pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="7b23c-103">This dialog appears if you attempt to save a database diagram or selected tables but some of the database objects that will be affected by the save action are out of date with the database.</span></span> <span data-ttu-id="7b23c-104">Le fait d'accepter les modifications indiquées dans cette boîte de dialogue met à jour la base de données pour qu'elle corresponde à votre schéma et écrase les modifications des autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7b23c-104">Accepting the changes shown in this dialog box updates the database to match your diagram and overwrites other users' changes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7b23c-105">Bien que vous ne puissiez pas annuler les modifications apportées à une table ou à un diagramme de base de données, les modifications ne seront enregistrées dans la base de données que lorsque vous enregistrerez la table ou le diagramme.</span><span class="sxs-lookup"><span data-stu-id="7b23c-105">Although you cannot undo changes made to a table or database diagram, the changes are not saved to the database until you save the table or diagram.</span></span> <span data-ttu-id="7b23c-106">Vous pouvez ignorer les modifications non enregistrées en choisissant **Non** et en fermant tous les schémas ouverts sans les enregistrer.</span><span class="sxs-lookup"><span data-stu-id="7b23c-106">You can discard any unsaved changes by choosing **No** and closing all open diagrams without saving them.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7b23c-107">Options</span><span class="sxs-lookup"><span data-stu-id="7b23c-107">Options</span></span>  
 <span data-ttu-id="7b23c-108">**Signaler les différences de détection**</span><span class="sxs-lookup"><span data-stu-id="7b23c-108">**Warn about difference detection**</span></span>  
 <span data-ttu-id="7b23c-109">Spécifie si cette boîte de dialogue apparaît à la prochaine tentative d’enregistrement du diagramme de base de données ou des tables sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="7b23c-109">Specify whether this dialog box appears the next time you attempt to save a database diagram or selected tables.</span></span> <span data-ttu-id="7b23c-110">Si l'option est activée, la boîte de dialogue continue d'apparaître chaque fois que vous enregistrez un schéma ou une table devenus obsolètes pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="7b23c-110">Checked means that the dialog box continues to appear each time you save a diagram or table that is out of date with the database.</span></span> <span data-ttu-id="7b23c-111">Si l'option est désactivée, elle signifie que la boîte de dialogue n'apparaît pas.</span><span class="sxs-lookup"><span data-stu-id="7b23c-111">Unchecked means that the dialog box does not appear.</span></span> <span data-ttu-id="7b23c-112">Par défaut, cette case est activée.</span><span class="sxs-lookup"><span data-stu-id="7b23c-112">By default, this box is checked.</span></span> <span data-ttu-id="7b23c-113">Si vous décochez cette option, vous pouvez la recocher dans la boîte de dialogue **Options** .</span><span class="sxs-lookup"><span data-stu-id="7b23c-113">If you uncheck this option, you can recheck it in the **Options** dialog box.</span></span>  
  
 <span data-ttu-id="7b23c-114">**Oui**</span><span class="sxs-lookup"><span data-stu-id="7b23c-114">**Yes**</span></span>  
 <span data-ttu-id="7b23c-115">Met à jour la base de données avec toutes les modifications indiquées dans la liste.</span><span class="sxs-lookup"><span data-stu-id="7b23c-115">Update the database with all the changes shown in the list.</span></span>  
  
 <span data-ttu-id="7b23c-116">**Non**</span><span class="sxs-lookup"><span data-stu-id="7b23c-116">**No**</span></span>  
 <span data-ttu-id="7b23c-117">Annule la demande d'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="7b23c-117">Cancel the save action.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7b23c-118">Pour actualiser votre schéma afin qu'il corresponde à la base de données, fermez-la sans enregistrer les modifications, cliquez avec le bouton droit sur le schéma dans l'Explorateur de serveurs et cliquez sur Actualiser, puis rouvrez le schéma.</span><span class="sxs-lookup"><span data-stu-id="7b23c-118">To refresh your diagram to match the database, close it without saving changes, right-click the diagram in Server Explorer and click Refresh, and then reopen the diagram.</span></span>  
  
 <span data-ttu-id="7b23c-119">**Enregistrer comme fichier texte**</span><span class="sxs-lookup"><span data-stu-id="7b23c-119">**Save Text File**</span></span>  
 <span data-ttu-id="7b23c-120">Affiche la boîte de dialogue **Enregistrer sous** qui permet de spécifier un emplacement pour un fichier texte contenant une liste des modifications de la base de données.</span><span class="sxs-lookup"><span data-stu-id="7b23c-120">Display the **Save As** dialog box, letting you specify a location for a text file containing a list of the database changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b23c-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7b23c-121">See Also</span></span>  
 <span data-ttu-id="7b23c-122">[Rapprocher un schéma de base de données avec une base de données modifiée &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7b23c-122">[Reconcile a Database Diagram with a Modified Database &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="7b23c-123">Environnements multi-utilisateurs &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="7b23c-123">Multiuser Environments &#40;Visual Database Tools&#41;</span></span>](multiuser-environments-visual-database-tools.md)  
  
  
