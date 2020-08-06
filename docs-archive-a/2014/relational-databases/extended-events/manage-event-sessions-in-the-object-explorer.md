---
title: Gérer les sessions d’événements dans l’Explorateur d’objets | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
ms.assetid: 16849e38-d3fb-414d-8dcb-797b5ffce6ee
author: rothja
ms.author: jroth
ms.openlocfilehash: 1aa33a97137f63348898e6b1fcb7b19b2d218573
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600913"
---
# <a name="manage-event-sessions-in-the-object-explorer"></a><span data-ttu-id="65683-102">Gérer les sessions d'événements dans l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="65683-102">Manage Event Sessions in the Object Explorer</span></span>
  <span data-ttu-id="65683-103">Cette rubrique décrit les actions effectuées dans l' **Explorateur d'objets** qui affectent les événements étendus :</span><span class="sxs-lookup"><span data-stu-id="65683-103">This topic discusses the actions you can take in **Object Explorer** that affect Extended Events:</span></span>  
  
-   <span data-ttu-id="65683-104">Créer une session d'événements étendus</span><span class="sxs-lookup"><span data-stu-id="65683-104">Create an Extended Events Session</span></span>  
  
-   <span data-ttu-id="65683-105">Démarrer ou arrêter une session d'événements étendus</span><span class="sxs-lookup"><span data-stu-id="65683-105">Starting or Stopping an Extended Events Session</span></span>  
  
-   <span data-ttu-id="65683-106">Exporter une session d'événements étendus</span><span class="sxs-lookup"><span data-stu-id="65683-106">Export an Extended Events Session</span></span>  
  
-   <span data-ttu-id="65683-107">Importer un modèle de session d'événements étendus</span><span class="sxs-lookup"><span data-stu-id="65683-107">Import an Extended Events Session Template</span></span>  
  
-   <span data-ttu-id="65683-108">Modifier une session d'événements étendus</span><span class="sxs-lookup"><span data-stu-id="65683-108">Edit an Extended Events Session</span></span>  
  
-   <span data-ttu-id="65683-109">Supprimer une session d'événements étendus</span><span class="sxs-lookup"><span data-stu-id="65683-109">Delete an Extended Events Session</span></span>  
  
## <a name="create-an-extended-events-session"></a><span data-ttu-id="65683-110">Créer une session d'événements étendus</span><span class="sxs-lookup"><span data-stu-id="65683-110">Create an Extended Events Session</span></span>  
 <span data-ttu-id="65683-111">Pour plus d'informations sur la création d'une session d'événements étendus, consultez [Create an Extended Events Session](../../database-engine/create-an-extended-events-session.md).</span><span class="sxs-lookup"><span data-stu-id="65683-111">For more information about creating an Extended Events session, see [Create an Extended Events Session](../../database-engine/create-an-extended-events-session.md).</span></span>  
  
## <a name="starting-or-stopping-an-extended-events-session"></a><span data-ttu-id="65683-112">Démarrer ou arrêter une session d'événements étendus</span><span class="sxs-lookup"><span data-stu-id="65683-112">Starting or Stopping an Extended Events Session</span></span>  
 <span data-ttu-id="65683-113">Vous pouvez démarrer ou arrêter une session d’événements étendus via l' **éditeur de requête** à l’aide de l' `ALTER EVENT SESSION` instruction, ou en utilisant le nœud **événements étendus** de l' **Explorateur d’objets**.</span><span class="sxs-lookup"><span data-stu-id="65683-113">You can start or stop an Extended Events session through the **Query Editor** using the `ALTER EVENT SESSION` statement, or by using the **Extended Events** node of **Object Explorer**.</span></span>  
  
 <span data-ttu-id="65683-114">Quand vous arrêtez une session d’événements, la session n’apparaît plus comme une session active dans la vue de gestion dynamique sys.dm_xe_sessions.</span><span class="sxs-lookup"><span data-stu-id="65683-114">When you stop an event session, the session is no longer listed as an active session in the sys.dm_xe_sessions dynamic management view (DMV).</span></span> <span data-ttu-id="65683-115">Toutefois, la définition de session reste intacte, et vous pouvez redémarrer la session.</span><span class="sxs-lookup"><span data-stu-id="65683-115">However, the session definition remains intact, and you can restart the session.</span></span> <span data-ttu-id="65683-116">Pour supprimer complètement une définition de session, vous devez supprimer la session.</span><span class="sxs-lookup"><span data-stu-id="65683-116">To completely remove a session definition, you must delete the session.</span></span>  
  
 <span data-ttu-id="65683-117">Pour démarrer ou arrêter une session d'événements étendus, vous devez disposer de l'autorisation ALTER ANY EVENT SESSION.</span><span class="sxs-lookup"><span data-stu-id="65683-117">To start or stop an Extended Events session, you must have the ALTER ANY EVENT SESSION permission.</span></span>  
  
 <span data-ttu-id="65683-118">Quand vous arrêtez une session qui utilise une cible en mémoire, telle que la cible de mémoire tampon en anneau, la cible de création de compartiments, la cible d’appariement d’événements ou la cible de compteur d’événements synchrone, toutes les informations stockées dans la mémoire tampon de la session (colonne target_data de la vue de gestion dynamique sys.dm_xe_session_targets) sont perdues.</span><span class="sxs-lookup"><span data-stu-id="65683-118">When you stop a session that uses an in-memory target, such as the ring buffer, bucketing, event pairing, or synchronous event counter targets, all the information stored in the session's buffer (the target_data column of the sys.dm_xe_session_targets DMV) will be lost.</span></span> <span data-ttu-id="65683-119">Pour accéder aux données d'un événement après avoir interrompu une session, vous devez enregistrer les données avant de mettre fin à la session ou configurer la session pour pouvoir utiliser un fichier cible.</span><span class="sxs-lookup"><span data-stu-id="65683-119">To access event data after you stop the session, you should either save the data before you stop the session, or configure the session to use the file target.</span></span>  
  
### <a name="start-or-stop-an-extended-events-session-using-query-editor"></a><span data-ttu-id="65683-120">Démarrer ou arrêter une session d'événements étendus à l'aide de l'Éditeur de requête</span><span class="sxs-lookup"><span data-stu-id="65683-120">Start or Stop an Extended Events Session Using Query Editor</span></span>  
 <span data-ttu-id="65683-121">Pour démarrer une session, émettez les instructions suivantes, en remplaçant *session_name* par le nom de la session d’événements étendus :</span><span class="sxs-lookup"><span data-stu-id="65683-121">To start a session, issue the following statements, replacing *session_name* with the name of the Extended Events session:</span></span>  
  
```  
ALTER EVENT SESSION [session_name]  
ON SERVER  
STATE = START  
```  
  
 <span data-ttu-id="65683-122">Pour arrêter une session, émettez les instructions suivantes, en remplaçant *session_name* par le nom de la session d’événements étendus :</span><span class="sxs-lookup"><span data-stu-id="65683-122">To stop a session, issue the following statements, replacing *session_name* with the name of the Extended Events session:</span></span>  
  
```  
ALTER EVENT SESSION [session_name]  
ON SERVER  
STATE = STOP  
```  
  
### <a name="start-or-stop-an-extended-events-session-in-object-explorer"></a><span data-ttu-id="65683-123">Démarrer ou arrêter une session d'événements étendus dans l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="65683-123">Start or Stop an Extended Events Session in Object Explorer</span></span>  
 <span data-ttu-id="65683-124">Pour démarrer ou arrêter une session d'événements étendus dans l' **Explorateur d'objets**, développez **Gestion**, **Événements étendus**, puis les nœuds **Sessions** ; cliquez ensuite avec le bouton droit sur une session, puis cliquez sur **Démarrer la session** ou sur **Arrêter la session**.</span><span class="sxs-lookup"><span data-stu-id="65683-124">To start or stop an Extended Events session in **Object Explorer**, expand the **Management**, **Extended Events**, and then **Sessions** nodes and right click on a session and then click **Start Session** or **Stop Session**.</span></span>  
  
## <a name="export-an-extended-events-session-template"></a><span data-ttu-id="65683-125">Exporter un modèle de session d'événements étendus</span><span class="sxs-lookup"><span data-stu-id="65683-125">Export an Extended Events Session Template</span></span>  
 <span data-ttu-id="65683-126">Vous pouvez exporter une session d'événements étendus à l'aide de l' **Explorateur d'objets**, puis l'enregistrer en tant que fichier modèle .xml.</span><span class="sxs-lookup"><span data-stu-id="65683-126">You can export an Extended Events session using **Object Explorer**, and save it as an .xml template file.</span></span> <span data-ttu-id="65683-127">Par exemple, vous pouvez exporter une session, puis appliquer le modèle à une nouvelle session d'événements à l'aide de l' **Assistant Nouvelle session** ou de l'interface **Nouvelle session** .</span><span class="sxs-lookup"><span data-stu-id="65683-127">For example, you may want to export a session and then apply the template to a new event session using the **New Session Wizard** or the **New Session** wizard.</span></span>  
  
 <span data-ttu-id="65683-128">Lorsque vous exportez une session, assurez-vous d'enregistrer le fichier modèle à un emplacement qui utilise le système de fichiers NTFS, et que vous limitez l'accès aux utilisateurs autorisés à afficher les informations.</span><span class="sxs-lookup"><span data-stu-id="65683-128">When you export a session, make sure that you save the template file to a location that uses the NTFS file system, and that you restrict access to users who are authorized to view the information.</span></span>  
  
 <span data-ttu-id="65683-129">Pour exporter une session d'événements étendus à l'aide de l' **Explorateur d'objets**:</span><span class="sxs-lookup"><span data-stu-id="65683-129">To export an Extended Events session in **Object Explorer**:</span></span>  
  
1.  <span data-ttu-id="65683-130">Développez les nœuds **Gestion**, **Événements étendus**, puis **Sessions** .</span><span class="sxs-lookup"><span data-stu-id="65683-130">Expand the **Management**, **Extended Events**, and then **Sessions** nodes</span></span>  
  
2.  <span data-ttu-id="65683-131">Cliquez avec le bouton droit sur la session à exporter, puis sélectionnez **Exporter une session**.</span><span class="sxs-lookup"><span data-stu-id="65683-131">Right-click the session that you want to export, and select **Export Session**.</span></span>  
  
3.  <span data-ttu-id="65683-132">Dans la boîte de dialogue **Enregistrer sous** , sélectionnez un emplacement pour enregistrer le fichier, tapez le nom du fichier dans la zone **Nom de fichier** , puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="65683-132">In the **Save As** dialog box, select a location to save the file, type the file name in the **File name** box, and then click **Save**.</span></span>  
  
     <span data-ttu-id="65683-133">Si vous enregistrez le fichier à l'emplacement de modèle par défaut [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , le modèle s'affiche dans la liste déroulante des modèles prédéfinis lorsque vous utilisez l' **Assistant Nouvelle session** et la boîte de dialogue **Nouvelle session** .</span><span class="sxs-lookup"><span data-stu-id="65683-133">If you save the file to the default [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] template location, the template will appear in the dropdown list of predefined templates when you use the **New Session Wizard** and **New Session** dialog.</span></span>  
  
## <a name="import-an-extended-events-session-template"></a><span data-ttu-id="65683-134">Importer un modèle de session d'événements étendus</span><span class="sxs-lookup"><span data-stu-id="65683-134">Import an Extended Events Session Template</span></span>  
 <span data-ttu-id="65683-135">À l'aide de l' **Explorateur d'objets**, vous pouvez importer un modèle pour une session d'événements étendus.</span><span class="sxs-lookup"><span data-stu-id="65683-135">Using **Object Explorer**, you can import a template for an Extended Events session.</span></span> <span data-ttu-id="65683-136">Par exemple, vous pouvez souhaiter procéder ainsi pour créer une session a partir d'un modèle qui a été exporté à partir d'une autre instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65683-136">For example, you may want to do this to create a session from a template that was exported from another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="65683-137">Pour importer une session d'événements étendus, vous devez disposer des autorisations `ALTER ANY EVENT SESSION` nécessaires.</span><span class="sxs-lookup"><span data-stu-id="65683-137">To import an Extended Events session, you must have the necessary `ALTER ANY EVENT SESSION` permissions.</span></span>  
  
 <span data-ttu-id="65683-138">Avant d'importer un fichier modèle, vérifiez que le fichier provient d'une source approuvée.</span><span class="sxs-lookup"><span data-stu-id="65683-138">Before you import a template file, make sure that the file is from a trusted source.</span></span> <span data-ttu-id="65683-139">Les fichiers modèles doivent être enregistrés dans un emplacement qui utilise le système de fichiers NTFS et où l'accès est limité aux utilisateurs qui sont autorisés à afficher les informations.</span><span class="sxs-lookup"><span data-stu-id="65683-139">Template files should be saved to a location that uses the NTFS file system and where access is restricted to users who are authorized to view the information.</span></span>  
  
 <span data-ttu-id="65683-140">Pour importer une session d'événements étendus :</span><span class="sxs-lookup"><span data-stu-id="65683-140">To import an Extended Events session:</span></span>  
  
1.  <span data-ttu-id="65683-141">Dans l' **Explorateur d'objets**, développez les nœuds **Gestion**, puis **Événements étendus** .</span><span class="sxs-lookup"><span data-stu-id="65683-141">In **Object Explorer**, expand the **Management**, and then **Extended Events** nodes.</span></span>  
  
2.  <span data-ttu-id="65683-142">Cliquez avec le bouton droit sur **Sessions** et sélectionnez **Nouvelle session**.</span><span class="sxs-lookup"><span data-stu-id="65683-142">Right-click **Sessions** and select **New Session**.</span></span>  
  
3.  <span data-ttu-id="65683-143">Donnez un nom à la session.</span><span class="sxs-lookup"><span data-stu-id="65683-143">Specify a name for the session.</span></span>  
  
4.  <span data-ttu-id="65683-144">Développez la zone déroulante **Modèle** .</span><span class="sxs-lookup"><span data-stu-id="65683-144">Expand the **Template** drop down box.</span></span>  
  
5.  <span data-ttu-id="65683-145">Cliquez sur **\<File From ...>Ouvrir** et recherchez la session (fichier XML) que vous souhaitez importer.</span><span class="sxs-lookup"><span data-stu-id="65683-145">Click **\<File From ...>Open** and browse for the session (XML file) you want to import.</span></span>  
  
 <span data-ttu-id="65683-146">La session apparaît sous le nœud **Sessions** .</span><span class="sxs-lookup"><span data-stu-id="65683-146">The session appears under the **Sessions** node.</span></span> <span data-ttu-id="65683-147">Par défaut, la session n'est pas démarrée.</span><span class="sxs-lookup"><span data-stu-id="65683-147">By default, the session is not started.</span></span>  
  
## <a name="edit-an-extended-events-session"></a><span data-ttu-id="65683-148">Modifier une session d'événements étendus</span><span class="sxs-lookup"><span data-stu-id="65683-148">Edit an Extended Events Session</span></span>  
 <span data-ttu-id="65683-149">Vous pouvez modifier une session d'événements étendus dans l'Explorateur d'objets.</span><span class="sxs-lookup"><span data-stu-id="65683-149">You can edit an Extended Events session in Object Explorer.</span></span>  
  
 <span data-ttu-id="65683-150">Pour modifier une session d'événements étendus :</span><span class="sxs-lookup"><span data-stu-id="65683-150">To edit an Extended Events session:</span></span>  
  
1.  <span data-ttu-id="65683-151">Dans l' **Explorateur d'objets**, développez les nœuds **Gestion**, **Événements étendus**, puis **Sessions** .</span><span class="sxs-lookup"><span data-stu-id="65683-151">In **Object Explorer**, expand the **Management**, **Extended Events**, and then **Sessions** nodes.</span></span>  
  
2.  <span data-ttu-id="65683-152">Cliquez avec le bouton droit sur une session et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="65683-152">Right-click a session and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="65683-153">Dans la section **Sélectionner une page** , sélectionnez la ou les pages que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="65683-153">In the **Select a page** section, select the page or pages you want to edit.</span></span>  
  
4.  <span data-ttu-id="65683-154">Après avoir modifié la session d'événements, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="65683-154">After you finish revising the event session, click **OK**.</span></span>  
  
## <a name="script-an-event-session-definition-using-tsql"></a><span data-ttu-id="65683-155">Générer le script d'une définition de session d'événements à l'aide de [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65683-155">Script an Event Session Definition Using [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
 <span data-ttu-id="65683-156">L'Assistant Nouvelle session et la boîte de dialogue Nouvelle session comprennent une option qui génère un script [!INCLUDE[tsql](../../includes/tsql-md.md)] définissant la session événements étendus.</span><span class="sxs-lookup"><span data-stu-id="65683-156">Both the New Session Wizard and the New Session dialog have a Script option that generates the [!INCLUDE[tsql](../../includes/tsql-md.md)] that defines the Extended Events session.</span></span>  
  
 <span data-ttu-id="65683-157">Vous pouvez accéder à [!INCLUDE[tsql](../../includes/tsql-md.md)] pour une session d'événements étendus existante en cliquant sur le nom de la session, en sélectionnant **Générer un script de la session en tant que**, puis sélectionnant **Créer vers**.</span><span class="sxs-lookup"><span data-stu-id="65683-157">You can access the [!INCLUDE[tsql](../../includes/tsql-md.md)] for an existing Extended Events session by right clicking the session name, selecting **Script Session as**, and then selecting **Create to**.</span></span>  
  
## <a name="delete-an-extended-events-session"></a><span data-ttu-id="65683-158">Supprimer une session d'événements étendus</span><span class="sxs-lookup"><span data-stu-id="65683-158">Delete an Extended Events Session</span></span>  
 <span data-ttu-id="65683-159">Vous pouvez supprimer une session d'événements étendus :</span><span class="sxs-lookup"><span data-stu-id="65683-159">You can delete an Extended Events session:</span></span>  
  
-   <span data-ttu-id="65683-160">Dans l'Éditeur de requête, à l'aide de `DROP EVENT SESSION`.</span><span class="sxs-lookup"><span data-stu-id="65683-160">In Query Editor using `DROP EVENT SESSION`.</span></span>  
  
-   <span data-ttu-id="65683-161">Dans l' **Explorateur d'objets**.</span><span class="sxs-lookup"><span data-stu-id="65683-161">In **Object Explorer**.</span></span>  
  
 <span data-ttu-id="65683-162">Quand vous supprimez une session d’événements, toutes les informations de configuration sont supprimées, et la définition de session ne s’affiche plus dans l’affichage catalogue sys.server_event_sessions.</span><span class="sxs-lookup"><span data-stu-id="65683-162">When you delete an event session, all configuration information is removed and the session definition no longer appears in the sys.server_event_sessions catalog view.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="65683-163">system_health et AlwaysOn_health sont inclus avec [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ; ne les supprimez pas.</span><span class="sxs-lookup"><span data-stu-id="65683-163">system_health and AlwaysOn_health are included with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]; do not delete them.</span></span> <span data-ttu-id="65683-164">system_health est activée par défaut (pour plus d’informations, consultez [Utiliser la session system_health](use-the-ssms-xe-profiler.md)).</span><span class="sxs-lookup"><span data-stu-id="65683-164">system_health is enabled by default (for more information, see [Use the system_health Session](use-the-ssms-xe-profiler.md)).</span></span> <span data-ttu-id="65683-165">AlwaysOn_health est désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="65683-165">AlwaysOn_health is off by default.</span></span> <span data-ttu-id="65683-166">Ces sessions collectent des données qui peuvent être utiles pour le diagnostic des problèmes de performances.</span><span class="sxs-lookup"><span data-stu-id="65683-166">These sessions collect data that can be useful for diagnosing performance issues.</span></span>  
  
 <span data-ttu-id="65683-167">Pour supprimer une session d'événements étendus, vous devez disposer de l'autorisation ALTER ANY EVENT SESSION.</span><span class="sxs-lookup"><span data-stu-id="65683-167">To delete an Extended Events session, you must have the ALTER ANY EVENT SESSION permission.</span></span>  
  
 <span data-ttu-id="65683-168">Pour supprimer une session d'événements étendus dans l' **Explorateur d'objets**:</span><span class="sxs-lookup"><span data-stu-id="65683-168">To delete an Extended Events session in **Object Explorer**:</span></span>  
  
1.  <span data-ttu-id="65683-169">Développez les nœuds **Gestion**, **Événements étendus**, puis **Sessions** .</span><span class="sxs-lookup"><span data-stu-id="65683-169">Expand the **Management**, **Extended Events**, and then **Sessions** nodes.</span></span>  
  
2.  <span data-ttu-id="65683-170">Cliquez avec le bouton droit sur une session et sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="65683-170">Right-click a session and select **Delete**.</span></span>  
  
3.  <span data-ttu-id="65683-171">Dans la boîte de dialogue **Supprimer l'objet** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="65683-171">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
4.  <span data-ttu-id="65683-172">Après avoir modifié la session d'événements, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="65683-172">After you finish revising the event session, click **OK**.</span></span>  
  
 <span data-ttu-id="65683-173">Pour supprimer une session d’événements étendus dans l’ **Éditeur de requête**, émettez les instructions suivantes en remplaçant *session_name* par le nom de la session d’événements étendus à supprimer :</span><span class="sxs-lookup"><span data-stu-id="65683-173">To delete an Extended Events session in the **Query Editor**, Issue the following statements, replacing *session_name* with the name of the Extended Events session that you want to delete:</span></span>  
  
```  
DROP EVENT SESSION [session_name]  
ON SERVER  
```  
  
  
