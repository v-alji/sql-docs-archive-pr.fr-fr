---
title: 'Procédure : Déboguer des assemblys personnalisés | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom assemblies [Reporting Services], debugging
- debugging custom assemblies [Reporting Services]
- troubleshooting [Reporting Services], custom assemblies
ms.assetid: 3a3215b3-548c-4474-81ba-3a98dd3912bf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1b5f9f5a4595d59cce98da4f753422cd07529926
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702496"
---
# <a name="how-to-debug-custom-assemblies"></a><span data-ttu-id="46dc6-102">Procédure : Déboguer des assemblages personnalisés</span><span class="sxs-lookup"><span data-stu-id="46dc6-102">How to: Debug Custom Assemblies</span></span>
  <span data-ttu-id="46dc6-103">Le [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] fournit plusieurs outils de débogage qui peuvent vous aider à analyser votre code d’assembly personnalisé et à localiser les erreurs qu’il contient.</span><span class="sxs-lookup"><span data-stu-id="46dc6-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provides several debugging tools that can help you analyze your custom assembly code and locate errors in it.</span></span> <span data-ttu-id="46dc6-104">Vous devez choisir un outil en fonction de ce que vous essayez d'accomplir.</span><span class="sxs-lookup"><span data-stu-id="46dc6-104">The best tool to use will depend on what you are trying to accomplish.</span></span> <span data-ttu-id="46dc6-105">Cet exemple utilise [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46dc6-105">This example uses [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)].</span></span>  
  
 <span data-ttu-id="46dc6-106">La méthode recommandée pour concevoir, développer et tester des assemblys personnalisés pour [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] consiste à créer une solution contenant à la fois vos rapports de test et votre assembly personnalisé.</span><span class="sxs-lookup"><span data-stu-id="46dc6-106">The recommended way to design, develop, and test custom assemblies for [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is to create a solution that contains both your test reports and your custom assembly.</span></span>  
  
### <a name="to-debug-assemblies-using-a-single-instance-of-visual-studio"></a><span data-ttu-id="46dc6-107">Pour déboguer des assemblys à l'aide d'une instance unique de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="46dc6-107">To debug assemblies using a single instance of Visual Studio</span></span>  
  
1.  <span data-ttu-id="46dc6-108">Créez un projet de rapport à l'aide de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46dc6-108">Create a new report project using [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span>  
  
     <span data-ttu-id="46dc6-109">En même temps que vous créez un projet de rapport, [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] crée une solution destinée à le contenir.</span><span class="sxs-lookup"><span data-stu-id="46dc6-109">At the time you create a report project, [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] also creates a solution to contain it.</span></span>  
  
2.  <span data-ttu-id="46dc6-110">Ajoutez un nouveau projet Bibliothèque de classes à la solution existante.</span><span class="sxs-lookup"><span data-stu-id="46dc6-110">Add a new Class Library project to the existing solution.</span></span> <span data-ttu-id="46dc6-111">Assurez-vous que le projet de rapport est défini comme projet de démarrage.</span><span class="sxs-lookup"><span data-stu-id="46dc6-111">Make sure that the report project is set as the startup project.</span></span> <span data-ttu-id="46dc6-112">Pour plus d'informations sur la procédure à suivre, consultez la documentation de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46dc6-112">For more information about how to accomplish this, see your [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] documentation.</span></span>  
  
3.  <span data-ttu-id="46dc6-113">Dans l'Explorateur de solutions, sélectionnez la solution de votre choix.</span><span class="sxs-lookup"><span data-stu-id="46dc6-113">In Solution Explorer, select the solution.</span></span>  
  
4.  <span data-ttu-id="46dc6-114">Dans le menu **Affichage**, cliquez sur **Pages de propriétés**.</span><span class="sxs-lookup"><span data-stu-id="46dc6-114">On the **View** menu, click **Property Pages**.</span></span>  
  
     <span data-ttu-id="46dc6-115">La boîte de dialogue **Pages de propriétés de Solution** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="46dc6-115">The **Solution Property Pages** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="46dc6-116">Dans le volet gauche, développez **Propriétés communes** si nécessaire, et cliquez sur **Dépendances du projet**.</span><span class="sxs-lookup"><span data-stu-id="46dc6-116">In the left pane, expand **Common Properties** if necessary, and click **Project Dependencies**.</span></span> <span data-ttu-id="46dc6-117">Sélectionnez le projet de rapport dans la liste déroulante **Projet**.</span><span class="sxs-lookup"><span data-stu-id="46dc6-117">Select the report project from the **Project** drop-down list.</span></span> <span data-ttu-id="46dc6-118">Sélectionnez votre projet d’assembly dans la liste **Dépend de**.</span><span class="sxs-lookup"><span data-stu-id="46dc6-118">Select your assembly project in the **Depends On** list.</span></span>  
  
6.  <span data-ttu-id="46dc6-119">Cliquez sur **OK** pour enregistrer les modifications et fermez le dialogue **Pages de propriétés**.</span><span class="sxs-lookup"><span data-stu-id="46dc6-119">Click **OK** to save the changes, and close the **Property Pages** dialog.</span></span>  
  
7.  <span data-ttu-id="46dc6-120">Dans l'Explorateur de solutions, sélectionnez votre projet d'assembly personnalisé.</span><span class="sxs-lookup"><span data-stu-id="46dc6-120">In Solution Explorer, select your custom assembly project.</span></span>  
  
8.  <span data-ttu-id="46dc6-121">Dans le menu **Affichage**, cliquez sur **Pages de propriétés**.</span><span class="sxs-lookup"><span data-stu-id="46dc6-121">On the **View** menu, click **Property Pages**.</span></span>  
  
     <span data-ttu-id="46dc6-122">La boîte de dialogue **Pages de propriétés de Projet** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="46dc6-122">The **Project Property Pages** dialog box opens.</span></span>  
  
9. <span data-ttu-id="46dc6-123">Cliquez sur l’onglet **Générer** si vous travaillez sur un projet C# ou sur l’onglet **Compiler** s’il s’agit d’un projet [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46dc6-123">Click the **Build** tab if you're in a C# project or the **Compile** tab if you're in a [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] project.</span></span>  
  
10. <span data-ttu-id="46dc6-124">Dans la page **générer**la / **compilation** , entrez le chemin d’accès au dossier concepteur de rapports.</span><span class="sxs-lookup"><span data-stu-id="46dc6-124">On the **Build**/**Compile** page, enter the path to the Report Designer folder.</span></span> <span data-ttu-id="46dc6-125">Par défaut, il s’agit de C:\Program Files\Microsoft SQL Server\100\Tools\Binn\VSShell\Common7\IDE dans la zone de texte **Chemin de sortie**.</span><span class="sxs-lookup"><span data-stu-id="46dc6-125">By default, this is C:\Program Files\Microsoft SQL Server\100\Tools\Binn\VSShell\Common7\IDE) in the **Output Path** text box.</span></span> <span data-ttu-id="46dc6-126">Une version mise à jour de votre assembly personnalisé est alors générée et déployée directement dans le Concepteur de rapports avant exécution de votre rapport.</span><span class="sxs-lookup"><span data-stu-id="46dc6-126">This builds and deploys an updated version of your custom assembly directly to Report Designer before your report is executed.</span></span>  
  
11. <span data-ttu-id="46dc6-127">Une fois votre rapport généré et votre assembly personnalisé développé, définissez des points d'arrêt dans le code de votre assembly personnalisé.</span><span class="sxs-lookup"><span data-stu-id="46dc6-127">Once you have designed your report and developed your custom assembly, set breakpoints in your custom assembly code.</span></span>  
  
12. <span data-ttu-id="46dc6-128">Exécutez le rapport en mode **DebugLocal** en appuyant sur la touche F5.</span><span class="sxs-lookup"><span data-stu-id="46dc6-128">Run the report under **DebugLocal** mode by pressing the F5 key.</span></span> <span data-ttu-id="46dc6-129">Lorsque le rapport s'exécute dans la fenêtre d'aperçu contextuelle, le débogueur atteint chacun des points d'arrêt correspondant au code exécutable de votre assembly.</span><span class="sxs-lookup"><span data-stu-id="46dc6-129">When the report executes in the pop-up preview window, the debugger hits any breakpoints that correspond to executable code in your assembly.</span></span> <span data-ttu-id="46dc6-130">Utilisez la touche F11 pour exécuter le code de votre assembly personnalisé en pas à pas.</span><span class="sxs-lookup"><span data-stu-id="46dc6-130">Use F11 to step through your custom assembly code.</span></span>  
  
### <a name="to-debug-assemblies-using-two-instances-of-visual-studio"></a><span data-ttu-id="46dc6-131">Pour déboguer des assemblys à l'aide de deux instances de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="46dc6-131">To debug assemblies using two instances of Visual Studio</span></span>  
  
1.  <span data-ttu-id="46dc6-132">Démarrez [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] et ouvrez votre projet d'assembly personnalisé.</span><span class="sxs-lookup"><span data-stu-id="46dc6-132">Start [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] and open your custom assembly project.</span></span>  
  
2.  <span data-ttu-id="46dc6-133">Générez le projet et déployez votre assembly personnalisé de même que le fichier .pdb associé dans le Concepteur de rapports.</span><span class="sxs-lookup"><span data-stu-id="46dc6-133">Build the project, and deploy your custom assembly and the accompanying .pdb file to the Report Designer.</span></span> <span data-ttu-id="46dc6-134">Pour plus d’informations sur le déploiement, consultez [Déploiement d’un assembly personnalisé](deploying-a-custom-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="46dc6-134">For more information about deployment, see [Deploying a Custom Assembly](deploying-a-custom-assembly.md).</span></span>  
  
3.  <span data-ttu-id="46dc6-135">Ouvrez un projet de rapport utilisant votre assembly personnalisé en laissant votre code d'assembly personnalisé ouvert dans une instance distincte de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46dc6-135">Open up a report project that uses your custom assembly while leaving your custom assembly code open in a separate instance of [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span>  
  
4.  <span data-ttu-id="46dc6-136">Naviguez vers l'instance de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] qui contient votre projet d'assembly personnalisé et définissez des points d'arrêt dans votre code.</span><span class="sxs-lookup"><span data-stu-id="46dc6-136">Navigate to the instance of [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] that contains your custom assembly project and set some break points in your code.</span></span>  
  
5.  <span data-ttu-id="46dc6-137">Alors que le projet d’assembly personnalisé se trouve toujours dans la fenêtre active, cliquez sur **Attacher au processus** dans le menu **Déboguer**.</span><span class="sxs-lookup"><span data-stu-id="46dc6-137">With the custom assembly project still the active window, click **Attach to Process** on the **Debug** menu.</span></span>  
  
     <span data-ttu-id="46dc6-138">La boîte de dialogue **Attacher au processus** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="46dc6-138">The **Attach to Process** dialog opens.</span></span>  
  
6.  <span data-ttu-id="46dc6-139">Dans la liste des processus, sélectionnez le processus devenv.exe qui correspond à votre projet de rapport, puis cliquez sur **Attacher**.</span><span class="sxs-lookup"><span data-stu-id="46dc6-139">From the list of processes, select the devenv.exe process that corresponds to your Report Project and click **Attach**.</span></span>  
  
7.  <span data-ttu-id="46dc6-140">Définissez les expressions qui vous utiliserez dans votre rapport à partir de votre assembly personnalisé et concevez votre rapport.</span><span class="sxs-lookup"><span data-stu-id="46dc6-140">Define the expressions that you will use in your report from your custom assembly and design your report.</span></span>  
  
8.  <span data-ttu-id="46dc6-141">Une fois la conception de votre rapport terminée, cliquez sur l’onglet **Aperçu**.</span><span class="sxs-lookup"><span data-stu-id="46dc6-141">When you are finished designing your report, click the **Preview** tab.</span></span>  
  
     <span data-ttu-id="46dc6-142">Le rapport s'exécute et le code de l'assembly personnalisé doit s'arrêter aux points d'arrêt prédéfinis.</span><span class="sxs-lookup"><span data-stu-id="46dc6-142">The report executes, and the custom assembly code should break at your predefined break points.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="46dc6-143">L’utilisation de l’onglet **Aperçu** ne permet pas d’appliquer les autorisations de code de l’assembly.</span><span class="sxs-lookup"><span data-stu-id="46dc6-143">Using the **Preview** tab does not enforce code permissions for the assembly.</span></span> <span data-ttu-id="46dc6-144">Pour effectuer un test complet, qui inclut toutes les erreurs de sécurité d’accès du code, lancez le projet de rapport avec le paramètre de configuration **DebugLocal**.</span><span class="sxs-lookup"><span data-stu-id="46dc6-144">For a complete test, which includes any code access security errors, start the report project under the **DebugLocal** configuration setting.</span></span>  
  
9. <span data-ttu-id="46dc6-145">Exécutez le code pas à pas à l'aide de la touche F11.</span><span class="sxs-lookup"><span data-stu-id="46dc6-145">Step through your code using the F11 key.</span></span> <span data-ttu-id="46dc6-146">Pour plus d'informations sur le débogage à l'aide de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], consultez la documentation de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46dc6-146">For more information about debugging using [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], see the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46dc6-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="46dc6-147">See Also</span></span>  
 [<span data-ttu-id="46dc6-148">Utilisation d'assemblys personnalisés avec des rapports</span><span class="sxs-lookup"><span data-stu-id="46dc6-148">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
