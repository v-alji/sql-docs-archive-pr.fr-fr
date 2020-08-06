---
title: Utilitaire osql | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- statements [SQL Server], command prompt
- QUIT command
- Transact-SQL statements, command prompt
- EXIT command
- operating systems [SQL Server], commands
- osql utility [SQL Server]
- stored procedures [SQL Server], command prompt
- scripts [SQL Server], command prompt
- RESET command
- GO command
- command prompt utilities [SQL Server], osql
- CTRL+C command
ms.assetid: cf530d9e-0609-4528-8975-ab8e08e40b9a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 95782afe0de8567781316e3478d04a090f968ed5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694976"
---
# <a name="osql-utility"></a><span data-ttu-id="78084-102">Utilitaire osql</span><span class="sxs-lookup"><span data-stu-id="78084-102">osql Utility</span></span>
  <span data-ttu-id="78084-103">L'utilitaire **osql** permet de spécifier des instructions [!INCLUDE[tsql](../includes/tsql-md.md)] , des procédures système, ainsi que des fichiers de script.</span><span class="sxs-lookup"><span data-stu-id="78084-103">The **osql** utility allows you to enter [!INCLUDE[tsql](../includes/tsql-md.md)] statements, system procedures, and script files.</span></span> <span data-ttu-id="78084-104">Pour communiquer avec le serveur, cet utilitaire fait appel à ODBC.</span><span class="sxs-lookup"><span data-stu-id="78084-104">This utility uses ODBC to communicate with the server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="78084-105">Cette fonctionnalité sera supprimée dans une version future de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78084-105">This feature will be removed in a future version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="78084-106">Évitez de recourir à ce composant dans un nouveau travail de développement et planifiez la modification des applications qui l'utilisent actuellement.</span><span class="sxs-lookup"><span data-stu-id="78084-106">Avoid using this feature in new development work, and plan to modify applications that currently use the feature.</span></span> <span data-ttu-id="78084-107">Utilisez plutôt **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="78084-107">Use **sqlcmd** instead.</span></span> <span data-ttu-id="78084-108">Pour plus d'informations, consultez [sqlcmd Utility](sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="78084-108">For more information, see [sqlcmd Utility](sqlcmd-utility.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78084-109">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="78084-109">Syntax</span></span>  
  
```  
  
      osql  
[-?] |  
[-L] |  
[  
  {  
     {-Ulogin_id [-Ppassword]} | -E }  
     [-Sserver_name[\instance_name]] [-Hwksta_name] [-ddb_name]  
     [-ltime_out] [-ttime_out] [-hheaders]  
     [-scol_separator] [-wcolumn_width] [-apacket_size]  
     [-e] [-I] [-D data_source_name]  
     [-ccmd_end] [-q "query"] [-Q"query"]  
     [-n] [-merror_level] [-r {0 | 1}]  
     [-iinput_file] [-ooutput_file] [-p]  
     [-b] [-u] [-R] [-O]  
]  
```  
  
## <a name="arguments"></a><span data-ttu-id="78084-110">Arguments</span><span class="sxs-lookup"><span data-stu-id="78084-110">Arguments</span></span>  
 <span data-ttu-id="78084-111">**-?**</span><span class="sxs-lookup"><span data-stu-id="78084-111">**-?**</span></span>  
 <span data-ttu-id="78084-112">Affiche un résumé de la syntaxe des commutateurs **osql** .</span><span class="sxs-lookup"><span data-stu-id="78084-112">Displays the syntax summary of **osql** switches.</span></span>  
  
 <span data-ttu-id="78084-113">**-L**</span><span class="sxs-lookup"><span data-stu-id="78084-113">**-L**</span></span>  
 <span data-ttu-id="78084-114">Répertorie tous les serveurs configurés localement et les noms des serveurs émettant sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="78084-114">Lists the locally configured servers and the names of the servers broadcasting on the network.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="78084-115">En raison de la nature de la diffusion sur les réseaux, **osql** risque de ne pas recevoir de réponse de tous les serveurs dans les délais impartis.</span><span class="sxs-lookup"><span data-stu-id="78084-115">Due to the nature of broadcasting on networks, **osql** may not receive a timely response from all servers.</span></span> <span data-ttu-id="78084-116">Par conséquent, la liste des serveurs retournée peut varier à chaque invocation de cette option.</span><span class="sxs-lookup"><span data-stu-id="78084-116">Therefore the list of servers returned may vary for each invocation of this option.</span></span>  
  
 <span data-ttu-id="78084-117">**-U** _login_id_</span><span class="sxs-lookup"><span data-stu-id="78084-117">**-U** _login_id_</span></span>  
 <span data-ttu-id="78084-118">ID de connexion de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="78084-118">Is the user login ID.</span></span> <span data-ttu-id="78084-119">Les ID de connexion respectent la casse.</span><span class="sxs-lookup"><span data-stu-id="78084-119">Login IDs are case-sensitive.</span></span>  
  
 <span data-ttu-id="78084-120">**-P** _password_</span><span class="sxs-lookup"><span data-stu-id="78084-120">**-P** _password_</span></span>  
 <span data-ttu-id="78084-121">Spécifie le mot de passe pour l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="78084-121">Is a user-specified password.</span></span> <span data-ttu-id="78084-122">Si l’option **-P** n’est pas utilisée, **osql** invite à entrer un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="78084-122">If the **-P** option is not used, **osql** prompts for a password.</span></span> <span data-ttu-id="78084-123">Si l’option **-P** est utilisée à la fin de la ligne de commande sans spécifier de mot de passe, **osql** emploie le mot de passe par défaut (NULL).</span><span class="sxs-lookup"><span data-stu-id="78084-123">If the **-P** option is used at the end of the command prompt without any password, **osql** uses the default password (NULL).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="78084-124">N'utilisez pas de mot de passe vide.</span><span class="sxs-lookup"><span data-stu-id="78084-124">Do not use a blank password.</span></span> <span data-ttu-id="78084-125">Utilisez un mot de passe fort.</span><span class="sxs-lookup"><span data-stu-id="78084-125">Use a strong password.</span></span> <span data-ttu-id="78084-126">Pour plus d’informations, consultez [Strong Passwords](../relational-databases/security/strong-passwords.md).</span><span class="sxs-lookup"><span data-stu-id="78084-126">For more information, see [Strong Passwords](../relational-databases/security/strong-passwords.md).</span></span>  
  
 <span data-ttu-id="78084-127">Les mots de passe respectent la casse.</span><span class="sxs-lookup"><span data-stu-id="78084-127">Passwords are case-sensitive.</span></span>  
  
 <span data-ttu-id="78084-128">La variable d'environnement OSQLPASSWORD permet de définir un mot de passe par défaut pour la session en cours.</span><span class="sxs-lookup"><span data-stu-id="78084-128">The OSQLPASSWORD environment variable allows you to set a default password for the current session.</span></span> <span data-ttu-id="78084-129">Par conséquent, il est inutile de programmer spécifiquement le mot de passe dans des fichiers de commandes.</span><span class="sxs-lookup"><span data-stu-id="78084-129">Therefore, you do not have to hard code a password into batch files.</span></span>  
  
 <span data-ttu-id="78084-130">Si vous ne spécifiez pas de mot de passe avec l’option **-P** , **osql** commence par rechercher la variable OSQLPASSWORD.</span><span class="sxs-lookup"><span data-stu-id="78084-130">If you do not specify a password with the **-P** option, **osql** first checks for the OSQLPASSWORD variable.</span></span> <span data-ttu-id="78084-131">Si aucune valeur n'est définie, **osql** utilise le mot de passe par défaut (NULL).</span><span class="sxs-lookup"><span data-stu-id="78084-131">If no value is set, **osql** uses the default password, NULL.</span></span> <span data-ttu-id="78084-132">L'exemple suivant définit la variable OSQLPASSWORD dans une invite de commandes et accède ensuite à l'utilitaire **osql** :</span><span class="sxs-lookup"><span data-stu-id="78084-132">The following example sets the OSQLPASSWORD variable at a command prompt and then accesses the **osql** utility:</span></span>  
  
```  
C:\>SET OSQLPASSWORD=abracadabra  
C:\>osql   
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="78084-133">Pour masquer votre mot de passe, ne spécifiez pas l’option **-P** avec l’option **-U** .</span><span class="sxs-lookup"><span data-stu-id="78084-133">To mask your password, do not specify the **-P** option along with the **-U** option.</span></span> <span data-ttu-id="78084-134">À la place, appuyez sur Entrée après avoir spécifié **osql** avec l’option **-U** et d’autres commutateurs (ne spécifiez pas **-P**). **osql** vous demandera d’entrer un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="78084-134">Instead, after specifying **osql** along with the **-U** option and other switches (do not specify **-P**), press ENTER, and **osql** will prompt you for a password.</span></span> <span data-ttu-id="78084-135">Cette méthode garantit le masquage de votre mot de passe lors de son entrée.</span><span class="sxs-lookup"><span data-stu-id="78084-135">This method ensures that your password will be masked when it is entered.</span></span>  
  
 <span data-ttu-id="78084-136">**-E**</span><span class="sxs-lookup"><span data-stu-id="78084-136">**-E**</span></span>  
 <span data-ttu-id="78084-137">Utilise une connexion approuvée au lieu de demander un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="78084-137">Uses a trusted connection instead of requesting a password.</span></span>  
  
 <span data-ttu-id="78084-138">**-S** _SERVER_NAME_[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="78084-138">**-S** _server_name_[ **\\**_instance_name_]</span></span>  
 <span data-ttu-id="78084-139">Spécifie l'instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] à laquelle établir une connexion.</span><span class="sxs-lookup"><span data-stu-id="78084-139">Specifies the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to connect to.</span></span> <span data-ttu-id="78084-140">Spécifiez *server_name* pour vous connecter à l’instance par défaut du [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] sur ce serveur.</span><span class="sxs-lookup"><span data-stu-id="78084-140">Specify *server_name* to connect to the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="78084-141">Spécifiez _SERVER_NAME_ **\\** _instance_name_ pour vous connecter à une instance nommée de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] sur ce serveur.</span><span class="sxs-lookup"><span data-stu-id="78084-141">Specify _server_name_**\\**_instance_name_ to connect to a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="78084-142">Si aucun serveur n'est spécifié, **osql** se connecte à l'instance par défaut de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] sur l'ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="78084-142">If no server is specified, **osql** connects to the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on the local computer.</span></span> <span data-ttu-id="78084-143">Cette option est indispensable lorsque vous exécutez **osql** à partir d'un ordinateur distant connecté au réseau.</span><span class="sxs-lookup"><span data-stu-id="78084-143">This option is required when executing **osql** from a remote computer on the network.</span></span>  
  
 <span data-ttu-id="78084-144">**-H** _wksta_name_</span><span class="sxs-lookup"><span data-stu-id="78084-144">**-H** _wksta_name_</span></span>  
 <span data-ttu-id="78084-145">Nom d'une station de travail.</span><span class="sxs-lookup"><span data-stu-id="78084-145">Is a workstation name.</span></span> <span data-ttu-id="78084-146">Le nom de la station de travail est stocké dans **sysprocesses.hostname** et est affiché par **sp_who**.</span><span class="sxs-lookup"><span data-stu-id="78084-146">The workstation name is stored in **sysprocesses.hostname** and is displayed by **sp_who**.</span></span> <span data-ttu-id="78084-147">Si cette option n'est pas spécifiée, le nom d'ordinateur en cours est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="78084-147">If this option is not specified, the current computer name is assumed.</span></span>  
  
 <span data-ttu-id="78084-148">**-d** _db_name_</span><span class="sxs-lookup"><span data-stu-id="78084-148">**-d** _db_name_</span></span>  
 <span data-ttu-id="78084-149">Émet une instruction USE *db_name* au démarrage d’ **osql**.</span><span class="sxs-lookup"><span data-stu-id="78084-149">Issues a USE *db_name* statement when **osql**is started.</span></span>  
  
 <span data-ttu-id="78084-150">**-l** _time_out_</span><span class="sxs-lookup"><span data-stu-id="78084-150">**-l** _time_out_</span></span>  
 <span data-ttu-id="78084-151">Spécifie le nombre de secondes avant expiration du délai de connexion à **osql** . Le délai d’attente par défaut pour la connexion à **osql** est de huit secondes.</span><span class="sxs-lookup"><span data-stu-id="78084-151">Specifies the number of seconds before an **osql** login times out. The default time-out for login to **osql** is eight seconds.</span></span>  
  
 <span data-ttu-id="78084-152">**-t** _time_out_</span><span class="sxs-lookup"><span data-stu-id="78084-152">**-t** _time_out_</span></span>  
 <span data-ttu-id="78084-153">Spécifie le nombre de secondes accordées pour l'exécution d'une commande. Si aucune valeur *time_out* n’est spécifiée, les commandes n’ont pas de délai d’expiration.</span><span class="sxs-lookup"><span data-stu-id="78084-153">Specifies the number of seconds before a command times out. If a *time_out* value is not specified, commands do not time out.</span></span>  
  
 <span data-ttu-id="78084-154">**-h** _headers_</span><span class="sxs-lookup"><span data-stu-id="78084-154">**-h** _headers_</span></span>  
 <span data-ttu-id="78084-155">Spécifie le nombre de lignes à imprimer entre les en-têtes de colonne.</span><span class="sxs-lookup"><span data-stu-id="78084-155">Specifies the number of rows to print between column headings.</span></span> <span data-ttu-id="78084-156">Par défaut, les en-têtes ne sont imprimés qu'une fois pour chaque jeu de résultats d'une requête.</span><span class="sxs-lookup"><span data-stu-id="78084-156">The default is to print headings one time for each set of query results.</span></span> <span data-ttu-id="78084-157">Utilisez -1 pour indiquer qu'aucun titre ne sera imprimé.</span><span class="sxs-lookup"><span data-stu-id="78084-157">Use -1 to specify that no headers will be printed.</span></span> <span data-ttu-id="78084-158">Si vous utilisez -1, ne laissez aucun espace entre le paramètre et sa valeur ( **-h-1**, et non **-h -1**).</span><span class="sxs-lookup"><span data-stu-id="78084-158">If -1 is used, there must be no space between the parameter and the setting (**-h-1**, not **-h -1**).</span></span>  
  
 <span data-ttu-id="78084-159">**-s** _col_separator_</span><span class="sxs-lookup"><span data-stu-id="78084-159">**-s** _col_separator_</span></span>  
 <span data-ttu-id="78084-160">Spécification du caractère de séparation des colonnes, qui est par défaut un espace.</span><span class="sxs-lookup"><span data-stu-id="78084-160">Specifies the column-separator character, which is a blank space by default.</span></span> <span data-ttu-id="78084-161">Pour utiliser des caractères qui ont une signification particulière pour le système d’exploitation (par exemple, |; & \< > ), mettez le caractère entre guillemets doubles (").</span><span class="sxs-lookup"><span data-stu-id="78084-161">To use characters that have special meaning to the operating system (for example, | ; & \< >), enclose the character in double quotation marks (").</span></span>  
  
 <span data-ttu-id="78084-162">**-w** _column_width_</span><span class="sxs-lookup"><span data-stu-id="78084-162">**-w** _column_width_</span></span>  
 <span data-ttu-id="78084-163">Permet à l'utilisateur de définir la largeur d'écran des sorties.</span><span class="sxs-lookup"><span data-stu-id="78084-163">Allows the user to set the screen width for output.</span></span> <span data-ttu-id="78084-164">La valeur par défaut est de 80 caractères.</span><span class="sxs-lookup"><span data-stu-id="78084-164">The default is 80 characters.</span></span> <span data-ttu-id="78084-165">Lorsqu'une ligne de sortie a atteint la largeur d'écran maximale, elle est scindée en plusieurs lignes.</span><span class="sxs-lookup"><span data-stu-id="78084-165">When an output line has reached its maximum screen width, it is broken into multiple lines.</span></span>  
  
 <span data-ttu-id="78084-166">**-a** _packet_size_</span><span class="sxs-lookup"><span data-stu-id="78084-166">**-a** _packet_size_</span></span>  
 <span data-ttu-id="78084-167">Spécifie le taille des paquets.</span><span class="sxs-lookup"><span data-stu-id="78084-167">Allows you to request a different-sized packet.</span></span> <span data-ttu-id="78084-168">Les valeurs correctes pour *packet_size* sont comprises entre 512 et 65535.</span><span class="sxs-lookup"><span data-stu-id="78084-168">The valid values for *packet_size* are 512 through 65535.</span></span> <span data-ttu-id="78084-169">La valeur **osql** par défaut est la valeur par défaut du serveur.</span><span class="sxs-lookup"><span data-stu-id="78084-169">The default value **osql** is the server default.</span></span> <span data-ttu-id="78084-170">Une plus grande taille de paquet permet d'améliorer les performances lors de l'exécution de scripts plus volumineux, où la quantité d'instructions SQL entre les commandes GO est substantielle.</span><span class="sxs-lookup"><span data-stu-id="78084-170">Increased packet size can enhance performance on larger script execution where the amount of SQL statements between GO commands is substantial.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="78084-171">indiquent que la valeur 8192 représente généralement le réglage le plus rapide pour les opérations de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="78084-171">testing indicates that 8192 is typically the fastest setting for bulk copy operations.</span></span> <span data-ttu-id="78084-172">Une taille de paquet supérieure peut être demandée, mais **osql** prend la valeur par défaut du serveur si la requête ne peut pas être satisfaite.</span><span class="sxs-lookup"><span data-stu-id="78084-172">A larger packet size can be requested, but **osql** defaults to the server default if the request cannot be granted.</span></span>  
  
 <span data-ttu-id="78084-173">**-e**</span><span class="sxs-lookup"><span data-stu-id="78084-173">**-e**</span></span>  
 <span data-ttu-id="78084-174">Retourne les données d'entrée.</span><span class="sxs-lookup"><span data-stu-id="78084-174">Echoes input.</span></span>  
  
 <span data-ttu-id="78084-175">**-I**</span><span class="sxs-lookup"><span data-stu-id="78084-175">**-I**</span></span>  
 <span data-ttu-id="78084-176">Active l'option de connexion QUOTED_IDENTIFIER.</span><span class="sxs-lookup"><span data-stu-id="78084-176">Sets the QUOTED_IDENTIFIER connection option on.</span></span>  
  
 <span data-ttu-id="78084-177">**-D** _data_source_name_</span><span class="sxs-lookup"><span data-stu-id="78084-177">**-D** _data_source_name_</span></span>  
 <span data-ttu-id="78084-178">Établit la connexion à une source de données ODBC définie à l'aide du pilote ODBC de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78084-178">Connects to an ODBC data source that is defined using the ODBC driver for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="78084-179">La connexion **osql** utilise les options spécifiées dans la source de données.</span><span class="sxs-lookup"><span data-stu-id="78084-179">The **osql** connection uses the options specified in the data source.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="78084-180">Cette option ne fonctionne pas avec les sources de données définies pour les autres pilotes.</span><span class="sxs-lookup"><span data-stu-id="78084-180">This option does not work with data sources defined for other drivers.</span></span>  
  
 <span data-ttu-id="78084-181">**-c** _cmd_end_</span><span class="sxs-lookup"><span data-stu-id="78084-181">**-c** _cmd_end_</span></span>  
 <span data-ttu-id="78084-182">Spécifie l'indicateur de fin de commande.</span><span class="sxs-lookup"><span data-stu-id="78084-182">Specifies the command terminator.</span></span> <span data-ttu-id="78084-183">Par défaut, il faut entrer la commande GO sur une ligne isolée pour terminer une commande et la soumettre à [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="78084-183">By default, commands are terminated and sent to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] by entering GO on a line by itself.</span></span> <span data-ttu-id="78084-184">Si vous changez d'indicateur de fin de commande, n'utilisez ni les mots réservés [!INCLUDE[tsql](../includes/tsql-md.md)] ni les caractères ayant une signification particulière pour le système d'exploitation, qu'ils soient ou non précédés d'une barre oblique inverse</span><span class="sxs-lookup"><span data-stu-id="78084-184">When you reset the command terminator, do not use [!INCLUDE[tsql](../includes/tsql-md.md)] reserved words or characters that have special meaning to the operating system, whether preceded by a backslash or not.</span></span>  
  
 <span data-ttu-id="78084-185">**-q "** _query_ **"**</span><span class="sxs-lookup"><span data-stu-id="78084-185">**-q "** _query_ **"**</span></span>  
 <span data-ttu-id="78084-186">Exécute une requête au démarrage d’ **osql** , mais ne quitte pas **osql** à l’issue de la requête.</span><span class="sxs-lookup"><span data-stu-id="78084-186">Executes a query when **osql** starts, but does not exit **osql** when the query completes.</span></span> <span data-ttu-id="78084-187">(Notez que la requête ne doit pas comporter d'instruction GO).</span><span class="sxs-lookup"><span data-stu-id="78084-187">(Note that the query statement should not include GO).</span></span> <span data-ttu-id="78084-188">Si vous exécutez une requête à partir d'un fichier de commandes, vous pouvez utiliser %variable ou %variable d'environnement%.</span><span class="sxs-lookup"><span data-stu-id="78084-188">If you issue a query from a batch file, use %variables, or environment %variables%.</span></span> <span data-ttu-id="78084-189">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="78084-189">For example:</span></span>  
  
```  
SET table=sys.objects  
osql -E -q "select name, object_id from %table%"  
```  
  
 <span data-ttu-id="78084-190">Placez le nom de la requête entre guillemets doubles et tout élément imbriqué dans la requête entre guillemets simples.</span><span class="sxs-lookup"><span data-stu-id="78084-190">Use double quotation marks around the query and single quotation marks around anything embedded in the query.</span></span>  
  
 <span data-ttu-id="78084-191">**-Q"** _query_ **"**</span><span class="sxs-lookup"><span data-stu-id="78084-191">**-Q"** _query_ **"**</span></span>  
 <span data-ttu-id="78084-192">Exécute une requête, puis quitte immédiatement **osql**.</span><span class="sxs-lookup"><span data-stu-id="78084-192">Executes a query and immediately exits **osql**.</span></span> <span data-ttu-id="78084-193">Placez le nom de la requête entre guillemets doubles et tout élément imbriqué dans la requête entre guillemets simples.</span><span class="sxs-lookup"><span data-stu-id="78084-193">Use double quotation marks around the query and single quotation marks around anything embedded in the query.</span></span>  
  
 <span data-ttu-id="78084-194">**-n**</span><span class="sxs-lookup"><span data-stu-id="78084-194">**-n**</span></span>  
 <span data-ttu-id="78084-195">Supprime la numérotation et le symbole de ligne de commande (>) des lignes d'entrée.</span><span class="sxs-lookup"><span data-stu-id="78084-195">Removes numbering and the prompt symbol (>) from input lines.</span></span>  
  
 <span data-ttu-id="78084-196">**-m** _error_level_</span><span class="sxs-lookup"><span data-stu-id="78084-196">**-m** _error_level_</span></span>  
 <span data-ttu-id="78084-197">Personnalise l'affichage des messages d'erreur.</span><span class="sxs-lookup"><span data-stu-id="78084-197">Customizes the display of error messages.</span></span> <span data-ttu-id="78084-198">Le numéro du message, son état et son niveau d'erreur sont affichés pour les erreurs atteignant ou dépassant le niveau de gravité indiqué.</span><span class="sxs-lookup"><span data-stu-id="78084-198">The message number, state, and error level are displayed for errors of the specified severity level or higher.</span></span> <span data-ttu-id="78084-199">Aucune information n'est affichée pour les erreurs d'une gravité inférieure au niveau indiqué.</span><span class="sxs-lookup"><span data-stu-id="78084-199">Nothing is displayed for errors of levels lower than the specified level.</span></span> <span data-ttu-id="78084-200">Utilisez **-1** pour afficher tous les en-têtes retournés avec les messages, même s’il s’agit de messages d’information.</span><span class="sxs-lookup"><span data-stu-id="78084-200">Use **-1** to specify that all headers are returned with messages, even informational messages.</span></span> <span data-ttu-id="78084-201">Si vous utilisez **-1**, ne laissez aucun espace entre le paramètre et sa valeur ( **-m-1**, et non **-m -1**).</span><span class="sxs-lookup"><span data-stu-id="78084-201">If using **-1**, there must be no space between the parameter and the setting (**-m-1**, not **-m -1**).</span></span>  
  
 <span data-ttu-id="78084-202">**-r** { **0**| **1**}</span><span class="sxs-lookup"><span data-stu-id="78084-202">**-r** { **0**| **1**}</span></span>  
 <span data-ttu-id="78084-203">Redirige la sortie des messages à l’écran (**stderr**).</span><span class="sxs-lookup"><span data-stu-id="78084-203">Redirects message output to the screen (**stderr**).</span></span> <span data-ttu-id="78084-204">Si vous n'indiquez aucun paramètre ou si vous spécifiez la valeur **0**, seuls les messages d'erreur de gravité égale ou supérieure à 11 sont redirigés.</span><span class="sxs-lookup"><span data-stu-id="78084-204">If you do not specify a parameter, or if you specify **0**, only error messages with a severity level 11 or higher are redirected.</span></span> <span data-ttu-id="78084-205">Si vous indiquez la valeur **1**, tous les messages émis (y compris les messages d’impression) sont redirigés.</span><span class="sxs-lookup"><span data-stu-id="78084-205">If you specify **1**, all message output (including "print") is redirected.</span></span>  
  
 <span data-ttu-id="78084-206">**-i** _input_file_</span><span class="sxs-lookup"><span data-stu-id="78084-206">**-i** _input_file_</span></span>  
 <span data-ttu-id="78084-207">Identifie le fichier contenant un traitement d'instructions SQL ou des procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="78084-207">Identifies the file that contains a batch of SQL statements or stored procedures.</span></span> <span data-ttu-id="78084-208">L’opérateur de comparaison inférieur à ( **\<** ) peut être utilisé à la place de **-i**.</span><span class="sxs-lookup"><span data-stu-id="78084-208">The less than (**\<**) comparison operator can be used in place of **-i**.</span></span>  
  
 <span data-ttu-id="78084-209">**-o** _output_file_</span><span class="sxs-lookup"><span data-stu-id="78084-209">**-o** _output_file_</span></span>  
 <span data-ttu-id="78084-210">Identifie le fichier recevant une sortie de **osql**.</span><span class="sxs-lookup"><span data-stu-id="78084-210">Identifies the file that receives output from **osql**.</span></span> <span data-ttu-id="78084-211">L’opérateur de comparaison supérieur à ( **>** ) peut être utilisé à la place de **-o**.</span><span class="sxs-lookup"><span data-stu-id="78084-211">The greater than (**>**) comparison operator can be used in place of **-o**.</span></span>  
  
 <span data-ttu-id="78084-212">Si *input_file* n’est pas au format Unicode et si **-u** n’est pas spécifié, *output_file* est enregistré au format OEM.</span><span class="sxs-lookup"><span data-stu-id="78084-212">If *input_file* is not Unicode and **-u** is not specified, *output_file* is stored in OEM format.</span></span> <span data-ttu-id="78084-213">Si *input_file* est au format Unicode ou si **-u** est spécifié, *output_file* est stocké au format Unicode.</span><span class="sxs-lookup"><span data-stu-id="78084-213">If *input_file* is Unicode or **-u** is specified, *output_file* is stored in Unicode format.</span></span>  
  
 <span data-ttu-id="78084-214">**-p**</span><span class="sxs-lookup"><span data-stu-id="78084-214">**-p**</span></span>  
 <span data-ttu-id="78084-215">Affiche les statistiques sur les performances.</span><span class="sxs-lookup"><span data-stu-id="78084-215">Prints performance statistics.</span></span>  
  
 <span data-ttu-id="78084-216">**-b**</span><span class="sxs-lookup"><span data-stu-id="78084-216">**-b**</span></span>  
 <span data-ttu-id="78084-217">Spécifie que **osql** prend fin et retourne une valeur DOS ERRORLEVEL quand une erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="78084-217">Specifies that **osql** exits and returns a DOS ERRORLEVEL value when an error occurs.</span></span> <span data-ttu-id="78084-218">La valeur retournée à la variable DOS ERRORLEVEL est 1 lorsque le message d'erreur de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] possède une gravité égale ou supérieure à 11, sinon la valeur retournée est 0.</span><span class="sxs-lookup"><span data-stu-id="78084-218">The value returned to the DOS ERRORLEVEL variable is 1 when the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] error message has a severity of 11 or greater; otherwise, the value returned is 0.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="78084-219">Les fichiers de commande MS-DOS peuvent tester la valeur de DOS ERRORLEVEL et traiter l’erreur d’une manière appropriée.</span><span class="sxs-lookup"><span data-stu-id="78084-219">MS-DOS batch files can test the value of DOS ERRORLEVEL and handle the error appropriately.</span></span>  
  
 <span data-ttu-id="78084-220">**-u**</span><span class="sxs-lookup"><span data-stu-id="78084-220">**-u**</span></span>  
 <span data-ttu-id="78084-221">Spécifie qu’ *output_file* est stocké au format Unicode, quel que soit le format d’ *input_file*.</span><span class="sxs-lookup"><span data-stu-id="78084-221">Specifies that *output_file* is stored in Unicode format, regardless of the format of the *input_file*.</span></span>  
  
 <span data-ttu-id="78084-222">**-R**</span><span class="sxs-lookup"><span data-stu-id="78084-222">**-R**</span></span>  
 <span data-ttu-id="78084-223">Spécifie l’utilisation par le pilote ODBC de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] des paramètres du client pour convertir monnaie, date et heure en données caractères.</span><span class="sxs-lookup"><span data-stu-id="78084-223">Specifies that the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ODBC driver use client settings when converting currency, date, and time data to character data.</span></span>  
  
 <span data-ttu-id="78084-224">**-O**</span><span class="sxs-lookup"><span data-stu-id="78084-224">**-O**</span></span>  
 <span data-ttu-id="78084-225">Spécifie que certaines fonctionnalités d’ **osql** sont désactivées pour assurer la continuité avec des versions antérieures d’ **isql**.</span><span class="sxs-lookup"><span data-stu-id="78084-225">Specifies that certain **osql** features be deactivated to match the behavior of earlier versions of **isql**.</span></span> <span data-ttu-id="78084-226">Les fonctionnalités suivantes sont désactivées :</span><span class="sxs-lookup"><span data-stu-id="78084-226">These features are deactivated:</span></span>  
  
-   <span data-ttu-id="78084-227">Traitement de lot EOF</span><span class="sxs-lookup"><span data-stu-id="78084-227">EOF batch processing</span></span>  
  
-   <span data-ttu-id="78084-228">Mise à l'échelle automatique de la largeur de la console</span><span class="sxs-lookup"><span data-stu-id="78084-228">Automatic console width scaling</span></span>  
  
-   <span data-ttu-id="78084-229">Messages larges</span><span class="sxs-lookup"><span data-stu-id="78084-229">Wide messages</span></span>  
  
 <span data-ttu-id="78084-230">Il attribue aussi la valeur par défaut -1 à DOS ERRORLEVEL.</span><span class="sxs-lookup"><span data-stu-id="78084-230">It also sets the default DOS ERRORLEVEL value to -1.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="78084-231">Les options **-n**, **-O** et **-D** ne sont plus prises en charge par **osql**.</span><span class="sxs-lookup"><span data-stu-id="78084-231">The **-n**, **-O** and **-D** options are no longer supported by **osql**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78084-232">Notes</span><span class="sxs-lookup"><span data-stu-id="78084-232">Remarks</span></span>  
 <span data-ttu-id="78084-233">L’utilitaire **osql** doit être exécuté directement à partir du système d’exploitation à l’aide des options respectant la casse énumérées ici.</span><span class="sxs-lookup"><span data-stu-id="78084-233">The **osql** utility is started directly from the operating system with the case-sensitive options listed here.</span></span> <span data-ttu-id="78084-234">Une fois **osql**démarré, il accepte les instructions SQL et les envoie de manière interactive à [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="78084-234">After **osql**starts, it accepts SQL statements and sends them to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] interactively.</span></span> <span data-ttu-id="78084-235">Les résultats sont mis en forme et affichés à l’écran (**stdout**).</span><span class="sxs-lookup"><span data-stu-id="78084-235">The results are formatted and displayed on the screen (**stdout**).</span></span> <span data-ttu-id="78084-236">Pour quitter **osql**, utilisez QUIT ou EXIT.</span><span class="sxs-lookup"><span data-stu-id="78084-236">Use QUIT or EXIT to exit from **osql**.</span></span>  
  
 <span data-ttu-id="78084-237">Si vous ne spécifiez pas de nom d’utilisateur lorsque vous démarrez **osql**, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] vérifie les variables d’environnement et les utilise, par exemple **osqluser = ( *`user`* )** ou **osqlserver = ( *`server`* )**.</span><span class="sxs-lookup"><span data-stu-id="78084-237">If you do not specify a user name when you start **osql**, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] checks for the environment variables and uses those, for example, **osqluser=(*`user`*)** or **osqlserver=(*`server`*)**.</span></span> <span data-ttu-id="78084-238">Si aucune variable d'environnement n'est définie, le nom d'utilisateur du poste de travail est utilisé.</span><span class="sxs-lookup"><span data-stu-id="78084-238">If no environment variables are set, the workstation user name is used.</span></span> <span data-ttu-id="78084-239">Si vous n'indiquez pas de serveur, le nom du poste de travail est utilisé.</span><span class="sxs-lookup"><span data-stu-id="78084-239">If you do not specify a server, the name of the workstation is used.</span></span>  
  
 <span data-ttu-id="78084-240">Si aucune des options **-U** et **-P** n’est utilisée, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tente de se connecter à l’aide du mode d’authentification [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="78084-240">If neither the **-U** or **-P** options are used, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] attempts to connect using [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication Mode.</span></span> <span data-ttu-id="78084-241">L'authentification est basée sur le compte [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows de l'utilisateur exécutant **osql**.</span><span class="sxs-lookup"><span data-stu-id="78084-241">Authentication is based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows account of the user running **osql**.</span></span>  
  
 <span data-ttu-id="78084-242">L'utilitaire **osql** utilise l'API ODBC.</span><span class="sxs-lookup"><span data-stu-id="78084-242">The **osql** utility uses the ODBC API.</span></span> <span data-ttu-id="78084-243">Cet utilitaire emploie les paramètres par défaut du pilote ODBC [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pour les options de connexion ISO de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="78084-243">The utility uses the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ODBC driver default settings for the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ISO connection options.</span></span> <span data-ttu-id="78084-244">Pour plus d'informations, consultez « Effets des options ANSI ».</span><span class="sxs-lookup"><span data-stu-id="78084-244">For more information, see Effects of ANSI Options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="78084-245">L’utilitaire **osql** ne prend pas en charge les types de données CLR définis par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="78084-245">The **osql** utility does not support CLR user-defined data types.</span></span> <span data-ttu-id="78084-246">Pour traiter ces types de données, vous devez employer l'utilitaire **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="78084-246">To process these data types, you must use the **sqlcmd** utility.</span></span> <span data-ttu-id="78084-247">Pour plus d'informations, consultez [sqlcmd Utility](sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="78084-247">For more information, see [sqlcmd Utility](sqlcmd-utility.md).</span></span>  
  
## <a name="osql-commands"></a><span data-ttu-id="78084-248">Commandes OSQL</span><span class="sxs-lookup"><span data-stu-id="78084-248">OSQL Commands</span></span>  
 <span data-ttu-id="78084-249">En plus des instructions [!INCLUDE[tsql](../includes/tsql-md.md)] dans **osql**, les commandes ci-dessous sont également disponibles.</span><span class="sxs-lookup"><span data-stu-id="78084-249">In addition to [!INCLUDE[tsql](../includes/tsql-md.md)] statements within **osql**, these commands are also available.</span></span>  
  
|<span data-ttu-id="78084-250">Commande</span><span class="sxs-lookup"><span data-stu-id="78084-250">Command</span></span>|<span data-ttu-id="78084-251">Description</span><span class="sxs-lookup"><span data-stu-id="78084-251">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="78084-252">GO</span><span class="sxs-lookup"><span data-stu-id="78084-252">GO</span></span>|<span data-ttu-id="78084-253">Exécute toutes les commandes entrées après le dernier GO.</span><span class="sxs-lookup"><span data-stu-id="78084-253">Executes all statements entered after the last GO.</span></span>|  
|<span data-ttu-id="78084-254">RESET</span><span class="sxs-lookup"><span data-stu-id="78084-254">RESET</span></span>|<span data-ttu-id="78084-255">Efface toutes les instructions que vous avez entrées.</span><span class="sxs-lookup"><span data-stu-id="78084-255">Clears any statements you have entered.</span></span>|  
|<span data-ttu-id="78084-256">QUIT ou EXIT( )</span><span class="sxs-lookup"><span data-stu-id="78084-256">QUIT or EXIT( )</span></span>|<span data-ttu-id="78084-257">Quitte **osql**.</span><span class="sxs-lookup"><span data-stu-id="78084-257">Exits from **osql**.</span></span>|  
|<span data-ttu-id="78084-258">CTRL+C</span><span class="sxs-lookup"><span data-stu-id="78084-258">CTRL+C</span></span>|<span data-ttu-id="78084-259">Termine une requête sans quitter **osql**.</span><span class="sxs-lookup"><span data-stu-id="78084-259">Ends a query without exiting from **osql**.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="78084-260">Les commandes</span><span class="sxs-lookup"><span data-stu-id="78084-260">The !!</span></span> <span data-ttu-id="78084-261">!! et ED ne sont plus prises en charge par **osql**.</span><span class="sxs-lookup"><span data-stu-id="78084-261">and ED commands are no longer supported by **osql**.</span></span>  
  
 <span data-ttu-id="78084-262">Les indicateurs de fin de commande, GO (par défaut), RESET EXIT, QUIT et CTRL+C ne sont reconnus que s’ils apparaissent au début d’une ligne immédiatement après l’invite **osql** .</span><span class="sxs-lookup"><span data-stu-id="78084-262">The command terminators GO (by default), RESET EXIT, QUIT, and CTRL+C, are recognized only if they appear at the beginning of a line, immediately following the **osql** prompt.</span></span>  
  
 <span data-ttu-id="78084-263">GO indique la fin d'un traitement et l'exécution des commandes [!INCLUDE[tsql](../includes/tsql-md.md)] placées dans le cache.</span><span class="sxs-lookup"><span data-stu-id="78084-263">GO signals both the end of a batch and the execution of any cached [!INCLUDE[tsql](../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="78084-264">Quand vous appuyez sur ENTRÉE à la fin d'une ligne d'entrée, **osql** place les instructions de cette ligne dans le cache.</span><span class="sxs-lookup"><span data-stu-id="78084-264">When you press ENTER at the end of each input line, **osql** caches the statements on that line.</span></span> <span data-ttu-id="78084-265">Lorsque vous appuyez sur ENTRÉE après avoir tapé GO, toutes les instructions en cache sont envoyées en tant que traitement à [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78084-265">When you press ENTER after typing GO, all of the currently cached statements are sent as a batch to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="78084-266">L'utilitaire **osql** actuel fonctionne comme si une instruction GO implicite terminait chaque script exécuté, de sorte que toutes les instructions du script sont exécutées.</span><span class="sxs-lookup"><span data-stu-id="78084-266">The current **osql** utility works as if there is an implied GO at the end of any script executed, therefore all statements in the script execute.</span></span>  
  
 <span data-ttu-id="78084-267">Pour terminer une commande, tapez une ligne commençant par un indicateur de fin de commande.</span><span class="sxs-lookup"><span data-stu-id="78084-267">End a command by typing a line beginning with a command terminator.</span></span> <span data-ttu-id="78084-268">Vous pouvez faire suivre cet indicateur de fin de commande d'un nombre entier pour indiquer le nombre d'exécutions de la commande.</span><span class="sxs-lookup"><span data-stu-id="78084-268">You can follow the command terminator with an integer to specify how many times the command should be run.</span></span> <span data-ttu-id="78084-269">Par exemple, pour exécuter cette commande 100 fois, entrez :</span><span class="sxs-lookup"><span data-stu-id="78084-269">For example, to execute this command 100 times, type:</span></span>  
  
```  
SELECT x = 1  
GO 100  
```  
  
 <span data-ttu-id="78084-270">Les résultats sont imprimés une fois à la fin de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="78084-270">The results are printed once at the end of execution.</span></span> <span data-ttu-id="78084-271">**osql** n'accepte pas plus de 1 000 caractères par ligne.</span><span class="sxs-lookup"><span data-stu-id="78084-271">**osql** does not accept more than 1,000 characters per line.</span></span> <span data-ttu-id="78084-272">Les instructions de grande taille doivent être scindées en plusieurs lignes.</span><span class="sxs-lookup"><span data-stu-id="78084-272">Large statements should be spread across multiple lines.</span></span>  
  
 <span data-ttu-id="78084-273">La fonction de rappel de commande de Windows peut servir à rappeler et à modifier des instructions **osql** .</span><span class="sxs-lookup"><span data-stu-id="78084-273">The command recall facilities of Windows can be used to recall and modify **osql** statements.</span></span> <span data-ttu-id="78084-274">Le tampon de requête en cours peut être vidé en tapant RESET.</span><span class="sxs-lookup"><span data-stu-id="78084-274">The existing query buffer can be cleared by typing RESET.</span></span>  
  
 <span data-ttu-id="78084-275">Lors de l'exécution de procédures stockées, **osql** imprime une ligne vide entre chaque jeu de résultats d'un lot.</span><span class="sxs-lookup"><span data-stu-id="78084-275">When running stored procedures, **osql** prints a blank line between each set of results in a batch.</span></span> <span data-ttu-id="78084-276">En outre, le message « 0 ligne affectée » ne s'affiche pas lorsqu'il ne concerne pas l'instruction exécutée.</span><span class="sxs-lookup"><span data-stu-id="78084-276">In addition, the "0 rows affected" message does not appear when it does not apply to the statement executed.</span></span>  
  
## <a name="using-osql-interactively"></a><span data-ttu-id="78084-277">Utilisation interactive de osql</span><span class="sxs-lookup"><span data-stu-id="78084-277">Using osql Interactively</span></span>  
 <span data-ttu-id="78084-278">Pour utiliser **osql** en mode interactif, entrez la commande **osql** (et les options désirées) après l’invite de commandes du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="78084-278">To use **osql** interactively, type the **osql** command (and any of the options) at a command prompt.</span></span>  
  
 <span data-ttu-id="78084-279">Vous pouvez exécuter dans **osql** la requête contenue dans un fichier (tel que Stores.qry) en entrant une commande de ce type :</span><span class="sxs-lookup"><span data-stu-id="78084-279">You can read in a file containing a query (such as Stores.qry) for execution by **osql** by typing a command similar to this:</span></span>  
  
```  
osql -E -i stores.qry  
```  
  
 <span data-ttu-id="78084-280">Vous pouvez lire un fichier contenant une requête (tel que Titles.qry) et rediriger les résultats vers un autre fichier en entrant une commande de ce type :</span><span class="sxs-lookup"><span data-stu-id="78084-280">You can read in a file containing a query (such as Titles.qry) and direct the results to another file by typing a command similar to this:</span></span>  
  
```  
osql -E -i titles.qry -o titles.res  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="78084-281">Quand cela est possible, utilisez l’option **-E**(connexion approuvée).</span><span class="sxs-lookup"><span data-stu-id="78084-281">When possible, use the **-E**option (trusted connection).</span></span>  
  
 <span data-ttu-id="78084-282">Quand vous utilisez **osql** de manière interactive, vous pouvez lire un fichier du système d’exploitation dans la mémoire tampon de commande avec **: r**_file_name_.</span><span class="sxs-lookup"><span data-stu-id="78084-282">When using **osql** interactively, you can read an operating-system file into the command buffer with **:r**_file_name_.</span></span> <span data-ttu-id="78084-283">Cette opération adresse le script SQL qui se trouve dans *nom_fichier* directement au serveur en un seul traitement.</span><span class="sxs-lookup"><span data-stu-id="78084-283">This sends the SQL script in *file_name* directly to the server as a single batch.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="78084-284">Quand **osql**est utilisé, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] traite le délimiteur de lot « GO » comme une erreur de syntaxe s’il apparaît dans un fichier de script SQL.</span><span class="sxs-lookup"><span data-stu-id="78084-284">When using **osql**, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] treats the batch separator GO, if it appears in a SQL script file, as a syntax error.</span></span>  
  
## <a name="inserting-comments"></a><span data-ttu-id="78084-285">Insertion de commentaires</span><span class="sxs-lookup"><span data-stu-id="78084-285">Inserting Comments</span></span>  
 <span data-ttu-id="78084-286">Vous pouvez inclure des commentaires dans une instruction Transact-SQL soumise à [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] par **osql**.</span><span class="sxs-lookup"><span data-stu-id="78084-286">You can include comments in a Transact-SQL statement submitted to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] by **osql**.</span></span> <span data-ttu-id="78084-287">Il existe deux syntaxes de commentaires : -- et /\*...\*/.</span><span class="sxs-lookup"><span data-stu-id="78084-287">Two types of commenting styles are allowed: -- and /\*...\*/.</span></span>  
  
## <a name="using-exit-to-return-results-in-osql"></a><span data-ttu-id="78084-288">Utilisation d'EXIT pour retourner des résultats dans osql</span><span class="sxs-lookup"><span data-stu-id="78084-288">Using EXIT to Return Results in osql</span></span>  
 <span data-ttu-id="78084-289">Vous pouvez utiliser le résultat d'une instruction SELECT comme valeur retournée par **osql**.</span><span class="sxs-lookup"><span data-stu-id="78084-289">You can use the result of a SELECT statement as the return value from **osql**.</span></span> <span data-ttu-id="78084-290">S'il est numérique, la dernière colonne de la dernière ligne de résultats est convertie en entier de 4 octets (entier long).</span><span class="sxs-lookup"><span data-stu-id="78084-290">If it is numeric, the last column of the last result row is converted to a 4-byte integer (long).</span></span> <span data-ttu-id="78084-291">MS-DOS transmet l'octet de poids faible au processus parent ou au niveau erreur du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="78084-291">MS-DOS passes the low byte to the parent process or operating system error level.</span></span> <span data-ttu-id="78084-292">Windows transmet la totalité de l'entier de 4 octets.</span><span class="sxs-lookup"><span data-stu-id="78084-292">Windows passes the entire 4-byte integer.</span></span> <span data-ttu-id="78084-293">La syntaxe est :</span><span class="sxs-lookup"><span data-stu-id="78084-293">The syntax is:</span></span>  
  
```  
EXIT ( < query > )  
```  
  
 <span data-ttu-id="78084-294">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="78084-294">For example:</span></span>  
  
```  
EXIT(SELECT @@ROWCOUNT)  
```  
  
 <span data-ttu-id="78084-295">Vous pouvez également inclure le paramètre EXIT dans un fichier de commandes.</span><span class="sxs-lookup"><span data-stu-id="78084-295">You can also include the EXIT parameter as part of a batch file.</span></span> <span data-ttu-id="78084-296">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="78084-296">For example:</span></span>  
  
```  
osql -E -Q "EXIT(SELECT COUNT(*) FROM '%1')"  
```  
  
 <span data-ttu-id="78084-297">L’utilitaire **osql** transmet au serveur toutes les informations placées entre parenthèses **()** telles qu’elles ont été entrées.</span><span class="sxs-lookup"><span data-stu-id="78084-297">The **osql** utility passes everything between the parentheses **()** to the server exactly as entered.</span></span> <span data-ttu-id="78084-298">Si une procédure système stockée sélectionne un ensemble et retourne une valeur, seule la sélection est retournée.</span><span class="sxs-lookup"><span data-stu-id="78084-298">If a stored system procedure selects a set and returns a value, only the selection is returned.</span></span> <span data-ttu-id="78084-299">L’instruction **()** sans information entre parenthèses exécute toutes les commandes qui la précèdent dans le traitement, puis quitte l’utilitaire sans retourner de valeur.</span><span class="sxs-lookup"><span data-stu-id="78084-299">The EXIT **()** statement with nothing between the parentheses executes everything preceding it in the batch and then exits with no return value.</span></span>  
  
 <span data-ttu-id="78084-300">Il existe quatre formats de sortie :</span><span class="sxs-lookup"><span data-stu-id="78084-300">There are four EXIT formats:</span></span>  
  
-   <span data-ttu-id="78084-301">EXIT</span><span class="sxs-lookup"><span data-stu-id="78084-301">EXIT</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="78084-302">N'exécute pas le traitement ; ferme immédiatement l'utilitaire et ne retourne aucune valeur.</span><span class="sxs-lookup"><span data-stu-id="78084-302">Does not execute the batch; quits immediately and returns no value.</span></span>  
  
-   <span data-ttu-id="78084-303">EXIT **()**</span><span class="sxs-lookup"><span data-stu-id="78084-303">EXIT **()**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="78084-304">Exécute le traitement, puis quitte sans retourner de valeur.</span><span class="sxs-lookup"><span data-stu-id="78084-304">Executes the batch, and then quits and returns no value.</span></span>  
  
-   <span data-ttu-id="78084-305">QUITTER **( *`query`* )**</span><span class="sxs-lookup"><span data-stu-id="78084-305">EXIT **(*`query`*)**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="78084-306">Exécute le traitement, y compris la requête, puis quitte en retournant les résultats de la requête.</span><span class="sxs-lookup"><span data-stu-id="78084-306">Executes the batch, including the query, and then quits after returning the results of the query.</span></span>  
  
-   <span data-ttu-id="78084-307">RAISERROR avec une gravité de 127</span><span class="sxs-lookup"><span data-stu-id="78084-307">RAISERROR with a state of 127</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="78084-308">Si RAISERROR est utilisé dans un script **osql** et qu'une erreur de gravité 127 se produit, l'exécution d’ **osql** se termine et l'ID du message est retourné au client.</span><span class="sxs-lookup"><span data-stu-id="78084-308">If RAISERROR is used within an **osql** script and a state of 127 is raised, **osql** will quit and return the message ID back to the client.</span></span> <span data-ttu-id="78084-309">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="78084-309">For example:</span></span>  
  
```  
RAISERROR(50001, 10, 127)  
```  
  
 <span data-ttu-id="78084-310">Cette erreur entraîne l'arrêt de l'exécution du script **osql** et envoie le message 50001 au client.</span><span class="sxs-lookup"><span data-stu-id="78084-310">This error will cause the **osql** script to end and the message ID 50001 will be returned to the client.</span></span>  
  
 <span data-ttu-id="78084-311">Les valeurs retournées comprises entre -1 et -99 sont réservées à [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. **osql** définit les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="78084-311">The return values -1 to -99 are reserved by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]; **osql** defines these values:</span></span>  
  
-   <span data-ttu-id="78084-312">-100</span><span class="sxs-lookup"><span data-stu-id="78084-312">-100</span></span>  
  
     <span data-ttu-id="78084-313">Erreur rencontrée avant la sélection d'une valeur retournée.</span><span class="sxs-lookup"><span data-stu-id="78084-313">Error encountered prior to selecting return value.</span></span>  
  
-   <span data-ttu-id="78084-314">-101</span><span class="sxs-lookup"><span data-stu-id="78084-314">-101</span></span>  
  
     <span data-ttu-id="78084-315">Aucune ligne trouvée lors de la sélection d'une valeur retournée.</span><span class="sxs-lookup"><span data-stu-id="78084-315">No rows found when selecting return value.</span></span>  
  
-   <span data-ttu-id="78084-316">-102</span><span class="sxs-lookup"><span data-stu-id="78084-316">-102</span></span>  
  
     <span data-ttu-id="78084-317">Erreur de conversion survenue lors de la sélection d'une valeur retournée.</span><span class="sxs-lookup"><span data-stu-id="78084-317">Conversion error occurred when selecting return value.</span></span>  
  
## <a name="displaying-money-and-smallmoney-data-types"></a><span data-ttu-id="78084-318">Affichage des types de données money et smallmoney</span><span class="sxs-lookup"><span data-stu-id="78084-318">Displaying money and smallmoney Data Types</span></span>  
 <span data-ttu-id="78084-319">**osql** affiche les `money` types de données et avec deux décimales, `smallmoney` bien que [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] stocke la valeur en interne avec quatre décimales.</span><span class="sxs-lookup"><span data-stu-id="78084-319">**osql** displays the `money` and `smallmoney` data types with two decimal places although [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] stores the value internally with four decimal places.</span></span> <span data-ttu-id="78084-320">Prenons cet exemple :</span><span class="sxs-lookup"><span data-stu-id="78084-320">Consider the example:</span></span>  
  
```  
SELECT CAST(CAST(10.3496 AS money) AS decimal(6, 4))  
GO  
```  
  
 <span data-ttu-id="78084-321">Cette instruction produit le résultat `10.3496`, ce qui indique que la valeur est bien stockée avec toutes ses décimales.</span><span class="sxs-lookup"><span data-stu-id="78084-321">This statement produces a result of `10.3496`, which indicates that the value is stored with all decimal places intact.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78084-322">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="78084-322">See Also</span></span>  
 <span data-ttu-id="78084-323">[Commentaire &#40;MDX&#41;](/sql/mdx/comment-mdx) </span><span class="sxs-lookup"><span data-stu-id="78084-323">[Comment &#40;MDX&#41;](/sql/mdx/comment-mdx) </span></span>  
 <span data-ttu-id="78084-324">[-- &#40;Comment&#41; &#40;MDX&#41;](/sql/mdx/comment-mdx) </span><span class="sxs-lookup"><span data-stu-id="78084-324">[-- &#40;Comment&#41; &#40;MDX&#41;](/sql/mdx/comment-mdx) </span></span>  
 <span data-ttu-id="78084-325">[CAST et CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="78084-325">[CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql) </span></span>  
 [<span data-ttu-id="78084-326">RAISERROR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="78084-326">RAISERROR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/raiserror-transact-sql)  
  
  
