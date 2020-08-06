---
title: Invoke-PolicyEvaluation (applet de commande) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, Invoke-PolicyEvaluation
- Policy-Based Management, PowerShell
- Invoke-PolicyEvaluation cmdlet
- Cmdlets [SQL Server], Invoke-PolicyEvaluation
- PowerShell [SQL Server], Invoke-PolicyEvaluation
ms.assetid: 3e6d4f5a-59b7-4203-b95a-f7e692c0f131
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 656fdffea191c9cf6fc42d860164bc5af1e04561
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698508"
---
# <a name="invoke-policyevaluation-cmdlet"></a><span data-ttu-id="dee99-102">Invoke-PolicyEvaluation (applet de commande)</span><span class="sxs-lookup"><span data-stu-id="dee99-102">Invoke-PolicyEvaluation cmdlet</span></span>
  <span data-ttu-id="dee99-103">**Invoke-PolicyEvaluation** est une applet de commande [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] qui indique si un jeu cible d’objets SQL Server est conforme ou non aux conditions spécifiées dans une ou plusieurs stratégies de gestion basée sur des stratégies.</span><span class="sxs-lookup"><span data-stu-id="dee99-103">**Invoke-PolicyEvaluation** is a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cmdlet that reports whether a target set of SQL Server objects complies with the conditions specified in one or more Policy-Based Management policies.</span></span>  
  
## <a name="using-invoke-policyevaluation"></a><span data-ttu-id="dee99-104">Utilisation d'Invoke-PolicyEvaluation</span><span class="sxs-lookup"><span data-stu-id="dee99-104">Using Invoke-PolicyEvaluation</span></span>  
 <span data-ttu-id="dee99-105">**Invoke-PolicyEvaluation** évalue une ou plusieurs stratégies par rapport à un jeu d’objets SQL Server appelé « jeu cible ».</span><span class="sxs-lookup"><span data-stu-id="dee99-105">**Invoke-PolicyEvaluation** evaluates one or more policies against a set of SQL Server objects called the target set.</span></span> <span data-ttu-id="dee99-106">Le jeu d'objets cibles provient d'un serveur cible.</span><span class="sxs-lookup"><span data-stu-id="dee99-106">The set of target objects comes from a target server.</span></span> <span data-ttu-id="dee99-107">Chaque stratégie définit des conditions qui représentent les états autorisés pour les objets cibles.</span><span class="sxs-lookup"><span data-stu-id="dee99-107">Each policy defines conditions, which are the allowed states for the target objects.</span></span> <span data-ttu-id="dee99-108">Par exemple, la stratégie **Trustworthy Database** stipule que la propriété de base de données TRUSTWORTHY doit avoir la valeur OFF.</span><span class="sxs-lookup"><span data-stu-id="dee99-108">For example, the **Trustworthy Database** policy states that the TRUSTWORTHY database property must be set to OFF.</span></span>  
  
 <span data-ttu-id="dee99-109">Le paramètre **-AdHocPolicyEvaluationMode** spécifie les actions effectuées :</span><span class="sxs-lookup"><span data-stu-id="dee99-109">The **-AdHocPolicyEvaluationMode** parameter specifies the actions taken:</span></span>  
  
 <span data-ttu-id="dee99-110">Vérification</span><span class="sxs-lookup"><span data-stu-id="dee99-110">Check</span></span>  
 <span data-ttu-id="dee99-111">Indique l'état de conformité des objets cibles à l'aide des informations d'identification de votre connexion actuelle.</span><span class="sxs-lookup"><span data-stu-id="dee99-111">Report the compliance status of the target objects using the credentials of your current login.</span></span> <span data-ttu-id="dee99-112">Ne reconfigure pas d'objets.</span><span class="sxs-lookup"><span data-stu-id="dee99-112">Do no reconfigure any objects.</span></span> <span data-ttu-id="dee99-113">Il s'agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="dee99-113">This is the default setting.</span></span>  
  
 <span data-ttu-id="dee99-114">CheckSqlScriptAsProxy</span><span class="sxs-lookup"><span data-stu-id="dee99-114">CheckSqlScriptAsProxy</span></span>  
 <span data-ttu-id="dee99-115">Indique l’état de conformité des objets cibles à l’aide des informations d’identification de la connexion proxy **##MS_PolicyTSQLExecutionLogin##** .</span><span class="sxs-lookup"><span data-stu-id="dee99-115">Report the compliance status of the target objects using the credentials of the **##MS_PolicyTSQLExecutionLogin##** proxy login.</span></span> <span data-ttu-id="dee99-116">Ne reconfigure pas d'objets.</span><span class="sxs-lookup"><span data-stu-id="dee99-116">Do no reconfigure any objects.</span></span>  
  
 <span data-ttu-id="dee99-117">Configurer</span><span class="sxs-lookup"><span data-stu-id="dee99-117">Configure</span></span>  
 <span data-ttu-id="dee99-118">Indique l'état de conformité des objets cibles à l'aide des informations d'identification de votre connexion actuelle.</span><span class="sxs-lookup"><span data-stu-id="dee99-118">Report the compliance status of the target objects using the credentials of your current login.</span></span> <span data-ttu-id="dee99-119">Reconfigure toutes les options définissables et déterministes qui ne sont pas conformes aux stratégies.</span><span class="sxs-lookup"><span data-stu-id="dee99-119">Reconfigure any settable and deterministic options that are not in compliance with the policies.</span></span>  
  
## <a name="specifying-polices"></a><span data-ttu-id="dee99-120">Spécification de stratégies</span><span class="sxs-lookup"><span data-stu-id="dee99-120">Specifying Polices</span></span>  
 <span data-ttu-id="dee99-121">La façon dont vous spécifiez une stratégie dépend de l'emplacement de stockage de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="dee99-121">How you specify a policy depends on where the policy is stored.</span></span> <span data-ttu-id="dee99-122">Les stratégies peuvent être stockées dans deux formats :</span><span class="sxs-lookup"><span data-stu-id="dee99-122">Policies can be stored in two formats:</span></span>  
  
-   <span data-ttu-id="dee99-123">Elles peuvent être constituées d'objets stockés dans un magasin de stratégies, par exemple une instance du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="dee99-123">They can be objects stored in a policy store, such as an instance of the Database Engine.</span></span> <span data-ttu-id="dee99-124">Vous pouvez utiliser le dossier SQLSERVER:\SQLPolicy pour spécifier l'emplacement de stratégies dans un magasin de stratégies.</span><span class="sxs-lookup"><span data-stu-id="dee99-124">You can use the SQLSERVER:\SQLPolicy folder to specify the location of policies in a policy store.</span></span> <span data-ttu-id="dee99-125">Vous pouvez utiliser des applets de commande Windows PowerShell pour filtrer les stratégies d'entrée selon leurs propriétés, par exemple Where-Object pour appliquer un filtre sur la catégorie de la stratégie ou Get-Item pour appliquer un filtre sur le nom de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="dee99-125">You can use Windows PowerShell cmdlets to filter the input polices based on their properties, such as using Where-Object to filter on the policy category or Get-Item to filter on policy name.</span></span>  
  
-   <span data-ttu-id="dee99-126">Elles peuvent être exportées en tant que fichiers XML.</span><span class="sxs-lookup"><span data-stu-id="dee99-126">They can be exported as XML files.</span></span> <span data-ttu-id="dee99-127">Vous pouvez utiliser un lecteur du système de fichiers, tel que D:, pour spécifier l'emplacement des fichiers XML.</span><span class="sxs-lookup"><span data-stu-id="dee99-127">You can use a file system drive, such as D:, to specify the location of the XML files.</span></span> <span data-ttu-id="dee99-128">Vous pouvez utiliser des applets de commande Windows PowerShell tels que Where-Object pour filtrer les stratégies selon les propriétés du fichier, par exemple le nom du fichier.</span><span class="sxs-lookup"><span data-stu-id="dee99-128">You can use Windows PowerShell cmdlets such as Where-Object to filter the policies on their file properties, such as file name.</span></span>  
  
 <span data-ttu-id="dee99-129">Si les stratégies sont stockées dans un magasin de stratégies, vous devez passer un jeu de PSObjects pointant vers les stratégies à évaluer.</span><span class="sxs-lookup"><span data-stu-id="dee99-129">If the policies are stored in a policy store, you must pass in a set of PSObjects pointing to the policies to be evaluated.</span></span> <span data-ttu-id="dee99-130">Pour ce faire, dirigez la sortie d’une applet de commande, telle que Get-Item, vers **Invoke-PolicyEvaluation**. Inutile de spécifier le paramètre **-Policy** .</span><span class="sxs-lookup"><span data-stu-id="dee99-130">This is typically done by piping the output of a cmdlet such as Get-Item to **Invoke-PolicyEvaluation**, and does not require that you specify the **-Policy** parameter.</span></span> <span data-ttu-id="dee99-131">Par exemple, si vous avez importé les stratégies Recommandations de Microsoft dans votre instance du moteur de base de données, cette commande évalue la stratégie **État de la base de données** :</span><span class="sxs-lookup"><span data-stu-id="dee99-131">For example, if you have imported the Microsoft Best Practices policies into your instance of the database engine, this command evaluates the **Database Status** policy:</span></span>  
  
```powershell
sl "SQLSERVER:\SQLPolicy\MyComputer\DEFAULT\Policies"  
Get-Item "Database Status" | Invoke-PolicyEvaluation -TargetServerName "MYCOMPUTER"  
```  
  
 <span data-ttu-id="dee99-132">Cet exemple montre comment utiliser Where-Object pour filtrer plusieurs stratégies d’un magasin de stratégies, en fonction de leur propriété **PolicyCategory** .</span><span class="sxs-lookup"><span data-stu-id="dee99-132">This example shows using Where-Object to filter multiple policies from a policy store based on their **PolicyCategory** property.</span></span> <span data-ttu-id="dee99-133">Les objets de la sortie dirigée de **Where-Object** sont consommés par **Invoke-PolicyEvaluation**.</span><span class="sxs-lookup"><span data-stu-id="dee99-133">The objects from the piped output of **Where-Object** is consumed by **Invoke-PolicyEvaluation**.</span></span>  
  
```powershell
sl "SQLSERVER:\SQLPolicy\MyComputer\DEFAULT\Policies"  
gci | Where-Object {$_.PolicyCategory -eq "Microsoft Best Practices: Maintenance"} | Invoke-PolicyEvaluation -TargetServer "MYCOMPUTER"  
```  
  
 <span data-ttu-id="dee99-134">Si les stratégies sont stockées sous la forme de fichiers XML, vous devez utiliser le paramètre **-Policy** pour fournir le chemin et le nom de chaque stratégie.</span><span class="sxs-lookup"><span data-stu-id="dee99-134">If the policies are stored as XML files, you must use the **-Policy** parameter to supply both the path and name for each policy.</span></span> <span data-ttu-id="dee99-135">Si vous ne spécifiez pas de chemin dans le paramètre **-Policy** , **Invoke-PolicyEvaluation** utilise le paramètre actuel du chemin **sqlps** .</span><span class="sxs-lookup"><span data-stu-id="dee99-135">If you do not specify a path in the **-Policy** parameter, **Invoke-PolicyEvaulation** uses the current setting of the **sqlps** path.</span></span> <span data-ttu-id="dee99-136">Par exemple, cette commande évalue l'une des stratégies Recommandations de Microsoft installées avec SQL Server par rapport à la base de données par défaut pour votre connexion :</span><span class="sxs-lookup"><span data-stu-id="dee99-136">For example, this command evaluates one of the Microsoft Best Practice policies installed with SQL Server against the default database for your login:</span></span>  
  
```powershell
Invoke-PolicyEvaluation -Policy "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033\Database Status.xml" -TargetServerName "MYCOMPUTER"  
```  
  
 <span data-ttu-id="dee99-137">Cette commande a le même effet, sauf qu’elle utilise le chemin d’accès **sqlps** courant pour établir l’emplacement du fichier XML de la stratégie :</span><span class="sxs-lookup"><span data-stu-id="dee99-137">This command does the same thing, only it uses the current **sqlps** path to establish the location of the policy XML file:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033"  
Invoke-PolicyEvaluation -Policy "Database Status.xml" -TargetServerName "MYCOMPUTER"  
```  
  
 <span data-ttu-id="dee99-138">Cet exemple montre comment utiliser l’applet de commande **Get-ChildItem** pour récupérer plusieurs fichiers XML de stratégie et diriger les objets vers **Invoke-PolicyEvaluation**:</span><span class="sxs-lookup"><span data-stu-id="dee99-138">This example shows using the **Get-ChildItem** cmdlet to retrieve multiple policy XML files and pipe the objects into **Invoke-PolicyEvaluation**:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033"  
gci "Database Status.xml", "Trustworthy Database.xml" | Invoke-PolicyEvaluation -TargetServer "MYCOMPUTER"  
```  
  
## <a name="specifying-the-target-set"></a><span data-ttu-id="dee99-139">Spécification du jeu de cibles</span><span class="sxs-lookup"><span data-stu-id="dee99-139">Specifying the Target Set</span></span>  
 <span data-ttu-id="dee99-140">Utilisez trois paramètres pour spécifier le jeu d'objets cibles :</span><span class="sxs-lookup"><span data-stu-id="dee99-140">Use three parameters to specify the set of target objects:</span></span>  
  
-   <span data-ttu-id="dee99-141">**-TargetServerName** spécifie l’instance de SQL Server contenant les objets cibles.</span><span class="sxs-lookup"><span data-stu-id="dee99-141">**-TargetServerName** specifies the instance of SQL Server containing the target objects.</span></span> <span data-ttu-id="dee99-142">Vous pouvez spécifier les informations dans une chaîne qui utilise le format défini pour la propriété ConnectionString de la classe <xref:System.Data.SqlClient.SqlConnection> .</span><span class="sxs-lookup"><span data-stu-id="dee99-142">You can specify the information in a string that uses the format defined for the ConnectionString property of the <xref:System.Data.SqlClient.SqlConnection> class.</span></span> <span data-ttu-id="dee99-143">Vous pouvez utiliser la classe <xref:System.Data.SqlClient.SqlConnectionStringBuilder> pour générer une chaîne de connexion correctement mise en forme.</span><span class="sxs-lookup"><span data-stu-id="dee99-143">You can use the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> class to build a correctly formatted connection string.</span></span> <span data-ttu-id="dee99-144">Vous pouvez également créer un objet <xref:Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection> et le transmettre à **-TargetServer**.</span><span class="sxs-lookup"><span data-stu-id="dee99-144">You can also create a <xref:Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection> object and pass it to **-TargetServer**.</span></span> <span data-ttu-id="dee99-145">Si vous spécifiez une chaîne qui ne contient que le nom du serveur, **Invoke-PolicyEvaluation** utilise l’authentification Windows pour se connecter au serveur.</span><span class="sxs-lookup"><span data-stu-id="dee99-145">If you supply a string that has only the name of the server, **Invoke-PolicyEvaluation** uses Windows Authentication to connect to the server.</span></span>  
  
-   <span data-ttu-id="dee99-146">**-TargetObjects** accepte un objet ou un tableau d’objets représentant les objets SQL Server dans le jeu cible.</span><span class="sxs-lookup"><span data-stu-id="dee99-146">**-TargetObjects** takes an object or array of objects that represent the SQL Server objects in the target set.</span></span> <span data-ttu-id="dee99-147">Par exemple, vous pouvez créer un tableau d’objets de classe <xref:Microsoft.SqlServer.Management.Smo.Database> à transmettre à **-TargetObjects**.</span><span class="sxs-lookup"><span data-stu-id="dee99-147">For example, you could create an array of <xref:Microsoft.SqlServer.Management.Smo.Database> class objects to pass in to **-TargetObjects**.</span></span>  
  
-   <span data-ttu-id="dee99-148">**-TargetExpressions** accepte une chaîne contenant une expression de requête qui spécifie les objets dans le jeu cible.</span><span class="sxs-lookup"><span data-stu-id="dee99-148">**-TargetExpressions** takes a string containing a query expression that specifies the objects in the target set.</span></span> <span data-ttu-id="dee99-149">L'expression de requête se présente sous la forme de nœuds séparés par le caractère « / ».</span><span class="sxs-lookup"><span data-stu-id="dee99-149">The query expression is in the form of nodes separated by the '/' character.</span></span> <span data-ttu-id="dee99-150">Chaque nœud se présente sous la forme ObjectType[Filter].</span><span class="sxs-lookup"><span data-stu-id="dee99-150">Each node is in the form ObjectType[Filter].</span></span> <span data-ttu-id="dee99-151">Le type d’objet est l’un des objets d’une hiérarchie d’objets SMO (SQL Server Management Object).</span><span class="sxs-lookup"><span data-stu-id="dee99-151">Object type is one of the objects in a SQL Server Management Object (SMO) object hierarchy.</span></span> <span data-ttu-id="dee99-152">Le filtre est une expression qui filtre les objets au niveau de ce nœud.</span><span class="sxs-lookup"><span data-stu-id="dee99-152">Filter is an expression that filters for objects at that node.</span></span> <span data-ttu-id="dee99-153">Pour plus d’informations, consultez [Expressions de requête et noms URN](../powershell/query-expressions-and-uniform-resource-names.md).</span><span class="sxs-lookup"><span data-stu-id="dee99-153">For more information, see [Query Expressions and Uniform Resource Names](../powershell/query-expressions-and-uniform-resource-names.md).</span></span>  
  
 <span data-ttu-id="dee99-154">Spécifiez **-TargetObjects** ou **-TargetExpression**, mais pas les deux.</span><span class="sxs-lookup"><span data-stu-id="dee99-154">Specify either **-TargetObjects** or **-TargetExpression**, not both.</span></span>  
  
 <span data-ttu-id="dee99-155">Cet exemple utilise un objet Sfc.SqlStoreConnection pour spécifier le serveur cible :</span><span class="sxs-lookup"><span data-stu-id="dee99-155">This example uses an Sfc.SqlStoreConnection object to specify the target server:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033"  
$conn = New-Object Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection("server='MYCOMPUTER';Trusted_Connection=True")  
Invoke-PolicyEvaluation -Policy "Database Status.xml" -TargetServerName $conn  
```  
  
 <span data-ttu-id="dee99-156">Cet exemple utilise **-TargetExpression** pour identifier la base de données à évaluer :</span><span class="sxs-lookup"><span data-stu-id="dee99-156">This example uses **-TargetExpression** to identify the specific database to evaluate:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033"  
Invoke-PolicyEvaluation -Policy "Database Status.xml" -TargetServerName "MyComputer" -TargetExpression "Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012']"  
```  
  
## <a name="evaluating-analysis-services-policies"></a><span data-ttu-id="dee99-157">Évaluation de stratégies Analysis Services</span><span class="sxs-lookup"><span data-stu-id="dee99-157">Evaluating Analysis Services Policies</span></span>  
 <span data-ttu-id="dee99-158">Pour évaluer des stratégies par rapport à une instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], vous devez charger et inscrire un assembly dans PowerShell, créer une variable avec un objet de connexion Analysis Services, puis transmettre la variable au paramètre **-TargetObject** .</span><span class="sxs-lookup"><span data-stu-id="dee99-158">To evaluate policies against an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], you must load and register an assembly into PowerShell, create a variable with an Analysis Services connection object, and pass the variable to the **-TargetObject** parameter.</span></span> <span data-ttu-id="dee99-159">Cet exemple montre comment évaluer la stratégie de configuration de la surface d'exposition des Recommandations pour [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="dee99-159">This example shows evaluating the Best Practices surface area configuration policy for [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\AnalysisServices\1033"  
[System.Reflection.Assembly]::LoadWithPartialName("Microsoft.AnalysisServices")  
$SSASsvr = New-Object Microsoft.AnalysisServices.Server  
$SSASsvr.Connect("Data Source=Localhost")  
Invoke-PolicyEvaluation -Policy "Surface Area Configuration for Analysis Services Features.xml" -TargetObject $SSASsvr  
```  
  
## <a name="evaluating-reporting-services-policies"></a><span data-ttu-id="dee99-160">Évaluation de stratégies Reporting Services</span><span class="sxs-lookup"><span data-stu-id="dee99-160">Evaluating Reporting Services Policies</span></span>  
 <span data-ttu-id="dee99-161">Pour évaluer des stratégies [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , vous devez charger et inscrire un assembly dans PowerShell, créer une variable avec un objet de connexion [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , puis transmettre la variable au paramètre **-TargetObject** .</span><span class="sxs-lookup"><span data-stu-id="dee99-161">To evaluate [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] policies, you must load and register an assembly into PowerShell, create a variable with a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] connection object, and pass the variable to the **-TargetObject** parameter.</span></span> <span data-ttu-id="dee99-162">Cet exemple montre comment évaluer la stratégie de configuration de la surface d'exposition des Recommandations pour [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="dee99-162">This example shows evaluating the Best Practices surface area configuration policy for [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\ReportingServices\1033"  
[System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SqlServer.Dmf.Adapters")  
$SSRSsvr = new-object Microsoft.SqlServer.Management.Adapters.RSContainer('MyComputer')  
Invoke-PolicyEvaluation -Policy "Surface Area Configuration for Reporting Services 2008 Features.xml" -TargetObject $SSRSsvr  
```  
  
## <a name="formatting-output"></a><span data-ttu-id="dee99-163">Mise en forme de la sortie</span><span class="sxs-lookup"><span data-stu-id="dee99-163">Formatting Output</span></span>  
 <span data-ttu-id="dee99-164">Par défaut, la sortie de **Invoke-PolicyEvaluation** s’affiche dans la fenêtre d’invite de commandes sous la forme d’un rapport concis au format explicite.</span><span class="sxs-lookup"><span data-stu-id="dee99-164">By default, the output of **Invoke-PolicyEvaluation** is displayed in the command prompt window as a concise report in human-readable format.</span></span> <span data-ttu-id="dee99-165">Vous pouvez utiliser le paramètre **-OutputXML** pour que l’applet de commande génère plutôt un rapport détaillé sous la forme d’un fichier XML.</span><span class="sxs-lookup"><span data-stu-id="dee99-165">You can use the **-OutputXML** parameter to specify that the cmdlet instead produce a detailed report as an XML file.</span></span> <span data-ttu-id="dee99-166">**Invoke-PolicyEvaluation** utilise le schéma SML-IF (Systems Modeling Language Interchange Format) pour que le fichier soit lisible par les lecteurs SML-IF.</span><span class="sxs-lookup"><span data-stu-id="dee99-166">**Invoke-PolicyEvaluation** uses the Systems Modeling Language Interchange Format (SML-IF) schema so the file can be read by SML-IF readers.</span></span>  
  
```powershell
sl "SQLSERVER:\SQLPolicy\MyComputer\DEFAULT\Policies"  
Invoke-PolicyEvaluation -Policy "Datbase Status" -TargetServer "MYCOMPUTER" -OutputXML > C:\MyReports\DatabaseStatusReport.xml  
```  
  
## <a name="see-also"></a><span data-ttu-id="dee99-167">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dee99-167">See Also</span></span>  
 [<span data-ttu-id="dee99-168">Utiliser les applets de commande du Moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="dee99-168">Use the Database Engine cmdlets</span></span>](../../2014/database-engine/use-the-database-engine-cmdlets.md)  
