---
title: Validation des données (Complément MDS pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 71eda98f-01a4-4fff-8246-be3133782523
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f8e97ff6481996b2e16436e1f78478bd234fe6ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605529"
---
# <a name="validating-data-mds-add-in-for-excel"></a><span data-ttu-id="4e931-102">Validation des données (Complément MDS pour Excel)</span><span class="sxs-lookup"><span data-stu-id="4e931-102">Validating Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="4e931-103">Dans le [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], lorsque vous publiez des données, deux types de validation ont lieu :</span><span class="sxs-lookup"><span data-stu-id="4e931-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], when you publish data, two types of validation take place:</span></span>  
  
-   <span data-ttu-id="4e931-104">Toutes les règles d'entreprise définies sont appliquées aux données.</span><span class="sxs-lookup"><span data-stu-id="4e931-104">Any defined business rules are applied to the data.</span></span>  
  
-   <span data-ttu-id="4e931-105">Les données sont comparées aux valeurs d'attribut autorisées (par exemple, le nombre de caractères ou le type de données).</span><span class="sxs-lookup"><span data-stu-id="4e931-105">Data is checked against allowed attribute values (for example, number of characters or type of data).</span></span>  
  
 <span data-ttu-id="4e931-106">Dans chaque cas, les données valides sont publiées dans le référentiel MDS.</span><span class="sxs-lookup"><span data-stu-id="4e931-106">In each case, valid data is published to the MDS repository.</span></span> <span data-ttu-id="4e931-107">Les données non valides sont mises en surbrillance et les détails de l'erreur peuvent être affichés dans les colonnes d'état.</span><span class="sxs-lookup"><span data-stu-id="4e931-107">Data that is not valid is highlighted, and details of the error can be shown in status columns.</span></span>  
  
## <a name="when-validation-occurs"></a><span data-ttu-id="4e931-108">Lorsque la validation a lieu</span><span class="sxs-lookup"><span data-stu-id="4e931-108">When Validation Occurs</span></span>  
 <span data-ttu-id="4e931-109">Dans [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], la validation a lieu lorsque vous publiez des données nouvelles ou modifiées, ou lorsque vous appliquez manuellement des règles d'entreprise.</span><span class="sxs-lookup"><span data-stu-id="4e931-109">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], validation occurs when you publish new or changed data, or when you manually apply business rules.</span></span>  
  
 <span data-ttu-id="4e931-110">Lorsque les règles d'entreprise échouent, les données sont tout de même publiées dans le référentiel MDS.</span><span class="sxs-lookup"><span data-stu-id="4e931-110">When business rules fail, the data is still published to the MDS repository.</span></span> <span data-ttu-id="4e931-111">Lorsque la validation d'entrée échoue, les données ne sont pas publiées dans le référentiel.</span><span class="sxs-lookup"><span data-stu-id="4e931-111">When input validation fails, the data is not published to the repository.</span></span>  
  
## <a name="validation-statuses"></a><span data-ttu-id="4e931-112">États de validation</span><span class="sxs-lookup"><span data-stu-id="4e931-112">Validation Statuses</span></span>  
 <span data-ttu-id="4e931-113">Dans le [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], les états de validation suivants sont possibles.</span><span class="sxs-lookup"><span data-stu-id="4e931-113">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], the following validation statuses are possible.</span></span>  
  
|<span data-ttu-id="4e931-114">Statut</span><span class="sxs-lookup"><span data-stu-id="4e931-114">Status</span></span>|<span data-ttu-id="4e931-115">Description</span><span class="sxs-lookup"><span data-stu-id="4e931-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="4e931-116">Error</span><span class="sxs-lookup"><span data-stu-id="4e931-116">Error</span></span>|<span data-ttu-id="4e931-117">Une ou plusieurs valeurs dans la ligne n'ont pas pu être validées par rapport aux règles d'entreprise définies par un administrateur MDS.</span><span class="sxs-lookup"><span data-stu-id="4e931-117">One or more values in the row failed validation against business rules defined by an MDS administrator.</span></span>|  
|<span data-ttu-id="4e931-118">Non validé</span><span class="sxs-lookup"><span data-stu-id="4e931-118">Not Validated</span></span>|<span data-ttu-id="4e931-119">Les valeurs dans la ligne n'ont pas encore été validées par rapport aux règles d'entreprise.</span><span class="sxs-lookup"><span data-stu-id="4e931-119">Values in the row have not yet been validated against business rules.</span></span>|  
|<span data-ttu-id="4e931-120">Succès</span><span class="sxs-lookup"><span data-stu-id="4e931-120">Success</span></span>|<span data-ttu-id="4e931-121">Toutes les valeurs dans la ligne ont réussi la validation par rapport aux règles d'entreprise.</span><span class="sxs-lookup"><span data-stu-id="4e931-121">All values in the row have passed validation against business rules.</span></span>|  
  
## <a name="input-statuses"></a><span data-ttu-id="4e931-122">États d'entrée</span><span class="sxs-lookup"><span data-stu-id="4e931-122">Input Statuses</span></span>  
 <span data-ttu-id="4e931-123">Dans le [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], les états d’entrée suivants sont possibles :</span><span class="sxs-lookup"><span data-stu-id="4e931-123">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], the following input statuses are possible</span></span>  
  
|<span data-ttu-id="4e931-124">Statut</span><span class="sxs-lookup"><span data-stu-id="4e931-124">Status</span></span>|<span data-ttu-id="4e931-125">Description</span><span class="sxs-lookup"><span data-stu-id="4e931-125">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="4e931-126">Error</span><span class="sxs-lookup"><span data-stu-id="4e931-126">Error</span></span>|<span data-ttu-id="4e931-127">Une ou plusieurs valeurs dans la ligne ne répondent pas à la configuration requise, notamment en termes de longueur ou de type de données.</span><span class="sxs-lookup"><span data-stu-id="4e931-127">One or more values in the row don't meet system requirements like length or data type.</span></span> <span data-ttu-id="4e931-128">La valeur n'est pas mise à jour dans le référentiel MDS.</span><span class="sxs-lookup"><span data-stu-id="4e931-128">The value is not updated in the MDS repository.</span></span>|  
|<span data-ttu-id="4e931-129">Nouvelle ligne</span><span class="sxs-lookup"><span data-stu-id="4e931-129">New Row</span></span>|<span data-ttu-id="4e931-130">Les valeurs dans la ligne n'ont pas encore été publiées dans le référentiel MDS.</span><span class="sxs-lookup"><span data-stu-id="4e931-130">The values in the row have not yet been published to the MDS repository.</span></span>|  
|<span data-ttu-id="4e931-131">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="4e931-131">Read Only</span></span>|<span data-ttu-id="4e931-132">L'utilisateur connecté dispose d'autorisations en lecture seule sur une ou plusieurs valeurs dans la ligne et les valeurs ne peuvent pas être mises à jour.</span><span class="sxs-lookup"><span data-stu-id="4e931-132">The logged in user has Read-only permissions to one or more values in the row and the value(s) cannot be updated.</span></span>|  
|<span data-ttu-id="4e931-133">Inchangé</span><span class="sxs-lookup"><span data-stu-id="4e931-133">Unchanged</span></span>|<span data-ttu-id="4e931-134">Aucune valeur dans la ligne n'a été modifiée dans la feuille de calcul.</span><span class="sxs-lookup"><span data-stu-id="4e931-134">No values in the row have been changed in the worksheet.</span></span> <span data-ttu-id="4e931-135">Cela ne signifie pas que les valeurs contenues dans le référentiel n’ont pas changé ; pour obtenir les données les plus récentes dans la feuille, dans le groupe **Se connecter et charger** , cliquez **Charger ou actualiser**.</span><span class="sxs-lookup"><span data-stu-id="4e931-135">This does not mean the values in the repository have not changed; to get the latest data in the sheet, in the **Connect and Load** group, click **Load or Refresh**.</span></span><br /><br /> <span data-ttu-id="4e931-136">Il s'agit du paramètre par défaut pour chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="4e931-136">This is the default setting for each row.</span></span>|  
  
## <a name="related-tasks"></a><span data-ttu-id="4e931-137">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="4e931-137">Related Tasks</span></span>  
  
|<span data-ttu-id="4e931-138">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="4e931-138">Task Description</span></span>|<span data-ttu-id="4e931-139">Rubrique</span><span class="sxs-lookup"><span data-stu-id="4e931-139">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="4e931-140">Déterminez les valeurs qui ne respectent pas les règles d'entreprise définies.</span><span class="sxs-lookup"><span data-stu-id="4e931-140">Determine which values do not pass the defined business rules.</span></span>|[<span data-ttu-id="4e931-141">Appliquer des règles d’entreprise &#40;Complément MDS pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4e931-141">Apply Business Rules &#40;MDS Add-in for Excel&#41;</span></span>](apply-business-rules-mds-add-in-for-excel.md)|  
|<span data-ttu-id="4e931-142">Pour aider à corriger les erreurs de validation, affichez toutes les transactions qui ont eu lieu pour un membre.</span><span class="sxs-lookup"><span data-stu-id="4e931-142">To help correct validation errors, view all transactions that have taken place for a member.</span></span>|[<span data-ttu-id="4e931-143">Afficher toutes les annotations ou transactions pour un membre &#40;Complément MDS pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4e931-143">View All Annotations or Transactions for a Member &#40;MDS Add-in for Excel&#41;</span></span>](view-all-annotations-or-transactions-for-a-member-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="4e931-144">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="4e931-144">Related Content</span></span>  
  
-   [<span data-ttu-id="4e931-145">Publication des Complément MDS pour Excel de &#40;de données&#41;</span><span class="sxs-lookup"><span data-stu-id="4e931-145">Publishing Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-importing-data-from-excel-mds-add-in-for-excel.md)  
  
  
