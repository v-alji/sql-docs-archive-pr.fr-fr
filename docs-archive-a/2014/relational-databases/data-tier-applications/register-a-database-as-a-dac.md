---
title: Inscrire une base de données en tant que DAC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.registerdacwizard.registerdac.f1
- sql12.swb.registerdacwizard.summary.f1
- sql12.swb.registerdacwizard.introduction.f1
- sql12.swb.registerdacwizard.setproperties.f1
helpviewer_keywords:
- wizard [DAC], register
- How to [DAC], register
- register DAC
- data-tier application [SQL Server], register
ms.assetid: 08e52aa6-12f3-41dd-a793-14b99a083fd5
author: stevestein
ms.author: sstein
ms.openlocfilehash: c4e8061362d013dbfbd6cbaba47d0f2cb4d8e83b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614635"
---
# <a name="register-a-database-as-a-dac"></a><span data-ttu-id="725f8-102">Inscrire une base de données en tant que DAC</span><span class="sxs-lookup"><span data-stu-id="725f8-102">Register a Database As a DAC</span></span>
  <span data-ttu-id="725f8-103">Utilisez l' **Assistant inscrire l’application de la couche données** ou un script Windows PowerShell pour générer une définition d’application de la couche données (DAC) qui décrit les objets d’une base de données existante et enregistrez la définition de la DAC dans la `msdb` base de données système (**Master** dans [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="725f8-103">Use either the **Register Data-tier Application Wizard** or a Windows PowerShell script to build a data-tier application (DAC) definition that describes the objects in an existing database, and register the DAC definition in the `msdb` system database (**master** in [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)]).</span></span>  
  
-   <span data-ttu-id="725f8-104">**Avant de commencer :**  [Limitations et restrictions](#LimitationsRestrictions), [Autorisations](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="725f8-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="725f8-105">**Pour mettre à niveau une DAC à l’aide de** :  [l’Assistant d’inscription de l’application de la couche Données](#UsingRegisterDACWizard), [PowerShell](#RegisterDACPowerShell)</span><span class="sxs-lookup"><span data-stu-id="725f8-105">**To upgrade a DAC, using:**  [The Register Data-tier Application Wizard](#UsingRegisterDACWizard), [PowerShell](#RegisterDACPowerShell)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="725f8-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="725f8-106">Before You Begin</span></span>  
 <span data-ttu-id="725f8-107">Le processus d'inscription crée une définition de la DAC qui définit les objets de la base de données.</span><span class="sxs-lookup"><span data-stu-id="725f8-107">The registration process creates a DAC definition that defines the objects in the database.</span></span> <span data-ttu-id="725f8-108">La combinaison de la définition de la DAC et de la base de données forme une instance DAC.</span><span class="sxs-lookup"><span data-stu-id="725f8-108">The combination of the DAC definition and the database form a DAC instance.</span></span> <span data-ttu-id="725f8-109">Si vous inscrivez une base de données comme une DAC sur une instance gérée du moteur de base de données, la DAC inscrite est incorporée dans l'utilitaire SQL Server la prochaine fois que le jeu d'éléments de collecte de l'utilitaire est envoyé de l'instance au point de contrôle de l'utilitaire.</span><span class="sxs-lookup"><span data-stu-id="725f8-109">If you register a database as a DAC on a managed instance of the Database Engine, the registered DAC will be incorporated into the SQL Server Utility the next time the utility collection set is sent from the instance to the Utility Control Point.</span></span> <span data-ttu-id="725f8-110">La DAC est ensuite présente dans le nœud **Application de la couche Données déployée** au sein de l’**Explorateur d’utilitaire** [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] et est signalée dans la page de détails pour **Application de la couche Données déployée**.</span><span class="sxs-lookup"><span data-stu-id="725f8-110">The DAC will then be present in the **Deployed Data-tier Applications** node of the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] **Utility Explorer** and reported in the **Deployed Data-tier Applications** details page.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="725f8-111">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="725f8-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="725f8-112">L'inscription de la DAC ne peut être exécutée que sur une base de données dans [!INCLUDE[ssSDS](../../includes/sssds-md.md)]ou [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="725f8-112">DAC registration can only be performed on a database in [!INCLUDE[ssSDS](../../includes/sssds-md.md)], or [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) or later.</span></span> <span data-ttu-id="725f8-113">L'inscription de la DAC ne peut pas être effectuée si une DAC est déjà inscrite pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="725f8-113">DAC registration cannot be performed if a DAC is already registered for the database.</span></span> <span data-ttu-id="725f8-114">Par exemple, si la base de données a été créée en déployant une DAC, vous ne pouvez pas exécuter l’ **Assistant Inscrire l’application de la couche Données**.</span><span class="sxs-lookup"><span data-stu-id="725f8-114">For example, if the database was created by deploying a DAC, you cannot run the **Register Data-tier Application Wizard**.</span></span>  
  
 <span data-ttu-id="725f8-115">Vous ne pouvez pas inscrire de DAC si la base de données a des objets qui ne sont pas pris en charge dans une DAC, ou des utilisateurs à relation contenant-contenu.</span><span class="sxs-lookup"><span data-stu-id="725f8-115">You cannot register a DAC if the database has objects that are not supported in a DAC, or contained users.</span></span> <span data-ttu-id="725f8-116">Pour plus d'informations sur les types d'objets pris en charge dans une DAC, consultez [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span><span class="sxs-lookup"><span data-stu-id="725f8-116">For more information about the types of objects supported in a DAC, see [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="725f8-117">Autorisations</span><span class="sxs-lookup"><span data-stu-id="725f8-117">Permissions</span></span>  
 <span data-ttu-id="725f8-118">L’inscription d’une DAC dans une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] nécessite au moins les autorisations ALTER ANY LOGIN et VIEW DEFINITION de l’étendue de la base de données, les autorisations SELECT sur **sys.sql_expression_dependencies**, et l’appartenance au rôle serveur fixe **dbcreator** .</span><span class="sxs-lookup"><span data-stu-id="725f8-118">Registering a DAC in an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] requires at least ALTER ANY LOGIN and database scope VIEW DEFINITION permissions, SELECT permissions on **sys.sql_expression_dependencies**, and membership in the **dbcreator** fixed server role.</span></span> <span data-ttu-id="725f8-119">Les membres du rôle serveur fixe **sysadmin** ou le compte d’administrateur système intégré de SQL Server nommé **sa** peuvent également inscrire une DAC.</span><span class="sxs-lookup"><span data-stu-id="725f8-119">Members of the **sysadmin** fixed server role or the built-in SQL Server system administrator account named **sa** can also register a DAC.</span></span> <span data-ttu-id="725f8-120">L'inscription d'une DAC qui ne contient pas de connexions dans [!INCLUDE[ssSDS](../../includes/sssds-md.md)] requiert l'appartenance aux rôles **dbmanager** ou **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="725f8-120">Registering a DAC that does not contain logins in [!INCLUDE[ssSDS](../../includes/sssds-md.md)] requires membership in the **dbmanager** or **serveradmin** roles.</span></span> <span data-ttu-id="725f8-121">L'inscription d'une DAC comportant des connexions dans [!INCLUDE[ssSDS](../../includes/sssds-md.md)] requiert l'appartenance aux rôles **loginmanager** ou **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="725f8-121">Registering a DAC that contains logins in [!INCLUDE[ssSDS](../../includes/sssds-md.md)] requires membership in the **loginmanager** or **serveradmin** roles.</span></span>  
  
##  <a name="using-the-register-data-tier-application-wizard"></a><a name="UsingRegisterDACWizard"></a> <span data-ttu-id="725f8-122">Utilisation de l'Assistant Inscrire l'application de la couche Données</span><span class="sxs-lookup"><span data-stu-id="725f8-122">Using the Register Data-tier Application Wizard</span></span>  
 <span data-ttu-id="725f8-123">**Pour inscrire une DAC à l'aide d'un Assistant**</span><span class="sxs-lookup"><span data-stu-id="725f8-123">**To Register a DAC Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="725f8-124">Dans l' **Explorateur d'objets**, développez le nœud pour l'instance qui contient la base de données à inscrire en tant que DAC.</span><span class="sxs-lookup"><span data-stu-id="725f8-124">In **Object Explorer**, expand the node for the instance containing the database to be registered as a DAC.</span></span>  
  
2.  <span data-ttu-id="725f8-125">Développez le nœud **Bases de données** .</span><span class="sxs-lookup"><span data-stu-id="725f8-125">Expand the **Databases** node.</span></span>  
  
3.  <span data-ttu-id="725f8-126">Cliquez avec le bouton droit sur la base de données à inscrire, pointez sur **Tâches**, puis sélectionnez **Inscrire en tant qu’application de la couche Données**.</span><span class="sxs-lookup"><span data-stu-id="725f8-126">Right-click the database to be registered, point to **Tasks**, and then select **Register As Data-tier Application...**</span></span>  
  
4.  <span data-ttu-id="725f8-127">Renseignez les boîtes de dialogue de l'Assistant :</span><span class="sxs-lookup"><span data-stu-id="725f8-127">Complete the wizard dialogs:</span></span>  
  
    1.  [<span data-ttu-id="725f8-128">Page Introduction</span><span class="sxs-lookup"><span data-stu-id="725f8-128">Introduction Page</span></span>](#Introduction)  
  
    2.  [<span data-ttu-id="725f8-129">Page Définir les propriétés</span><span class="sxs-lookup"><span data-stu-id="725f8-129">Set Properties Page</span></span>](#Set_properties)  
  
    3.  [<span data-ttu-id="725f8-130">Page Validation et résumé</span><span class="sxs-lookup"><span data-stu-id="725f8-130">Validation and Summary Page</span></span>](#Summary)  
  
    4.  [<span data-ttu-id="725f8-131">Page Inscrire la DAC</span><span class="sxs-lookup"><span data-stu-id="725f8-131">Register DAC Page</span></span>](#Register)  
  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="725f8-132">Page Introduction</span><span class="sxs-lookup"><span data-stu-id="725f8-132">Introduction Page</span></span>  
 <span data-ttu-id="725f8-133">Cette page décrit les étapes de l'inscription d'une application de la couche Données.</span><span class="sxs-lookup"><span data-stu-id="725f8-133">This page describes the steps for registering a data-tier application.</span></span>  
  
 <span data-ttu-id="725f8-134">**Ne plus afficher cette page.**</span><span class="sxs-lookup"><span data-stu-id="725f8-134">**Do not show this page again.**</span></span> <span data-ttu-id="725f8-135">- Cochez la case pour ne plus afficher la page à l'avenir.</span><span class="sxs-lookup"><span data-stu-id="725f8-135">- Click the check box to stop the page from being displayed in the future.</span></span>  
  
 <span data-ttu-id="725f8-136">**Suivant >** : passe à la page **Définir les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="725f8-136">**Next >** - Proceeds to the **Set Properties** page.</span></span>  
  
 <span data-ttu-id="725f8-137">**Annuler** : termine l’Assistant sans inscrire une DAC.</span><span class="sxs-lookup"><span data-stu-id="725f8-137">**Cancel** - Terminates the wizard without registering a DAC.</span></span>  
  
##  <a name="set-properties-page"></a><a name="Set_properties"></a> <span data-ttu-id="725f8-138">Page Définir les propriétés</span><span class="sxs-lookup"><span data-stu-id="725f8-138">Set Properties Page</span></span>  
 <span data-ttu-id="725f8-139">Utilisez cette page pour spécifier des propriétés au niveau de la DAC telles que le nom de l'application et sa version.</span><span class="sxs-lookup"><span data-stu-id="725f8-139">Use this page to specify DAC-level properties such as the application name and version.</span></span>  
  
 <span data-ttu-id="725f8-140">**Nom de l'application.**</span><span class="sxs-lookup"><span data-stu-id="725f8-140">**Application name.**</span></span> <span data-ttu-id="725f8-141">- Chaîne qui spécifie le nom utilisé pour identifier la définition de la DAC. Le champ est renseigné avec le nom de la base de données.</span><span class="sxs-lookup"><span data-stu-id="725f8-141">- A string that specifies the name used to identify the DAC definition, the field is been populated with the database name.</span></span>  
  
 <span data-ttu-id="725f8-142">**Version.**</span><span class="sxs-lookup"><span data-stu-id="725f8-142">**Version.**</span></span> <span data-ttu-id="725f8-143">- Valeur numérique qui identifie la version de la DAC.</span><span class="sxs-lookup"><span data-stu-id="725f8-143">- A numeric value that identifies the version of the DAC.</span></span> <span data-ttu-id="725f8-144">La version de la DAC est utilisée dans Visual Studio pour identifier la version de la DAC sur laquelle les développeurs travaillent.</span><span class="sxs-lookup"><span data-stu-id="725f8-144">The DAC version is used in Visual Studio to identify the version of the DAC that developers are working on.</span></span> <span data-ttu-id="725f8-145">Lors du déploiement d’une DAC, la version est stockée dans la `msdb` base de données et peut être affichée ultérieurement sous le nœud applications de la **couche données** dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="725f8-145">When deploying a DAC, the version is stored in the `msdb` database and can later be viewed under the **Data-tier Applications** node in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="725f8-146">**Description.**</span><span class="sxs-lookup"><span data-stu-id="725f8-146">**Description.**</span></span> <span data-ttu-id="725f8-147">- Facultatif.</span><span class="sxs-lookup"><span data-stu-id="725f8-147">- Optional.</span></span> <span data-ttu-id="725f8-148">Texte qui explique l'objectif de la DAC.</span><span class="sxs-lookup"><span data-stu-id="725f8-148">Text that explains the purpose of the DAC.</span></span> <span data-ttu-id="725f8-149">Lors du déploiement d’une DAC, la description est stockée dans la `msdb` base de données et peut être affichée ultérieurement sous le nœud applications de la **couche données** dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="725f8-149">When deploying a DAC, the description is stored in the `msdb` database and can later be viewed under the **Data-tier Applications** node in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="725f8-150">\*\* \< Précédent\*\* : vous renvoie à la page **Introduction** .</span><span class="sxs-lookup"><span data-stu-id="725f8-150">**\< Previous** - Returns you to the **Introduction** page.</span></span>  
  
 <span data-ttu-id="725f8-151">**Suivant >** : vérifie qu’une DAC peut être générée à partir des objets de la base de données et affiche les résultats dans la page **Validation et résumé**.</span><span class="sxs-lookup"><span data-stu-id="725f8-151">**Next >** - Verifies that a DAC can be built from the objects in the database, and displays the results in the **Validation and Summary** page.</span></span>  
  
 <span data-ttu-id="725f8-152">**Annuler** : termine l’Assistant sans inscrire la DAC.</span><span class="sxs-lookup"><span data-stu-id="725f8-152">**Cancel** - Terminates the wizard without registering the DAC.</span></span>  
  
##  <a name="validation-and-summary-page"></a><a name="Summary"></a> <span data-ttu-id="725f8-153">Page Validation et résumé</span><span class="sxs-lookup"><span data-stu-id="725f8-153">Validation and Summary Page</span></span>  
 <span data-ttu-id="725f8-154">Utilisez cette page pour examiner les mesures que l'Assistant prendra lors de l'inscription de la DAC.</span><span class="sxs-lookup"><span data-stu-id="725f8-154">Use this page to review the actions the wizard will take when registering the DAC.</span></span> <span data-ttu-id="725f8-155">La page passe par trois états alors qu'elle vérifie qu'une DAC peut être générée à partir des objets de la base de données.</span><span class="sxs-lookup"><span data-stu-id="725f8-155">The page transitions through three states as it verifies that a DAC can be built from the objects in the database.</span></span>  
  
### <a name="retrieving-objects"></a><span data-ttu-id="725f8-156">Récupération d'objets</span><span class="sxs-lookup"><span data-stu-id="725f8-156">Retrieving Objects</span></span>  
 <span data-ttu-id="725f8-157">**Récupération d'objets de bases de données et de serveurs.**</span><span class="sxs-lookup"><span data-stu-id="725f8-157">**Retrieving database and server objects.**</span></span> <span data-ttu-id="725f8-158">- Affiche une barre de progression au fur et à mesure que l'Assistant récupère tous les objets requis de la base de données et de l'instance du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="725f8-158">- Displays a progress bar as the wizard retrieves all of the required objects from the database and the instance of the Database Engine.</span></span>  
  
 <span data-ttu-id="725f8-159">\*\* \< Précédent\*\* : vous renvoie à la page **définir les propriétés** pour modifier vos entrées.</span><span class="sxs-lookup"><span data-stu-id="725f8-159">**\< Previous** - Returns you to the **Set Properties** page to change your entries.</span></span>  
  
 <span data-ttu-id="725f8-160">**Suivant >** : inscrit la DAC et affiche les résultats dans la page **Inscrire la DAC**.</span><span class="sxs-lookup"><span data-stu-id="725f8-160">**Next >** - Registers the DAC and displays the results in the **Register DAC** page.</span></span>  
  
 <span data-ttu-id="725f8-161">**Annuler** : termine l’Assistant sans inscrire la DAC.</span><span class="sxs-lookup"><span data-stu-id="725f8-161">**Cancel** - Terminates the wizard without registering the DAC.</span></span>  
  
### <a name="validating-objects"></a><span data-ttu-id="725f8-162">Validation d'objets</span><span class="sxs-lookup"><span data-stu-id="725f8-162">Validating Objects</span></span>  
 <span data-ttu-id="725f8-163">**Vérification de**  _SchemaName_ **.**</span><span class="sxs-lookup"><span data-stu-id="725f8-163">**Checking**  _SchemaName_ **.**</span></span> <span data-ttu-id="725f8-164">_ObjectName_ **.**</span><span class="sxs-lookup"><span data-stu-id="725f8-164">_ObjectName_ **.**</span></span> <span data-ttu-id="725f8-165">- Affiche une barre de progression au fur et à mesure que l'Assistant vérifie les dépendances des objets récupérés, et vérifie que ces objets sont tous valides pour une DAC.</span><span class="sxs-lookup"><span data-stu-id="725f8-165">- Displays a progress bar as the wizard verifies the dependencies of the retrieved objects, and verifies that they are all valid objects for a DAC.</span></span> <span data-ttu-id="725f8-166">_SchemaName_ **.** _ObjectName_ identifient quel objet est vérifié actuellement.</span><span class="sxs-lookup"><span data-stu-id="725f8-166">_SchemaName_**.**_ObjectName_ identify which object is currently being verified.</span></span>  
  
 <span data-ttu-id="725f8-167">\*\* \< Précédent\*\* : vous renvoie à la page **définir les propriétés** pour modifier vos entrées.</span><span class="sxs-lookup"><span data-stu-id="725f8-167">**\< Previous** - Returns you to the **Set Properties** page to change your entries.</span></span>  
  
 <span data-ttu-id="725f8-168">**Suivant >** : inscrit la DAC et affiche les résultats dans la page **Inscrire la DAC**.</span><span class="sxs-lookup"><span data-stu-id="725f8-168">**Next >** - Registers the DAC and displays the results in the **Register DAC** page.</span></span>  
  
 <span data-ttu-id="725f8-169">**Annuler** : termine l’Assistant sans inscrire la DAC.</span><span class="sxs-lookup"><span data-stu-id="725f8-169">**Cancel** - Terminates the wizard without registering the DAC.</span></span>  
  
### <a name="summary"></a><span data-ttu-id="725f8-170">Résumé</span><span class="sxs-lookup"><span data-stu-id="725f8-170">Summary</span></span>  
 <span data-ttu-id="725f8-171">**Le paramètre suivant sera utilisé pour inscrire votre DAC.**</span><span class="sxs-lookup"><span data-stu-id="725f8-171">**The following setting will be used to register your DAC.**</span></span> <span data-ttu-id="725f8-172">- Affiche un rapport des propriétés et objets qui seront inclus dans la DAC.</span><span class="sxs-lookup"><span data-stu-id="725f8-172">- Displays a report of the properties and objects that will be included in the DAC.</span></span>  
  
 <span data-ttu-id="725f8-173">**Enregistrer le rapport** : sélectionnez ce bouton pour enregistrer une copie du rapport de validation dans un fichier HTML.</span><span class="sxs-lookup"><span data-stu-id="725f8-173">**Save Report** - Select this button to save a copy of the validation report to an HTML file.</span></span> <span data-ttu-id="725f8-174">Le dossier par défaut est un dossier **SQL Server Management Studio\DAC Packages** dans le dossier Documents de votre compte Windows.</span><span class="sxs-lookup"><span data-stu-id="725f8-174">The default folder is a **SQL Server Management Studio\DAC Packages** folder in the Documents folder of your Windows account.</span></span>  
  
 <span data-ttu-id="725f8-175">\*\* \< Précédent\*\* : vous renvoie à la page **définir les propriétés** pour modifier vos entrées.</span><span class="sxs-lookup"><span data-stu-id="725f8-175">**\< Previous** - Returns you to the **Set Properties** page to change your entries.</span></span>  
  
 <span data-ttu-id="725f8-176">**Suivant >** : inscrit la DAC et affiche les résultats dans la page **Inscrire la DAC**.</span><span class="sxs-lookup"><span data-stu-id="725f8-176">**Next >** - Registers the DAC and displays the results in the **Register DAC** page.</span></span>  
  
 <span data-ttu-id="725f8-177">**Annuler** : termine l’Assistant sans inscrire la DAC.</span><span class="sxs-lookup"><span data-stu-id="725f8-177">**Cancel** - Terminates the wizard without registering the DAC.</span></span>  
  
##  <a name="register-dac-page"></a><a name="Register"></a> <span data-ttu-id="725f8-178">Page Inscrire la DAC</span><span class="sxs-lookup"><span data-stu-id="725f8-178">Register DAC Page</span></span>  
 <span data-ttu-id="725f8-179">Cette page signale la réussite ou l'échec de l'inscription.</span><span class="sxs-lookup"><span data-stu-id="725f8-179">This page reports the success or failure of the registration.</span></span>  
  
 <span data-ttu-id="725f8-180">**Inscription de la DAC** : signale la réussite ou l’échec de chaque action entreprise pour inscrire la DAC.</span><span class="sxs-lookup"><span data-stu-id="725f8-180">**Registering the DAC** - Reports the success or failure of each action taken to register the DAC.</span></span> <span data-ttu-id="725f8-181">Examinez les informations pour déterminer la réussite ou l'échec de chaque action.</span><span class="sxs-lookup"><span data-stu-id="725f8-181">Review the information to determine the success or failure of each action.</span></span> <span data-ttu-id="725f8-182">Toute action pour laquelle une erreur s'est produite aura un lien dans la colonne **Résultat** .</span><span class="sxs-lookup"><span data-stu-id="725f8-182">Any action that encountered an error will have a link in the **Result** column.</span></span> <span data-ttu-id="725f8-183">Sélectionnez le lien pour consulter le rapport de d'erreur de cette action.</span><span class="sxs-lookup"><span data-stu-id="725f8-183">Select the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="725f8-184">**Enregistrer le rapport** : sélectionnez ce bouton pour enregistrer le rapport d’inscription dans un fichier HTML.</span><span class="sxs-lookup"><span data-stu-id="725f8-184">**Save Report** - Select this button to save the registration report to an HTML file.</span></span> <span data-ttu-id="725f8-185">Le fichier signale l'état de chaque action, notamment toutes les erreurs générées par chacune des actions.</span><span class="sxs-lookup"><span data-stu-id="725f8-185">The file reports the status of each action, including all errors generated by any of the actions.</span></span> <span data-ttu-id="725f8-186">Le dossier par défaut est un dossier **SQL Server Management Studio\DAC Packages** dans le dossier Documents de votre compte Windows.</span><span class="sxs-lookup"><span data-stu-id="725f8-186">The default folder is a **SQL Server Management Studio\DAC Packages** folder in the Documents folder of your Windows account.</span></span> <span data-ttu-id="725f8-187">Le nom de fichier est au format \<DACPackageName>_RegisterDACReport_aaaammjj.html, où \<*DACPackageName*> est le nom du package déployé, *aaaa* = l’année en cours, *mm* = le mois en cours et *jj* = la date du jour.</span><span class="sxs-lookup"><span data-stu-id="725f8-187">The file name is in the format \<DACPackageName>_RegisterDACReport_yyyymmdd.html, where \<*DACPackageName*> is the name of the package being deployed, *yyyy* = the current year, *mm* = the current month, and *dd* = the current day.</span></span>  
  
 <span data-ttu-id="725f8-188">**Terminer** : met fin à l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="725f8-188">**Finish** - Terminates the wizard.</span></span>  
  
##  <a name="register-a-dac-using-powershell"></a><a name="RegisterDACPowerShell"></a> <span data-ttu-id="725f8-189">Inscrire une DAC à l'aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="725f8-189">Register a DAC Using PowerShell</span></span>  
 <span data-ttu-id="725f8-190">**Pour inscrire une base de données comme DAC à l’aide de la méthode Register() dans un script PowerShell**</span><span class="sxs-lookup"><span data-stu-id="725f8-190">**To register a database as a DAC using the Register() method in a PowerShell script**</span></span>  
  
1.  <span data-ttu-id="725f8-191">Créez un objet serveur SMO et définissez-le sur l'instance qui contient la base de données à inscrire comme une DAC.</span><span class="sxs-lookup"><span data-stu-id="725f8-191">Create a SMO Server object and set it to the instance that contains the database to be registered as a DAC.</span></span>  
  
2.  <span data-ttu-id="725f8-192">Ajoutez une variable qui spécifie le nom de la base de données.</span><span class="sxs-lookup"><span data-stu-id="725f8-192">Add a variable that specifies the name of the database.</span></span>  
  
3.  <span data-ttu-id="725f8-193">Spécifiez les métadonnées pour la DAC, par exemple le nom de la DAC, la version et la description.</span><span class="sxs-lookup"><span data-stu-id="725f8-193">Specify the metadata for the DAC, such as the DAC name, version, and description.</span></span>  
  
4.  <span data-ttu-id="725f8-194">Exécutez la méthode Register avec les informations spécifiées ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="725f8-194">Run the Register method with the information specified above.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="725f8-195">Exemple (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="725f8-195">Example (PowerShell)</span></span>  
 <span data-ttu-id="725f8-196">L'exemple suivant inscrit une base de données nommée MyDB comme une DAC.</span><span class="sxs-lookup"><span data-stu-id="725f8-196">The following example registers a database named MyDB as a DAC.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Specify the database to register as a DAC.  
$dbname = "MyDB"  
  
## Specify the DAC metadata.  
$applicationname = "MyApplication"  
$version = "1.0.0.0"  
$description = "This DAC defines the database used by my application."  
  
## Register the DAC.  
$registerunit = New-Object Microsoft.SqlServer.Management.Dac.DacExtractionUnit($srv, $dbname, $applicationname, $version)  
$registerunit.Description = $description  
$registerunit.Register()  
```  
  
## <a name="see-also"></a><span data-ttu-id="725f8-197">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="725f8-197">See Also</span></span>  
 [<span data-ttu-id="725f8-198">Applications de la couche Données</span><span class="sxs-lookup"><span data-stu-id="725f8-198">Data-tier Applications</span></span>](data-tier-applications.md)  
