---
title: Utilitaire Ssms | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], opening
- command prompt utilities [SQL Server], sqlwb
- sqlwb utility
- Management Studio command line
- opening SQL Server Management Studio
ms.assetid: aafda520-9e2a-4e1e-b936-1b165f1684e8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0cfc9469e49e6ce3839d02a61477b8957fbc13e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613767"
---
# <a name="ssms-utility"></a><span data-ttu-id="aac3f-102">Utilitaire Ssms</span><span class="sxs-lookup"><span data-stu-id="aac3f-102">Ssms Utility</span></span>
  <span data-ttu-id="aac3f-103">L’utilitaire **Ssms**ouvre [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aac3f-103">The **Ssms**utility opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="aac3f-104">Si cela est spécifié, **Ssms** établit également une connexion à un serveur et ouvre des requêtes, des scripts, des fichiers, des projets et des solutions.</span><span class="sxs-lookup"><span data-stu-id="aac3f-104">If specified, **Ssms** also establishes a connection to a server, and opens queries, scripts, files, projects, and solutions.</span></span>  
  
 <span data-ttu-id="aac3f-105">Vous pouvez spécifier des fichiers contenant des requêtes, des projets ou des solutions.</span><span class="sxs-lookup"><span data-stu-id="aac3f-105">You can specify files that contain queries, projects, or solutions.</span></span> <span data-ttu-id="aac3f-106">Les fichiers qui contiennent des requêtes sont automatiquement connectés à un serveur si des informations de connexion sont fournies et si le type de fichier est associé à ce type de serveur.</span><span class="sxs-lookup"><span data-stu-id="aac3f-106">Files that contain queries are automatically connected to a server if connection information is provided and the file type is associated with that type of server.</span></span> <span data-ttu-id="aac3f-107">Par exemple, les fichiers .sql ouvrent une fenêtre Éditeur de requête SQL dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], tandis que des fichiers .mdx ouvrent une fenêtre Éditeur de requête MDX dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aac3f-107">For instance, .sql files will open a SQL Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], and .mdx files will open an MDX Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="aac3f-108">Les**solutions et projets SQL Server** s’ouvrent dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aac3f-108">**SQL Server Solutions and Projects** will open in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aac3f-109">L’utilitaire **Ssms** n’exécute pas de requêtes.</span><span class="sxs-lookup"><span data-stu-id="aac3f-109">The **Ssms** utility does not run queries.</span></span> <span data-ttu-id="aac3f-110">Pour exécuter des requêtes depuis la ligne de commande, employez l’utilitaire **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="aac3f-110">To run queries from the command line, use the **sqlcmd** utility.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aac3f-111">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="aac3f-111">Syntax</span></span>  
  
```  
  
      Ssms  
    [scriptfile] [projectfile] [solutionfile]  
    [-Sservername] [-ddatabasename] [-Uusername] [-Ppassword]   
    [-E] [-nosplash] [-log[filename]?] [-?]  
```  
  
## <a name="arguments"></a><span data-ttu-id="aac3f-112">Arguments</span><span class="sxs-lookup"><span data-stu-id="aac3f-112">Arguments</span></span>  
 <span data-ttu-id="aac3f-113">*scriptfile*</span><span class="sxs-lookup"><span data-stu-id="aac3f-113">*scriptfile*</span></span>  
 <span data-ttu-id="aac3f-114">Spécifie un ou plusieurs fichiers de script à ouvrir.</span><span class="sxs-lookup"><span data-stu-id="aac3f-114">Specifies one or more script files to open.</span></span> <span data-ttu-id="aac3f-115">Le paramètre doit contenir le chemin complet d'accès aux fichiers.</span><span class="sxs-lookup"><span data-stu-id="aac3f-115">The parameter must contain the full path to the files.</span></span>  
  
 <span data-ttu-id="aac3f-116">*projectfile*</span><span class="sxs-lookup"><span data-stu-id="aac3f-116">*projectfile*</span></span>  
 <span data-ttu-id="aac3f-117">Spécifie un projet de script à ouvrir.</span><span class="sxs-lookup"><span data-stu-id="aac3f-117">Specifies a script project to open.</span></span> <span data-ttu-id="aac3f-118">Le paramètre doit contenir le chemin d'accès complet au fichier de projet de script.</span><span class="sxs-lookup"><span data-stu-id="aac3f-118">The parameter must contain the full path to the script project file.</span></span>  
  
 <span data-ttu-id="aac3f-119">*solutionfile*</span><span class="sxs-lookup"><span data-stu-id="aac3f-119">*solutionfile*</span></span>  
 <span data-ttu-id="aac3f-120">Spécifie une solution à ouvrir.</span><span class="sxs-lookup"><span data-stu-id="aac3f-120">Specifies a solution to open.</span></span> <span data-ttu-id="aac3f-121">Le paramètre doit contenir le chemin d'accès complet au fichier de solution.</span><span class="sxs-lookup"><span data-stu-id="aac3f-121">The parameter must contain the full path to the solution file.</span></span>  
  
 <span data-ttu-id="aac3f-122">[**-S** _nom_serveur_]</span><span class="sxs-lookup"><span data-stu-id="aac3f-122">[**-S** _servername_]</span></span>  
 <span data-ttu-id="aac3f-123">Nom du serveur</span><span class="sxs-lookup"><span data-stu-id="aac3f-123">Server name</span></span>  
  
 <span data-ttu-id="aac3f-124">[**-d** _DatabaseName_]</span><span class="sxs-lookup"><span data-stu-id="aac3f-124">[**-d** _databasename_]</span></span>  
 <span data-ttu-id="aac3f-125">Nom de la base de données</span><span class="sxs-lookup"><span data-stu-id="aac3f-125">Database name</span></span>  
  
 <span data-ttu-id="aac3f-126">[**-U** _nom_d_utilisateur_]</span><span class="sxs-lookup"><span data-stu-id="aac3f-126">[**-U** _username_]</span></span>  
 <span data-ttu-id="aac3f-127">Nom d'utilisateur lors d'une connexion avec l'authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aac3f-127">User name when connecting with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication</span></span>  
  
 <span data-ttu-id="aac3f-128">[**-P** _mot de passe_]</span><span class="sxs-lookup"><span data-stu-id="aac3f-128">[**-P** _password_]</span></span>  
 <span data-ttu-id="aac3f-129">Mot de passe lors d'une connexion avec l'authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aac3f-129">Password when connecting with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication</span></span>  
  
 <span data-ttu-id="aac3f-130">[**-E**]</span><span class="sxs-lookup"><span data-stu-id="aac3f-130">[**-E**]</span></span>  
 <span data-ttu-id="aac3f-131">Connexion avec l'authentification Windows</span><span class="sxs-lookup"><span data-stu-id="aac3f-131">Connect using Windows Authentication</span></span>  
  
 <span data-ttu-id="aac3f-132">[**-nosplash**]</span><span class="sxs-lookup"><span data-stu-id="aac3f-132">[**-nosplash**]</span></span>  
 <span data-ttu-id="aac3f-133">Empêche [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] d'afficher le graphique de l'écran de démarrage lors de l'ouverture.</span><span class="sxs-lookup"><span data-stu-id="aac3f-133">Prevents [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from displaying the splash screen graphic while opening.</span></span> <span data-ttu-id="aac3f-134">Utilisez cette option lors d'une connexion à l'ordinateur exécutant [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] au moyen des services Terminal Server sur une connexion dotée d'une bande passante limitée.</span><span class="sxs-lookup"><span data-stu-id="aac3f-134">Use this option when connecting to the computer running [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] by means of Terminal Services over a connection with a limited bandwidth.</span></span> <span data-ttu-id="aac3f-135">Cet argument ne respecte pas la casse et peut apparaître avant ou après d'autres arguments</span><span class="sxs-lookup"><span data-stu-id="aac3f-135">This argument is not case-sensitive and may appear before or after other arguments</span></span>  
  
 <span data-ttu-id="aac3f-136">[**-log**_[nom de fichier] ?_]</span><span class="sxs-lookup"><span data-stu-id="aac3f-136">[**-log**_[filename]?_]</span></span>  
 <span data-ttu-id="aac3f-137">Consigne l'activité de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] dans le fichier spécifié à des fins de dépannage</span><span class="sxs-lookup"><span data-stu-id="aac3f-137">Logs [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] activity to the specified file for troubleshooting</span></span>  
  
 <span data-ttu-id="aac3f-138">[**-?**]</span><span class="sxs-lookup"><span data-stu-id="aac3f-138">[**-?**]</span></span>  
 <span data-ttu-id="aac3f-139">Affiche l'aide de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="aac3f-139">Displays command line help</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aac3f-140">Notes</span><span class="sxs-lookup"><span data-stu-id="aac3f-140">Remarks</span></span>  
 <span data-ttu-id="aac3f-141">Tous les commutateurs sont facultatifs et séparés par un espace à l'exception des fichiers qui sont séparés par des virgules.</span><span class="sxs-lookup"><span data-stu-id="aac3f-141">All of the switches are optional and separated by a space except files which are separated by commas.</span></span> <span data-ttu-id="aac3f-142">Si vous ne spécifiez pas de commutateur, **Ssms** ouvre [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] tel que spécifié dans les paramètres **Options** du menu **Outils** .</span><span class="sxs-lookup"><span data-stu-id="aac3f-142">If you do not specify any switches, **Ssms** opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] as specified in the **Options** settings on the **Tools** menu.</span></span> <span data-ttu-id="aac3f-143">Par exemple, si l’option **Au démarrage** de la page **Environnement/Général** spécifie **Ouvrir la fenêtre de nouvelle requête**, **Ssms** s’ouvre avec un éditeur de requête vide.</span><span class="sxs-lookup"><span data-stu-id="aac3f-143">For example, if the **Environment/General** page **At startup** option specifies **Open new query window**, **Ssms** will open with a blank Query Editor.</span></span>  
  
 <span data-ttu-id="aac3f-144">Le commutateur **-log** doit apparaître à la fin de la ligne de commande, après tous les autres commutateurs.</span><span class="sxs-lookup"><span data-stu-id="aac3f-144">The **-log** switch must appear at the end of the command line, after all other switches.</span></span> <span data-ttu-id="aac3f-145">L'argument de nom de fichier (filename) est facultatif.</span><span class="sxs-lookup"><span data-stu-id="aac3f-145">The filename argument is optional.</span></span> <span data-ttu-id="aac3f-146">Si un nom de fichier est spécifié et que le fichier n'existe pas, il est créé.</span><span class="sxs-lookup"><span data-stu-id="aac3f-146">If a filename is specified, and the file does not exist, the file is created.</span></span> <span data-ttu-id="aac3f-147">Si le fichier ne peut pas être créé (par exemple, en raison d’un accès en écriture insuffisant), le journal est écrit à la place à l’emplacement APPDATA non localisé (voir ci-dessous).</span><span class="sxs-lookup"><span data-stu-id="aac3f-147">If the file cannot be created - for example, due to insufficient write access, the log is written to the nonlocalized APPDATA location instead (See below).</span></span> <span data-ttu-id="aac3f-148">Si l'argument du nom de fichier (filename) n'est pas spécifié, deux fichiers sont écrits dans le dossier des données d'application non localisé de l'utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="aac3f-148">If the filename argument is not specified, two files are written to the current user's nonlocalized application data folder.</span></span> <span data-ttu-id="aac3f-149">Le dossier de données d'application non localisé de SQL Server peut se trouver dans la variable d'environnement APPDATA.</span><span class="sxs-lookup"><span data-stu-id="aac3f-149">The nonlocalized application data folder for SQL Server can be found from the APPDATA environment variable.</span></span> <span data-ttu-id="aac3f-150">Par exemple, pour SQL Server 2012, le dossier est \<system drive> : \utilisateurs \\<nom d’utilisateur \> \AppData\Roaming\Microsoft\AppEnv\10.0 \\ .</span><span class="sxs-lookup"><span data-stu-id="aac3f-150">For example, for SQL Server 2012, the folder is \<system drive>:\Users\\<username\>\AppData\Roaming\Microsoft\AppEnv\10.0\\.</span></span> <span data-ttu-id="aac3f-151">Les deux fichiers sont nommés, par défaut, ActivityLog.xml et ActivityLog.xsl.</span><span class="sxs-lookup"><span data-stu-id="aac3f-151">The two files are, by default, named ActivityLog.xml and ActivityLog.xsl.</span></span> <span data-ttu-id="aac3f-152">Le premier contient les données du journal des activités et le deuxième est une feuille de style XML qui offre un moyen plus pratique d'afficher le fichier XML.</span><span class="sxs-lookup"><span data-stu-id="aac3f-152">The former contains the activity log data and the latter is an XML style sheet which provides a more convenient way to view the XML file.</span></span> <span data-ttu-id="aac3f-153">Suivez les étapes ci-dessous pour afficher le fichier journal dans votre visionneuse XML par défaut, comme Internet Explorer : cliquez sur Démarrer, puis sur Exécuter...», tapez « \<system drive> : \utilisateurs \\<nom d’utilisateur \>\AppData\Roaming\Microsoft\AppEnv\10.0\ActivityLog.xml » dans le champ fourni, puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="aac3f-153">Use the following steps to view the log file in your default XML viewer, like Internet Explorer:  Click Start, then click Run...", then type "\<system drive>:\Users\\<username\>\AppData\Roaming\Microsoft\AppEnv\10.0\ActivityLog.xml" into the field provided, and then press Enter.</span></span>  
  
 <span data-ttu-id="aac3f-154">Les fichiers qui contiennent des requêtes demandent une confirmation pour la connexion à un serveur si des informations de connexion sont fournies et si le type de fichier est associé à ce type de serveur.</span><span class="sxs-lookup"><span data-stu-id="aac3f-154">Files that contain queries will prompt to be connected to a server if connection information is provided and the file type is associated with that type of server.</span></span> <span data-ttu-id="aac3f-155">Par exemple, les fichiers .sql ouvrent une fenêtre Éditeur de requête SQL dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], tandis que des fichiers .mdx ouvrent une fenêtre Éditeur de requête MDX dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aac3f-155">For instance, .sql files will open a SQL Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], and .mdx files will open an MDX Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="aac3f-156">Les**solutions et projets SQL Server** s’ouvrent dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aac3f-156">**SQL Server Solutions and Projects** will open in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="aac3f-157">Le tableau suivant mappe des types de serveur à des extensions de fichier.</span><span class="sxs-lookup"><span data-stu-id="aac3f-157">The following table maps server types to file extensions.</span></span>  
  
|<span data-ttu-id="aac3f-158">Type de serveur</span><span class="sxs-lookup"><span data-stu-id="aac3f-158">Server type</span></span>|<span data-ttu-id="aac3f-159">Extension</span><span class="sxs-lookup"><span data-stu-id="aac3f-159">Extension</span></span>|  
|-----------------|---------------|  
|[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]|<span data-ttu-id="aac3f-160">.sql</span><span class="sxs-lookup"><span data-stu-id="aac3f-160">.sql</span></span>|  
|<span data-ttu-id="aac3f-161">SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="aac3f-161">SQL Server Analysis Services</span></span>|<span data-ttu-id="aac3f-162">.mdx</span><span class="sxs-lookup"><span data-stu-id="aac3f-162">.mdx</span></span><br /><br /> <span data-ttu-id="aac3f-163">.xmla</span><span class="sxs-lookup"><span data-stu-id="aac3f-163">.xmla</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="aac3f-164">Exemples</span><span class="sxs-lookup"><span data-stu-id="aac3f-164">Examples</span></span>  
 <span data-ttu-id="aac3f-165">Le script suivant ouvre [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] à partir d'une invite de commandes avec les paramètres par défaut :</span><span class="sxs-lookup"><span data-stu-id="aac3f-165">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt with the default settings:</span></span>  
  
```  
Ssms  
  
```  
  
 <span data-ttu-id="aac3f-166">Le script suivant ouvre [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] à partir d'une invite de commandes, avec l'authentification Windows, avec l'Éditeur de code réglé sur le serveur `ACCTG and the database AdventureWorks2012,` , sans affichage de l'écran de démarrage :</span><span class="sxs-lookup"><span data-stu-id="aac3f-166">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt, with Windows Authentication, with the Code Editor set to the server `ACCTG and the database AdventureWorks2012,` without showing the splash screen:</span></span>  
  
```  
Ssms -E -S ACCTG -d AdventureWorks2012 -nosplash  
  
```  
  
 <span data-ttu-id="aac3f-167">Le script suivant ouvre [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] à partir d'une invite de commandes et ouvre le script MonthEndQuery.</span><span class="sxs-lookup"><span data-stu-id="aac3f-167">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt, and opens the MonthEndQuery script.</span></span>  
  
```  
Ssms "C:\Documents and Settings\username\My Documents\SQL Server Management Studio Projects\FinanceScripts\FinanceScripts\MonthEndQuery.sql"  
  
```  
  
 <span data-ttu-id="aac3f-168">Le script suivant ouvre [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] à partir d'une invite de commandes et ouvre le projet NewReportsProject sur l'ordinateur nommé `developer`:</span><span class="sxs-lookup"><span data-stu-id="aac3f-168">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt, and opens the NewReportsProject project on the computer named `developer`:</span></span>  
  
```  
Ssms "\\developer\fin\ReportProj\ReportProj\NewReportProj.ssmssqlproj"  
  
```  
  
 <span data-ttu-id="aac3f-169">Le script suivant ouvre [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] à partir d'une invite de commandes et ouvre la solution MonthlyReports.</span><span class="sxs-lookup"><span data-stu-id="aac3f-169">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt, and opens the MonthlyReports solution:</span></span>  
  
```  
Ssms "C:\solutionsfolder\ReportProj\MonthlyReports.ssmssln"  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="aac3f-170">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="aac3f-170">See Also</span></span>  
 [<span data-ttu-id="aac3f-171">Utiliser SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="aac3f-171">Use SQL Server Management Studio</span></span>](../database-engine/use-sql-server-management-studio.md)  
  
  
