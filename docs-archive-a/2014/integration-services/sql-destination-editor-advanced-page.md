---
title: Éditeur de destination SQL (page avancé) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlserverdestadapter.advanced.f1
helpviewer_keywords:
- SQL Server Destination Editor
ms.assetid: 9b46bcf8-ddaf-4d7d-90a6-80bc19517e9b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ccf25ad888c93f694678a152417affe5c0e16091
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602201"
---
# <a name="sql-destination-editor-advanced-page"></a><span data-ttu-id="a84dd-102">Éditeur de destination SQL (page Avancé)</span><span class="sxs-lookup"><span data-stu-id="a84dd-102">SQL Destination Editor (Advanced Page)</span></span>
  <span data-ttu-id="a84dd-103">Utilisez la page **Avancé** de la boîte de dialogue **Éditeur de destination SQL** pour spécifier les options avancées pour l’insertion en bloc.</span><span class="sxs-lookup"><span data-stu-id="a84dd-103">Use the **Advanced** page of the **SQL Destination Editor** dialog box to specify advanced bulk insert options.</span></span>  
  
 <span data-ttu-id="a84dd-104">Pour en savoir plus sur la destination pour SQL Server, consultez [SQL Server Destination](data-flow/sql-server-destination.md).</span><span class="sxs-lookup"><span data-stu-id="a84dd-104">To learn more about the SQL Server destination, see [SQL Server Destination](data-flow/sql-server-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a84dd-105">Options</span><span class="sxs-lookup"><span data-stu-id="a84dd-105">Options</span></span>  
 <span data-ttu-id="a84dd-106">**Conserver l'identité**</span><span class="sxs-lookup"><span data-stu-id="a84dd-106">**Keep identity**</span></span>  
 <span data-ttu-id="a84dd-107">Spécifie si la tâche doit insérer des valeurs dans les colonnes d'identité.</span><span class="sxs-lookup"><span data-stu-id="a84dd-107">Specify whether the task should insert values into identity columns.</span></span> <span data-ttu-id="a84dd-108">La valeur par défaut de cette propriété est `False`.</span><span class="sxs-lookup"><span data-stu-id="a84dd-108">The default value of this property is `False`.</span></span>  
  
 <span data-ttu-id="a84dd-109">**Conserver les valeurs NULL**</span><span class="sxs-lookup"><span data-stu-id="a84dd-109">**Keep nulls**</span></span>  
 <span data-ttu-id="a84dd-110">Spécifie si la tâche doit conserver les valeurs NULL.</span><span class="sxs-lookup"><span data-stu-id="a84dd-110">Specify whether the task should keep null values.</span></span> <span data-ttu-id="a84dd-111">La valeur par défaut de cette propriété est `False`.</span><span class="sxs-lookup"><span data-stu-id="a84dd-111">The default value of this property is `False`.</span></span>  
  
 <span data-ttu-id="a84dd-112">**Verrou de table**</span><span class="sxs-lookup"><span data-stu-id="a84dd-112">**Table lock**</span></span>  
 <span data-ttu-id="a84dd-113">Spécifie si la table est verrouillée lors du chargement des données.</span><span class="sxs-lookup"><span data-stu-id="a84dd-113">Specify whether the table is locked when the data is loaded.</span></span> <span data-ttu-id="a84dd-114">La valeur par défaut de cette propriété est `True`.</span><span class="sxs-lookup"><span data-stu-id="a84dd-114">The default value of this property is `True`.</span></span>  
  
 <span data-ttu-id="a84dd-115">**Contraintes de validation**</span><span class="sxs-lookup"><span data-stu-id="a84dd-115">**Check constraints**</span></span>  
 <span data-ttu-id="a84dd-116">Spécifie si la tâche doit vérifier les contraintes.</span><span class="sxs-lookup"><span data-stu-id="a84dd-116">Specify whether the task should check constraints.</span></span> <span data-ttu-id="a84dd-117">La valeur par défaut de cette propriété est `True`.</span><span class="sxs-lookup"><span data-stu-id="a84dd-117">The default value of this property is `True`.</span></span>  
  
 <span data-ttu-id="a84dd-118">**Exécuter les déclencheurs**</span><span class="sxs-lookup"><span data-stu-id="a84dd-118">**Fire triggers**</span></span>  
 <span data-ttu-id="a84dd-119">Spécifie si l'insertion en bloc doit exécuter les déclencheurs sur les tables.</span><span class="sxs-lookup"><span data-stu-id="a84dd-119">Specify whether the bulk insert should fire triggers on tables.</span></span> <span data-ttu-id="a84dd-120">La valeur par défaut de cette propriété est `False`.</span><span class="sxs-lookup"><span data-stu-id="a84dd-120">The default value of this property is `False`.</span></span>  
  
 <span data-ttu-id="a84dd-121">**Première ligne**</span><span class="sxs-lookup"><span data-stu-id="a84dd-121">**First Row**</span></span>  
 <span data-ttu-id="a84dd-122">Spécifie la première ligne à insérer.</span><span class="sxs-lookup"><span data-stu-id="a84dd-122">Specify the first row to insert.</span></span> <span data-ttu-id="a84dd-123">La valeur par défaut de cette propriété est **-1**, ce qui signifie qu’aucune valeur ne lui a été assignée.</span><span class="sxs-lookup"><span data-stu-id="a84dd-123">The default value of this property is **-1**, indicating that no value has been assigned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a84dd-124">Effacez la zone de texte dans **l’Éditeur de destination SQL** pour indiquer que vous ne voulez pas assigner de valeur à cette propriété.</span><span class="sxs-lookup"><span data-stu-id="a84dd-124">Clear the text box in the **SQL Destination Editor** to indicate that you do not want to assign a value for this property.</span></span> <span data-ttu-id="a84dd-125">Utilisez -1 dans la fenêtre **Propriétés** , **l’Éditeur avancé**et le modèle objet.</span><span class="sxs-lookup"><span data-stu-id="a84dd-125">Use -1 in the **Properties** window, the **Advanced Editor**, and the object model.</span></span>  
  
 <span data-ttu-id="a84dd-126">**Dernière ligne**</span><span class="sxs-lookup"><span data-stu-id="a84dd-126">**Last Row**</span></span>  
 <span data-ttu-id="a84dd-127">Spécifie la dernière ligne à insérer.</span><span class="sxs-lookup"><span data-stu-id="a84dd-127">Specify the last row to insert.</span></span> <span data-ttu-id="a84dd-128">La valeur par défaut de cette propriété est **-1**, ce qui signifie qu’aucune valeur ne lui a été assignée.</span><span class="sxs-lookup"><span data-stu-id="a84dd-128">The default value of this property is **-1**, indicating that no value has been assigned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a84dd-129">Effacez la zone de texte dans **l’Éditeur de destination SQL** pour indiquer que vous ne voulez pas assigner de valeur à cette propriété.</span><span class="sxs-lookup"><span data-stu-id="a84dd-129">Clear the text box in the **SQL Destination Editor** to indicate that you do not want to assign a value for this property.</span></span> <span data-ttu-id="a84dd-130">Utilisez -1 dans la fenêtre **Propriétés** , **l’Éditeur avancé**et le modèle objet.</span><span class="sxs-lookup"><span data-stu-id="a84dd-130">Use -1 in the **Properties** window, the **Advanced Editor**, and the object model.</span></span>  
  
 <span data-ttu-id="a84dd-131">**Nombre maximum d'erreurs**</span><span class="sxs-lookup"><span data-stu-id="a84dd-131">**Maximum number of errors**</span></span>  
 <span data-ttu-id="a84dd-132">Spécifie le nombre d'erreurs au-delà duquel l'insertion en bloc s'arrête.</span><span class="sxs-lookup"><span data-stu-id="a84dd-132">Specify the number of errors that can occur before the bulk insert stops.</span></span> <span data-ttu-id="a84dd-133">La valeur par défaut de cette propriété est **-1**, ce qui signifie qu’aucune valeur ne lui a été assignée.</span><span class="sxs-lookup"><span data-stu-id="a84dd-133">The default value of this property is **-1**, indicating that no value has been assigned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a84dd-134">Effacez la zone de texte dans **l’Éditeur de destination SQL** pour indiquer que vous ne voulez pas assigner de valeur à cette propriété.</span><span class="sxs-lookup"><span data-stu-id="a84dd-134">Clear the text box in the **SQL Destination Editor** to indicate that you do not want to assign a value for this property.</span></span> <span data-ttu-id="a84dd-135">Utilisez -1 dans la fenêtre **Propriétés** , **l’Éditeur avancé**et le modèle objet.</span><span class="sxs-lookup"><span data-stu-id="a84dd-135">Use -1 in the **Properties** window, the **Advanced Editor**, and the object model.</span></span>  
  
 <span data-ttu-id="a84dd-136">**Délai d'expiration**</span><span class="sxs-lookup"><span data-stu-id="a84dd-136">**Timeout**</span></span>  
 <span data-ttu-id="a84dd-137">Spécifie le nombre de secondes pouvant s'écouler avant l'expiration de l'insertion en bloc.</span><span class="sxs-lookup"><span data-stu-id="a84dd-137">Specify the number of seconds to wait before the bulk insert stops because of a time-out.</span></span>  
  
 <span data-ttu-id="a84dd-138">**Ordre des colonnes**</span><span class="sxs-lookup"><span data-stu-id="a84dd-138">**Order columns**</span></span>  
 <span data-ttu-id="a84dd-139">Tapez le nom des colonnes de tri.</span><span class="sxs-lookup"><span data-stu-id="a84dd-139">Type the names of the sort columns.</span></span> <span data-ttu-id="a84dd-140">Chaque colonne peut être triée par ordre croissant ou décroissant.</span><span class="sxs-lookup"><span data-stu-id="a84dd-140">Each column can be sorted in ascending or descending order.</span></span> <span data-ttu-id="a84dd-141">Si vous utilisez plusieurs colonnes de tri, délimitez la liste par des virgules.</span><span class="sxs-lookup"><span data-stu-id="a84dd-141">If you use multiple sort columns, delimit the list with commas.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a84dd-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a84dd-142">See Also</span></span>  
 <span data-ttu-id="a84dd-143">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a84dd-143">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="a84dd-144">[Éditeur de destination SQL &#40;page Gestionnaire de connexions&#41;](../../2014/integration-services/sql-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="a84dd-144">[SQL Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/sql-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="a84dd-145">[Éditeur de destination SQL &#40;page Mappages&#41;](../../2014/integration-services/sql-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="a84dd-145">[SQL Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/sql-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="a84dd-146">Charger des données en masse à l'aide de la destination SQL Server</span><span class="sxs-lookup"><span data-stu-id="a84dd-146">Bulk Load Data by Using the SQL Server Destination</span></span>](data-flow/bulk-load-data-by-using-the-sql-server-destination.md)  
  
  
