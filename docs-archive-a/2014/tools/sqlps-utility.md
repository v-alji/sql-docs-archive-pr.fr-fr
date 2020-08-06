---
title: Utilitaire sqlps | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- sqlps utility
- PowerShell [SQL Server], sqlps utility
ms.assetid: 4b2515a6-12c3-44fb-b263-1c567681cd2b
author: stevestein
ms.author: sstein
ms.openlocfilehash: b445366b3fb99ad4beebdf7b203ada77afe90c8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694892"
---
# <a name="sqlps-utility"></a><span data-ttu-id="27268-102">sqlps (utilitaire)</span><span class="sxs-lookup"><span data-stu-id="27268-102">sqlps Utility</span></span>
  <span data-ttu-id="27268-103">L'utilitaire `sqlps` démarre une session Windows PowerShell 2.0 avec les applets de commande et le fournisseur [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell chargés et inscrits.</span><span class="sxs-lookup"><span data-stu-id="27268-103">The `sqlps` utility starts a Windows PowerShell 2.0 session with the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell provider and cmdlets loaded and registered.</span></span> <span data-ttu-id="27268-104">Vous pouvez entrer des scripts ou des commandes PowerShell qui utilisent les composants [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell pour travailler avec des instances de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] et leurs objets.</span><span class="sxs-lookup"><span data-stu-id="27268-104">You can enter PowerShell commands or scripts that use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell components to work with instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and their objects.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="27268-105">Utilisez plutôt le module `sqlps` PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27268-105">Use the `sqlps` PowerShell module instead.</span></span> <span data-ttu-id="27268-106">Pour plus d’informations sur le `sqlps` module, consultez [importer le module sqlps](../database-engine/import-the-sqlps-module.md).</span><span class="sxs-lookup"><span data-stu-id="27268-106">For more information about the `sqlps` module, see [Import the SQLPS Module](../database-engine/import-the-sqlps-module.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27268-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="27268-107">Syntax</span></span>  
  
```  
  
      sqlps   
[ [ [ -NoLogo ][ -NoExit ][ -NoProfile ]  
    [ -OutPutFormat { Text | XML } ] [ -InPutFormat { Text | XML } ]  
  ]  
  [ -Command { -  
             | script_block [ -argsargument_array ]  
             | string [ command_parameters ]  
             }  
  ]  
]  
[ -? | -Help ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="27268-108">Arguments</span><span class="sxs-lookup"><span data-stu-id="27268-108">Arguments</span></span>  
 <span data-ttu-id="27268-109">**-NoLogo**</span><span class="sxs-lookup"><span data-stu-id="27268-109">**-NoLogo**</span></span>  
 <span data-ttu-id="27268-110">Spécifie que l'utilitaire `sqlps` doit masquer la bannière de copyright lorsqu'il démarre.</span><span class="sxs-lookup"><span data-stu-id="27268-110">Specifies that the `sqlps` utility hide the copyright banner when it starts.</span></span>  
  
 <span data-ttu-id="27268-111">**-NoExit**</span><span class="sxs-lookup"><span data-stu-id="27268-111">**-NoExit**</span></span>  
 <span data-ttu-id="27268-112">Spécifie que l'utilitaire `sqlps` doit poursuivre son exécution après le lancement des commandes de démarrage.</span><span class="sxs-lookup"><span data-stu-id="27268-112">Specifies that the `sqlps` utility continue running after the startup commands have completed.</span></span>  
  
 <span data-ttu-id="27268-113">**-NoProfile**</span><span class="sxs-lookup"><span data-stu-id="27268-113">**-NoProfile**</span></span>  
 <span data-ttu-id="27268-114">Spécifie que l'utilitaire `sqlps` ne doit pas charger de profil utilisateur.</span><span class="sxs-lookup"><span data-stu-id="27268-114">Specifies that the `sqlps` utility not load a user profile.</span></span> <span data-ttu-id="27268-115">Les profils utilisateur enregistrent des alias, fonctions et variables fréquemment utilisés en vue de leur utilisation au cours de différentes sessions PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27268-115">User profiles record commonly used aliases, functions, and variables for use across PowerShell sessions.</span></span>  
  
 <span data-ttu-id="27268-116">**-OutPutFormat** { **Text** | **XML** }</span><span class="sxs-lookup"><span data-stu-id="27268-116">**-OutPutFormat** { **Text** | **XML** }</span></span>  
 <span data-ttu-id="27268-117">Spécifie que la sortie de l' `sqlps` utilitaire doit être mise en forme en tant que chaînes de texte (**texte**) ou dans un format CLIXML sérialisé (**XML**).</span><span class="sxs-lookup"><span data-stu-id="27268-117">Specifies that the `sqlps` utility output be formatted as either text strings (**Text**) or in a serialized CLIXML format (**XML**).</span></span>  
  
 <span data-ttu-id="27268-118">**-InPutFormat** { **Text** | **XML** }</span><span class="sxs-lookup"><span data-stu-id="27268-118">**-InPutFormat** { **Text** | **XML** }</span></span>  
 <span data-ttu-id="27268-119">Spécifie que l’entrée de l' `sqlps` utilitaire est mise en forme en tant que chaînes de texte (**texte**) ou dans un format CLIXML sérialisé (**XML**).</span><span class="sxs-lookup"><span data-stu-id="27268-119">Specifies that input to the `sqlps` utility is formatted as either text strings (**Text**) or in a serialized CLIXML format (**XML**).</span></span>  
  
 <span data-ttu-id="27268-120">**-Command**</span><span class="sxs-lookup"><span data-stu-id="27268-120">**-Command**</span></span>  
 <span data-ttu-id="27268-121">Spécifie la commande de l'utilitaire `sqlps` à utiliser.</span><span class="sxs-lookup"><span data-stu-id="27268-121">Specifies the command for the `sqlps` utility to run.</span></span> <span data-ttu-id="27268-122">L' `sqlps` utilitaire exécute la commande, puis se ferme, sauf si **-NoExit** est également spécifié.</span><span class="sxs-lookup"><span data-stu-id="27268-122">The `sqlps` utility runs the command and then exits, unless **-NoExit** is also specified.</span></span> <span data-ttu-id="27268-123">Ne spécifiez pas d’autres commutateurs après **-Command**, car ils seront lus comme des paramètres de commande.</span><span class="sxs-lookup"><span data-stu-id="27268-123">Do not specify any other switches after **-Command**, they will be read as command parameters.</span></span>  
  
 **-**  
 <span data-ttu-id="27268-124">**-Command :** spécifie que l' `sqlps` utilitaire lit l’entrée à partir de l’entrée standard.</span><span class="sxs-lookup"><span data-stu-id="27268-124">**-Command-** specifies that the `sqlps` utility read the input from the standard input.</span></span>  
  
 <span data-ttu-id="27268-125">*script_block* [ **-args**_argument_array_ ]</span><span class="sxs-lookup"><span data-stu-id="27268-125">*script_block* [ **-args**_argument_array_ ]</span></span>  
 <span data-ttu-id="27268-126">Spécifie un bloc de commandes PowerShell à exécuter ; le bloc doit être placé entre des accolades : {}.</span><span class="sxs-lookup"><span data-stu-id="27268-126">Specifies a block of PowerShell commands to run, the block must be enclosed in braces: {}.</span></span> <span data-ttu-id="27268-127">*Script_block* peut être spécifié uniquement quand l' `sqlps` utilitaire est appelé à partir de **PowerShell** ou d’une autre session de l' `sqlps` utilitaire.</span><span class="sxs-lookup"><span data-stu-id="27268-127">*Script_block* can only be specified when the `sqlps` utility is called from either **PowerShell** or another `sqlps` utility session.</span></span> <span data-ttu-id="27268-128">*argument_array* est un tableau de variables PowerShell contenant les arguments pour les commandes PowerShell de *script_block*.</span><span class="sxs-lookup"><span data-stu-id="27268-128">The *argument_array* is an array of PowerShell variables containing the arguments for the PowerShell commands in the *script_block*.</span></span>  
  
 <span data-ttu-id="27268-129">*string* [ *command_parameters* ]</span><span class="sxs-lookup"><span data-stu-id="27268-129">*string* [ *command_parameters* ]</span></span>  
 <span data-ttu-id="27268-130">Spécifie une chaîne qui contient les commandes PowerShell à exécuter.</span><span class="sxs-lookup"><span data-stu-id="27268-130">Specifies a string that contains the PowerShell commands to be run.</span></span> <span data-ttu-id="27268-131">Utilisez le format **« & { *`command`* } »**.</span><span class="sxs-lookup"><span data-stu-id="27268-131">Use the format **"&{*`command`*}"**.</span></span> <span data-ttu-id="27268-132">Les guillemets indiquent une chaîne, tandis que l’opérateur d’appel (&) entraîne l' `sqlps` exécution de la commande par l’utilitaire.</span><span class="sxs-lookup"><span data-stu-id="27268-132">The quotation marks indicate a string, and the invoke operator (&) causes the `sqlps` utility to run the command.</span></span>  
  
 <span data-ttu-id="27268-133">[ **-?**</span><span class="sxs-lookup"><span data-stu-id="27268-133">[ **-?**</span></span><span data-ttu-id="27268-134"> |  **-Help** ]</span><span class="sxs-lookup"><span data-stu-id="27268-134"> | **-Help** ]</span></span>  
 <span data-ttu-id="27268-135">Affiche le récapitulatif de la syntaxe des options de l'utilitaire `sqlps`.</span><span class="sxs-lookup"><span data-stu-id="27268-135">Shows the syntax summary of the `sqlps` utility options.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27268-136">Notes</span><span class="sxs-lookup"><span data-stu-id="27268-136">Remarks</span></span>  
 <span data-ttu-id="27268-137">L' `sqlps` utilitaire démarre l’environnement PowerShell (PowerShell.exe) et charge le [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] module PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27268-137">The `sqlps` utility starts the PowerShell environment (PowerShell.exe) and loads the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell module.</span></span> <span data-ttu-id="27268-138">Le module, également nommé `sqlps` , charge et inscrit ces [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] composants logiciels enfichables PowerShell :</span><span class="sxs-lookup"><span data-stu-id="27268-138">The module, also named `sqlps`, loads and registers these [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell snap-ins:</span></span>  
  
-   <span data-ttu-id="27268-139">Microsoft.SqlServer.Management.PSProvider.dll</span><span class="sxs-lookup"><span data-stu-id="27268-139">Microsoft.SqlServer.Management.PSProvider.dll</span></span>  
  
     <span data-ttu-id="27268-140">Implémente le fournisseur PowerShell pour [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] et les applets de commande associées, comme **Encode-SqlName** et **Decode-SqlName**.</span><span class="sxs-lookup"><span data-stu-id="27268-140">Implements the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell provider and associated cmdlets such as **Encode-SqlName** and **Decode-SqlName**.</span></span>  
  
-   <span data-ttu-id="27268-141">Microsoft.SqlServer.Management.PSSnapin.dll</span><span class="sxs-lookup"><span data-stu-id="27268-141">Microsoft.SqlServer.Management.PSSnapin.dll</span></span>  
  
     <span data-ttu-id="27268-142">Implémente les applets de commande **Invoke-Sqlcmd** et **Invoke-PolicyEvaluation** .</span><span class="sxs-lookup"><span data-stu-id="27268-142">Implements the **Invoke-Sqlcmd** and **Invoke-PolicyEvaluation** cmdlets.</span></span>  
  
 <span data-ttu-id="27268-143">Vous pouvez recourir à l'utilitaire `sqlps` pour effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="27268-143">You can use the `sqlps` utility to do the following:</span></span>  
  
-   <span data-ttu-id="27268-144">exécuter des commandes PowerShell de façon interactive ;</span><span class="sxs-lookup"><span data-stu-id="27268-144">Interactively run PowerShell commands.</span></span>  
  
-   <span data-ttu-id="27268-145">exécuter des fichiers script PowerShell ;</span><span class="sxs-lookup"><span data-stu-id="27268-145">Run PowerShell script files.</span></span>  
  
-   <span data-ttu-id="27268-146">exécuter des applets de commande [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ;</span><span class="sxs-lookup"><span data-stu-id="27268-146">Run [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cmdlets.</span></span>  
  
-   <span data-ttu-id="27268-147">utiliser les chemins d'accès du fournisseur [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pour naviguer dans la hiérarchie des objets [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ;</span><span class="sxs-lookup"><span data-stu-id="27268-147">Use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider paths to navigate through the hierarchy of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects.</span></span>  
  
 <span data-ttu-id="27268-148">Par défaut, l' `sqlps` utilitaire s’exécute avec la stratégie d’exécution de script définie sur **Restricted**.</span><span class="sxs-lookup"><span data-stu-id="27268-148">By default, the `sqlps` utility runs with the scripting execution policy set to **Restricted**.</span></span> <span data-ttu-id="27268-149">Cela empêche l'exécution de scripts PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27268-149">This prevents running any PowerShell scripts.</span></span> <span data-ttu-id="27268-150">Vous pouvez utiliser l’applet de commande **Set-ExecutionPolicy** pour activer l’exécution de scripts signés ou de tout type de script.</span><span class="sxs-lookup"><span data-stu-id="27268-150">You can use the **Set-ExecutionPolicy** cmdlet to enable running signed scripts, or any scripts.</span></span> <span data-ttu-id="27268-151">Exécutez uniquement des scripts provenant de sources fiables et sécurisez tous les fichiers d'entrée et de sortie en utilisant les autorisations NTFS appropriées.</span><span class="sxs-lookup"><span data-stu-id="27268-151">Only run scripts from trusted sources, and secure all input and output files by using the appropriate NTFS permissions.</span></span> <span data-ttu-id="27268-152">Pour plus d'informations sur l'activation de scripts PowerShell, consultez [Exécution de scripts Windows PowerShell](https://www.tech-recipes.com/rx/2513/powershell_enable_script_support/).</span><span class="sxs-lookup"><span data-stu-id="27268-152">For more information about enabling PowerShell scripts, see [Running Windows PowerShell Scripts](https://www.tech-recipes.com/rx/2513/powershell_enable_script_support/).</span></span>  
  
 <span data-ttu-id="27268-153">La version de l'utilitaire `sqlps` dans [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] et [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] a été implémentée en tant que mini-shell Windows PowerShell 1.0.</span><span class="sxs-lookup"><span data-stu-id="27268-153">The version of the `sqlps` utility in [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] and [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] was implemented as a Windows PowerShell 1.0 mini-shell.</span></span> <span data-ttu-id="27268-154">Les mini-shells comportent certaines restrictions, comme le fait de ne pas autoriser les utilisateurs à charger des composants logiciels enfichables autres que ceux chargés par le mini-shell.</span><span class="sxs-lookup"><span data-stu-id="27268-154">Mini-shells have certain restrictions, such as not allowing users to load snap-ins other than those loaded by the mini-shell.</span></span> <span data-ttu-id="27268-155">Ces restrictions ne s'appliquent pas à la version [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] et aux versions ultérieures de l'utilitaire, qui ont été modifiées pour utiliser le module `sqlps`.</span><span class="sxs-lookup"><span data-stu-id="27268-155">These restrictions do not apply to the [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] and higher versions of the utility, which have been changed to use the `sqlps` module.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="27268-156">Exemples</span><span class="sxs-lookup"><span data-stu-id="27268-156">Examples</span></span>  

### <a name="a-run-the-sqlps-utility-in-default-interactive-mode-without-the-copyright-banner"></a><span data-ttu-id="27268-157">R.</span><span class="sxs-lookup"><span data-stu-id="27268-157">A.</span></span> <span data-ttu-id="27268-158">Exécution de l’utilitaire sqlps en mode interactif par défaut, sans bannière de copyright</span><span class="sxs-lookup"><span data-stu-id="27268-158">Run the sqlps utility in default, interactive mode without the copyright banner</span></span>
  
```cmd
sqlps -NoLogo  
```  
  
### <a name="b-run-a-sql-server-powershell-script-from-the-command-prompt"></a><span data-ttu-id="27268-159">B.</span><span class="sxs-lookup"><span data-stu-id="27268-159">B.</span></span> <span data-ttu-id="27268-160">Exécution d'un script SQL Server PowerShell à partir de l'invite de commandes</span><span class="sxs-lookup"><span data-stu-id="27268-160">Run a SQL Server PowerShell script from the command prompt</span></span>
  
```cmd
sqlps -Command "&{.\MyFolder.MyScript.ps1}"  
```  
  
### <a name="c-run-a-sql-server-powershell-script-from-the-command-prompt-and-keep-running-after-the-script-completes"></a><span data-ttu-id="27268-161">C.</span><span class="sxs-lookup"><span data-stu-id="27268-161">C.</span></span> <span data-ttu-id="27268-162">Exécution d'un script SQL Server PowerShell à partir de l'invite de commandes et poursuite de l'exécution une fois le script terminé</span><span class="sxs-lookup"><span data-stu-id="27268-162">Run a SQL Server PowerShell script from the command prompt, and keep running after the script completes</span></span>
  
```cmd
sqlps -NoExit -Command "&{.\MyFolder.MyScript.ps1}"  
```  
  
## <a name="see-also"></a><span data-ttu-id="27268-163">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="27268-163">See Also</span></span>  
 <span data-ttu-id="27268-164">[Activer ou désactiver un protocole réseau de serveur](../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="27268-164">[Enable or Disable a Server Network Protocol](../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md) </span></span>  
 [<span data-ttu-id="27268-165">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="27268-165">SQL Server PowerShell</span></span>](../powershell/sql-server-powershell.md)  
