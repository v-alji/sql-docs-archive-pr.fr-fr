---
title: Créer un rapport lié | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- linked reports [Reporting Services], creating
ms.assetid: 12be8341-cb57-45e8-a421-2bf66b50234d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ed5e70c9ff8179ae05186685e21303693fc9aed7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611523"
---
# <a name="create-a-linked-report"></a><span data-ttu-id="cad2b-102">Créer un rapport lié</span><span class="sxs-lookup"><span data-stu-id="cad2b-102">Create a Linked Report</span></span>
  <span data-ttu-id="cad2b-103">Un rapport lié est un élément de serveur de rapports qui fournit un point d'accès à un rapport existant.</span><span class="sxs-lookup"><span data-stu-id="cad2b-103">A linked report is a report server item that provides an access point to an existing report.</span></span> <span data-ttu-id="cad2b-104">Au niveau conceptuel, il est assimilable au raccourci d'un programme que vous utilisez pour exécuter une application ou ouvrir un fichier.</span><span class="sxs-lookup"><span data-stu-id="cad2b-104">Conceptually, it is similar to a program shortcut that you use to run a program or open a file.</span></span>

 <span data-ttu-id="cad2b-105">Un rapport lié est issu d'un rapport existant et il reste fidèle à la définition de rapport d'origine.</span><span class="sxs-lookup"><span data-stu-id="cad2b-105">A linked report is derived from an existing report and retains the original's report definition.</span></span> <span data-ttu-id="cad2b-106">Il hérite toujours des propriétés de la source de données et de la mise en page du rapport d'origine.</span><span class="sxs-lookup"><span data-stu-id="cad2b-106">A linked report always inherits report layout and data source properties of the original report.</span></span> <span data-ttu-id="cad2b-107">Toutes les autres propriétés et toutes les autres valeurs peuvent différer, notamment la sécurité, les paramètres, l'emplacement, les abonnements et les planifications.</span><span class="sxs-lookup"><span data-stu-id="cad2b-107">All other properties and settings can be different from those of the original report, including security, parameters, location, subscriptions, and schedules.</span></span>

 <span data-ttu-id="cad2b-108">Vous créez un rapport lié lorsque vous voulez créer des versions supplémentaires d'un rapport existant.</span><span class="sxs-lookup"><span data-stu-id="cad2b-108">You can create a linked report when you want to create additional versions of an existing report.</span></span> <span data-ttu-id="cad2b-109">Ainsi, vous pouvez trouver pratique d'utiliser un rapport de ventes régional unique pour créer des rapports spécifiques aux régions pour tous vos secteurs de ventes.</span><span class="sxs-lookup"><span data-stu-id="cad2b-109">For example, you could use a single regional sales report to create region-specific reports for all of your sales territories.</span></span>

 <span data-ttu-id="cad2b-110">Bien que les rapports liés soient généralement basés sur des rapports paramétrés, il n'est pas obligatoire de recourir à des rapports paramétrés.</span><span class="sxs-lookup"><span data-stu-id="cad2b-110">Although linked reports are typically based on parameterized reports, a parameterized report is not required.</span></span> <span data-ttu-id="cad2b-111">Vous pouvez créer des rapports liés dès lors que vous souhaitez déployer un rapport existant avec des paramètres différents.</span><span class="sxs-lookup"><span data-stu-id="cad2b-111">You can create linked reports whenever you want to deploy an existing report with different settings.</span></span>

### <a name="to-create-a-linked-report"></a><span data-ttu-id="cad2b-112">Pour créer un rapport lié</span><span class="sxs-lookup"><span data-stu-id="cad2b-112">To create a linked report</span></span>

1.  <span data-ttu-id="cad2b-113">Dans le Gestionnaire de rapports, accédez au dossier qui contient le rapport à lier, puis ouvrez le menu d’options et cliquez sur **Créer un rapport lié**.</span><span class="sxs-lookup"><span data-stu-id="cad2b-113">In Report Manager, navigate to the folder containing the report that you want to link to, and then open the options menu can click **Create Linked Report**.</span></span>

2.  <span data-ttu-id="cad2b-114">Indiquez un nom pour le nouveau rapport lié.</span><span class="sxs-lookup"><span data-stu-id="cad2b-114">Type a name for the new linked report.</span></span> <span data-ttu-id="cad2b-115">Tapez éventuellement une description.</span><span class="sxs-lookup"><span data-stu-id="cad2b-115">Optionally type a description.</span></span>

3.  <span data-ttu-id="cad2b-116">Pour sélectionner un autre dossier pour le rapport, cliquez sur **Modifier l’emplacement**.</span><span class="sxs-lookup"><span data-stu-id="cad2b-116">To select a different folder for the report, click **Change Location**.</span></span> <span data-ttu-id="cad2b-117">Cliquez ensuite sur le dossier à utiliser ou tapez son nom dans la zone **Emplacement** .</span><span class="sxs-lookup"><span data-stu-id="cad2b-117">Click the folder you want to use, or type the folder name in the **Location** box.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)] <span data-ttu-id="cad2b-118">Si vous ne sélectionnez aucun dossier, le rapport lié est créé dans le dossier actif (où est stocké le rapport sur lequel il est basé).</span><span class="sxs-lookup"><span data-stu-id="cad2b-118">If you do not select a different folder, the linked report is created in the current folder (where the report it is based on is stored).</span></span>

4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)] <span data-ttu-id="cad2b-119">Le rapport lié s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="cad2b-119">The linked report opens.</span></span>

     <span data-ttu-id="cad2b-120">L'icône d'un rapport lié est différente des autres éléments gérés par un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="cad2b-120">A linked report's icon differs from other items managed by a report server.</span></span> <span data-ttu-id="cad2b-121">L'icône ci-après indique un rapport lié :</span><span class="sxs-lookup"><span data-stu-id="cad2b-121">The following icon indicates a linked report:</span></span>

     <span data-ttu-id="cad2b-122">![Icône Rapport lié](../media/hlp-16linked.gif "Icône Rapport lié")</span><span class="sxs-lookup"><span data-stu-id="cad2b-122">![Linked report icon](../media/hlp-16linked.gif "Linked report icon")</span></span>

## <a name="see-also"></a><span data-ttu-id="cad2b-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cad2b-123">See Also</span></span>
 <span data-ttu-id="cad2b-124">[Ouvrez et fermez une &#40;de rapport Gestionnaire de rapports&#41;](../reports/open-and-close-a-report-report-manager.md) page [nouveau rapport lié &#40;gestionnaire de rapports](../new-linked-report-page-report-manager.md) [&#41;&#40;](../choose-item-location-page-report-manager.md) gestionnaire de rapports&#41;[SSRS](../reporting-services-concepts-ssrs.md) &#40;gestionnaire de rapports&#41;SSRS [en mode natif](../report-manager-ssrs-native-mode.md) Reporting Services de &#40;&#41;[de](../general-properties-page-reports-report-manager.md) gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="cad2b-124">[Open and Close a Report &#40;Report Manager&#41;](../reports/open-and-close-a-report-report-manager.md) [New Linked Report Page &#40;Report Manager&#41;](../new-linked-report-page-report-manager.md) [Choose Item Location Page &#40;Report Manager&#41;](../choose-item-location-page-report-manager.md) [General Properties Page, Reports &#40;Report Manager&#41;](../general-properties-page-reports-report-manager.md) [Reporting Services Concepts &#40;SSRS&#41;](../reporting-services-concepts-ssrs.md) [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md)</span></span>


