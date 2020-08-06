---
title: Utiliser sqlcmd avec des variables de script
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- scripts [SQL Server], sqlcmd utility
- variables [SQL Server], scripts
- scripting variables [SQL Server]
- sqlcmd utility, scripts
- setvar command
ms.assetid: 793495ca-cfc9-498d-8276-c44a5d09a92c
author: rothja
ms.author: jroth
ms.openlocfilehash: 8443cb400dc099726ba75bfcec2d38cee4ee2dff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612763"
---
# <a name="use-sqlcmd-with-scripting-variables"></a><span data-ttu-id="ce8d3-102">Utiliser sqlcmd avec des variables de script</span><span class="sxs-lookup"><span data-stu-id="ce8d3-102">Use sqlcmd with Scripting Variables</span></span>
  <span data-ttu-id="ce8d3-103">Les variables utilisées dans les scripts sont appelées des variables de script.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-103">Variables that are used in scripts are called scripting variables.</span></span> <span data-ttu-id="ce8d3-104">Ces variables permettent à un script d'être utilisé dans plusieurs scénarios.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-104">Scripting variables enable one script to be used in multiple scenarios.</span></span> <span data-ttu-id="ce8d3-105">Par exemple, pour exécuter un script sur plusieurs serveurs, vous pouvez utiliser une variable de script pour le nom du serveur au lieu de modifier le script pour chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-105">For example, if you want to run one script against multiple servers, instead of modifying the script for each server, you can use a scripting variable for the server name.</span></span> <span data-ttu-id="ce8d3-106">La modification du nom de serveur fourni à la variable de script permet d'exécuter le même script sur différents serveurs.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-106">By changing the server name supplied to the scripting variable, the same script can be executed on different servers.</span></span>  
  
 <span data-ttu-id="ce8d3-107">Les variables de script peuvent être définies explicitement à l’aide de la commande **setvar** ou implicitement à l’aide de l’option **sqlcmd-v** .</span><span class="sxs-lookup"><span data-stu-id="ce8d3-107">Scripting variables can be defined explicitly by using the **setvar** command, or implicitly by using the **sqlcmd-v** option.</span></span>  
  
 <span data-ttu-id="ce8d3-108">Cette rubrique contient également des exemples de définition de variables d’environnement dans l’invite de commandes Cmd.exe à l’aide de **SET**.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-108">This topic also includes examples defining environmental variables at the Cmd.exe command prompt by using **SET**.</span></span>  
  
## <a name="setting-scripting-variables-by-using-the-setvar-command"></a><span data-ttu-id="ce8d3-109">Définition des variables de script à l'aide de la commande setvar</span><span class="sxs-lookup"><span data-stu-id="ce8d3-109">Setting Scripting Variables by Using the setvar Command</span></span>  
 <span data-ttu-id="ce8d3-110">La commande **setvar** permet de définir des variables de script.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-110">The **setvar** command is used to define scripting variables.</span></span> <span data-ttu-id="ce8d3-111">Les variables définies à l’aide de la commande **setvar** sont stockées en interne.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-111">Variables that are defined by using the **setvar** command are stored internally.</span></span> <span data-ttu-id="ce8d3-112">Il ne faut pas confondre les variables de script avec les variables d’environnement qui sont définies dans l’invite de commandes à l’aide de **SET**.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-112">Scripting variables should not be confused with environment variables that are defined at the command prompt by using **SET**.</span></span> <span data-ttu-id="ce8d3-113">Si un script fait référence à une variable qui n’est pas une variable d’environnement ou qui n’est pas définie à l’aide de **setvar**, un message d’erreur est renvoyé et l’exécution du script s’arrête.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-113">If a script references a variable that is not an environment variable or is not defined by using **setvar**, an error message is returned and the execution of the script will stop.</span></span> <span data-ttu-id="ce8d3-114">Pour plus d’informations, consultez l’option **-b** dans [Utilitaire sqlcmd](../../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="ce8d3-114">For more information, see the **-b** option in [sqlcmd Utility](../../tools/sqlcmd-utility.md).</span></span>  
  
## <a name="variable-precedence-low-to-high"></a><span data-ttu-id="ce8d3-115">Priorité des variables (faible à élevée)</span><span class="sxs-lookup"><span data-stu-id="ce8d3-115">Variable Precedence (Low to High)</span></span>  
 <span data-ttu-id="ce8d3-116">Si plusieurs types de variables ont le même nom, la variable dont la priorité est la plus élevée est utilisée.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-116">If more than one type of variable has the same name, the variable with the highest precedence is used.</span></span>  
  
1.  <span data-ttu-id="ce8d3-117">Variables d'environnement de niveau système</span><span class="sxs-lookup"><span data-stu-id="ce8d3-117">System level environmental variables</span></span>  
  
2.  <span data-ttu-id="ce8d3-118">Variables d'environnement de niveau utilisateur</span><span class="sxs-lookup"><span data-stu-id="ce8d3-118">User level environmental variables</span></span>  
  
3.  <span data-ttu-id="ce8d3-119">Interface de commande (**SET X=Y**) définie dans l’invite de commandes avant le démarrage de **sqlcmd**</span><span class="sxs-lookup"><span data-stu-id="ce8d3-119">Command shell (**SET X=Y**) set at command prompt before starting **sqlcmd**</span></span>  
  
4.  <span data-ttu-id="ce8d3-120">**sqlcmd-v** X=Y</span><span class="sxs-lookup"><span data-stu-id="ce8d3-120">**sqlcmd-v** X=Y</span></span>  
  
5.  <span data-ttu-id="ce8d3-121">**:Setvar** X Y</span><span class="sxs-lookup"><span data-stu-id="ce8d3-121">**:Setvar** X Y</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ce8d3-122">Pour afficher les variables d’environnement, dans le **Panneau de configuration**, ouvrez **Système**, puis cliquez sur l’onglet **Avancé** .</span><span class="sxs-lookup"><span data-stu-id="ce8d3-122">To view the environmental variables, in **Control Panel**, open **System**, and then click the **Advanced** tab.</span></span>  
  
## <a name="implicitly-setting-scripting-variables"></a><span data-ttu-id="ce8d3-123">Définition de variables de script de manière implicite</span><span class="sxs-lookup"><span data-stu-id="ce8d3-123">Implicitly Setting Scripting Variables</span></span>  
 <span data-ttu-id="ce8d3-124">Lorsque vous démarrez **sqlcmd** avec une option associée à une variable **sqlcmd** , la variable **sqlcmd** prend implicitement la valeur spécifiée par l’option.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-124">When you start **sqlcmd** with an option that has a related **sqlcmd** variable, the **sqlcmd** variable is set implicitly to the value that is specified by using the option.</span></span> <span data-ttu-id="ce8d3-125">Dans l'exemple suivant, `sqlcmd` démarre avec l'option `-l` .</span><span class="sxs-lookup"><span data-stu-id="ce8d3-125">In the following example, `sqlcmd` is started with the `-l` option.</span></span> <span data-ttu-id="ce8d3-126">Cette opération définit implicitement la variable SQLLOGINTIMEOUT.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-126">This implicitly sets the SQLLOGINTIMEOUT variable.</span></span>  
  
 `c:\> sqlcmd -l 60`  
  
 <span data-ttu-id="ce8d3-127">Vous pouvez également utiliser l’option **-v** pour définir une variable de script qui existe dans un script.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-127">You can also use the **-v** option to set a scripting variable that exists in a script.</span></span> <span data-ttu-id="ce8d3-128">Dans le script suivant (le nom de fichier est `testscript.sql`), `ColumnName` représente une variable de script.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-128">In the following script (the file name is `testscript.sql`), `ColumnName` is a scripting variable.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `SELECT x.$(ColumnName)`  
  
 `FROM Person.Person x`  
  
 <span data-ttu-id="ce8d3-129">`WHERE c.`BusinessEntityID `< 5;`</span><span class="sxs-lookup"><span data-stu-id="ce8d3-129">`WHERE c.`BusinessEntityID `< 5;`</span></span>  
  
 <span data-ttu-id="ce8d3-130">Vous pouvez ensuite spécifier le nom de la colonne à retourner à l'aide de l'option `-v` :</span><span class="sxs-lookup"><span data-stu-id="ce8d3-130">You can then specify the name of the column that you want returned by using the `-v` option:</span></span>  
  
 `sqlcmd -v ColumnName ="FirstName" -i c:\testscript.sql`  
  
 <span data-ttu-id="ce8d3-131">Pour retourner une autre colonne à l'aide du même script, modifiez la valeur de la variable de script `ColumnName` .</span><span class="sxs-lookup"><span data-stu-id="ce8d3-131">To return a different column by using the same script, change the value of the `ColumnName` scripting variable.</span></span>  
  
 `sqlcmd -v ColumnName ="LastName" -i c:\testscript.sql`  
  
## <a name="guidelines-for-scripting-variable-names-and-values"></a><span data-ttu-id="ce8d3-132">Instructions pour les noms et valeurs de variables de script</span><span class="sxs-lookup"><span data-stu-id="ce8d3-132">Guidelines for Scripting Variable Names and Values</span></span>  
 <span data-ttu-id="ce8d3-133">Lorsque vous nommez des variables de script, tenez compte des instructions suivantes :</span><span class="sxs-lookup"><span data-stu-id="ce8d3-133">Consider the following guidelines when you name scripting variables:</span></span>  
  
-   <span data-ttu-id="ce8d3-134">Les noms de variables ne doivent pas contenir d'espaces blancs ou de guillemets.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-134">Variable names must not contain white space characters or quotation marks.</span></span>  
  
-   <span data-ttu-id="ce8d3-135">Les noms de variables ne peuvent pas avoir la même forme qu’une expression de variable, telle que *$(var)*.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-135">Variable names must not have the same form as a variable expression, such as *$(var)*.</span></span>  
  
-   <span data-ttu-id="ce8d3-136">Les variables de script ne respectent pas la casse.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-136">Scripting variables are case-insensitive</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ce8d3-137">Si aucune valeur n’est affectée à une variable d’environnement **sqlcmd** , la variable est supprimée.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-137">If no value is assigned to a **sqlcmd** environment variable, the variable is removed.</span></span> <span data-ttu-id="ce8d3-138">Si vous déclarez **:setvar VarName** sans spécifier de valeur, la variable est supprimée.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-138">Using **:setvar VarName** without a value clears the variable.</span></span>  
  
 <span data-ttu-id="ce8d3-139">Lorsque vous spécifiez des valeurs pour des variables de script, tenez compte des instructions suivantes :</span><span class="sxs-lookup"><span data-stu-id="ce8d3-139">Consider the following guidelines when you specify values for scripting variables:</span></span>  
  
-   <span data-ttu-id="ce8d3-140">Les valeurs de variable définies à l’aide de **setvar** ou de l’option **-v** doivent être placées entre guillemets si la valeur de type chaîne contient des espaces.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-140">Variable values that are defined by using **setvar** or the **-v** option must be enclosed by quotation marks if the string value contains spaces.</span></span>  
  
-   <span data-ttu-id="ce8d3-141">Si la valeur de variable contient des guillemets, ceux-ci doivent être placés dans une séquence d'échappement.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-141">If quotation marks are part of the variable value, they must be escaped.</span></span> <span data-ttu-id="ce8d3-142">Par exemple :`setvar MyVar "spac""e"`.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-142">For example: :`setvar MyVar "spac""e"`.</span></span>  
  
## <a name="guidelines-for-cmdexe-set-variable-values-and-names"></a><span data-ttu-id="ce8d3-143">Instructions pour utiliser Cmd.exe SET avec les noms et valeurs de variables</span><span class="sxs-lookup"><span data-stu-id="ce8d3-143">Guidelines for Cmd.exe SET Variable Values and Names</span></span>  
 <span data-ttu-id="ce8d3-144">Les variables définies à l’aide de SET appartiennent à l’environnement Cmd.exe et peuvent être référencées par **sqlcmd**.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-144">Variables that are defined by using SET are part of the Cmd.exe environment and can be referenced by **sqlcmd**.</span></span> <span data-ttu-id="ce8d3-145">Tenez compte des recommandations suivantes :</span><span class="sxs-lookup"><span data-stu-id="ce8d3-145">Consider the following guidelines:</span></span>  
  
-   <span data-ttu-id="ce8d3-146">Les noms de variables ne doivent pas contenir d'espaces blancs ou de guillemets.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-146">Variable names must not contain white space characters or quotation marks.</span></span>  
  
-   <span data-ttu-id="ce8d3-147">Les valeurs de variables peuvent contenir des espaces ou des guillemets.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-147">Variable values may contain spaces or quotation marks.</span></span>  
  
## <a name="sqlcmd-scripting-variables"></a><span data-ttu-id="ce8d3-148">Variables de script sqlcmd</span><span class="sxs-lookup"><span data-stu-id="ce8d3-148">sqlcmd Scripting Variables</span></span>  
 <span data-ttu-id="ce8d3-149">Les variables définies par **sqlcmd** sont reconnues comme des variables de script.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-149">Variables that are defined by **sqlcmd** are known as scripting variables.</span></span> <span data-ttu-id="ce8d3-150">Le tableau suivant répertorie les variables de script **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="ce8d3-150">The following table lists **sqlcmd** scripting variables.</span></span>  
  
|<span data-ttu-id="ce8d3-151">Variable</span><span class="sxs-lookup"><span data-stu-id="ce8d3-151">Variable</span></span>|<span data-ttu-id="ce8d3-152">Option connexe</span><span class="sxs-lookup"><span data-stu-id="ce8d3-152">Related option</span></span>|<span data-ttu-id="ce8d3-153">R/W (Lecture/écriture)</span><span class="sxs-lookup"><span data-stu-id="ce8d3-153">R/W</span></span>|<span data-ttu-id="ce8d3-154">Default</span><span class="sxs-lookup"><span data-stu-id="ce8d3-154">Default</span></span>|  
|--------------|--------------------|----------|-------------|  
|<span data-ttu-id="ce8d3-155">SQLCMDUSER\*</span><span class="sxs-lookup"><span data-stu-id="ce8d3-155">SQLCMDUSER\*</span></span>|<span data-ttu-id="ce8d3-156">-U</span><span class="sxs-lookup"><span data-stu-id="ce8d3-156">-U</span></span>|<span data-ttu-id="ce8d3-157">R</span><span class="sxs-lookup"><span data-stu-id="ce8d3-157">R</span></span>|<span data-ttu-id="ce8d3-158">""</span><span class="sxs-lookup"><span data-stu-id="ce8d3-158">""</span></span>|  
|<span data-ttu-id="ce8d3-159">SQLCMDPASSWORD\*</span><span class="sxs-lookup"><span data-stu-id="ce8d3-159">SQLCMDPASSWORD\*</span></span>|<span data-ttu-id="ce8d3-160">-P</span><span class="sxs-lookup"><span data-stu-id="ce8d3-160">-P</span></span>|--|<span data-ttu-id="ce8d3-161">""</span><span class="sxs-lookup"><span data-stu-id="ce8d3-161">""</span></span>|  
|<span data-ttu-id="ce8d3-162">SQLCMDSERVER\*</span><span class="sxs-lookup"><span data-stu-id="ce8d3-162">SQLCMDSERVER\*</span></span>|<span data-ttu-id="ce8d3-163">-S</span><span class="sxs-lookup"><span data-stu-id="ce8d3-163">-S</span></span>|<span data-ttu-id="ce8d3-164">R</span><span class="sxs-lookup"><span data-stu-id="ce8d3-164">R</span></span>|<span data-ttu-id="ce8d3-165">"DefaultLocalInstance"</span><span class="sxs-lookup"><span data-stu-id="ce8d3-165">"DefaultLocalInstance"</span></span>|  
|<span data-ttu-id="ce8d3-166">SQLCMDWORKSTATION</span><span class="sxs-lookup"><span data-stu-id="ce8d3-166">SQLCMDWORKSTATION</span></span>|<span data-ttu-id="ce8d3-167">-H</span><span class="sxs-lookup"><span data-stu-id="ce8d3-167">-H</span></span>|<span data-ttu-id="ce8d3-168">R</span><span class="sxs-lookup"><span data-stu-id="ce8d3-168">R</span></span>|<span data-ttu-id="ce8d3-169">"ComputerName"</span><span class="sxs-lookup"><span data-stu-id="ce8d3-169">"ComputerName"</span></span>|  
|<span data-ttu-id="ce8d3-170">SQLCMDDBNAME</span><span class="sxs-lookup"><span data-stu-id="ce8d3-170">SQLCMDDBNAME</span></span>|<span data-ttu-id="ce8d3-171">-d</span><span class="sxs-lookup"><span data-stu-id="ce8d3-171">-d</span></span>|<span data-ttu-id="ce8d3-172">R</span><span class="sxs-lookup"><span data-stu-id="ce8d3-172">R</span></span>|<span data-ttu-id="ce8d3-173">""</span><span class="sxs-lookup"><span data-stu-id="ce8d3-173">""</span></span>|  
|<span data-ttu-id="ce8d3-174">SQLCMDLOGINTIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ce8d3-174">SQLCMDLOGINTIMEOUT</span></span>|<span data-ttu-id="ce8d3-175">-l</span><span class="sxs-lookup"><span data-stu-id="ce8d3-175">-l</span></span>|<span data-ttu-id="ce8d3-176">R/W (Lecture/écriture)</span><span class="sxs-lookup"><span data-stu-id="ce8d3-176">R/W</span></span>|<span data-ttu-id="ce8d3-177">"8" (secondes)</span><span class="sxs-lookup"><span data-stu-id="ce8d3-177">"8" (seconds)</span></span>|  
|<span data-ttu-id="ce8d3-178">SQLCMDSTATTIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ce8d3-178">SQLCMDSTATTIMEOUT</span></span>|<span data-ttu-id="ce8d3-179">-T</span><span class="sxs-lookup"><span data-stu-id="ce8d3-179">-t</span></span>|<span data-ttu-id="ce8d3-180">R/W (Lecture/écriture)</span><span class="sxs-lookup"><span data-stu-id="ce8d3-180">R/W</span></span>|<span data-ttu-id="ce8d3-181">"0" = Attendre indéfiniment</span><span class="sxs-lookup"><span data-stu-id="ce8d3-181">"0" = wait indefinitely</span></span>|  
|<span data-ttu-id="ce8d3-182">SQLCMDHEADERS</span><span class="sxs-lookup"><span data-stu-id="ce8d3-182">SQLCMDHEADERS</span></span>|<span data-ttu-id="ce8d3-183">-H</span><span class="sxs-lookup"><span data-stu-id="ce8d3-183">-h</span></span>|<span data-ttu-id="ce8d3-184">R/W (Lecture/écriture)</span><span class="sxs-lookup"><span data-stu-id="ce8d3-184">R/W</span></span>|<span data-ttu-id="ce8d3-185">"0"</span><span class="sxs-lookup"><span data-stu-id="ce8d3-185">"0"</span></span>|  
|<span data-ttu-id="ce8d3-186">SQLCMDCOLSEP</span><span class="sxs-lookup"><span data-stu-id="ce8d3-186">SQLCMDCOLSEP</span></span>|<span data-ttu-id="ce8d3-187">-S</span><span class="sxs-lookup"><span data-stu-id="ce8d3-187">-s</span></span>|<span data-ttu-id="ce8d3-188">R/W (Lecture/écriture)</span><span class="sxs-lookup"><span data-stu-id="ce8d3-188">R/W</span></span>|<span data-ttu-id="ce8d3-189">" "</span><span class="sxs-lookup"><span data-stu-id="ce8d3-189">" "</span></span>|  
|<span data-ttu-id="ce8d3-190">SQLCMDCOLWIDTH</span><span class="sxs-lookup"><span data-stu-id="ce8d3-190">SQLCMDCOLWIDTH</span></span>|<span data-ttu-id="ce8d3-191">-w</span><span class="sxs-lookup"><span data-stu-id="ce8d3-191">-w</span></span>|<span data-ttu-id="ce8d3-192">R/W (Lecture/écriture)</span><span class="sxs-lookup"><span data-stu-id="ce8d3-192">R/W</span></span>|<span data-ttu-id="ce8d3-193">"0"</span><span class="sxs-lookup"><span data-stu-id="ce8d3-193">"0"</span></span>|  
|<span data-ttu-id="ce8d3-194">SQLCMDPACKETSIZE</span><span class="sxs-lookup"><span data-stu-id="ce8d3-194">SQLCMDPACKETSIZE</span></span>|<span data-ttu-id="ce8d3-195">-a</span><span class="sxs-lookup"><span data-stu-id="ce8d3-195">-a</span></span>|<span data-ttu-id="ce8d3-196">R</span><span class="sxs-lookup"><span data-stu-id="ce8d3-196">R</span></span>|<span data-ttu-id="ce8d3-197">"4096"</span><span class="sxs-lookup"><span data-stu-id="ce8d3-197">"4096"</span></span>|  
|<span data-ttu-id="ce8d3-198">SQLCMDERRORLEVEL</span><span class="sxs-lookup"><span data-stu-id="ce8d3-198">SQLCMDERRORLEVEL</span></span>|<span data-ttu-id="ce8d3-199">-M</span><span class="sxs-lookup"><span data-stu-id="ce8d3-199">-m</span></span>|<span data-ttu-id="ce8d3-200">R/W (Lecture/écriture)</span><span class="sxs-lookup"><span data-stu-id="ce8d3-200">R/W</span></span>|<span data-ttu-id="ce8d3-201">"0"</span><span class="sxs-lookup"><span data-stu-id="ce8d3-201">"0"</span></span>|  
|<span data-ttu-id="ce8d3-202">SQLCMDMAXVARTYPEWIDTH</span><span class="sxs-lookup"><span data-stu-id="ce8d3-202">SQLCMDMAXVARTYPEWIDTH</span></span>|<span data-ttu-id="ce8d3-203">-y</span><span class="sxs-lookup"><span data-stu-id="ce8d3-203">-y</span></span>|<span data-ttu-id="ce8d3-204">R/W (Lecture/écriture)</span><span class="sxs-lookup"><span data-stu-id="ce8d3-204">R/W</span></span>|<span data-ttu-id="ce8d3-205">"256"</span><span class="sxs-lookup"><span data-stu-id="ce8d3-205">"256"</span></span>|  
|<span data-ttu-id="ce8d3-206">SQLCMDMAXFIXEDTYPEWIDTH</span><span class="sxs-lookup"><span data-stu-id="ce8d3-206">SQLCMDMAXFIXEDTYPEWIDTH</span></span>|<span data-ttu-id="ce8d3-207">-y</span><span class="sxs-lookup"><span data-stu-id="ce8d3-207">-Y</span></span>|<span data-ttu-id="ce8d3-208">R/W (Lecture/écriture)</span><span class="sxs-lookup"><span data-stu-id="ce8d3-208">R/W</span></span>|<span data-ttu-id="ce8d3-209">"0" = illimitée</span><span class="sxs-lookup"><span data-stu-id="ce8d3-209">"0" = unlimited</span></span>|  
|<span data-ttu-id="ce8d3-210">SQLCMDEDITOR</span><span class="sxs-lookup"><span data-stu-id="ce8d3-210">SQLCMDEDITOR</span></span>||<span data-ttu-id="ce8d3-211">R/W (Lecture/écriture)</span><span class="sxs-lookup"><span data-stu-id="ce8d3-211">R/W</span></span>|<span data-ttu-id="ce8d3-212">"edit.com"</span><span class="sxs-lookup"><span data-stu-id="ce8d3-212">"edit.com"</span></span>|  
|<span data-ttu-id="ce8d3-213">SQLCMDINI</span><span class="sxs-lookup"><span data-stu-id="ce8d3-213">SQLCMDINI</span></span>||<span data-ttu-id="ce8d3-214">R</span><span class="sxs-lookup"><span data-stu-id="ce8d3-214">R</span></span>|<span data-ttu-id="ce8d3-215">""</span><span class="sxs-lookup"><span data-stu-id="ce8d3-215">""</span></span>|  
  
 <span data-ttu-id="ce8d3-216">\*SQLCMDUSER, SQLCMDPASSWORD et SQLCMDSERVER sont définis lorsque **: Connect** est utilisé.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-216">\* SQLCMDUSER, SQLCMDPASSWORD and SQLCMDSERVER are set when **:Connect** is used.</span></span>  
  
 <span data-ttu-id="ce8d3-217">R indique que la valeur ne peut être définie qu'une seule fois lors de l'initialisation du programme.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-217">R indicates the value can only be set one time during program initialization.</span></span>  
  
 <span data-ttu-id="ce8d3-218">R/W indique que la valeur peut être réinitialisée à l’aide de la commande **setvar** et que les commandes suivantes utiliseront la nouvelle valeur.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-218">R/W indicates that the value can be reset by using the **setvar** command and subsequent commands will use the new value.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="ce8d3-219">Exemples</span><span class="sxs-lookup"><span data-stu-id="ce8d3-219">Examples</span></span>  
  
### <a name="a-using-the-setvar-command-in-a-script"></a><span data-ttu-id="ce8d3-220">R.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-220">A.</span></span> <span data-ttu-id="ce8d3-221">Utilisation de la commande setvar dans un script</span><span class="sxs-lookup"><span data-stu-id="ce8d3-221">Using the setvar command in a script</span></span>  
 <span data-ttu-id="ce8d3-222">De nombreuses options de **sqlcmd** peuvent être contrôlées dans un script à l’aide de la commande **setvar** .</span><span class="sxs-lookup"><span data-stu-id="ce8d3-222">Many **sqlcmd** options can be controlled in a script by using the **setvar** command.</span></span> <span data-ttu-id="ce8d3-223">Dans l'exemple suivant, le script `test.sql` est créé ; dans ce dernier, la variable `SQLCMDLOGINTIMEOUT` a la valeur `60` secondes et une variable de script, `server`, a la valeur `testserver`.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-223">In the following example, the script `test.sql` is created in which the `SQLCMDLOGINTIMEOUT` variable is set to `60` seconds and another scripting variable, `server`, is set to `testserver`.</span></span> <span data-ttu-id="ce8d3-224">Le code suivant figure dans le fichier `test.sql`.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-224">The following code is in `test.sql`.</span></span>  
  
 `:setvar SQLCMDLOGINTIMEOUT 60`  
  
 `:setvar server "testserver"`  
  
 `:connect $(server) -l $(SQLCMDLOGINTIMEOUT)`  
  
 `USE AdventureWorks2012;`  
  
 `SELECT FirstName, LastName`  
  
 `FROM Person.Person;`  
  
 `The script is then called by using sqlcmd:`  
  
 `sqlcmd -i c:\test.sql`  
  
### <a name="b-using-the-setvar-command-interactively"></a><span data-ttu-id="ce8d3-225">B.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-225">B.</span></span> <span data-ttu-id="ce8d3-226">Utilisation de la commande setvar de façon interactive</span><span class="sxs-lookup"><span data-stu-id="ce8d3-226">Using the setvar command interactively</span></span>  
 <span data-ttu-id="ce8d3-227">L'exemple suivant illustre la définition d'une variable de script de façon interactive à l'aide de la commande `setvar` .</span><span class="sxs-lookup"><span data-stu-id="ce8d3-227">The following example shows how to set a scripting variable interactively by using the `setvar` command.</span></span>  
  
 `sqlcmd`  
  
 `:setvar  MYDATABASE AdventureWorks2012`  
  
 `USE $(MYDATABASE);`  
  
 `GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `Changed database context to 'AdventureWorks2012'`  
  
 `1>`  
  
### <a name="c-using-command-prompt-environment-variables-within-sqlcmd"></a><span data-ttu-id="ce8d3-228">C.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-228">C.</span></span> <span data-ttu-id="ce8d3-229">Utilisation de variables d'environnement à l'invite de commandes dans sqlcmd</span><span class="sxs-lookup"><span data-stu-id="ce8d3-229">Using command prompt environment variables within sqlcmd</span></span>  
 <span data-ttu-id="ce8d3-230">Dans l’exemple suivant, quatre variables d’environnement ( `are` ) sont définies puis appelées depuis `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-230">In the following example, four environment variables `are` set and then called from `sqlcmd`.</span></span>  
  
 `C:\>SET tablename=Person.Person`  
  
 `C:\>SET col1=FirstName`  
  
 `C:\>SET col2=LastName`  
  
 `C:\>SET title=Ms.`  
  
 `C:\>sqlcmd -d AdventureWorks2012`  
  
 `1> SELECT TOP 5 $(col1) + ' ' + $(col2) AS Name`  
  
 `2> FROM $(tablename)`  
  
 `3> WHERE Title ='$(title)'`  
  
 `4> GO`  
  
### <a name="d-using-user-level-environment-variables-within-sqlcmd"></a><span data-ttu-id="ce8d3-231">D.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-231">D.</span></span> <span data-ttu-id="ce8d3-232">Utilisation de variables d'environnement au niveau utilisateur dans sqlcmd</span><span class="sxs-lookup"><span data-stu-id="ce8d3-232">Using user-level environment variables within sqlcmd</span></span>  
 <span data-ttu-id="ce8d3-233">Dans l'exemple suivant, la variable d'environnement au niveau utilisateur `%Temp%` est définie à l'invite de commandes et transmise au fichier d'entrée `sqlcmd` .</span><span class="sxs-lookup"><span data-stu-id="ce8d3-233">In the following example the user-level environmental variable `%Temp%` is set at the command prompt and passed to the `sqlcmd` input file.</span></span> <span data-ttu-id="ce8d3-234">Pour obtenir la variable d’environnement au niveau utilisateur, dans le **Panneau de configuration**, double-cliquez sur **Système**.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-234">To obtain the user-level environment variable, in **Control Panel**, double-click **System**.</span></span> <span data-ttu-id="ce8d3-235">Cliquez sur l'onglet **Avancé** , puis sur **Variables d'environnement**.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-235">Click the **Advance** tab, and then click **Environment Variables**.</span></span>  
  
 <span data-ttu-id="ce8d3-236">Le code suivant figure dans le fichier d'entrée `c:\testscript.txt`:</span><span class="sxs-lookup"><span data-stu-id="ce8d3-236">The following code is in the input file `c:\testscript.txt`:</span></span>  
  
 `:OUT $(MyTempDirectory)`  
  
 `USE AdventureWorks2012;`  
  
 `SELECT FirstName`  
  
 `FROM AdventureWorks2012.Person.Person`  
  
 <span data-ttu-id="ce8d3-237">`WHERE BusinessEntityID` `< 5;`</span><span class="sxs-lookup"><span data-stu-id="ce8d3-237">`WHERE BusinessEntityID` `< 5;`</span></span>  
  
 <span data-ttu-id="ce8d3-238">Le code suivant est entré à l'invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="ce8d3-238">This following code is entered at the command prompt:</span></span>  
  
 `C:\ >SET MyTempDirectory=%Temp%\output.txt`  
  
 `C:\ >sqlcmd -i C:\testscript.txt`  
  
 <span data-ttu-id="ce8d3-239">Le résultat suivant est envoyé dans le fichier de sortie C:\Documents and Settings\\<utilisateur\>\Local Settings\Temp\output.txt.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-239">The following result is sent to the output file C:\Documents and Settings\\<user\>\Local Settings\Temp\output.txt.</span></span>  
  
 `Changed database context to 'AdventureWorks2012'.`  
  
 `FirstName`  
  
 `--------------------------------------------------`  
  
 `Gustavo`  
  
 `Catherine`  
  
 `Kim`  
  
 `Humberto`  
  
 `(4 rows affected)`  
  
### <a name="e-using-a-startup-script"></a><span data-ttu-id="ce8d3-240">E.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-240">E.</span></span> <span data-ttu-id="ce8d3-241">Utilisation d'un script de démarrage</span><span class="sxs-lookup"><span data-stu-id="ce8d3-241">Using a startup script</span></span>  
 <span data-ttu-id="ce8d3-242">Un script de démarrage **sqlcmd** est exécuté au démarrage de **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="ce8d3-242">A **sqlcmd** startup script is executed when **sqlcmd** is started.</span></span> <span data-ttu-id="ce8d3-243">L'exemple suivant définit la variable d'environnement `SQLCMDINI`.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-243">The following example sets the environment variable `SQLCMDINI`.</span></span> <span data-ttu-id="ce8d3-244">Voici le contenu de `init.sql.`</span><span class="sxs-lookup"><span data-stu-id="ce8d3-244">This is the contents of `init.sql.`</span></span>  
  
 `SET NOCOUNT ON`  
  
 `GO`  
  
 `DECLARE @nt_username nvarchar(128)`  
  
 `SET @nt_username = (SELECT rtrim(convert(nvarchar(128), nt_username))`  
  
 `FROM sys.dm_exec_sessions WHERE spid = @@SPID)`  
  
 `SELECT  @nt_username + ' is connected to ' +`  
  
 `rtrim(CONVERT(nvarchar(20), SERVERPROPERTY('servername'))) +`  
  
 `' (' +`  
  
 `rtrim(CONVERT(nvarchar(20), SERVERPROPERTY('productversion'))) +`  
  
 `')'`  
  
 `:setvar SQLCMDMAXFIXEDTYPEWIDTH 100`  
  
 `SET NOCOUNT OFF`  
  
 `GO`  
  
 `:setvar SQLCMDMAXFIXEDTYPEWIDTH`  
  
 <span data-ttu-id="ce8d3-245">Ce code appelle le fichier `init.sql` au démarrage de `sqlcmd` .</span><span class="sxs-lookup"><span data-stu-id="ce8d3-245">This calls the `init.sql` file when `sqlcmd` is started.</span></span>  
  
 `C:\> SET sqlcmdini=c:\init.sql`  
  
 `>1 Sqlcmd`  
  
 <span data-ttu-id="ce8d3-246">Il s'agit de la sortie.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-246">This is the output.</span></span>  
  
 `>1 < user > is connected to < server > (9.00.2047.00)`  
  
> [!NOTE]  
>  <span data-ttu-id="ce8d3-247">L’option **-X** désactive la fonctionnalité de script de démarrage.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-247">The **-X** option disables the startup script feature.</span></span>  
  
### <a name="f-variable-expansion"></a><span data-ttu-id="ce8d3-248">F.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-248">F.</span></span> <span data-ttu-id="ce8d3-249">Expansion de variables</span><span class="sxs-lookup"><span data-stu-id="ce8d3-249">Variable expansion</span></span>  
 <span data-ttu-id="ce8d3-250">l’exemple suivant illustre l’utilisation de données sous la forme d’une variable **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="ce8d3-250">The following example shows working with data in the form of a **sqlcmd** variable.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `CREATE TABLE AdventureWorks2012.dbo.VariableTest`  
  
 `(`  
  
 `Col1 nvarchar(50)`  
  
 `);`  
  
 `GO`  
  
 <span data-ttu-id="ce8d3-251">Insérez une ligne dans `Col1` de `dbo.VariableTest` qui contient la valeur `$(tablename)`.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-251">Insert one row into `Col1` of `dbo.VariableTest` that contains the value `$(tablename)`.</span></span>  
  
 `INSERT INTO AdventureWorks2012.dbo.VariableTest(Col1)`  
  
 `VALUES('$(tablename)');`  
  
 `GO`  
  
 <span data-ttu-id="ce8d3-252">À l'invite de commandes `sqlcmd` , si aucune variable n'a la valeur `$(tablename)`, les instructions suivantes retournent la ligne.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-252">At the `sqlcmd` prompt, when no variable is set equal to `$(tablename)`, the following statements return the row.</span></span>  
  
 `C:\> sqlcmd`  
  
 `>1 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = '$(tablename)';`  
  
 `>2 GO`  
  
 `>3 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = N'$(tablename)';`  
  
 `>4 GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `>1 Col1`  
  
 `>2 ------------------`  
  
 `>3 $(tablename)`  
  
 `>4`  
  
 `>5 (1 rows affected)`  
  
 <span data-ttu-id="ce8d3-253">La variable `MyVar` a la valeur `$(tablename)`.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-253">Given the variable `MyVar` is set to `$(tablename)`.</span></span>  
  
 `>6 :setvar MyVar $(tablename)`  
  
 <span data-ttu-id="ce8d3-254">Ces instructions retournent la ligne ainsi que le message « La variable de script « tablename » n'est pas définie ».</span><span class="sxs-lookup"><span data-stu-id="ce8d3-254">These statements return the row and also return the message "'tablename' scripting variable not defined."</span></span>  
  
 `>6 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = '$(tablename)';`  
  
 `>7 GO`  
  
 `>1 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = N'$(tablename)';`  
  
 `>2 GO`  
  
 <span data-ttu-id="ce8d3-255">Ces instructions retournent la ligne.</span><span class="sxs-lookup"><span data-stu-id="ce8d3-255">These statements return the row.</span></span>  
  
 `>1 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = '$(MyVar)';`  
  
 `>2 GO`  
  
 `>1 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = N'$(MyVar)';`  
  
 `>2 GO`  
  
## <a name="see-also"></a><span data-ttu-id="ce8d3-256">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ce8d3-256">See Also</span></span>  
 <span data-ttu-id="ce8d3-257">[Utiliser l’utilitaire sqlcmd](sqlcmd-use-the-utility.md) </span><span class="sxs-lookup"><span data-stu-id="ce8d3-257">[Use the sqlcmd Utility](sqlcmd-use-the-utility.md) </span></span>  
 <span data-ttu-id="ce8d3-258">[Utilitaire sqlcmd](../../tools/sqlcmd-utility.md) </span><span class="sxs-lookup"><span data-stu-id="ce8d3-258">[sqlcmd Utility](../../tools/sqlcmd-utility.md) </span></span>  
 [<span data-ttu-id="ce8d3-259">Référence de l’utilitaire d’invite de commandes &#40;moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="ce8d3-259">Command Prompt Utility Reference &#40;Database Engine&#41;</span></span>](../../tools/command-prompt-utility-reference-database-engine.md)  
  
  
