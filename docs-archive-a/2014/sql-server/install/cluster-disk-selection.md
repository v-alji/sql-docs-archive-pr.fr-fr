---
title: Sélection du disque du cluster | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- cluster disk selection
ms.assetid: 0d6b863d-5972-4a20-9990-64ee8016fea6
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0f53d6d3f623254d2b17996be7fd5b8235dca223
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604955"
---
# <a name="cluster-disk-selection"></a><span data-ttu-id="70a41-102">Sélection du disque du cluster</span><span class="sxs-lookup"><span data-stu-id="70a41-102">Cluster Disk Selection</span></span>
  <span data-ttu-id="70a41-103">Utilisez la page **Sélection du disque du cluster** de l’Assistant Installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour sélectionner la ressource disque de cluster partagée pour votre cluster de basculement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="70a41-103">Use the **Cluster Disk Selection** page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard to select the shared cluster disk resource for your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster.</span></span> <span data-ttu-id="70a41-104">Le disque de cluster est l'emplacement où les données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] seront placées.</span><span class="sxs-lookup"><span data-stu-id="70a41-104">The cluster disk is where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data will be placed.</span></span>  
  
 <span data-ttu-id="70a41-105">Un disque de cluster partagé n’est pas obligatoire pour les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] installations de cluster.</span><span class="sxs-lookup"><span data-stu-id="70a41-105">A shared cluster disk is not a requirement for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] cluster installations.</span></span> <span data-ttu-id="70a41-106">Un serveur de fichiers SMB est un stockage pris en charge pour les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] installations de cluster de basculement et peut être spécifié à l’aide de la page **moteur de base de données-répertoires de données** avant d’effectuer l’installation.</span><span class="sxs-lookup"><span data-stu-id="70a41-106">An SMB file server is a supported storage for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] failover cluster installations, and can be specified by using the **Database Engine - Data Directories** page before completing the installation.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="70a41-107">Si vous avez sélectionné Analysis Services pour l'installer, vous devez spécifier un disque de cluster partagé.</span><span class="sxs-lookup"><span data-stu-id="70a41-107">If you have selected Analysis Services to be installed, you must specify a shared cluster disk.</span></span>  
>   
>  <span data-ttu-id="70a41-108">Si vous envisagez d'activer FILESTREAM sur cette instance du cluster de basculement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vous devez spécifier un disque de cluster partagé.</span><span class="sxs-lookup"><span data-stu-id="70a41-108">If you plan to enable FILESTREAM on this [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster instance, you must specify a shared cluster disk.</span></span>  
  
## <a name="options"></a><span data-ttu-id="70a41-109">Options</span><span class="sxs-lookup"><span data-stu-id="70a41-109">Options</span></span>  
 <span data-ttu-id="70a41-110">**Disques partagés**</span><span class="sxs-lookup"><span data-stu-id="70a41-110">**Shared Disks**</span></span>  
 <span data-ttu-id="70a41-111">Sélectionnez un disque dans la liste.</span><span class="sxs-lookup"><span data-stu-id="70a41-111">Select a single disk from the list.</span></span> <span data-ttu-id="70a41-112">Le disque de cluster est l'emplacement où les données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] seront placées.</span><span class="sxs-lookup"><span data-stu-id="70a41-112">The cluster disk is where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data will be placed.</span></span>  
  
 <span data-ttu-id="70a41-113">Un seul disque peut être spécifié.</span><span class="sxs-lookup"><span data-stu-id="70a41-113">Only one disk can be specified.</span></span> <span data-ttu-id="70a41-114">Si vous sélectionnez le groupe contenant la ressource quorum du cluster, un avertissement s'affiche.</span><span class="sxs-lookup"><span data-stu-id="70a41-114">If you select the group containing the cluster quorum resource, a warning will be displayed.</span></span> <span data-ttu-id="70a41-115">Il est recommandé de ne pas procéder à l'installation dans cette ressource.</span><span class="sxs-lookup"><span data-stu-id="70a41-115">We recommend that you do not install to the cluster quorum resource.</span></span>  
  
 <span data-ttu-id="70a41-116">**Disques partagés disponibles**</span><span class="sxs-lookup"><span data-stu-id="70a41-116">**Available Shared Disks**</span></span>  
 <span data-ttu-id="70a41-117">Affiche une liste de disques disponibles, indique si chacun d'eux est qualifié en tant que disque partagé et fournit une description de chaque ressource de disque.</span><span class="sxs-lookup"><span data-stu-id="70a41-117">Displays a list of available disks, whether each is qualified as a shared disk, and a description of each disk resource.</span></span>  
  
  
