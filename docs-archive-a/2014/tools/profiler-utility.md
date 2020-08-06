---
title: Utilitaire de profileur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- command prompt utilities [SQL Server], profiler90 utility
- profiler90 utility
- Profiler [SQL Server Profiler], starting
- SQL Server Profiler, starting
- starting SQL Server Profiler
ms.assetid: e91c30a9-0d29-4f84-bcb8-e8fb62afadda
author: stevestein
ms.author: sstein
ms.openlocfilehash: a8df3e8557bb52839d17291bae0c5ba507d0a671
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694971"
---
# <a name="profiler-utility"></a><span data-ttu-id="e7f9f-102">Utilitaire profiler</span><span class="sxs-lookup"><span data-stu-id="e7f9f-102">Profiler Utility</span></span>
  <span data-ttu-id="e7f9f-103">L’utilitaire **profiler** lance l’outil [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e7f9f-103">The **profiler** utility launches the [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] tool.</span></span> <span data-ttu-id="e7f9f-104">Les arguments facultatifs répertoriés ci-dessous dans cette rubrique permettent de contrôler le démarrage de l'application.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-104">The optional arguments listed later in this topic allow you to control how the application starts.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e7f9f-105">L’utilitaire **profiler** n’est pas destiné à générer des scripts de trace.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-105">The **profiler** utility is not intended for scripting traces.</span></span> <span data-ttu-id="e7f9f-106">Pour en savoir plus, voir [SQL Server Profiler](sql-server-profiler/sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="e7f9f-106">For more information, see [SQL Server Profiler](sql-server-profiler/sql-server-profiler.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7f9f-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="e7f9f-107">Syntax</span></span>  
  
```  
  
      profiler  
          [ /? ] |  
[  
{  
{ /U login_id [ /P password ] }  
| /E  
}  
{[ /S sql_server_name ] | [ /A analysis_services_server_name ] }  
[ /D database ]  
[ /T "template_name" ]  
[ /B { "trace_table_name" } ]  
{ [/F "filename" ] | [ /O "filename" ] }  
[ /L locale_ID ]  
[ /M "MM-DD-YY hh:mm:ss" ]  
[ /R ]  
[ /Z file_size ]  
]  
```  
  
## <a name="arguments"></a><span data-ttu-id="e7f9f-108">Arguments</span><span class="sxs-lookup"><span data-stu-id="e7f9f-108">Arguments</span></span>  
 <span data-ttu-id="e7f9f-109">**/?**</span><span class="sxs-lookup"><span data-stu-id="e7f9f-109">**/?**</span></span>  
 <span data-ttu-id="e7f9f-110">Affiche le résumé de la syntaxe des arguments de **profiler** .</span><span class="sxs-lookup"><span data-stu-id="e7f9f-110">Displays the syntax summary of **profiler** arguments.</span></span>  
  
 <span data-ttu-id="e7f9f-111">**/U** *login_id*</span><span class="sxs-lookup"><span data-stu-id="e7f9f-111">**/U** *login_id*</span></span>  
 <span data-ttu-id="e7f9f-112">ID de connexion de l'utilisateur pour l'authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e7f9f-112">Is the user login ID for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="e7f9f-113">Les ID de connexion respectent la casse.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-113">Login IDs are case sensitive.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoteWinAuthentication](../includes/ssnotewinauthentication-md.md)]<span data-ttu-id="e7f9f-114">.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-114">.</span></span>  
  
 <span data-ttu-id="e7f9f-115">**/P** *mot de passe*</span><span class="sxs-lookup"><span data-stu-id="e7f9f-115">**/P** *password*</span></span>  
 <span data-ttu-id="e7f9f-116">Indique un mot de passe spécifié par l'utilisateur pour l'authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e7f9f-116">Specifies a user-specified password for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="e7f9f-117">**/E**</span><span class="sxs-lookup"><span data-stu-id="e7f9f-117">**/E**</span></span>  
 <span data-ttu-id="e7f9f-118">Spécifie la connexion avec l'authentification Windows en utilisant les informations d'identification de l'utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-118">Specifies connecting with Windows Authentication with the current user's credentials.</span></span>  
  
 <span data-ttu-id="e7f9f-119">**/S**  *sql_server_name*</span><span class="sxs-lookup"><span data-stu-id="e7f9f-119">**/S**  *sql_server_name*</span></span>  
 <span data-ttu-id="e7f9f-120">Spécifie une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7f9f-120">Specifies an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e7f9f-121">Profiler se connecte automatiquement au serveur spécifié en utilisant les informations d’authentification spécifiées dans les commutateurs **/U** et **/P** ou dans le commutateur **/E** .</span><span class="sxs-lookup"><span data-stu-id="e7f9f-121">Profiler will automatically connect to the specified server using the authentication information specified in the **/U** and **/P** switches or the **/E** switch.</span></span> <span data-ttu-id="e7f9f-122">Pour vous connecter à une instance nommée de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], utilisez **/S** *sql_server_name*\\*instance_name*.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-122">To connect to a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], use **/S** *sql_server_name*\\*instance_name*.</span></span>  
  
 <span data-ttu-id="e7f9f-123">**/A**  *analysis_services_server_name*</span><span class="sxs-lookup"><span data-stu-id="e7f9f-123">**/A**  *analysis_services_server_name*</span></span>  
 <span data-ttu-id="e7f9f-124">Spécifie une instance d'Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-124">Specifies an instance of Analysis Services.</span></span> <span data-ttu-id="e7f9f-125">Profiler se connecte automatiquement au serveur spécifié en utilisant les informations d’authentification spécifiées dans les commutateurs **/U** et **/P** ou dans le commutateur **/E** .</span><span class="sxs-lookup"><span data-stu-id="e7f9f-125">Profiler will automatically connect to the specified server using the authentication information specified in the **/U** and **/P** switches or the **/E** switch.</span></span> <span data-ttu-id="e7f9f-126">Pour vous connecter à une instance nommée de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , utilisez **/A** *analysis_services_server_name\instance_name*.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-126">To connect to a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] use **/A** *analysis_services_server_name\instance_name*.</span></span>  
  
 <span data-ttu-id="e7f9f-127">**/D** *base de données*</span><span class="sxs-lookup"><span data-stu-id="e7f9f-127">**/D** *database*</span></span>  
 <span data-ttu-id="e7f9f-128">Spécifie le nom de la base de données à utiliser avec la connexion.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-128">Specifies the name of the database to be used with the connection.</span></span> <span data-ttu-id="e7f9f-129">Cette option sélectionne la base de données par défaut pour l'utilisateur spécifié si aucune base de données n'est spécifiée.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-129">This option will select the default database for the specified user if no database is specified.</span></span>  
  
 <span data-ttu-id="e7f9f-130">**/B "** *trace_table_name* **"**</span><span class="sxs-lookup"><span data-stu-id="e7f9f-130">**/B "** *trace_table_name* **"**</span></span>  
 <span data-ttu-id="e7f9f-131">Spécifie une table de trace à charger lors du démarrage du générateur de profils.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-131">Specifies a trace table to load when the profiler is launched.</span></span> <span data-ttu-id="e7f9f-132">Vous devez spécifier la base de données, l'utilisateur ou le schéma, ainsi que la table.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-132">You must specify the database, the user or schema, and the table.</span></span>  
  
 <span data-ttu-id="e7f9f-133">**/T"** *template_name* **"**</span><span class="sxs-lookup"><span data-stu-id="e7f9f-133">**/T"** *template_name* **"**</span></span>  
 <span data-ttu-id="e7f9f-134">Spécifie le modèle qui sera chargé pour configurer la trace.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-134">Specifies the template that will be loaded to configure the trace.</span></span> <span data-ttu-id="e7f9f-135">Le nom du modèle doit être entre guillemets.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-135">The template name must be in quotes.</span></span> <span data-ttu-id="e7f9f-136">Le nom du modèle doit être le répertoire de modèles système ou le répertoire de modèles utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-136">The template name must be in either the system template directory or the user template directory.</span></span> <span data-ttu-id="e7f9f-137">Si deux modèles portant le même nom existent dans les deux répertoires, le modèle du répertoire système est chargé.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-137">If two templates with the same name exist in both directories, the template from the system directory will be loaded.</span></span> <span data-ttu-id="e7f9f-138">Si aucun modèle n'existe sous le nom spécifié, le modèle standard est chargé.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-138">If no template with the specified name exists, the standard template will be loaded.</span></span> <span data-ttu-id="e7f9f-139">Notez que l’extension de fichier du modèle (.tdf) ne doit pas être spécifiée dans *template_name*.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-139">Note that the file extension for the template (.tdf) should not be specified as part of the *template_name*.</span></span> <span data-ttu-id="e7f9f-140">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="e7f9f-140">For example:</span></span>  
  
```  
/T "standard"  
```  
  
 <span data-ttu-id="e7f9f-141">**/F"** *nom de fichier* **"**</span><span class="sxs-lookup"><span data-stu-id="e7f9f-141">**/F"** *filename* **"**</span></span>  
 <span data-ttu-id="e7f9f-142">Spécifie le chemin et le nom d'un fichier de trace à charger lors du démarrage du générateur de profils.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-142">Specifies the path and filename of a trace file to load when profiler is launched.</span></span> <span data-ttu-id="e7f9f-143">Le chemin complet et le nom de fichier doivent être entre guillemets.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-143">The entire path and filename must be in quotes.</span></span> <span data-ttu-id="e7f9f-144">Cette option n’est pas utilisable avec **/O**.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-144">This option cannot be used with **/O**.</span></span>  
  
 <span data-ttu-id="e7f9f-145">**/O "** *nom de fichier*  **"**</span><span class="sxs-lookup"><span data-stu-id="e7f9f-145">**/O "** *filename*  **"**</span></span>  
 <span data-ttu-id="e7f9f-146">Spécifie le chemin d'accès et le nom d'un fichier dans lequel les résultats de trace doivent être écrits.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-146">Specifies the path and filename of a file to which trace results should be written.</span></span> <span data-ttu-id="e7f9f-147">Le chemin complet et le nom de fichier doivent être entre guillemets.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-147">The entire path and filename must be in quotes.</span></span> <span data-ttu-id="e7f9f-148">Cette option n’est pas utilisable avec **/F**.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-148">This option cannot be used with **/F.**</span></span>  
  
 <span data-ttu-id="e7f9f-149">**/L** *locale_ID*</span><span class="sxs-lookup"><span data-stu-id="e7f9f-149">**/L** *locale_ID*</span></span>  
 <span data-ttu-id="e7f9f-150">Non disponible.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-150">Not available.</span></span>  
  
 <span data-ttu-id="e7f9f-151">**/M "** *MM-DD-YY hh:mm:ss* **"**</span><span class="sxs-lookup"><span data-stu-id="e7f9f-151">**/M "** *MM-DD-YY hh:mm:ss* **"**</span></span>  
 <span data-ttu-id="e7f9f-152">Spécifie la date et l'heure auxquelles la trace doit s'arrêter.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-152">Specifies the date and time for the trace to stop.</span></span> <span data-ttu-id="e7f9f-153">L'heure d'arrêt doit être indiquée entre guillemets.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-153">The stop time must be in quotes.</span></span> <span data-ttu-id="e7f9f-154">Spécifiez l'heure d'arrêt conformément aux paramètres du tableau ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="e7f9f-154">Specify the stop time according to the parameters in the table below:</span></span>  
  
|<span data-ttu-id="e7f9f-155">Paramètre</span><span class="sxs-lookup"><span data-stu-id="e7f9f-155">Parameter</span></span>|<span data-ttu-id="e7f9f-156">Définition</span><span class="sxs-lookup"><span data-stu-id="e7f9f-156">Definition</span></span>|  
|---------------|----------------|  
|<span data-ttu-id="e7f9f-157">MM</span><span class="sxs-lookup"><span data-stu-id="e7f9f-157">MM</span></span>|<span data-ttu-id="e7f9f-158">Mois à deux chiffres</span><span class="sxs-lookup"><span data-stu-id="e7f9f-158">Two-digit month</span></span>|  
|<span data-ttu-id="e7f9f-159">DD</span><span class="sxs-lookup"><span data-stu-id="e7f9f-159">DD</span></span>|<span data-ttu-id="e7f9f-160">Jour à deux chiffres</span><span class="sxs-lookup"><span data-stu-id="e7f9f-160">Two-digit day</span></span>|  
|<span data-ttu-id="e7f9f-161">YY</span><span class="sxs-lookup"><span data-stu-id="e7f9f-161">YY</span></span>|<span data-ttu-id="e7f9f-162">Année à deux chiffres</span><span class="sxs-lookup"><span data-stu-id="e7f9f-162">Two-digit year</span></span>|  
|<span data-ttu-id="e7f9f-163">hh</span><span class="sxs-lookup"><span data-stu-id="e7f9f-163">hh</span></span>|<span data-ttu-id="e7f9f-164">Heure à deux chiffres au format 24 heures</span><span class="sxs-lookup"><span data-stu-id="e7f9f-164">Two-digit hour on a 24-hour clock</span></span>|  
|<span data-ttu-id="e7f9f-165">MM</span><span class="sxs-lookup"><span data-stu-id="e7f9f-165">mm</span></span>|<span data-ttu-id="e7f9f-166">Minute à deux chiffres</span><span class="sxs-lookup"><span data-stu-id="e7f9f-166">Two-digit minute</span></span>|  
|<span data-ttu-id="e7f9f-167">ss</span><span class="sxs-lookup"><span data-stu-id="e7f9f-167">ss</span></span>|<span data-ttu-id="e7f9f-168">Seconde à deux chiffres</span><span class="sxs-lookup"><span data-stu-id="e7f9f-168">Two-digit second</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="e7f9f-169">Le format « MM-DD-YY hh:mm:ss » peut être utilisé uniquement si l’option **Utiliser des paramètres régionaux pour afficher les valeurs de date et d’heure** est activée dans [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7f9f-169">The "MM-DD-YY hh:mm:ss" format can only be used if the **Use regional settings to display date and time values** option is enabled in [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="e7f9f-170">Si cette option n'est pas activée, vous devez utiliser le format de date et heure « YYYY-MM-DD hh:mm:ss ».</span><span class="sxs-lookup"><span data-stu-id="e7f9f-170">If this option is not enabled, you must use the "YYYY-MM-DD hh:mm:ss" date and time format.</span></span>  
  
 <span data-ttu-id="e7f9f-171">**/R**</span><span class="sxs-lookup"><span data-stu-id="e7f9f-171">**/R**</span></span>  
 <span data-ttu-id="e7f9f-172">Permet la substitution du fichier de trace.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-172">Enables trace file rollover.</span></span>  
  
 <span data-ttu-id="e7f9f-173">**/Z**  *file_size*</span><span class="sxs-lookup"><span data-stu-id="e7f9f-173">**/Z**  *file_size*</span></span>  
 <span data-ttu-id="e7f9f-174">Spécifie la taille du fichier de trace, en mégaoctets (Mo).</span><span class="sxs-lookup"><span data-stu-id="e7f9f-174">Specifies the size of the trace file in megabytes (MB).</span></span> <span data-ttu-id="e7f9f-175">La taille par défaut est de 5 Mo.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-175">The default size is 5 MB.</span></span> <span data-ttu-id="e7f9f-176">Si la substitution est activée, tous les fichiers de substitution sont limités à la valeur spécifiée dans cet argument.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-176">If rollover is enabled, all rollover files will be limited to the value specified in this argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7f9f-177">Notes</span><span class="sxs-lookup"><span data-stu-id="e7f9f-177">Remarks</span></span>  
 <span data-ttu-id="e7f9f-178">Pour démarrer une trace avec un modèle spécifique, utilisez les options **/S** et **/T** simultanément.</span><span class="sxs-lookup"><span data-stu-id="e7f9f-178">To start a trace with a specific template, use the **/S** and **/T** options together.</span></span> <span data-ttu-id="e7f9f-179">Par exemple, pour démarrer une trace en utilisant le modèle Standard sur MyServer\MyInstance, entrez ce qui suit à l'invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="e7f9f-179">For example, to start a trace using the Standard template on MyServer\MyInstance, enter the following at the command prompt:</span></span>  
  
```  
profiler /S MyServer\MyInstance /T "Standard"  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7f9f-180">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e7f9f-180">See Also</span></span>  
 [<span data-ttu-id="e7f9f-181">Référence de l’utilitaire d’invite de commandes &#40;moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="e7f9f-181">Command Prompt Utility Reference &#40;Database Engine&#41;</span></span>](command-prompt-utility-reference-database-engine.md)  
  
  
