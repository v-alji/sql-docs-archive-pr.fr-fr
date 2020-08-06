---
title: Exemple de configuration avec privilèges minimum pour PowerPivot pour SharePoint 2013 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c1e09e6c-52d3-48ab-8c70-818d5d775087
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0188f314e4c354b33d03e6e7948aed1ba4cf8be2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697276"
---
# <a name="example-of-a-minimum-privilege-configuration-for-powerpivot-for-sharepoint-2013"></a><span data-ttu-id="446bd-102">Exemple de configuration avec privilèges minimum pour Power Pivot pour SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="446bd-102">Example of a Minimum-Privilege Configuration for PowerPivot for SharePoint 2013</span></span>
  <span data-ttu-id="446bd-103">Cette rubrique décrit un exemple de configuration de PowerPivot pour SharePoint 2013 avec les privilèges minimums.</span><span class="sxs-lookup"><span data-stu-id="446bd-103">This topic describes an example PowerPivot for SharePoint 2013 configuration with minimum privileges.</span></span> <span data-ttu-id="446bd-104">La configuration utilise un compte différent pour chacun des trois composants et chaque compte dispose du niveau minimum de privilèges.</span><span class="sxs-lookup"><span data-stu-id="446bd-104">The configuration utilizes a different account for each of the three components and each account has the minimum level of privileges.</span></span>  
  
## <a name="summary-of-accounts"></a><span data-ttu-id="446bd-105">Récapitulatif des comptes</span><span class="sxs-lookup"><span data-stu-id="446bd-105">Summary of Accounts</span></span>  
 <span data-ttu-id="446bd-106">PowerPivot pour SharePoint 2013 prend en charge l'utilisation du compte Service réseau pour le compte de service Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="446bd-106">PowerPivot for SharePoint 2013 supports the use of the Network Service account for the Analysis Services service account.</span></span> <span data-ttu-id="446bd-107">Le compte Service réseau n'est pas un scénario pris en charge avec SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="446bd-107">The Network Service account is not a supported scenario with SharePoint 2010.</span></span> <span data-ttu-id="446bd-108">Pour plus d’informations sur les comptes de service, consultez [configurer les comptes de service Windows et les autorisations](../../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md) ( https://msdn.microsoft.com/library/ms143504.aspx) .</span><span class="sxs-lookup"><span data-stu-id="446bd-108">For more information on Service accounts, see [Configure Windows Service Accounts and Permissions](../../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md) (https://msdn.microsoft.com/library/ms143504.aspx).</span></span>  
  
 <span data-ttu-id="446bd-109">Le tableau suivant récapitule les trois comptes utilisés dans cet exemple de configuration avec privilèges minimums.</span><span class="sxs-lookup"><span data-stu-id="446bd-109">The following table summarizes the three accounts used in this example of a minimum privileged configuration.</span></span>  
  
|<span data-ttu-id="446bd-110">Étendue</span><span class="sxs-lookup"><span data-stu-id="446bd-110">Scope</span></span>|<span data-ttu-id="446bd-111">Nom</span><span class="sxs-lookup"><span data-stu-id="446bd-111">Name</span></span>|  
|-----------|----------|  
|<span data-ttu-id="446bd-112">Compte Administrateur SharePoint</span><span class="sxs-lookup"><span data-stu-id="446bd-112">SharePoint Administrator account</span></span>|<span data-ttu-id="446bd-113">**SPAdmin**</span><span class="sxs-lookup"><span data-stu-id="446bd-113">**SPAdmin**</span></span>|  
|<span data-ttu-id="446bd-114">Compte de batterie de serveurs SharePoint</span><span class="sxs-lookup"><span data-stu-id="446bd-114">SharePoint Farm account</span></span>|<span data-ttu-id="446bd-115">**SPFarm**</span><span class="sxs-lookup"><span data-stu-id="446bd-115">**SPFarm**</span></span>|  
|<span data-ttu-id="446bd-116">Compte de service Analysis Services</span><span class="sxs-lookup"><span data-stu-id="446bd-116">Analysis Services service account</span></span>|<span data-ttu-id="446bd-117">**SPsvc**</span><span class="sxs-lookup"><span data-stu-id="446bd-117">**SPsvc**</span></span>|  
  
### <a name="the-sharepoint-administrator-account-spadmin"></a><span data-ttu-id="446bd-118">Compte Administrateur SharePoint (SpAdmin)</span><span class="sxs-lookup"><span data-stu-id="446bd-118">The SharePoint Administrator account (SpAdmin)</span></span>  
 <span data-ttu-id="446bd-119">**SPAdmin** est un compte de domaine que vous utilisez pour installer et configurer la batterie de serveurs.</span><span class="sxs-lookup"><span data-stu-id="446bd-119">**SPAdmin** is a domain account you use to install and configure the farm.</span></span> <span data-ttu-id="446bd-120">Il s’agit du compte utilisé pour exécuter l’Assistant Configuration de SharePoint et l’outil de configuration de PowerPivot pour SharePoint 2013 **. le compte d’administrateur est** le seul compte qui requiert des droits d’administrateur local.</span><span class="sxs-lookup"><span data-stu-id="446bd-120">It is the account used to run the SharePoint Configuration Wizard and the PowerPivot Configuration Tool for SharePoint 2013.The **SPAdmin** account is the only account that requires local Administrator rights.</span></span> <span data-ttu-id="446bd-121">Avant d’exécuter l’outil de configuration de PowerPivot, accordez les privilèges de compte d' **administrateur** à l’instance de base de données SQL Server dans laquelle SharePoint crée des bases de données de contenu et de configuration.</span><span class="sxs-lookup"><span data-stu-id="446bd-121">Before running the PowerPivot Configuration tool, grant the **SPAdmin** account privileges to the SQL Server database instance where SharePoint creates content and configuration databases.</span></span> <span data-ttu-id="446bd-122">Pour configurer le compte SPAdmin dans un scénario avec privilèges minimums, il doit être membre des rôles **securityadmin** et **dbcreator**.</span><span class="sxs-lookup"><span data-stu-id="446bd-122">To configure the SPAdmin account in a minimum privilege scenario, it should be a member of the roles **securityadmin** and **dbcreator**.</span></span>  
  
### <a name="the-farm-account-spfarm"></a><span data-ttu-id="446bd-123">Compte de batterie de serveurs (SPFarm)</span><span class="sxs-lookup"><span data-stu-id="446bd-123">The Farm account (SPFarm)</span></span>  
 <span data-ttu-id="446bd-124">**SPFarm** est un compte de domaine que le service du minuteur SharePoint et l'application Web de l'Administration centrale utilisent pour accéder à la base de données de contenu SharePoint.</span><span class="sxs-lookup"><span data-stu-id="446bd-124">**SPFarm** is a domain account that the SharePoint Timer service and the web application for Central Administration use to access the SharePoint content database.</span></span> <span data-ttu-id="446bd-125">Ce compte n'a pas besoin d'être administrateur local.</span><span class="sxs-lookup"><span data-stu-id="446bd-125">This account does not need to be a local administrator.</span></span> <span data-ttu-id="446bd-126">L’Assistant Configuration SharePoint octroie le privilège minimal approprié dans la base de données SQL Server principale. La configuration de privilèges minimums SQL Server correspond à l’appartenance aux rôles **securityadmin** et **dbcreator**.</span><span class="sxs-lookup"><span data-stu-id="446bd-126">The SharePoint configuration wizard grants the proper minimal privilege in the back-end SQL Server database.The minimum SQL Server privilege configuration is membership in the roles **securityadmin** and **dbcreator**.</span></span>  
  
### <a name="the-service-account-for-powerpivot-service-spsvc"></a><span data-ttu-id="446bd-127">Compte de service pour le service PowerPivot (SPsvc)</span><span class="sxs-lookup"><span data-stu-id="446bd-127">The Service Account for PowerPivot Service (SPsvc)</span></span>  
 <span data-ttu-id="446bd-128">Si une nouvelle batterie de serveurs SharePoint n'est pas configurée avant d'exécuter l'outil de configuration PowerPivot, alors, par défaut, l'outil de configuration PowerPivot crée ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="446bd-128">If a new SharePoint farm is not configured before you run the PowerPivot Configuration tool, then by default the PowerPivot Configuration tool will create the following:</span></span>  
  
-   <span data-ttu-id="446bd-129">Application de service PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="446bd-129">PowerPivot Service application.</span></span>  
  
-   <span data-ttu-id="446bd-130">Application Excel Services.</span><span class="sxs-lookup"><span data-stu-id="446bd-130">Excel Services application.</span></span>  
  
-   <span data-ttu-id="446bd-131">Application Banque d'informations sécurisée.</span><span class="sxs-lookup"><span data-stu-id="446bd-131">Secure Store application.</span></span>  
  
 <span data-ttu-id="446bd-132">L'outil de configuration PowerPivot configure les trois applications de service dans le pool d'applications par défaut.</span><span class="sxs-lookup"><span data-stu-id="446bd-132">The PowerPivot configuration tool configures all three of the service applications in the default application pool.</span></span> <span data-ttu-id="446bd-133">Ce pool d'applications est généralement configuré pour s'exécuter sous le compte SPFarm, lequel a accès à un grand nombre de ressources dont un compte de service n'a pas besoin. Pour transformer l'environnement en un environnement de privilèges minimums, configurez un nouveau compte de domaine qui sera utilisé par le pool d'applications et l'application Web appropriés.</span><span class="sxs-lookup"><span data-stu-id="446bd-133">That application pool is typically configured to run as the SPFarm account, which has access to many resources that a service account does not require.To make the environment a minimum-privileged environment, configure a new domain account to be use by the appropriate application pool and web application.</span></span>  
  
 <span data-ttu-id="446bd-134">**Pour créer un compte de domaine SPsvc à utiliser comme compte de service SharePoint :**</span><span class="sxs-lookup"><span data-stu-id="446bd-134">**To create a new domain account SPsvc to be used as a SharePoint Service account:**</span></span>  
  
1.  <span data-ttu-id="446bd-135">Dans l’administration centrale de SharePoint, cliquez sur **sécurité**.</span><span class="sxs-lookup"><span data-stu-id="446bd-135">In SharePoint Central Administration, click **Security**.</span></span>  
  
2.  <span data-ttu-id="446bd-136">Cliquez sur **configurer les comptes de service**</span><span class="sxs-lookup"><span data-stu-id="446bd-136">Click **Configure Service Accounts**</span></span>  
  
3.  <span data-ttu-id="446bd-137">Cliquez sur **inscrire un nouveau compte géré**.</span><span class="sxs-lookup"><span data-stu-id="446bd-137">Click **Register new managed account**.</span></span>  
  
 <span data-ttu-id="446bd-138">Le compte **SPSvc** ne dispose d'aucun privilège d'administrateur local et SPsvc ne disposera d'aucun privilège dans la base de données SharePoint.</span><span class="sxs-lookup"><span data-stu-id="446bd-138">The **SPSvc** account has no local administrator privileges and SPsvc will not have any privileges in the SharePoint database.</span></span> <span data-ttu-id="446bd-139">Seuls les privilèges requis par SPsvc sont les droits d'administration sur l'instance PowerPivot d'Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="446bd-139">The only privileges SPsvc requires is administrative rights to the PowerPivot Instance of the Analysis Services.</span></span>  
  
 <span data-ttu-id="446bd-140">**Pour configurer le pool d'applications approprié pour utiliser le compte de SPsvc :**</span><span class="sxs-lookup"><span data-stu-id="446bd-140">**To configure the appropriate application pool to use the SPsvc account :**</span></span>  
  
1.  <span data-ttu-id="446bd-141">Dans l’administration centrale de SharePoint, cliquez sur **sécurité**.</span><span class="sxs-lookup"><span data-stu-id="446bd-141">In SharePoint Central Administration, click **Security**.</span></span>  
  
2.  <span data-ttu-id="446bd-142">Cliquez sur **configurer les comptes de service**.</span><span class="sxs-lookup"><span data-stu-id="446bd-142">Click **Configure Service Accounts**.</span></span>  
  
3.  <span data-ttu-id="446bd-143">Sélectionnez le pool d'application de service utilisé par l'application de service PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="446bd-143">Select the service application pool used by the PowerPivot Service application.</span></span> <span data-ttu-id="446bd-144">Ensuite, sélectionnez le compte SPSvc.</span><span class="sxs-lookup"><span data-stu-id="446bd-144">Then select the SPSvc account.</span></span>  
  
 <span data-ttu-id="446bd-145">**Pour accorder l'accès à l'application Web avec PowerShell :**</span><span class="sxs-lookup"><span data-stu-id="446bd-145">**To Grant access to the web application with PowerShell:**</span></span>  
  
1.  <span data-ttu-id="446bd-146">Exécutez SharePoint 2013 Management Shell avec des privilèges d'administrateur.</span><span class="sxs-lookup"><span data-stu-id="446bd-146">Run the SharePoint 2013 Management Shell with administrator privileges.</span></span>  
  
2.  <span data-ttu-id="446bd-147">Exécutez le code PowerShell suivant :</span><span class="sxs-lookup"><span data-stu-id="446bd-147">Run the following PowerShell code:</span></span>  
  
    ```powershell
    $webApp = Get-SPWebApplication "http://<servername>"  
    $webApp.GrantAccessToProcessIdentity("DOMAIN\<ServiceAccountName>")
    ```  
