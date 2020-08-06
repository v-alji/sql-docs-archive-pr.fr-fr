---
title: Désinstaller la version autonome de Générateur de rapports (Générateur de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 009538c6-4941-4393-b14b-9144cffdbdaf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cda13248d1aa14ee3d57a951872d3ad8ded17da9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612697"
---
# <a name="uninstall-the-stand-alone-version-of-report-builder-report-builder"></a><span data-ttu-id="d51a9-102">Désinstaller la version autonome du Générateur de rapports (Générateur de rapports)</span><span class="sxs-lookup"><span data-stu-id="d51a9-102">Uninstall the Stand-Alone Version of Report Builder (Report Builder)</span></span>
  <span data-ttu-id="d51a9-103">Vous pouvez désinstaller la version autonome du Générateur de rapports à partir du Panneau de configuration ou de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="d51a9-103">You can uninstall the stand-alone version of Report Builder from the control panel or the command line.</span></span> <span data-ttu-id="d51a9-104">Vous ne pouvez pas désinstaller la version [!INCLUDE[ndptecclick](../../includes/ndptecclick-md.md)] du Générateur de rapports sans désinstaller [!INCLUDE[ssRSCurrent](../../includes/ssrscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d51a9-104">You cannot uninstall the [!INCLUDE[ndptecclick](../../includes/ndptecclick-md.md)] version of Report Builder without uninstalling [!INCLUDE[ssRSCurrent](../../includes/ssrscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="d51a9-105">La désinstallation du Générateur de rapports à partir de la ligne de commande utilise une syntaxe identique à celle que vous utilisez pour installer le Générateur de rapports, à la différence près que vous utilisez l'option /x à la place de l'option /i.</span><span class="sxs-lookup"><span data-stu-id="d51a9-105">Uninstalling Report Builder from the command line uses syntax that is identical to the syntax you use to install Report Builder, except you use the /x option instead of the /i option.</span></span> <span data-ttu-id="d51a9-106">Les lignes de commande de désinstallation peuvent également inclure l'option /quiet et d'autres options standard.</span><span class="sxs-lookup"><span data-stu-id="d51a9-106">Command lines for uninstalling can also include the /quiet option and other standard options.</span></span> <span data-ttu-id="d51a9-107">Si le package Windows Installer du Générateur de rapports (ReportBuilder3_x86.msi) a été supprimé, la ligne de commande ne permet pas de désinstaller facilement le Générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="d51a9-107">If the Report Builder Windows Installer Package (ReportBuilder3_x86.msi) has been removed, you cannot use the command line easily to uninstall Report Builder.</span></span> <span data-ttu-id="d51a9-108">Pour en savoir plus sur la suppression du Générateur de rapports à l'aide de son GUID, consultez la documentation du programme msiexec dans MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="d51a9-108">To learn more about how you might be able to remove Report Builder by using its GUID, see the documentation for the msiexec program in the msdn library.</span></span>  
  
 <span data-ttu-id="d51a9-109">Si les dossiers utilisés par le Générateur de rapports incluent des fichiers personnalisés, les dossiers et fichiers sont conservés lors de la suppression du Générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="d51a9-109">If folders used by Report Builder include custom files, the folders and the files are preserved when Report Builder is removed.</span></span> <span data-ttu-id="d51a9-110">Seuls les fichiers du Générateur de rapports sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="d51a9-110">Only the Report Builder files are removed.</span></span>  
  
### <a name="to-uninstall-report-builder-from-the-control-panel"></a><span data-ttu-id="d51a9-111">Pour désinstaller le Générateur de rapports à partir du panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="d51a9-111">To uninstall Report Builder from the control panel</span></span>  
  
1.  <span data-ttu-id="d51a9-112">Dans le menu **Démarrer** , cliquez sur **Panneau de configuration**.</span><span class="sxs-lookup"><span data-stu-id="d51a9-112">On the **Start** menu, click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="d51a9-113">Dans le Panneau de configuration, cliquez sur **Programmes et fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="d51a9-113">In the Control Panel, click **Programs and Features**.</span></span>  
  
3.  <span data-ttu-id="d51a9-114">Recherchez Générateur de rapports  dans la liste Nom , puis cliquez dessus.</span><span class="sxs-lookup"><span data-stu-id="d51a9-114">Locate [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Report Builder in the **Name** list and click it.</span></span>  
  
4.  <span data-ttu-id="d51a9-115">Cliquez sur **Désinstaller**.</span><span class="sxs-lookup"><span data-stu-id="d51a9-115">Click **Uninstall**.</span></span>  
  
5.  <span data-ttu-id="d51a9-116">Si vous êtes invité à confirmer la désinstallation du Générateur de rapports, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="d51a9-116">If prompted to confirm the uninstall of Report Builder, click **Yes**.</span></span>  
  
### <a name="to-uninstall-report-builder-from-the-command-line"></a><span data-ttu-id="d51a9-117">Pour désinstaller le Générateur de rapports à partir de la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="d51a9-117">To uninstall Report Builder from the command line</span></span>  
  
1.  <span data-ttu-id="d51a9-118">Dans le menu **Démarrer** , cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="d51a9-118">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="d51a9-119">Dans la zone de texte **ouvrir** , tapez`cmd.`</span><span class="sxs-lookup"><span data-stu-id="d51a9-119">In the **Open** text box, type `cmd.`</span></span>  
  
3.  <span data-ttu-id="d51a9-120">Dans la fenêtre d'invite de commandes, naviguez jusqu'au dossier avec ReportBuilder3_x86.msi.</span><span class="sxs-lookup"><span data-stu-id="d51a9-120">In the command prompt window, navigate to the folder with ReportBuilder3_x86.msi.</span></span>  
  
4.  <span data-ttu-id="d51a9-121">Tapez une ligne de commande de base, par exemple :</span><span class="sxs-lookup"><span data-stu-id="d51a9-121">Type a basic command line such as the following:</span></span>  
  
 `msiexec /x ReportBuilder3_x86.msi /quiet /l*v install.log`  
  
 <span data-ttu-id="d51a9-122">Pour inclure l'enregistrement, utilisez une ligne de commande telle que :</span><span class="sxs-lookup"><span data-stu-id="d51a9-122">If you can to include logging, use a command line such as the following:</span></span>  
  
 `msiexec /x ReportBuilder3_x86.msi /quiet /l*v c:\junk\install.log`  
  
1.  <span data-ttu-id="d51a9-123">Appuyez sur **Entrée**.</span><span class="sxs-lookup"><span data-stu-id="d51a9-123">Press **Enter**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d51a9-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d51a9-124">See Also</span></span>  
 <span data-ttu-id="d51a9-125">[Installer, désinstaller et Générateur de rapports la prise en charge](../install-uninstall-and-report-builder-support.md) </span><span class="sxs-lookup"><span data-stu-id="d51a9-125">[Install, Uninstall, and Report Builder Support](../install-uninstall-and-report-builder-support.md) </span></span>  
 [<span data-ttu-id="d51a9-126">Installer la version autonome de Générateur de rapports &#40;Générateur de rapports&#41;</span><span class="sxs-lookup"><span data-stu-id="d51a9-126">Install the Stand-Alone Version of Report Builder &#40;Report Builder&#41;</span></span>](install-report-builder.md)  
  
  
