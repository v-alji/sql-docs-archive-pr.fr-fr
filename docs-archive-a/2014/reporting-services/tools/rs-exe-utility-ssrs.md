---
title: Utilitaire RS.exe (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- automatic report server tasks
- rs utility
- command prompt utilities [Reporting Services]
- report servers [Reporting Services], automating tasks
- command prompt utilities [SQL Server], rs
- scripts [Reporting Services], command prompt
- deploying reports [Reporting Services]
ms.assetid: bd6f958f-cce6-4e79-8a0f-9475da2919ce
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bcf21a1bf2453d2bd1f0644e31ca46f3f94e6884
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704824"
---
# <a name="rsexe-utility-ssrs"></a><span data-ttu-id="b0112-102">Utilitaire RS.exe (SSRS)</span><span class="sxs-lookup"><span data-stu-id="b0112-102">RS.exe Utility (SSRS)</span></span>
  <span data-ttu-id="b0112-103">L'utilitaire rs.exe traite le script que vous fournissez dans un fichier d'entrée.</span><span class="sxs-lookup"><span data-stu-id="b0112-103">The rs.exe utility processes script that you provide in an input file.</span></span> <span data-ttu-id="b0112-104">Utilisez cet utilitaire pour automatiser les tâches de déploiement et d'administration du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="b0112-104">Use this utility to automate report server deployment and administration tasks.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b0112-105">Depuis [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], l’utilitaire **rs** est pris en charge sur les serveurs de rapports configurés pour le mode intégré SharePoint ainsi que sur les serveurs configurés en mode natif.</span><span class="sxs-lookup"><span data-stu-id="b0112-105">Beginning with [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], the **rs** utility is supported against report servers that are configured for SharePoint integrated mode as well as servers configured in native mode.</span></span> <span data-ttu-id="b0112-106">Les versions antérieures ne prenaient en charge que les configurations en mode natif.</span><span class="sxs-lookup"><span data-stu-id="b0112-106">Previous versions only supported native mode configurations.</span></span>  
  
 <span data-ttu-id="b0112-107">**Dans cette rubrique :**</span><span class="sxs-lookup"><span data-stu-id="b0112-107">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="b0112-108">Emplacement du fichier</span><span class="sxs-lookup"><span data-stu-id="b0112-108">File Location</span></span>](#bkmk_filelocation)  
  
-   [<span data-ttu-id="b0112-109">Arguments</span><span class="sxs-lookup"><span data-stu-id="b0112-109">Arguments</span></span>](#bkmk_arguments)  
  
-   [<span data-ttu-id="b0112-110">autorisations</span><span class="sxs-lookup"><span data-stu-id="b0112-110">Permissions</span></span>](#bkmk_permissions)  
  
-   [<span data-ttu-id="b0112-111">Exemples</span><span class="sxs-lookup"><span data-stu-id="b0112-111">Examples</span></span>](#bkmk_examples)  
  
## <a name="syntax"></a><span data-ttu-id="b0112-112">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b0112-112">Syntax</span></span>  
  
```  
  
      rs {-?}  
{-i input_file=}  
{-s serverURL}  
{-u username}  
{-p password}  
{-e endpoint}  
{-l time_out}  
{-b batchmode}  
{-v globalvars=}  
{-t trace}  
```  
  
##  <a name="file-location"></a><a name="bkmk_filelocation"></a> <span data-ttu-id="b0112-113">Emplacement du fichier</span><span class="sxs-lookup"><span data-stu-id="b0112-113">File Location</span></span>  
 <span data-ttu-id="b0112-114">**RS.exe** se trouve à l’emplacement **\Program Files\Microsoft SQL Server\110\Tools\Binn**.</span><span class="sxs-lookup"><span data-stu-id="b0112-114">**RS.exe** is located at **\Program Files\Microsoft SQL Server\110\Tools\Binn**.</span></span> <span data-ttu-id="b0112-115">Vous pouvez exécuter l'utilitaire à partir de n'importe quel dossier de votre système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="b0112-115">You can run the utility from any folder on your file system.</span></span>  
  
##  <a name="arguments"></a><a name="bkmk_arguments"></a> <span data-ttu-id="b0112-116">Arguments</span><span class="sxs-lookup"><span data-stu-id="b0112-116">Arguments</span></span>  
 <span data-ttu-id="b0112-117">**-?**</span><span class="sxs-lookup"><span data-stu-id="b0112-117">**-?**</span></span>  
 <span data-ttu-id="b0112-118">(Facultatif) Affiche la syntaxe des arguments de **rs** .</span><span class="sxs-lookup"><span data-stu-id="b0112-118">(Optional) Displays the syntax of **rs** arguments.</span></span>  
  
 <span data-ttu-id="b0112-119">`-i`*input_file*</span><span class="sxs-lookup"><span data-stu-id="b0112-119">`-i` *input_file*</span></span>  
 <span data-ttu-id="b0112-120">(Obligatoire) Spécifie le fichier .rss à exécuter.</span><span class="sxs-lookup"><span data-stu-id="b0112-120">(Required) Specifies the .rss file to execute.</span></span> <span data-ttu-id="b0112-121">Cette valeur peut être un chemin d'accès relatif ou totalement défini au fichier .rss.</span><span class="sxs-lookup"><span data-stu-id="b0112-121">This value can be a relative or fully qualified path to the .rss file.</span></span>  
  
 <span data-ttu-id="b0112-122">`-s`*ServerURL*</span><span class="sxs-lookup"><span data-stu-id="b0112-122">`-s` *serverURL*</span></span>  
 <span data-ttu-id="b0112-123">(Obligatoire) Spécifie les noms du serveur Web et du répertoire virtuel du serveur de rapports auxquels s'applique le fichier à exécuter.</span><span class="sxs-lookup"><span data-stu-id="b0112-123">(Required) Specifies the Web server name and report server virtual directory name to execute the file against.</span></span> <span data-ttu-id="b0112-124">L'URL du serveur de rapports pourrait être par exemple `http://examplewebserver/reportserver`.</span><span class="sxs-lookup"><span data-stu-id="b0112-124">An example of a report server URL is `http://examplewebserver/reportserver`.</span></span> <span data-ttu-id="b0112-125">Le préfixe http:// ou https:// placé au début du nom du serveur est facultatif.</span><span class="sxs-lookup"><span data-stu-id="b0112-125">The prefix http:// or https:// at the beginning of the server name is optional.</span></span> <span data-ttu-id="b0112-126">Si vous omettez le préfixe, l'environnement d'exécution de scripts du serveur de rapports tente en premier lieu d'utiliser https et, si cela ne fonctionne pas, il essaie avec http.</span><span class="sxs-lookup"><span data-stu-id="b0112-126">If you omit the prefix, the report server script host tries to use https first, and then uses http if https does not work.</span></span>  
  
 <span data-ttu-id="b0112-127">`-u`[*domaine* \\ ] *nom d’utilisateur*</span><span class="sxs-lookup"><span data-stu-id="b0112-127">`-u` [*domain*\\]*username*</span></span>  
 <span data-ttu-id="b0112-128">(Facultatif) Spécifie un compte d'utilisateur utilisé pour se connecter au serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="b0112-128">(Optional) Specifies a user account used to connect to the report server.</span></span> <span data-ttu-id="b0112-129">Si `-u` et `-p` sont absents, le compte d'utilisateur Windows actuel est utilisé.</span><span class="sxs-lookup"><span data-stu-id="b0112-129">If `-u` and `-p` are omitted, the current Windows user account is used.</span></span>  
  
 <span data-ttu-id="b0112-130">`-p` *mot de passe*</span><span class="sxs-lookup"><span data-stu-id="b0112-130">`-p` *password*</span></span>  
 <span data-ttu-id="b0112-131">(Obligatoire si `-u` est spécifié) Spécifie le mot de passe à utiliser avec l'argument `-u`.</span><span class="sxs-lookup"><span data-stu-id="b0112-131">(Required if `-u` is specified) Specifies the password to use with the `-u` argument.</span></span> <span data-ttu-id="b0112-132">Cette valeur respecte la casse.</span><span class="sxs-lookup"><span data-stu-id="b0112-132">This value is case-sensitive.</span></span>  
  
 `-e`  
 <span data-ttu-id="b0112-133">(Facultatif) Spécifie le point de terminaison SOAP sur lequel le script devrait s'exécuter.</span><span class="sxs-lookup"><span data-stu-id="b0112-133">(Optional) Specifies the SOAP endpoint against which the script should run.</span></span> <span data-ttu-id="b0112-134">Les valeurs suivantes sont valides :</span><span class="sxs-lookup"><span data-stu-id="b0112-134">Valid values are the following:</span></span>  
  
-   <span data-ttu-id="b0112-135">Mgmt2010</span><span class="sxs-lookup"><span data-stu-id="b0112-135">Mgmt2010</span></span>  
  
-   <span data-ttu-id="b0112-136">Mgmt2006</span><span class="sxs-lookup"><span data-stu-id="b0112-136">Mgmt2006</span></span>  
  
-   <span data-ttu-id="b0112-137">Mgmt2005</span><span class="sxs-lookup"><span data-stu-id="b0112-137">Mgmt2005</span></span>  
  
-   <span data-ttu-id="b0112-138">Exec2005</span><span class="sxs-lookup"><span data-stu-id="b0112-138">Exec2005</span></span>  
  
 <span data-ttu-id="b0112-139">Si une valeur n'est pas spécifiée, le point de terminaison Mgmt2005 est utilisé.</span><span class="sxs-lookup"><span data-stu-id="b0112-139">If a value is not specified, the Mgmt2005 endpoint is used.</span></span> <span data-ttu-id="b0112-140">Pour plus d'informations sur les points de terminaison SOAP, consultez [Report Server Web Service Endpoints](../report-server-web-service/methods/report-server-web-service-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="b0112-140">For more information about the SOAP endpoints, see [Report Server Web Service Endpoints](../report-server-web-service/methods/report-server-web-service-endpoints.md).</span></span>  
  
 <span data-ttu-id="b0112-141">`-l`*time_out*</span><span class="sxs-lookup"><span data-stu-id="b0112-141">`-l` *time_out*</span></span>  
 <span data-ttu-id="b0112-142">Facultatif Spécifie le nombre de secondes qui s’écoulent avant l’expiration de la connexion au serveur. La valeur par défaut est 60 secondes.</span><span class="sxs-lookup"><span data-stu-id="b0112-142">(Optional) Specifies the number of seconds that elapse before the connection to the server times out. The default is 60 seconds.</span></span> <span data-ttu-id="b0112-143">Si vous ne spécifiez pas de délai d'expiration, la valeur par défaut est utilisée.</span><span class="sxs-lookup"><span data-stu-id="b0112-143">If you do not specify a time-out value, the default is used.</span></span> <span data-ttu-id="b0112-144">La valeur `0` indique que la connexion n'arrive jamais à expiration.</span><span class="sxs-lookup"><span data-stu-id="b0112-144">A value of `0` specifies that the connection never times out.</span></span>  
  
 <span data-ttu-id="b0112-145">**-b**</span><span class="sxs-lookup"><span data-stu-id="b0112-145">**-b**</span></span>  
 <span data-ttu-id="b0112-146">(Facultatif) Spécifie que les commandes du fichier script s'exécutent dans un lot.</span><span class="sxs-lookup"><span data-stu-id="b0112-146">(Optional) Specifies that the commands in the script file run in a batch.</span></span> <span data-ttu-id="b0112-147">En cas d'échec d'une commande, l'ensemble du lot est annulé.</span><span class="sxs-lookup"><span data-stu-id="b0112-147">If any commands fail, the batch is rolled back.</span></span> <span data-ttu-id="b0112-148">Certaines commandes ne peuvent pas être traitées par lot ; leur exécution se déroule normalement.</span><span class="sxs-lookup"><span data-stu-id="b0112-148">Some commands cannot be batched, and those run as usual.</span></span> <span data-ttu-id="b0112-149">Seules les exceptions générées qui ne sont pas gérées par le code du script entraînent une annulation.</span><span class="sxs-lookup"><span data-stu-id="b0112-149">Only exceptions that are thrown and are not handled within the script result in a rollback.</span></span> <span data-ttu-id="b0112-150">Si le script gère une exception et si l'exécution se poursuit normalement à partir de `Main`, le traitement est validé.</span><span class="sxs-lookup"><span data-stu-id="b0112-150">If the script handles an exception and returns normally from `Main`, the batch is committed.</span></span> <span data-ttu-id="b0112-151">Si vous omettez ce paramètre, les commandes s'exécutent sans créer de lot.</span><span class="sxs-lookup"><span data-stu-id="b0112-151">If you omit this parameter, the commands run without creating a batch.</span></span> <span data-ttu-id="b0112-152">Pour plus d’informations, voir [Batching Methods](../report-server-web-service-net-framework-soap-headers/batching-methods.md).</span><span class="sxs-lookup"><span data-stu-id="b0112-152">For more information, see [Batching Methods](../report-server-web-service-net-framework-soap-headers/batching-methods.md).</span></span>  
  
 <span data-ttu-id="b0112-153">`-v`*GlobalVar (*</span><span class="sxs-lookup"><span data-stu-id="b0112-153">`-v` *globalvar*</span></span>  
 <span data-ttu-id="b0112-154">(Facultatif) Spécifie les variables globales utilisées dans le script.</span><span class="sxs-lookup"><span data-stu-id="b0112-154">(Optional) Specifies global variables that are used in the script.</span></span> <span data-ttu-id="b0112-155">Si le script utilise des variables globales, vous devez spécifier cet argument.</span><span class="sxs-lookup"><span data-stu-id="b0112-155">If the script uses global variables, you must specify this argument.</span></span> <span data-ttu-id="b0112-156">La valeur que vous spécifiez doit être une valeur correcte définie dans le fichier .rss pour les variables globales.</span><span class="sxs-lookup"><span data-stu-id="b0112-156">The value that you specify must be valid for global variable defined in the .rss file.</span></span> <span data-ttu-id="b0112-157">Vous devez spécifier une variable globale pour chaque argument **-v** .</span><span class="sxs-lookup"><span data-stu-id="b0112-157">You must specify one global variable for each **-v** argument.</span></span>  
  
 <span data-ttu-id="b0112-158">L'argument `-v` est spécifié sur la ligne de commande et est utilisé pour configurer la valeur pour une variable globale définie dans votre script au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="b0112-158">The `-v` argument is specified on the command line and is used to set the value for a global variable that is defined in your script at run time.</span></span> <span data-ttu-id="b0112-159">Par exemple, si votre script contient une variable nommée *parentFolder*, vous pouvez spécifier un nom pour ce dossier sur la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="b0112-159">For example, if your script contains a variable named *parentFolder*, you can specify a name for that folder on the command line:</span></span>  
  
 `rs.exe -i myScriptFile.rss -s http://myServer/reportserver -v parentFolder="Financial Reports"`  
  
 <span data-ttu-id="b0112-160">Les variables globales sont créées avec les noms donnés et prennent les valeurs fournies.</span><span class="sxs-lookup"><span data-stu-id="b0112-160">Global variables are created with the names given and set to the values supplied.</span></span> <span data-ttu-id="b0112-161">Par exemple, **-v a =**" `1` " **-v b =**" `2` " produit une variable nommée `a` avec une valeur de " `1` " et une variable **b** avec la valeur " `2` ".</span><span class="sxs-lookup"><span data-stu-id="b0112-161">For example, **-v a=**"`1`" **-v b=**"`2`" results in a variable named `a` with a value of"`1`" and a variable **b** with a value of "`2`".</span></span>  
  
 <span data-ttu-id="b0112-162">Les variables globales sont accessibles à n'importe quelle fonction du script.</span><span class="sxs-lookup"><span data-stu-id="b0112-162">Global variables are available to any function in the script.</span></span> <span data-ttu-id="b0112-163">Une barre oblique inverse et un guillemet (\*\* \\ "\*\*) sont interprétés comme des guillemets doubles.</span><span class="sxs-lookup"><span data-stu-id="b0112-163">A backslash and quotation mark (**\\"**) is interpreted as a double quotation mark.</span></span> <span data-ttu-id="b0112-164">Les guillemets sont obligatoires uniquement si la chaîne contient un espace.</span><span class="sxs-lookup"><span data-stu-id="b0112-164">The quotation marks are required only if the string contains a space.</span></span> <span data-ttu-id="b0112-165">Les noms de variables doivent être valides pour [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] ; ils doivent commencer par un caractère alphabétique ou un trait de soulignement et contenir des caractères alphabétiques, des chiffres ou des traits de soulignement.</span><span class="sxs-lookup"><span data-stu-id="b0112-165">Variable names must be valid for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]; they must start with alphabetical character or underscore and contain alphabetical characters, digits, or underscores.</span></span> <span data-ttu-id="b0112-166">Les mots réservés ne peuvent pas être utilisés en tant que noms de variables.</span><span class="sxs-lookup"><span data-stu-id="b0112-166">Reserved words cannot be used as variable names.</span></span> <span data-ttu-id="b0112-167">Pour plus d’informations sur l’utilisation de variables globales, consultez [Collections intégrées dans les expressions &#40;Générateur de rapports et SSRS&#41;](../report-design/built-in-collections-in-expressions-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="b0112-167">For more information about using global variables, see [Built-in Collections in Expressions &#40;Report Builder and SSRS&#41;](../report-design/built-in-collections-in-expressions-report-builder.md).</span></span>  
  
 <span data-ttu-id="b0112-168">**-t**</span><span class="sxs-lookup"><span data-stu-id="b0112-168">**-t**</span></span>  
 <span data-ttu-id="b0112-169">(Facultatif) Génère des messages d'erreur dans le journal des traces.</span><span class="sxs-lookup"><span data-stu-id="b0112-169">(Optional) Outputs error messages to the trace log.</span></span> <span data-ttu-id="b0112-170">Cet argument ne prend pas de valeur.</span><span class="sxs-lookup"><span data-stu-id="b0112-170">This argument does not take a value.</span></span> <span data-ttu-id="b0112-171">Pour plus d’informations, consultez [Report Server Service Trace Log](../report-server/report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="b0112-171">For more information, see [Report Server Service Trace Log](../report-server/report-server-service-trace-log.md).</span></span>  
  
##  <a name="permissions"></a><a name="bkmk_permissions"></a> <span data-ttu-id="b0112-172">Autorisations</span><span class="sxs-lookup"><span data-stu-id="b0112-172">Permissions</span></span>  
 <span data-ttu-id="b0112-173">Pour exécuter l'outil, vous devez avoir l'autorisation de vous connecter à l'instance du serveur de rapports sur laquelle s'exécute le script.</span><span class="sxs-lookup"><span data-stu-id="b0112-173">To run the tool, you must have permission to connect to the report server instance you are running the script against.</span></span> <span data-ttu-id="b0112-174">Vous pouvez exécuter des scripts pour apporter des modifications à l'ordinateur local ou à un ordinateur distant.</span><span class="sxs-lookup"><span data-stu-id="b0112-174">You can run scripts to make changes to the local computer or a remote computer.</span></span> <span data-ttu-id="b0112-175">Pour apporter des modifications à un serveur de rapports installé sur un ordinateur distant, spécifiez l'ordinateur distant dans l'argument `-s`.</span><span class="sxs-lookup"><span data-stu-id="b0112-175">To make changes to a report server installed on a remote computer, specify the remote computer in the `-s` argument.</span></span>  
  
##  <a name="examples"></a><a name="bkmk_examples"></a> <span data-ttu-id="b0112-176">Exemples</span><span class="sxs-lookup"><span data-stu-id="b0112-176">Examples</span></span>  
 <span data-ttu-id="b0112-177">L'exemple ci-dessous montre comment spécifier le fichier de script qui contient un script [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET et les méthodes du service Web que vous souhaitez exécuter.</span><span class="sxs-lookup"><span data-stu-id="b0112-177">The following example illustrates how to specify the script file that contains [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET script and Web service methods that you want to execute.</span></span>  
  
```  
rs -i c:\scriptfiles\script_copycontent.rss -s http://localhost/reportserver  
```  
  
 <span data-ttu-id="b0112-178"> Pour obtenir un exemple détaillé, consultez [Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="b0112-178">For a detailed example, see [Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span></span>  
  
 <span data-ttu-id="b0112-179">Pour obtenir des exemples supplémentaires, consultez [Exécuter un fichier de script Reporting Services](run-a-reporting-services-script-file.md).</span><span class="sxs-lookup"><span data-stu-id="b0112-179">For additional examples, see [Run a Reporting Services Script File](run-a-reporting-services-script-file.md)</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0112-180">Notes</span><span class="sxs-lookup"><span data-stu-id="b0112-180">Remarks</span></span>  
 <span data-ttu-id="b0112-181">Vous pouvez créer des scripts pour définir des propriétés système, publier des rapports, etc.</span><span class="sxs-lookup"><span data-stu-id="b0112-181">You can define scripts to set system properties, publish reports, and so forth.</span></span> <span data-ttu-id="b0112-182">Les scripts que vous créez peuvent inclure toutes les méthodes de l'API [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b0112-182">The scripts that you create can include any methods of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] API.</span></span> <span data-ttu-id="b0112-183">Pour plus d'informations sur les méthodes et les propriétés disponibles, consultez [Report Server Web Service](../report-server-web-service/report-server-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="b0112-183">For more information about the methods and properties available to you, see [Report Server Web Service](../report-server-web-service/report-server-web-service.md).</span></span>  
  
 <span data-ttu-id="b0112-184">Le script doit être écrit en code [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET et stocké dans un fichier texte au format Unicode ou UTF-8, avec l’extension de nom de fichier .rss.</span><span class="sxs-lookup"><span data-stu-id="b0112-184">The script must be written in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET code, and stored in a Unicode or UTF-8 text file with an .rss file name extension.</span></span> <span data-ttu-id="b0112-185">Vous ne pouvez pas déboguer les scripts à l’aide de l’utilitaire **rs** .</span><span class="sxs-lookup"><span data-stu-id="b0112-185">You cannot debug scripts with the **rs** utility.</span></span> <span data-ttu-id="b0112-186">Pour déboguer un script, exécutez le code dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b0112-186">To debug a script, run the code within [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="b0112-187"> Pour obtenir un exemple détaillé, consultez [Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="b0112-187">For a detailed example, see [Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0112-188">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b0112-188">See Also</span></span>  
 <span data-ttu-id="b0112-189">[Exécuter un fichier de script Reporting Services](run-a-reporting-services-script-file.md) </span><span class="sxs-lookup"><span data-stu-id="b0112-189">[Run a Reporting Services Script File](run-a-reporting-services-script-file.md) </span></span>  
 <span data-ttu-id="b0112-190">[Script de déploiement et tâches administratives](script-deployment-and-administrative-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="b0112-190">[Script Deployment and Administrative Tasks](script-deployment-and-administrative-tasks.md) </span></span>  
 <span data-ttu-id="b0112-191">[Script avec l’utilitaire rs.exe et le service Web](script-with-the-rs-exe-utility-and-the-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="b0112-191">[Script with the rs.exe Utility and the Web Service](script-with-the-rs-exe-utility-and-the-web-service.md) </span></span>  
 [<span data-ttu-id="b0112-192">Utilitaires d’invite de commandes du serveur de rapports &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b0112-192">Report Server Command Prompt Utilities &#40;SSRS&#41;</span></span>](report-server-command-prompt-utilities-ssrs.md)  
  
  
