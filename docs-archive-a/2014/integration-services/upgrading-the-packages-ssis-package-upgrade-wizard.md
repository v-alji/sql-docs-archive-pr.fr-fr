---
title: Mise à niveau des packages (Assistant Mise à niveau de packages SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.is.upgradewizard.upgradingpackage.f1
ms.assetid: cdb842e3-2e59-4ede-b127-be4fde46875c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d13228dabc1566b592733da4afd8ebde3671ee0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602189"
---
# <a name="upgrading-the-packages-ssis-package-upgrade-wizard"></a><span data-ttu-id="a184c-102">Mise à niveau des packages (Assistant Mise à niveau de packages SSIS)</span><span class="sxs-lookup"><span data-stu-id="a184c-102">Upgrading the Packages (SSIS Package Upgrade Wizard)</span></span>
  <span data-ttu-id="a184c-103">Utilisez la page **Mise à niveau des packages** pour afficher la progression de la mise à niveau de packages et pour interrompre le processus de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="a184c-103">Use the **Upgrading the Packages** page to view the progress of package upgrade and to interrupt the upgrade process.</span></span> <span data-ttu-id="a184c-104">L'Assistant Mise à niveau de packages [!INCLUDE[ssIS](../includes/ssis-md.md)] met à niveau, un par un, les packages sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="a184c-104">The [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard upgrades the selected packages one by one.</span></span>  
  
 <span data-ttu-id="a184c-105">**Pour afficher les packages mis à niveau qui ont été enregistrés dans une base de données SQL Server ou dans le magasin de packages**</span><span class="sxs-lookup"><span data-stu-id="a184c-105">**To view upgraded packages that were saved to a SQL Server database or to the package store**</span></span>  
  
-   <span data-ttu-id="a184c-106">Dans l'Explorateur d'objets de [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], connectez-vous à l'instance locale d' [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], puis développez le nœud **Packages stockés** pour voir les packages mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="a184c-106">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], in Object Explorer, connect to the local instance of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], and then expand the **Stored Packages** node to see the packages that were upgraded.</span></span>  
  
 <span data-ttu-id="a184c-107">**Pour afficher les packages mis à niveau à partir des outils de données SQL Server**</span><span class="sxs-lookup"><span data-stu-id="a184c-107">**To view upgraded packages that were upgraded from SQL Server Data Tools**</span></span>  
  
-   <span data-ttu-id="a184c-108">Dans l'Explorateur de solutions de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , puis développez le nœud **Packages SSIS** pour voir les packages mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="a184c-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in Solution Explorer, open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, and then expand the **SSIS Packages** node to see the upgraded packages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a184c-109">Options</span><span class="sxs-lookup"><span data-stu-id="a184c-109">Options</span></span>  
 <span data-ttu-id="a184c-110">**Volet de message**</span><span class="sxs-lookup"><span data-stu-id="a184c-110">**Message pane**</span></span>  
 <span data-ttu-id="a184c-111">Affiche des messages de progression et des informations de résumé pendant le processus de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="a184c-111">Displays progress messages and summary information during the upgrade process.</span></span>  
  
 <span data-ttu-id="a184c-112">**Action**</span><span class="sxs-lookup"><span data-stu-id="a184c-112">**Action**</span></span>  
 <span data-ttu-id="a184c-113">Permet d'afficher les actions de la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="a184c-113">View the actions in the upgrade.</span></span>  
  
 <span data-ttu-id="a184c-114">**État**</span><span class="sxs-lookup"><span data-stu-id="a184c-114">**Status**</span></span>  
 <span data-ttu-id="a184c-115">Permet d'afficher le résultat de chaque action.</span><span class="sxs-lookup"><span data-stu-id="a184c-115">View the result of each action.</span></span>  
  
 <span data-ttu-id="a184c-116">**Message**</span><span class="sxs-lookup"><span data-stu-id="a184c-116">**Message**</span></span>  
 <span data-ttu-id="a184c-117">Permet d'afficher les messages d'erreur générés par chaque action.</span><span class="sxs-lookup"><span data-stu-id="a184c-117">View the error messages that each action generates.</span></span>  
  
 <span data-ttu-id="a184c-118">**Stop**</span><span class="sxs-lookup"><span data-stu-id="a184c-118">**Stop**</span></span>  
 <span data-ttu-id="a184c-119">Permet d'arrêter la mise à niveau de packages.</span><span class="sxs-lookup"><span data-stu-id="a184c-119">Stop the package upgrade.</span></span>  
  
 <span data-ttu-id="a184c-120">**Report**</span><span class="sxs-lookup"><span data-stu-id="a184c-120">**Report**</span></span>  
 <span data-ttu-id="a184c-121">Sélectionnez ce que vous voulez faire avec le rapport qui contient les résultats de la mise à niveau de packages :</span><span class="sxs-lookup"><span data-stu-id="a184c-121">Select what you want to do with the report that contains the results of the package upgrade:</span></span>  
  
-   <span data-ttu-id="a184c-122">Afficher le rapport en ligne.</span><span class="sxs-lookup"><span data-stu-id="a184c-122">View the report online.</span></span>  
  
-   <span data-ttu-id="a184c-123">Enregistrer le rapport dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="a184c-123">Save the report to a file.</span></span>  
  
-   <span data-ttu-id="a184c-124">Copier le rapport dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="a184c-124">Copy the report to the Clipboard</span></span>  
  
-   <span data-ttu-id="a184c-125">Envoyer le rapport sous forme de message électronique.</span><span class="sxs-lookup"><span data-stu-id="a184c-125">Send the report as an e-mail message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a184c-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a184c-126">See Also</span></span>  
 [<span data-ttu-id="a184c-127">Mettre à niveau des packages Integration Services</span><span class="sxs-lookup"><span data-stu-id="a184c-127">Upgrade Integration Services Packages</span></span>](install-windows/upgrade-integration-services-packages.md)  
  
  
