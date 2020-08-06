---
title: Éditeur de restauration de références de colonnes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.resolvereferences.mapper.F1
- sql12.dts.designer.resolvereferences.preview.F1
ms.assetid: bb3ee33c-79c4-4c76-a82f-71581b4a60f1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 600b6f4d5ec12290d654f0854cc548a5bbcf4335
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610772"
---
# <a name="resolve-column-reference-editor"></a><span data-ttu-id="d8931-102">Éditeur de restauration de références de colonnes</span><span class="sxs-lookup"><span data-stu-id="d8931-102">Resolve Column Reference Editor</span></span>
  <span data-ttu-id="d8931-103">Lorsqu'un chemin d'accès d'entrée est déconnecté ou s'il existe des colonnes non mappées dans le chemin d'accès, une icône d'erreur s'affiche en regard du chemin d'accès aux données correspondant.</span><span class="sxs-lookup"><span data-stu-id="d8931-103">When an input path is disconnected or if there are any unmapped columns in the path, an error icon is displayed beside the corresponding data path.</span></span> <span data-ttu-id="d8931-104">Pour simplifier la résolution des erreurs de référence de colonne, le nouvel éditeur de résolution des références vous permet de lier des colonnes de sortie non mappées avec des colonnes d'entrée non mappées pour tous les chemins d'accès de l'arborescence d'exécution.</span><span class="sxs-lookup"><span data-stu-id="d8931-104">To simplify the resolution of column reference errors, the new Resolve References editor allows you to link unmapped output columns with unmapped input columns for all paths in the execution tree.</span></span> <span data-ttu-id="d8931-105">L'éditeur de résolution des références met également en surbrillance les chemins d'accès pour indiquer ceux qui sont résolus.</span><span class="sxs-lookup"><span data-stu-id="d8931-105">The Resolve References editor will also highlight the paths to indicate which paths are being resolved.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d8931-106">Il est maintenant possible de modifier un composant même lorsque son chemin d'accès d'entrée est déconnecté.</span><span class="sxs-lookup"><span data-stu-id="d8931-106">It is now possible to edit a component even when its input path is disconnected</span></span>  
  
 <span data-ttu-id="d8931-107">Une fois toutes les références de colonnes résolues, s'il n'y a pas d'autres erreurs de chemin d'accès aux données, aucune icône d'erreur ne s'affiche en regard des chemins d'accès aux données.</span><span class="sxs-lookup"><span data-stu-id="d8931-107">After all column references have been resolved, if there are no other data path errors, no error icons will be displayed beside the data paths.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d8931-108">Options</span><span class="sxs-lookup"><span data-stu-id="d8931-108">Options</span></span>  
 <span data-ttu-id="d8931-109">Colonnes de sortie non mappées (source) :</span><span class="sxs-lookup"><span data-stu-id="d8931-109">Unmapped Output Columns (Source):</span></span>  
 <span data-ttu-id="d8931-110">Colonnes du chemin d'accès en amont qui ne sont pas mappées</span><span class="sxs-lookup"><span data-stu-id="d8931-110">Columns from the upstream path that are not currently mapped</span></span>  
  
 <span data-ttu-id="d8931-111">Colonnes mappées (source) :</span><span class="sxs-lookup"><span data-stu-id="d8931-111">Mapped Columns (Source):</span></span>  
 <span data-ttu-id="d8931-112">Colonnes du chemin d'accès en amont qui sont mappées à des colonnes du chemin d'accès en aval</span><span class="sxs-lookup"><span data-stu-id="d8931-112">Columns from the upstream path that are mapped to columns from the downstream path</span></span>  
  
 <span data-ttu-id="d8931-113">Colonnes mappées (destination) :</span><span class="sxs-lookup"><span data-stu-id="d8931-113">Mapped Columns (Destination):</span></span>  
 <span data-ttu-id="d8931-114">Colonnes du chemin d'accès en amont qui sont mappées à des colonnes du chemin d'accès en aval</span><span class="sxs-lookup"><span data-stu-id="d8931-114">Columns from the upstream path that are mapped to columns from the downstream path</span></span>  
  
 <span data-ttu-id="d8931-115">Colonnes d'entrée non mappées (destination) :</span><span class="sxs-lookup"><span data-stu-id="d8931-115">Unmapped Input Columns (Destination):</span></span>  
 <span data-ttu-id="d8931-116">Colonnes du chemin d'accès en aval qui ne sont pas mappées</span><span class="sxs-lookup"><span data-stu-id="d8931-116">Columns from the downstream path that are not currently mapped</span></span>  
  
 <span data-ttu-id="d8931-117">Supprimer les colonnes d'entrée non mappées</span><span class="sxs-lookup"><span data-stu-id="d8931-117">Delete Unmapped Input Columns</span></span>  
 <span data-ttu-id="d8931-118">Activez Supprimer les colonnes d'entrée non mappées pour ignorer les colonnes non mappées au niveau de la destination du chemin d'accès aux données.</span><span class="sxs-lookup"><span data-stu-id="d8931-118">Check Delete Unmapped Input Columns to ignore unmapped columns at the destination of the data path.</span></span> <span data-ttu-id="d8931-119">Le bouton Aperçu des modifications affiche la liste des modifications qui se produiront lorsque vous appuierez sur le bouton OK.</span><span class="sxs-lookup"><span data-stu-id="d8931-119">The Preview Changes button displays a list of the changes that will occur when you press the OK button.</span></span>  
  
  
