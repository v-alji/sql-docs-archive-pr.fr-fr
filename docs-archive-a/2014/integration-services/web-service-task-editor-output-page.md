---
title: Éditeur de tâche de service Web (page sortie) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.webservicestask.output.f1
helpviewer_keywords:
- Web Service Task Editor
ms.assetid: 73c83969-7b0e-479d-a436-0a46b2068d01
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6ad034ae78a096ebe5998ac2c3d2573fe7c3bfd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613518"
---
# <a name="web-service-task-editor-output-page"></a><span data-ttu-id="979e0-102">Éditeur de tâche de service Web (page Sortie)</span><span class="sxs-lookup"><span data-stu-id="979e0-102">Web Service Task Editor (Output Page)</span></span>
  <span data-ttu-id="979e0-103">Utilisez la page **Sortie** de la boîte de dialogue **Éditeur de tâche de service Web** pour définir l’emplacement de stockage du résultat retourné par la méthode web.</span><span class="sxs-lookup"><span data-stu-id="979e0-103">Use the **Output** page of the **Web Service Task Editor** dialog box to specify where to store the result returned by the Web method.</span></span>  
  
 <span data-ttu-id="979e0-104">Pour en savoir plus sur cette tâche, consultez [Tâche de service web](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="979e0-104">To learn about this task, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="979e0-105">Options statiques</span><span class="sxs-lookup"><span data-stu-id="979e0-105">Static Options</span></span>  
 <span data-ttu-id="979e0-106">**OutputType**</span><span class="sxs-lookup"><span data-stu-id="979e0-106">**OutputType**</span></span>  
 <span data-ttu-id="979e0-107">Sélectionnez le type de stockage à utiliser pour stocker le résultat.</span><span class="sxs-lookup"><span data-stu-id="979e0-107">Select the storage type to use when storing the results.</span></span> <span data-ttu-id="979e0-108">Cette propriété dispose des options répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="979e0-108">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="979e0-109">Valeur</span><span class="sxs-lookup"><span data-stu-id="979e0-109">Value</span></span>|<span data-ttu-id="979e0-110">Description</span><span class="sxs-lookup"><span data-stu-id="979e0-110">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="979e0-111">**Connexion de fichiers**</span><span class="sxs-lookup"><span data-stu-id="979e0-111">**File Connection**</span></span>|<span data-ttu-id="979e0-112">Stocke le résultat dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="979e0-112">Store the results in a file.</span></span> <span data-ttu-id="979e0-113">Cette valeur affiche l’option dynamique **Fichier**.</span><span class="sxs-lookup"><span data-stu-id="979e0-113">Selecting this value displays the dynamic option, **File**.</span></span>|  
|<span data-ttu-id="979e0-114">**Variable**</span><span class="sxs-lookup"><span data-stu-id="979e0-114">**Variable**</span></span>|<span data-ttu-id="979e0-115">Stocke le résultat dans une variable.</span><span class="sxs-lookup"><span data-stu-id="979e0-115">Store the results in a variable.</span></span> <span data-ttu-id="979e0-116">Cette valeur affiche l’option dynamique **Variable**.</span><span class="sxs-lookup"><span data-stu-id="979e0-116">Selecting this value displays the dynamic option, **Variable**.</span></span>|  
  
## <a name="outputtype-dynamic-options"></a><span data-ttu-id="979e0-117">Options dynamiques OutputType</span><span class="sxs-lookup"><span data-stu-id="979e0-117">OutputType Dynamic Options</span></span>  
  
### <a name="outputtype--file-connection"></a><span data-ttu-id="979e0-118">OutputType = Connexion de fichiers</span><span class="sxs-lookup"><span data-stu-id="979e0-118">OutputType = File Connection</span></span>  
 <span data-ttu-id="979e0-119">**File**</span><span class="sxs-lookup"><span data-stu-id="979e0-119">**File**</span></span>  
 <span data-ttu-id="979e0-120">Sélectionnez un gestionnaire de connexions de fichiers dans la liste ou cliquez sur \<**New Connection...**> pour créer un gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="979e0-120">Select a File connection manager in the list or click \<**New Connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="979e0-121">**Rubriques connexes :** [Gestionnaire de connexions de fichiers](connection-manager/file-connection-manager.md), [Éditeur du gestionnaire de connexions de fichiers](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="979e0-121">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="outputtype--variable"></a><span data-ttu-id="979e0-122">OutputType = Variable</span><span class="sxs-lookup"><span data-stu-id="979e0-122">OutputType = Variable</span></span>  
 <span data-ttu-id="979e0-123">**Variable**</span><span class="sxs-lookup"><span data-stu-id="979e0-123">**Variable**</span></span>  
 <span data-ttu-id="979e0-124">Sélectionnez une variable dans la liste, ou cliquez sur \<**New Variable...**> pour en créer une.</span><span class="sxs-lookup"><span data-stu-id="979e0-124">Select a variable in the list or click \<**New Variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="979e0-125">**Rubriques connexes :**  [Variables Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Ajouter une variable](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="979e0-125">**Related Topics:**  [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="979e0-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="979e0-126">See Also</span></span>  
 <span data-ttu-id="979e0-127">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="979e0-127">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="979e0-128">[Éditeur de tâche de service Web &#40;page général&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="979e0-128">[Web Service Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="979e0-129">[Éditeur de tâche de service Web &#40;page d’entrée&#41;](../../2014/integration-services/web-service-task-editor-input-page.md) </span><span class="sxs-lookup"><span data-stu-id="979e0-129">[Web Service Task Editor &#40;Input Page&#41;](../../2014/integration-services/web-service-task-editor-input-page.md) </span></span>  
 [<span data-ttu-id="979e0-130">Page Expressions</span><span class="sxs-lookup"><span data-stu-id="979e0-130">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
