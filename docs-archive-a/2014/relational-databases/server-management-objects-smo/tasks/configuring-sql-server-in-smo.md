---
title: Configuration de SQL Server dans SMO | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server, configuring
- configuration options [SMO]
ms.assetid: 0a372643-15cb-45a7-8665-04f1215df8ed
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6da1bca0aec650c01553b42bc2f3628b0bf7282e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707359"
---
# <a name="configuring-sql-server-in-smo"></a><span data-ttu-id="29e0f-102">Configuration de SQL Server dans SMO</span><span class="sxs-lookup"><span data-stu-id="29e0f-102">Configuring SQL Server in SMO</span></span>
  <span data-ttu-id="29e0f-103">Dans SMO, l’objet, l’objet, <xref:Microsoft.SqlServer.Management.Smo.Information> <xref:Microsoft.SqlServer.Management.Smo.Settings> l’objet <xref:Microsoft.SqlServer.Management.Smo.UserOptions> et l' <xref:Microsoft.SqlServer.Management.Smo.Configuration> objet contiennent des paramètres et des informations pour l’instance de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="29e0f-103">In SMO, the <xref:Microsoft.SqlServer.Management.Smo.Information> object, the <xref:Microsoft.SqlServer.Management.Smo.Settings> object, the <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object, and the <xref:Microsoft.SqlServer.Management.Smo.Configuration> object contain settings and information for the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="29e0f-104">possède de nombreuses propriétés qui décrivent le comportement de l'instance installée.</span><span class="sxs-lookup"><span data-stu-id="29e0f-104">has numerous properties that describe the behavior of the installed instance.</span></span> <span data-ttu-id="29e0f-105">Les propriétés décrivent les options de démarrage, les valeurs par défaut du serveur, les fichiers et répertoires, les informations sur le processeur et le système, le produit et les versions, les informations sur la connexion, les options de mémoire, les sélections de langue et de classement et le mode d'authentification.</span><span class="sxs-lookup"><span data-stu-id="29e0f-105">The properties describe the startup options, the server defaults, files and directories, system and processor information, product and versions, connection information, memory options, language and collation selections, and the authentication mode.</span></span>  
  
## <a name="sql-server-configuration"></a><span data-ttu-id="29e0f-106">Configuration de SQL Server</span><span class="sxs-lookup"><span data-stu-id="29e0f-106">SQL Server Configuration</span></span>  
 <span data-ttu-id="29e0f-107">Les propriétés de l'objet <xref:Microsoft.SqlServer.Management.Smo.Information> contiennent des informations sur l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], par exemple le processeur et la plateforme.</span><span class="sxs-lookup"><span data-stu-id="29e0f-107">The <xref:Microsoft.SqlServer.Management.Smo.Information> object properties contain information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], such as processor and platform.</span></span>  
  
 <span data-ttu-id="29e0f-108">Les propriétés de l'objet <xref:Microsoft.SqlServer.Management.Smo.Settings> contiennent des informations sur l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29e0f-108">The <xref:Microsoft.SqlServer.Management.Smo.Settings> object properties contain information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="29e0f-109">Le fichier et le répertoire par défaut de la base de données peuvent être modifiés en plus du profil de messagerie et du compte du serveur.</span><span class="sxs-lookup"><span data-stu-id="29e0f-109">The default database file and directory can be modified in addition to the Mail Profile and the Server Account.</span></span> <span data-ttu-id="29e0f-110">Ces propriétés restent valables pendant toute la durée de la connexion.</span><span class="sxs-lookup"><span data-stu-id="29e0f-110">These properties remain for the duration of the connection.</span></span>  
  
 <span data-ttu-id="29e0f-111">Les propriétés de l'objet <xref:Microsoft.SqlServer.Management.Smo.UserOptions> contiennent des informations sur le comportement des connexions actuelles en ce qui concerne l'arithmétique, les normes ANSI et les transactions.</span><span class="sxs-lookup"><span data-stu-id="29e0f-111">The <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object properties contain information about the current connections behavior relating to arithmetic, ANSI standards, and transactions.</span></span>  
  
 <span data-ttu-id="29e0f-112">Il existe également un jeu d'options de configuration représenté par l'objet <xref:Microsoft.SqlServer.Management.Smo.Configuration>.</span><span class="sxs-lookup"><span data-stu-id="29e0f-112">There is also a set of configuration options that is represented by the <xref:Microsoft.SqlServer.Management.Smo.Configuration> object.</span></span> <span data-ttu-id="29e0f-113">Il contient un jeu de propriétés qui représentent les options qui peuvent être modifiées par la procédure stockée `sp_configure`.</span><span class="sxs-lookup"><span data-stu-id="29e0f-113">It contains a set of properties that represent the options that can be modified by the `sp_configure` stored procedure.</span></span> <span data-ttu-id="29e0f-114">Les options telles que **renforcement de priorité**, intervalle de **récupération** et **taille du paquet réseau**contrôlent les performances de l’instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="29e0f-114">Options such as **Priority Boost**, **Recovery Interval** and **Network Packet Size**control the performance of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="29e0f-115">Nombre de ces options peuvent être modifiées de manière dynamique, mais dans certains cas, la valeur est d'abord configurée, puis modifiée lorsque l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] est redémarrée.</span><span class="sxs-lookup"><span data-stu-id="29e0f-115">Many of these options can be changed dynamically, but in some cases the value is first configured and then changed when the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is restarted.</span></span>  
  
 <span data-ttu-id="29e0f-116">Il existe une propriété d'objet <xref:Microsoft.SqlServer.Management.Smo.Configuration> pour chaque option de configuration.</span><span class="sxs-lookup"><span data-stu-id="29e0f-116">There is a <xref:Microsoft.SqlServer.Management.Smo.Configuration> object property for every configuration option.</span></span> <span data-ttu-id="29e0f-117">Vous pouvez modifier le paramètre de configuration global en utilisant l'objet <xref:Microsoft.SqlServer.Management.Smo.ConfigProperty>.</span><span class="sxs-lookup"><span data-stu-id="29e0f-117">Using the <xref:Microsoft.SqlServer.Management.Smo.ConfigProperty> object you can modify the global configuration setting.</span></span> <span data-ttu-id="29e0f-118">De nombreuses propriétés disposent de valeurs minimum et maximum qui sont également stockées sous la forme de propriétés <xref:Microsoft.SqlServer.Management.Smo.ConfigProperty>.</span><span class="sxs-lookup"><span data-stu-id="29e0f-118">Many properties have maximum and minimum values that are also stored as <xref:Microsoft.SqlServer.Management.Smo.ConfigProperty> properties.</span></span> <span data-ttu-id="29e0f-119">Ces propriétés requièrent la <xref:Microsoft.SqlServer.Management.Smo.ConfigurationBase.Alter%2A> méthode pour valider la modification apportée à l’instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="29e0f-119">These properties require the <xref:Microsoft.SqlServer.Management.Smo.ConfigurationBase.Alter%2A> method to commit the change to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="29e0f-120">Toutes les options de configuration de l'objet <xref:Microsoft.SqlServer.Management.Smo.Configuration> doivent être modifiées par l'administrateur système.</span><span class="sxs-lookup"><span data-stu-id="29e0f-120">All of the configuration options in the <xref:Microsoft.SqlServer.Management.Smo.Configuration> object must be changed by the system administrator.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="29e0f-121">Exemples</span><span class="sxs-lookup"><span data-stu-id="29e0f-121">Examples</span></span>  
 <span data-ttu-id="29e0f-122">Dans les exemples de code suivants, vous devez sélectionner l'environnement, le modèle et le langage de programmation à utiliser pour créer votre application.</span><span class="sxs-lookup"><span data-stu-id="29e0f-122">For the following code examples, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="29e0f-123">Pour plus d’informations, consultez [créer un projet Visual Basic Smo dans Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) et [créer un projet Visual C&#35; Smo dans Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="29e0f-123">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="modifying-sql-server-configuration-options-in-visual-basic"></a><span data-ttu-id="29e0f-124">Modification des options de configuration de SQL Server en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="29e0f-124">Modifying SQL Server Configuration Options in Visual Basic</span></span>  
 <span data-ttu-id="29e0f-125">L'exemple de code montre comment mettre à jour une option de configuration en Visual Basic .NET.</span><span class="sxs-lookup"><span data-stu-id="29e0f-125">The code example shows how to update a configuration option in Visual Basic .NET.</span></span> <span data-ttu-id="29e0f-126">Il récupère et affiche également des informations relatives aux valeurs minimale et maximale de l'option de configuration spécifiée.</span><span class="sxs-lookup"><span data-stu-id="29e0f-126">It also retrieves and displays information about maximum and minimum values for the specified configuration option.</span></span> <span data-ttu-id="29e0f-127">Enfin, le programme indique à l'utilisateur si la modification a été apportée dynamiquement ou si elle est stockée jusqu'au redémarrage de l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="29e0f-127">Finally, the program informs the user if the change has been made dynamically, or if it is stored until the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is restarted.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBConfigure2](SMO How to#SMO_VBConfigure2)]  -->  
  
## <a name="modifying-sql-server-settings-in-visual-basic"></a><span data-ttu-id="29e0f-128">Modification des paramètres de SQL Server en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="29e0f-128">Modifying SQL Server Settings in Visual Basic</span></span>  
 <span data-ttu-id="29e0f-129">L’exemple de code affiche des informations sur l’instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans <xref:Microsoft.SqlServer.Management.Smo.Information> et <xref:Microsoft.SqlServer.Management.Smo.Settings> , et modifie les paramètres dans et les propriétés de l' <xref:Microsoft.SqlServer.Management.Smo.Settings> <xref:Microsoft.SqlServer.Management.Smo.UserOptions> objet.</span><span class="sxs-lookup"><span data-stu-id="29e0f-129">The code example displays information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in <xref:Microsoft.SqlServer.Management.Smo.Information> and <xref:Microsoft.SqlServer.Management.Smo.Settings>, and modifies settings in <xref:Microsoft.SqlServer.Management.Smo.Settings> and <xref:Microsoft.SqlServer.Management.Smo.UserOptions>object properties.</span></span>  
  
 <span data-ttu-id="29e0f-130">Dans l'exemple, l'objet <xref:Microsoft.SqlServer.Management.Smo.UserOptions> et l'objet <xref:Microsoft.SqlServer.Management.Smo.Settings> disposent tous deux d'une méthode <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>.</span><span class="sxs-lookup"><span data-stu-id="29e0f-130">In the example the <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object and the <xref:Microsoft.SqlServer.Management.Smo.Settings> object both have an <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> method.</span></span> <span data-ttu-id="29e0f-131">Vous pouvez exécuter ces méthodes <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> individuellement.</span><span class="sxs-lookup"><span data-stu-id="29e0f-131">You can run the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> methods for these individually.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBConfigure1](SMO How to#SMO_VBConfigure1)]  -->  
  
## <a name="modifying-sql-server-settings-in-visual-c"></a><span data-ttu-id="29e0f-132">Modification des paramètres de SQL Server en Visual C#</span><span class="sxs-lookup"><span data-stu-id="29e0f-132">Modifying SQL Server Settings in Visual C#</span></span>  
 <span data-ttu-id="29e0f-133">L’exemple de code affiche des informations sur l’instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans <xref:Microsoft.SqlServer.Management.Smo.Information> et <xref:Microsoft.SqlServer.Management.Smo.Settings> , et modifie les paramètres dans et les propriétés de l' <xref:Microsoft.SqlServer.Management.Smo.Settings> <xref:Microsoft.SqlServer.Management.Smo.UserOptions> objet.</span><span class="sxs-lookup"><span data-stu-id="29e0f-133">The code example displays information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in <xref:Microsoft.SqlServer.Management.Smo.Information> and <xref:Microsoft.SqlServer.Management.Smo.Settings>, and modifies settings in <xref:Microsoft.SqlServer.Management.Smo.Settings> and <xref:Microsoft.SqlServer.Management.Smo.UserOptions>object properties.</span></span>  
  
 <span data-ttu-id="29e0f-134">Dans l'exemple, l'objet <xref:Microsoft.SqlServer.Management.Smo.UserOptions> et l'objet <xref:Microsoft.SqlServer.Management.Smo.Settings> disposent tous deux d'une méthode <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>.</span><span class="sxs-lookup"><span data-stu-id="29e0f-134">In the example the <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object and the <xref:Microsoft.SqlServer.Management.Smo.Settings> object both have an <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> method.</span></span> <span data-ttu-id="29e0f-135">Vous pouvez exécuter ces méthodes <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> individuellement.</span><span class="sxs-lookup"><span data-stu-id="29e0f-135">You can run the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> methods for these individually.</span></span>  
  
 `//Connect to the local, default instance of SQL Server.`  
  
```csharp
{  
            Server srv = new Server();  
            //Display all the configuration options.   
  
            foreach (ConfigProperty p in srv.Configuration.Properties)  
            {  
                Console.WriteLine(p.DisplayName);  
            }  
            Console.WriteLine("There are " + srv.Configuration.Properties.Count.ToString() + " configuration options.");  
            //Display the maximum and minimum values for ShowAdvancedOptions.   
            int min = 0;  
            int max = 0;  
            min = srv.Configuration.ShowAdvancedOptions.Minimum;  
            max = srv.Configuration.ShowAdvancedOptions.Maximum;  
            Console.WriteLine("Minimum and Maximum values are " + min + " and " + max + ".");  
            //Modify the value of ShowAdvancedOptions and run the Alter method.   
            srv.Configuration.ShowAdvancedOptions.ConfigValue = 0;  
            srv.Configuration.Alter();  
            //Display when the change takes place according to the IsDynamic property.   
            if (srv.Configuration.ShowAdvancedOptions.IsDynamic == true)  
            {  
                Console.WriteLine("Configuration option has been updated.");  
            }  
            else  
            {  
                Console.WriteLine("Configuration option will be updated when SQL Server is restarted.");  
            }  
        }  
```  
  
## <a name="modifying-sql-server-settings-in-powershell"></a><span data-ttu-id="29e0f-136">Modification des paramètres de SQL Server dans PowerShell</span><span class="sxs-lookup"><span data-stu-id="29e0f-136">Modifying SQL Server Settings in PowerShell</span></span>  
 <span data-ttu-id="29e0f-137">L’exemple de code affiche des informations sur l’instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans <xref:Microsoft.SqlServer.Management.Smo.Information> et <xref:Microsoft.SqlServer.Management.Smo.Settings> , et modifie les paramètres dans et les propriétés de l' <xref:Microsoft.SqlServer.Management.Smo.Settings> <xref:Microsoft.SqlServer.Management.Smo.UserOptions> objet.</span><span class="sxs-lookup"><span data-stu-id="29e0f-137">The code example displays information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in <xref:Microsoft.SqlServer.Management.Smo.Information> and <xref:Microsoft.SqlServer.Management.Smo.Settings>, and modifies settings in <xref:Microsoft.SqlServer.Management.Smo.Settings> and <xref:Microsoft.SqlServer.Management.Smo.UserOptions>object properties.</span></span>  
  
 <span data-ttu-id="29e0f-138">Dans l'exemple, l'objet <xref:Microsoft.SqlServer.Management.Smo.UserOptions> et l'objet <xref:Microsoft.SqlServer.Management.Smo.Settings> disposent tous deux d'une méthode <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>.</span><span class="sxs-lookup"><span data-stu-id="29e0f-138">In the example the <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object and the <xref:Microsoft.SqlServer.Management.Smo.Settings> object both have an <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> method.</span></span> <span data-ttu-id="29e0f-139">Vous pouvez exécuter ces méthodes <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> individuellement.</span><span class="sxs-lookup"><span data-stu-id="29e0f-139">You can run the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> methods for these individually.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\  
$srv = Get-Item default  
  
#Display information about the instance of SQL Server in Information and Settings.  
"OS Version = " + $srv.Information.OSVersion  
"State = "+ $srv.Settings.State.ToString()  
  
#Display information specific to the current user in UserOptions.  
"Quoted Identifier support = " + $srv.UserOptions.QuotedIdentifier  
  
#Modify server settings in Settings.  
$srv.Settings.LoginMode = [Microsoft.SqlServer.Management.SMO.ServerLoginMode]::Integrated  
  
#Modify settings specific to the current connection in UserOptions.  
$srv.UserOptions.AbortOnArithmeticErrors = $true  
  
#Run the Alter method to make the changes on the instance of SQL Server.  
$srv.Alter()  
```  
  
## <a name="modifying-sql-server-configuration-options-in-powershell"></a><span data-ttu-id="29e0f-140">Modification des options de configuration de SQL Server dans PowerShell</span><span class="sxs-lookup"><span data-stu-id="29e0f-140">Modifying SQL Server Configuration Options in PowerShell</span></span>  
 <span data-ttu-id="29e0f-141">L'exemple de code montre comment mettre à jour une option de configuration en Visual Basic .NET.</span><span class="sxs-lookup"><span data-stu-id="29e0f-141">The code example shows how to update a configuration option in Visual Basic .NET.</span></span> <span data-ttu-id="29e0f-142">Il récupère et affiche également des informations relatives aux valeurs minimale et maximale de l'option de configuration spécifiée.</span><span class="sxs-lookup"><span data-stu-id="29e0f-142">It also retrieves and displays information about maximum and minimum values for the specified configuration option.</span></span> <span data-ttu-id="29e0f-143">Enfin, le programme indique à l'utilisateur si la modification a été apportée dynamiquement ou si elle est stockée jusqu'au redémarrage de l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="29e0f-143">Finally, the program informs the user if the change has been made dynamically, or if it is stored until the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is restarted.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance replace LocalMachine with the physical server  
cd \sql\LocalMachine  
$svr = Get-Item default  
  
#enumerate its properties  
foreach ($Item in $Svr.Configuration.Properties)   
{  
 $Item.DisplayName  
}  
  
"There are " + $svr.Configuration.Properties.Count.ToString() + " configuration options."  
  
#Display the maximum and minimum values for ShowAdvancedOptions.  
$min = $svr.Configuration.ShowAdvancedOptions.Minimum  
$max = $svr.Configuration.ShowAdvancedOptions.Maximum  
"Minimum and Maximum values are " + $min.ToString() + " and " + $max.ToString() + "."  
  
#Modify the value of ShowAdvancedOptions and run the Alter method.  
$svr.Configuration.ShowAdvancedOptions.ConfigValue = 0  
$svr.Configuration.Alter()  
  
#Display when the change takes place according to the IsDynamic property.  
If ($svr.Configuration.ShowAdvancedOptions.IsDynamic -eq $true)  
 {
   "Configuration option has been updated."  
 }  
Else  
 {  
    "Configuration option will be updated when SQL Server is restarted."  
 }  
```  
