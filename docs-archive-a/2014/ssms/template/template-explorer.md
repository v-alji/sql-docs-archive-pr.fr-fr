---
title: Explorateur de modèles | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.wb.templates.f1
- sql12.swb.templates.explorer.f1
helpviewer_keywords:
- templates [SQL Server]
- SQL Server Management Studio [SQL Server], Template Explorer
- Template Explorer
- templates [Transact-SQL]
- templates [SQL Server], Template Explorer
ms.assetid: b9ee55c5-bb44-4f76-90ac-792d8d83b4c8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 35e7ee1e6261c759580df3a836f9cc4b500a77ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611464"
---
# <a name="template-explorer"></a><span data-ttu-id="f4a1b-102">Explorateur de modèles</span><span class="sxs-lookup"><span data-stu-id="f4a1b-102">Template Explorer</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f4a1b-103">propose divers modèles.</span><span class="sxs-lookup"><span data-stu-id="f4a1b-103">provides a variety of templates.</span></span> <span data-ttu-id="f4a1b-104">Les modèles sont des fichiers réutilisables contenant des scripts SQL qui peuvent vous aider à créer des objets dans une base de données.</span><span class="sxs-lookup"><span data-stu-id="f4a1b-104">Templates are boilerplate files containing SQL scripts that help you create objects in a database.</span></span> <span data-ttu-id="f4a1b-105">La première fois que l’Explorateur de modèles est ouvert, une copie des modèles est placée dans le dossier de l’utilisateur dans C:\Users, sous AppData\Roaming\Microsoft\SQL Server Management Studio\120\Templates.</span><span class="sxs-lookup"><span data-stu-id="f4a1b-105">The first time the template explorer is opened, a copy of the templates are placed in the user's folder in C:\Users, under AppData\Roaming\Microsoft\SQL Server Management Studio\120\Templates.</span></span>  
  
 <span data-ttu-id="f4a1b-106">Vous pouvez parcourir les modèles disponibles dans l'Explorateur de modèles, puis ouvrir un modèle pour incorporer code dans une fenêtre d'éditeur de code.</span><span class="sxs-lookup"><span data-stu-id="f4a1b-106">You can browse the available templates in Template Explorer, then open a template to incorporate the code into a code editor window.</span></span> <span data-ttu-id="f4a1b-107">Vous pouvez également créer des modèles personnalisés.</span><span class="sxs-lookup"><span data-stu-id="f4a1b-107">You can also create custom templates.</span></span>  
  
## <a name="benefits-of-templates"></a><span data-ttu-id="f4a1b-108">Avantages des modèles</span><span class="sxs-lookup"><span data-stu-id="f4a1b-108">Benefits of Templates</span></span>  
 <span data-ttu-id="f4a1b-109">Les modèles peuvent être utilisés pour les solutions, les projets et différents types d'éditeurs de code.</span><span class="sxs-lookup"><span data-stu-id="f4a1b-109">Templates are available for solutions, projects, and various types of code editors.</span></span> <span data-ttu-id="f4a1b-110">Certains modèles sont destinés à la création d’objets tels que des bases de données, des tables, des vues, des index, des procédures stockées, des déclencheurs, des statistiques et des fonctions.</span><span class="sxs-lookup"><span data-stu-id="f4a1b-110">Templates are available to create objects like databases, tables, views, indexes, stored procedures, triggers, statistics, and functions.</span></span> <span data-ttu-id="f4a1b-111">D'autres modèles sont conçus pour simplifier la gestion de votre serveur en créant des propriétés étendues, des serveurs liés, des noms d'accès, des rôles et des utilisateurs. Il existe en outre certains modèles destinés à [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4a1b-111">In addition, there are templates that help you to manage your server by creating extended properties, linked servers, logins, roles, users, and templates for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="f4a1b-112">Les modèles de scripts fournis avec [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] contiennent des paramètres qui permettent de personnaliser le code.</span><span class="sxs-lookup"><span data-stu-id="f4a1b-112">The template scripts provided with [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] contain parameters to help you customize the code.</span></span> <span data-ttu-id="f4a1b-113">Quand vous ouvrez un modèle, utilisez la boîte de dialogue **Remplacer les paramètres de modèle** pour insérer des valeurs dans le script.</span><span class="sxs-lookup"><span data-stu-id="f4a1b-113">When you open a template, Use the **Replace Template Parameters** dialog box to insert values into the script.</span></span>  
  
 <span data-ttu-id="f4a1b-114">Créez des modèles personnalisés pour les tâches que vous effectuez fréquemment.</span><span class="sxs-lookup"><span data-stu-id="f4a1b-114">Create custom templates for tasks you perform frequently.</span></span> <span data-ttu-id="f4a1b-115">Organisez les scripts personnalisés dans les dossiers existants ou créez une structure de dossiers.</span><span class="sxs-lookup"><span data-stu-id="f4a1b-115">Organize your custom scripts into the existing folders or create a new folder structure.</span></span>  
  
 <span data-ttu-id="f4a1b-116">L'Éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] prend également en charge les extraits de code, que vous pouvez insérer à des emplacements spécifiques dans un script en cliquant avec le bouton droit à cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="f4a1b-116">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query editor also supports code snippets, which can be inserted at specific locations in a script by right-clicking at that location.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="f4a1b-117">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="f4a1b-117">Related Tasks</span></span>  
 <span data-ttu-id="f4a1b-118">Utiliser les rubriques suivantes pour commencer à utiliser les modèles</span><span class="sxs-lookup"><span data-stu-id="f4a1b-118">Use the following topics to get started with templates</span></span>  
  
|<span data-ttu-id="f4a1b-119">**Description**</span><span class="sxs-lookup"><span data-stu-id="f4a1b-119">**Description**</span></span>|<span data-ttu-id="f4a1b-120">**Rubrique**</span><span class="sxs-lookup"><span data-stu-id="f4a1b-120">**Topic**</span></span>|  
|---------------------|---------------|  
|<span data-ttu-id="f4a1b-121">Explique comment incorporer le code d'un modèle dans une fenêtre d'éditeur de code.</span><span class="sxs-lookup"><span data-stu-id="f4a1b-121">Describes how to incorporate the code from a template into a code editor window.</span></span>|[<span data-ttu-id="f4a1b-122">Ouvrir un modèle</span><span class="sxs-lookup"><span data-stu-id="f4a1b-122">Open a Template</span></span>](open-a-template.md)|  
|<span data-ttu-id="f4a1b-123">Explique comment remplacer des valeurs de paramètre de modèle après avoir ouvert un modèle dans un éditeur de code.</span><span class="sxs-lookup"><span data-stu-id="f4a1b-123">Describes how to replace template parameter values after opening a template in a code editor.</span></span>|[<span data-ttu-id="f4a1b-124">Remplacer les paramètres de modèle</span><span class="sxs-lookup"><span data-stu-id="f4a1b-124">Replace Template Parameters</span></span>](replace-template-parameters.md)|  
  
  
