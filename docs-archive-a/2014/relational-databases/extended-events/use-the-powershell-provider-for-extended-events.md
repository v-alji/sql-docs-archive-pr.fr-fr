---
title: Utiliser le fournisseur PowerShell pour les événements étendus | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- PowerShell [SQL Server], xevent
- extended events [SQL Server], PowerShell
- PowerShell [SQL Server], extended events
ms.assetid: 0b10016f-a479-4444-a484-46cb4677cf64
author: rothja
ms.author: jroth
ms.openlocfilehash: a9efbd389545dcde8285a38b06f41580fb65de6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611075"
---
# <a name="use-the-powershell-provider-for-extended-events"></a><span data-ttu-id="263aa-102">Utiliser le fournisseur PowerShell pour les événements étendus</span><span class="sxs-lookup"><span data-stu-id="263aa-102">Use the PowerShell Provider for Extended Events</span></span>
  <span data-ttu-id="263aa-103">Vous pouvez gérer les Événements étendus de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'aide du fournisseur PowerShell [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="263aa-103">You can manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Extended Events by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell provider.</span></span> <span data-ttu-id="263aa-104">Le sous-dossier XEvent est disponible sous le lecteur SQLSERVER.</span><span class="sxs-lookup"><span data-stu-id="263aa-104">The XEvent subfolder is available under the SQLSERVER drive.</span></span> <span data-ttu-id="263aa-105">Vous pouvez accéder à ce dossier selon l'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="263aa-105">You can access the folder by using either of the following methods:</span></span>  
  
-   <span data-ttu-id="263aa-106">À l’invite de commandes, saisissez `sqlps`, puis appuyez sur ENTRÉE.</span><span class="sxs-lookup"><span data-stu-id="263aa-106">At a command prompt, type `sqlps`, and then press ENTER.</span></span> <span data-ttu-id="263aa-107">Tapez `cd xevent`, puis appuyez sur ENTRÉE.</span><span class="sxs-lookup"><span data-stu-id="263aa-107">Type `cd xevent`, and then press ENTER.</span></span> <span data-ttu-id="263aa-108">À partir de là, vous pouvez **cd** utiliser les `dir` applets de commande CD et Commands (ou **set-location** et **obten-ChildItem** ) pour accéder au nom du serveur et au nom de l’instance.</span><span class="sxs-lookup"><span data-stu-id="263aa-108">From there, you can use the **cd** and `dir` commands (or **Set-Location** and **Get-Childitem** cmdlets) to navigate to the server name and instance name.</span></span>  
  
-   <span data-ttu-id="263aa-109">Dans l’Explorateur d’objets, développez le nom de l’instance, développez **Gestion**, cliquez avec le bouton droit sur **Événements étendus**, puis cliquez sur **Démarrer PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="263aa-109">In Object Explorer, expand the instance name, expand **Management**, right-click **Extended Events**, and then click **Start PowerShell**.</span></span> <span data-ttu-id="263aa-110">Cela démarre PowerShell selon le chemin d'accès suivant :</span><span class="sxs-lookup"><span data-stu-id="263aa-110">This starts PowerShell in the following path:</span></span>  
  
     <span data-ttu-id="263aa-111">PS SqlServer : \ XEvent \\ *nom_serveur* \\ *nom_instance*></span><span class="sxs-lookup"><span data-stu-id="263aa-111">PS SQLSERVER:\XEvent\\*ServerName*\\*InstanceName*></span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="263aa-112">Vous pouvez démarrer PowerShell à partir de n'importe quel nœud sous **Événements étendus**.</span><span class="sxs-lookup"><span data-stu-id="263aa-112">You can start PowerShell from any node under **Extended Events**.</span></span> <span data-ttu-id="263aa-113">Par exemple, vous pouvez cliquer avec le bouton droit sur **Sessions**, puis cliquer sur **Démarrer PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="263aa-113">For example, you can right-click **Sessions**, and then click **Start PowerShell**.</span></span> <span data-ttu-id="263aa-114">Cela démarre PowerShell à un niveau plus profond, au niveau du dossier Sessions.</span><span class="sxs-lookup"><span data-stu-id="263aa-114">This starts PowerShell one level deeper, at the Sessions folder.</span></span>  
  
 <span data-ttu-id="263aa-115">Vous pouvez parcourir l'arborescence des dossiers XEvent pour consulter les sessions Événements étendus existantes, ainsi que leurs événements, cibles et prédicats associés.</span><span class="sxs-lookup"><span data-stu-id="263aa-115">You can browse the XEvent folder tree to view existing Extended Events sessions and their associated events, targets and predicates.</span></span> <span data-ttu-id="263aa-116">Par exemple, à partir du chemin d’accès PS SqlServer : \ XEvent \\ *ServerName* \\ *nom_instance*>, si vous tapez `cd sessions` , appuyez sur entrée, tapez `dir` , puis appuyez sur entrée, vous pouvez voir la liste des sessions stockées sur cette instance.</span><span class="sxs-lookup"><span data-stu-id="263aa-116">For example, from the PS SQLSERVER:\XEvent\\*ServerName*\\*InstanceName*> path, if you type `cd sessions`, press ENTER, type `dir`, and then press ENTER, you can see the list of sessions that are stored on that instance.</span></span> <span data-ttu-id="263aa-117">Vous pouvez également voir si la session est en cours (et si c'est le cas, pour combien de temps), et savoir si elle est configurée pour démarrer en même temps que l'instance.</span><span class="sxs-lookup"><span data-stu-id="263aa-117">You can also view whether the session is running (and if this is the case, for how long), and whether the session is configured to start when the instance starts.</span></span>  
  
 <span data-ttu-id="263aa-118">Pour consulter les événements, leurs prédicats et les cibles associés à une session, vous pouvez attribuer le nom de la session aux répertoires, puis voir le dossier des événements ou des cibles.</span><span class="sxs-lookup"><span data-stu-id="263aa-118">To view the events, their predictates, and the targets that are associated with a session, you can change directories to the session name, and then view either the events or targets folder.</span></span> <span data-ttu-id="263aa-119">Par exemple, pour afficher les événements et leurs prédicats associés à la session d’intégrité système par défaut, à partir du chemin d’accès PS SqlServer : \ XEvent \\ *ServerName* \\ *nom_instance*\Sessions>, tapez `cd system_health\events,` Appuyez sur entrée, tapez `dir` , puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="263aa-119">For example, to view the events and their predicates that are associated with the default system health session, from the PS SQLSERVER:\XEvent\\*ServerName*\\*InstanceName*\Sessions> path, type `cd system_health\events,` press ENTER, type `dir`, and then press ENTER.</span></span>  
  
 <span data-ttu-id="263aa-120">Le fournisseur PowerShell [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est un outil puissant que vous pouvez utiliser pour créer, modifier et gérer des sessions Événements étendus.</span><span class="sxs-lookup"><span data-stu-id="263aa-120">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell provider is a powerful tool that you can use to create, alter, and manage Extended Events sessions.</span></span> <span data-ttu-id="263aa-121">La section suivante fournit quelques exemples simples d'utilisation de scripts PowerShell avec des Événements étendus.</span><span class="sxs-lookup"><span data-stu-id="263aa-121">The following section provides some basic examples of using PowerShell scripts with Extended Events.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="263aa-122">Exemples</span><span class="sxs-lookup"><span data-stu-id="263aa-122">Examples</span></span>  
 <span data-ttu-id="263aa-123">Dans les exemples ci-après, notez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="263aa-123">In the following examples, note the following:</span></span>  
  
-   <span data-ttu-id="263aa-124">Les scripts doivent être exécutés à partir de l’invite PS SQLSERVER : \\> (disponible en tapant `sqlps` à l’invite de commandes).</span><span class="sxs-lookup"><span data-stu-id="263aa-124">The scripts must be run from the PS SQLSERVER:\\> prompt (available by typing `sqlps` at a command prompt).</span></span>  
  
-   <span data-ttu-id="263aa-125">Les scripts utilisent l'instance par défaut de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="263aa-125">The scripts use the default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="263aa-126">Les scripts doivent être enregistrés avec une extension .ps1.</span><span class="sxs-lookup"><span data-stu-id="263aa-126">The scripts must be saved with a .ps1 extension.</span></span>  
  
-   <span data-ttu-id="263aa-127">La stratégie d'exécution de PowerShell doit autoriser l'exécution du script.</span><span class="sxs-lookup"><span data-stu-id="263aa-127">The PowerShell execution policy must allow the script to run.</span></span> <span data-ttu-id="263aa-128">Pour définir la stratégie d’exécution, utilisez l’applet de commande **Set-Executionpolicy** .</span><span class="sxs-lookup"><span data-stu-id="263aa-128">To set the execution policy, use the **Set-Executionpolicy** cmdlet.</span></span> <span data-ttu-id="263aa-129">(Pour en savoir plus, saisissez `get-help set-executionpolicy -detailed` et appuyez sur ENTRÉE.)</span><span class="sxs-lookup"><span data-stu-id="263aa-129">(For more information, type `get-help set-executionpolicy -detailed`, and then press ENTER.)</span></span>  
  
 <span data-ttu-id="263aa-130">Le script suivant crée une nouvelle session nommée « TestSession ».</span><span class="sxs-lookup"><span data-stu-id="263aa-130">The following script creates a new session that is named 'TestSession'.</span></span>  
  
```powershell
#Script for creating a session.  
cd XEvent  
$h = hostname  
cd $h  
  
#Use the default instance.  
$store = dir | where {$_.DisplayName -ieq 'default'}  
$session = New-Object Microsoft.SqlServer.Management.XEvent.Session -ArgumentList $store, "TestSession"  
$event = $session.AddEvent("sqlserver.file_written")  
$event.AddAction("package0.callstack")  
$session.Create()  
```  
  
 <span data-ttu-id="263aa-131">Le script suivant ajoute la cible de mémoire tampon en anneau à la session créée dans l'exemple précédent.</span><span class="sxs-lookup"><span data-stu-id="263aa-131">The following script adds the ring buffer target to the session that was created in the previous example.</span></span> <span data-ttu-id="263aa-132">(Cet exemple montre comment utiliser la méthode `Alter`.</span><span class="sxs-lookup"><span data-stu-id="263aa-132">(This example shows the use of the `Alter` method.</span></span> <span data-ttu-id="263aa-133">Sachez que vous pouvez ajouter la cible au moment même où vous créez la session).</span><span class="sxs-lookup"><span data-stu-id="263aa-133">Be aware that you can add the target when you first create the session.)</span></span>  
  
```powershell
#Script to alter a session.  
cd XEvent  
$h = hostname  
cd $h  
cd DEFAULT\Sessions  
  
#Used to find the specified session.  
$session = dir | where {$_.Name -eq 'TestSession'}  
  
#Add the ring buffer target and call the Alter method.  
$session.AddTarget("package0.ring_buffer")  
$session.Alter()  
```  
  
 <span data-ttu-id="263aa-134">Le script suivant crée une nouvelle session qui utilise une expression de prédicat.</span><span class="sxs-lookup"><span data-stu-id="263aa-134">The following script creates a new session that uses a predicate expression.</span></span> <span data-ttu-id="263aa-135">Dans ce cas, la session recueille les informations portant sur le moment où a été créé le fichier c:\temp.log (par le biais de l’événement sqlserver.file_written).</span><span class="sxs-lookup"><span data-stu-id="263aa-135">In this case, the session collects information for when the c:\temp.log file is written to (through the sqlserver.file_written event).</span></span>  
  
```powershell
#Script for creating a session.  
cd XEvent  
$h = hostname  
cd $h  
  
#Use the default instance.  
$store = dir | where {$_.DisplayName -ieq 'default'}  
$session = New-Object Microsoft.SqlServer.Management.XEvent.Session -ArgumentList $store, "TestSession2"  
$event = $session.AddEvent("sqlserver.file_written")  
  
#Construct a predicate "equal_i_unicode_string(path, N'c:\temp.log')".  
$column = $store.SqlServerPackage.EventInfoSet["file_written"].DataEventColumnInfoSet["path"]  
$operand = new-object Microsoft.SqlServer.Management.XEvent.PredOperand -argumentlist $column  
$value = new-object Microsoft.SqlServer.Management.XEvent.PredValue -argumentlist "c:\temp.log"  
$compare = $store.Package0Package.PredCompareInfoSet["equal_i_unicode_string"]  
$predicate = new-object Microsoft.SqlServer.Management.XEvent.PredFunctionExpr -ArgumentList $compare, $operand, $value  
$event.SetPredicate($predicate)  
$session.Create()  
```  
  
## <a name="security"></a><span data-ttu-id="263aa-136">Sécurité</span><span class="sxs-lookup"><span data-stu-id="263aa-136">Security</span></span>  
 <span data-ttu-id="263aa-137">Pour créer, modifier ou supprimer une session Événements étendus, vous devez disposer de l'autorisation ALTER ANY EVENT SESSION.</span><span class="sxs-lookup"><span data-stu-id="263aa-137">To create, alter, or drop an Extended Events session, you must have the ALTER ANY EVENT SESSION permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="263aa-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="263aa-138">See Also</span></span>  
 <span data-ttu-id="263aa-139">[SQL Server PowerShell](../../powershell/sql-server-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="263aa-139">[SQL Server PowerShell](../../powershell/sql-server-powershell.md) </span></span>  
 <span data-ttu-id="263aa-140">[Utiliser la session system_health](use-the-ssms-xe-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="263aa-140">[Use the system_health Session](use-the-ssms-xe-profiler.md) </span></span>  
 [<span data-ttu-id="263aa-141">Outils associés aux événements étendus</span><span class="sxs-lookup"><span data-stu-id="263aa-141">Extended Events Tools</span></span>](extended-events-tools.md)  
