---
title: Nouveau rôle système (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.newsystemrole.f1
ms.assetid: 7b4a0b98-975b-478a-8359-7db39ccbb347
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a744fc78bdd5ae6ef3a37f96ff5ae8cd10f71a80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700692"
---
# <a name="new-system-role-management-studio"></a><span data-ttu-id="5deb3-102">Nouveau rôle système (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="5deb3-102">New System Role (Management Studio)</span></span>
  <span data-ttu-id="5deb3-103">Utilisez cette page pour créer une définition de rôle au niveau système.</span><span class="sxs-lookup"><span data-stu-id="5deb3-103">Use this page to create a system-level role definition.</span></span> <span data-ttu-id="5deb3-104">Une définition de rôle système spécifie un ensemble de tâches au niveau système qui s'appliquent à l'ensemble du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="5deb3-104">A system role definition specifies a set of system-level tasks that apply to a report server as whole.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5deb3-105">Les définitions de rôles sont utilisées uniquement sur un serveur de rapports qui s'exécute en mode natif.</span><span class="sxs-lookup"><span data-stu-id="5deb3-105">Role definitions are used only on a report server that runs in native mode.</span></span> <span data-ttu-id="5deb3-106">Si le serveur de rapports est configuré pour l'intégration SharePoint, cette page n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="5deb3-106">If the report server is configured for SharePoint integration, this page is not available.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5deb3-107">Options</span><span class="sxs-lookup"><span data-stu-id="5deb3-107">Options</span></span>  
 <span data-ttu-id="5deb3-108">**Nom**</span><span class="sxs-lookup"><span data-stu-id="5deb3-108">**Name**</span></span>  
 <span data-ttu-id="5deb3-109">Tapez le nom de la définition de rôle.</span><span class="sxs-lookup"><span data-stu-id="5deb3-109">Type the name of the role definition.</span></span> <span data-ttu-id="5deb3-110">Un nom de définition de rôle doit être unique dans l'espace de noms du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="5deb3-110">A role definition name must be unique within the report server namespace.</span></span> <span data-ttu-id="5deb3-111">Le nom doit contenir un caractère alphanumérique au minimum.</span><span class="sxs-lookup"><span data-stu-id="5deb3-111">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="5deb3-112">Il peut également comporter des espaces et quelques symboles.</span><span class="sxs-lookup"><span data-stu-id="5deb3-112">It can also include spaces and some symbols.</span></span> <span data-ttu-id="5deb3-113">N'utilisez pas les caractères suivants dans le nom :</span><span class="sxs-lookup"><span data-stu-id="5deb3-113">Do not use the following characters when specifying a name:</span></span>  
  
 <span data-ttu-id="5deb3-114">; ?</span><span class="sxs-lookup"><span data-stu-id="5deb3-114">; ?</span></span> <span data-ttu-id="5deb3-115">: \@ & = +, $/\*\< ></span><span class="sxs-lookup"><span data-stu-id="5deb3-115">: \@ & = + , $ / \* \< ></span></span>  
  
 <span data-ttu-id="5deb3-116">" /</span><span class="sxs-lookup"><span data-stu-id="5deb3-116">" /</span></span>  
  
 <span data-ttu-id="5deb3-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="5deb3-117">**Description**</span></span>  
 <span data-ttu-id="5deb3-118">Fournit une description qui explique l'utilisation du rôle et énumère les éléments pris en charge par ce dernier.</span><span class="sxs-lookup"><span data-stu-id="5deb3-118">Provide a description that explains how to use the role and enumerates what the role supports.</span></span>  
  
 <span data-ttu-id="5deb3-119">**Tâche**</span><span class="sxs-lookup"><span data-stu-id="5deb3-119">**Task**</span></span>  
 <span data-ttu-id="5deb3-120">Sélectionnez les tâches au niveau système qui peuvent être effectuées par ce rôle.</span><span class="sxs-lookup"><span data-stu-id="5deb3-120">Select the system-level tasks that can be performed through this role.</span></span> <span data-ttu-id="5deb3-121">Vous ne pouvez pas créer de tâches ou modifier les tâches existantes qui sont prises en charge par [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5deb3-121">You cannot create new tasks or modify the existing tasks that are supported by [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="5deb3-122">Vous ne pouvez pas choisir des tâches au niveau élément pour la définition d'un rôle système.</span><span class="sxs-lookup"><span data-stu-id="5deb3-122">You cannot choose item-level tasks for a system role definition.</span></span>  
  
 <span data-ttu-id="5deb3-123">**Description de la tâche**</span><span class="sxs-lookup"><span data-stu-id="5deb3-123">**Task Description**</span></span>  
 <span data-ttu-id="5deb3-124">Affiche une description de la tâche qui énumère les opérations ou les autorisations prises en charge par cette dernière.</span><span class="sxs-lookup"><span data-stu-id="5deb3-124">Shows a description of the task that enumerates the operations or permissions that the task supports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5deb3-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5deb3-125">See Also</span></span>  
 <span data-ttu-id="5deb3-126">[Aide du serveur de rapports dans Management Studio accessible par la touche F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="5deb3-126">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="5deb3-127">Définitions de rôles</span><span class="sxs-lookup"><span data-stu-id="5deb3-127">Role Definitions</span></span>](../security/role-definitions.md)  
  
  
