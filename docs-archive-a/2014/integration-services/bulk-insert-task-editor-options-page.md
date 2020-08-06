---
title: Éditeur de tâche d’insertion en bloc (page Options) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.bulkinserttask.options.f1
helpviewer_keywords:
- Bulk Insert Task Editor
ms.assetid: b3702811-3eb8-4b28-9190-5ae7a1a7bb6f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1751d1e0ac01d5459a8c76e6a48626c2ad6deafd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706671"
---
# <a name="bulk-insert-task-editor-options-page"></a><span data-ttu-id="93078-102">Éditeur de tâche d'insertion en bloc (page Options)</span><span class="sxs-lookup"><span data-stu-id="93078-102">Bulk Insert Task Editor (Options Page)</span></span>
  <span data-ttu-id="93078-103">Utilisez la page **Options** de la boîte de dialogue **Éditeur de tâche d'insertion en bloc** afin de définir les propriétés de l'opération d'insertion en bloc.</span><span class="sxs-lookup"><span data-stu-id="93078-103">Use the **Options** page of the **Bulk Insert Task Editor** dialog box to set properties for the bulk insert operation.</span></span> <span data-ttu-id="93078-104">La tâche d’insertion en bloc copie des volumes importants de données dans une table ou une vue [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93078-104">The Bulk Insert task copies large amounts of data into a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table or view.</span></span>  
  
 <span data-ttu-id="93078-105">Pour en savoir plus sur l’utilisation des insertions en bloc, consultez [Tâche d’insertion en bloc](control-flow/bulk-insert-task.md) et [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="93078-105">To learn about working with bulk inserts, see [Bulk Insert Task](control-flow/bulk-insert-task.md) and [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
## <a name="options"></a><span data-ttu-id="93078-106">Options</span><span class="sxs-lookup"><span data-stu-id="93078-106">Options</span></span>  
 <span data-ttu-id="93078-107">**CodePage**</span><span class="sxs-lookup"><span data-stu-id="93078-107">**CodePage**</span></span>  
 <span data-ttu-id="93078-108">Permet d'indiquer la page de codes des données dans le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="93078-108">Specify the code page of the data in the data file.</span></span>  
  
 <span data-ttu-id="93078-109">**DataFileType**</span><span class="sxs-lookup"><span data-stu-id="93078-109">**DataFileType**</span></span>  
 <span data-ttu-id="93078-110">Permet d'indiquer la valeur correspondant au type de données à utiliser lors d'une opération de chargement.</span><span class="sxs-lookup"><span data-stu-id="93078-110">Specify the data-type value to use in the load operation.</span></span>  
  
 <span data-ttu-id="93078-111">**BatchSize**</span><span class="sxs-lookup"><span data-stu-id="93078-111">**BatchSize**</span></span>  
 <span data-ttu-id="93078-112">Permet d'indiquer le nombre de lignes contenues dans un traitement.</span><span class="sxs-lookup"><span data-stu-id="93078-112">Specify the number of rows in a batch.</span></span> <span data-ttu-id="93078-113">La valeur par défaut correspond à la totalité du fichier de données.</span><span class="sxs-lookup"><span data-stu-id="93078-113">The default is the entire data file.</span></span> <span data-ttu-id="93078-114">Si vous attribuez à **BatchSize** la valeur zéro, les données sont chargées dans un traitement unique.</span><span class="sxs-lookup"><span data-stu-id="93078-114">If you set **BatchSize** to zero, the data is loaded in a single batch.</span></span>  
  
 <span data-ttu-id="93078-115">**LastRow**</span><span class="sxs-lookup"><span data-stu-id="93078-115">**LastRow**</span></span>  
 <span data-ttu-id="93078-116">Permet de spécifier la dernière ligne à copier.</span><span class="sxs-lookup"><span data-stu-id="93078-116">Specify the last row to copy.</span></span>  
  
 <span data-ttu-id="93078-117">**FirstRow**</span><span class="sxs-lookup"><span data-stu-id="93078-117">**FirstRow**</span></span>  
 <span data-ttu-id="93078-118">Permet de spécifier la première ligne à partir de laquelle la copie doit commencer.</span><span class="sxs-lookup"><span data-stu-id="93078-118">Specify the first row from which to start copying.</span></span>  
  
 <span data-ttu-id="93078-119">**Options**</span><span class="sxs-lookup"><span data-stu-id="93078-119">**Options**</span></span>  
 |<span data-ttu-id="93078-120">Terme</span><span class="sxs-lookup"><span data-stu-id="93078-120">Term</span></span>|<span data-ttu-id="93078-121">Définition</span><span class="sxs-lookup"><span data-stu-id="93078-121">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="93078-122">**Contraintes de validation**</span><span class="sxs-lookup"><span data-stu-id="93078-122">**Check constraints**</span></span>|<span data-ttu-id="93078-123">Permet de vérifier les contraintes s'appliquant à la table et aux colonnes.</span><span class="sxs-lookup"><span data-stu-id="93078-123">Select to check the table and column constraints.</span></span>|  
|<span data-ttu-id="93078-124">**Conserver les valeurs NULL**</span><span class="sxs-lookup"><span data-stu-id="93078-124">**Keep nulls**</span></span>|<span data-ttu-id="93078-125">Permet de conserver les valeurs Null pendant l'opération d'insertion en bloc au lieu d'insérer des valeurs par défaut dans les colonnes vides.</span><span class="sxs-lookup"><span data-stu-id="93078-125">Select to retain null values during the bulk insert operation, instead of inserting any default values for empty columns.</span></span>|  
|<span data-ttu-id="93078-126">**Activer l’insertion d’identité**</span><span class="sxs-lookup"><span data-stu-id="93078-126">**Enable identity insert**</span></span>|<span data-ttu-id="93078-127">Permet d'insérer des valeurs existantes dans une colonne d'identité.</span><span class="sxs-lookup"><span data-stu-id="93078-127">Select to insert existing values into an identity column.</span></span>|  
|<span data-ttu-id="93078-128">**Verrou de table**</span><span class="sxs-lookup"><span data-stu-id="93078-128">**Table lock**</span></span>|<span data-ttu-id="93078-129">Permet de verrouiller la table lors de l'opération d'insertion en bloc.</span><span class="sxs-lookup"><span data-stu-id="93078-129">Select to lock the table during the bulk insert.</span></span>|  
|<span data-ttu-id="93078-130">**Exécuter les déclencheurs**</span><span class="sxs-lookup"><span data-stu-id="93078-130">**Fire triggers**</span></span>|<span data-ttu-id="93078-131">Lance tout déclencheur d'insertion, de mise à jour ou de suppression sur la table.</span><span class="sxs-lookup"><span data-stu-id="93078-131">Select to fire any insert, update, or delete triggers on the table.</span></span>|  
  
 <span data-ttu-id="93078-132">**SortedData**</span><span class="sxs-lookup"><span data-stu-id="93078-132">**SortedData**</span></span>  
 <span data-ttu-id="93078-133">Implique l'ajout de la clause ORDER BY dans l'instruction d'insertion en bloc.</span><span class="sxs-lookup"><span data-stu-id="93078-133">Specify the ORDER BY clause in the bulk insert statement.</span></span> <span data-ttu-id="93078-134">Le nom de colonne que vous fournissez doit être celui d'une colonne valide pour la table de destination.</span><span class="sxs-lookup"><span data-stu-id="93078-134">The column name that you supply must be a valid column in the destination table.</span></span> <span data-ttu-id="93078-135">Par défaut, il s’agit de `false`.</span><span class="sxs-lookup"><span data-stu-id="93078-135">The default is `false`.</span></span> <span data-ttu-id="93078-136">En d'autres termes, les données ne sont pas triées par une clause ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="93078-136">This means that the data is not sorted by an ORDER BY clause.</span></span>  
  
 <span data-ttu-id="93078-137">**MaxErrors**</span><span class="sxs-lookup"><span data-stu-id="93078-137">**MaxErrors**</span></span>  
 <span data-ttu-id="93078-138">Permet de spécifier le nombre maximal d'erreurs tolérées avant l'annulation de l'opération d'insertion en bloc.</span><span class="sxs-lookup"><span data-stu-id="93078-138">Specify the maximum number of errors that can occur before the bulk insert operation is canceled.</span></span> <span data-ttu-id="93078-139">La valeur 0 indique qu'un nombre illimité d'erreurs est autorisé.</span><span class="sxs-lookup"><span data-stu-id="93078-139">A value of 0 indicates that an infinite number of errors are allowed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="93078-140">Chaque ligne ne pouvant pas être importée par l'opération de chargement en masse est comptée comme une erreur.</span><span class="sxs-lookup"><span data-stu-id="93078-140">Each row that cannot be imported by the bulk load operation is counted as one error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93078-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="93078-141">See Also</span></span>  
 <span data-ttu-id="93078-142">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="93078-142">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="93078-143">[Éditeur de tâche d’insertion en bloc &#40;page général&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="93078-143">[Bulk Insert Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="93078-144">[Éditeur de tâche d’insertion en bloc &#40;page connexion&#41;](../../2014/integration-services/bulk-insert-task-editor-connection-page.md) </span><span class="sxs-lookup"><span data-stu-id="93078-144">[Bulk Insert Task Editor &#40;Connection Page&#41;](../../2014/integration-services/bulk-insert-task-editor-connection-page.md) </span></span>  
 <span data-ttu-id="93078-145">[Page Expressions](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="93078-145">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="93078-146">Flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="93078-146">Control Flow</span></span>](control-flow/control-flow.md)  
  
  
