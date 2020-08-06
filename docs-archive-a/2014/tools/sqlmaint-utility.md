---
title: Utilitaire sqlmaint | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- database maintenance plans [SQL Server]
- sqlmaint utility
- maintaining databases [SQL Server]
- backups [SQL Server], sqlmaint utility
- command prompt utilities [SQL Server], sqlmaint
- maintenance plans [SQL Server], command prompt
- backing up [SQL Server], sqlmaint utility
ms.assetid: 937a9932-4aed-464b-b97a-a5acfe6a50de
author: stevestein
ms.author: sstein
ms.openlocfilehash: 80e60b75305ee91e8b62a201d9c86af301326789
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694895"
---
# <a name="sqlmaint-utility"></a><span data-ttu-id="15400-102">sqlmaint (utilitaire)</span><span class="sxs-lookup"><span data-stu-id="15400-102">sqlmaint Utility</span></span>
  <span data-ttu-id="15400-103">L’utilitaire**sqlmaint** exécute un ensemble spécifique d’opérations de maintenance sur une ou plusieurs bases de données.</span><span class="sxs-lookup"><span data-stu-id="15400-103">The**sqlmaint** utility performs a specified set of maintenance operations on one or more databases.</span></span> <span data-ttu-id="15400-104">Utilisez **sqlmaint** pour exécuter des vérifications DBCC, sauvegarder une base de données et son journal des transactions, mettre à jour des statistiques et reconstruire des index.</span><span class="sxs-lookup"><span data-stu-id="15400-104">Use **sqlmaint** to run DBCC checks, back up a database and its transaction log, update statistics, and rebuild indexes.</span></span> <span data-ttu-id="15400-105">Toutes les activités de maintenance de base de données produisent un rapport qui peut être envoyé vers un fichier texte, un fichier HTML ou un compte de messagerie déterminé.</span><span class="sxs-lookup"><span data-stu-id="15400-105">All database maintenance activities generate a report that can be sent to a designated text file, HTML file, or e-mail account.</span></span> <span data-ttu-id="15400-106">**sqlmaint** exécute les plans de maintenance de base de données créés avec des versions précédentes de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15400-106">**sqlmaint** executes database maintenance plans created with previous versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="15400-107">Pour exécuter des plans de maintenance [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] à partir de l’invite de commandes, utilisez [l’utilitaire dtexec](../integration-services/packages/dtexec-utility.md).</span><span class="sxs-lookup"><span data-stu-id="15400-107">To run [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] maintenance plans from the command prompt, use the [dtexec Utility](../integration-services/packages/dtexec-utility.md).</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextAvoid](../includes/ssnotedepnextavoid-md.md)] <span data-ttu-id="15400-108">Utilisez plutôt la fonction plan de maintenance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15400-108">Use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] maintenance plan feature instead.</span></span> <span data-ttu-id="15400-109">Pour plus d’informations sur les plans de maintenance, consultez [Plans de maintenance](../relational-databases/maintenance-plans/maintenance-plans.md).</span><span class="sxs-lookup"><span data-stu-id="15400-109">For more information on maintenance plans, see [Maintenance Plans](../relational-databases/maintenance-plans/maintenance-plans.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15400-110">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="15400-110">Syntax</span></span>  
  
```  
  
      sqlmaint   
[-?] |  
[  
     [-Sserver_name[\instance_name]]  
     [-Ulogin_ID [-Ppassword]]  
     {  
          [-Ddatabase_name | -PlanNamename | -PlanIDguid ]  
          [-Rpttext_file]  
          [-Tooperator_name]  
          [-HtmlRpthtml_file [-DelHtmlRpt <time_period>] ]  
          [-RmUnusedSpacethreshold_percentfree_percent]  
          [-CkDB | -CkDBNoIdx]  
          [-CkAl | -CkAlNoIdx]  
          [-CkCat]  
          [-UpdOptiStatssample_percent]  
          [-RebldIdxfree_space]  
          [-SupportComputedColumn]  
          [-WriteHistory]  
          [  
               {-BkUpDB [backup_path] | -BkUpLog [backup_path] }  
               {-BkUpMedia  
                    {DISK [  
                           [-DelBkUps<time_period>]   
                           [-CrBkSubDir ]   
                           [-UseDefDir ]   
                          ]  
                     | TAPE   
                    }  
               }  
               [-BkUpOnlyIfClean]  
               [-VrfyBackup]  
          ]  
     }  
]  
<time_period> ::=  
number[minutes | hours | days | weeks | months]  
```  
  
## <a name="arguments"></a><span data-ttu-id="15400-111">Arguments</span><span class="sxs-lookup"><span data-stu-id="15400-111">Arguments</span></span>  
 <span data-ttu-id="15400-112">Les paramètres et leurs valeurs doivent être séparés par un espace.</span><span class="sxs-lookup"><span data-stu-id="15400-112">The parameters and their values must be separated by a space.</span></span> <span data-ttu-id="15400-113">Par exemple, il doit exister un espace entre **-S** et *server_name*.</span><span class="sxs-lookup"><span data-stu-id="15400-113">For example, there must be a space between **-S** and *server_name*.</span></span>  
  
 <span data-ttu-id="15400-114">**-?**</span><span class="sxs-lookup"><span data-stu-id="15400-114">**-?**</span></span>  
 <span data-ttu-id="15400-115">Spécifie que le diagramme de syntaxe pour l’utilitaire **sqlmaint** doit être retourné.</span><span class="sxs-lookup"><span data-stu-id="15400-115">Specifies that the syntax diagram for **sqlmaint** be returned.</span></span> <span data-ttu-id="15400-116">Ce paramètre doit être utilisé seul.</span><span class="sxs-lookup"><span data-stu-id="15400-116">This parameter must be used alone.</span></span>  
  
 <span data-ttu-id="15400-117">**-S** _SERVER_NAME_[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="15400-117">**-S** _server_name_[ **\\**_instance_name_]</span></span>  
 <span data-ttu-id="15400-118">Spécifie l’instance cible de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15400-118">Specifies the target instance of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="15400-119">Spécifiez *server_name* pour vous connecter à l’instance par défaut du [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] sur ce serveur.</span><span class="sxs-lookup"><span data-stu-id="15400-119">Specify *server_name* to connect to the default instance of [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] on that server.</span></span> <span data-ttu-id="15400-120">Spécifiez *server_name **_\\_** instance_name* pour vous connecter à une instance nommée de [!INCLUDE[ssDE](../includes/ssde-md.md)] sur ce serveur.</span><span class="sxs-lookup"><span data-stu-id="15400-120">Specify *server_name\*\*_\\_*\* instance_name\* to connect to a named instance of [!INCLUDE[ssDE](../includes/ssde-md.md)] on that server.</span></span> <span data-ttu-id="15400-121">Si aucun serveur n’est spécifié, **sqlmaint** se connecte à l’instance par défaut de [!INCLUDE[ssDE](../includes/ssde-md.md)] sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="15400-121">If no server is specified, **sqlmaint** connects to the default instance of [!INCLUDE[ssDE](../includes/ssde-md.md)] on the local computer.</span></span>  
  
 <span data-ttu-id="15400-122">**-U** _login_ID_</span><span class="sxs-lookup"><span data-stu-id="15400-122">**-U** _login_ID_</span></span>  
 <span data-ttu-id="15400-123">Spécifie l'ID de connexion à utiliser lors de la connexion au serveur.</span><span class="sxs-lookup"><span data-stu-id="15400-123">Specifies the login ID to use when connecting to the server.</span></span> <span data-ttu-id="15400-124">Si celui-ci n’est pas fourni, **sqlmaint** tente d’utiliser l’authentification [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="15400-124">If not supplied, **sqlmaint** attempts to use [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication.</span></span> <span data-ttu-id="15400-125">Si *login_ID* contient des caractères spéciaux, il doit être encadré par des guillemets doubles. Ceux-ci sont facultatifs dans tous les autres cas.</span><span class="sxs-lookup"><span data-stu-id="15400-125">If *login_ID* contains special characters, it must be enclosed in double quotation marks ("); otherwise, the double quotation marks are optional.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="15400-126">Lorsque c'est possible, utilisez l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="15400-126">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="15400-127">**-P** _password_</span><span class="sxs-lookup"><span data-stu-id="15400-127">**-P** _password_</span></span>  
 <span data-ttu-id="15400-128">Spécifie le mot de passe de l’ID de connexion.</span><span class="sxs-lookup"><span data-stu-id="15400-128">Specifies the password for the login ID.</span></span> <span data-ttu-id="15400-129">Uniquement valide si le paramètre **-U** est également fourni.</span><span class="sxs-lookup"><span data-stu-id="15400-129">Only valid if the **-U** parameter is also supplied.</span></span> <span data-ttu-id="15400-130">Si le *password* contient des caractères spéciaux, il doit être encadré par des guillemets doubles ; ceux-ci sont facultatifs dans tous les autres cas.</span><span class="sxs-lookup"><span data-stu-id="15400-130">If *password* contains special characters, it must be enclosed in double quotation marks; otherwise, the double quotation marks are optional.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="15400-131">Le mot de passe n'est pas masqué.</span><span class="sxs-lookup"><span data-stu-id="15400-131">The password is not masked.</span></span> <span data-ttu-id="15400-132">Lorsque c'est possible, utilisez l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="15400-132">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="15400-133">**-D** _database_name_</span><span class="sxs-lookup"><span data-stu-id="15400-133">**-D** _database_name_</span></span>  
 <span data-ttu-id="15400-134">Spécifie le nom de la base de données dans laquelle l'opération de maintenance doit être effectuée.</span><span class="sxs-lookup"><span data-stu-id="15400-134">Specifies the name of the database in which to perform the maintenance operation.</span></span> <span data-ttu-id="15400-135">Si *database_name* contient des caractères spéciaux, il doit être encadré par des guillemets doubles. Ceux-ci sont facultatifs dans tous les autres cas.</span><span class="sxs-lookup"><span data-stu-id="15400-135">If *database_name* contains special characters, it must be enclosed in double quotation marks; otherwise, the double quotation marks are optional.</span></span>  
  
 <span data-ttu-id="15400-136">**-PlanName** _name_</span><span class="sxs-lookup"><span data-stu-id="15400-136">**-PlanName** _name_</span></span>  
 <span data-ttu-id="15400-137">Spécifie le nom du plan de maintenance de base de données défini par l'Assistant Plan de maintenance de base de données.</span><span class="sxs-lookup"><span data-stu-id="15400-137">Specifies the name of a database maintenance plan defined using the Database Maintenance Plan Wizard.</span></span> <span data-ttu-id="15400-138">La seule information du plan utilisée par **sqlmaint** est la liste des bases de données qui y figurent.</span><span class="sxs-lookup"><span data-stu-id="15400-138">The only information **sqlmaint** uses from the plan is the list of the databases in the plan.</span></span> <span data-ttu-id="15400-139">Toutes les activités de maintenance spécifiées dans les autres paramètres de **sqlmaint** s’appliquent à cette liste de bases de données.</span><span class="sxs-lookup"><span data-stu-id="15400-139">Any maintenance activities you specify in the other **sqlmaint** parameters are applied to this list of databases.</span></span>  
  
 <span data-ttu-id="15400-140">**-PlanID** _guid_</span><span class="sxs-lookup"><span data-stu-id="15400-140">**-PlanID** _guid_</span></span>  
 <span data-ttu-id="15400-141">Spécifie l'identificateur global unique (GUID) d'un plan de maintenance de base de données à l'aide de l'Assistant Plan de maintenance de base de données.</span><span class="sxs-lookup"><span data-stu-id="15400-141">Specifies the globally unique identifier (GUID) of a database maintenance plan defined using the Database Maintenance Plan Wizard.</span></span> <span data-ttu-id="15400-142">La seule information du plan utilisée par **sqlmaint** est la liste des bases de données qui y figurent.</span><span class="sxs-lookup"><span data-stu-id="15400-142">The only information **sqlmaint** uses from the plan is the list of the databases in the plan.</span></span> <span data-ttu-id="15400-143">Toutes les activités de maintenance spécifiées dans les autres paramètres de **sqlmaint** s’appliquent à cette liste de bases de données.</span><span class="sxs-lookup"><span data-stu-id="15400-143">Any maintenance activities you specify in the other **sqlmaint** parameters are applied to this list of databases.</span></span> <span data-ttu-id="15400-144">Cela doit correspondre à une valeur plan_id dans msdb.dbo.sysdbmaintplans.</span><span class="sxs-lookup"><span data-stu-id="15400-144">This must match a plan_id value in msdb.dbo.sysdbmaintplans.</span></span>  
  
 <span data-ttu-id="15400-145">**-Rpt** _text_file_</span><span class="sxs-lookup"><span data-stu-id="15400-145">**-Rpt** _text_file_</span></span>  
 <span data-ttu-id="15400-146">Spécifie le chemin et le nom complet du fichier dans lequel le rapport doit être créé.</span><span class="sxs-lookup"><span data-stu-id="15400-146">Specifies the full path and name of the file into which the report is to be generated.</span></span> <span data-ttu-id="15400-147">Le rapport est aussi créé à l'écran.</span><span class="sxs-lookup"><span data-stu-id="15400-147">The report is also generated on the screen.</span></span> <span data-ttu-id="15400-148">Le rapport conserve les informations de version en ajoutant une date au nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="15400-148">The report maintains version information by adding a date to the file name.</span></span> <span data-ttu-id="15400-149">La date est générée comme suit : à la fin du nom de fichier, mais avant le point, sous la forme _*yyyyMMddhhmm*.</span><span class="sxs-lookup"><span data-stu-id="15400-149">The date is generated as follows: at the end of the file name but before the period, in the form _*yyyyMMddhhmm*.</span></span> <span data-ttu-id="15400-150">*yyyy* = année, *MM* = mois, *dd* = jour, *hh* = heure, *mm* = minute.</span><span class="sxs-lookup"><span data-stu-id="15400-150">*yyyy* = year, *MM* = month, *dd* = day, *hh* = hour, *mm* = minute.</span></span>  
  
 <span data-ttu-id="15400-151">Si vous exécutez l'utilitaire à 10h23</span><span class="sxs-lookup"><span data-stu-id="15400-151">If you run the utility at 10:23 A.M.</span></span> <span data-ttu-id="15400-152">le 1er décembre 1996, avec la valeur *text_file* suivante :</span><span class="sxs-lookup"><span data-stu-id="15400-152">on December 1, 1996, and this is the *text_file* value:</span></span>  
  
```  
c:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint.rpt  
```  
  
 <span data-ttu-id="15400-153">Le nom du fichier créé est :</span><span class="sxs-lookup"><span data-stu-id="15400-153">The generated file name is:</span></span>  
  
```  
c:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint_199612011023.rpt  
```  
  
 <span data-ttu-id="15400-154">Le nom de fichier complet UNC (Universal Naming Convention) est requis pour *text_file* lorsque **sqlmaint** accède à un serveur distant.</span><span class="sxs-lookup"><span data-stu-id="15400-154">The full Universal Naming Convention (UNC) file name is required for *text_file* when **sqlmaint** accesses a remote server.</span></span>  
  
 <span data-ttu-id="15400-155">**-To** _operator_name_</span><span class="sxs-lookup"><span data-stu-id="15400-155">**-To** _operator_name_</span></span>  
 <span data-ttu-id="15400-156">Spécifie l'opérateur auquel le rapport créé sera envoyé par l'intermédiaire de SQL Mail.</span><span class="sxs-lookup"><span data-stu-id="15400-156">Specifies the operator to whom the generated report is sent through SQL Mail.</span></span>  
  
 <span data-ttu-id="15400-157">**-HtmlRpt** _html_file_</span><span class="sxs-lookup"><span data-stu-id="15400-157">**-HtmlRpt** _html_file_</span></span>  
 <span data-ttu-id="15400-158">Spécifie le chemin et le nom complets du fichier dans lequel un rapport HTML doit être créé.</span><span class="sxs-lookup"><span data-stu-id="15400-158">Specifies the full path and name of the file into which an HTML report is to be generated.</span></span> <span data-ttu-id="15400-159">**sqlmaint** crée le nom de fichier en lui ajoutant une chaîne de type _*yyyyMMddhhmm* de la même manière que pour le paramètre **-Rpt** .</span><span class="sxs-lookup"><span data-stu-id="15400-159">**sqlmaint** generates the file name by appending a string of the format _*yyyyMMddhhmm* to the file name, just as it does for the **-Rpt** parameter.</span></span>  
  
 <span data-ttu-id="15400-160">Le nom de fichier complet UNC est requis pour *html_file* lorsque **sqlmaint** accède à un serveur distant.</span><span class="sxs-lookup"><span data-stu-id="15400-160">The full UNC file name is required for *html_file* when **sqlmaint** accesses a remote server.</span></span>  
  
 <span data-ttu-id="15400-161">**-DelHtmlRpt** \<*time_period*></span><span class="sxs-lookup"><span data-stu-id="15400-161">**-DelHtmlRpt** \<*time_period*></span></span>  
 <span data-ttu-id="15400-162">Spécifie que tous les rapports HTML du répertoire des rapports doivent être supprimés si l'intervalle de temps écoulé depuis la création du fichier de rapport excède la valeur \<*time_period*>.</span><span class="sxs-lookup"><span data-stu-id="15400-162">Specifies that any HTML report in the report directory be deleted if the time interval after the creation of the report file exceeds \<*time_period*>.</span></span> <span data-ttu-id="15400-163">**-DelHtmlRpt** recherche les fichiers dont les noms correspondent au modèle créé à partir du paramètre *html_file*.</span><span class="sxs-lookup"><span data-stu-id="15400-163">**-DelHtmlRpt** looks for files whose name fits the pattern generated from the *html_file* parameter.</span></span> <span data-ttu-id="15400-164">Si *html_file* est c:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint.htm, **-DelHtmlRpt** provoque la suppression par **sqlmaint** de tous les fichiers dont le nom correspond au modèle C:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint\*.htm et qui sont antérieurs à \<*time_period*>.</span><span class="sxs-lookup"><span data-stu-id="15400-164">If *html_file* is c:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint.htm, then **-DelHtmlRpt** causes **sqlmaint** to delete any files whose names match the pattern C:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint\*.htm and that are older than the specified \<*time_period*>.</span></span>  
  
 <span data-ttu-id="15400-165">**-RmUnusedSpace** _threshold_percent free_percent_</span><span class="sxs-lookup"><span data-stu-id="15400-165">**-RmUnusedSpace** _threshold_percent free_percent_</span></span>  
 <span data-ttu-id="15400-166">Spécifie que l’espace inutilisé est retiré de la base de données spécifiée dans **-D**.</span><span class="sxs-lookup"><span data-stu-id="15400-166">Specifies that unused space be removed from the database specified in **-D**.</span></span> <span data-ttu-id="15400-167">Cette option est uniquement utile pour les bases de données dont la configuration prévoit une croissance automatique.</span><span class="sxs-lookup"><span data-stu-id="15400-167">This option is only useful for databases that are defined to grow automatically.</span></span> <span data-ttu-id="15400-168">*Threshold_percent* indique, en Mo, la taille qu’une base de données doit atteindre pour que **sqlmaint** tente d’en supprimer l’espace de données inutilisé.</span><span class="sxs-lookup"><span data-stu-id="15400-168">*Threshold_percent* specifies in megabytes the size that the database must reach before **sqlmaint** attempts to remove unused data space.</span></span> <span data-ttu-id="15400-169">Si la base de données est plus petite que *threshold_percent*, aucune action n’est exécutée.</span><span class="sxs-lookup"><span data-stu-id="15400-169">If the database is smaller than the *threshold_percent*, no action is taken.</span></span> <span data-ttu-id="15400-170">*Free_percent* spécifie l’espace qui doit rester libre dans la base de données, exprimé sous la forme d’un pourcentage de la taille finale de celle-ci.</span><span class="sxs-lookup"><span data-stu-id="15400-170">*Free_percent* specifies how much unused space must remain in the database, specified as a percentage of the final size of the database.</span></span> <span data-ttu-id="15400-171">Prenons l’exemple d’une base de données de 200 Mo contenant 100 Mo de données. Si la valeur 10 est affectée à *free_percent* , la base de données a pour taille finale 110 Mo.</span><span class="sxs-lookup"><span data-stu-id="15400-171">For example, if a 200-MB database contains 100 MB of data, specifying 10 for *free_percent* results in the final database size being 110 MB.</span></span> <span data-ttu-id="15400-172">La base de données n’est pas étendue si elle est inférieure à la valeur de *free_percent* augmentée de la quantité de données contenue dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="15400-172">Note that a database is not expanded if it is smaller than *free_percent* plus the amount of data in the database.</span></span> <span data-ttu-id="15400-173">Prenons l’exemple d’une base de données de 108 Mo contenant 100 Mo de données. Si la valeur 10 est affectée à *free_percent* , la base de données ne passera pas à 110 Mo, mais conserve sa taille de 108 Mo.</span><span class="sxs-lookup"><span data-stu-id="15400-173">For example, if a 108-MB database has 100 MB of data, specifying 10 for *free_percent* does not expand the database to 110 MB; it remains at 108 MB.</span></span>  
  
 <span data-ttu-id="15400-174">**-CkDB** |  **-CkDBNoIdx**</span><span class="sxs-lookup"><span data-stu-id="15400-174">**-CkDB** | **-CkDBNoIdx**</span></span>  
 <span data-ttu-id="15400-175">Spécifie qu’une instruction DBCC CHECKDB ou une instruction DBCC CHECKDB avec l’option NOINDEX est exécutée dans la base de données indiquée dans **-D**.</span><span class="sxs-lookup"><span data-stu-id="15400-175">Specifies that a DBCC CHECKDB statement or a DBCC CHECKDB statement with the NOINDEX option be run in the database specified in **-D**.</span></span> <span data-ttu-id="15400-176">Pour plus d'informations, consultez DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="15400-176">For more information, see DBCC CHECKDB.</span></span>  
  
 <span data-ttu-id="15400-177">Un avertissement est enregistré dans *text_file* si la base de données est en cours d’utilisation lorsque **sqlmaint** est exécuté.</span><span class="sxs-lookup"><span data-stu-id="15400-177">A warning is written to *text_file* if the database is in use when **sqlmaint** runs.</span></span>  
  
 <span data-ttu-id="15400-178">**-CkAl** |  **-CkAlNoIdx**</span><span class="sxs-lookup"><span data-stu-id="15400-178">**-CkAl** | **-CkAlNoIdx**</span></span>  
 <span data-ttu-id="15400-179">Spécifie qu’une instruction DBCC CHECKALLOC avec l’option NOINDEX est exécutée dans la base de données indiquée dans **-D**.</span><span class="sxs-lookup"><span data-stu-id="15400-179">Specifies that a DBCC CHECKALLOC statement with the NOINDEX option be run in the database specified in **-D**.</span></span> <span data-ttu-id="15400-180">Pour plus d’informations, consultez [DBCC CHECKALLOC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkalloc-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="15400-180">For more information, see [DBCC CHECKALLOC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkalloc-transact-sql).</span></span>  
  
 <span data-ttu-id="15400-181">**-CkCat**</span><span class="sxs-lookup"><span data-stu-id="15400-181">**-CkCat**</span></span>  
 <span data-ttu-id="15400-182">Spécifie qu’une instruction DBCC CHECKCATALOG (Transact-SQL) est exécutée dans la base de données indiquée dans **-D**.</span><span class="sxs-lookup"><span data-stu-id="15400-182">Specifies that a DBCC CHECKCATALOG (Transact-SQL) statement be run in the database specified in **-D**.</span></span> <span data-ttu-id="15400-183">Pour plus d’informations, consultez [DBCC CHECKCATALOG &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkcatalog-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="15400-183">For more information, see [DBCC CHECKCATALOG &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkcatalog-transact-sql).</span></span>  
  
 <span data-ttu-id="15400-184">**-UpdOptiStats** _sample_percent_</span><span class="sxs-lookup"><span data-stu-id="15400-184">**-UpdOptiStats** _sample_percent_</span></span>  
 <span data-ttu-id="15400-185">Spécifie que l'instruction suivante doit être exécutée sur chacune des tables de la base de données :</span><span class="sxs-lookup"><span data-stu-id="15400-185">Specifies that the following statement be run on each table in the database:</span></span>  
  
```  
UPDATE STATISTICS table WITH SAMPLE sample_percent PERCENT;  
```  
  
 <span data-ttu-id="15400-186">Si les tables contiennent des colonnes calculées, vous devez également spécifier l’argument **-SupportedComputedColumn** lorsque vous utilisez **-UpdOptiStats**.</span><span class="sxs-lookup"><span data-stu-id="15400-186">If the tables contain computed columns, you must also specify the **-SupportedComputedColumn** argument when you use **-UpdOptiStats**.</span></span>  
  
 <span data-ttu-id="15400-187">Pour plus d’informations, consultez [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="15400-187">For more information, see [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span></span>  
  
 <span data-ttu-id="15400-188">**-RebldIdx** _free_space_</span><span class="sxs-lookup"><span data-stu-id="15400-188">**-RebldIdx** _free_space_</span></span>  
 <span data-ttu-id="15400-189">Spécifie que les index sur les tables de la base de données cible doivent être reconstruits sur base d’un pourcentage *free_space* inversement proportionnel au facteur de remplissage.</span><span class="sxs-lookup"><span data-stu-id="15400-189">Specifies that indexes on tables in the target database should be rebuilt by using the *free_space* percent value as the inverse of the fill factor.</span></span> <span data-ttu-id="15400-190">Par exemple, si le pourcentage *free_space* est égal à 30, le facteur de remplissage utilisé est 70.</span><span class="sxs-lookup"><span data-stu-id="15400-190">For example, if *free_space* percentage is 30, then the fill factor used is 70.</span></span> <span data-ttu-id="15400-191">Si le pourcentage indiqué dans *free_space* a comme valeur 100, les index sont reconstruits sur base du facteur de remplissage d’origine.</span><span class="sxs-lookup"><span data-stu-id="15400-191">If a *free_space* percentage value of 100 is specified, then the indexes are rebuilt with the original fill factor value.</span></span>  
  
 <span data-ttu-id="15400-192">Si les index se trouvent sur des colonnes calculées, vous devez également spécifier l’argument **-SupportComputedColumn** lorsque vous utilisez **-RebldIdx**.</span><span class="sxs-lookup"><span data-stu-id="15400-192">If the indexes are on computed columns, you must also specify the **-SupportComputedColumn** argument when you use **-RebldIdx**.</span></span>  
  
 <span data-ttu-id="15400-193">**-SupportComputedColumn**</span><span class="sxs-lookup"><span data-stu-id="15400-193">**-SupportComputedColumn**</span></span>  
 <span data-ttu-id="15400-194">Doit être spécifié pour l’exécution de commandes de maintenance DBCC avec **sqlmaint** sur des colonnes calculées.</span><span class="sxs-lookup"><span data-stu-id="15400-194">Must be specified to run DBCC maintenance commands with **sqlmaint** on computed columns.</span></span>  
  
 <span data-ttu-id="15400-195">**-WriteHistory**</span><span class="sxs-lookup"><span data-stu-id="15400-195">**-WriteHistory**</span></span>  
 <span data-ttu-id="15400-196">Spécifie que chaque action de maintenance effectuée par **sqlmaint**fait l’objet d’une entrée dans msdb.dbo.sysdbmaintplan_history.</span><span class="sxs-lookup"><span data-stu-id="15400-196">Specifies that an entry be made in msdb.dbo.sysdbmaintplan_history for each maintenance action performed by **sqlmaint**.</span></span> <span data-ttu-id="15400-197">Si **-PlanName** ou **-PlanID** est spécifié, les entrées de sysdbmaintplan_history utilisent l’ID du plan spécifié.</span><span class="sxs-lookup"><span data-stu-id="15400-197">If **-PlanName** or **-PlanID** is specified, the entries in sysdbmaintplan_history use the ID of the specified plan.</span></span> <span data-ttu-id="15400-198">Si **-D** est spécifié, l’ID du plan est remplacé par des zéros dans les entrées de sysdbmaintplan_history.</span><span class="sxs-lookup"><span data-stu-id="15400-198">If **-D** is specified, the entries in sysdbmaintplan_history are made with zeroes for the plan ID.</span></span>  
  
 <span data-ttu-id="15400-199">**-BkUpDB** [ *backup_path*] |  **-BkUpLog** [ *backup_path* ]</span><span class="sxs-lookup"><span data-stu-id="15400-199">**-BkUpDB** [ *backup_path*] |  **-BkUpLog** [ *backup_path* ]</span></span>  
 <span data-ttu-id="15400-200">Spécifie une action de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="15400-200">Specifies a backup action.</span></span> <span data-ttu-id="15400-201">**-BkUpDb** sauvegarde l’ensemble de la base de données.</span><span class="sxs-lookup"><span data-stu-id="15400-201">**-BkUpDb** backs up the entire database.</span></span> <span data-ttu-id="15400-202">**-BkUpLog** sauvegarde uniquement le journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="15400-202">**-BkUpLog** backs up only the transaction log.</span></span>  
  
 <span data-ttu-id="15400-203">*backup_path* spécifie le répertoire pour la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="15400-203">*backup_path* specifies the directory for the backup.</span></span> <span data-ttu-id="15400-204">*backup_path* n’est pas nécessaire si **-UseDefDir** est également spécifié et il est remplacé par la valeur de **-UseDefDir** si toutes deux sont spécifiées.</span><span class="sxs-lookup"><span data-stu-id="15400-204">*backup_path* is not needed if **-UseDefDir** is also specified, and is overridden by **-UseDefDir** if both are specified.</span></span> <span data-ttu-id="15400-205">La sauvegarde peut être placée à une adresse de répertoire ou de périphérique à bande (par exemple, \\\\.\TAPE0).</span><span class="sxs-lookup"><span data-stu-id="15400-205">The backup can be placed in a directory or a tape device address (for example, \\\\.\TAPE0).</span></span> <span data-ttu-id="15400-206">Le nom de fichier pour la sauvegarde d'une base de données est créé automatiquement comme suit :</span><span class="sxs-lookup"><span data-stu-id="15400-206">The file name for a database backup is generated automatically as follows:</span></span>  
  
```  
dbname_db_yyyyMMddhhmm.BAK  
  
```  
  
 <span data-ttu-id="15400-207">where</span><span class="sxs-lookup"><span data-stu-id="15400-207">where</span></span>  
  
-   <span data-ttu-id="15400-208">*dbname* est le nom de la base de données actuellement sauvegardée.</span><span class="sxs-lookup"><span data-stu-id="15400-208">*dbname* is the name of the database being backed up.</span></span>  
  
-   <span data-ttu-id="15400-209">*yyyyMMddhhmm* correspond à la date et à l’heure de l’opération de sauvegarde où *yyyy* = année, *MM* = mois, *dd* = jour, *hh* = jour et *mm* = minute.</span><span class="sxs-lookup"><span data-stu-id="15400-209">*yyyyMMddhhmm* is the time of the backup operation with *yyyy* = year, *MM* = month, *dd* = day, *hh* = hour, and *mm* = minute.</span></span>  
  
 <span data-ttu-id="15400-210">Le nom de fichier d'une transaction de sauvegarde est automatiquement créé sous la forme suivante :</span><span class="sxs-lookup"><span data-stu-id="15400-210">The file name for a transaction backup is generated automatically with a similar format:</span></span>  
  
```  
dbname_log_yyyymmddhhmm.BAK  
  
```  
  
 <span data-ttu-id="15400-211">Si vous utilisez le paramètre **-BkUpDB** , vous devez aussi spécifier le support de sauvegarde à l’aide du paramètre **-BkUpMedia** .</span><span class="sxs-lookup"><span data-stu-id="15400-211">If you use the **-BkUpDB** parameter, you must also specify the media by using the **-BkUpMedia** parameter.</span></span>  
  
 <span data-ttu-id="15400-212">**-BkUpMedia**</span><span class="sxs-lookup"><span data-stu-id="15400-212">**-BkUpMedia**</span></span>  
 <span data-ttu-id="15400-213">Précise le type de support utilisé pour la sauvegarde, DISK ou TAPE.</span><span class="sxs-lookup"><span data-stu-id="15400-213">Specifies the media type of the backup, either DISK or TAPE.</span></span>  
  
 <span data-ttu-id="15400-214">**DISK**</span><span class="sxs-lookup"><span data-stu-id="15400-214">**DISK**</span></span>  
 <span data-ttu-id="15400-215">Spécifie que le support de sauvegarde est un disque.</span><span class="sxs-lookup"><span data-stu-id="15400-215">Specifies that the backup medium is disk.</span></span>  
  
 <span data-ttu-id="15400-216">**-DelBkUps**\< *time_period* ></span><span class="sxs-lookup"><span data-stu-id="15400-216">**-DelBkUps**\< *time_period* ></span></span>  
 <span data-ttu-id="15400-217">Pour les sauvegardes sur disque, spécifie que tous les fichiers de sauvegarde du répertoire de sauvegarde doivent être supprimés si l'intervalle de temps écoulé depuis la création de la sauvegarde excède la valeur indiquée dans \<*time_period*>.</span><span class="sxs-lookup"><span data-stu-id="15400-217">For disk backups, specifies that any backup file in the backup directory be deleted if the time interval after the creation of the backup exceeds the \<*time_period*>.</span></span>  
  
 <span data-ttu-id="15400-218">**-CrBkSubDir**</span><span class="sxs-lookup"><span data-stu-id="15400-218">**-CrBkSubDir**</span></span>  
 <span data-ttu-id="15400-219">Pour les sauvegardes sur disque, spécifie qu’un sous-répertoire doit être créé dans le répertoire [*backup_path*] ou dans le répertoire de sauvegarde par défaut si **-UseDefDir** est également spécifié.</span><span class="sxs-lookup"><span data-stu-id="15400-219">For disk backups, specifies that a subdirectory be created in the [*backup_path*] directory or in the default backup directory if **-UseDefDir** is also specified.</span></span> <span data-ttu-id="15400-220">Le nom du sous-répertoire est généré à partir du nom de base de données spécifié dans **-D**.</span><span class="sxs-lookup"><span data-stu-id="15400-220">The name of the subdirectory is generated from the database name specified in **-D**.</span></span> <span data-ttu-id="15400-221">**-CrBkSubDir** offre un moyen aisé de placer toutes les sauvegardes de différentes bases de données dans des sous-répertoires séparés sans devoir modifier le paramètre *backup_path* .</span><span class="sxs-lookup"><span data-stu-id="15400-221">**-CrBkSubDir** offers an easy way to put all the backups for different databases into separate subdirectories without having to change the *backup_path* parameter.</span></span>  
  
 <span data-ttu-id="15400-222">**-UseDefDir**</span><span class="sxs-lookup"><span data-stu-id="15400-222">**-UseDefDir**</span></span>  
 <span data-ttu-id="15400-223">Pour les sauvegardes sur disque, spécifie que le fichier de sauvegarde doit être créé dans le répertoire de sauvegarde par défaut.</span><span class="sxs-lookup"><span data-stu-id="15400-223">For disk backups, specifies that the backup file be created in the default backup directory.</span></span> <span data-ttu-id="15400-224">**UseDefDir** est prioritaire sur *backup_path* si ces deux paramètres sont spécifiés.</span><span class="sxs-lookup"><span data-stu-id="15400-224">**UseDefDir** overrides *backup_path* if both are specified.</span></span> <span data-ttu-id="15400-225">Avec une installation de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] par défaut, le répertoire de sauvegarde par défaut est C:\Program Files\Microsoft SQL Server\MSSQL10_50.MSSQLSERVER\MSSQL\Backup.</span><span class="sxs-lookup"><span data-stu-id="15400-225">With a default [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] setup, the default backup directory is C:\Program Files\Microsoft SQL Server\MSSQL10_50.MSSQLSERVER\MSSQL\Backup.</span></span>  
  
 <span data-ttu-id="15400-226">**TAPE**</span><span class="sxs-lookup"><span data-stu-id="15400-226">**TAPE**</span></span>  
 <span data-ttu-id="15400-227">Spécifie que le support de sauvegarde est une bande.</span><span class="sxs-lookup"><span data-stu-id="15400-227">Specifies that the backup medium is tape.</span></span>  
  
 <span data-ttu-id="15400-228">**-BkUpOnlyIfClean**</span><span class="sxs-lookup"><span data-stu-id="15400-228">**-BkUpOnlyIfClean**</span></span>  
 <span data-ttu-id="15400-229">Spécifie que la sauvegarde a lieu uniquement si les contrôles **-Ck** spécifiés n’ont rencontré aucun problème au niveau des données.</span><span class="sxs-lookup"><span data-stu-id="15400-229">Specifies that the backup occur only if any specified **-Ck** checks did not find problems with the data.</span></span> <span data-ttu-id="15400-230">Les actions de maintenance s'exécutent dans le même ordre que celui dans lequel elles apparaissent dans la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="15400-230">Maintenance actions run in the same sequence as they appear in the command prompt.</span></span> <span data-ttu-id="15400-231">Spécifiez les paramètres **-CkDB**, **-CkDBNoIdx**, **-CkAl**, **-CkAlNoIdx**, **-CkTxtAl**ou **-CkCat** avant le(s) paramètre(s) **-BkUpDB**/ **-BkUpLog** si vous allez également spécifier **-BkUpOnlyIfClean**ou la sauvegarde a lieu, même si la vérification signale des problèmes ou pas.</span><span class="sxs-lookup"><span data-stu-id="15400-231">Specify the parameters **-CkDB**, **-CkDBNoIdx**, **-CkAl**, **-CkAlNoIdx**, **-CkTxtAl**, or **-CkCat** before the **-BkUpDB**/**-BkUpLog** parameter(s) if you are also going to specify **-BkUpOnlyIfClean**, or the backup occurs whether or not the check reports problems.</span></span>  
  
 <span data-ttu-id="15400-232">**-VrfyBackup**</span><span class="sxs-lookup"><span data-stu-id="15400-232">**-VrfyBackup**</span></span>  
 <span data-ttu-id="15400-233">Spécifie que RESTORE VERIFYONLY est exécuté sur la sauvegarde lorsque celle-ci est terminée.</span><span class="sxs-lookup"><span data-stu-id="15400-233">Specifies that RESTORE VERIFYONLY be run on the backup when it completes.</span></span>  
  
 <span data-ttu-id="15400-234">*number*[**minutes**| **hours**| **day**| **weeks**| **months**]</span><span class="sxs-lookup"><span data-stu-id="15400-234">*number*[**minutes**| **hours**| **day**| **weeks**| **months**]</span></span>  
 <span data-ttu-id="15400-235">Spécifie l'intervalle de temps utilisé pour déterminer si un rapport ou un fichier de sauvegarde est suffisamment ancien pour être supprimé.</span><span class="sxs-lookup"><span data-stu-id="15400-235">Specifies the time interval used to determine if a report or backup file is old enough to be deleted.</span></span> <span data-ttu-id="15400-236">*number* est un entier suivi (sans espace) d’une unité de temps.</span><span class="sxs-lookup"><span data-stu-id="15400-236">*number* is an integer followed (without a space) by a unit of time.</span></span> <span data-ttu-id="15400-237">Exemples valides :</span><span class="sxs-lookup"><span data-stu-id="15400-237">Valid examples:</span></span>  
  
-   <span data-ttu-id="15400-238">**12weeks**</span><span class="sxs-lookup"><span data-stu-id="15400-238">**12weeks**</span></span>  
  
-   <span data-ttu-id="15400-239">**3months**</span><span class="sxs-lookup"><span data-stu-id="15400-239">**3months**</span></span>  
  
-   <span data-ttu-id="15400-240">**15days**</span><span class="sxs-lookup"><span data-stu-id="15400-240">**15days**</span></span>  
  
 <span data-ttu-id="15400-241">Si seul le paramètre *number* est spécifié, la partie de la date sélectionnée par défaut est **semaines**.</span><span class="sxs-lookup"><span data-stu-id="15400-241">If only *number* is specified, the default date part is **weeks**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15400-242">Notes</span><span class="sxs-lookup"><span data-stu-id="15400-242">Remarks</span></span>  
 <span data-ttu-id="15400-243">L’utilitaire **sqlmaint** effectue des opérations de maintenance sur une ou plusieurs bases de données.</span><span class="sxs-lookup"><span data-stu-id="15400-243">The **sqlmaint** utility performs maintenance operations on one or more databases.</span></span> <span data-ttu-id="15400-244">Si **-D** est spécifié, les opérations spécifiées par ailleurs portent uniquement sur la base de données indiquée.</span><span class="sxs-lookup"><span data-stu-id="15400-244">If **-D** is specified, the operations specified in the remaining switches are performed only on the specified database.</span></span> <span data-ttu-id="15400-245">Si **-PlanName** ou **-PlanID** est spécifié, la seule information récupérée du plan de maintenance indiqué par **sqlmaint** est la liste des bases de données contenues dans le plan.</span><span class="sxs-lookup"><span data-stu-id="15400-245">If **-PlanName** or **-PlanID** are specified, the only information **sqlmaint** retrieves from the specified maintenance plan is the list of databases in the plan.</span></span> <span data-ttu-id="15400-246">Toutes les opérations spécifiées dans les autres paramètres de **sqlmaint** s’appliquent à chaque base de données figurant sur la liste extraite du plan,</span><span class="sxs-lookup"><span data-stu-id="15400-246">All operations specified in the remaining **sqlmaint** parameters are applied against each database in the list obtained from the plan.</span></span> <span data-ttu-id="15400-247">l’utilitaire **sqlmaint** n’effectuant aucune opération de maintenance définie dans le plan lui-même.</span><span class="sxs-lookup"><span data-stu-id="15400-247">The **sqlmaint** utility does not apply any of the maintenance activities defined in the plan itself.</span></span>  
  
 <span data-ttu-id="15400-248">L’utilitaire **sqlmaint** retourne 0 en cas de réussite et 1 en cas d’échec.</span><span class="sxs-lookup"><span data-stu-id="15400-248">The **sqlmaint** utility returns 0 if it runs successfully or 1 if it fails.</span></span> <span data-ttu-id="15400-249">L'échec de l'exécution est signalé :</span><span class="sxs-lookup"><span data-stu-id="15400-249">Failure is reported:</span></span>  
  
-   <span data-ttu-id="15400-250">Les opérations de maintenance échouent dans les ces suivants :</span><span class="sxs-lookup"><span data-stu-id="15400-250">If any of the maintenance actions fail.</span></span>  
  
-   <span data-ttu-id="15400-251">Si les vérifications **-CkDB**, **-CkDBNoIdx**, **-CkAl**, **-CkAlNoIdx**, **-CkTxtAl**ou **-CkCat** trouvent des problèmes sur les données.</span><span class="sxs-lookup"><span data-stu-id="15400-251">If **-CkDB**, **-CkDBNoIdx**, **-CkAl**, **-CkAlNoIdx**, **-CkTxtAl**, or **-CkCat** checks find problems with the data.</span></span>  
  
-   <span data-ttu-id="15400-252">En cas de panne générale.</span><span class="sxs-lookup"><span data-stu-id="15400-252">If a general failure is encountered.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="15400-253">Autorisations</span><span class="sxs-lookup"><span data-stu-id="15400-253">Permissions</span></span>  
 <span data-ttu-id="15400-254">L’utilitaire **sqlmaint** peut être exécuté par tout utilisateur Windows disposant de l’autorisation **Lecture et exécution** sur `sqlmaint.exe`, qui est stockée par défaut dans le dossier `x:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER1\MSSQL\Binn` .</span><span class="sxs-lookup"><span data-stu-id="15400-254">The **sqlmaint** utility can be executed by any Windows user with **Read and Execute** permission on `sqlmaint.exe`, which by default is stored in the `x:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER1\MSSQL\Binn` folder.</span></span> <span data-ttu-id="15400-255">En outre, la connexion [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] spécifiée avec **-login_ID** doit disposer des autorisations [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] requises pour effectuer l’action spécifiée.</span><span class="sxs-lookup"><span data-stu-id="15400-255">Additionally, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login specified with **-login_ID** must have the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] permissions required to perform the specified action.</span></span> <span data-ttu-id="15400-256">Si la connexion à [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] utilise l'authentification Windows, le nom d'ouverture de session [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] mappé à l'utilisateur Windows authentifié doit disposer des autorisations [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] requises pour effectuer l'action spécifiée.</span><span class="sxs-lookup"><span data-stu-id="15400-256">If the connection to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] uses Windows Authentication, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login mapped to the authenticated Windows user must have the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] permissions required to perform the specified action.</span></span>  
  
 <span data-ttu-id="15400-257">Par exemple, l’utilisation de l’argument **-BkUpDB** nécessite l’autorisation d’exécution de l’instruction BACKUP.</span><span class="sxs-lookup"><span data-stu-id="15400-257">For example, using the **-BkUpDB** requires permission to execute the BACKUP statement.</span></span> <span data-ttu-id="15400-258">L’utilisation de l’argument **-UpdOptiStats** nécessite l’autorisation d’exécution de l’instruction UPDATE STATISTICS.</span><span class="sxs-lookup"><span data-stu-id="15400-258">And using the **-UpdOptiStats** argument requires permission to execute the UPDATE STATISTICS statement.</span></span> <span data-ttu-id="15400-259">Pour plus d'informations, consultez la section « Autorisations » des rubriques correspondantes de la documentation en ligne.</span><span class="sxs-lookup"><span data-stu-id="15400-259">For more information, see the "Permissions" sections of the corresponding topics in Books Online.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="15400-260">Exemples</span><span class="sxs-lookup"><span data-stu-id="15400-260">Examples</span></span>  
  
### <a name="a-performing-dbcc-checks-on-a-database"></a><span data-ttu-id="15400-261">R.</span><span class="sxs-lookup"><span data-stu-id="15400-261">A.</span></span> <span data-ttu-id="15400-262">Réalisation de vérifications DBCC sur une base de données</span><span class="sxs-lookup"><span data-stu-id="15400-262">Performing DBCC checks on a database</span></span>  
  
```  
sqlmaint -S MyServer -D AdventureWorks2012 -CkDB -CkAl -CkCat -Rpt C:\MyReports\AdvWks_chk.rpt  
```  
  
### <a name="b-updating-statistics-using-a-15-sample-in-all-databases-in-a-plan-also-shrink-any-of-the-database-that-have-reached-110-mb-to-having-only-10-free-space"></a><span data-ttu-id="15400-263">B.</span><span class="sxs-lookup"><span data-stu-id="15400-263">B.</span></span> <span data-ttu-id="15400-264">Mise à jour des statistiques avec un échantillonnage de 15 % dans toutes les bases de données d'un plan.</span><span class="sxs-lookup"><span data-stu-id="15400-264">Updating statistics using a 15% sample in all databases in a plan.</span></span> <span data-ttu-id="15400-265">Compactage des bases de données ayant atteint 110 Mo de sorte qu'elles aient seulement 10 % d'espace libre</span><span class="sxs-lookup"><span data-stu-id="15400-265">Also, shrink any of the database that have reached 110 MB to having only 10% free space</span></span>  
  
```  
sqlmaint -S MyServer -PlanName MyUserDBPlan -UpdOptiStats 15 -RmUnusedSpace 110 10  
```  
  
### <a name="c-backing-up-all-the-databases-in-a-plan-to-their-individual-subdirectories-in-the-default-xprogram-filesmicrosoft-sql-servermssql12mssqlservermssqlbackup-directory-also-delete-any-backups-older-than-2-weeks"></a><span data-ttu-id="15400-266">C.</span><span class="sxs-lookup"><span data-stu-id="15400-266">C.</span></span> <span data-ttu-id="15400-267">Sauvegarde de toutes les bases de données d'un plan dans leurs sous-répertoires respectifs du répertoire par défaut x:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup.</span><span class="sxs-lookup"><span data-stu-id="15400-267">Backing up all the databases in a plan to their individual subdirectories in the default x:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup directory.</span></span> <span data-ttu-id="15400-268">Suppression de toute sauvegarde antérieure à 2 semaines</span><span class="sxs-lookup"><span data-stu-id="15400-268">Also, delete any backups older than 2 weeks</span></span>  
  
```  
sqlmaint -S MyServer -PlanName MyUserDBPlan -BkUpDB -BkUpMedia DISK -UseDefDir -CrBkSubDir -DelBkUps 2weeks  
```  
  
### <a name="d-backing-up-a-database-to-the-default-xprogram-filesmicrosoft-sql-servermssql12mssqlservermssqlbackup-directory"></a><span data-ttu-id="15400-269">D.</span><span class="sxs-lookup"><span data-stu-id="15400-269">D.</span></span> <span data-ttu-id="15400-270">Sauvegarde d’une base de données dans la base de données par défaut x:\Program Files\Microsoft SQL Server\MSSQL12. Répertoire MSSQLSERVER\MSSQL\Backup. </span><span class="sxs-lookup"><span data-stu-id="15400-270">Backing up a database to the default x:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup directory.</span></span>\  
  
```  
sqlmaint -S MyServer -BkUpDB -BkUpMedia DISK -UseDefDir  
```  
  
## <a name="see-also"></a><span data-ttu-id="15400-271">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="15400-271">See Also</span></span>  
 <span data-ttu-id="15400-272">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="15400-272">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 [<span data-ttu-id="15400-273">UPDATE STATISTICS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="15400-273">UPDATE STATISTICS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/update-statistics-transact-sql)  
  
  
