---
title: Utiliser PowerShell pour modifier et répertorier Reporting Services propriétaires d’abonnement et exécuter un abonnement | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0fa6cb36-68fc-4fb8-b1dc-ae4f12bf6ff0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b274dc190d8830a2cf7b55110f15267a00c581e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610421"
---
# <a name="use-powershell-to-change-and-list-reporting-services-subscription-owners-and-run-a-subscription"></a><span data-ttu-id="aca25-102">Utiliser PowerShell pour modifier et répertorier les propriétaires d’abonnements Reporting Services, et exécuter un abonnement</span><span class="sxs-lookup"><span data-stu-id="aca25-102">Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription</span></span>
  <span data-ttu-id="aca25-103">À compter de [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)][!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] , vous pouvez transférer par programmation la propriété d’un abonnement [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] d’un utilisateur à un autre.</span><span class="sxs-lookup"><span data-stu-id="aca25-103">Starting with [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)][!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] you can programmatically transfer the ownership of a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] subscription from one user to another.</span></span> <span data-ttu-id="aca25-104">Cette rubrique fournit plusieurs scripts Windows PowerShell que vous pouvez utiliser pour modifier ou simplement dresser la liste des appartenances aux abonnements.</span><span class="sxs-lookup"><span data-stu-id="aca25-104">This topic provides several Windows PowerShell scripts you can use to change or simply list subscription ownership.</span></span> <span data-ttu-id="aca25-105">Chaque exemple comprend un exemple de syntaxe pour le mode Natif et le mode SharePoint.</span><span class="sxs-lookup"><span data-stu-id="aca25-105">Each sample includes sample syntax for both Native mode and SharePoint mode.</span></span> <span data-ttu-id="aca25-106">Une fois que vous avez modifié le propriétaire d'un abonnement, celui-ci s'exécute dans le contexte de sécurité du nouveau propriétaire et le champ User!UserID du rapport affiche la valeur du nouveau propriétaire.</span><span class="sxs-lookup"><span data-stu-id="aca25-106">After you change the subscription owner, the subscription will then execute in the security context of the new owner, and the User!UserID field in the report will display the value of new owner.</span></span> <span data-ttu-id="aca25-107">Pour plus d’informations sur le modèle objet appelé par les exemples PowerShell, consultez <xref:ReportService2010.ReportingService2010.ChangeSubscriptionOwner%2A></span><span class="sxs-lookup"><span data-stu-id="aca25-107">For more information on the object model the PowerShell samples call, see <xref:ReportService2010.ReportingService2010.ChangeSubscriptionOwner%2A></span></span>

 <span data-ttu-id="aca25-108">![Contenu relatif à PowerShell](../media/rs-powershellicon.jpg "Contenu relatif à PowerShell")</span><span class="sxs-lookup"><span data-stu-id="aca25-108">![PowerShell related content](../media/rs-powershellicon.jpg "PowerShell related content")</span></span>

||
|-|
|<span data-ttu-id="aca25-109">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Mode natif &#124; [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Mode SharePoint</span><span class="sxs-lookup"><span data-stu-id="aca25-109">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Native mode &#124; [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>|

 <span data-ttu-id="aca25-110">**Dans cette rubrique :**</span><span class="sxs-lookup"><span data-stu-id="aca25-110">**In this topic:**</span></span>

-   [<span data-ttu-id="aca25-111">Pour utiliser les scripts</span><span class="sxs-lookup"><span data-stu-id="aca25-111">How to use the scripts</span></span>](#bkmk_how_to)

-   [<span data-ttu-id="aca25-112">Script : dresser la liste des propriétaires de tous les abonnements</span><span class="sxs-lookup"><span data-stu-id="aca25-112">Script: List the ownership of all subscriptions</span></span>](#bkmk_list_ownership_all)

-   [<span data-ttu-id="aca25-113">Script : dresser la liste de tous les abonnements détenus par un utilisateur spécifique</span><span class="sxs-lookup"><span data-stu-id="aca25-113">Script: List all subscriptions owned by a specific user</span></span>](#bkmk_list_all_one_user)

-   [<span data-ttu-id="aca25-114">Script : modifier la propriété de tous les abonnements détenus par un utilisateur spécifique</span><span class="sxs-lookup"><span data-stu-id="aca25-114">Script: Change ownership for all subscriptions owned by a specific user</span></span>](#bkmk_change_all)

-   [<span data-ttu-id="aca25-115">Script : dresser la liste de tous les abonnements associés à un rapport spécifique</span><span class="sxs-lookup"><span data-stu-id="aca25-115">Script: List all subscriptions associated with a specific report</span></span>](#bkmk_list_for_1_report)

-   [<span data-ttu-id="aca25-116">Script : modifier la propriété d'un abonnement spécifique</span><span class="sxs-lookup"><span data-stu-id="aca25-116">Script: Change ownership of a specific subscription</span></span>](#bkmk_change_all_1_subscription)

-   [<span data-ttu-id="aca25-117">Script : exécuter (déclencher) un seul abonnement</span><span class="sxs-lookup"><span data-stu-id="aca25-117">Script: Run (fire) a single subscription</span></span>](#bkmk_run_1_subscription)

##  <a name="how-to-use-the-scripts"></a><a name="bkmk_how_to"></a> <span data-ttu-id="aca25-118">Pour utiliser les scripts</span><span class="sxs-lookup"><span data-stu-id="aca25-118">How to use the scripts</span></span>

### <a name="permissions"></a><span data-ttu-id="aca25-119">Autorisations</span><span class="sxs-lookup"><span data-stu-id="aca25-119">Permissions</span></span>
 <span data-ttu-id="aca25-120">Cette section récapitule les niveaux d'autorisation requis pour utiliser chacune des méthodes pour le mode Natif et le mode SharePoint [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aca25-120">This section summarizes the permission levels required to use each of the methods for both Native and SharePoint mode [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="aca25-121">Les scripts de cette rubrique utilisent les méthodes [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] suivantes :</span><span class="sxs-lookup"><span data-stu-id="aca25-121">The scripts in this topic use the following [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] methods:</span></span>

-   [<span data-ttu-id="aca25-122">Méthode ReportingService2010.ListSubscriptions</span><span class="sxs-lookup"><span data-stu-id="aca25-122">ReportingService2010.ListSubscriptions Method</span></span>](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.listsubscriptions.aspx)

-   [<span data-ttu-id="aca25-123">Méthode ReportingService2010.ChangeSubscriptionOwner</span><span class="sxs-lookup"><span data-stu-id="aca25-123">ReportingService2010.ChangeSubscriptionOwner Method</span></span>](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.changesubscriptionowner.aspx)

-   [<span data-ttu-id="aca25-124">ReportingService2010.ListChildren</span><span class="sxs-lookup"><span data-stu-id="aca25-124">ReportingService2010.ListChildren</span></span>](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.listchildren.aspx)

-   <span data-ttu-id="aca25-125">La méthode [ReportingService2010.FireEvent](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.fireevent.aspx) est utilisée uniquement dans le dernier script pour déclencher l'exécution d'un abonnement spécifique.</span><span class="sxs-lookup"><span data-stu-id="aca25-125">The method [ReportingService2010.FireEvent](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.fireevent.aspx) is only used in the last script to trigger a specific subscription to run.</span></span> <span data-ttu-id="aca25-126">Si vous ne prévoyez pas d'utiliser ce script, vous pouvez ignorer les exigences relatives aux autorisations pour la méthode FireEvent.</span><span class="sxs-lookup"><span data-stu-id="aca25-126">If you do not plan to use that script you can ignore the permission requirements for the FireEvent method.</span></span>

 <span data-ttu-id="aca25-127">**Mode natif :**</span><span class="sxs-lookup"><span data-stu-id="aca25-127">**Native mode:**</span></span>

-   <span data-ttu-id="aca25-128">Répertorier les abonnements : (lien hypertexte « https://technet.microsoft.com/library/microsoft.reportingservices.interfaces.reportoperation.aspx » ReadSubscription sur le rapport et l’utilisateur est le propriétaire de l’abonnement) ou ReadAnySubscription</span><span class="sxs-lookup"><span data-stu-id="aca25-128">List Subscriptions: ( HYPERLINK "https://technet.microsoft.com/library/microsoft.reportingservices.interfaces.reportoperation.aspx" ReadSubscription on the report AND the user is the subscription owner) OR ReadAnySubscription</span></span>

-   <span data-ttu-id="aca25-129">Modifier des abonnements : l'utilisateur doit être membre du groupe BUILTIN\\Administrateurs</span><span class="sxs-lookup"><span data-stu-id="aca25-129">Change Subscriptions: The user must be a member of the BUILTIN\Administrators group</span></span>

-   <span data-ttu-id="aca25-130">Dresser la liste des enfants : ReadProperties on Item</span><span class="sxs-lookup"><span data-stu-id="aca25-130">List Children: ReadProperties on Item</span></span>

-   <span data-ttu-id="aca25-131">Déclencher un événement : GenerateEvents (Système)</span><span class="sxs-lookup"><span data-stu-id="aca25-131">Fire Event: GenerateEvents (System)</span></span>

 <span data-ttu-id="aca25-132">**Mode SharePoint :**</span><span class="sxs-lookup"><span data-stu-id="aca25-132">**SharePoint mode:**</span></span>

-   <span data-ttu-id="aca25-133">Répertorier les abonnements : ManageAlerts ou (HYPERLINK " https://technet.microsoft.com/library/microsoft.sharepoint.spbasepermissions.aspx " CreateAlerts sur le rapport et l’utilisateur est le propriétaire de l’abonnement et l’abonnement est un abonnement chronométré).</span><span class="sxs-lookup"><span data-stu-id="aca25-133">List Subscriptions: ManageAlerts OR ( HYPERLINK "https://technet.microsoft.com/library/microsoft.sharepoint.spbasepermissions.aspx" CreateAlerts on the report AND the user is the subscription owner and the subscription is a timed subscription).</span></span>

-   <span data-ttu-id="aca25-134">Modifier des abonnements : ManageWeb</span><span class="sxs-lookup"><span data-stu-id="aca25-134">Change Subscriptions: ManageWeb</span></span>

-   <span data-ttu-id="aca25-135">Dresser la liste des enfants : ViewListItems</span><span class="sxs-lookup"><span data-stu-id="aca25-135">List Children: ViewListItems</span></span>

-   <span data-ttu-id="aca25-136">Déclencher un événement : ManageWeb</span><span class="sxs-lookup"><span data-stu-id="aca25-136">Fire Event: ManageWeb</span></span>

 <span data-ttu-id="aca25-137">Pour plus d'informations, consultez [Comparer des rôles et des tâches dans Reporting Services pour des autorisations et des groupes SharePoint](../reporting-services-roles-tasks-vs-sharepoint-groups-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="aca25-137">For more information, see [Compare Roles and Tasks in Reporting Services to SharePoint Groups and Permissions](../reporting-services-roles-tasks-vs-sharepoint-groups-permissions.md).</span></span>

### <a name="script-usage"></a><span data-ttu-id="aca25-138">Utilisation des scripts</span><span class="sxs-lookup"><span data-stu-id="aca25-138">Script usage</span></span>
 <span data-ttu-id="aca25-139">**Créer les fichiers de scripts (.ps1)**</span><span class="sxs-lookup"><span data-stu-id="aca25-139">**Create Script files (.ps1)**</span></span>

1.  <span data-ttu-id="aca25-140">Créez un dossier nommé **c:\scripts**.</span><span class="sxs-lookup"><span data-stu-id="aca25-140">Create a folder named **c:\scripts**.</span></span> <span data-ttu-id="aca25-141">Si vous choisissez un autre dossier, modifiez le nom du dossier utilisé dans les exemples d'instructions de syntaxe de ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="aca25-141">If you choose a different folder then modify the folder name used in the example command line syntax statements.</span></span>

2.  <span data-ttu-id="aca25-142">Créez un fichier texte pour chaque script et enregistrez les fichiers dans le dossier c:\scripts.</span><span class="sxs-lookup"><span data-stu-id="aca25-142">Create a text file for each script and save the files to the c:\scripts folder.</span></span> <span data-ttu-id="aca25-143">Lorsque vous créez les fichiers .ps1, utilisez le nom mentionné dans chaque exemple de syntaxe de ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="aca25-143">When you create the .ps1 files, use the name from each example command line syntax.</span></span>

3.  <span data-ttu-id="aca25-144">Ouvrez une invite de commandes avec les privilèges d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="aca25-144">Open a command prompt with administrative privileges.</span></span>

4.  <span data-ttu-id="aca25-145">Exécutez chaque fichier de script, à l'aide de l'exemple de syntaxe de ligne de commande fourni avec chaque exemple.</span><span class="sxs-lookup"><span data-stu-id="aca25-145">Run each script file, using the sample command line syntax provided with each example.</span></span>

 <span data-ttu-id="aca25-146">**Environnements testés**</span><span class="sxs-lookup"><span data-stu-id="aca25-146">**Tested environments**</span></span>

 <span data-ttu-id="aca25-147">Les scripts de cette rubrique ont été testés sur PowerShell version 3 et avec les versions suivantes de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="aca25-147">The scripts in this topic were tested on PowerShell version 3 and with the following versions of [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]:</span></span>

-   [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]

-   [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]

-   [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)]

##  <a name="script-list-the-ownership-of-all-subscriptions"></a><a name="bkmk_list_ownership_all"></a> <span data-ttu-id="aca25-148">Script : dresser la liste des propriétaires de tous les abonnements</span><span class="sxs-lookup"><span data-stu-id="aca25-148">Script: List the ownership of all subscriptions</span></span>
 <span data-ttu-id="aca25-149">Ce script dresse la liste de tous les abonnements sur un site.</span><span class="sxs-lookup"><span data-stu-id="aca25-149">This script lists all of the subscriptions on a site.</span></span> <span data-ttu-id="aca25-150">Vous pouvez utiliser ce script pour tester votre connexion ou pour vérifier le chemin d'accès aux rapports et l'ID d'abonnement utilisables dans les autres scripts.</span><span class="sxs-lookup"><span data-stu-id="aca25-150">You can use this script to test your connection or to verify the report path and subscription id for use in the other scripts.</span></span> <span data-ttu-id="aca25-151">Il est également utile pour simplement vérifier quels abonnements existent et qui en est le propriétaire.</span><span class="sxs-lookup"><span data-stu-id="aca25-151">This is also a useful script to simply audit what subscriptions exist and who owns them.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="aca25-152">Syntaxe en mode natif</span><span class="sxs-lookup"><span data-stu-id="aca25-152">Native mode syntax</span></span>

```cmd
powershell c:\scripts\ListAll_SSRS_Subscriptions.ps1 "[server]/reportserver" "/"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="aca25-153">Syntaxe en mode SharePoint</span><span class="sxs-lookup"><span data-stu-id="aca25-153">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\ListAll_SSRS_Subscriptions.ps1 "[server]/_vti_bin/reportserver" "http://[server]"
```

### <a name="script"></a><span data-ttu-id="aca25-154">Script</span><span class="sxs-lookup"><span data-stu-id="aca25-154">Script</span></span>

```powershell
# Parameters
#    server   - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)

Param(
    [string]$server,
    [string]$site
   )

$rs2010 += New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
$subscriptions += $rs2010.ListSubscriptions($site); # use "/" for default native mode site

Write-Host " "
Write-Host "----- $server's Subscriptions: "
$subscriptions | select Path, report, Description, Owner, SubscriptionID, lastexecuted, Status
```

> [!TIP]
>  <span data-ttu-id="aca25-155">Pour vérifier les URL de site en mode SharePoint, utilisez l’applet de commande SharePoint **Get-SPSite**.</span><span class="sxs-lookup"><span data-stu-id="aca25-155">To verify site URLS in SharePoint mode, use the SharePoint cmdlet **Get-SPSite**.</span></span> <span data-ttu-id="aca25-156">Pour plus d’informations, consultez [Get-SPSite](https://technet.microsoft.com/library/ff607950\(v=office.15\).aspx).</span><span class="sxs-lookup"><span data-stu-id="aca25-156">For more information, see [Get-SPSite](https://technet.microsoft.com/library/ff607950\(v=office.15\).aspx).</span></span>

##  <a name="script-list-all-subscriptions-owned-by-a-specific-user"></a><a name="bkmk_list_all_one_user"></a> <span data-ttu-id="aca25-157">Script : dresser la liste de tous les abonnements détenus par un utilisateur spécifique</span><span class="sxs-lookup"><span data-stu-id="aca25-157">Script: List all subscriptions owned by a specific user</span></span>
 <span data-ttu-id="aca25-158">Ce script dresse la liste de tous les abonnements détenus par un utilisateur spécifique.</span><span class="sxs-lookup"><span data-stu-id="aca25-158">This script lists all of the subscriptions owned by a specific user.</span></span> <span data-ttu-id="aca25-159">Vous pouvez utiliser ce script pour tester votre connexion ou pour vérifier le chemin d'accès aux rapports et l'ID d'abonnement utilisables dans les autres scripts.</span><span class="sxs-lookup"><span data-stu-id="aca25-159">You can use this script to test your connection or to verify the report path and subscription id for use in the other scripts.</span></span> <span data-ttu-id="aca25-160">Il est utile en cas de départ d'un employé de votre organisation, si vous souhaitez vérifier les abonnements qu'il détenait afin d'en modifier le propriétaire ou de supprimer les abonnements.</span><span class="sxs-lookup"><span data-stu-id="aca25-160">This script is useful when someone in your organization leaves and you want to verify what subscriptions they owned so you can change the owner or delete the subscription.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="aca25-161">Syntaxe en mode natif</span><span class="sxs-lookup"><span data-stu-id="aca25-161">Native mode syntax</span></span>

```cmd
powershell c:\scripts\ListAll_SSRS_Subscriptions4User.ps1 "[Domain]\[user]" "[server]/reportserver" "/"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="aca25-162">Syntaxe en mode SharePoint</span><span class="sxs-lookup"><span data-stu-id="aca25-162">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\ListAll_SSRS_Subscriptions4User.ps1 "[Domain]\[user]"  "[server]/_vti_bin/reportserver" "http://[server]"
```

### <a name="script"></a><span data-ttu-id="aca25-163">Script</span><span class="sxs-lookup"><span data-stu-id="aca25-163">Script</span></span>

```powershell
# Parameters:
#    currentOwner - DOMAIN\USER that owns the subscriptions you wish to change
#    server        - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)
#    site        - use "/" for default native mode site
Param(
    [string]$currentOwner,
    [string]$server,
    [string]$site
)

$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
$subscriptions += $rs2010.ListSubscriptions($site);

Write-Host " "
Write-Host " "
Write-Host "----- $currentOwner's Subscriptions: "
$subscriptions | select Path, report, Description, Owner, SubscriptionID, lastexecuted,Status | where {$_.owner -eq $currentOwner}
```

##  <a name="script-change-ownership-for-all-subscriptions-owned-by-a-specific-user"></a><a name="bkmk_change_all"></a> <span data-ttu-id="aca25-164">Script : modifier la propriété de tous les abonnements détenus par un utilisateur spécifique</span><span class="sxs-lookup"><span data-stu-id="aca25-164">Script: Change ownership for all subscriptions owned by a specific user</span></span>
 <span data-ttu-id="aca25-165">Ce script affecte un nouveau propriétaire à tous les abonnements détenus par un utilisateur spécifique.</span><span class="sxs-lookup"><span data-stu-id="aca25-165">This script changes the ownership for all subscriptions owned by a specific user to the new owner parameter.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="aca25-166">Syntaxe en mode natif</span><span class="sxs-lookup"><span data-stu-id="aca25-166">Native mode syntax</span></span>

```cmd
powershell c:\scripts\ChangeALL_SSRS_SubscriptionOwner.ps1 "[Domain]\current owner]" "[Domain]\[new owner]" "[server]/reportserver"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="aca25-167">Syntaxe en mode SharePoint</span><span class="sxs-lookup"><span data-stu-id="aca25-167">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\ChangeALL_SSRS_SubscriptionOwner.ps1 "[Domain]\{current owner]" "[Domain]\[new owner]" "[server]/_vti_bin/reportserver"
```

### <a name="script"></a><span data-ttu-id="aca25-168">Script</span><span class="sxs-lookup"><span data-stu-id="aca25-168">Script</span></span>

```powershell
# Parameters:
#    currentOwner - DOMAIN\USER that owns the subscriptions you wish to change
#    newOwner      - DOMAIN\USER that will own the subscriptions you wish to change
#    server        - server and instance name (e.g. myserver/reportserver, myserver/reportserver_db2, myserver/_vti_bin/reportserver)

Param(
    [string]$currentOwner,
    [string]$newOwner,
    [string]$server
)

$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
$items = $rs2010.ListChildren("/", $true);

$subscriptions = @();

ForEach ($item in $items)
{
    if ($item.TypeName -eq "Report")
    {
        $curRepSubs = $rs2010.ListSubscriptions($item.Path);
        ForEach ($curRepSub in $curRepSubs)
        {
            if ($curRepSub.Owner -eq $currentOwner)
            {
                $subscriptions += $curRepSub;
            }
        }
    }
}

Write-Host " "
Write-Host " "
Write-Host -foregroundcolor "green" "-----  $currentOwner's Subscriptions changing ownership to $newOwner : "
$subscriptions | select SubscriptionID, Owner, Path, Description,  Status  | format-table -AutoSize

ForEach ($sub in $subscriptions)
{
    $rs2010.ChangeSubscriptionOwner($sub.SubscriptionID, $newOwner);
}

$subs2 = @();

ForEach ($item in $items)
{
    if ($item.TypeName -eq "Report")
    {
        $subs2 += $rs2010.ListSubscriptions($item.Path);
    }
}
```

##  <a name="script-list-all-subscriptions-associated-with-a-specific-report"></a><a name="bkmk_list_for_1_report"></a> <span data-ttu-id="aca25-169">Script : dresser la liste de tous les abonnements associés à un rapport spécifique</span><span class="sxs-lookup"><span data-stu-id="aca25-169">Script: List all subscriptions associated with a specific report</span></span>
 <span data-ttu-id="aca25-170">Ce script dresse la liste de tous les abonnements associés à un rapport spécifique.</span><span class="sxs-lookup"><span data-stu-id="aca25-170">This script lists all of the subscriptions associated with a specific report.</span></span> <span data-ttu-id="aca25-171">La syntaxe du chemin d'accès au rapport est différente en mode SharePoint, car elle nécessite une URL complète.</span><span class="sxs-lookup"><span data-stu-id="aca25-171">The report path syntax is different SharePoint mode which requires a full URL.</span></span> <span data-ttu-id="aca25-172">Dans les exemples de syntaxe, le nom du rapport utilisé est « title only », qui contient un espace et nécessite par conséquent de placer le nom du rapport entre guillemets simples.</span><span class="sxs-lookup"><span data-stu-id="aca25-172">In the syntax examples, the report name used is "title only", which contains a space and therefore requires the single quotes around the report name.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="aca25-173">Syntaxe en mode natif</span><span class="sxs-lookup"><span data-stu-id="aca25-173">Native mode syntax</span></span>

```cmd
powershell c:\scripts\List_SSRS_One_Reports_Subscriptions.ps1 "[server]/reportserver" "'/reports/title only'" "/"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="aca25-174">Syntaxe en mode SharePoint</span><span class="sxs-lookup"><span data-stu-id="aca25-174">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\List_SSRS_One_Reports_Subscriptions.ps1 "[server]/_vti_bin/reportserver"  "'http://[server]/shared documents/title only.rdl'" "http://[server]"
```

### <a name="script"></a><span data-ttu-id="aca25-175">Script</span><span class="sxs-lookup"><span data-stu-id="aca25-175">Script</span></span>

```powershell
# Parameters:
#    server      - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)
#    reportpath  - path to report in the report server, including report name e.g. /reports/test report >> pass in  "'/reports/title only'"
#    site        - use "/" for default native mode site
Param
(
      [string]$server,
      [string]$reportpath,
      [string]$site
)

$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
$subscriptions += $rs2010.ListSubscriptions($site);

Write-Host " "
Write-Host " "
Write-Host "----- $reportpath 's Subscriptions: "
$subscriptions | select Path, report, Description, Owner, SubscriptionID, lastexecuted,Status | where {$_.path -eq $reportpath}
```

##  <a name="script-change-ownership-of-a-specific-subscription"></a><a name="bkmk_change_all_1_subscription"></a> <span data-ttu-id="aca25-176">Script : modifier la propriété d'un abonnement spécifique</span><span class="sxs-lookup"><span data-stu-id="aca25-176">Script: Change ownership of a specific subscription</span></span>
 <span data-ttu-id="aca25-177">Ce script modifie la propriété d'un abonnement spécifique.</span><span class="sxs-lookup"><span data-stu-id="aca25-177">This script changes the ownership for a specific subscription.</span></span> <span data-ttu-id="aca25-178">L'abonnement est identifié par le paramètre SubscriptionID, que vous passez dans le script.</span><span class="sxs-lookup"><span data-stu-id="aca25-178">The subscription is identified by the SubscriptionID that you pass into the script.</span></span> <span data-ttu-id="aca25-179">Vous pouvez utiliser l'un des scripts de liste d'abonnements pour déterminer le SubscriptionID correct.</span><span class="sxs-lookup"><span data-stu-id="aca25-179">You can use one of the list subscription scripts to determine the correct SubscriptionID.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="aca25-180">Syntaxe en mode natif</span><span class="sxs-lookup"><span data-stu-id="aca25-180">Native mode syntax</span></span>

```cmd
powershell c:\scripts\Change_SSRS_Owner_One_Subscription.ps1 "[Domain]\[new owner]" "[server]/reportserver" "/" "ac5637a1-9982-4d89-9d69-a72a9c3b3150"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="aca25-181">Syntaxe en mode SharePoint</span><span class="sxs-lookup"><span data-stu-id="aca25-181">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\Change_SSRS_Owner_One_Subscription.ps1 "[Domain]\[new owner]" "[server]/_vti_bin/reportserver" "http://[server]" "9660674b-f020-453f-b1e3-d9ba37624519"
```

### <a name="script"></a><span data-ttu-id="aca25-182">Script</span><span class="sxs-lookup"><span data-stu-id="aca25-182">Script</span></span>

```powershell
# Parameters:
#    newOwner       - DOMAIN\USER that will own the subscriptions you wish to change
#    server         - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)
#    site        - use "/" for default native mode site
#    subscriptionID - guid for the single subscription to change

Param(
    [string]$newOwner,
    [string]$server,
    [string]$site,
    [string]$subscriptionid
   )
$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential;

$subscription += $rs2010.ListSubscriptions($site) | where {$_.SubscriptionID -eq $subscriptionid};

Write-Host " "
Write-Host "----- $subscriptionid's Subscription properties: "
$subscription | select Path, report, Description, SubscriptionID, Owner, Status

$rs2010.ChangeSubscriptionOwner($subscription.SubscriptionID, $newOwner)

#refresh the list
$subscription = $rs2010.ListSubscriptions($site) | where {$_.SubscriptionID -eq $subscriptionid}; # use "/" for default native mode site
Write-Host "----- $subscriptionid's Subscription properties: "
$subscription | select Path, report, Description, SubscriptionID, Owner, Status
```

##  <a name="script-run-fire-a-single-subscription"></a><a name="bkmk_run_1_subscription"></a> <span data-ttu-id="aca25-183">Script : exécuter (déclencher) un seul abonnement</span><span class="sxs-lookup"><span data-stu-id="aca25-183">Script: Run (fire) a single subscription</span></span>
 <span data-ttu-id="aca25-184">Ce script exécute un abonnement spécifique à l'aide de la méthode FireEvent.</span><span class="sxs-lookup"><span data-stu-id="aca25-184">This script will run a specific subscription using the FireEvent method.</span></span> <span data-ttu-id="aca25-185">Le script exécute immédiatement l'abonnement quelle que soit la planification configurée pour lui.</span><span class="sxs-lookup"><span data-stu-id="aca25-185">The script will immediately run the subscription regardless of the schedule configured for the subscription.</span></span> <span data-ttu-id="aca25-186">L'EventType est comparé à l'ensemble connu d'événements définis dans le fichier de configuration du serveur de rapports **rsreportserver.config** . Le script utilise le type d'événement suivant pour les abonnements standard :</span><span class="sxs-lookup"><span data-stu-id="aca25-186">The EventType is matched against the known set of events that are defined in the report server configuration file **rsreportserver.config** The script uses the following event type for standard subscriptions:</span></span>

 `<Event>`

 `<Type>TimedSubscription</Type>`

 `</Event>`

 <span data-ttu-id="aca25-187">Pour plus d'informations sur le fichier de configuration, consultez [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="aca25-187">For more information on the configuration file, see [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span></span>

 <span data-ttu-id="aca25-188">Le script comprend la logique de délai « `Start-Sleep -s 6` ». Il y a donc suffisamment de temps pour que l’état mis à jour soit disponible avec la méthode ListSubscription après le déclenchement de l’événement.</span><span class="sxs-lookup"><span data-stu-id="aca25-188">The script includes delay logic "`Start-Sleep -s 6`" so there is time after the event fires, for the updated status to be available with the ListSubscription method.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="aca25-189">Syntaxe en mode natif</span><span class="sxs-lookup"><span data-stu-id="aca25-189">Native mode syntax</span></span>

```cmd
powershell c:\scripts\FireSubscription.ps1 "[server]/reportserver" $null "70366e82-2d3c-4edd-a216-b97e51e26de9"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="aca25-190">Syntaxe en mode SharePoint</span><span class="sxs-lookup"><span data-stu-id="aca25-190">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\FireSubscription.ps1 "[server]/_vti_bin/reportserver" "http://[server]" "c3425c72-580d-423e-805a-41cf9799fd25"
```

### <a name="script"></a><span data-ttu-id="aca25-191">Script</span><span class="sxs-lookup"><span data-stu-id="aca25-191">Script</span></span>

```powershell
# Parameters
#    server         - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)
#    site           - use $null for a native mode server
#    subscriptionid - subscription guid

Param(
  [string]$server,
  [string]$site,
  [string]$subscriptionid
  )

$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
#event type is case sensative to what is in the rsreportserver.config
$rs2010.FireEvent("TimedSubscription",$subscriptionid,$site)

Write-Host " "
Write-Host "----- Subscription ($subscriptionid) status: "
#get list of subscriptions and filter to the specific ID to see the Status and LastExecuted
Start-Sleep -s 6 # slight delay in processing so ListSubscription returns the updated Status and LastExecuted
$subscriptions = $rs2010.ListSubscriptions($site); 
$subscriptions | select Status, Path, report, Description, Owner, SubscriptionID, EventType, lastexecuted | where {$_.SubscriptionID -eq $subscriptionid}
```

## <a name="see-also"></a><span data-ttu-id="aca25-192">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="aca25-192">See Also</span></span>
 <span data-ttu-id="aca25-193"><xref:ReportService2010.ReportingService2010.ListSubscriptions%2A> <xref:ReportService2010.ReportingService2010.ChangeSubscriptionOwner%2A></span><span class="sxs-lookup"><span data-stu-id="aca25-193"><xref:ReportService2010.ReportingService2010.ListSubscriptions%2A> <xref:ReportService2010.ReportingService2010.ChangeSubscriptionOwner%2A></span></span> 
 <xref:ReportService2010.ReportingService2010.ListChildren%2A> 
 <xref:ReportService2010.ReportingService2010.FireEvent%2A>
