---
title: Renommer une instance de Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- instances of Analysis Services, renaming
- renaming instances of Analysis Services
- names [Analysis Services], renaming instances
- names [Analysis Services]
ms.assetid: 87494741-4a2e-4fed-8061-418fd1e111c3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 763986d82dda7424f2187daf401424fd256ddd64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702065"
---
# <a name="rename-an-analysis-services-instance"></a><span data-ttu-id="aeadb-102">Renommer une instance d'Analysis Services</span><span class="sxs-lookup"><span data-stu-id="aeadb-102">Rename an Analysis Services Instance</span></span>
  <span data-ttu-id="aeadb-103">Vous pouvez renommer une instance existante de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] à l’aide de la boîte de dialogue **Renommer l’instance** .</span><span class="sxs-lookup"><span data-stu-id="aeadb-103">You can rename an existing instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] by using the **Rename Instance** dialog box.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="aeadb-104">Pendant que l’instance est renommée, l’utilitaire Modification du nom d’instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] s’exécute avec des privilèges élevés et met à jour le nom de service Windows, les comptes de sécurité et les entrées de Registre associées à cette instance.</span><span class="sxs-lookup"><span data-stu-id="aeadb-104">While renaming the instance, the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Instance Rename tool runs under elevated privileges, updating the Windows service name, security accounts, and registry entries associated with that instance.</span></span> <span data-ttu-id="aeadb-105">Pour vous assurer que ces actions sont effectuées, veillez à exécuter cet outil en tant qu'administrateur système local.</span><span class="sxs-lookup"><span data-stu-id="aeadb-105">To ensure that these actions are performed, be sure to run this tool as a local system administrator.</span></span>  
  
 <span data-ttu-id="aeadb-106">L’utilitaire Modification du nom d’instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ne modifie pas le dossier du programme créé pour l’instance d’origine.</span><span class="sxs-lookup"><span data-stu-id="aeadb-106">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Instance Rename tool does not modify the program folder that was created for the original instance.</span></span> <span data-ttu-id="aeadb-107">Ne modifiez pas le nom du dossier du programme pour qu'il corresponde à l'instance que vous renommez.</span><span class="sxs-lookup"><span data-stu-id="aeadb-107">Do not modify the program folder name to match the instance you are renaming.</span></span> <span data-ttu-id="aeadb-108">Le fait de modifier un nom de dossier de programme peut empêcher au programme d'installation de réparer ou désinstaller celle-ci.</span><span class="sxs-lookup"><span data-stu-id="aeadb-108">Changing a program folder name can prevent Setup from repairing or uninstalling the installation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aeadb-109">L’utilitaire Modification du nom d’instance de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] n’est pas pris en charge pour une utilisation dans un environnement de cluster.</span><span class="sxs-lookup"><span data-stu-id="aeadb-109">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Instance Rename tool is not supported for use in a cluster environment.</span></span>  
  
### <a name="to-rename-an-instance-of-analysis-services"></a><span data-ttu-id="aeadb-110">Pour renommer une instance d'Analysis Services</span><span class="sxs-lookup"><span data-stu-id="aeadb-110">To rename an instance of Analysis Services</span></span>  
  
1.  <span data-ttu-id="aeadb-111">Lancez l’outil **modification du nom d’instance** , **asinstancerename.exe**, à partir de C:\Program Files\Microsoft SQL Server\110\Tools\Binn\ManagementStudio.</span><span class="sxs-lookup"><span data-stu-id="aeadb-111">Launch the **Instance Rename** tool, **asinstancerename.exe**, from C:\Program Files\Microsoft SQL Server\110\Tools\Binn\ManagementStudio.</span></span>  
  
2.  <span data-ttu-id="aeadb-112">Dans la boîte de dialogue **Renommer l’instance** , sélectionnez dans la liste **Instance à renommer** l’instance que vous souhaitez renommer.</span><span class="sxs-lookup"><span data-stu-id="aeadb-112">In the **Rename Instance** dialog box, in the **Instance to rename** list, select the instance that you want to rename.</span></span>  
  
3.  <span data-ttu-id="aeadb-113">Dans la zone **Nouveau nom d’instance** , entrez le nouveau nom de l’instance.</span><span class="sxs-lookup"><span data-stu-id="aeadb-113">In the **New instance name** box, enter the new name for the instance.</span></span>  
  
4.  <span data-ttu-id="aeadb-114">Vérifiez que le nom d’utilisateur et le mot de passe sont corrects, puis cliquez sur **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="aeadb-114">Verify that the user name and password are correct, and then click **Rename**.</span></span>  
  
     <span data-ttu-id="aeadb-115">L'instance Analysis Services sera arrêtée et redémarrée dans le cadre du changement de nom.</span><span class="sxs-lookup"><span data-stu-id="aeadb-115">The Analysis Services instance will be stopped and restarted as part of the name change.</span></span>  
  
### <a name="post-rename-checklist"></a><span data-ttu-id="aeadb-116">Liste de contrôle après la modification du nom</span><span class="sxs-lookup"><span data-stu-id="aeadb-116">Post-rename checklist</span></span>  
  
1.  <span data-ttu-id="aeadb-117">Pour récupérer l'accès aux bases de données qui s'exécutent sur l'instance renommée, vous devez mettre à jour manuellement les connexions de données dans Excel ou les autres applications clientes.</span><span class="sxs-lookup"><span data-stu-id="aeadb-117">To resume access to databases that are running on the renamed instance, you will need to manually update the data connections in Excel or other client applications.</span></span> <span data-ttu-id="aeadb-118">Vérifiez également toutes les connexions prédéfinies, telles que les sources de données partagées Reporting Services, les fichiers ODC Excel ou les fichiers de connexion de modèle sémantique BI qui peuvent référencer l'instance que vous venez de renommer.</span><span class="sxs-lookup"><span data-stu-id="aeadb-118">Also check any predefined connections, such as Reporting Services shared data sources, Excel ODC files, or BI Semantic Model connection files that might reference the instance you just renamed.</span></span> <span data-ttu-id="aeadb-119">Pour plus d’informations, consultez [Se connecter à Analysis Services](connect-to-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="aeadb-119">For more information, see [Connect to Analysis Services](connect-to-analysis-services.md).</span></span>  
  
2.  <span data-ttu-id="aeadb-120">Mettez à jour les scripts PowerShell ou AMO (Analysis Management Objects) que vous utilisez régulièrement pour la sauvegarde, la synchronisation ou le traitement des bases de données.</span><span class="sxs-lookup"><span data-stu-id="aeadb-120">Update PowerShell scripts or AMO scripts that you routinely use to backup, synchronize, or process databases.</span></span>  
  
3.  <span data-ttu-id="aeadb-121">Mettez à jour les propriétés des projets [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dans lesquels vous travaillez dans [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aeadb-121">Update project properties for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projects that you work with in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span> <span data-ttu-id="aeadb-122">Pour les instances de serveur en mode tabulaire, veillez à mettre à jour la propriété Serveur d'espace de travail dans le fichier model.bim, ainsi que la propriété Serveur dans le projet.</span><span class="sxs-lookup"><span data-stu-id="aeadb-122">For tabular mode server instances, be sure to update the Workspace Server property on the model.bim file, as well as the Server property on the project.</span></span>  
  
4.  <span data-ttu-id="aeadb-123">Selon la façon dont vous avez spécifié le compte de service, vous devrez peut-être mettre à jour les connexions à la base de données ou les autorisations de fichiers qui accordent des droits d'accès au service (par exemple, si vous utilisez le compte de service pour le traitement des données ou pour accéder aux objets liés sur un autre serveur).</span><span class="sxs-lookup"><span data-stu-id="aeadb-123">Depending on how you specified the service account, you might need to update database logins or file permissions that grant data access rights to the service (for example, if you use the service account to process data or access linked objects on another server).</span></span>  
  
     <span data-ttu-id="aeadb-124">La mise à jour d'une connexion à une base de données ou des autorisations de fichiers est nécessaire si vous avez utilisé un compte virtuel pour configurer le service.</span><span class="sxs-lookup"><span data-stu-id="aeadb-124">Updating a database login or file permissions will be necessary if you used a virtual account to provision the service.</span></span> <span data-ttu-id="aeadb-125">Les comptes virtuels sont basés sur le nom de l'instance, donc si vous renommez l'instance, le compte virtuel est également mis à jour.</span><span class="sxs-lookup"><span data-stu-id="aeadb-125">Virtual accounts are based on the instance name, so if you rename the instance, the virtual account is also updated at the same time.</span></span> <span data-ttu-id="aeadb-126">Cela signifie que toutes les connexions ou autorisations précédentes créées pour l'instance antérieure ne sont plus valides.</span><span class="sxs-lookup"><span data-stu-id="aeadb-126">This means that any previous logins or permissions that you created for the previous instance are no longer valid.</span></span>  
  
     <span data-ttu-id="aeadb-127">L'exemple suivant en est l'illustration.</span><span class="sxs-lookup"><span data-stu-id="aeadb-127">The following example provides an illustration.</span></span> <span data-ttu-id="aeadb-128">Supposons que vous avez installé un serveur en mode tabulaire en tant qu’instance nommée « Tabular » à l’aide du compte virtuel par défaut, ce qui entraîne la configuration suivante :</span><span class="sxs-lookup"><span data-stu-id="aeadb-128">Suppose you installed a tabular mode server as an instance named "Tabular" using the default virtual account, resulting in the following configuration:</span></span>  
  
    1.  <span data-ttu-id="aeadb-129">Nom de l’instance = \<server> \TABULAR</span><span class="sxs-lookup"><span data-stu-id="aeadb-129">Instance name = \<server>\TABULAR</span></span>  
  
    2.  <span data-ttu-id="aeadb-130">Nom du service = MSOLAP$TABULAR</span><span class="sxs-lookup"><span data-stu-id="aeadb-130">Service name = MSOLAP$TABULAR</span></span>  
  
    3.  <span data-ttu-id="aeadb-131">Compte virtuel = NT Service\ MSOLAP$TABULAR</span><span class="sxs-lookup"><span data-stu-id="aeadb-131">Virtual account = NT Service\ MSOLAP$TABULAR</span></span>  
  
     <span data-ttu-id="aeadb-132">Supposons à présent que vous renommez l’instance en « TAB2 ».</span><span class="sxs-lookup"><span data-stu-id="aeadb-132">Now suppose you rename the instance to "TAB2".</span></span> <span data-ttu-id="aeadb-133">Suite au changement de nom, la configuration se présente à présent comme suit :</span><span class="sxs-lookup"><span data-stu-id="aeadb-133">As a result of the name change, your configuration would now look like the following:</span></span>  
  
    1.  <span data-ttu-id="aeadb-134">Nom de l’instance = \<server> \TAB2</span><span class="sxs-lookup"><span data-stu-id="aeadb-134">Instance name = \<server>\TAB2</span></span>  
  
    2.  <span data-ttu-id="aeadb-135">Nom du service = MSOLAP$TAB2</span><span class="sxs-lookup"><span data-stu-id="aeadb-135">Service name = MSOLAP$TAB2</span></span>  
  
    3.  <span data-ttu-id="aeadb-136">Compte virtuel = NT Service\ MSOLAP$TAB2</span><span class="sxs-lookup"><span data-stu-id="aeadb-136">Virtual account = NT Service\ MSOLAP$TAB2</span></span>  
  
     <span data-ttu-id="aeadb-137">Comme vous pouvez le voir, les autorisations de base de données et de fichier précédemment accordées à « NT Service \ MSOLAP $ TABULAr » ne sont plus valides.</span><span class="sxs-lookup"><span data-stu-id="aeadb-137">As you can see, database and file permissions that were previously granted to "NT Service\ MSOLAP$TABULAR" are no longer valid.</span></span> <span data-ttu-id="aeadb-138">Pour vous assurer que les tâches et les opérations effectuées par le service s’exécutent comme avant, vous devez maintenant accorder aux nouvelles autorisations de base de données et de fichier la valeur « NT Service \ MSOLAP $ TAB2 ».</span><span class="sxs-lookup"><span data-stu-id="aeadb-138">To ensure that tasks and operations performed by the service run as before, you would now need to grant new database and file permissions to "NT Service\ MSOLAP$TAB2".</span></span>  
  
  
