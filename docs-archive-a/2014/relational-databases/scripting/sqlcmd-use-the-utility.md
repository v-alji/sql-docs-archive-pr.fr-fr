---
title: Utiliser l'utilitaire sqlcmd
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- Transact-SQL statements, executing
- command prompt utilities [SQL Server], sqlcmd
- statements [SQL Server], executing
- sqlcmd utility, about sqlcmd utility
ms.assetid: 3ec89119-7314-43ef-9e91-12e72bb63d62
author: rothja
ms.author: jroth
ms.openlocfilehash: 922f9915272fb2d7fc63487ec135ce44ee91e88b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612216"
---
# <a name="use-the-sqlcmd-utility"></a><span data-ttu-id="26836-102">Utiliser l'utilitaire sqlcmd</span><span class="sxs-lookup"><span data-stu-id="26836-102">Use the sqlcmd Utility</span></span>
  <span data-ttu-id="26836-103">L'utilitaire `sqlcmd` est un utilitaire de ligne de commande destiné à l'exécution ad hoc et interactive des instructions et des scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] et à l'automatisation des tâches de script [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26836-103">The `sqlcmd` utility is a command-line utility for ad hoc, interactive execution of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and scripts and for automating [!INCLUDE[tsql](../../includes/tsql-md.md)] scripting tasks.</span></span> <span data-ttu-id="26836-104">Pour utiliser `sqlcmd` de façon interactive ou pour créer des fichiers de script destinés à être exécutés avec `sqlcmd`, les utilisateurs doivent connaître [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26836-104">To use `sqlcmd` interactively, or to build script files to be run using `sqlcmd`, users must understand [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="26836-105">L'utilitaire `sqlcmd` est généralement utilisé des façons suivantes :</span><span class="sxs-lookup"><span data-stu-id="26836-105">The `sqlcmd` utility is typically used in the following ways:</span></span>  
  
-   <span data-ttu-id="26836-106">Les utilisateurs entrent les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] de façon interactive comme s'ils travaillaient à partir de l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="26836-106">Users interactively enter [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in a manner similar to working at the command prompt.</span></span> <span data-ttu-id="26836-107">Les résultats s'affichent dans l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="26836-107">The results are displayed at the command prompt.</span></span> <span data-ttu-id="26836-108">Pour ouvrir une fenêtre d'invite de commandes, cliquez sur **Démarrer**, sur **Tous les programmes**, pointez sur **Accessoires**, puis cliquez sur **Invite de commandes**.</span><span class="sxs-lookup"><span data-stu-id="26836-108">To open a Command Prompt window, click **Start**, click **All Programs**, point to **Accessories**, and then click **Command Prompt**.</span></span> <span data-ttu-id="26836-109">À l'invite de commandes, tapez `sqlcmd` suivi d'une liste des options de votre choix.</span><span class="sxs-lookup"><span data-stu-id="26836-109">At the command prompt, type `sqlcmd` followed by a list of options that you want.</span></span> <span data-ttu-id="26836-110">Pour obtenir la liste complète des options prises en charge par `sqlcmd` , consultez l' [utilitaire sqlcmd](../../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="26836-110">For a complete list of the options that are supported by `sqlcmd`, see [sqlcmd Utility](../../tools/sqlcmd-utility.md).</span></span>  
  
-   <span data-ttu-id="26836-111">Les utilisateurs soumettent un travail `sqlcmd` soit en spécifiant une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] unique à exécuter, soit en indiquant à l'utilitaire un fichier texte contenant les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] à exécuter.</span><span class="sxs-lookup"><span data-stu-id="26836-111">Users submit a `sqlcmd` job either by specifying a single [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to execute, or by pointing the utility to a text file that contains [!INCLUDE[tsql](../../includes/tsql-md.md)] statements to execute.</span></span> <span data-ttu-id="26836-112">Le résultat est généralement généré dans un fichier texte, mais il peut aussi être affiché dans l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="26836-112">The output is usually directed to a text file, but it can also be displayed at the command prompt.</span></span>  
  
-   <span data-ttu-id="26836-113">[Mode SQLCMD](edit-sqlcmd-scripts-with-query-editor.md) dans l'Éditeur de requête [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="26836-113">[SQLCMD mode](edit-sqlcmd-scripts-with-query-editor.md) in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor.</span></span>  
  
-   <span data-ttu-id="26836-114">SMO (SQL Server Management Objects)</span><span class="sxs-lookup"><span data-stu-id="26836-114">SQL Server Management Objects (SMO)</span></span>  
  
-   <span data-ttu-id="26836-115">Travaux CmdExec de SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="26836-115">SQL Server Agent CmdExec jobs.</span></span>  
  
## <a name="typically-used-sqlcmd-options"></a><span data-ttu-id="26836-116">Options sqlcmd courantes</span><span class="sxs-lookup"><span data-stu-id="26836-116">Typically Used sqlcmd Options</span></span>  
 <span data-ttu-id="26836-117">Les options suivantes sont les plus fréquemment utilisées :</span><span class="sxs-lookup"><span data-stu-id="26836-117">The following options are used most frequently:</span></span>  
  
-   <span data-ttu-id="26836-118">L’option de serveur (**-S**) qui identifie l’instance de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à laquelle `sqlcmd` se connecte.</span><span class="sxs-lookup"><span data-stu-id="26836-118">The server option (**-S**) that identifies the instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to which `sqlcmd` connects.</span></span>  
  
-   <span data-ttu-id="26836-119">Options d’authentification (**-E**, **-U**et **-P**) qui spécifient les informations d’identification `sqlcmd` utilisées par pour se connecter à l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="26836-119">Authentication options (**-E**, **-U**, and **-P**) that specify the credentials that `sqlcmd` uses to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="26836-120">L’option **-E** est l’option par défaut et il n’est pas nécessaire de la définir.</span><span class="sxs-lookup"><span data-stu-id="26836-120">The **-E** option is the default and does not have to be specified.</span></span>  
  
-   <span data-ttu-id="26836-121">Options d’entrée (**-q**, **-q**et **-i**) qui identifient l’emplacement de l’entrée dans `sqlcmd` .</span><span class="sxs-lookup"><span data-stu-id="26836-121">Input options (**-Q**, **-q**, and **-i**) that identify the location of the input to `sqlcmd`.</span></span>  
  
-   <span data-ttu-id="26836-122">Option de sortie (**-o**) qui spécifie le fichier dans lequel la `sqlcmd` sortie doit être placée.</span><span class="sxs-lookup"><span data-stu-id="26836-122">The output option (**-o**) that specifies the file in which `sqlcmd` is to put its output.</span></span>  
  
## <a name="connecting-to-the-sqlcmd-utility"></a><span data-ttu-id="26836-123">Connexion à l'utilitaire sqlcmd</span><span class="sxs-lookup"><span data-stu-id="26836-123">Connecting to the sqlcmd Utility</span></span>  
 <span data-ttu-id="26836-124">Ci-dessous figurent quelques utilisations courantes de l'utilitaire `sqlcmd` :</span><span class="sxs-lookup"><span data-stu-id="26836-124">The following are common uses of the `sqlcmd` utility:</span></span>  
  
-   <span data-ttu-id="26836-125">Connexion à une instance par défaut à l'aide de l'authentification Windows pour exécuter de manière interactive des instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="26836-125">Connecting to a default instance by using Windows Authentication to interactively run [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    sqlcmd -S <ComputerName>  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="26836-126">Dans l’exemple précédent, **-E** n’est pas spécifié, car il s’agit de la valeur par défaut et `sqlcmd` se connecte à l’instance par défaut à l’aide de l’authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="26836-126">In the previous example, **-E** is not specified because it is the default and `sqlcmd` connects to the default instance by using Windows Authentication.</span></span>  
  
-   <span data-ttu-id="26836-127">Connexion à une instance nommée à l'aide de l'authentification Windows pour exécuter de manière interactive des instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="26836-127">Connecting to a named instance by using Windows Authentication to interactively run [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    sqlcmd -S <ComputerName>\<InstanceName>  
    ```  
  
     <span data-ttu-id="26836-128">or</span><span class="sxs-lookup"><span data-stu-id="26836-128">or</span></span>  
  
    ```  
    sqlcmd -S .\<InstanceName>  
    ```  
  
-   <span data-ttu-id="26836-129">Connexion à une instance nommée en utilisant l'authentification Windows et définition des fichiers d'entrée et de sortie :</span><span class="sxs-lookup"><span data-stu-id="26836-129">Connecting to a named instance by using Windows Authentication and specifying input and output files:</span></span>  
  
    ```  
    sqlcmd -S <ComputerName>\<InstanceName> -i <MyScript.sql> -o <MyOutput.rpt>  
    ```  
  
-   <span data-ttu-id="26836-130">Connexion à l'instance par défaut sur l'ordinateur local à l'aide de l'authentification Windows, exécution d'une requête et maintien de `sqlcmd` actif à la fin de la requête :</span><span class="sxs-lookup"><span data-stu-id="26836-130">Connecting to the default instance on the local computer by using Windows Authentication, executing a query, and having `sqlcmd` remain running after the query has finished running:</span></span>  
  
    ```  
    sqlcmd -q "SELECT * FROM AdventureWorks2012.Person.Person"  
    ```  
  
-   <span data-ttu-id="26836-131">Connexion à l'instance par défaut sur l'ordinateur local à l'aide de l'authentification Windows, exécution d'une requête, envoi de la sortie vers un fichier et fin de l'exécution de `sqlcmd` à la fin de la requête :</span><span class="sxs-lookup"><span data-stu-id="26836-131">Connecting to the default instance on the local computer by using Windows Authentication, executing a query, directing the output to a file, and having `sqlcmd` exit after the query has finished running:</span></span>  
  
    ```  
    sqlcmd -Q "SELECT * FROM AdventureWorks2012.Person.Person" -o MyOutput.txt  
    ```  
  
-   <span data-ttu-id="26836-132">Connexion à une instance nommée à l'aide de l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour exécuter des instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] de manière interactive, avec `sqlcmd` demandant un mot de passe :</span><span class="sxs-lookup"><span data-stu-id="26836-132">Connecting to a named instance using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication to interactively run [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, with `sqlcmd` prompting for a password:</span></span>  
  
    ```  
    sqlcmd -U MyLogin -S <ComputerName>\<InstanceName>  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="26836-133">Pour obtenir une liste des options prises en charge par l'utilitaire `sqlcmd`, exécutez `sqlcmd -?`.</span><span class="sxs-lookup"><span data-stu-id="26836-133">To see a list of the options that are supported by the `sqlcmd` utility run: `sqlcmd -?`.</span></span>  
  
## <a name="running-transact-sql-statements-interactively-by-using-sqlcmd"></a><span data-ttu-id="26836-134">Exécution d'instructions Transact-SQL interactivement à l'aide de sqlcmd</span><span class="sxs-lookup"><span data-stu-id="26836-134">Running Transact-SQL Statements Interactively by Using sqlcmd</span></span>  
 <span data-ttu-id="26836-135">Vous pouvez utiliser l'utilitaire `sqlcmd` interactivement pour exécuter des instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] dans une fenêtre d'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="26836-135">You can use the `sqlcmd` utility interactively to execute [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in a Command Prompt window.</span></span> <span data-ttu-id="26836-136">Pour exécuter interactivement des [!INCLUDE[tsql](../../includes/tsql-md.md)] instructions à l’aide de `sqlcmd` , exécutez l’utilitaire sans utiliser les options **-q**, **-q**, **-Z**ou **-i** pour spécifier des fichiers ou des requêtes d’entrée.</span><span class="sxs-lookup"><span data-stu-id="26836-136">To interactively execute [!INCLUDE[tsql](../../includes/tsql-md.md)] statements by using `sqlcmd`, run the utility without using the **-Q**, **-q**, **-Z**, or **-i** options to specify any input files or queries.</span></span> <span data-ttu-id="26836-137">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="26836-137">For example:</span></span>  
  
 `sqlcmd -S <ComputerName>\<InstanceName>`  
  
 <span data-ttu-id="26836-138">Lorsque la commande est exécutée sans fichiers ou requêtes d'entrée, `sqlcmd` se connecte à l'instance spécifiée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et affiche ensuite une nouvelle ligne comportant un `1>` suivi d'un trait de soulignement clignotant, appelé invite `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="26836-138">When the command is executed without input files or queries, `sqlcmd` connects to the specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and then displays a new line with a `1>` followed by a blinking underscore that is named the `sqlcmd` prompt.</span></span> <span data-ttu-id="26836-139">Le `1` signifie qu'il s'agit de la première ligne d'une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] et l'invite `sqlcmd` représente le point à partir duquel l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] commencera lorsque vous la taperez.</span><span class="sxs-lookup"><span data-stu-id="26836-139">The `1` signifies that this is the first line of a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, and the `sqlcmd` prompt is the point at which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement will start when you type it in.</span></span>  
  
 <span data-ttu-id="26836-140">À l'invite `sqlcmd`, vous pouvez taper à la fois des instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] et des commandes `sqlcmd`, telles que `GO` et `EXIT`.</span><span class="sxs-lookup"><span data-stu-id="26836-140">At the `sqlcmd` prompt, you can type both [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and `sqlcmd` commands, such as `GO` and `EXIT`.</span></span> <span data-ttu-id="26836-141">Chaque instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] est placée dans une mémoire tampon, appelée cache d'instruction.</span><span class="sxs-lookup"><span data-stu-id="26836-141">Each [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is put in a buffer called the statement cache.</span></span> <span data-ttu-id="26836-142">Ces instructions sont envoyées à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dès lors que vous avez tapé la commande `GO` et appuyé sur la touche ENTRÉE.</span><span class="sxs-lookup"><span data-stu-id="26836-142">These statements are sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] after you type the `GO` command and press ENTER.</span></span> <span data-ttu-id="26836-143">Pour quitter `sqlcmd` , tapez `EXIT` ou `QUIT` au début d’une nouvelle ligne.</span><span class="sxs-lookup"><span data-stu-id="26836-143">To exit `sqlcmd`, type `EXIT` or `QUIT` at the start of a new line.</span></span>  
  
 <span data-ttu-id="26836-144">Pour effacer le cache d'instruction, tapez `:RESET`.</span><span class="sxs-lookup"><span data-stu-id="26836-144">To clear the statement cache, type `:RESET`.</span></span> <span data-ttu-id="26836-145">La `^C` frappe `sqlcmd` se termine.</span><span class="sxs-lookup"><span data-stu-id="26836-145">Typing `^C` causes `sqlcmd` to exit.</span></span> <span data-ttu-id="26836-146">`^C` peut également être utilisé pour arrêter l'exécution du cache d'instruction après la saisie d'une commande `GO`.</span><span class="sxs-lookup"><span data-stu-id="26836-146">`^C` can also be used to stop the execution of the statement cache after a `GO` command has been issued.</span></span>  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)]<span data-ttu-id="26836-147">les instructions entrées dans une session interactive peuvent être modifiées en entrant la commande **: Ed** et l' `sqlcmd` invite.</span><span class="sxs-lookup"><span data-stu-id="26836-147">statements that are entered in an interactive session can edited by entering the **:ED** command and the `sqlcmd` prompt.</span></span> <span data-ttu-id="26836-148">L'éditeur s'ouvre et après avoir modifié l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] et refermé l'éditeur, l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] révisée s'affiche dans la fenêtre de commandes.</span><span class="sxs-lookup"><span data-stu-id="26836-148">The editor will open and, after editing the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement and closing the editor, the revised [!INCLUDE[tsql](../../includes/tsql-md.md)] statement will appear in the command window.</span></span> <span data-ttu-id="26836-149">Entrez `GO` pour exécuter l' [!INCLUDE[tsql](../../includes/tsql-md.md)] instruction révisée.</span><span class="sxs-lookup"><span data-stu-id="26836-149">Enter `GO` to run therevised [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
## <a name="quoted-strings"></a><span data-ttu-id="26836-150">Chaînes entre guillemets</span><span class="sxs-lookup"><span data-stu-id="26836-150">Quoted Strings</span></span>  
 <span data-ttu-id="26836-151">Les caractères entourés par des guillemets sont utilisés sans autre prétraitement, à l'exception des guillemets insérés au sein d'une chaîne en entrant deux guillemets consécutifs.</span><span class="sxs-lookup"><span data-stu-id="26836-151">Characters that are enclosed in quotation marks are used without any additional preprocessing, except that quotations marks can be inserted into a string by entering two consecutive quotation marks.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="26836-152">traite cette séquence de caractères comme un seul guillemet.</span><span class="sxs-lookup"><span data-stu-id="26836-152">treats this character sequence as one quotation mark.</span></span> <span data-ttu-id="26836-153">(La traduction s'effectue toutefois sur le serveur). Les variables des scripts ne sont pas développées lorsqu'elles apparaissent au sein d'une chaîne.</span><span class="sxs-lookup"><span data-stu-id="26836-153">(However, the translation occurs in the server.) Scripting variables will not be expanded when they appear within a string.</span></span>  
  
 <span data-ttu-id="26836-154">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="26836-154">For example:</span></span>  
  
 `sqlcmd`  
  
 `PRINT "Length: 5"" 7'";`  
  
 `GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `Length: 5" 7'`  
  
## <a name="strings-that-span-multiple-lines"></a><span data-ttu-id="26836-155">Chaînes qui s'étendent sur plusieurs lignes</span><span class="sxs-lookup"><span data-stu-id="26836-155">Strings That Span Multiple Lines</span></span>  
 <span data-ttu-id="26836-156">`sqlcmd` prend en charge les scripts comportant des chaînes qui s'étendent sur plusieurs lignes.</span><span class="sxs-lookup"><span data-stu-id="26836-156">`sqlcmd` supports scripts that have strings that span multiple lines.</span></span> <span data-ttu-id="26836-157">Par exemple, l'instruction `SELECT` suivante s'étend sur plusieurs lignes mais constitue une seule chaîne exécutée lorsque vous appuyez sur la touche ENTRÉE après avoir tapé `GO`.</span><span class="sxs-lookup"><span data-stu-id="26836-157">For example, the following `SELECT` statement spans multiple lines but is a single string executed when you press the ENTER key after typing `GO`.</span></span>  
  
 `SELECT First line`  
  
 `FROM Second line`  
  
 `WHERE Third line;`  
  
 `GO`  
  
## <a name="interactive-sqlcmd-example"></a><span data-ttu-id="26836-158">Exemple d'utilisation interactive de sqlcmd</span><span class="sxs-lookup"><span data-stu-id="26836-158">Interactive sqlcmd Example</span></span>  
 <span data-ttu-id="26836-159">Il s'agit d'un exemple de ce que vous voyez lorsque vous exécutez `sqlcmd` interactivement.</span><span class="sxs-lookup"><span data-stu-id="26836-159">This is an example of what you see when you run `sqlcmd` interactively.</span></span>  
  
 <span data-ttu-id="26836-160">Lorsque vous ouvrez une fenêtre d'invite de commandes, elle ne comporte qu'une seule ligne similaire à la ligne suivante :</span><span class="sxs-lookup"><span data-stu-id="26836-160">When you open a Command Prompt window, there is one line similar to:</span></span>  
  
 `C:\> _`  
  
 <span data-ttu-id="26836-161">Cela signifie que le dossier `C:\` est le dossier en cours et que si vous spécifiez un nom de fichier, Windows recherchera le fichier dans ce dossier.</span><span class="sxs-lookup"><span data-stu-id="26836-161">This means the folder `C:\` is the current folder, and if you specify a file name, Windows will look for the file in that folder.</span></span>  
  
 <span data-ttu-id="26836-162">Tapez `sqlcmd` pour vous connecter à l'instance par défaut de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] située sur l'ordinateur local. Le contenu de la fenêtre d'invite de commandes sera alors :</span><span class="sxs-lookup"><span data-stu-id="26836-162">Type `sqlcmd` to connect to the default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on the local computer, and the contents of the Command Prompt window will be:</span></span>  
  
 `C:\>sqlcmd`  
  
 `1> _`  
  
 <span data-ttu-id="26836-163">Cela signifie que vous vous êtes connecté à l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et que `sqlcmd` est maintenant prêt à accepter des instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] ainsi que des commandes `sqlcmd` .</span><span class="sxs-lookup"><span data-stu-id="26836-163">This means you have connected to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and `sqlcmd` is now ready to accept [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and `sqlcmd` commands.</span></span> <span data-ttu-id="26836-164">Le trait de soulignement clignotant situé après `1>` est l'invite de `sqlcmd` qui marque l'emplacement où les instructions et les commandes que vous tapez sont affichées.</span><span class="sxs-lookup"><span data-stu-id="26836-164">The flashing underscore after the `1>` is the `sqlcmd` prompt that marks the location at which the statements and commands you type will be displayed.</span></span> <span data-ttu-id="26836-165">À présent, tapez `USE AdventureWorks2012` et appuyez sur entrée, puis tapez `GO` et appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="26836-165">Now, type `USE AdventureWorks2012` and press ENTER, and then type `GO` and press ENTER.</span></span> <span data-ttu-id="26836-166">La fenêtre d'invite de commandes affiche les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="26836-166">The contents of the Command Prompt window will be:</span></span>  
  
 `sqlcmd`  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `Changed database context to 'AdventureWorks2012'.`  
  
 `1> _`  
  
 <span data-ttu-id="26836-167">Appuyer sur la touche ENTRÉE après avoir tapé `USE AdventureWorks2012` correspond à demander à `sqlcmd` de commencer une nouvelle ligne.</span><span class="sxs-lookup"><span data-stu-id="26836-167">Pressing ENTER after entering `USE AdventureWorks2012` signaled `sqlcmd` to start a new line.</span></span> <span data-ttu-id="26836-168">Le fait d'appuyer sur la touche ENTRÉE après avoir tapé `GO,` revient à demander à `sqlcmd` d'envoyer l'instruction `USE AdventureWorks2012` à l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26836-168">Pressing ENTER, after you type `GO,` signaled `sqlcmd` to send the `USE AdventureWorks2012` statement to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="26836-169">`sqlcmd` retourne alors un message pour indiquer que l'instruction `USE` a correctement abouti et affiche une nouvelle invite `1>` qui vous signale que vous pouvez entrer une nouvelle instruction ou une nouvelle commande.</span><span class="sxs-lookup"><span data-stu-id="26836-169">`sqlcmd` then returned a message to indicate that the `USE` statement completed successfully and displayed a new `1>` prompt as a signal to enter a new statement or command.</span></span>  
  
 <span data-ttu-id="26836-170">L'exemple suivant affiche le contenu de la fenêtre d'invite de commandes si vous tapez une instruction `SELECT` , une commande `GO` pour exécuter `SELECT`et une commande `EXIT` pour quitter `sqlcmd`:</span><span class="sxs-lookup"><span data-stu-id="26836-170">The following example shows what the Command Prompt window contains if you type a `SELECT` statement, a `GO` to execute the `SELECT`, and an `EXIT` to exit `sqlcmd`:</span></span>  
  
 `sqlcmd`  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 `SELECT TOP (3) BusinessEntityID, FirstName, LastName`  
  
 `FROM Person.Person;`  
  
 `GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `BusinessEntityID   FirstName                 LastName`  
  
 `----------- -------------------------------- -----------`  
  
 `1           Syed                             Abbas`  
  
 `2           Catherine                        Abel`  
  
 `3           Kim                              Abercrombie`  
  
 `(3 rows affected)`  
  
 `1> EXIT`  
  
 `C:\>`  
  
 <span data-ttu-id="26836-171">Les lignes situées après la ligne `3> GO` sont les données de sortie d'une instruction `SELECT` .</span><span class="sxs-lookup"><span data-stu-id="26836-171">The lines after line `3> GO` are the output of a `SELECT` statement.</span></span> <span data-ttu-id="26836-172">Une fois les données de sortie générées, `sqlcmd` réinitialise l'invite `sqlcmd` et affiche `1>`.</span><span class="sxs-lookup"><span data-stu-id="26836-172">After you generate output, `sqlcmd` resets the `sqlcmd` prompt and displays `1>`.</span></span> <span data-ttu-id="26836-173">Après avoir entré `EXIT` sur la ligne `1>`, la fenêtre d'invite de commandes affiche la même ligne que celle qu'elle a affichée lorsque vous avez ouvert l'invite de commandes la première fois.</span><span class="sxs-lookup"><span data-stu-id="26836-173">After entering `EXIT` at line `1>`, the Command Prompt window displays the same line it did when you first opened it.</span></span> <span data-ttu-id="26836-174">Ceci indique que `sqlcmd` a mis fin à sa session.</span><span class="sxs-lookup"><span data-stu-id="26836-174">This indicates that `sqlcmd` has exited its session.</span></span> <span data-ttu-id="26836-175">Vous pouvez maintenant fermer la fenêtre d'invite de commandes en tapant une autre commande `EXIT` .</span><span class="sxs-lookup"><span data-stu-id="26836-175">You can now close the Command Prompt window by typing another `EXIT` command.</span></span>  
  
## <a name="running-transact-sql-script-files-by-using-sqlcmd"></a><span data-ttu-id="26836-176">Exécution de fichiers de script Transact-SQL à l'aide de sqlcmd</span><span class="sxs-lookup"><span data-stu-id="26836-176">Running Transact-SQL Script Files by Using sqlcmd</span></span>  
 <span data-ttu-id="26836-177">Vous pouvez utiliser `sqlcmd` pour exécuter des fichiers de script de base de données.</span><span class="sxs-lookup"><span data-stu-id="26836-177">You can use `sqlcmd` to execute database script files.</span></span> <span data-ttu-id="26836-178">Les fichiers de script sont des fichiers texte qui contiennent une combinaison d' [!INCLUDE[tsql](../../includes/tsql-md.md)] instructions, de `sqlcmd` commandes et de variables de script.</span><span class="sxs-lookup"><span data-stu-id="26836-178">Script files are text files that contain a mix of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, `sqlcmd` commands, and scripting variables.</span></span> <span data-ttu-id="26836-179">Pour plus d’informations sur la façon de générer un script pour des variables, consultez [Utiliser sqlcmd avec des variables de script](sqlcmd-use-with-scripting-variables.md).</span><span class="sxs-lookup"><span data-stu-id="26836-179">For more information about how to script variables, see [Use sqlcmd with Scripting Variables](sqlcmd-use-with-scripting-variables.md).</span></span> <span data-ttu-id="26836-180">`sqlcmd` fonctionne avec les instructions, les commandes et les variables de script contenues dans un fichier de script de manière très similaire à son fonctionnement avec des instructions et des commandes entrées de manière interactive.</span><span class="sxs-lookup"><span data-stu-id="26836-180">`sqlcmd` works with the statements, commands, and scripting variables in a script file in a manner similar to how it works with statements and commands that are entered interactively.</span></span> <span data-ttu-id="26836-181">La principale différence est que `sqlcmd` lit le fichier d'entrée sans marquer de pause au lieu d'attendre que l'utilisateur entre les instructions, les commandes et les variables de script.</span><span class="sxs-lookup"><span data-stu-id="26836-181">The main difference is that `sqlcmd` reads through the input file without pause instead of waiting for a user to enter the statements, commands, and scripting variables.</span></span>  
  
 <span data-ttu-id="26836-182">Il existe plusieurs manières de créer des fichiers de script de base de données :</span><span class="sxs-lookup"><span data-stu-id="26836-182">There are different ways to create database script files:</span></span>  
  
-   <span data-ttu-id="26836-183">Vous pouvez construire et déboguer de manière interactive un ensemble d'instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], puis enregistrer le contenu de la fenêtre Requête en tant que fichier de script.</span><span class="sxs-lookup"><span data-stu-id="26836-183">You can interactively build and debug a set of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then save the contents of the Query window as a script file.</span></span>  
  
-   <span data-ttu-id="26836-184">Vous pouvez créer un fichier texte contenant des instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] à l'aide d'un éditeur de texte tel que le Bloc-notes.</span><span class="sxs-lookup"><span data-stu-id="26836-184">You can create a text file that contains [!INCLUDE[tsql](../../includes/tsql-md.md)] statements by using a text editor, such as Notepad.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="26836-185">Exemples</span><span class="sxs-lookup"><span data-stu-id="26836-185">Examples</span></span>  
  
### <a name="a-running-a-script-by-using-sqlcmd"></a><span data-ttu-id="26836-186">R.</span><span class="sxs-lookup"><span data-stu-id="26836-186">A.</span></span> <span data-ttu-id="26836-187">Exécution d'un script à l'aide de sqlcmd</span><span class="sxs-lookup"><span data-stu-id="26836-187">Running a script by using sqlcmd</span></span>  
 <span data-ttu-id="26836-188">Démarrez le Bloc-notes et tapez les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] suivantes :</span><span class="sxs-lookup"><span data-stu-id="26836-188">Start Notepad, and type the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 `SELECT TOP (3) BusinessEntityID, FirstName, LastName`  
  
 `FROM Person.Person;`  
  
 `GO`  
  
 <span data-ttu-id="26836-189">Créez un dossier intitulé `MyFolder` puis enregistrez le script sous le fichier `MyScript.sql` dans le dossier `C:\MyFolder`.</span><span class="sxs-lookup"><span data-stu-id="26836-189">Create a folder named `MyFolder` and then save the script as the file `MyScript.sql` in the folder `C:\MyFolder`.</span></span> <span data-ttu-id="26836-190">Entrez les instructions suivantes à l'invite de commandes pour exécuter le script et diriger la sortie dans `MyOutput.txt` dans `MyFolder`:</span><span class="sxs-lookup"><span data-stu-id="26836-190">Enter the following at the command prompt to run the script and put the output in `MyOutput.txt` in `MyFolder`:</span></span>  
  
 `sqlcmd -i C:\MyFolder\MyScript.sql -o C:\MyFolder\MyOutput.txt`  
  
 <span data-ttu-id="26836-191">Lorsque vous affichez le contenu de `MyOutput.txt` dans le Bloc-notes, vous découvrez son contenu :</span><span class="sxs-lookup"><span data-stu-id="26836-191">When you view the contents of `MyOutput.txt` in Notepad, you will see the following:</span></span>  
  
 `Changed database context to 'AdventureWorks2012'.`  
  
 `BusinessEntityID FirstName   LastName`  
  
 `---------------- ----------- -----------`  
  
 `1                Syed        Abbas`  
  
 `2                Catherine   Abel`  
  
 `3                Kim         Abercrombie`  
  
 `(3 rows affected)`  
  
### <a name="b-using-sqlcmd-with-a-dedicated-administrative-connection"></a><span data-ttu-id="26836-192">B.</span><span class="sxs-lookup"><span data-stu-id="26836-192">B.</span></span> <span data-ttu-id="26836-193">Utilisation de sqlcmd avec une connexion d'administration dédiée</span><span class="sxs-lookup"><span data-stu-id="26836-193">Using sqlcmd with a dedicated administrative connection</span></span>  
 <span data-ttu-id="26836-194">Dans l'exemple suivant, `sqlcmd` permet de se connecter à un serveur ayant un problème de blocage à l'aide de la connexion administrateur dédiée.</span><span class="sxs-lookup"><span data-stu-id="26836-194">In the following example, `sqlcmd` is used to connect to a server that has a blocking problem by using the dedicated administrator connection (DAC).</span></span>  
  
 `C:\>sqlcmd -S ServerName -A`  
  
 `1> SELECT blocked FROM sys.dm_exec_requests WHERE blocked <> 0;`  
  
 `2> GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `spid   blocked`  
  
 `------ -------`  
  
 `62       64`  
  
 `(1 rows affected)`  
  
 <span data-ttu-id="26836-195">Utilisez `sqlcmd` pour mettre fin au processus de blocage.</span><span class="sxs-lookup"><span data-stu-id="26836-195">Use `sqlcmd` to end the blocking process.</span></span>  
  
 `1> KILL 64;`  
  
 `2> GO`  
  
### <a name="c-using-sqlcmd-to-execute-a-stored-procedure"></a><span data-ttu-id="26836-196">C.</span><span class="sxs-lookup"><span data-stu-id="26836-196">C.</span></span> <span data-ttu-id="26836-197">Utilisation de sqlcmd pour exécuter une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="26836-197">Using sqlcmd to execute a stored procedure</span></span>  
 <span data-ttu-id="26836-198">L'exemple suivant montre comment exécuter une procédure stockée à l'aide de `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="26836-198">The following example shows how to execute a stored procedure by using `sqlcmd`.</span></span> <span data-ttu-id="26836-199">Créez la procédure stockée suivante.</span><span class="sxs-lookup"><span data-stu-id="26836-199">Create the following stored procedure.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `IF OBJECT_ID ( ' dbo.ContactEmailAddress, 'P' ) IS NOT NULL`  
  
 `DROP PROCEDURE dbo.ContactEmailAddress;`  
  
 `GO`  
  
 `CREATE PROCEDURE dbo.ContactEmailAddress`  
  
 `(`  
  
 `@FirstName nvarchar(50)`  
  
 `,@LastName nvarchar(50)`  
  
 `)`  
  
 `AS`  
  
 `SET NOCOUNT ON`  
  
 `SELECT EmailAddress`  
  
 `FROM Person.Person`  
  
 `WHERE FirstName = @FirstName`  
  
 `AND LastName = @LastName;`  
  
 `SET NOCOUNT OFF`  
  
 <span data-ttu-id="26836-200">À l'invite `sqlcmd` , entrez :</span><span class="sxs-lookup"><span data-stu-id="26836-200">At the `sqlcmd` prompt, enter the following:</span></span>  
  
 `C:\sqlcmd`  
  
 `1> :Setvar FirstName Gustavo`  
  
 `1> :Setvar LastName Achong`  
  
 `1> EXEC dbo.ContactEmailAddress $(Gustavo),$(Achong)`  
  
 `2> GO`  
  
 `EmailAddress`  
  
 `-----------------------------`  
  
 `gustavo0@adventure-works.com`  
  
### <a name="d-using-sqlcmd-for-database-maintenance"></a><span data-ttu-id="26836-201">D.</span><span class="sxs-lookup"><span data-stu-id="26836-201">D.</span></span> <span data-ttu-id="26836-202">Utilisation de sqlcmd pour la maintenance de base de données</span><span class="sxs-lookup"><span data-stu-id="26836-202">Using sqlcmd for database maintenance</span></span>  
 <span data-ttu-id="26836-203">L'exemple suivant montre comment utiliser `sqlcmd` pour une tâche de maintenance de base de données.</span><span class="sxs-lookup"><span data-stu-id="26836-203">The following example shows how to use `sqlcmd` for a database maintenance task.</span></span> <span data-ttu-id="26836-204">Créez `C:\BackupTemplate.sql` à l'aide du code suivant.</span><span class="sxs-lookup"><span data-stu-id="26836-204">Create `C:\BackupTemplate.sql` with the following code.</span></span>  
  
 `USE master;`  
  
 `BACKUP DATABASE [$(db)] TO DISK='$(bakfile)';`  
  
 <span data-ttu-id="26836-205">À l'invite `sqlcmd` , entrez :</span><span class="sxs-lookup"><span data-stu-id="26836-205">At the `sqlcmd` prompt, enter the following:</span></span>  
  
 `C:\ >sqlcmd`  
  
 `1> :connect <server>`  
  
 `Sqlcmd: Successfully connected to server <server>.`  
  
 `1> :setvar db msdb`  
  
 `1> :setvar bakfile c:\msdb.bak`  
  
 `1> :r c:\BackupTemplate.sql`  
  
 `2> GO`  
  
 `Changed database context to 'master'.`  
  
 `Processed 688 pages for database 'msdb', file 'MSDBData' on file 2.`  
  
 `Processed 5 pages for database 'msdb', file 'MSDBLog' on file 2.`  
  
 `BACKUP DATABASE successfully processed 693 pages in 0.725 seconds (7.830 MB/sec)`  
  
### <a name="e-using-sqlcmd-to-execute-code-on-multiple-instances"></a><span data-ttu-id="26836-206">E.</span><span class="sxs-lookup"><span data-stu-id="26836-206">E.</span></span> <span data-ttu-id="26836-207">Utilisation de sqlcmd pour exécuter du code sur plusieurs instances</span><span class="sxs-lookup"><span data-stu-id="26836-207">Using sqlcmd to execute code on multiple instances</span></span>  
 <span data-ttu-id="26836-208">Le code suivant dans un fichier illustre la connexion d'un script à deux instances.</span><span class="sxs-lookup"><span data-stu-id="26836-208">The following code in a file shows a script that connects to two instances.</span></span> <span data-ttu-id="26836-209">Notez `GO` avant la connexion à la deuxième instance.</span><span class="sxs-lookup"><span data-stu-id="26836-209">Notice the `GO` before the connection to the second instance.</span></span>  
  
 `:CONNECT <server>\,<instance1>`  
  
 `EXEC dbo.SomeProcedure`  
  
 `GO`  
  
 `:CONNECT <server>\,<instance2>`  
  
 `EXEC dbo.SomeProcedure`  
  
 `GO`  
  
### <a name="e-returning-xml-output"></a><span data-ttu-id="26836-210">E.</span><span class="sxs-lookup"><span data-stu-id="26836-210">E.</span></span> <span data-ttu-id="26836-211">Retour d'une sortie XML</span><span class="sxs-lookup"><span data-stu-id="26836-211">Returning XML output</span></span>  
 <span data-ttu-id="26836-212">L'exemple suivant montre comment la sortie XML est retournée, sans mise en forme, dans un flux continu.</span><span class="sxs-lookup"><span data-stu-id="26836-212">The following example shows how XML output is returned unformatted, in a continuous stream.</span></span>  
  
 `C:\>sqlcmd -d AdventureWorks2012`  
  
 `1> :XML ON`  
  
 `1> SELECT TOP 3 FirstName + ' ' + LastName + ', '`  
  
 `2> FROM Person.Person`  
  
 `3> GO`  
  
 `Syed Abbas, Catherine Abel, Kim Abercrombie,`  
  
### <a name="f-using-sqlcmd-in-a-windows-script-file"></a><span data-ttu-id="26836-213">F.</span><span class="sxs-lookup"><span data-stu-id="26836-213">F.</span></span> <span data-ttu-id="26836-214">Utilisation de sqlcmd dans un fichier de script Windows</span><span class="sxs-lookup"><span data-stu-id="26836-214">Using sqlcmd in a Windows script file</span></span>  
 <span data-ttu-id="26836-215">Une `sqlcmd` commande telle que `sqlcmd -i C:\InputFile.txt -o C:\OutputFile.txt,` peut être exécutée dans un fichier. bat en même temps que VBScript.</span><span class="sxs-lookup"><span data-stu-id="26836-215">A `sqlcmd`command such as `sqlcmd -i C:\InputFile.txt -o C:\OutputFile.txt,` can be executed in a .bat file together with VBScript.</span></span> <span data-ttu-id="26836-216">Dans ce cas, n'utilisez pas les options interactives.</span><span class="sxs-lookup"><span data-stu-id="26836-216">In this case, do not use interactive options.</span></span> <span data-ttu-id="26836-217">`sqlcmd` doit être installé sur l'ordinateur qui exécute le fichier .bat.</span><span class="sxs-lookup"><span data-stu-id="26836-217">`sqlcmd` must be installed on the computer that is executing the .bat file.</span></span>  
  
 <span data-ttu-id="26836-218">Commencez par créer les quatre fichiers suivants :</span><span class="sxs-lookup"><span data-stu-id="26836-218">First, create the following four files:</span></span>  
  
-   <span data-ttu-id="26836-219">C:\badscript.sql</span><span class="sxs-lookup"><span data-stu-id="26836-219">C:\badscript.sql</span></span>  
  
    ```  
    SELECT batch_1_this_is_an_error  
    GO  
    SELECT 'batch #2'  
    GO  
    ```  
  
-   <span data-ttu-id="26836-220">C:\goodscript.sql</span><span class="sxs-lookup"><span data-stu-id="26836-220">C:\goodscript.sql</span></span>  
  
    ```  
    SELECT 'batch #1'  
    GO  
    SELECT 'batch #2'  
    GO  
    ```  
  
-   <span data-ttu-id="26836-221">C:\returnvalue.sql</span><span class="sxs-lookup"><span data-stu-id="26836-221">C:\returnvalue.sql</span></span>  
  
    ```  
    :exit(select 100)  
    @echo off  
    C:\windowsscript.bat  
    @echo off  
  
    echo Running badscript.sql  
    sqlcmd -i badscript.sql -b -o out.log  
    if not errorlevel 1 goto next1  
    echo == An error occurred   
  
    :next1  
  
    echo Running goodscript.sql  
    sqlcmd -i goodscript.sql -b -o out.log  
    if not errorlevel 1 goto next2  
    echo == An error occurred   
  
    :next2  
    echo Running returnvalue.sql  
    sqlcmd -i returnvalue.sql -o out.log  
    echo SQLCMD returned %errorlevel% to the command shell  
  
    :exit  
    ```  
  
-   <span data-ttu-id="26836-222">C:\windowsscript.bat</span><span class="sxs-lookup"><span data-stu-id="26836-222">C:\windowsscript.bat</span></span>  
  
    ```  
    @echo off  
  
    echo Running badscript.sql  
    sqlcmd -i badscript.sql -b -o out.log  
    if not errorlevel 1 goto next1  
    echo == An error occurred   
  
    :next1  
  
    echo Running goodscript.sql  
    sqlcmd -i goodscript.sql -b -o out.log  
    if not errorlevel 1 goto next2  
    echo == An error occurred   
  
    :next2  
    echo Running returnvalue.sql  
    sqlcmd -i returnvalue.sql -o out.log  
    echo SQLCMD returned %errorlevel% to the command shell  
  
    :exit  
    ```  
  
 <span data-ttu-id="26836-223">Puis, à l'invite de commandes, exécutez `C:\windowsscript.bat`:</span><span class="sxs-lookup"><span data-stu-id="26836-223">Then, at the command prompt, run `C:\windowsscript.bat`:</span></span>  
  
 `C:\>windowsscript.bat`  
  
 `Running badscript.sql`  
  
 `== An error occurred`  
  
 `Running goodscript.sql`  
  
 `Running returnvalue.sql`  
  
 `SQLCMD returned 100 to the command shell`  
  
### <a name="g-using-sqlcmd-to-set-encryption-on-azure-sql-database"></a><span data-ttu-id="26836-224">G.</span><span class="sxs-lookup"><span data-stu-id="26836-224">G.</span></span> <span data-ttu-id="26836-225">Utilisation de sqlcmd pour définir le chiffrement sur Azure SQL Database</span><span class="sxs-lookup"><span data-stu-id="26836-225">Using sqlcmd to set encryption on Azure SQL Database</span></span>  
 <span data-ttu-id="26836-226">Une `sqlcmd` peut être exécutée sur une connexion aux [!INCLUDE[ssSDS](../../includes/sssds-md.md)] données pour spécifier le chiffrement et l’approbation de certificat.</span><span class="sxs-lookup"><span data-stu-id="26836-226">A `sqlcmd`can be executed on a connection to [!INCLUDE[ssSDS](../../includes/sssds-md.md)] data on to specify encryption and certificate trust.</span></span> <span data-ttu-id="26836-227">Deux options « sqlcmd » «» sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="26836-227">Two \`sqlcmd\`\`\`options are available:</span></span>  
  
-   <span data-ttu-id="26836-228">Le commutateur -N est utilisé par le client pour demander une connexion chiffrée.</span><span class="sxs-lookup"><span data-stu-id="26836-228">The -N switch is used by the client to request an encrypted connection.</span></span> <span data-ttu-id="26836-229">Cette option est équivalente à l'option ADO.net `ENCRYPT = true`.</span><span class="sxs-lookup"><span data-stu-id="26836-229">This option is equivalent to the ADO.net option `ENCRYPT = true`.</span></span>  
  
-   <span data-ttu-id="26836-230">Le commutateur -C est utilisé par le client pour le configurer de façon à approuver implicitement le certificat de serveur sans pour autant le valider.</span><span class="sxs-lookup"><span data-stu-id="26836-230">The -C switch is used by the client to configure it to implicitly the trust server certificate and not validate it.</span></span> <span data-ttu-id="26836-231">Cette option est équivalente à l'option ADO.net `TRUSTSERVERCERTIFICATE = true`.</span><span class="sxs-lookup"><span data-stu-id="26836-231">This option is equivalent to the ADO.net option `TRUSTSERVERCERTIFICATE = true`.</span></span>  
  
 <span data-ttu-id="26836-232">Le service [!INCLUDE[ssSDS](../../includes/sssds-md.md)] ne prend pas en charge toutes les options `SET` disponibles sur une instance SQL Server.</span><span class="sxs-lookup"><span data-stu-id="26836-232">The [!INCLUDE[ssSDS](../../includes/sssds-md.md)] service does not support all the `SET` options available on a SQL Server instance.</span></span> <span data-ttu-id="26836-233">Les options suivantes provoquent une erreur lorsque l'option `SET` correspondante est définie sur `ON` ou `OFF`:</span><span class="sxs-lookup"><span data-stu-id="26836-233">The following options throw an error when the corresponding `SET` option is set to `ON` or `OFF`:</span></span>  
  
-   <span data-ttu-id="26836-234">SET ANSI_DEFAULTS</span><span class="sxs-lookup"><span data-stu-id="26836-234">SET ANSI_DEFAULTS</span></span>  
  
-   <span data-ttu-id="26836-235">SET ANSI_NULLS</span><span class="sxs-lookup"><span data-stu-id="26836-235">SET ANSI_NULLS</span></span>  
  
-   <span data-ttu-id="26836-236">SET REMOTE_PROC_TRANSACTIONS</span><span class="sxs-lookup"><span data-stu-id="26836-236">SET REMOTE_PROC_TRANSACTIONS</span></span>  
  
-   <span data-ttu-id="26836-237">SET ANSI_NULL_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="26836-237">SET ANSI_NULL_DEFAULT</span></span>  
  
 <span data-ttu-id="26836-238">Les options SET suivantes ne provoquent pas d'exceptions mais ne peuvent pas être utilisées.</span><span class="sxs-lookup"><span data-stu-id="26836-238">The following SET options do not throw exceptions but cannot be used.</span></span> <span data-ttu-id="26836-239">Elles sont déconseillées :</span><span class="sxs-lookup"><span data-stu-id="26836-239">They are deprecated:</span></span>  
  
-   <span data-ttu-id="26836-240">SET CONCAT_NULL_YIELDS_NULL</span><span class="sxs-lookup"><span data-stu-id="26836-240">SET CONCAT_NULL_YIELDS_NULL</span></span>  
  
-   <span data-ttu-id="26836-241">SET ANSI_PADDING</span><span class="sxs-lookup"><span data-stu-id="26836-241">SET ANSI_PADDING</span></span>  
  
-   <span data-ttu-id="26836-242">SET QUERY_GOVERNOR_COST_LIMIT</span><span class="sxs-lookup"><span data-stu-id="26836-242">SET QUERY_GOVERNOR_COST_LIMIT</span></span>  
  
#### <a name="syntax"></a><span data-ttu-id="26836-243">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="26836-243">Syntax</span></span>  
 <span data-ttu-id="26836-244">Les exemples suivants font référence à des cas où les paramètres du fournisseur Native Client [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] incluent : `ForceProtocolEncryption = False`, `Trust Server Certificate = No`</span><span class="sxs-lookup"><span data-stu-id="26836-244">The following examples refer to cases where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client Provider settings include: `ForceProtocolEncryption = False`, `Trust Server Certificate = No`</span></span>  
  
 <span data-ttu-id="26836-245">Connexion à l'aide des informations d'identification Windows et d'une communication chiffrée :</span><span class="sxs-lookup"><span data-stu-id="26836-245">Connect using Windows credentials and encrypt communication:</span></span>  
  
```  
SQLCMD -E -N  
  
```  
  
 <span data-ttu-id="26836-246">Connexion à l'aide des informations d'identification Windows et d'un certificat de serveur de confiance :</span><span class="sxs-lookup"><span data-stu-id="26836-246">Connect using Windows credentials and trust server certificate:</span></span>  
  
```  
SQLCMD -E -C  
  
```  
  
 <span data-ttu-id="26836-247">Connexion à l'aide des informations d'identification Windows, d'une communication chiffrée et d'un certificat de serveur de confiance :</span><span class="sxs-lookup"><span data-stu-id="26836-247">Connect using Windows credentials, encrypt communication and trust server certificate:</span></span>  
  
```  
SQLCMD -E -N -C  
  
```  
  
 <span data-ttu-id="26836-248">Les exemples suivants font référence à des cas où les paramètres du fournisseur Native Client [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] incluent : `ForceProtocolEncryption = True`, `TrustServerCertificate = Yes`.</span><span class="sxs-lookup"><span data-stu-id="26836-248">The following examples refer to cases where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client Provider settings include: `ForceProtocolEncryption = True`, `TrustServerCertificate = Yes`.</span></span>  
  
 <span data-ttu-id="26836-249">Connexion à l'aide des informations d'identification Windows, d'une communication chiffrée et d'un certificat de serveur de confiance :</span><span class="sxs-lookup"><span data-stu-id="26836-249">Connect using Windows credentials, encrypt communication and trust server certificate:</span></span>  
  
```  
SQLCMD -E  
  
```  
  
 <span data-ttu-id="26836-250">Connexion à l'aide des informations d'identification Windows, d'une communication chiffrée et d'un certificat de serveur de confiance :</span><span class="sxs-lookup"><span data-stu-id="26836-250">Connect using Windows credentials, encrypt communication and trust server certificate:</span></span>  
  
```  
SQLCMD -E -N  
  
```  
  
 <span data-ttu-id="26836-251">Connexion à l'aide des informations d'identification Windows, d'une communication chiffrée et d'un certificat de serveur de confiance :</span><span class="sxs-lookup"><span data-stu-id="26836-251">Connect using Windows credentials, encrypt communication and trust server certificate:</span></span>  
  
```  
SQLCMD -E -T  
  
```  
  
 <span data-ttu-id="26836-252">Connexion à l'aide des informations d'identification Windows, d'une communication chiffrée et d'un certificat de serveur de confiance :</span><span class="sxs-lookup"><span data-stu-id="26836-252">Connect using Windows credentials, encrypt communication and trust server certificate:</span></span>  
  
```  
SQLCMD -E -N -C  
  
```  
  
 <span data-ttu-id="26836-253">Si le fournisseur spécifie `ForceProtocolEncryption = True` , alors le chiffrement est activé même si `Encrypt=No` est indiqué dans la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="26836-253">If the provider specifies `ForceProtocolEncryption = True` then encryption is enabled even if `Encrypt=No` in the connection string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26836-254">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="26836-254">See Also</span></span>  
 <span data-ttu-id="26836-255">[Utilitaire sqlcmd](../../tools/sqlcmd-utility.md) </span><span class="sxs-lookup"><span data-stu-id="26836-255">[sqlcmd Utility](../../tools/sqlcmd-utility.md) </span></span>  
 <span data-ttu-id="26836-256">[Utiliser sqlcmd avec des variables de script](sqlcmd-use-with-scripting-variables.md) </span><span class="sxs-lookup"><span data-stu-id="26836-256">[Use sqlcmd with Scripting Variables](sqlcmd-use-with-scripting-variables.md) </span></span>  
 <span data-ttu-id="26836-257">[Modifier des scripts SQLCMD à l'aide de l'Éditeur de requête](edit-sqlcmd-scripts-with-query-editor.md) </span><span class="sxs-lookup"><span data-stu-id="26836-257">[Edit SQLCMD Scripts with Query Editor](edit-sqlcmd-scripts-with-query-editor.md) </span></span>  
 <span data-ttu-id="26836-258">[Gérer les étapes de travail](../../ssms/agent/manage-job-steps.md) </span><span class="sxs-lookup"><span data-stu-id="26836-258">[Manage Job Steps](../../ssms/agent/manage-job-steps.md) </span></span>  
 [<span data-ttu-id="26836-259">Créer une étape de travail CmdExec</span><span class="sxs-lookup"><span data-stu-id="26836-259">Create a CmdExec Job Step</span></span>](../../ssms/agent/create-a-cmdexec-job-step.md)  
  
  
