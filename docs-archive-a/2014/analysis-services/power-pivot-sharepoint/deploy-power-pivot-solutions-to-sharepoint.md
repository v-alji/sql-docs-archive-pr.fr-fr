---
title: Déployer des solutions PowerPivot sur SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f202a2b7-34e0-43aa-90d5-c9a085a37c32
author: minewiskan
ms.author: owend
ms.openlocfilehash: 043647988598f932b70cc06e6bb5492d66864372
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611967"
---
# <a name="deploy-powerpivot-solutions-to-sharepoint"></a><span data-ttu-id="fbbe7-102">Déployer des solutions PowerPivot sur SharePoint</span><span class="sxs-lookup"><span data-stu-id="fbbe7-102">Deploy PowerPivot Solutions to SharePoint</span></span>
  <span data-ttu-id="fbbe7-103">Utilisez les instructions suivantes pour déployer manuellement deux packages de solution qui ajoutent des fonctionnalités PowerPivot à un environnement SharePoint Server 2010.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-103">Use the following instructions to manually deploy two solution packages that add PowerPivot features to a SharePoint Server 2010 environment.</span></span> <span data-ttu-id="fbbe7-104">Le déploiement des solutions est une étape indispensable pour configurer PowerPivot pour SharePoint sur un serveur SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-104">Deploying the solutions is a required step for configuring PowerPivot for SharePoint on a SharePoint 2010 server.</span></span> <span data-ttu-id="fbbe7-105">Pour afficher la liste complète des étapes requises, consultez [administration et configuration du serveur PowerPivot dans l’administration centrale](power-pivot-server-administration-and-configuration-in-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="fbbe7-105">To view the complete list of required steps, see [PowerPivot Server Administration and Configuration in Central Administration](power-pivot-server-administration-and-configuration-in-central-administration.md).</span></span>  
  
 <span data-ttu-id="fbbe7-106">Pour déployer les solutions, vous pouvez également utiliser l'outil de configuration PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-106">Alternatively, you can use the PowerPivot Configuration Tool to deploy the solutions.</span></span> <span data-ttu-id="fbbe7-107">L'utilisation de l'outil de configuration est plus simple et plus efficace pour une installation sur un serveur unique, mais vous souhaiterez peut-être recourir à l'Administration centrale et à PowerShell si vous préférez travailler avec un outil qui vous est familier ou si vous configurez plusieurs fonctionnalités en même temps.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-107">Using the configuration tool is easier and more efficient for a single server installation, but you might want to use Central Administration and PowerShell if you prefer using a familiar tool or if you are configuring multiple features at the same time.</span></span> <span data-ttu-id="fbbe7-108">Pour plus d’informations sur l’utilisation de l’outil de configuration de, consultez [outils de configuration de PowerPivot](power-pivot-configuration-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fbbe7-108">For more information about using the configuration tool, see [PowerPivot Configuration Tools](power-pivot-configuration-tools.md).</span></span>  
  
 <span data-ttu-id="fbbe7-109">Avant de déployer ces solutions, vous devez d'abord installer PowerPivot pour SharePoint à l'aide du support d'installation de SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-109">Before deploying the solutions, you must first install PowerPivot for SharePoint using the SQL Server 2012 installation media.</span></span> <span data-ttu-id="fbbe7-110">Le programme d'installation de SQL Server installe les packages de solution que vous êtes sur le point de déployer.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-110">SQL Server Setup installs the solution packages that you are about to deploy.</span></span>  
  
 <span data-ttu-id="fbbe7-111">Cette rubrique contient les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="fbbe7-111">This topic contains the following sections:</span></span>  
  
 [<span data-ttu-id="fbbe7-112">Condition préalable : vérifier que l’application Web utilise l’authentification en mode classique</span><span class="sxs-lookup"><span data-stu-id="fbbe7-112">Prerequisite: Verify the Web Application uses Classic Mode Authentication</span></span>](#bkmk_classic)  
  
 [<span data-ttu-id="fbbe7-113">Étape 1 : déployer la solution de batterie de serveurs</span><span class="sxs-lookup"><span data-stu-id="fbbe7-113">Step 1: Deploy the Farm Solution</span></span>](#bkmk_farm)  
  
 [<span data-ttu-id="fbbe7-114">Étape 2 : déployer la solution d'application Web PowerPivot sur l'Administration centrale</span><span class="sxs-lookup"><span data-stu-id="fbbe7-114">Step 2: Deploy the PowerPivot Web Application Solution to Central Administration</span></span>](#deployCA)  
  
 [<span data-ttu-id="fbbe7-115">Étape 3 : déployer la solution d'application Web PowerPivot sur d'autres applications Web</span><span class="sxs-lookup"><span data-stu-id="fbbe7-115">Step 3: Deploy the PowerPivot Web Application Solution to Other Web Applications</span></span>](#deployUI)  
  
 [<span data-ttu-id="fbbe7-116">Redéployer ou retirer la solution</span><span class="sxs-lookup"><span data-stu-id="fbbe7-116">Redeploy or retract the Solution</span></span>](#retract)  
  
 [<span data-ttu-id="fbbe7-117">À propos des solutions PowerPivot</span><span class="sxs-lookup"><span data-stu-id="fbbe7-117">About the PowerPivot Solutions</span></span>](#intro)  
  
##  <a name="prerequisite-verify-the-web-application-uses-classic-mode-authentication"></a><a name="bkmk_classic"></a> <span data-ttu-id="fbbe7-118">Condition préalable : vérifier que l'application Web utilise l'authentification en mode classique</span><span class="sxs-lookup"><span data-stu-id="fbbe7-118">Prerequisite: Verify the Web Application uses Classic Mode Authentication</span></span>  
 <span data-ttu-id="fbbe7-119">PowerPivot pour SharePoint n'est pris en charge que pour les applications Web qui utilisent l'authentification en mode classique.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-119">PowerPivot for SharePoint is only supported for web applications that use Windows-classic mode authentication.</span></span> <span data-ttu-id="fbbe7-120">Pour vérifier si l’application utilise le mode classique, exécutez l’applet de commande PowerShell suivante à partir de **SharePoint 2010 Management Shell**, `http://<top-level site name>` en remplaçant par le nom de votre site SharePoint :</span><span class="sxs-lookup"><span data-stu-id="fbbe7-120">To check whether the application uses Classic mode, run the following PowerShell cmdlet from the **SharePoint 2010 Management Shell**, replacing `http://<top-level site name>` with the name of your SharePoint site:</span></span>  
  
```powershell
Get-SPWebApplication http://<top-level site name> | Format-List UseClaimsAuthentication  
```  
  
 <span data-ttu-id="fbbe7-121">La valeur de retour devrait être **False**.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-121">The return value should be **false**.</span></span> <span data-ttu-id="fbbe7-122">Si la **valeur est true**, vous ne pouvez pas accéder aux données PowerPivot avec cette application Web.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-122">If it is **true**, you cannot access PowerPivot data with this web application.</span></span>  
  
##  <a name="step-1-deploy-the-farm-solution"></a><a name="bkmk_farm"></a> <span data-ttu-id="fbbe7-123">Étape 1 : déployer la solution de batterie de serveurs</span><span class="sxs-lookup"><span data-stu-id="fbbe7-123">Step 1: Deploy the Farm Solution</span></span>  
 <span data-ttu-id="fbbe7-124">Cette section montre comment déployer des solutions à l'aide de PowerShell, mais vous pouvez également utiliser l'outil de configuration PowerPivot pour effectuer cette tâche.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-124">This section shows you how to deploy solutions using PowerShell, but you can also use the PowerPivot Configuration Tool to complete this task.</span></span> <span data-ttu-id="fbbe7-125">Pour plus d’informations, consultez [configurer ou réparer PowerPivot pour SharePoint 2010 &#40;outil de configuration de PowerPivot&#41;](../configure-repair-powerpivot-sharepoint-2010.md).</span><span class="sxs-lookup"><span data-stu-id="fbbe7-125">For more information, see [Configure or Repair PowerPivot for SharePoint 2010 &#40;PowerPivot Configuration Tool&#41;](../configure-repair-powerpivot-sharepoint-2010.md).</span></span>  
  
 <span data-ttu-id="fbbe7-126">Cette tâche ne doit être effectuée qu'une seule fois, après l'installation de PowerPivot pour SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-126">This task only needs to be performed once, after you install PowerPivot for SharePoint.</span></span>  
  
1.  <span data-ttu-id="fbbe7-127">Sur un serveur disposant d’une installation de PowerPivot pour SharePoint, ouvrez un environnement de gestion SharePoint 2010 à l’aide de l’option **exécuter en tant qu’administrateur** .</span><span class="sxs-lookup"><span data-stu-id="fbbe7-127">On a server that has an installation of PowerPivot for SharePoint, open a SharePoint 2010 Management Shell using the **Run as Administrator** option.</span></span>  
  
2.  <span data-ttu-id="fbbe7-128">Exécutez l'applet de commande suivante pour ajouter la solution de batterie de serveurs.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-128">Run the following cmdlet to add the farm solution.</span></span>  
  
    ```powershell
    Add-SPSolution -LiteralPath "C:\Program Files\Microsoft SQL Server\110\Tools\PowerPivotTools\ConfigurationTool\Resources\PowerPivotFarm.wsp"  
    ```  
  
     <span data-ttu-id="fbbe7-129">L'applet de commande retourne le nom de la solution, son ID, et Deployed=False.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-129">The cmdlet returns the name of the solution, its solution ID, and Deployed=False.</span></span> <span data-ttu-id="fbbe7-130">À l'étape suivante, vous déploierez la solution.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-130">In the next step, you will deploy the solution.</span></span>  
  
3.  <span data-ttu-id="fbbe7-131">Exécutez l'applet de commande suivante pour déployer la solution de batterie de serveurs :</span><span class="sxs-lookup"><span data-stu-id="fbbe7-131">Run the next cmdlet to deploy the farm solution:</span></span>  
  
    ```powershell
    Install-SPSolution -Identity PowerPivotFarm.wsp -GACDeployment -Force  
    ```  
  
##  <a name="step-2-deploy-the-powerpivot-web-application-solution-to-central-administration"></a><a name="deployCA"></a><span data-ttu-id="fbbe7-132">Étape 2 : déployer la solution d’application Web PowerPivot dans l’administration centrale</span><span class="sxs-lookup"><span data-stu-id="fbbe7-132">Step 2: Deploy the PowerPivot Web Application Solution to Central Administration</span></span>  
 <span data-ttu-id="fbbe7-133">Après avoir déployé la solution de batterie de serveurs, vous devez déployer la solution d'application Web sur l'Administration centrale.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-133">After you deploy the farm solution, you must deploy the Web application solution to Central Administration.</span></span> <span data-ttu-id="fbbe7-134">Cette étape ajoute le tableau de bord de gestion PowerPivot dans l'Administration centrale.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-134">This step adds the PowerPivot Management Dashboard to Central Administration.</span></span>  
  
1.  <span data-ttu-id="fbbe7-135">Ouvrez SharePoint 2010 Management Shell à l'aide de l'option **Exécuter en tant qu'administrateur** .</span><span class="sxs-lookup"><span data-stu-id="fbbe7-135">Open a SharePoint 2010 Management Shell using the **Run as Administrator** option.</span></span>  
  
2.  <span data-ttu-id="fbbe7-136">Exécutez l'applet de commande suivante pour créer une référence à l'Administration centrale :</span><span class="sxs-lookup"><span data-stu-id="fbbe7-136">Run the following cmdlet to create a reference to Central Administration:</span></span>  
  
    ```powershell
    $centralAdmin = $(Get-SPWebApplication -IncludeCentralAdministration | Where { $_.IsAdministrationWebApplication -eq $TRUE})  
    ```  
  
3.  <span data-ttu-id="fbbe7-137">Exécutez l'applet de commande suivante pour ajouter la solution de batterie de serveurs.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-137">Run the following cmdlet to add the farm solution.</span></span>  
  
    ```powershell
    Add-SPSolution -LiteralPath "C:\Program Files\Microsoft SQL Server\110\Tools\PowerPivotTools\ConfigurationTool\Resources\PowerPivotWebApp.wsp"  
    ```  
  
     <span data-ttu-id="fbbe7-138">L'applet de commande retourne le nom de la solution, son ID, et Deployed=False.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-138">The cmdlet returns the name of the solution, its solution ID, and Deployed=False.</span></span> <span data-ttu-id="fbbe7-139">À l'étape suivante, vous déploierez la solution.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-139">In the next step, you will deploy the solution.</span></span>  
  
4.  <span data-ttu-id="fbbe7-140">Exécutez l'applet de commande suivante pour installer la solution d'application Web sur l'Administration centrale.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-140">Run the next cmdlet to install the web application solution to Central Administration.</span></span>  
  
    ```powershell
    Install-SPSolution -Identity PowerPivotWebApp.wsp -GACDeployment -Force -WebApplication $centralAdmin  
    ```  
  
 <span data-ttu-id="fbbe7-141">Maintenant que la solution d'application Web est déployée sur l'Administration centrale, vous pouvez recourir à cette dernière pour effectuer toutes les étapes de configuration restantes.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-141">Now that the web application solution is deployed to Central Administration, you can use Central Administration to complete all remaining configuration steps.</span></span>  
  
##  <a name="step-3-deploy-the-powerpivot-web-application-solution-to-other-web-applications"></a><a name="deployUI"></a><span data-ttu-id="fbbe7-142">Étape 3 : déployer la solution d’application Web PowerPivot sur d’autres applications Web</span><span class="sxs-lookup"><span data-stu-id="fbbe7-142">Step 3: Deploy the PowerPivot Web Application Solution to Other Web Applications</span></span>  
 <span data-ttu-id="fbbe7-143">Dans la tâche précédente, vous avez déployé Powerpivotwebapp.wsp sur l'Administration centrale.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-143">In the previous task, you deployed Powerpivotwebapp.wsp to Central Administration.</span></span> <span data-ttu-id="fbbe7-144">Dans cette section, vous allez déployer powerpivotwebapp.wsp sur chaque application Web existante qui prend en charge l'accès aux données PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-144">In this section, you deploy the powerpivotwebapp.wsp on each existing web application that supports PowerPivot data access.</span></span> <span data-ttu-id="fbbe7-145">Si vous ajoutez des applications Web supplémentaires par la suite, assurez-vous que vous répétez cette étape pour chacune de ces applications.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-145">If you add more web applications later, be sure to repeat this step for those additional web applications.</span></span>  
  
1.  <span data-ttu-id="fbbe7-146">Dans l'Administration centrale, sous Paramètres système, cliquez sur **Gérer les solutions de la batterie**.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-146">In Central Administration, in System Settings, click **Manage farm solutions**.</span></span>  
  
2.  <span data-ttu-id="fbbe7-147">Cliquez sur **powerpivotwebapp. wsp**.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-147">Click **powerpivotwebapp.wsp**.</span></span>  
  
3.  <span data-ttu-id="fbbe7-148">Cliquez sur **Déployer la solution**.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-148">Click **Deploy Solution**.</span></span>  
  
4.  <span data-ttu-id="fbbe7-149">Dans **déployer sur ?**, sélectionnez l’application Web SharePoint pour laquelle vous souhaitez ajouter la prise en charge des fonctionnalités PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-149">In **Deploy To?**, select the SharePoint web application for which you want to add PowerPivot feature support.</span></span>  
  
5.  <span data-ttu-id="fbbe7-150">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-150">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="fbbe7-151">Répétez ces opérations pour les autres applications Web SharePoint qui prendront également en charge l'accès aux données PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-151">Repeat for other SharePoint web applications that will also support PowerPivot data access.</span></span>  
  
##  <a name="redeploy-or-retract-the-solution"></a><a name="retract"></a> <span data-ttu-id="fbbe7-152">Redéployer ou vous retirer la solution</span><span class="sxs-lookup"><span data-stu-id="fbbe7-152">Redeploy or retract the Solution</span></span>  
 <span data-ttu-id="fbbe7-153">Bien que l'Administration centrale de SharePoint permette de retirer une solution, vous n'avez pas besoin de retirer le fichier powerpivotwebapp.wsp, sauf si vous dépannez une installation de manière systématique ou si vous corrigez un problème de déploiement.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-153">Although SharePoint Central Administration provides solution retraction, you do not need to retract the powerpivotwebapp.wsp file unless you are systematically troubleshooting an installation or patch deployment problem.</span></span>  
  
1.  <span data-ttu-id="fbbe7-154">Dans l'Administration centrale de SharePoint 2010, sous Paramètres système, cliquez sur **Gérer les solutions de la batterie**.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-154">In SharePoint 2010 Central Administration, in System Settings, click **Manage farm solutions**.</span></span>  
  
2.  <span data-ttu-id="fbbe7-155">Cliquez sur **Powerpivotwebapp.wsp**.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-155">Click **Powerpivotwebapp.wsp**.</span></span>  
  
3.  <span data-ttu-id="fbbe7-156">Cliquez sur **Retirer la solution**.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-156">Click **Retract Solution**.</span></span>  
  
 <span data-ttu-id="fbbe7-157">Si vous rencontrez des problèmes de déploiement de serveur que vous suivez dans la solution de batterie de serveurs, vous pouvez le redéployer en exécutant l’option **réparer** dans l’outil de configuration de PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-157">If you encounter server deployment issues that you trace back to the farm solution, you can redeploy it by running the **Repair** option in the PowerPivot Configuration Tool.</span></span> <span data-ttu-id="fbbe7-158">Il est préférable de réparer les opérations via l'outil, car vous aurez moins d'étapes à effectuer.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-158">Repair operations via the tool is preferred because it requires fewer steps on your part.</span></span> <span data-ttu-id="fbbe7-159">Pour plus d’informations, consultez [configurer ou réparer PowerPivot pour SharePoint 2010 &#40;outil de configuration de PowerPivot&#41;](../configure-repair-powerpivot-sharepoint-2010.md).</span><span class="sxs-lookup"><span data-stu-id="fbbe7-159">For more information, see [Configure or Repair PowerPivot for SharePoint 2010 &#40;PowerPivot Configuration Tool&#41;](../configure-repair-powerpivot-sharepoint-2010.md).</span></span>  
  
 <span data-ttu-id="fbbe7-160">Si vous souhaitez néanmoins redéployer toutes les solutions, veillez à le faire dans cet ordre :</span><span class="sxs-lookup"><span data-stu-id="fbbe7-160">If you still want to re-deploy all solutions, be sure to do so in this order:</span></span>  
  
1.  <span data-ttu-id="fbbe7-161">Retirez la solution d'application Web PowerPivot de toutes les applications Web SharePoint qui l'utilisent.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-161">Retract the PowerPivot Web application solution from all SharePoint web applications that use it.</span></span>  
  
2.  <span data-ttu-id="fbbe7-162">Retirez la solution de batterie PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-162">Retract the PowerPivot farm solution.</span></span>  
  
3.  <span data-ttu-id="fbbe7-163">Redéployez la solution de batterie PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-163">Redeploy the PowerPivot farm solution.</span></span>  
  
4.  <span data-ttu-id="fbbe7-164">Redéployez la solution d'application Web PowerPivot sur toutes les applications Web SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-164">Redeploy the PowerPivot Web application solution to all SharePoint web applications.</span></span>  
  
##  <a name="about-the-powerpivot-solutions"></a><a name="intro"></a><span data-ttu-id="fbbe7-165">À propos des solutions PowerPivot</span><span class="sxs-lookup"><span data-stu-id="fbbe7-165">About the PowerPivot Solutions</span></span>  
 <span data-ttu-id="fbbe7-166">PowerPivot pour SharePoint utilise deux packages de solution pour déployer ses fichiers programme et ses pages d'application dans la batterie de serveurs et dans des applications Web individuelles.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-166">PowerPivot for SharePoint uses two solution packages to deploy its application pages and program files to the farm and to individual web applications.</span></span>  
  
-   <span data-ttu-id="fbbe7-167">La solution de batterie est globale.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-167">The farm solution is global.</span></span> <span data-ttu-id="fbbe7-168">Elle est déployée une fois, puis reste automatiquement à la disposition des nouveaux serveurs PowerPivot pour SharePoint que vous ajouterez ultérieurement à la batterie.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-168">It is deployed once and then becomes automatically available to any new PowerPivot for SharePoint servers that you add to the farm later.</span></span>  
  
-   <span data-ttu-id="fbbe7-169">La solution d'application Web est spécifique aux applications et doit être déployée sur chaque application Web de la batterie de serveurs, notamment sur l'application Web Administration centrale.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-169">The web application solution is application-specific and must be deployed to each web application in the farm, including the Central Administration web application.</span></span>  
  
 <span data-ttu-id="fbbe7-170">Chaque solution est déployée différemment.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-170">Each solution is deployed differently.</span></span>  <span data-ttu-id="fbbe7-171">La solution de batterie de serveurs est déployée une fois, après l'installation de la première instance de PowerPivot pour SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-171">The farm solution is deployed once, after the first PowerPivot for SharePoint instance is installed.</span></span> <span data-ttu-id="fbbe7-172">Pour déployer la solution de batterie de serveurs, utilisez l'outil de configuration PowerPivot ou les applets de commande PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-172">To deploy the farm solution, you use the PowerPivot Configuration Tool or PowerShell cmdlets.</span></span>  
  
 <span data-ttu-id="fbbe7-173">La solution d'application Web est d'abord déployée sur l'Administration centrale, puis sur d'autres applications Web qui prendront en charge les demandes de données PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-173">The web application solution is initially deployed to Central Administration, followed by subsequent solution deployments to any additional web applications that will support requests for PowerPivot data.</span></span> <span data-ttu-id="fbbe7-174">Pour déployer la solution d'application Web sur l'Administration centrale, vous devez utiliser l'outil de configuration PowerPivot ou l'applet de commande PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-174">To deploy the web application solution to Central Administration, you must use the PowerPivot Configuration Tool or PowerShell cmdlet.</span></span> <span data-ttu-id="fbbe7-175">Pour toutes les autres applications Web, vous pouvez déployer la solution d'application Web manuellement à l'aide de l'Administration centrale ou de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-175">For all other web applications, you can deploy the web application solution manually using Central Administration or PowerShell.</span></span>  
  
|<span data-ttu-id="fbbe7-176">Solution</span><span class="sxs-lookup"><span data-stu-id="fbbe7-176">Solution</span></span>|<span data-ttu-id="fbbe7-177">Description</span><span class="sxs-lookup"><span data-stu-id="fbbe7-177">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="fbbe7-178">Powerpivotfarm.wsp</span><span class="sxs-lookup"><span data-stu-id="fbbe7-178">Powerpivotfarm.wsp</span></span>|<span data-ttu-id="fbbe7-179">Ajoute Microsoft.AnalysisServices.SharePoint.Integration.dll à l'assembly global.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-179">Adds Microsoft.AnalysisServices.SharePoint.Integration.dll to the global assembly.</span></span><br /><br /> <span data-ttu-id="fbbe7-180">Ajoute Microsoft.AnalysisServices.ChannelTransport.dll à l'assembly global.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-180">Adds Microsoft.AnalysisServices.ChannelTransport.dll to the global assembly.</span></span><br /><br /> <span data-ttu-id="fbbe7-181">Installe des fonctionnalités et des fichiers de ressources, et enregistre des types de contenu.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-181">Installs features and resources files, and registers content types.</span></span><br /><br /> <span data-ttu-id="fbbe7-182">Ajoute des modèles de bibliothèque pour la bibliothèque Galerie PowerPivot et les bibliothèques de Flux de données.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-182">Adds library templates for PowerPivot Gallery and Data Feed libraries.</span></span><br /><br /> <span data-ttu-id="fbbe7-183">Des pages d'application sont ajoutées pour la configuration de l'application de service, le Tableau de bord de gestion PowerPivot, l'actualisation des données et la bibliothèque Galerie PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-183">Adds application pages for service application configuration, PowerPivot Management Dashboard, data refresh, and PowerPivot Gallery.</span></span>|  
|<span data-ttu-id="fbbe7-184">powerpivotwebapp.wsp</span><span class="sxs-lookup"><span data-stu-id="fbbe7-184">Powerpivotwebapp.wsp</span></span>|<span data-ttu-id="fbbe7-185">Ajoute les fichiers de ressources Microsoft.AnalysisServices.SharePoint.Integration.dll au dossier des extensions du serveur Web sur le Web frontal.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-185">Adds Microsoft.AnalysisServices.SharePoint.Integration.dll resources files to the web server extensions folder on the Web front-end.</span></span><br /><br /> <span data-ttu-id="fbbe7-186">Ajoute le service Web PowerPivot sur le Web frontal.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-186">Adds PowerPivot Web service to the Web-front end.</span></span><br /><br /> <span data-ttu-id="fbbe7-187">Ajoute la génération de miniatures pour la bibliothèque Galerie PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="fbbe7-187">Adds thumbnail image generation for PowerPivot Gallery.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fbbe7-188">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fbbe7-188">See Also</span></span>  
 <span data-ttu-id="fbbe7-189">[Mettre à niveau PowerPivot pour SharePoint](../../database-engine/install-windows/upgrade-power-pivot-for-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="fbbe7-189">[Upgrade PowerPivot for SharePoint](../../database-engine/install-windows/upgrade-power-pivot-for-sharepoint.md) </span></span>  
 <span data-ttu-id="fbbe7-190">[Administration et configuration du serveur PowerPivot dans l’administration centrale](power-pivot-server-administration-and-configuration-in-central-administration.md) </span><span class="sxs-lookup"><span data-stu-id="fbbe7-190">[PowerPivot Server Administration and Configuration in Central Administration](power-pivot-server-administration-and-configuration-in-central-administration.md) </span></span>  
 [<span data-ttu-id="fbbe7-191">Configuration de PowerPivot à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fbbe7-191">PowerPivot Configuration using Windows PowerShell</span></span>](power-pivot-configuration-using-windows-powershell.md)  
