---
title: Modifier des scripts SQLCMD à l'aide de l'Éditeur de requête
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- scripts [SQL Server], SQLCMD scripts
- SQLCMD scripts
- modifying scripts
- Query Editor [Database Engine], SQLCMD scripts
- scripts [SQL Server], SQL Server Management Studio
ms.assetid: f77b866d-c330-47c9-9e74-0b8d8dff4b31
author: rothja
ms.author: jroth
ms.openlocfilehash: a3466cfc15ea2f4f0c8de5da42f4a1c24c28a575
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610579"
---
# <a name="edit-sqlcmd-scripts-with-query-editor"></a><span data-ttu-id="1da8e-102">Modifier des scripts SQLCMD à l'aide de l'Éditeur de requête</span><span class="sxs-lookup"><span data-stu-id="1da8e-102">Edit SQLCMD Scripts with Query Editor</span></span>
  <span data-ttu-id="1da8e-103">Grâce à l'éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , vous pouvez écrire et modifier des requêtes en tant que scripts SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="1da8e-103">By using the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] you can write and edit queries as SQLCMD scripts.</span></span> <span data-ttu-id="1da8e-104">Vous utilisez des scripts SQLCMD lorsque vous devez traiter des commandes Windows System et des instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] dans le même script.</span><span class="sxs-lookup"><span data-stu-id="1da8e-104">You use SQLCMD scripts when you have to process Windows System commands and [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the same script.</span></span>  
  
## <a name="sqlcmd-mode"></a><span data-ttu-id="1da8e-105">Mode SQLCMD</span><span class="sxs-lookup"><span data-stu-id="1da8e-105">SQLCMD Mode</span></span>  
 <span data-ttu-id="1da8e-106">Pour utiliser l'éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] moteur de base de données afin d'écrire ou de modifier des scripts SQLCMD, vous devez activer le mode de script SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="1da8e-106">To use the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor to write or edit SQLCMD scripts, you must enable the SQLCMD scripting mode.</span></span> <span data-ttu-id="1da8e-107">Par défaut, il n'est pas activé dans l'Éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="1da8e-107">By default, SQLCMD mode is not enabled in the Query Editor.</span></span> <span data-ttu-id="1da8e-108">Vous pouvez l'activer en cliquant sur l'icône **Mode SQLCMD** dans la barre d'outils ou en sélectionnant **Mode SQLCMD** dans le menu **Requête** .</span><span class="sxs-lookup"><span data-stu-id="1da8e-108">You can enable scripting mode by clicking the **SQLCMD Mode** icon in the toolbar or by selecting **SQLCMD Mode** from the **Query** menu.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1da8e-109">L'activation du mode SQLCMD désactive IntelliSense et le débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] dans l'éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1da8e-109">Enabling SQLCMD mode turns off IntelliSense and the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span>  
  
 <span data-ttu-id="1da8e-110">Dans l'Éditeur de requête, les scripts SQLCMD peuvent utiliser les mêmes fonctionnalités que tous les scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1da8e-110">SQLCMD scripts in the Query Editor can use the same features that all [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts use.</span></span> <span data-ttu-id="1da8e-111">Ces fonctionnalités incluent les suivantes :</span><span class="sxs-lookup"><span data-stu-id="1da8e-111">These features include the following:</span></span>  
  
-   <span data-ttu-id="1da8e-112">codage en couleurs ;</span><span class="sxs-lookup"><span data-stu-id="1da8e-112">Color Coding</span></span>  
  
-   <span data-ttu-id="1da8e-113">exécution des scripts ;</span><span class="sxs-lookup"><span data-stu-id="1da8e-113">Executing Scripts</span></span>  
  
-   <span data-ttu-id="1da8e-114">Contrôle de la source</span><span class="sxs-lookup"><span data-stu-id="1da8e-114">Source Control</span></span>  
  
-   <span data-ttu-id="1da8e-115">analyse des scripts ;</span><span class="sxs-lookup"><span data-stu-id="1da8e-115">Parsing Scripts</span></span>  
  
-   <span data-ttu-id="1da8e-116">Showplan</span><span class="sxs-lookup"><span data-stu-id="1da8e-116">Showplan</span></span>  
  
## <a name="enable-sqlcmd-scripting-in-query-editor"></a><span data-ttu-id="1da8e-117">Activation des scripts SQLCMD dans l'Éditeur de requête</span><span class="sxs-lookup"><span data-stu-id="1da8e-117">Enable SQLCMD Scripting in Query Editor</span></span>  
 <span data-ttu-id="1da8e-118">Pour activer le script SQLCMD pour une fenêtre active de l'éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] moteur de base de données, utilisez la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="1da8e-118">To turn SQLCMD scripting on for an active [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window, use the following procedure.</span></span>  
  
#### <a name="to-switch-a-database-engine-query-editor-window-to-sqlcmd-mode"></a><span data-ttu-id="1da8e-119">Pour basculer l'Éditeur de requête du moteur de base de données en mode SQLCMD</span><span class="sxs-lookup"><span data-stu-id="1da8e-119">To switch a Database Engine Query Editor window to SQLCMD mode</span></span>  
  
1.  <span data-ttu-id="1da8e-120">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur le serveur et choisissez **Nouvelle requête**pour ouvrir une nouvelle fenêtre de l’éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1da8e-120">In Object Explorer, right-click the server, and then click **New Query**, to open a new [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window.</span></span>  
  
2.  <span data-ttu-id="1da8e-121">Dans le menu **Requête** , cliquez sur **Mode SQLCMD**.</span><span class="sxs-lookup"><span data-stu-id="1da8e-121">On the **Query** menu, click **SQLCMD Mode**.</span></span>  
  
     <span data-ttu-id="1da8e-122">L'éditeur de requête exécute les instructions **sqlcmd** dans son contexte.</span><span class="sxs-lookup"><span data-stu-id="1da8e-122">The Query Editor executes **sqlcmd** statements in the context of the Query Editor.</span></span>  
  
3.  <span data-ttu-id="1da8e-123">Dans la barre d'outils **Éditeur SQL** , dans la liste **Bases de données disponibles** , sélectionnez [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1da8e-123">On the **SQL Editor** toolbar, in the **Available Databases** list, select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
4.  <span data-ttu-id="1da8e-124">Dans la fenêtre de l’éditeur de requête, tapez les deux instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] suivantes et l’instruction `!!DIR` **sqlcmd** :</span><span class="sxs-lookup"><span data-stu-id="1da8e-124">In the Query Editor window, type the following two [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and the `!!DIR` **sqlcmd** statement:</span></span>  
  
    ```  
    SELECT DISTINCT Type FROM Sales.SpecialOffer;  
    GO  
    !!DIR  
    GO  
    SELECT ProductCategoryID, Name FROM Production.ProductCategory;  
    GO  
    ```  
  
5.  <span data-ttu-id="1da8e-125">Appuyez sur F5 pour exécuter toute la section d'instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] et MS-DOS.</span><span class="sxs-lookup"><span data-stu-id="1da8e-125">Press F5 to execute the whole section of mixed [!INCLUDE[tsql](../../includes/tsql-md.md)] and MS-DOS statements.</span></span>  
  
     <span data-ttu-id="1da8e-126">Consultez les deux volets de résultats SQL générés par la première et la troisième instruction.</span><span class="sxs-lookup"><span data-stu-id="1da8e-126">Notice the two SQL result panes from the first and third statements.</span></span>  
  
6.  <span data-ttu-id="1da8e-127">Dans le volet **Résultats** , cliquez sur l'onglet **Messages** pour afficher les messages des trois instructions :</span><span class="sxs-lookup"><span data-stu-id="1da8e-127">In the **Results** pane, click the **Messages** tab to see the messages from all three statements:</span></span>  
  
    -   <span data-ttu-id="1da8e-128">(6 lignes affectées)</span><span class="sxs-lookup"><span data-stu-id="1da8e-128">(6 row(s) affected)</span></span>  
  
    -   \<The directory information>  
  
    -   <span data-ttu-id="1da8e-129">(4 lignes affectées)</span><span class="sxs-lookup"><span data-stu-id="1da8e-129">(4 row(s) affected)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1da8e-130">Lorsque l'utilitaire **sqlcmd** est exécuté à partir de la ligne de commande, il permet une interaction totale avec le système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="1da8e-130">When executed from the command line, the **sqlcmd** utility permits full interaction with the operating system.</span></span> <span data-ttu-id="1da8e-131">Lorsque vous utilisez l'Éditeur de requête en **Mode SQLCMD**, vous devez veiller à ne pas exécuter d'instructions interactives.</span><span class="sxs-lookup"><span data-stu-id="1da8e-131">When you use the Query Editor in **SQLCMD Mode**, you must be careful not to execute interactive statements.</span></span> <span data-ttu-id="1da8e-132">L'Éditeur de requêtes ne peut pas répondre aux invites du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="1da8e-132">The Query Editor cannot respond to operating system prompts.</span></span>  
  
 <span data-ttu-id="1da8e-133">Pour plus d'informations sur l'exécution de SQLCMD, consultez [sqlcmd Utility](../../tools/sqlcmd-utility.md)ou suivez le didacticiel qui lui est consacré.</span><span class="sxs-lookup"><span data-stu-id="1da8e-133">For more information about how to run SQLCMD, see [sqlcmd Utility](../../tools/sqlcmd-utility.md), or take the SQLCMD tutorial.</span></span>  
  
## <a name="enable-sqlcmd-scripting-by-default"></a><span data-ttu-id="1da8e-134">Activation des scripts SQLCMD par défaut</span><span class="sxs-lookup"><span data-stu-id="1da8e-134">Enable SQLCMD Scripting by Default</span></span>  
 <span data-ttu-id="1da8e-135">Pour activer les scripts SQLCMD par défaut, dans le menu **Outils** , sélectionnez **Options**, développez **Exécution de la requête**, **SQL Server**, cliquez sur la page **Général** , puis activez la case à cocher **Par défaut, ouvrir les nouvelles requêtes en mode SQLCMD** .</span><span class="sxs-lookup"><span data-stu-id="1da8e-135">To turn SQLCMD scripting on by default, on the **Tools** menu select **Options**, expand **Query Execution**, and **SQL Server**, click the **General** page, and then check the **By default open new queries in SQLCMD Mode** box.</span></span>  
  
## <a name="writing-and-editing-sqlcmd-scripts"></a><span data-ttu-id="1da8e-136">Écriture et modification de scripts SQLCMD</span><span class="sxs-lookup"><span data-stu-id="1da8e-136">Writing and Editing SQLCMD Scripts</span></span>  
 <span data-ttu-id="1da8e-137">Une fois le mode de scripts activé, vous pouvez écrire des commandes SQLCMD et des instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1da8e-137">After enabling scripting mode you may write SQLCMD commands and [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="1da8e-138">Les règles suivantes s’appliquent :</span><span class="sxs-lookup"><span data-stu-id="1da8e-138">The following rules apply:</span></span>  
  
-   <span data-ttu-id="1da8e-139">Les commandes SQLCMD doivent être la première instruction d'une ligne.</span><span class="sxs-lookup"><span data-stu-id="1da8e-139">SQLCMD commands must be the first statement on a line.</span></span>  
  
-   <span data-ttu-id="1da8e-140">Une seule commande SQLCMD est autorisée par ligne.</span><span class="sxs-lookup"><span data-stu-id="1da8e-140">Only one SQLCMD command is permitted on each line.</span></span>  
  
-   <span data-ttu-id="1da8e-141">Les commandes SQLCMD peuvent être précédées de commentaires ou d'espaces.</span><span class="sxs-lookup"><span data-stu-id="1da8e-141">SQLCMD commands can be preceded by comments or white space.</span></span>  
  
-   <span data-ttu-id="1da8e-142">Les commandes SQLCMD placées entre des caractères de commentaires ne sont pas exécutées.</span><span class="sxs-lookup"><span data-stu-id="1da8e-142">SQLCMD commands within comment characters are not executed.</span></span>  
  
-   <span data-ttu-id="1da8e-143">Les caractères de commentaires d'une seule ligne sont deux tirets (`--)` qui doivent être placés au début d'une ligne.</span><span class="sxs-lookup"><span data-stu-id="1da8e-143">Single line comment characters are two hyphens (`--)` and must appear at the beginning of a line.</span></span>  
  
-   <span data-ttu-id="1da8e-144">Les commandes du système d'exploitation doivent être précédées de deux points d'exclamation (`!!`).</span><span class="sxs-lookup"><span data-stu-id="1da8e-144">Operating system commands must be preceded by two exclamation points (`!!`).</span></span> <span data-ttu-id="1da8e-145">La commande avec deux points d'exclamation entraîne l'exécution de l'instruction qui suit les points d'exclamation avec le processeur de commandes `cmd.exe` .</span><span class="sxs-lookup"><span data-stu-id="1da8e-145">The double-exclamation points command causes the statement that follows the exclamation points to be executed using the `cmd.exe` command processor.</span></span> <span data-ttu-id="1da8e-146">Le texte situé après `!!` est transmis en tant que paramètre à `cmd.exe`. La ligne de commande finale s'exécute donc en tant que : `"%SystemRoot%\system32\cmd.exe /c <text after !!>"`.</span><span class="sxs-lookup"><span data-stu-id="1da8e-146">The text after `!!` is passed in as a parameter to `cmd.exe`, so the final command line will execute as: `"%SystemRoot%\system32\cmd.exe /c <text after !!>"`.</span></span>  
  
-   <span data-ttu-id="1da8e-147">Pour distinguer clairement les commandes SQLCMD des commandes [!INCLUDE[tsql](../../includes/tsql-md.md)], toutes les commandes SQLCMD doivent être précédées d'un symbole deux-points (`:`).</span><span class="sxs-lookup"><span data-stu-id="1da8e-147">To make a clear distinction between SQLCMD commands and [!INCLUDE[tsql](../../includes/tsql-md.md)], all SQLCMD commands, need to be prefixed with a colon (`:`).</span></span>  
  
-   <span data-ttu-id="1da8e-148">La commande `GO` peut être utilisée sans préfixe, ou bien précédée de `!!:`</span><span class="sxs-lookup"><span data-stu-id="1da8e-148">The `GO` command may be used without preface, or preceded by `!!:`</span></span>  
  
-   <span data-ttu-id="1da8e-149">L’éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] prend en charge les variables d’environnement et les variables définies dans un script SQLCMD, mais il ne prend pas en charge les variables SQLCMD intégrées ni les variables **osql** .</span><span class="sxs-lookup"><span data-stu-id="1da8e-149">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor supports environment variables and variables that are defined as part of a SQLCMD script, but does not support built-in SQLCMD or **osql** variables.</span></span> <span data-ttu-id="1da8e-150">Le traitement SQLCMD de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] respecte la casse pour les variables.</span><span class="sxs-lookup"><span data-stu-id="1da8e-150">SQLCMD processing by [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is case sensitive for variables.</span></span> <span data-ttu-id="1da8e-151">Par exemple, PRINT '$ (COMPUTERNAME)' génère le bon résultat et PRINT '$ (ComputerName)' retourne une erreur.</span><span class="sxs-lookup"><span data-stu-id="1da8e-151">For example, PRINT '$(COMPUTERNAME)' produces the correct result, but PRINT '$(ComputerName)' returns an error.</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="1da8e-152">utilise [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]SqlClient pour les exécutions en mode normal et SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="1da8e-152">uses [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]SqlClient for execution in regular and SQLCMD mode.</span></span> <span data-ttu-id="1da8e-153">Lorsqu'il est exécuté à partir de la ligne de commande, SQLCMD utilise le fournisseur OLE DB.</span><span class="sxs-lookup"><span data-stu-id="1da8e-153">When run from the command line, SQLCMD uses the OLE DB provider.</span></span> <span data-ttu-id="1da8e-154">Dans la mesure où des options par défaut peuvent s'appliquer, il est possible d'obtenir un comportement différent pendant l'exécution de la même requête en mode SQLCMD [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] et dans l'utilitaire SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="1da8e-154">Because different default options may apply, it is possible to get different behavior while executing the same query in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] SQLCMD Mode, and in the SQLCMD utility.</span></span>  
  
## <a name="supported-sqlcmd-syntax"></a><span data-ttu-id="1da8e-155">Syntaxe SQLCMD prise en charge</span><span class="sxs-lookup"><span data-stu-id="1da8e-155">Supported SQLCMD Syntax</span></span>  
 <span data-ttu-id="1da8e-156">L'éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] prend en charge les mots clés de script SQLCMD suivants :</span><span class="sxs-lookup"><span data-stu-id="1da8e-156">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor supports the following SQLCMD script keywords:</span></span>  
  
 `[!!:]GO[count]`  
  
 `!! <command>`  
  
 `:exit(statement)`  
  
 `:Quit`  
  
 `:r <filename>`  
  
 `:setvar <var> <value>`  
  
 `:connect server[\instance] [-l login_timeout] [-U user [-P password]]`  
  
 `:on error [ignore|exit]`  
  
 `:error <filename>|stderr|stdout`  
  
 `:out <filename>|stderr|stdout`  
  
> [!NOTE]  
>  <span data-ttu-id="1da8e-157">Pour `:error` et `:out`, `stderr` et `stdout` envoient la sortie dans l'onglet des messages.</span><span class="sxs-lookup"><span data-stu-id="1da8e-157">For both `:error` and `:out`, `stderr` and `stdout` send output to the messages tab.</span></span>  
  
 <span data-ttu-id="1da8e-158">Les commandes SQLCMD qui ne sont pas répertoriées ci-dessus ne sont pas prises en charge dans l'Éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="1da8e-158">SQLCMD commands not listed above are not supported in Query Editor.</span></span> <span data-ttu-id="1da8e-159">Lorsqu’un script contenant des mots clés SQLCMD qui ne sont pas pris en charge est exécuté, l’éditeur de requête envoie un message « commande ignorée \* \<ignored command*> » à la destination pour chaque mot clé non pris en charge.</span><span class="sxs-lookup"><span data-stu-id="1da8e-159">When a script containing SQLCMD keywords that are not supported is executed, the Query Editor will send an "Ignoring command \*\<ignored command*>" message to the destination for each unsupported keyword.</span></span> <span data-ttu-id="1da8e-160">Le script s'exécute correctement mais les commandes non prises en charge sont ignorées.</span><span class="sxs-lookup"><span data-stu-id="1da8e-160">The script will execute successfully, but the unsupported commands will be ignored.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="1da8e-161">Étant donné que vous ne démarrez pas SQLCMD à partir de la ligne de commande, l'exécution de l'Éditeur de requête en mode SQLCMD est quelque peu limitée.</span><span class="sxs-lookup"><span data-stu-id="1da8e-161">Because you are not starting SQLCMD from the command line, there are some limitations when running Query Editor in SQLCMD Mode.</span></span> <span data-ttu-id="1da8e-162">Vous ne pouvez pas transmettre des paramètres de ligne de commande tels que des variables, et, comme l'éditeur de requête n'a pas la possibilité de répondre aux invites du système d'exploitation, vous ne devez pas exécuter d'instructions interactives.</span><span class="sxs-lookup"><span data-stu-id="1da8e-162">You cannot pass in command-line parameters such as variables, and, because the Query Editor does not have the ability to respond to operating system prompts, you must be careful not to execute interactive statements.</span></span>  
  
## <a name="color-coding-in-sqlcmd-scripts"></a><span data-ttu-id="1da8e-163">Codage en couleurs dans les scripts SQLCMD</span><span class="sxs-lookup"><span data-stu-id="1da8e-163">Color Coding in SQLCMD Scripts</span></span>  
 <span data-ttu-id="1da8e-164">Lorsque les scripts SQLCMD sont activés, les scripts sont codés en couleurs.</span><span class="sxs-lookup"><span data-stu-id="1da8e-164">With SQLCMD scripting enabled, scripts will be color coded.</span></span> <span data-ttu-id="1da8e-165">Le codage en couleurs des mots clés [!INCLUDE[tsql](../../includes/tsql-md.md)] reste inchangé.</span><span class="sxs-lookup"><span data-stu-id="1da8e-165">The color coding for [!INCLUDE[tsql](../../includes/tsql-md.md)] keywords will remain the same.</span></span> <span data-ttu-id="1da8e-166">Les commandes SQLCMD sont présentées avec un arrière-plan ombré.</span><span class="sxs-lookup"><span data-stu-id="1da8e-166">SQLCMD commands are presented with a shaded background.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1da8e-167">Exemple</span><span class="sxs-lookup"><span data-stu-id="1da8e-167">Example</span></span>  
 <span data-ttu-id="1da8e-168">L’exemple ci-après utilise une instruction **sqlcmd** pour créer un fichier de sortie nommé testoutput.txt et exécute deux instructions SELECT [!INCLUDE[tsql](../../includes/tsql-md.md)] ainsi qu’une commande du système d’exploitation (pour imprimer le répertoire actuel).</span><span class="sxs-lookup"><span data-stu-id="1da8e-168">The following example uses a **sqlcmd** statement to create an output file called testoutput.txt, executes two [!INCLUDE[tsql](../../includes/tsql-md.md)] SELECT statements along with one operating system command (to print out the current directory).</span></span> <span data-ttu-id="1da8e-169">Le fichier résultant contient la sortie du message provenant de l'instruction `DIR` , suivie des résultats des instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1da8e-169">The resultant file contains the message output from the `DIR` statement, followed by the results output from the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
```  
:out C:\testoutput.txt  
SELECT @@VERSION As 'Server Version'  
!!DIR  
!!:GO  
SELECT @@SERVERNAME AS 'Server Name'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="1da8e-170">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1da8e-170">See Also</span></span>  
 [<span data-ttu-id="1da8e-171">Utilitaire sqlcmd</span><span class="sxs-lookup"><span data-stu-id="1da8e-171">sqlcmd Utility</span></span>](../../tools/sqlcmd-utility.md)  
  
  
