---
title: Éditeur de tâche DDL d’exécution de Analysis Services (page DDL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.asexecuteddltask.ddl.f1
helpviewer_keywords:
- Analysis Services Execute DDL Task Editor
ms.assetid: f21bf8d0-ec5f-4c18-9de0-8875addb927b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d207afe666e582c44f1014a6c80f4f4984fd5410
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602972"
---
# <a name="analysis-services-execute-ddl-task-editor-ddl-page"></a><span data-ttu-id="8cbe6-102">Éditeur de tâche DDL d'exécution d'Analysis Services (page DDL)</span><span class="sxs-lookup"><span data-stu-id="8cbe6-102">Analysis Services Execute DDL Task Editor (DDL Page)</span></span>
  <span data-ttu-id="8cbe6-103">Utilisez la page **DDL** de la boîte de dialogue **Éditeur de tâche DDL d’exécution d’Analysis Services** pour spécifier une connexion à un projet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ou à une base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] et fournir des informations sur la source des instructions de langage de définition de données (DDL).</span><span class="sxs-lookup"><span data-stu-id="8cbe6-103">Use the **DDL** page of the **Analysis Services Execute DDL Task Editor** dialog box to specify a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project or an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database and to provide information about the source of data definition language (DDL) statements.</span></span>  
  
 <span data-ttu-id="8cbe6-104">Pour en savoir plus sur cette tâche, consultez [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md).</span><span class="sxs-lookup"><span data-stu-id="8cbe6-104">To learn about this task, see [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="8cbe6-105">Options statiques</span><span class="sxs-lookup"><span data-stu-id="8cbe6-105">Static Options</span></span>  
 <span data-ttu-id="8cbe6-106">**Connection**</span><span class="sxs-lookup"><span data-stu-id="8cbe6-106">**Connection**</span></span>  
 <span data-ttu-id="8cbe6-107">Sélectionnez un projet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ou un gestionnaire de connexions [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] dans la liste, ou cliquez sur \<**New connection...**> et utilisez la boîte de dialogue **Ajout d’un gestionnaire de connexions Analysis Services** pour créer une connexion.</span><span class="sxs-lookup"><span data-stu-id="8cbe6-107">Select an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project or an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] connection manager in the list, or click \<**New connection...**> and use the **Add Analysis Services Connection Manager** dialog box to create a new connection.</span></span>  
  
 <span data-ttu-id="8cbe6-108">**Rubriques connexes :** [Informations de référence sur l’interface utilisateur de la boîte de dialogue Ajout d’un gestionnaire de connexions Analysis Services](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md), [Gestionnaire de connexions Analysis Services](connection-manager/analysis-services-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="8cbe6-108">**Related Topics:** [Add Analysis Services Connection Manager Dialog Box UI Reference](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md), [Analysis Services Connection Manager](connection-manager/analysis-services-connection-manager.md)</span></span>  
  
 <span data-ttu-id="8cbe6-109">**SourceType**</span><span class="sxs-lookup"><span data-stu-id="8cbe6-109">**SourceType**</span></span>  
 <span data-ttu-id="8cbe6-110">Spécifiez le type de source des instructions DDL.</span><span class="sxs-lookup"><span data-stu-id="8cbe6-110">Specify the source type of the DDL statements.</span></span> <span data-ttu-id="8cbe6-111">Cette propriété dispose des options répertoriées dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="8cbe6-111">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="8cbe6-112">Valeur</span><span class="sxs-lookup"><span data-stu-id="8cbe6-112">Value</span></span>|<span data-ttu-id="8cbe6-113">Description</span><span class="sxs-lookup"><span data-stu-id="8cbe6-113">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8cbe6-114">**Entrée directe**</span><span class="sxs-lookup"><span data-stu-id="8cbe6-114">**Direct Input**</span></span>|<span data-ttu-id="8cbe6-115">Définissez la source de l'instruction DDL enregistrée dans la zone de texte **SourceDirect** .</span><span class="sxs-lookup"><span data-stu-id="8cbe6-115">Set the source to the DDL statement stored in the **SourceDirect** text box.</span></span> <span data-ttu-id="8cbe6-116">Sélectionnez cette valeur pour afficher l'option dynamique de la section suivante.</span><span class="sxs-lookup"><span data-stu-id="8cbe6-116">Selecting this value displays the dynamic options in the following section.</span></span>|  
|<span data-ttu-id="8cbe6-117">**Connexion de fichiers**</span><span class="sxs-lookup"><span data-stu-id="8cbe6-117">**File Connection**</span></span>|<span data-ttu-id="8cbe6-118">Définissez la source par un fichier qui contient l'instruction DDL.</span><span class="sxs-lookup"><span data-stu-id="8cbe6-118">Set the source to a file that contains the DDL statement.</span></span> <span data-ttu-id="8cbe6-119">Sélectionnez cette valeur pour afficher l'option dynamique de la section suivante.</span><span class="sxs-lookup"><span data-stu-id="8cbe6-119">Selecting this value displays the dynamic options in the following section.</span></span>|  
|<span data-ttu-id="8cbe6-120">**Variable**</span><span class="sxs-lookup"><span data-stu-id="8cbe6-120">**Variable**</span></span>|<span data-ttu-id="8cbe6-121">Définissez la source par une variable.</span><span class="sxs-lookup"><span data-stu-id="8cbe6-121">Set the source to a variable.</span></span> <span data-ttu-id="8cbe6-122">Sélectionnez cette valeur pour afficher l'option dynamique de la section suivante.</span><span class="sxs-lookup"><span data-stu-id="8cbe6-122">Selecting this value displays the dynamic options in the following section.</span></span>|  
  
## <a name="dynamic-options"></a><span data-ttu-id="8cbe6-123">Options dynamiques</span><span class="sxs-lookup"><span data-stu-id="8cbe6-123">Dynamic Options</span></span>  
  
### <a name="sourcetype--direct-input"></a><span data-ttu-id="8cbe6-124">SourceType = Entrée directe</span><span class="sxs-lookup"><span data-stu-id="8cbe6-124">SourceType = Direct Input</span></span>  
 <span data-ttu-id="8cbe6-125">**Source**</span><span class="sxs-lookup"><span data-stu-id="8cbe6-125">**Source**</span></span>  
 <span data-ttu-id="8cbe6-126">Tapez les instructions DDL ou cliquez sur le bouton représentant des points de suspension **(...)** , puis tapez les instructions dans la boîte de dialogue **Instructions DDL**.</span><span class="sxs-lookup"><span data-stu-id="8cbe6-126">Type the DDL statements or click the ellipsis **(...)** and then type the statements in the **DDL Statements** dialog box.</span></span>  
  
### <a name="sourcetype--file-connection"></a><span data-ttu-id="8cbe6-127">SourceType = Connexion de fichiers</span><span class="sxs-lookup"><span data-stu-id="8cbe6-127">SourceType = File Connection</span></span>  
 <span data-ttu-id="8cbe6-128">**Source**</span><span class="sxs-lookup"><span data-stu-id="8cbe6-128">**Source**</span></span>  
 <span data-ttu-id="8cbe6-129">Sélectionnez une connexion de fichiers dans la liste ou cliquez sur \<**New connection...**> et utilisez la boîte de dialogue **Gestionnaire de connexions de fichiers** pour créer une connexion.</span><span class="sxs-lookup"><span data-stu-id="8cbe6-129">Select a File connection in the list, or click \<**New connection...**> and use the **File Connection Manager** dialog box to create a new connection.</span></span>  
  
 <span data-ttu-id="8cbe6-130">**Rubriques connexes :** [Gestionnaire de connexions de fichiers](connection-manager/file-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="8cbe6-130">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md)</span></span>  
  
### <a name="sourcetype--variable"></a><span data-ttu-id="8cbe6-131">SourceType = Variable</span><span class="sxs-lookup"><span data-stu-id="8cbe6-131">SourceType = Variable</span></span>  
 <span data-ttu-id="8cbe6-132">**Source**</span><span class="sxs-lookup"><span data-stu-id="8cbe6-132">**Source**</span></span>  
 <span data-ttu-id="8cbe6-133">Sélectionnez une variable dans la liste ou cliquez sur \<**New variable...**> et utilisez la boîte de dialogue **Ajouter une variable** pour créer une variable.</span><span class="sxs-lookup"><span data-stu-id="8cbe6-133">Select a variable in the list, or click \<**New variable...**> and use the **Add Variable** dialog box to create a new variable.</span></span>  
  
 <span data-ttu-id="8cbe6-134">**Rubriques connexes :** [Variables Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md)</span><span class="sxs-lookup"><span data-stu-id="8cbe6-134">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cbe6-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8cbe6-135">See Also</span></span>  
 <span data-ttu-id="8cbe6-136">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="8cbe6-136">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="8cbe6-137">[Analysis Services éditeur de tâche DDL d’exécution &#40;page général&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="8cbe6-137">[Analysis Services Execute DDL Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="8cbe6-138">[Page Expressions](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="8cbe6-138">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="8cbe6-139">[Flux de contrôle](control-flow/control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="8cbe6-139">[Control Flow](control-flow/control-flow.md) </span></span>  
 <span data-ttu-id="8cbe6-140">[Analysis Services&#41; référence du langage de script &#40;ASSL](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla) </span><span class="sxs-lookup"><span data-stu-id="8cbe6-140">[Analysis Services Scripting Language &#40;ASSL&#41; Reference](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla) </span></span>  
 [<span data-ttu-id="8cbe6-141">Référence XML for Analysis &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="8cbe6-141">XML for Analysis  &#40;XMLA&#41; Reference</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference)  
  
  
