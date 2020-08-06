---
title: Paramétrer la boîte de dialogue | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.parameter.f1
ms.assetid: fac02b6d-d247-447a-8940-e8700c7ac350
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8db19844132402740aec092d6e88f3c9e3864d58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605532"
---
# <a name="parameterize-dialog-box"></a><span data-ttu-id="62892-102">Parameterize Dialog Box</span><span class="sxs-lookup"><span data-stu-id="62892-102">Parameterize Dialog Box</span></span>
  <span data-ttu-id="62892-103">La boîte de dialogue **Paramétrer** vous permet d'associer un paramètre nouveau ou existant à la propriété d'une tâche.</span><span class="sxs-lookup"><span data-stu-id="62892-103">The **Parameterize** dialog box enables you to associate a new or an existing parameter with a property of a task.</span></span> <span data-ttu-id="62892-104">Vous ouvrez la boîte de dialogue en cliquant avec le bouton droit sur une tâche ou en affichant l'onglet Flux de contrôle dans le Concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] , puis en cliquant sur **Paramétrer**.</span><span class="sxs-lookup"><span data-stu-id="62892-104">You open the dialog box by right-clicking a task or the Control Flow tab in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer and then by clicking **Parameterize**.</span></span> <span data-ttu-id="62892-105">La liste suivante décrit les éléments d'interface utilisateur de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="62892-105">The following list describes UI elements in the dialog box.</span></span> <span data-ttu-id="62892-106">Pour plus d’informations sur les paramètres, consultez [Paramètres Integration Services &#40;SSIS&#41;](integration-services-ssis-package-and-project-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="62892-106">For more information about parameters, see [Integration Services &#40;SSIS&#41; Parameters](integration-services-ssis-package-and-project-parameters.md).</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="62892-107">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="62892-107">UI element list</span></span>  
 <span data-ttu-id="62892-108">**Propriété**</span><span class="sxs-lookup"><span data-stu-id="62892-108">**Property**</span></span>  
 <span data-ttu-id="62892-109">Sélectionnez la propriété de la tâche que vous souhaitez associer à un paramètre.</span><span class="sxs-lookup"><span data-stu-id="62892-109">Select the property of the task that you want to associate with a parameter.</span></span> <span data-ttu-id="62892-110">Cette liste est remplie avec toutes les propriétés qui sont paramétrables.</span><span class="sxs-lookup"><span data-stu-id="62892-110">This list is populated with all the properties that can be parameterized.</span></span>  
  
 <span data-ttu-id="62892-111">**Utiliser un paramètre existant**</span><span class="sxs-lookup"><span data-stu-id="62892-111">**Use existing parameter**</span></span>  
 <span data-ttu-id="62892-112">Sélectionnez cette option pour associer la propriété de la tâche à un paramètre existant, puis sélectionnez le paramètre dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="62892-112">Select this option to associate the property of task with an existing parameter and then select the parameter from drop-down list.</span></span>  
  
 <span data-ttu-id="62892-113">**Ne pas utiliser de paramètre**</span><span class="sxs-lookup"><span data-stu-id="62892-113">**Do not use parameter**</span></span>  
 <span data-ttu-id="62892-114">Sélectionnez cette option pour supprimer une référence à un paramètre.</span><span class="sxs-lookup"><span data-stu-id="62892-114">Select this option to remove a reference to a parameter.</span></span> <span data-ttu-id="62892-115">Le paramètre n'est pas supprimé.</span><span class="sxs-lookup"><span data-stu-id="62892-115">The parameter is not deleted.</span></span>  
  
 <span data-ttu-id="62892-116">**Créer un nouveau paramètre**</span><span class="sxs-lookup"><span data-stu-id="62892-116">**Create new parameter**</span></span>  
 <span data-ttu-id="62892-117">Sélectionnez cette option pour créer un nouveau paramètre que vous souhaitez associer à la propriété de la tâche.</span><span class="sxs-lookup"><span data-stu-id="62892-117">Select this option to create a new parameter that you want to associate with the property of the task.</span></span>  
  
 <span data-ttu-id="62892-118">**Nom**</span><span class="sxs-lookup"><span data-stu-id="62892-118">**Name**</span></span>  
 <span data-ttu-id="62892-119">Spécifiez le nom du paramètre à créer.</span><span class="sxs-lookup"><span data-stu-id="62892-119">Specify the name of the parameter you want to create.</span></span>  
  
 <span data-ttu-id="62892-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="62892-120">**Description**</span></span>  
 <span data-ttu-id="62892-121">Spécifiez la description du paramètre.</span><span class="sxs-lookup"><span data-stu-id="62892-121">Specify the description for parameter.</span></span>  
  
 <span data-ttu-id="62892-122">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="62892-122">**Value**</span></span>  
 <span data-ttu-id="62892-123">Spécifiez la valeur par défaut du paramètre.</span><span class="sxs-lookup"><span data-stu-id="62892-123">Specify the default value for the parameter.</span></span> <span data-ttu-id="62892-124">Cette opération est aussi appelée « valeur par défaut de conception », qui peut être remplacée ultérieurement au moment du déploiement.</span><span class="sxs-lookup"><span data-stu-id="62892-124">This is also known as the design default, which can be overridden later at the deployment time.</span></span>  
  
 <span data-ttu-id="62892-125">**Portée**</span><span class="sxs-lookup"><span data-stu-id="62892-125">**Scope**</span></span>  
 <span data-ttu-id="62892-126">Spécifiez l'étendue du paramètre en sélectionnant l'option **Projet** ou **Package** .</span><span class="sxs-lookup"><span data-stu-id="62892-126">Specify the scope of the parameter by selecting either **Project** or **Package** option.</span></span> <span data-ttu-id="62892-127">Les paramètres du projet sont utilisés pour fournir une entrée externe que le projet reçoit à un ou plusieurs packages du projet.</span><span class="sxs-lookup"><span data-stu-id="62892-127">Project parameters are used to supply any external input the project receives to one or more packages in the project.</span></span> <span data-ttu-id="62892-128">L'utilisation de paramètres de package vous permet de modifier l'exécution du package sans avoir à modifier et à redéployer le package.</span><span class="sxs-lookup"><span data-stu-id="62892-128">Package parameters allow you to modify package execution without having to edit and redeploy the package.</span></span>  
  
 <span data-ttu-id="62892-129">**Stratégiques**</span><span class="sxs-lookup"><span data-stu-id="62892-129">**Sensitive**</span></span>  
 <span data-ttu-id="62892-130">Spécifiez si le paramètre contient une valeur sensible en activant ou en désactivant la case à cocher.</span><span class="sxs-lookup"><span data-stu-id="62892-130">Specify whether the parameter is a sensitive by checking or clearing the check box.</span></span> <span data-ttu-id="62892-131">Les valeurs de paramètre sensibles sont chiffrées dans le catalogue et apparaissent sous la forme d'une valeur Null lorsqu'elles sont affichées avec Transact-SQL ou SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="62892-131">Sensitive parameter values are encrypted in the catalog and appear as a NULL value when viewed with Transact-SQL or SQL Server Management Studio.</span></span>  
  
 <span data-ttu-id="62892-132">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="62892-132">**Required**</span></span>  
 <span data-ttu-id="62892-133">Spécifiez si le paramètre nécessite qu'une valeur, autre que la valeur de conception par défaut, soit spécifiée pour que le package puisse s'exécuter.</span><span class="sxs-lookup"><span data-stu-id="62892-133">Specify whether the parameter requires that a value, other than the design default, is specified before the package can execute.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="62892-134">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="62892-134">UI element list</span></span>  
  
