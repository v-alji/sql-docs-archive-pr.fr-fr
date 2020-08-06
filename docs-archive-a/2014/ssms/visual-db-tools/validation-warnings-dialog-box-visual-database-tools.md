---
title: Avertissements de validation, boîte de dialogue (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:65556
- vdt.dlgbox.validationwarnings
ms.assetid: fc76e234-ec9c-4a19-a65b-cb558ec8268e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4f94c3ae91e077af853db949847bc8448f6a4753
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610918"
---
# <a name="validation-warnings-dialog-box-visual-database-tools"></a><span data-ttu-id="16034-102">Avertissements de validation, boîte de dialogue (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="16034-102">Validation Warnings Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="16034-103">Cette boîte de dialogue apparaît si vous tentez d'enregistrer des modifications ayant des effets secondaires potentiellement préjudiciables, ou si l'opération de validation de la base de données risque d'échouer.</span><span class="sxs-lookup"><span data-stu-id="16034-103">This dialog box appears if you attempt to save modifications with potentially damaging side effects, or if the database commit operation is likely to fail.</span></span> <span data-ttu-id="16034-104">Cette boîte de dialogue indique quels pourraient être ces effets secondaires ou la raison pour laquelle l'opération de validation pourrait échouer.</span><span class="sxs-lookup"><span data-stu-id="16034-104">This dialog box indicates what those side effects might be or why the commit operation might fail.</span></span> <span data-ttu-id="16034-105">Elle vous donne la possibilité de continuer la modification ou d'annuler l'opération.</span><span class="sxs-lookup"><span data-stu-id="16034-105">It gives you the chance to continue with the modification or cancel the operation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="16034-106">Cette boîte de dialogue apparaît lorsque vous tentez de transmettre vos modifications à la base de données lors de l'enregistrement d'un script de modification.</span><span class="sxs-lookup"><span data-stu-id="16034-106">This dialog box appears when you attempt to transmit your modifications to the database or when you save a change script.</span></span>  
  
 <span data-ttu-id="16034-107">La boîte de dialogue peut apparaître pour l'une de ces raisons :</span><span class="sxs-lookup"><span data-stu-id="16034-107">The dialog box can appear for any of these reasons:</span></span>  
  
-   <span data-ttu-id="16034-108">Il est possible que vous n'ayez pas les autorisations de la base de données pour valider toutes les modifications.</span><span class="sxs-lookup"><span data-stu-id="16034-108">You might not have database permissions to commit all the modifications.</span></span>  
  
-   <span data-ttu-id="16034-109">Vos modifications auraient pour résultat des colonnes dérivées mal constituées, des contraintes DEFAULT ou CHECK.</span><span class="sxs-lookup"><span data-stu-id="16034-109">Your modifications would result in improperly formed derived columns, default constraints, or check constraints.</span></span>  
  
-   <span data-ttu-id="16034-110">Une modification apportée à un type de donnée de la colonne peut provoquer une perte de données.</span><span class="sxs-lookup"><span data-stu-id="16034-110">A modification to a column's data type might cause data loss.</span></span>  
  
-   <span data-ttu-id="16034-111">Une modification aurait pour résultat un index supérieur à 900 octets.</span><span class="sxs-lookup"><span data-stu-id="16034-111">A modification would result in an index greater than 900 bytes.</span></span>  
  
-   <span data-ttu-id="16034-112">Une modification pourrait modifier une table ou une colonne contribuant à une vue liée à un schéma ou à une fonction définie par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="16034-112">A modification would change a table or column contributing to a schema-bound view or user-defined function.</span></span>  
  
-   <span data-ttu-id="16034-113">Une modification aurait pour résultat la recréation d'une table ayant un ou plusieurs déclencheurs chiffrés ; les déclencheurs seront supprimés.</span><span class="sxs-lookup"><span data-stu-id="16034-113">A modification would result in the re-creation of a table that has one or more encrypted triggers; the triggers will be dropped.</span></span>  
  
-   <span data-ttu-id="16034-114">Vos modifications suspendront les paramètres remarquables de ANSI_NULLS ou ANSI_PADDING ou les deux pour les colonnes dans une table.</span><span class="sxs-lookup"><span data-stu-id="16034-114">Your modifications will yield noteworthy settings of ANSI_NULLS or ANSI_PADDING or both for the columns within one table.</span></span>  
  
## <a name="options"></a><span data-ttu-id="16034-115">Options</span><span class="sxs-lookup"><span data-stu-id="16034-115">Options</span></span>  
 <span data-ttu-id="16034-116">**Oui**</span><span class="sxs-lookup"><span data-stu-id="16034-116">**Yes**</span></span>  
 <span data-ttu-id="16034-117">Continue l'opération et entraîne la génération du script de modification ou le transfert des modifications à la base de données.</span><span class="sxs-lookup"><span data-stu-id="16034-117">Proceed with the operation and generate the change script or transmit the modifications to the database.</span></span> <span data-ttu-id="16034-118">L'opération de validation peut encore échouer si vous n'avez pas les privilèges nécessaires pour modifier la base de données, ou si vos modifications ont pour résultat un index supérieur à 900 octets ou une colonne calculée, une contrainte DEFAULT ou une contrainte CHECK mal constituée.</span><span class="sxs-lookup"><span data-stu-id="16034-118">The commit operation can still fail if you do not have privileges to modify the database, if your modifications will result in an index greater than 900 bytes, or if your modifications will result in an improperly formed computed column, default constraint, or check constraint.</span></span>  
  
 <span data-ttu-id="16034-119">**Non**</span><span class="sxs-lookup"><span data-stu-id="16034-119">**No**</span></span>  
 <span data-ttu-id="16034-120">Annule la demande d'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="16034-120">Cancel the save action.</span></span>  
  
 <span data-ttu-id="16034-121">**Enregistrer comme fichier texte**</span><span class="sxs-lookup"><span data-stu-id="16034-121">**Save Text File**</span></span>  
 <span data-ttu-id="16034-122">Affiche la boîte de dialogue **Enregistrer sous** , où vous pouvez spécifier un emplacement pour un fichier texte contenant une liste des avertissements.</span><span class="sxs-lookup"><span data-stu-id="16034-122">Display the **Save As** dialog box, where you can specify a location for a text file containing a list of the warnings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16034-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="16034-123">See Also</span></span>  
 <span data-ttu-id="16034-124">[Concevoir des tables &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="16034-124">[Design Tables &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="16034-125">Rubriques de procédures relatives à la conception de requêtes et de vues &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="16034-125">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
