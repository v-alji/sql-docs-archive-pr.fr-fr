---
title: Éditeur de tâche d’insertion en bloc (page connexion) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.bulkinserttask.connection.f1
helpviewer_keywords:
- Bulk Insert Task Editor
ms.assetid: 51252c20-8865-4ede-a3fd-bd73a968f47d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b2cd722fd8520ff011c0d57040a55d624178e15e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706680"
---
# <a name="bulk-insert-task-editor-connection-page"></a><span data-ttu-id="74afc-102">Éditeur de tâche d'insertion en bloc (page Connexion)</span><span class="sxs-lookup"><span data-stu-id="74afc-102">Bulk Insert Task Editor (Connection Page)</span></span>
  <span data-ttu-id="74afc-103">Utilisez la page **Connexion** de la boîte de dialogue **Éditeur de tâche d'insertion en bloc** pour définir la source et la destination de l'opération d'insertion en bloc et le format à utiliser.</span><span class="sxs-lookup"><span data-stu-id="74afc-103">Use the **Connection** page of the **Bulk Insert Task Editor** dialog box to specify the source and destination of the bulk insert operation and the format to use.</span></span>  
  
 <span data-ttu-id="74afc-104">Pour en savoir plus sur l’utilisation des insertions en bloc, consultez [Tâche d’insertion en bloc](control-flow/bulk-insert-task.md) et [Fichiers de format pour l’importation ou l’exportation de données &#40;SQL Server&#41;](../relational-databases/import-export/format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="74afc-104">To learn about working with bulk inserts, see [Bulk Insert Task](control-flow/bulk-insert-task.md) and [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](../relational-databases/import-export/format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="74afc-105">Options</span><span class="sxs-lookup"><span data-stu-id="74afc-105">Options</span></span>  
 <span data-ttu-id="74afc-106">**Connection**</span><span class="sxs-lookup"><span data-stu-id="74afc-106">**Connection**</span></span>  
 <span data-ttu-id="74afc-107">Sélectionnez un gestionnaire de connexions OLE DB dans la liste ou cliquez sur \<**New connection...**> pour créer une connexion.</span><span class="sxs-lookup"><span data-stu-id="74afc-107">Select an OLE DB connection manager in the list, or click \<**New connection...**> to create a new connection.</span></span>  
  
 <span data-ttu-id="74afc-108">**Rubriques connexes :** [Gestionnaire de connexions OLE DB](connection-manager/ole-db-connection-manager.md), [Configurer le gestionnaire de connexions OLE DB](../../2014/integration-services/configure-ole-db-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="74afc-108">**Related Topics:** [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md), [Configure OLE DB Connection Manager](../../2014/integration-services/configure-ole-db-connection-manager.md)</span></span>  
  
 <span data-ttu-id="74afc-109">**Table de destination**</span><span class="sxs-lookup"><span data-stu-id="74afc-109">**DestinationTable**</span></span>  
 <span data-ttu-id="74afc-110">Tapez le nom de la table de destination ou affichez ou sélectionnez une table ou une vue dans la liste.</span><span class="sxs-lookup"><span data-stu-id="74afc-110">Type the name of the destination table or view or select a table or view in the list.</span></span>  
  
 <span data-ttu-id="74afc-111">**Format**</span><span class="sxs-lookup"><span data-stu-id="74afc-111">**Format**</span></span>  
 <span data-ttu-id="74afc-112">Sélectionnez la source du format de l'insertion en bloc.</span><span class="sxs-lookup"><span data-stu-id="74afc-112">Select the source of the format for the bulk insert.</span></span> <span data-ttu-id="74afc-113">Cette propriété dispose des options répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="74afc-113">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="74afc-114">Valeur</span><span class="sxs-lookup"><span data-stu-id="74afc-114">Value</span></span>|<span data-ttu-id="74afc-115">Description</span><span class="sxs-lookup"><span data-stu-id="74afc-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="74afc-116">**Utiliser un fichier**</span><span class="sxs-lookup"><span data-stu-id="74afc-116">**Use File**</span></span>|<span data-ttu-id="74afc-117">Sélectionnez un fichier contenant la spécification de format.</span><span class="sxs-lookup"><span data-stu-id="74afc-117">Select a file containing the format specification.</span></span> <span data-ttu-id="74afc-118">Cette option affiche l'option dynamique **FormatFile**.</span><span class="sxs-lookup"><span data-stu-id="74afc-118">Selecting this option displays the dynamic option, **FormatFile**.</span></span>|  
|<span data-ttu-id="74afc-119">**Spécifier**</span><span class="sxs-lookup"><span data-stu-id="74afc-119">**Specify**</span></span>|<span data-ttu-id="74afc-120">Spécifiez le format.</span><span class="sxs-lookup"><span data-stu-id="74afc-120">Specify the format.</span></span> <span data-ttu-id="74afc-121">La sélection de cette option permet d’afficher les options dynamiques `RowDelimiter` et `ColumnDelimiter` .</span><span class="sxs-lookup"><span data-stu-id="74afc-121">Selecting this option displays the dynamic options, `RowDelimiter` and `ColumnDelimiter`.</span></span>|  
  
 <span data-ttu-id="74afc-122">**File**</span><span class="sxs-lookup"><span data-stu-id="74afc-122">**File**</span></span>  
 <span data-ttu-id="74afc-123">Sélectionnez un gestionnaire de connexions de fichiers ou de fichiers plats dans la liste, ou cliquez sur \<**New connection...**> pour créer une connexion.</span><span class="sxs-lookup"><span data-stu-id="74afc-123">Select a File or Flat File connection manager in the list, or click \<**New connection...**> to create a new connection.</span></span>  
  
 <span data-ttu-id="74afc-124">L'emplacement du fichier dépend du moteur de base de données SQL Server spécifié dans le gestionnaire de connexions pour cette tâche.</span><span class="sxs-lookup"><span data-stu-id="74afc-124">The file location is relative to the SQL Server Database Engine specified in the connection manager for this task.</span></span> <span data-ttu-id="74afc-125">Le fichier texte doit être accessible au moteur de base de données SQL Server situé sur un disque dur local du serveur ou via un partage ou un lecteur mappé à SQL Server.</span><span class="sxs-lookup"><span data-stu-id="74afc-125">The text file must be accessible by the SQL Server Database Engine either on a local hard drive on the server, or via a share or mapped drive to the SQL Server.</span></span> <span data-ttu-id="74afc-126">Le fichier n'est pas accessible au runtime SSIS.</span><span class="sxs-lookup"><span data-stu-id="74afc-126">The file is not accessed by the SSIS Runtime.</span></span>  
  
 <span data-ttu-id="74afc-127">Si vous accédez au fichier source en utilisant un gestionnaire de connexions de fichiers plats, la tâche d'insertion en bloc n'utilise pas le format défini dans le gestionnaire de connexions de fichiers plats.</span><span class="sxs-lookup"><span data-stu-id="74afc-127">If you access the source file by using a Flat File connection manager, the Bulk Insert task does not use the format specified in the Flat File connection manager.</span></span> <span data-ttu-id="74afc-128">Elle utilise à la place le format spécifié dans un fichier de format, ou les valeurs des propriétés RowDelimiter et ColumnDelimiter de la tâche.</span><span class="sxs-lookup"><span data-stu-id="74afc-128">Instead, the Bulk Insert task uses either the format specified in a format file or the values of the RowDelimiter and ColumnDelimiter properties of the task.</span></span>  
  
 <span data-ttu-id="74afc-129">**Rubriques connexes :** [Gestionnaire de connexions de fichiers](connection-manager/file-connection-manager.md), [Éditeur du gestionnaire de connexions de fichiers](../../2014/integration-services/file-connection-manager-editor.md), [Gestionnaire de connexions de fichiers plats](connection-manager/flat-file-connection-manager.md), [Éditeur du gestionnaire de connexions de fichiers plats &#40;page Général&#41;](general-page-of-integration-services-designers-options.md), [Éditeur du gestionnaire de connexions de fichiers plats &#40;page Colonnes&#41;](../../2014/integration-services/flat-file-connection-manager-editor-columns-page.md), [Éditeur du gestionnaire de connexions de fichiers plats &#40;page Avancé&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md)</span><span class="sxs-lookup"><span data-stu-id="74afc-129">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md), [Flat File Connection Manager](connection-manager/flat-file-connection-manager.md), [Flat File Connection Manager Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md), [Flat File Connection Manager Editor &#40;Columns Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-columns-page.md), [Flat File Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md)</span></span>  
  
 <span data-ttu-id="74afc-130">**Actualiser les tables**</span><span class="sxs-lookup"><span data-stu-id="74afc-130">**Refresh Tables**</span></span>  
 <span data-ttu-id="74afc-131">Actualise la liste des tables et des vues.</span><span class="sxs-lookup"><span data-stu-id="74afc-131">Refresh the list of tables and views.</span></span>  
  
## <a name="format-dynamic-options"></a><span data-ttu-id="74afc-132">Options dynamiques de format</span><span class="sxs-lookup"><span data-stu-id="74afc-132">Format Dynamic Options</span></span>  
  
### <a name="format--use-file"></a><span data-ttu-id="74afc-133">Format = Utiliser un fichier</span><span class="sxs-lookup"><span data-stu-id="74afc-133">Format = Use File</span></span>  
 <span data-ttu-id="74afc-134">**FormatFile**</span><span class="sxs-lookup"><span data-stu-id="74afc-134">**FormatFile**</span></span>  
 <span data-ttu-id="74afc-135">Tapez le chemin du fichier de format ou cliquez sur le bouton avec des points de suspension **(...)** pour rechercher le fichier de format.</span><span class="sxs-lookup"><span data-stu-id="74afc-135">Type the path of the format file or click the ellipsis button **(...)** to locate the format file.</span></span>  
  
### <a name="format--specify"></a><span data-ttu-id="74afc-136">Format = Spécifier</span><span class="sxs-lookup"><span data-stu-id="74afc-136">Format = Specify</span></span>  
 `RowDelimiter`  
 <span data-ttu-id="74afc-137">Spécifiez le délimiteur de ligne dans le fichier source.</span><span class="sxs-lookup"><span data-stu-id="74afc-137">Specify the row delimiter in the source file.</span></span> <span data-ttu-id="74afc-138">La valeur par défaut est **{CR}{LF}** .</span><span class="sxs-lookup"><span data-stu-id="74afc-138">The default value is **{CR}{LF}**.</span></span>  
  
 `ColumnDelimiter`  
 <span data-ttu-id="74afc-139">Spécifiez le délimiteur de colonne dans le fichier source.</span><span class="sxs-lookup"><span data-stu-id="74afc-139">Specify the column delimiter in the source file.</span></span> <span data-ttu-id="74afc-140">La valeur par défaut est **Tab**.</span><span class="sxs-lookup"><span data-stu-id="74afc-140">The default is **Tab**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74afc-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="74afc-141">See Also</span></span>  
 <span data-ttu-id="74afc-142">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="74afc-142">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="74afc-143">[Éditeur de tâche d’insertion en bloc &#40;page général&#41;](../../2014/integration-services/bulk-insert-task-editor-general-page.md) </span><span class="sxs-lookup"><span data-stu-id="74afc-143">[Bulk Insert Task Editor &#40;General Page&#41;](../../2014/integration-services/bulk-insert-task-editor-general-page.md) </span></span>  
 <span data-ttu-id="74afc-144">[Éditeur de tâche d’insertion en bloc &#40;page Options&#41;](../../2014/integration-services/bulk-insert-task-editor-options-page.md) </span><span class="sxs-lookup"><span data-stu-id="74afc-144">[Bulk Insert Task Editor &#40;Options Page&#41;](../../2014/integration-services/bulk-insert-task-editor-options-page.md) </span></span>  
 <span data-ttu-id="74afc-145">[Page Expressions](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="74afc-145">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="74afc-146">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="74afc-146">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 [<span data-ttu-id="74afc-147">Flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="74afc-147">Control Flow</span></span>](control-flow/control-flow.md)  
  
  
