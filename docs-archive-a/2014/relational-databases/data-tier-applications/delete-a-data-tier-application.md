---
title: Supprimer une application de la couche Données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.deletedacwizard.introduction.f1
- sql12.swb.deletedacwizard.deletedac.f1
- sql12.swb.deletedacwizard.summary.f1
- sql12.swb.deletedacwizard.choosemethod.f1
helpviewer_keywords:
- How to [DAC], delete
- data-tier application [SQL Server], delete
- wizard [DAC], delete
- delete DAC
ms.assetid: 16fe1c18-4486-424d-81d6-d276ed97482f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 602256c287a8c7bcf9d3fa5597b2fec2085c626c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705168"
---
# <a name="delete-a-data-tier-application"></a><span data-ttu-id="f1d24-102">Supprimer une application de la couche Données</span><span class="sxs-lookup"><span data-stu-id="f1d24-102">Delete a Data-tier Application</span></span>
  <span data-ttu-id="f1d24-103">Vous pouvez supprimer une application de la couche Données à l'aide de l'Assistant Supprimer l'application de la couche Données ou d'un script Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1d24-103">You can delete a data-tier application by using either the Delete Data-tier Application wizard or a Windows PowerShell script.</span></span> <span data-ttu-id="f1d24-104">Vous pouvez spécifier si la base de données associée doit être conservée, détachée ou supprimée.</span><span class="sxs-lookup"><span data-stu-id="f1d24-104">You can specify whether the associated database is retained, detached, or dropped.</span></span>  
  
-   <span data-ttu-id="f1d24-105">**Avant de commencer :**  [Limitations et restrictions](#LimitationsRestrictions), [Autorisations](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="f1d24-105">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="f1d24-106">**Pour mettre à niveau une DAC à l’aide de** :  [l’Assistant d’inscription de l’application de la couche Données](#UsingDeleteDACWizard), [PowerShell](#DeleteDACPowerShell)</span><span class="sxs-lookup"><span data-stu-id="f1d24-106">**To upgrade a DAC, using:**  [The Register Data-tier Application Wizard](#UsingDeleteDACWizard), [PowerShell](#DeleteDACPowerShell)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="f1d24-107">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="f1d24-107">Before You Begin</span></span>  
 <span data-ttu-id="f1d24-108">Lorsque vous supprimez une instance d'application de la couche Données (DAC), vous choisissez l'une des trois options qui spécifient le mode de traitement de la base de données associée à l'application de la couche Données.</span><span class="sxs-lookup"><span data-stu-id="f1d24-108">When you delete a data-tier application (DAC) instance, you choose one of three options specifying what is to be done with the database associated with the data-tier application.</span></span> <span data-ttu-id="f1d24-109">Les trois options suppriment les métadonnées de définition de la DAC.</span><span class="sxs-lookup"><span data-stu-id="f1d24-109">All three options delete the DAC definition metadata.</span></span> <span data-ttu-id="f1d24-110">Les options diffèrent de par ce qu'elles font de la base de données associée à l'application de couche Données.</span><span class="sxs-lookup"><span data-stu-id="f1d24-110">The options differ in what they do with the database associated with the data-tier application.</span></span> <span data-ttu-id="f1d24-111">L'Assistant ne supprime aucun des objets au niveau de l'instance associés à la DAC ou base de données, tels que les connexions.</span><span class="sxs-lookup"><span data-stu-id="f1d24-111">The wizard does not delete any of the instance-level objects associated with the DAC or database, such as logins.</span></span>  
  
|<span data-ttu-id="f1d24-112">Option</span><span class="sxs-lookup"><span data-stu-id="f1d24-112">Option</span></span>|<span data-ttu-id="f1d24-113">Actions de base de données</span><span class="sxs-lookup"><span data-stu-id="f1d24-113">Database actions</span></span>|  
|------------|----------------------|  
|<span data-ttu-id="f1d24-114">Supprimer l'inscription</span><span class="sxs-lookup"><span data-stu-id="f1d24-114">Delete registration</span></span>|<span data-ttu-id="f1d24-115">La base de données associée reste intacte.</span><span class="sxs-lookup"><span data-stu-id="f1d24-115">The associated database remains intact.</span></span>|  
|<span data-ttu-id="f1d24-116">Détacher la base de données</span><span class="sxs-lookup"><span data-stu-id="f1d24-116">Detach database</span></span>|<span data-ttu-id="f1d24-117">La base de données associée est détachée.</span><span class="sxs-lookup"><span data-stu-id="f1d24-117">The associated database is detached.</span></span> <span data-ttu-id="f1d24-118">L'instance du moteur de base de données ne peut pas référencer la base de données, mais les données et les fichiers journaux sont intacts.</span><span class="sxs-lookup"><span data-stu-id="f1d24-118">The instance of the Database Engine cannot reference the database, but the data and log files are intact.</span></span>|  
|<span data-ttu-id="f1d24-119">Supprimer la base de données</span><span class="sxs-lookup"><span data-stu-id="f1d24-119">Delete database</span></span>|<span data-ttu-id="f1d24-120">La base de données associée est supprimée.</span><span class="sxs-lookup"><span data-stu-id="f1d24-120">The associated database is dropped.</span></span> <span data-ttu-id="f1d24-121">Les données et fichiers journaux sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="f1d24-121">The data and log files are deleted.</span></span>|  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="f1d24-122">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="f1d24-122">Limitations and Restrictions</span></span>  
 <span data-ttu-id="f1d24-123">Il n'existe aucun mécanisme automatique pour restaurer les métadonnées de définition de la DAC ou la base de données après avoir supprimé une DAC.</span><span class="sxs-lookup"><span data-stu-id="f1d24-123">There is no automatic mechanism to restore the DAC definition metadata or the database after you delete a DAC.</span></span> <span data-ttu-id="f1d24-124">La possibilité de reconstruire l'instance de la DAC manuellement dépend de l'option de suppression.</span><span class="sxs-lookup"><span data-stu-id="f1d24-124">How you can manually rebuild the DAC instance depends on the delete option.</span></span>  
  
|<span data-ttu-id="f1d24-125">Option</span><span class="sxs-lookup"><span data-stu-id="f1d24-125">Option</span></span>|<span data-ttu-id="f1d24-126">Comment reconstruire l'instance de la DAC</span><span class="sxs-lookup"><span data-stu-id="f1d24-126">How to Rebuild the DAC Instance</span></span>|  
|------------|-------------------------------------|  
|<span data-ttu-id="f1d24-127">Supprimer l'inscription</span><span class="sxs-lookup"><span data-stu-id="f1d24-127">Delete registration</span></span>|<span data-ttu-id="f1d24-128">Enregistrez une DAC de la base de données laissée en place.</span><span class="sxs-lookup"><span data-stu-id="f1d24-128">Register a DAC from the database left in place.</span></span>|  
|<span data-ttu-id="f1d24-129">Détacher la base de données</span><span class="sxs-lookup"><span data-stu-id="f1d24-129">Detach database</span></span>|<span data-ttu-id="f1d24-130">Rattachez la base de données à l'aide de **sp_attachdb** ou de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], puis enregistrez une nouvelle instance de la DAC à partir de la base de données.</span><span class="sxs-lookup"><span data-stu-id="f1d24-130">Re-attach the database by using **sp_attachdb** or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then register a new DAC instance from the database.</span></span>|  
|<span data-ttu-id="f1d24-131">Supprimer la base de données</span><span class="sxs-lookup"><span data-stu-id="f1d24-131">Delete database</span></span>|<span data-ttu-id="f1d24-132">Restaurez la base de données à partir d'une sauvegarde complète effectuée avant que la DAC ait été supprimée, puis enregistrez une nouvelle instance de la DAC à partir de la base de données.</span><span class="sxs-lookup"><span data-stu-id="f1d24-132">Restore the database from a full backup made before the DAC was deleted, and then register a new DAC instance from the database.</span></span>|  
  
> [!WARNING]  
>  <span data-ttu-id="f1d24-133">La reconstruction d'une instance de la DAC en inscrivant une DAC à partir d'une base de données rattachée ou restaurée ne recréera pas certaines parties de la DAC d'origine, telles que la stratégie de sélection du serveur.</span><span class="sxs-lookup"><span data-stu-id="f1d24-133">Rebuilding a DAC instance by registering a DAC from a restored or re-attached database will not recreate some parts of the original DAC, such as the server selection policy.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f1d24-134">Autorisations</span><span class="sxs-lookup"><span data-stu-id="f1d24-134">Permissions</span></span>  
 <span data-ttu-id="f1d24-135">Une DAC peut uniquement être supprimée par les membres des rôles serveur fixes **sysadmin** ou **serveradmin** , ou par le propriétaire de la base de données.</span><span class="sxs-lookup"><span data-stu-id="f1d24-135">A DAC can only be deleted by members of the **sysadmin** or **serveradmin** fixed server roles, or by the database owner.</span></span> <span data-ttu-id="f1d24-136">Le compte d’administrateur système [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] intégré nommé **sa** peut également lancer l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="f1d24-136">The built-in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator account named **sa** can also launch the wizard.</span></span>  
  
##  <a name="using-the-delete-data-tier-application-wizard"></a><a name="UsingDeleteDACWizard"></a> <span data-ttu-id="f1d24-137">Utilisation de l'Assistant Supprimer l'application de la couche Données</span><span class="sxs-lookup"><span data-stu-id="f1d24-137">Using the Delete Data-tier Application Wizard</span></span>  
 <span data-ttu-id="f1d24-138">**Pour supprimer une DAC à l'aide d'un Assistant**</span><span class="sxs-lookup"><span data-stu-id="f1d24-138">**To Delete a DAC Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="f1d24-139">Dans l' **Explorateur d'objets**, développez le nœud pour l'instance qui contient la DAC à supprimer.</span><span class="sxs-lookup"><span data-stu-id="f1d24-139">In **Object Explorer**, expand the node for the instance containing the DAC to be deleted.</span></span>  
  
2.  <span data-ttu-id="f1d24-140">Développez le nœud **Gestion** .</span><span class="sxs-lookup"><span data-stu-id="f1d24-140">Expand the **Management** node.</span></span>  
  
3.  <span data-ttu-id="f1d24-141">Développez le nœud **Applications de la couche Données** .</span><span class="sxs-lookup"><span data-stu-id="f1d24-141">Expand the **Data-tier Applications** node.</span></span>  
  
4.  <span data-ttu-id="f1d24-142">Cliquez avec le bouton droit sur la DAC à supprimer et sélectionnez **Supprimer une application de la couche Données**.</span><span class="sxs-lookup"><span data-stu-id="f1d24-142">Right-click the DAC to be deleted, and then select **Delete Data-tier Application...**</span></span>  
  
5.  <span data-ttu-id="f1d24-143">Renseignez les boîtes de dialogue de l'Assistant :</span><span class="sxs-lookup"><span data-stu-id="f1d24-143">Complete the wizard dialogs:</span></span>  
  
    1.  [<span data-ttu-id="f1d24-144">Introduction</span><span class="sxs-lookup"><span data-stu-id="f1d24-144">Introduction</span></span>](#Introduction)  
  
    2.  [<span data-ttu-id="f1d24-145">Choisir une méthode</span><span class="sxs-lookup"><span data-stu-id="f1d24-145">Choose Method</span></span>](#Choose_method)  
  
    3.  [<span data-ttu-id="f1d24-146">Résumé</span><span class="sxs-lookup"><span data-stu-id="f1d24-146">Summary</span></span>](#Summary)  
  
    4.  [<span data-ttu-id="f1d24-147">Supprimer une application de couche Données</span><span class="sxs-lookup"><span data-stu-id="f1d24-147">Delete Data-tier Application</span></span>](#Delete_datatier_application)  
  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="f1d24-148">Page Introduction</span><span class="sxs-lookup"><span data-stu-id="f1d24-148">Introduction Page</span></span>  
 <span data-ttu-id="f1d24-149">Cette page décrit les étapes de la suppression d'une application de couche Données.</span><span class="sxs-lookup"><span data-stu-id="f1d24-149">This page describes the steps for deleting a data-tier application.</span></span>  
  
 <span data-ttu-id="f1d24-150">**Ne plus afficher cette page.**</span><span class="sxs-lookup"><span data-stu-id="f1d24-150">**Do not show this page again.**</span></span> <span data-ttu-id="f1d24-151">- Cochez la case pour ne plus afficher la page à l'avenir.</span><span class="sxs-lookup"><span data-stu-id="f1d24-151">- Click the check box to stop the page from being displayed in the future.</span></span>  
  
 <span data-ttu-id="f1d24-152">**Suivant >** : passe à la page **Choisir une méthode**.</span><span class="sxs-lookup"><span data-stu-id="f1d24-152">**Next >** - Proceeds to the **Choose Method** page.</span></span>  
  
 <span data-ttu-id="f1d24-153">**Annuler** : termine l’Assistant sans supprimer une application de couche Données ni une base de données.</span><span class="sxs-lookup"><span data-stu-id="f1d24-153">**Cancel** - Ends the wizard without deleting a data-tier application or database.</span></span>  
  
##  <a name="choose-method-page"></a><a name="Choose_method"></a><span data-ttu-id="f1d24-154">Page choisir une méthode</span><span class="sxs-lookup"><span data-stu-id="f1d24-154">Choose Method Page</span></span>  
 <span data-ttu-id="f1d24-155">Utilisez cette page pour spécifier l'option pour gérer la base de données associée à la DAC à supprimer.</span><span class="sxs-lookup"><span data-stu-id="f1d24-155">Use this page to specify the option for handling the database associated with the DAC to be deleted.</span></span>  
  
 <span data-ttu-id="f1d24-156">**Supprimer l’inscription** : supprime les métadonnées qui définissent l’application de couche Données, mais laisse la base de données associée intacte.</span><span class="sxs-lookup"><span data-stu-id="f1d24-156">**Delete registration** - Removes the metadata defining the data-tier application, but leaves the associated database intact.</span></span>  
  
 <span data-ttu-id="f1d24-157">**Détacher la base de données** : supprime les métadonnées qui définissent l’application de couche Données et détache la base de données associée.</span><span class="sxs-lookup"><span data-stu-id="f1d24-157">**Detach database** - Removes the metadata defining the data-tier application and detaches the associated database.</span></span>  
  
 <span data-ttu-id="f1d24-158">La base de données ne peut plus être référencée par cette instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)], mais les données et fichiers journaux restent intacts.</span><span class="sxs-lookup"><span data-stu-id="f1d24-158">The database can no longer be referenced by that instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], but the data and log files remain intact.</span></span>  
  
 <span data-ttu-id="f1d24-159">**Supprimer la base de données** : supprime les métadonnées qui définissent la DAC et supprime la base de données associée.</span><span class="sxs-lookup"><span data-stu-id="f1d24-159">**Delete database** - Removes the metadata defining the DAC and drops the associated database.</span></span>  
  
 <span data-ttu-id="f1d24-160">Les données et fichiers journaux pour la base de données sont supprimés définitivement.</span><span class="sxs-lookup"><span data-stu-id="f1d24-160">The data and log files for the database are permanently deleted.</span></span>  
  
 <span data-ttu-id="f1d24-161">\*\* \< Précédent\*\* : renvoie à la page **Introduction** .</span><span class="sxs-lookup"><span data-stu-id="f1d24-161">**\< Previous** - Returns to the **Introduction** page.</span></span>  
  
 <span data-ttu-id="f1d24-162">**Suivant >** : passe à la page **Résumé**.</span><span class="sxs-lookup"><span data-stu-id="f1d24-162">**Next >** - Proceeds to the **Summary** page.</span></span>  
  
 <span data-ttu-id="f1d24-163">**Annuler** : termine l’Assistant sans supprimer la DAC ni la base de données.</span><span class="sxs-lookup"><span data-stu-id="f1d24-163">**Cancel** - Ends the wizard without deleting the DAC or database.</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="f1d24-164">Page Résumé</span><span class="sxs-lookup"><span data-stu-id="f1d24-164">Summary Page</span></span>  
 <span data-ttu-id="f1d24-165">Utilisez cette page pour examiner les mesures prises par l'Assistant lors de la suppression de l'instance de la DAC.</span><span class="sxs-lookup"><span data-stu-id="f1d24-165">Use this page to review the actions the wizard will take when deleting the DAC instance.</span></span>  
  
 <span data-ttu-id="f1d24-166">**Examinez le résumé de vos sélections** : examinez la DAC, la base de données et la méthode de suppression affichées dans la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="f1d24-166">**Review your selection summary** - Review the DAC, database, and deletion method displayed in the box.</span></span> <span data-ttu-id="f1d24-167">Si les informations sont correctes, sélectionnez **Suivant** ou **Terminer** pour supprimer la DAC.</span><span class="sxs-lookup"><span data-stu-id="f1d24-167">If the information is correct, select either **Next** or **Finish** to delete the DAC.</span></span> <span data-ttu-id="f1d24-168">Si la DAC et les informations sur la base de données ne sont pas correctes, sélectionnez **Annuler** , puis la DAC appropriée.</span><span class="sxs-lookup"><span data-stu-id="f1d24-168">If the DAC and database information is not correct, select **Cancel** and select the correct DAC.</span></span> <span data-ttu-id="f1d24-169">Si la méthode de suppression n'est pas correcte, sélectionnez **Précédent** pour retourner à la page **Choisir une méthode** et sélectionner une méthode différente.</span><span class="sxs-lookup"><span data-stu-id="f1d24-169">If the deletion method is not correct, select **Previous** to return to the **Choose Method** page and select a different method.</span></span>  
  
 <span data-ttu-id="f1d24-170">\*\* \< Précédent\*\* : renvoie à la page **choisir une méthode** pour choisir une autre méthode de suppression.</span><span class="sxs-lookup"><span data-stu-id="f1d24-170">**\< Previous** - Returns to the **Choose Method** page to choose a different delete method.</span></span>  
  
 <span data-ttu-id="f1d24-171">**Suivant >** : supprime l’instance de la DAC en utilisant la méthode que vous avez choisie à la page précédente, puis passe à la page **Supprimer une application de couche Données**.</span><span class="sxs-lookup"><span data-stu-id="f1d24-171">**Next >** - Deletes the DAC instance using the method you chose on the previous page, and proceeds to the **Delete Data-tier Application** page.</span></span>  
  
 <span data-ttu-id="f1d24-172">**Annuler** : termine l’Assistant sans supprimer l’instance de la DAC.</span><span class="sxs-lookup"><span data-stu-id="f1d24-172">**Cancel** - Ends the wizard without deleting the DAC instance.</span></span>  
  
##  <a name="delete-data-tier-application-page"></a><a name="Delete_datatier_application"></a><span data-ttu-id="f1d24-173">Page supprimer une application de la couche données</span><span class="sxs-lookup"><span data-stu-id="f1d24-173">Delete Data-tier Application Page</span></span>  
 <span data-ttu-id="f1d24-174">Cette page signale la réussite ou l'échec de l'opération de suppression.</span><span class="sxs-lookup"><span data-stu-id="f1d24-174">This page reports the success or failure of the delete operation.</span></span>  
  
 <span data-ttu-id="f1d24-175">**Suppression de la DAC** : signale la réussite ou l’échec de chaque mesure prise pour supprimer l’instance de la DAC.</span><span class="sxs-lookup"><span data-stu-id="f1d24-175">**Deleting the DAC** - Reports the success or failure of each action taken to delete the DAC instance.</span></span> <span data-ttu-id="f1d24-176">Examinez les informations pour déterminer la réussite ou l'échec de chaque action.</span><span class="sxs-lookup"><span data-stu-id="f1d24-176">Review the information to determine the success or failure of each action.</span></span> <span data-ttu-id="f1d24-177">Toute action pour laquelle une erreur s'est produite aura un lien dans la colonne **Résultat** .</span><span class="sxs-lookup"><span data-stu-id="f1d24-177">Any action that encountered an error will have a link in the **Result** column.</span></span> <span data-ttu-id="f1d24-178">Sélectionnez le lien pour consulter le rapport de d'erreur de cette action.</span><span class="sxs-lookup"><span data-stu-id="f1d24-178">Select the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="f1d24-179">**Enregistrer le rapport** : sélectionnez ce bouton pour enregistrer le rapport de suppression dans un fichier HTML.</span><span class="sxs-lookup"><span data-stu-id="f1d24-179">**Save Report** - Select this button to save the deletion report to an HTML file.</span></span> <span data-ttu-id="f1d24-180">Le fichier signale l'état de chaque action, notamment toutes les erreurs générées par chacune des actions.</span><span class="sxs-lookup"><span data-stu-id="f1d24-180">The file reports the status of each action, including all errors generated by any of the actions.</span></span> <span data-ttu-id="f1d24-181">Le dossier par défaut est un dossier SQL Server Management Studio\DAC Packages dans le dossier Documents de votre compte Windows.</span><span class="sxs-lookup"><span data-stu-id="f1d24-181">The default folder is a SQL Server Management Studio\DAC Packages folder in the Documents folder of your Windows account..</span></span>  
  
 <span data-ttu-id="f1d24-182">**Terminer** : termine l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="f1d24-182">**Finish** - Ends the wizard.</span></span>  
  
##  <a name="delete-a-dac-using-powershell"></a><a name="DeleteDACPowerShell"></a><span data-ttu-id="f1d24-183">Supprimer une DAC à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1d24-183">Delete a DAC Using PowerShell</span></span>  
 <span data-ttu-id="f1d24-184">**Pour supprimer une DAC à l'aide d'un script PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f1d24-184">**To delete a DAC using a PowerShell script**</span></span>  
  
1.  <span data-ttu-id="f1d24-185">Créez un objet serveur SMO et définissez-le sur l'instance qui contient la DAC à supprimer.</span><span class="sxs-lookup"><span data-stu-id="f1d24-185">Create a SMO Server object and set it to the instance that contains the DAC to be deleted.</span></span>  
  
2.  <span data-ttu-id="f1d24-186">Ouvrez un objet `ServerConnection` et connectez-vous à la même instance.</span><span class="sxs-lookup"><span data-stu-id="f1d24-186">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="f1d24-187">Utilisez `add_DacActionStarted` et `add_DacActionFinished` pour vous abonner aux événements de mise à niveau de la DAC.</span><span class="sxs-lookup"><span data-stu-id="f1d24-187">Use `add_DacActionStarted` and `add_DacActionFinished` to subscribe to the DAC upgrade events.</span></span>  
  
4.  <span data-ttu-id="f1d24-188">Spécifiez la DAC à supprimer.</span><span class="sxs-lookup"><span data-stu-id="f1d24-188">Specify the DAC to delete.</span></span>  
  
5.  <span data-ttu-id="f1d24-189">Utilisez l'un des trois jeux de codes, en fonction de l'option de suppression qui convient le mieux :</span><span class="sxs-lookup"><span data-stu-id="f1d24-189">Use one of these three sets of code, depending on which delete option is appropriate:</span></span>  
  
    -   <span data-ttu-id="f1d24-190">Pour supprimer l'inscription de la DAC, mais laisser la base de données intacte, utilisez la méthode `Unmanage()`.</span><span class="sxs-lookup"><span data-stu-id="f1d24-190">To delete the DAC registration but leave the database intact, use the `Unmanage()` method.</span></span>  
  
    -   <span data-ttu-id="f1d24-191">Pour supprimer l'inscription de la DAC et détacher la base de données, utilisez la méthode `Uninstall()` et spécifiez `DetachDatabase`.</span><span class="sxs-lookup"><span data-stu-id="f1d24-191">To delete the DAC registration and detach the database, use the `Uninstall()` method and specify `DetachDatabase`.</span></span>  
  
    -   <span data-ttu-id="f1d24-192">Pour supprimer l'inscription de la DAC et supprimer la base de données, utilisez la méthode `Uninstall()` et spécifiez `DropDatabase`.</span><span class="sxs-lookup"><span data-stu-id="f1d24-192">To delete the DAC registration and drop the database, use the `Uninstall()` method and specify `DropDatabase`.</span></span>  
  
### <a name="example-deleting-the-dac-but-leaving-the-database-powershell"></a><span data-ttu-id="f1d24-193">Exemple de suppression de la DAC mais en laissant la base de données (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="f1d24-193">Example Deleting the DAC but Leaving the Database (PowerShell)</span></span>  
 <span data-ttu-id="f1d24-194">L'exemple suivant supprime une DAC nommée MyApplication à l'aide de la méthode `Unmanage()` pour supprimer la DAC, mais laisser la base de données intacte.</span><span class="sxs-lookup"><span data-stu-id="f1d24-194">The following example deletes a DAC named MyApplication using the `Unmanage()` method to delete the DAC but leave the database intact.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Subscribe to the DAC delete events.  
$dacstore.add_DacActionStarted({Write-Host `n`nStarting at $(get-date) :: $_.Description})  
$dacstore.add_DacActionFinished({Write-Host Completed at $(get-date) :: $_.Description})  
  
## Specify the DAC to delete.  
$dacName  = "MyApplication"  
  
## Only delete the DAC definition from msdb, the associated database remains active.  
$dacstore.Unmanage($dacName)  
```  
  
### <a name="example-deleting-the-dac-and-detaching-the-database-powershell"></a><span data-ttu-id="f1d24-195">Exemple de suppression de la DAC en détachant la base de données (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="f1d24-195">Example Deleting the DAC and Detaching the Database (PowerShell)</span></span>  
 <span data-ttu-id="f1d24-196">L'exemple suivant supprime une DAC nommée MyApplication à l'aide de la méthode `Uninstall()` pour supprimer la DAC et détacher la base de données.</span><span class="sxs-lookup"><span data-stu-id="f1d24-196">The following example deletes a DAC named MyApplication using the `Uninstall()` method to delete the DAC and detach the database.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = get-item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Subscribe to the DAC delete events.  
$dacstore.add_DacActionStarted({Write-Host `n`nStarting at $(get-date) :: $_.Description})  
$dacstore.add_DacActionFinished({Write-Host Completed at $(get-date) :: $_.Description})  
  
## Specify the DAC to delete.  
$dacName  = "MyApplication"  
  
## Delete the DAC definition from msdb and detach the associated database.  
$dacstore.Uninstall($dacName, [Microsoft.SqlServer.Management.Dac.DacUninstallMode]::DetachDatabase)  
```  
  
### <a name="example-deleting-the-dac-and-dropping-the-database-powershell"></a><span data-ttu-id="f1d24-197">Exemple de suppression de la DAC en supprimant la base de données (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="f1d24-197">Example Deleting the DAC and Dropping the Database (PowerShell)</span></span>  
 <span data-ttu-id="f1d24-198">L'exemple suivant supprime une DAC nommée MyApplication à l'aide de la méthode `Uninstall()` pour supprimer la DAC et la base de données.</span><span class="sxs-lookup"><span data-stu-id="f1d24-198">The following example deletes a DAC named MyApplication using the `Uninstall()` method to delete the DAC and drop the database.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Subscribe to the DAC delete events.  
$dacstore.add_DacActionStarted({Write-Host `n`nStarting at $(get-date) :: $_.Description})  
$dacstore.add_DacActionFinished({Write-Host Completed at $(get-date) :: $_.Description})  
  
## Specify the DAC to delete.  
$dacName  = "MyApplication"  
  
## Delete the DAC definition from msdb and drop the associated database.  
## $dacstore.Uninstall($dacName, [Microsoft.SqlServer.Management.Dac.DacUninstallMode]::DropDatabase)  
```  
  
## <a name="see-also"></a><span data-ttu-id="f1d24-199">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f1d24-199">See Also</span></span>  
 <span data-ttu-id="f1d24-200">[Applications de la couche Données](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="f1d24-200">[Data-tier Applications](data-tier-applications.md) </span></span>  
 <span data-ttu-id="f1d24-201">[Applications de la couche Données](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="f1d24-201">[Data-tier Applications](data-tier-applications.md) </span></span>  
 <span data-ttu-id="f1d24-202">[Déployer une application de la couche données](deploy-a-data-tier-application.md) </span><span class="sxs-lookup"><span data-stu-id="f1d24-202">[Deploy a Data-tier Application](deploy-a-data-tier-application.md) </span></span>  
 <span data-ttu-id="f1d24-203">[Inscrire une base de données en tant que DAC](register-a-database-as-a-dac.md) </span><span class="sxs-lookup"><span data-stu-id="f1d24-203">[Register a Database As a DAC](register-a-database-as-a-dac.md) </span></span>  
 <span data-ttu-id="f1d24-204">[Sauvegarde et restauration des bases de données SQL Server](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="f1d24-204">[Back Up and Restore of SQL Server Databases](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 [<span data-ttu-id="f1d24-205">Attacher et détacher une base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f1d24-205">Database Detach and Attach &#40;SQL Server&#41;</span></span>](../databases/database-detach-and-attach-sql-server.md)  
