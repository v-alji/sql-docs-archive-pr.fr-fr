---
title: Importer des rapports à partir de Microsoft Access (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Access reports [Reporting Services]
- importing reports
ms.assetid: 4f29d5b8-b77d-4714-a84a-05523df55646
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 862d8b90f3c91dffda35971677db7fdc231c1b63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612707"
---
# <a name="import-reports-from-microsoft-access-reporting-services"></a><span data-ttu-id="4257c-102">Importer des rapports depuis Microsoft Access (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="4257c-102">Import Reports from Microsoft Access (Reporting Services)</span></span>
  <span data-ttu-id="4257c-103">Dans Concepteur de rapports, vous pouvez importer des rapports à partir d’une [!INCLUDE[msCoName](../includes/msconame-md.md)] base de données ou d’un projet Access.</span><span class="sxs-lookup"><span data-stu-id="4257c-103">In Report Designer, you can import reports from a [!INCLUDE[msCoName](../includes/msconame-md.md)] Access database or project.</span></span> <span data-ttu-id="4257c-104">Microsoft Access 2002 (ou version ultérieure) doit être installé sur le même ordinateur que le Concepteur de rapports.</span><span class="sxs-lookup"><span data-stu-id="4257c-104">Access 2002 or a later version must be installed on the same computer on which Report Designer is installed.</span></span>  
  
 <span data-ttu-id="4257c-105">Lorsque vous utilisez la fonctionnalité d'importation, tous les états contenus dans le fichier de base de données ou de projet sont importés.</span><span class="sxs-lookup"><span data-stu-id="4257c-105">When you use the import feature, all reports in the database or project file are imported.</span></span> <span data-ttu-id="4257c-106">Si votre fichier Access contient plusieurs états, vous pouvez créer un projet de rapport séparé dans lequel importer les états, puis ouvrir les fichiers RDL individuels dans votre projet de rapport principal.</span><span class="sxs-lookup"><span data-stu-id="4257c-106">If your Access file contains many reports, you may want to create a separate report project into which to import the reports, and then open the individual RDL files in your main report project.</span></span> <span data-ttu-id="4257c-107">Vous pouvez modifier les états après les avoir importés dans le Concepteur de rapports.</span><span class="sxs-lookup"><span data-stu-id="4257c-107">You can edit the reports after they are imported into Report Designer.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="4257c-108">ne prend pas en charge tous les objets de rapport Access.</span><span class="sxs-lookup"><span data-stu-id="4257c-108">does not support all Access report objects.</span></span> <span data-ttu-id="4257c-109">Les éléments qui ne sont pas convertis sont affichés dans la fenêtre **liste des tâches** .</span><span class="sxs-lookup"><span data-stu-id="4257c-109">Items that are not converted are displayed in the **Task List** window.</span></span> <span data-ttu-id="4257c-110">Pour plus d’informations, consultez [fonctionnalités de rapport d’accès prises en charge &#40;&#41;SSRS ](../../2014/reporting-services/supported-access-report-features-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4257c-110">For more information, see [Supported Access Report Features &#40;SSRS&#41;](../../2014/reporting-services/supported-access-report-features-ssrs.md).</span></span>  
  
### <a name="to-import-reports-from-microsoft-access"></a><span data-ttu-id="4257c-111">Pour importer des rapports à partir de Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="4257c-111">To import reports from Microsoft Access</span></span>  
  
1.  <span data-ttu-id="4257c-112">Ouvrez ou créez un projet dans lequel importer les rapports.</span><span class="sxs-lookup"><span data-stu-id="4257c-112">Open or create a project into which to import the reports.</span></span>  
  
2.  <span data-ttu-id="4257c-113">Dans le menu **projet** , pointez sur **importer des rapports**, puis cliquez sur **Microsoft Access**.</span><span class="sxs-lookup"><span data-stu-id="4257c-113">On the **Project** menu, point to **Import Reports**, and then click **Microsoft Access**.</span></span> <span data-ttu-id="4257c-114">Vous pouvez également cliquer avec le bouton droit sur le projet dans Explorateur de solutions, pointer sur **importer des rapports**, puis cliquer sur **Microsoft Access**.</span><span class="sxs-lookup"><span data-stu-id="4257c-114">Alternatively, right-click the project in Solution Explorer, point to **Import Reports**, and then click **Microsoft Access**.</span></span>  
  
3.  <span data-ttu-id="4257c-115">Dans la boîte de dialogue **ouvrir** , sélectionnez la base de données Access (. mdb,. accdb) ou le projet (. ADP) qui contient les rapports, puis cliquez sur **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="4257c-115">In the **Open** dialog box, select the Access database (.mdb, .accdb) or project (.adp) that contains the reports, and then click **Open**.</span></span> <span data-ttu-id="4257c-116">Tous les rapports contenus dans le fichier de base de données ou de projet sont importés et répertoriés dans le dossier Rapports de l'Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="4257c-116">All the reports in the database or project file are imported and listed in the Reports folder in Solution Explorer.</span></span>  
  
4.  <span data-ttu-id="4257c-117">Recherchez les erreurs de génération dans la fenêtre **liste des tâches** .</span><span class="sxs-lookup"><span data-stu-id="4257c-117">Check the **Task List** window for build errors.</span></span> <span data-ttu-id="4257c-118">Pour afficher la fenêtre de **liste des tâches** , ouvrez le menu **affichage** , pointez sur **autres fenêtres**, puis cliquez sur **liste des tâches**.</span><span class="sxs-lookup"><span data-stu-id="4257c-118">To view the **Task List** window, open the **View** menu, point to **Other Windows**, and then click **Task List**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4257c-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4257c-119">See Also</span></span>  
 [<span data-ttu-id="4257c-120">Concevoir des rapports à l’aide du Concepteur de rapports &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="4257c-120">Design Reports with Report Designer &#40;SSRS&#41;</span></span>](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md)  
  
  
