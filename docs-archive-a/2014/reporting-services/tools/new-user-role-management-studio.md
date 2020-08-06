---
title: Nouveau rôle d’utilisateur (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.newrole.f1
ms.assetid: 9f76a235-0b58-479c-8e5b-50588091b71c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 78201c5ebedd0cdb7f8108b9e6effcaa7fbe87b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700691"
---
# <a name="new-user-role-management-studio"></a><span data-ttu-id="47160-102">Nouveau rôle d'utilisateur (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="47160-102">New User Role (Management Studio)</span></span>
  <span data-ttu-id="47160-103">Utilisez cette page pour créer une définition de rôle au niveau élément.</span><span class="sxs-lookup"><span data-stu-id="47160-103">Use this page to create an item-level role definition.</span></span> <span data-ttu-id="47160-104">Une définition de rôle au niveau élément est une collection nommée de tâches qui énumère les tâches qu'un utilisateur peut effectuer sur des dossiers, des rapports, des modèles, des ressources et des sources de données partagées.</span><span class="sxs-lookup"><span data-stu-id="47160-104">An item-level role definition is a named collection of tasks that enumerate the tasks a user can perform in relation to folders, reports, models, resources, and shared data sources.</span></span> <span data-ttu-id="47160-105">Le rôle Visiteur prédéfini est un exemple de définition de rôle au niveau élément qui identifie les types d'actions dont un utilisateur final de rapports peut avoir besoin pour naviguer entre des dossiers et afficher des rapports.</span><span class="sxs-lookup"><span data-stu-id="47160-105">An example of an item-level role definition is the predefined Browser role that identifies the kinds of actions a report end user might require for navigating folders and viewing reports.</span></span>  
  
 <span data-ttu-id="47160-106">Les définitions de rôles sont destinées à être peu nombreuses.</span><span class="sxs-lookup"><span data-stu-id="47160-106">Role definitions are intended to be few in number.</span></span> <span data-ttu-id="47160-107">La plupart des organisations n'en requièrent que quelques-unes.</span><span class="sxs-lookup"><span data-stu-id="47160-107">Most organizations only require a few role definitions.</span></span> <span data-ttu-id="47160-108">Toutefois, si les définitions de rôles prédéfinies sont insuffisantes, vous pouvez les modifier ou en créer de nouvelles.</span><span class="sxs-lookup"><span data-stu-id="47160-108">However, if the predefined role definitions are insufficient, you can vary them or create new ones.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="47160-109">Les définitions de rôles sont utilisées uniquement sur un serveur de rapports qui s'exécute en mode natif.</span><span class="sxs-lookup"><span data-stu-id="47160-109">Role definitions are used only on a report server that runs in native mode.</span></span> <span data-ttu-id="47160-110">Si le serveur de rapports est configuré pour l'intégration SharePoint, cette page n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="47160-110">If the report server is configured for SharePoint integration, this page is not available.</span></span>  
  
## <a name="options"></a><span data-ttu-id="47160-111">Options</span><span class="sxs-lookup"><span data-stu-id="47160-111">Options</span></span>  
 <span data-ttu-id="47160-112">**Nom**</span><span class="sxs-lookup"><span data-stu-id="47160-112">**Name**</span></span>  
 <span data-ttu-id="47160-113">Tapez le nom de la définition de rôle.</span><span class="sxs-lookup"><span data-stu-id="47160-113">Type the name of the role definition.</span></span> <span data-ttu-id="47160-114">Un nom de définition de rôle doit être unique dans l'espace de noms du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="47160-114">A role definition name must be unique within the report server namespace.</span></span> <span data-ttu-id="47160-115">Le nom doit contenir un caractère alphanumérique au minimum.</span><span class="sxs-lookup"><span data-stu-id="47160-115">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="47160-116">Il peut également comporter des espaces et quelques symboles.</span><span class="sxs-lookup"><span data-stu-id="47160-116">It can also include spaces and some symbols.</span></span> <span data-ttu-id="47160-117">N'utilisez pas les caractères suivants dans le nom :</span><span class="sxs-lookup"><span data-stu-id="47160-117">Do not use the following characters when specifying a name:</span></span>  
  
 <span data-ttu-id="47160-118">; ?</span><span class="sxs-lookup"><span data-stu-id="47160-118">; ?</span></span> <span data-ttu-id="47160-119">: \@ & = +, $/\*\< ></span><span class="sxs-lookup"><span data-stu-id="47160-119">: \@ & = + , $ / \* \< ></span></span>  
  
 <span data-ttu-id="47160-120">" /</span><span class="sxs-lookup"><span data-stu-id="47160-120">" /</span></span>  
  
 <span data-ttu-id="47160-121">**Description**</span><span class="sxs-lookup"><span data-stu-id="47160-121">**Description**</span></span>  
 <span data-ttu-id="47160-122">Entrez une description qui explique l'utilisation du rôle et énumère les éléments pris en charge par ce dernier.</span><span class="sxs-lookup"><span data-stu-id="47160-122">Type a description that explains how to use the role and enumerates what the role supports.</span></span>  
  
 <span data-ttu-id="47160-123">**Tâche**</span><span class="sxs-lookup"><span data-stu-id="47160-123">**Task**</span></span>  
 <span data-ttu-id="47160-124">Sélectionnez les tâches réalisables par ce rôle.</span><span class="sxs-lookup"><span data-stu-id="47160-124">Select the tasks that can be performed through this role.</span></span> <span data-ttu-id="47160-125">Vous ne pouvez pas créer de tâches ou modifier les tâches existantes qui sont prises en charge par [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47160-125">You cannot create new tasks or modify the existing tasks that are supported by [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="47160-126">Seules les tâches au niveau élément peuvent être utilisées dans une définition de rôle au niveau élément.</span><span class="sxs-lookup"><span data-stu-id="47160-126">Only item-level tasks can be used in an item-level role definition.</span></span>  
  
 <span data-ttu-id="47160-127">**Description de la tâche**</span><span class="sxs-lookup"><span data-stu-id="47160-127">**Task Description**</span></span>  
 <span data-ttu-id="47160-128">Affiche une description de la tâche qui énumère les opérations ou les autorisations prises en charge par cette dernière.</span><span class="sxs-lookup"><span data-stu-id="47160-128">Shows a description of the task that enumerates the operations or permissions that the task supports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47160-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="47160-129">See Also</span></span>  
 <span data-ttu-id="47160-130">[Aide du serveur de rapports dans Management Studio accessible par la touche F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="47160-130">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="47160-131">Définitions de rôles</span><span class="sxs-lookup"><span data-stu-id="47160-131">Role Definitions</span></span>](../security/role-definitions.md)  
  
  
