---
title: Configuration de PowerPivot à l’aide de Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 4d83e53e-04f1-417d-9039-d9e81ae0483d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 83b42da3e676a291bb021c02ee52e9a810207397
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613154"
---
# <a name="powerpivot-configuration-using-windows-powershell"></a><span data-ttu-id="f4598-102">Configuration de PowerPivot à l'aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4598-102">PowerPivot Configuration using Windows PowerShell</span></span>
  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="f4598-103">inclut des applets de commande Windows PowerShell que vous pouvez utiliser pour configurer une installation de [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4598-103">includes Windows PowerShell cmdlets that you can use to configure an installation of [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)].</span></span> <span data-ttu-id="f4598-104">La configuration complète d'une installation avec PowerShell requiert l'utilisation des applets de commande SharePoint et PowerPivot pour SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f4598-104">To fully configure an installation with PowerShell requires the use of both SharePoint cmdlets and PowerPivot for SharePoint cmdlets.</span></span> <span data-ttu-id="f4598-105">La majorité des configurations peut être effectuée avec un des outils de [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f4598-105">A majority of configuration can be completed using one of the [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] tools.</span></span> <span data-ttu-id="f4598-106">Pour plus d'informations sur les outils, consultez [PowerPivot Configuration Tools](power-pivot-configuration-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f4598-106">For more information on the tools, see [PowerPivot Configuration Tools](power-pivot-configuration-tools.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f4598-107">Pour une batterie SharePoint 2010, SharePoint 2010 SP1 doit être installé avant de pouvoir configurer PowerPivot pour SharePoint, ou une batterie de serveurs SharePoint qui utilise un serveur de base de données [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f4598-107">For a SharePoint 2010 farm, SharePoint 2010 SP1 must be installed before you can configure either PowerPivot for SharePoint, or a SharePoint farm that uses a [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] database server.</span></span> <span data-ttu-id="f4598-108">Si vous n'avez pas encore installé le Service Pack, installez-le avant de commencer la configuration du serveur.</span><span class="sxs-lookup"><span data-stu-id="f4598-108">If you have not yet installed the service pack, install it before you begin configuring the server.</span></span>  
  
## <a name="benefits-of-configuring-powerpivot-for-sharepoint-using-powershell"></a><span data-ttu-id="f4598-109">Avantages de la configuration de PowerPivot pour SharePoint à l'aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4598-109">Benefits of Configuring PowerPivot for SharePoint Using PowerShell</span></span>  
 <span data-ttu-id="f4598-110">Générez des fichiers de script Windows PowerShell (.ps1) pour automatiser les tâches de configuration.</span><span class="sxs-lookup"><span data-stu-id="f4598-110">You can build Windows PowerShell script (.ps1) files to automate configuration tasks.</span></span> <span data-ttu-id="f4598-111">Cette approche est recommandée si vous avez besoin d'une installation à base de script et d'étapes de configuration que vous pouvez exécuter sur n'importe quel serveur.</span><span class="sxs-lookup"><span data-stu-id="f4598-111">This approach is recommended if you require scripted installation and configuration steps that you can run on any server.</span></span> <span data-ttu-id="f4598-112">Vous pouvez avoir besoin d'un tel script dans le cadre d'un plan de récupération d'urgence afin de reconstruire un serveur en cas de défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="f4598-112">You might require such a script as part of a disaster recovery plan for rebuilding a server in the event of a hardware failure.</span></span>  
  
## <a name="view-a-list-of-the-powerpivot-cmdlets-on-a-server"></a><span data-ttu-id="f4598-113">Afficher une liste des applets de commande PowerPivot sur un serveur</span><span class="sxs-lookup"><span data-stu-id="f4598-113">View a list of the PowerPivot Cmdlets on a Server</span></span>  
 <span data-ttu-id="f4598-114">Pour afficher le contenu et des exemples des [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] applets de commande, consultez [référence PowerShell pour PowerPivot pour SharePoint](/sql/analysis-services/powershell/powershell-reference-for-power-pivot-for-sharepoint).</span><span class="sxs-lookup"><span data-stu-id="f4598-114">To see content and examples of the [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] cmdlets, see [PowerShell Reference for PowerPivot for SharePoint](/sql/analysis-services/powershell/powershell-reference-for-power-pivot-for-sharepoint).</span></span>  
  
 <span data-ttu-id="f4598-115">Pour utiliser PowerShell pour afficher une liste des applets de commande PowerPivot :</span><span class="sxs-lookup"><span data-stu-id="f4598-115">To use PowerShell to view a list of the PowerPivot cmdlets:</span></span>  
  
1.  <span data-ttu-id="f4598-116">Ouvrez SharePoint Management Shell à l'aide de l'option **Exécuter en tant qu'administrateur** .</span><span class="sxs-lookup"><span data-stu-id="f4598-116">Open SharePoint Management Shell using the **Run as Administrator** option.</span></span>  
  
2.  <span data-ttu-id="f4598-117">Entrez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f4598-117">Enter the following command:</span></span>  
  
    ```powershell
    Get-Help *powerpivot*  
    ```  
  
     <span data-ttu-id="f4598-118">Vous devez voir une liste d'applets de commande dont le nom inclut PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="f4598-118">You should see a list of cmdlets that include PowerPivot in the cmdlet name.</span></span> <span data-ttu-id="f4598-119">Par exemple, `Get-PowerPivotServiceApplication`.</span><span class="sxs-lookup"><span data-stu-id="f4598-119">For example `Get-PowerPivotServiceApplication`.</span></span> <span data-ttu-id="f4598-120">Le nombre d'applets de commande disponibles dépend de la version d'Analysis Services que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="f4598-120">The number of cmdlets available depends on the version of Analysis Services you are using.</span></span>  
  
    -   <span data-ttu-id="f4598-121">10 applets de commande avec le serveur SQL Server 2012 SP1 Analysis Services configuré en mode SharePoint et SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="f4598-121">10 cmdlets with SQL Server 2012 SP1 Analysis Services server configured in SharePoint mode, and SharePoint 2013.</span></span> <span data-ttu-id="f4598-122">La version 2012 SP1 utilise une nouvelle architecture qui permet au serveur d'analyse de s'exécuter en dehors de la batterie de serveurs SharePoint et nécessite moins d'applets de commande de gestion Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4598-122">The 2012 SP1 version utilizes a new architecture that allows the Analysis Server to run outside the SharePoint farm and requires fewer management Windows PowerShell cmdlets.</span></span>  
  
    -   <span data-ttu-id="f4598-123">17 applets de commande avec le serveur SQL Server 2012 Analysis Services configuré en mode SharePoint et SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="f4598-123">17 cmdlets with SQL Server 2012 Analysis Services server configured in SharePoint mode, and SharePoint 2010.</span></span>  
  
     <span data-ttu-id="f4598-124">Si aucune commande n’est retournée dans la liste ou si vous voyez un message d’erreur semblable à « `get-help could not find *powerpivot* in a help file in this session.` », consultez la section suivante de cette rubrique pour obtenir des instructions sur l’activation des applets de commande PowerPivot sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="f4598-124">If no commands are returned in the list or you see an error message similar to "`get-help could not find *powerpivot* in a help file in this session.`", see the next section in this topic for instructions on how to enable the PowerPivot cmdlets on the server.</span></span>  
  
     <span data-ttu-id="f4598-125">Toutes les applets de commande intègrent un système d'aide en ligne.</span><span class="sxs-lookup"><span data-stu-id="f4598-125">All cmdlets have online help.</span></span> <span data-ttu-id="f4598-126">L'exemple suivant montre comment afficher l'aide en ligne pour l'applet de commande `New-PowerPivotServiceApplication` :</span><span class="sxs-lookup"><span data-stu-id="f4598-126">The following example shows how to view the online help for the `New-PowerPivotServiceApplication` cmdlet:</span></span>  
  
    ```powershell
    Get-Help new-powerpivotserviceapplication -Full  
    ```  
  
     <span data-ttu-id="f4598-127">Sinon, pour afficher uniquement les exemples, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="f4598-127">Alternatively, to view just the examples, use the following syntax:</span></span>  
  
    ```powershell
    Get-Help new-powerpivotserviceapplication -Example  
    ```  
  
## <a name="enable-powerpivot-cmdlets-on-a-server"></a><span data-ttu-id="f4598-128">Activer les applets de commande PowerPivot sur un serveur</span><span class="sxs-lookup"><span data-stu-id="f4598-128">Enable PowerPivot Cmdlets on a Server</span></span>  
 <span data-ttu-id="f4598-129">Les applets de commande PowerPivot sont disponibles après que vous avez installé PowerPivot pour SharePoint et déployer la solution de batterie de serveurs.</span><span class="sxs-lookup"><span data-stu-id="f4598-129">PowerPivot cmdlets are available after you install PowerPivot for SharePoint and deploy the farm solution.</span></span> <span data-ttu-id="f4598-130">Les solutions sont déployées lorsque vous appelez l'outil de configuration PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="f4598-130">The solutions are deployed when you ran the PowerPivot Configuration tool.</span></span> <span data-ttu-id="f4598-131">Suivez ces étapes pour pouvoir utiliser des applets de commande :</span><span class="sxs-lookup"><span data-stu-id="f4598-131">Follow these steps to enable the use of cmdlets:</span></span>  
  
1.  <span data-ttu-id="f4598-132">Ouvrez SharePoint Management Shell à l'aide de l'option **Exécuter en tant qu'administrateur** .</span><span class="sxs-lookup"><span data-stu-id="f4598-132">Open SharePoint Management Shell using the **Run as Administrator** option.</span></span>  
  
2.  <span data-ttu-id="f4598-133">Exécutez la première applet de commande :</span><span class="sxs-lookup"><span data-stu-id="f4598-133">Run the first cmdlet:</span></span>  
  
    ```powershell
    Add-SPSolution -LiteralPath "C:\Program Files\Microsoft SQL Server\110\Tools\PowerPivotTools\ConfigurationTool\Resources\PowerPivotFarm.wsp"  
    ```  
  
     <span data-ttu-id="f4598-134">L'applet de commande retourne le nom de la solution, son ID, et Deployed=False.</span><span class="sxs-lookup"><span data-stu-id="f4598-134">The cmdlet returns the name of the solution, its solution ID, and Deployed=False.</span></span> <span data-ttu-id="f4598-135">À l'étape suivante, vous déployez la solution.</span><span class="sxs-lookup"><span data-stu-id="f4598-135">In the next step, you deploy the solution.</span></span>  
  
3.  <span data-ttu-id="f4598-136">Exécutez la deuxième applet de commande pour déployer la solution :</span><span class="sxs-lookup"><span data-stu-id="f4598-136">Run the second cmdlet to deploy the solution:</span></span>  
  
    ```powershell
    Install-SPSolution -Identity PowerPivotFarm.wsp -GACDeployment -Force  
    ```  
  
4.  <span data-ttu-id="f4598-137">Fermez la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="f4598-137">Close the window.</span></span> <span data-ttu-id="f4598-138">Rouvrez-la, à nouveau à l'aide de l'option **Exécuter en tant qu'administrateur** .</span><span class="sxs-lookup"><span data-stu-id="f4598-138">Reopen it, again using the **Run as Administrator** option.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="f4598-139">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="f4598-139">Related Content</span></span>  
 [<span data-ttu-id="f4598-140">Administration et configuration d’un serveur PowerPivot dans l’Administration centrale</span><span class="sxs-lookup"><span data-stu-id="f4598-140">PowerPivot Server Administration and Configuration in Central Administration</span></span>](power-pivot-server-administration-and-configuration-in-central-administration.md)  
  
 [<span data-ttu-id="f4598-141">Outils de configuration de PowerPivot</span><span class="sxs-lookup"><span data-stu-id="f4598-141">PowerPivot Configuration Tools</span></span>](power-pivot-configuration-tools.md)  
  
 [<span data-ttu-id="f4598-142">Référence PowerShell pour PowerPivot pour SharePoint</span><span class="sxs-lookup"><span data-stu-id="f4598-142">PowerShell Reference for PowerPivot for SharePoint</span></span>](/sql/analysis-services/powershell/powershell-reference-for-power-pivot-for-sharepoint)  
