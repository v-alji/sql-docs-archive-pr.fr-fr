---
title: Éditeur de transformation d’audit | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.audittransformation.f1
helpviewer_keywords:
- Audit Transformation Editor
ms.assetid: 32786a34-5870-4fde-83c7-ec74d62404b8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: af6490643a0bef60cca961dc9a0564c5f6b46484
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707736"
---
# <a name="audit-transformation-editor"></a><span data-ttu-id="09916-102">Éditeur de transformation d'audit</span><span class="sxs-lookup"><span data-stu-id="09916-102">Audit Transformation Editor</span></span>
  <span data-ttu-id="09916-103">La transformation d'audit permet au flux de données d'un package de contenir des données relatives à l'environnement d'exécution du package.</span><span class="sxs-lookup"><span data-stu-id="09916-103">The Audit transformation enables the data flow in a package to include data about the environment in which the package runs.</span></span> <span data-ttu-id="09916-104">Par exemple, le nom du package, de l'ordinateur et de l'opérateur peuvent être ajoutés au flux de données.</span><span class="sxs-lookup"><span data-stu-id="09916-104">For example, the name of the package, computer, and operator can be added to the data flow.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="09916-105">comprend des variables système qui fournissent ces informations.</span><span class="sxs-lookup"><span data-stu-id="09916-105">includes system variables that provide this information.</span></span>  
  
 <span data-ttu-id="09916-106">Pour en savoir plus sur la transformation d'audit, consultez [Audit Transformation](data-flow/transformations/audit-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="09916-106">To learn more about the Audit transformation, see [Audit Transformation](data-flow/transformations/audit-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="09916-107">Options</span><span class="sxs-lookup"><span data-stu-id="09916-107">Options</span></span>  
 <span data-ttu-id="09916-108">**Nom de la colonne de sortie**</span><span class="sxs-lookup"><span data-stu-id="09916-108">**Output column name**</span></span>  
 <span data-ttu-id="09916-109">Indique le nom de la nouvelle colonne de sortie qui va contenir les informations d'audit.</span><span class="sxs-lookup"><span data-stu-id="09916-109">Provide the name for a new output column that will contain the audit information.</span></span>  
  
 <span data-ttu-id="09916-110">**Type d’audit**</span><span class="sxs-lookup"><span data-stu-id="09916-110">**Audit type**</span></span>  
 <span data-ttu-id="09916-111">Sélectionne une variable système disponible pour fournir les informations d'audit.</span><span class="sxs-lookup"><span data-stu-id="09916-111">Select an available system variable to supply the audit information.</span></span>  
  
|<span data-ttu-id="09916-112">Valeur</span><span class="sxs-lookup"><span data-stu-id="09916-112">Value</span></span>|<span data-ttu-id="09916-113">Description</span><span class="sxs-lookup"><span data-stu-id="09916-113">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="09916-114">**GUID d'instance d'exécution**</span><span class="sxs-lookup"><span data-stu-id="09916-114">**Execution instance GUID**</span></span>|<span data-ttu-id="09916-115">Insérez le GUID qui identifie de manière unique l'instance d'exécution du package.</span><span class="sxs-lookup"><span data-stu-id="09916-115">Insert the GUID that uniquely identifies the execution instance of the package.</span></span>|  
|<span data-ttu-id="09916-116">**ID du package**</span><span class="sxs-lookup"><span data-stu-id="09916-116">**Package ID**</span></span>|<span data-ttu-id="09916-117">Insérez le GUID qui identifie de manière unique le package.</span><span class="sxs-lookup"><span data-stu-id="09916-117">Insert the GUID that uniquely identifies the package.</span></span>|  
|<span data-ttu-id="09916-118">**Nom du package**</span><span class="sxs-lookup"><span data-stu-id="09916-118">**Package name**</span></span>|<span data-ttu-id="09916-119">Insérez le nom du package.</span><span class="sxs-lookup"><span data-stu-id="09916-119">Insert the package name.</span></span>|  
|<span data-ttu-id="09916-120">**ID de version**</span><span class="sxs-lookup"><span data-stu-id="09916-120">**Version ID**</span></span>|<span data-ttu-id="09916-121">Insérez le GUID qui identifie de manière unique la version du package.</span><span class="sxs-lookup"><span data-stu-id="09916-121">Insert the GUID that uniquely identifies the version of the package.</span></span>|  
|<span data-ttu-id="09916-122">**Heure de début de l'exécution**</span><span class="sxs-lookup"><span data-stu-id="09916-122">**Execution start time**</span></span>|<span data-ttu-id="09916-123">Insérez l'heure à laquelle l'exécution du package a commencé.</span><span class="sxs-lookup"><span data-stu-id="09916-123">Insert the time at which package execution started.</span></span>|  
|<span data-ttu-id="09916-124">**Nom de l'ordinateur**</span><span class="sxs-lookup"><span data-stu-id="09916-124">**Machine name**</span></span>|<span data-ttu-id="09916-125">Insérez le nom de l'ordinateur sur lequel le package a été lancé.</span><span class="sxs-lookup"><span data-stu-id="09916-125">Insert the name of the computer on which the package was launched.</span></span>|  
|<span data-ttu-id="09916-126">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="09916-126">**User name**</span></span>|<span data-ttu-id="09916-127">Insérez le nom de connexion de l'utilisateur qui a lancé le package.</span><span class="sxs-lookup"><span data-stu-id="09916-127">Insert the login name of the user who launched the package.</span></span>|  
|<span data-ttu-id="09916-128">**Nom de la tâche**</span><span class="sxs-lookup"><span data-stu-id="09916-128">**Task name**</span></span>|<span data-ttu-id="09916-129">Insérez le nom de la tâche de flux de données à laquelle la transformation d'audit est associée.</span><span class="sxs-lookup"><span data-stu-id="09916-129">Insert the name of the Data Flow task with which the Audit transformation is associated.</span></span>|  
|<span data-ttu-id="09916-130">**ID de la tâche**</span><span class="sxs-lookup"><span data-stu-id="09916-130">**Task ID**</span></span>|<span data-ttu-id="09916-131">Insérez le GUID qui identifie de manière unique le flux de données à laquelle la transformation d'audit est associée.</span><span class="sxs-lookup"><span data-stu-id="09916-131">Insert the GUID that uniquely identifies the Data Flow task with which the Audit transformation is associated.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="09916-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="09916-132">See Also</span></span>  
 [<span data-ttu-id="09916-133">Guide de référence des erreurs et des messages propres à Integration Services</span><span class="sxs-lookup"><span data-stu-id="09916-133">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
