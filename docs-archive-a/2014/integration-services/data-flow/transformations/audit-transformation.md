---
title: Audit, transformation | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.audittrans.f1
helpviewer_keywords:
- environment data in packages [Integration Services]
- Audit transformation
ms.assetid: 8c143682-9c81-4150-83d6-1d9678151d37
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e8e302f6dd1dc5666ae65af2eb9705a4922915c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695872"
---
# <a name="audit-transformation"></a><span data-ttu-id="62e84-102">transformation d'audit</span><span class="sxs-lookup"><span data-stu-id="62e84-102">Audit Transformation</span></span>
  <span data-ttu-id="62e84-103">La transformation d'audit permet au flux de données d'un package de contenir des données relatives à l'environnement d'exécution du package.</span><span class="sxs-lookup"><span data-stu-id="62e84-103">The Audit transformation enables the data flow in a package to include data about the environment in which the package runs.</span></span> <span data-ttu-id="62e84-104">Par exemple, le nom du package, de l'ordinateur et de l'opérateur peuvent être ajoutés au flux de données.</span><span class="sxs-lookup"><span data-stu-id="62e84-104">For example, the name of the package, computer, and operator can be added to the data flow.</span></span> [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="62e84-105">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] comprend des variables système qui fournissent ces informations.</span><span class="sxs-lookup"><span data-stu-id="62e84-105">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] includes system variables that provide this information.</span></span>  
  
## <a name="system-variables"></a><span data-ttu-id="62e84-106">Variables système</span><span class="sxs-lookup"><span data-stu-id="62e84-106">System Variables</span></span>  
 <span data-ttu-id="62e84-107">Le tableau suivant décrit les variables système utilisables par la transformation d'audit.</span><span class="sxs-lookup"><span data-stu-id="62e84-107">The following table describes the system variables that the Audit transformation can use.</span></span>  
  
|<span data-ttu-id="62e84-108">Variable système</span><span class="sxs-lookup"><span data-stu-id="62e84-108">System variable</span></span>|<span data-ttu-id="62e84-109">Index</span><span class="sxs-lookup"><span data-stu-id="62e84-109">Index</span></span>|<span data-ttu-id="62e84-110">Description</span><span class="sxs-lookup"><span data-stu-id="62e84-110">Description</span></span>|  
|---------------------|-----------|-----------------|  
|`ExecutionInstanceGUID`|<span data-ttu-id="62e84-111">0</span><span class="sxs-lookup"><span data-stu-id="62e84-111">0</span></span>|<span data-ttu-id="62e84-112">GUID identifiant l'instance d'exécution du package.</span><span class="sxs-lookup"><span data-stu-id="62e84-112">The GUID that identifies the execution instance of the package.</span></span>|  
|`PackageID`|<span data-ttu-id="62e84-113">1</span><span class="sxs-lookup"><span data-stu-id="62e84-113">1</span></span>|<span data-ttu-id="62e84-114">Identificateur unique du package.</span><span class="sxs-lookup"><span data-stu-id="62e84-114">The unique identifier of the package.</span></span>|  
|`PackageName`|<span data-ttu-id="62e84-115">2</span><span class="sxs-lookup"><span data-stu-id="62e84-115">2</span></span>|<span data-ttu-id="62e84-116">Nom du package.</span><span class="sxs-lookup"><span data-stu-id="62e84-116">The package name.</span></span>|  
|`VersionID`|<span data-ttu-id="62e84-117">3</span><span class="sxs-lookup"><span data-stu-id="62e84-117">3</span></span>|<span data-ttu-id="62e84-118">Version du package.</span><span class="sxs-lookup"><span data-stu-id="62e84-118">The version of the package.</span></span>|  
|`ExecutionStartTime`|<span data-ttu-id="62e84-119">4</span><span class="sxs-lookup"><span data-stu-id="62e84-119">4</span></span>|<span data-ttu-id="62e84-120">Heure à laquelle l'exécution du package a commencé.</span><span class="sxs-lookup"><span data-stu-id="62e84-120">The time the package started to run.</span></span>|  
|`MachineName`|<span data-ttu-id="62e84-121">5</span><span class="sxs-lookup"><span data-stu-id="62e84-121">5</span></span>|<span data-ttu-id="62e84-122">Nom de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="62e84-122">The computer name.</span></span>|  
|`UserName`|<span data-ttu-id="62e84-123">6</span><span class="sxs-lookup"><span data-stu-id="62e84-123">6</span></span>|<span data-ttu-id="62e84-124">Nom de connexion de la personne qui a démarré le package.</span><span class="sxs-lookup"><span data-stu-id="62e84-124">The login name of the person who started the package.</span></span>|  
|`TaskName`|<span data-ttu-id="62e84-125">7</span><span class="sxs-lookup"><span data-stu-id="62e84-125">7</span></span>|<span data-ttu-id="62e84-126">Nom de la tâche de flux de données à laquelle la transformation d'audit est associée.</span><span class="sxs-lookup"><span data-stu-id="62e84-126">The name of the Data Flow task with which the Audit transformation is associated.</span></span>|  
|<span data-ttu-id="62e84-127">**TaskId**</span><span class="sxs-lookup"><span data-stu-id="62e84-127">**TaskId**</span></span>|<span data-ttu-id="62e84-128">8</span><span class="sxs-lookup"><span data-stu-id="62e84-128">8</span></span>|<span data-ttu-id="62e84-129">Identificateur unique de la tâche de flux de données.</span><span class="sxs-lookup"><span data-stu-id="62e84-129">The unique identifier of the Data Flow task.</span></span>|  
  
## <a name="configuration-of-the-audit-transformation"></a><span data-ttu-id="62e84-130">Configuration de la transformation d'audit</span><span class="sxs-lookup"><span data-stu-id="62e84-130">Configuration of the Audit Transformation</span></span>  
 <span data-ttu-id="62e84-131">Pour configurer la transformation d'audit, vous devez indiquer le nom d'une nouvelle colonne de sortie à ajouter à la sortie de la transformation, puis mapper la variable système avec la colonne de sortie.</span><span class="sxs-lookup"><span data-stu-id="62e84-131">You configure the Audit transformation by providing the name of a new output column to add to the transformation output, and then mapping the system variable to the output column.</span></span> <span data-ttu-id="62e84-132">Vous pouvez mapper une même variable système avec plusieurs colonnes.</span><span class="sxs-lookup"><span data-stu-id="62e84-132">You can map a single system variable to multiple columns.</span></span>  
  
 <span data-ttu-id="62e84-133">Cette transformation a une entrée et une sortie.</span><span class="sxs-lookup"><span data-stu-id="62e84-133">This transformation has one input and one output.</span></span> <span data-ttu-id="62e84-134">Elle ne prend pas en charge de sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="62e84-134">It does not support an error output.</span></span>  
  
 <span data-ttu-id="62e84-135">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="62e84-135">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="62e84-136">Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur de transformation d'audit** , consultez [Audit Transformation Editor](../../audit-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="62e84-136">For more information about the properties that you can set in the **Audit Transformation Editor** dialog box, see [Audit Transformation Editor](../../audit-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="62e84-137">La boîte de dialogue **Éditeur avancé** reflète les propriétés qui peuvent être définies par programmation.</span><span class="sxs-lookup"><span data-stu-id="62e84-137">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="62e84-138">Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur avancé** ou par programmation, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="62e84-138">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="62e84-139">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="62e84-139">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="62e84-140">Propriétés personnalisées des transformations</span><span class="sxs-lookup"><span data-stu-id="62e84-140">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="62e84-141">Pour plus d’informations sur la façon de définir les propriétés, consultez [Définir les propriétés d’un composant de flux de données](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="62e84-141">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
