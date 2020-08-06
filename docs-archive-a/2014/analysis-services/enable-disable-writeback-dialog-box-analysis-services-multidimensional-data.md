---
title: Boîte de dialogue Activer/désactiver l’écriture différée (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitiondesigner.writebackenabledisable.f1
ms.assetid: 2d254393-3f0d-4b70-8b98-87159f9f3639
author: minewiskan
ms.author: owend
ms.openlocfilehash: 54ee4597ee78f45682730bd0e8d7119d204eaf2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614882"
---
# <a name="enable-disable-writeback-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="7d841-102">Boîte de dialogue Activer/désactiver l’écriture différée (Analysis Services-données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="7d841-102">Enable-Disable Writeback Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="7d841-103">La boîte de dialogue **Activer/Désactiver l’écriture différée** permet d’activer ou de désactiver l’écriture différée pour un groupe de mesures dans un cube.</span><span class="sxs-lookup"><span data-stu-id="7d841-103">The **Enable/Disable Writeback** dialog box enables or disables writeback for a measure group in a cube.</span></span> <span data-ttu-id="7d841-104">L'activation de l'écriture différée dans un groupe de mesures définit une partition d'écriture différée et crée une table d'écriture différée pour le groupe de mesures.</span><span class="sxs-lookup"><span data-stu-id="7d841-104">Enabling writeback on a measure group defines a writeback partition and creates a writeback table for that measure group.</span></span> <span data-ttu-id="7d841-105">La désactivation de l'écriture différée dans un groupe de mesures supprime la partition d'écriture différée, mais ne supprime pas la table d'écriture différée pour éviter les pertes de données imprévues.</span><span class="sxs-lookup"><span data-stu-id="7d841-105">Disabling writeback on a measure group removes the writeback partition but does not delete the writeback table, to avoid unanticipated data loss.</span></span> <span data-ttu-id="7d841-106">Pour afficher la boîte de dialogue **Activer/Désactiver l’écriture différée** :</span><span class="sxs-lookup"><span data-stu-id="7d841-106">The **Enable/Disable Writeback** dialog box is displayed by:</span></span>  
  
-   <span data-ttu-id="7d841-107">Cliquez sur **Paramètres d’écriture différée** dans le volet **Groupes de mesures** de l’onglet **Partitions** du Concepteur de cube.</span><span class="sxs-lookup"><span data-stu-id="7d841-107">Clicking **Writeback Settings** in the **Measure Groups** pane on the **Partitions** tab in Cube Designer.</span></span>  
  
-   <span data-ttu-id="7d841-108">Cliquez avec le bouton droit sur une partition dans la grille **Partitions** du volet **Groupes de mesures** sous l’onglet **Partitions** du Concepteur de cube et sélectionnez **Paramètres d’écriture différée** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="7d841-108">Right-clicking a partition in the **Partitions** grid in the **Measure Groups** pane on the **Partitions** tab in Cube Designer and selecting **Writeback Settings** from the context menu.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7d841-109">Options</span><span class="sxs-lookup"><span data-stu-id="7d841-109">Options</span></span>  
 <span data-ttu-id="7d841-110">**Nom de la table**</span><span class="sxs-lookup"><span data-stu-id="7d841-110">**Table name**</span></span>  
 <span data-ttu-id="7d841-111">Tapez le nom de la table d'écriture différée à créer pour la partition sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7d841-111">Type the name of the writeback table to create for the selected partition.</span></span> <span data-ttu-id="7d841-112">La table d’écriture différée stocke les modifications apportées au groupe de mesures par une application cliente.</span><span class="sxs-lookup"><span data-stu-id="7d841-112">The writeback table stores the changes made to the measure group from a client application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7d841-113">Cette option est désactivée si l'écriture différée n'est pas active.</span><span class="sxs-lookup"><span data-stu-id="7d841-113">This option is disabled if writeback is not enabled.</span></span>  
  
 <span data-ttu-id="7d841-114">**Source de données**</span><span class="sxs-lookup"><span data-stu-id="7d841-114">**Data source**</span></span>  
 <span data-ttu-id="7d841-115">Sélectionne la source de données qui contiendra la table d'écriture différée.</span><span class="sxs-lookup"><span data-stu-id="7d841-115">Select the data source to contain the writeback table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7d841-116">Cette option est désactivée si l'écriture différée n'est pas active.</span><span class="sxs-lookup"><span data-stu-id="7d841-116">This option is disabled if writeback is not enabled.</span></span>  
  
 <span data-ttu-id="7d841-117">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="7d841-117">**New**</span></span>  
 <span data-ttu-id="7d841-118">Cliquez sur cette option pour afficher la boîte de dialogue **Gestionnaire de connexions** et définir une nouvelle source de données qui accueillera la table d’écriture différée.</span><span class="sxs-lookup"><span data-stu-id="7d841-118">Click to display the **Connection Manager** dialog box and define a new data source to contain the writeback table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7d841-119">Cette option est désactivée si l'écriture différée n'est pas active.</span><span class="sxs-lookup"><span data-stu-id="7d841-119">This option is disabled if writeback is not enabled.</span></span>  
  
  
