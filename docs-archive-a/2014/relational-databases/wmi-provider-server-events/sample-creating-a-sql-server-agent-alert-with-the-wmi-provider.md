---
title: 'Exemple : création d’une alerte SQL Server Agent à l’aide du fournisseur WMI pour les événements de serveur | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- SQL Server Agent [WMI]
- WMI Provider for Server Events, samples
- sample applications [WMI]
ms.assetid: d44811c7-cd46-4017-b284-c863ca088e8f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f23a3a8738435dc6a27a230f4521300a3ee2470f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702515"
---
# <a name="sample-creating-a-sql-server-agent-alert-by-using-the-wmi-provider-for-server-events"></a><span data-ttu-id="166c4-102">Exemple : Création d’une alerte de SQL Server Agent en utilisant le fournisseur WMI pour les événements de serveur</span><span class="sxs-lookup"><span data-stu-id="166c4-102">Sample: Creating a SQL Server Agent Alert by Using the WMI Provider for Server Events</span></span>
  <span data-ttu-id="166c4-103">Une façon courante d'utiliser le fournisseur d'événements WMI consiste à créer des alertes de l'Agent SQL Server qui répondent à des événements spécifiques.</span><span class="sxs-lookup"><span data-stu-id="166c4-103">One common way to use the WMI Event Provider is to create SQL Server Agent alerts that respond to specific events.</span></span> <span data-ttu-id="166c4-104">L'exemple suivant présente une alerte simple qui enregistre les événements du graphique de blocage XML dans une table pour leur analyse ultérieure.</span><span class="sxs-lookup"><span data-stu-id="166c4-104">The following sample presents a simple alert that saves XML deadlock graph events in a table for later analysis.</span></span> <span data-ttu-id="166c4-105">L'Agent SQL Server soumet une demande WQL, reçoit des événements WMI et exécute un travail en réponse à l'événement.</span><span class="sxs-lookup"><span data-stu-id="166c4-105">SQL Server Agent submits a WQL request, receives WMI events, and runs a job in response to the event.</span></span> <span data-ttu-id="166c4-106">Remarquez que, bien que plusieurs objets Service Broker soient impliqués dans le traitement du message de notification, le fournisseur d'événements WMI gère les détails de la création et de la gestion de ces objets.</span><span class="sxs-lookup"><span data-stu-id="166c4-106">Notice that, although several Service Broker objects are involved in processing the notification message, the WMI Event Provider handles the details of creating and managing these objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="166c4-107">Exemple</span><span class="sxs-lookup"><span data-stu-id="166c4-107">Example</span></span>  
 <span data-ttu-id="166c4-108">En premier lieu, une table est créée dans la base de données `AdventureWorks` pour contenir l'événement du graphique du blocage.</span><span class="sxs-lookup"><span data-stu-id="166c4-108">First, a table is created in the `AdventureWorks` database to hold the deadlock graph event.</span></span> <span data-ttu-id="166c4-109">La table contient deux colonnes : la colonne `AlertTime` contient l'heure à laquelle l'alerte s'exécute et la colonne `DeadlockGraph` contient le document XML qui inclut le graphique du blocage.</span><span class="sxs-lookup"><span data-stu-id="166c4-109">The table contains two columns: The `AlertTime` column holds the time that the alert runs, and the `DeadlockGraph` column holds the XML document that contains the deadlock graph.</span></span>  
  
 <span data-ttu-id="166c4-110">Ensuite, l'alerte est créée.</span><span class="sxs-lookup"><span data-stu-id="166c4-110">Then, the alert is created.</span></span> <span data-ttu-id="166c4-111">Le script commence par créer le travail que l'alerte exécutera, ajoute une étape de travail au travail et cible le travail sur l'instance actuelle de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="166c4-111">The script first creates the job that the alert will run, adds a job step to the job, and targets the job to the current instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="166c4-112">Le script crée alors l'alerte.</span><span class="sxs-lookup"><span data-stu-id="166c4-112">The script then creates the alert.</span></span>  
  
 <span data-ttu-id="166c4-113">L’étape de travail récupère la propriété **TextData** de l’instance d’événement WMI et insère cette valeur dans la colonne **DeadlockGraph** de la table **DeadlockEvents** .</span><span class="sxs-lookup"><span data-stu-id="166c4-113">The job step retrieves the **TextData** property of the WMI event instance and inserts that value into the **DeadlockGraph** column of the **DeadlockEvents** table.</span></span> <span data-ttu-id="166c4-114">Remarquez que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] convertit implicitement la chaîne au format XML.</span><span class="sxs-lookup"><span data-stu-id="166c4-114">Notice that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] implicitly converts the string into XML format.</span></span> <span data-ttu-id="166c4-115">Comme l'étape de travail utilise le sous-système [!INCLUDE[tsql](../../includes/tsql-md.md)], l'étape de travail ne spécifie pas de proxy.</span><span class="sxs-lookup"><span data-stu-id="166c4-115">Because the job step uses the [!INCLUDE[tsql](../../includes/tsql-md.md)] subsystem, the job step does not specify a proxy.</span></span>  
  
 <span data-ttu-id="166c4-116">L'alerte exécute le travail chaque fois qu'un événement de trace du graphique du blocage est consigné.</span><span class="sxs-lookup"><span data-stu-id="166c4-116">The alert runs the job whenever a deadlock graph trace event would be logged.</span></span> <span data-ttu-id="166c4-117">Pour une alerte WMI, l'Agent SQL Server crée une requête de notification à l'aide de l'espace de noms et de l'instruction WQL spécifiés.</span><span class="sxs-lookup"><span data-stu-id="166c4-117">For a WMI alert, SQL Server Agent creates a notification query using the namespace and WQL statement specified.</span></span> <span data-ttu-id="166c4-118">Pour cette alerte, l'Agent SQL Server analyse l'instance par défaut sur l'ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="166c4-118">For this alert, SQL Server Agent monitors the default instance on the local computer.</span></span> <span data-ttu-id="166c4-119">L'instruction WQL demande un événement `DEADLOCK_GRAPH` quelconque dans l'instance par défaut.</span><span class="sxs-lookup"><span data-stu-id="166c4-119">The WQL statement requests any `DEADLOCK_GRAPH` event in the default instance.</span></span> <span data-ttu-id="166c4-120">Pour modifier l'instance que l'alerte surveille, substituez le nom de l'instance pour `MSSQLSERVER` dans le `@wmi_namespace` pour l'alerte.</span><span class="sxs-lookup"><span data-stu-id="166c4-120">To change the instance that the alert monitors, substitute the instance name for `MSSQLSERVER` in the `@wmi_namespace` for the alert.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="166c4-121">Pour SQL Server Agent recevoir des événements WMI, [!INCLUDE[ssSB](../../includes/sssb-md.md)] doit être activé dans **msdb** et [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="166c4-121">For SQL Server Agent to receive WMI events, [!INCLUDE[ssSB](../../includes/sssb-md.md)] must be enabled in **msdb** and [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
```  
USE AdventureWorks ;  
GO  
  
IF OBJECT_ID('DeadlockEvents', 'U') IS NOT NULL  
BEGIN  
    DROP TABLE DeadlockEvents ;  
END ;  
GO  
  
CREATE TABLE DeadlockEvents  
    (AlertTime DATETIME, DeadlockGraph XML) ;  
GO  
-- Add a job for the alert to run.  
  
EXEC  msdb.dbo.sp_add_job @job_name=N'Capture Deadlock Graph',   
    @enabled=1,   
    @description=N'Job for responding to DEADLOCK_GRAPH events' ;  
GO  
  
-- Add a jobstep that inserts the current time and the deadlock graph into  
-- the DeadlockEvents table.  
  
EXEC msdb.dbo.sp_add_jobstep  
    @job_name = N'Capture Deadlock Graph',  
    @step_name=N'Insert graph into LogEvents',  
    @step_id=1,   
    @on_success_action=1,   
    @on_fail_action=2,   
    @subsystem=N'TSQL',   
    @command= N'INSERT INTO DeadlockEvents  
                (AlertTime, DeadlockGraph)  
                VALUES (getdate(), N''$(ESCAPE_SQUOTE(WMI(TextData)))'')',  
    @database_name=N'AdventureWorks' ;  
GO  
  
-- Set the job server for the job to the current instance of SQL Server.  
  
EXEC msdb.dbo.sp_add_jobserver @job_name = N'Capture Deadlock Graph' ;  
GO  
  
-- Add an alert that responds to all DEADLOCK_GRAPH events for  
-- the default instance. To monitor deadlocks for a different instance,  
-- change MSSQLSERVER to the name of the instance.  
  
EXEC msdb.dbo.sp_add_alert @name=N'Respond to DEADLOCK_GRAPH',   
@wmi_namespace=N'\\.\root\Microsoft\SqlServer\ServerEvents\MSSQLSERVER',   
    @wmi_query=N'SELECT * FROM DEADLOCK_GRAPH',   
    @job_name='Capture Deadlock Graph' ;  
GO  
```  
  
## <a name="testing-the-sample"></a><span data-ttu-id="166c4-122">Test de l'exemple</span><span class="sxs-lookup"><span data-stu-id="166c4-122">Testing the Sample</span></span>  
 <span data-ttu-id="166c4-123">Pour voir le travail s'exécuter, provoquez un blocage.</span><span class="sxs-lookup"><span data-stu-id="166c4-123">To see the job run, provoke a deadlock.</span></span> <span data-ttu-id="166c4-124">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , ouvrez deux onglets de **requête SQL** et connectez les deux requêtes à la même instance.</span><span class="sxs-lookup"><span data-stu-id="166c4-124">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open two **SQL Query** tabs and connect both queries to the same instance.</span></span> <span data-ttu-id="166c4-125">Exécutez le script ci-dessous sous l'un des onglets de requête.</span><span class="sxs-lookup"><span data-stu-id="166c4-125">Run the following script in one of the query tabs.</span></span> <span data-ttu-id="166c4-126">Ce script produit un jeu de résultats et se termine.</span><span class="sxs-lookup"><span data-stu-id="166c4-126">This script produces one result set and finishes.</span></span>  
  
```  
USE AdventureWorks ;  
GO  
  
BEGIN TRANSACTION ;  
GO  
  
SELECT TOP(1) Name FROM Production.Product WITH (XLOCK) ;  
GO  
```  
  
 <span data-ttu-id="166c4-127">Exécutez le script suivant dans le deuxième onglet de requête. Ce script produit un jeu de résultats, puis se bloque, en attendant d’acquérir un verrou sur `Production.Product` .</span><span class="sxs-lookup"><span data-stu-id="166c4-127">Run the following script in the second query tab. This script produces one result set and then blocks, waiting to acquire a lock on `Production.Product`.</span></span>  
  
```  
USE AdventureWorks ;  
GO  
  
BEGIN TRANSACTION ;  
GO  
  
SELECT TOP(1) Name FROM Production.Location WITH (XLOCK) ;  
GO  
  
SELECT TOP(1) Name FROM Production.Product WITH (XLOCK) ;  
GO  
```  
  
 <span data-ttu-id="166c4-128">Exécutez le script suivant dans le premier onglet de requête. Ce script bloque, en attendant d’acquérir un verrou sur `Production.Location` .</span><span class="sxs-lookup"><span data-stu-id="166c4-128">Run the following script in the first query tab. This script blocks, waiting to acquire a lock on `Production.Location`.</span></span> <span data-ttu-id="166c4-129">Après un court délai d'attente, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] choisira soit ce script, soit le script dans l'exemple comme victime du blocage et mettra un terme à la transaction.</span><span class="sxs-lookup"><span data-stu-id="166c4-129">After a short time-out, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will choose either this script or the script in the sample as the deadlock victim and end the transaction.</span></span>  
  
```  
SELECT TOP(1) Name FROM Production.Location WITH (XLOCK) ;  
GO  
```  
  
 <span data-ttu-id="166c4-130">Après avoir provoqué le blocage, attendez un certain temps que l'Agent SQL Server active l'alerte et exécute le travail.</span><span class="sxs-lookup"><span data-stu-id="166c4-130">After provoking the deadlock, wait several moments for SQL Server Agent to activate the alert and run the job.</span></span> <span data-ttu-id="166c4-131">Examinez le contenu de la table `DeadlockEvents` en exécutant le script suivant :</span><span class="sxs-lookup"><span data-stu-id="166c4-131">Examine the contents of the `DeadlockEvents` table by running the following script:</span></span>  
  
```  
SELECT * FROM DeadlockEvents ;  
GO  
```  
  
 <span data-ttu-id="166c4-132">La colonne `DeadlockGraph` doit contenir un document XML qui indique toutes les propriétés de l'événement du graphique du blocage.</span><span class="sxs-lookup"><span data-stu-id="166c4-132">The `DeadlockGraph` column should contain an XML document that shows all the properties of the deadlock graph event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="166c4-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="166c4-133">See Also</span></span>  
 [<span data-ttu-id="166c4-134">Fournisseur WMI pour les concepts des événements de serveur</span><span class="sxs-lookup"><span data-stu-id="166c4-134">WMI Provider for Server Events Concepts</span></span>](wmi-provider-for-server-events-concepts.md)  
  
  
