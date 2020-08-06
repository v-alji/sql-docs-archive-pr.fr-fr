---
title: Séparateur de capture de données modifiées | Documents Microsoft
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.cdcsplitter.f1
ms.assetid: 167bc5c6-fa36-439d-987c-b20acd1a77e2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 45dd16602625b28d2ca7e16f2fa6b0d62294fe81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611200"
---
# <a name="cdc-splitter"></a><span data-ttu-id="9e90f-102">Séparateur de capture de données modifiées</span><span class="sxs-lookup"><span data-stu-id="9e90f-102">CDC Splitter</span></span>
  <span data-ttu-id="9e90f-103">Le séparateur de capture de données modifiées fractionne un flux de lignes de modification d'un flux de données de source CDC en flux de données distincts pour les opérations d'insertion, de mise à jour et de suppression.</span><span class="sxs-lookup"><span data-stu-id="9e90f-103">The CDC splitter splits a single flow of change rows from a CDC source data flow into different data flows for Insert, Update and Delete operations.</span></span> <span data-ttu-id="9e90f-104">Le flux de données est fractionné en fonction de la colonne requise `__$operation` et de ses valeurs standard dans les tables de modification de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9e90f-104">The data flow is split based on the required column `__$operation` and its standard values in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] change tables.</span></span>  
  
|<span data-ttu-id="9e90f-105">Valeur de l'opération</span><span class="sxs-lookup"><span data-stu-id="9e90f-105">Value of Operation</span></span>|<span data-ttu-id="9e90f-106">Output</span><span class="sxs-lookup"><span data-stu-id="9e90f-106">Output</span></span>|<span data-ttu-id="9e90f-107">Description</span><span class="sxs-lookup"><span data-stu-id="9e90f-107">Description</span></span>|  
|------------------------|------------|-----------------|  
|<span data-ttu-id="9e90f-108">1</span><span class="sxs-lookup"><span data-stu-id="9e90f-108">1</span></span>|<span data-ttu-id="9e90f-109">DELETE</span><span class="sxs-lookup"><span data-stu-id="9e90f-109">Delete</span></span>|<span data-ttu-id="9e90f-110">Ligne supprimée</span><span class="sxs-lookup"><span data-stu-id="9e90f-110">Deleted Row</span></span>|  
|<span data-ttu-id="9e90f-111">2</span><span class="sxs-lookup"><span data-stu-id="9e90f-111">2</span></span>|<span data-ttu-id="9e90f-112">Insérer</span><span class="sxs-lookup"><span data-stu-id="9e90f-112">Insert</span></span>|<span data-ttu-id="9e90f-113">Ligne insérée (non disponible en cas d’utilisation du mode de capture de données modifiées **Net avec fusion** )</span><span class="sxs-lookup"><span data-stu-id="9e90f-113">Inserted row (not available when using **Net with Merge** CDC mode)</span></span>|  
|<span data-ttu-id="9e90f-114">3</span><span class="sxs-lookup"><span data-stu-id="9e90f-114">3</span></span>|<span data-ttu-id="9e90f-115">Update</span><span class="sxs-lookup"><span data-stu-id="9e90f-115">Update</span></span>|<span data-ttu-id="9e90f-116">Ligne avant la mise à jour (disponible uniquement en cas d’utilisation du mode de capture de données modifiées **Tout avec les anciennes valeurs** )</span><span class="sxs-lookup"><span data-stu-id="9e90f-116">Before-update row (available only when using **All with Old Values** CDC mode)</span></span>|  
|<span data-ttu-id="9e90f-117">4</span><span class="sxs-lookup"><span data-stu-id="9e90f-117">4</span></span>|<span data-ttu-id="9e90f-118">Update</span><span class="sxs-lookup"><span data-stu-id="9e90f-118">Update</span></span>|<span data-ttu-id="9e90f-119">Ligne après la mise à jour (suit avant la mise à jour)</span><span class="sxs-lookup"><span data-stu-id="9e90f-119">After-update row (follows the Before-update)</span></span>|  
|<span data-ttu-id="9e90f-120">5</span><span class="sxs-lookup"><span data-stu-id="9e90f-120">5</span></span>|<span data-ttu-id="9e90f-121">Update</span><span class="sxs-lookup"><span data-stu-id="9e90f-121">Update</span></span>|<span data-ttu-id="9e90f-122">Ligne de fusion (disponible uniquement en cas d’utilisation du mode de capture de données modifiées **Net avec fusion** )</span><span class="sxs-lookup"><span data-stu-id="9e90f-122">Merge row (available only when using **Net with Merge** CDC mode)</span></span>|  
|<span data-ttu-id="9e90f-123">Autres</span><span class="sxs-lookup"><span data-stu-id="9e90f-123">Other</span></span>|<span data-ttu-id="9e90f-124">Error</span><span class="sxs-lookup"><span data-stu-id="9e90f-124">Error</span></span>||  
  
 <span data-ttu-id="9e90f-125">Vous pouvez utiliser le séparateur pour vous connecter aux sorties INSERT, DELETE et UPDATE afin d'effectuer d'autres opérations de traitement.</span><span class="sxs-lookup"><span data-stu-id="9e90f-125">You can use the splitter to connect to pre-defined INSERT, DELETE, and UPDATE outputs for further processing.</span></span>  
  
 <span data-ttu-id="9e90f-126">La transformation de séparateur de capture de données modifiées a une sortie standard et une sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="9e90f-126">The CDC Splitter transformation has one regular input and one error output.</span></span>  
  
## <a name="error-handling"></a><span data-ttu-id="9e90f-127">Gestion des erreurs</span><span class="sxs-lookup"><span data-stu-id="9e90f-127">Error Handling</span></span>  
 <span data-ttu-id="9e90f-128">La transformation de séparateur de capture de données modifiées a une sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="9e90f-128">The CDC Splitter transformation has an error output.</span></span> <span data-ttu-id="9e90f-129">Les lignes d'entrée avec une valeur de colonne $operation non valide sont considérées comme incorrectes et sont gérées conformément à la propriété **ErrorRowDisposition** de l'entrée.</span><span class="sxs-lookup"><span data-stu-id="9e90f-129">Input rows with an invalid value of the $operation column are considered erroneous and are handled according to the **ErrorRowDisposition** property of the input.</span></span>  
  
 <span data-ttu-id="9e90f-130">La sortie d'erreur du composant contient les colonnes de sortie suivantes :</span><span class="sxs-lookup"><span data-stu-id="9e90f-130">The component error output includes the following output columns:</span></span>  
  
-   <span data-ttu-id="9e90f-131">**Code d'erreur**: la valeur est 1.</span><span class="sxs-lookup"><span data-stu-id="9e90f-131">**Error Code**: Set to 1.</span></span>  
  
-   <span data-ttu-id="9e90f-132">**Colonne d’erreur**: colonne source à l’origine de l’erreur (pour les erreurs de conversion).</span><span class="sxs-lookup"><span data-stu-id="9e90f-132">**Error Column**: The source column causing the error (for conversion errors).</span></span>  
  
-   <span data-ttu-id="9e90f-133">**Colonnes de ligne d'erreur**: colonnes d'entrée de la ligne à l'origine de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="9e90f-133">**Error Row Columns**: The input columns of the row that caused the error.</span></span>  
  
## <a name="configuring-the-cdc-splitter"></a><span data-ttu-id="9e90f-134">Configuration du séparateur de capture de données modifiées</span><span class="sxs-lookup"><span data-stu-id="9e90f-134">Configuring the CDC Splitter</span></span>  
 <span data-ttu-id="9e90f-135">Le séparateur de capture de données modifiées ne comporte aucune propriété configurable.</span><span class="sxs-lookup"><span data-stu-id="9e90f-135">There are no configurable properties for the CDC splitter.</span></span>  
  
 <span data-ttu-id="9e90f-136">Pour plus d'informations sur l'utilisation du séparateur de capture de données modifiées, consultez Composants de capture de données modifiées pour Microsoft SQL Server Integration Services.</span><span class="sxs-lookup"><span data-stu-id="9e90f-136">For more information about using the CDC splitter, see CDC Components for Microsoft SQL Server Integration Services.</span></span>  
  
 <span data-ttu-id="9e90f-137">La boîte de dialogue **Éditeur avancé** contient les propriétés qui peuvent être définies par programme.</span><span class="sxs-lookup"><span data-stu-id="9e90f-137">The **Advanced Editor** dialog box contains the properties that can be set programmatically.</span></span>  
  
 <span data-ttu-id="9e90f-138">Pour ouvrir la boîte de dialogue **Éditeur avancé** :</span><span class="sxs-lookup"><span data-stu-id="9e90f-138">To open the **Advanced Editor** dialog box:</span></span>  
  
-   <span data-ttu-id="9e90f-139">Sur l'écran **Flux de données** de votre projet [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] , cliquez avec le bouton droit sur le séparateur de capture de données modifiées, puis sélectionnez **Afficher l'éditeur avancé**.</span><span class="sxs-lookup"><span data-stu-id="9e90f-139">In the **Data Flow** screen of your [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project, right click the CDC splitter and select **Show Advanced Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e90f-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9e90f-140">See Also</span></span>  
 [<span data-ttu-id="9e90f-141">Diriger le flux de capture de données modifiées en fonction du type de modification</span><span class="sxs-lookup"><span data-stu-id="9e90f-141">Direct the CDC Stream According to the Type of Change</span></span>](direct-the-cdc-stream-according-to-the-type-of-change.md)  
  
  
