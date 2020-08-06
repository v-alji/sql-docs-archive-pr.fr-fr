---
title: Annuler la suppression des avertissements d’exécution de rapports personnalisés | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], custom reports
ms.assetid: 0deed900-c910-4d12-aac0-6ab9e39eb068
author: stevestein
ms.author: sstein
ms.openlocfilehash: 725362ff7f8a6c282529f652e8813a8083257eb8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695216"
---
# <a name="unsuppress-run-custom-report-warnings"></a><span data-ttu-id="16b65-102">Annuler la suppression des avertissements d'exécution de rapports personnalisés</span><span class="sxs-lookup"><span data-stu-id="16b65-102">Unsuppress Run Custom Report Warnings</span></span>
  <span data-ttu-id="16b65-103">Il existe deux boîtes de dialogue d'avertissement pour les rapports personnalisés.</span><span class="sxs-lookup"><span data-stu-id="16b65-103">There are two warning dialog boxes for custom reports.</span></span> <span data-ttu-id="16b65-104">Cette rubrique décrit comment annuler la suppression de l'affichage de ces zones dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16b65-104">This topic describes how to unsuppress the display of these boxes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="16b65-105">Par défaut, la boîte de dialogue **Exécuter le rapport personnalisé** apparaît avant l’exécution d’un rapport personnalisé.</span><span class="sxs-lookup"><span data-stu-id="16b65-105">By default, the **Run Custom Reports** dialog box appears before a custom report runs.</span></span> <span data-ttu-id="16b65-106">Elle n’apparaît plus si vous cochez la case **Ne plus afficher ce message** .</span><span class="sxs-lookup"><span data-stu-id="16b65-106">If you select the **Please don't show this warning again** check box, the dialog box will no longer appear.</span></span> <span data-ttu-id="16b65-107">De même, toujours par défaut, la boîte de dialogue **Exécuter le rapport personnalisé** s’affiche quand vous ouvrez un rapport personnalisé, puis cliquez sur un lien pour en ouvrir un autre.</span><span class="sxs-lookup"><span data-stu-id="16b65-107">Also by default, the **Run Custom Reports** dialog box appears when you open a custom report and then click a link to open another custom report.</span></span> <span data-ttu-id="16b65-108">Cette boîte de dialogue affiche le chemin du fichier de rapport d'extraction personnalisé.</span><span class="sxs-lookup"><span data-stu-id="16b65-108">This dialog box displays the fill path to the drill-through custom report file.</span></span> <span data-ttu-id="16b65-109">Elle n’apparaît plus si vous cochez la case **Ne plus afficher ce message** .</span><span class="sxs-lookup"><span data-stu-id="16b65-109">If you select the **Please don't show this warning again** check box, the dialog box will no longer appear.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="16b65-110">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="16b65-110">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-unsuppress-the-main-custom-report-warning-dialog-box"></a><span data-ttu-id="16b65-111">Pour annuler la suppression de la boîte de dialogue d'avertissement principale des rapports personnalisés</span><span class="sxs-lookup"><span data-stu-id="16b65-111">To unsuppress the main custom report warning dialog box</span></span>  
  
1.  <span data-ttu-id="16b65-112">Connectez-vous au \<*Server*> \\ < *partage* >| \<*Drive*> \Documents and Settings \\<UserProfile \> \Application Data\Microsoft\Microsoft SQL Server\120\Tools\Shell\reports.xml.</span><span class="sxs-lookup"><span data-stu-id="16b65-112">Connect to \<*Server*>\\<*Share*>|\<*Drive*>\Documents and Settings\\<UserProfile\>\Application Data\Microsoft\Microsoft SQL Server\120\Tools\Shell\reports.xml.</span></span>  
  
2.  <span data-ttu-id="16b65-113">Cliquez avec le bouton droit sur `reports.xml` , puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="16b65-113">Right-click `reports.xml`, and then click **Edit**.</span></span>  
  
3.  <span data-ttu-id="16b65-114">Remplacez\*\* \<SuppressWarning> true \</SuppressWarning> par \<SuppressWarning> false \</SuppressWarning> \*\*.</span><span class="sxs-lookup"><span data-stu-id="16b65-114">Change**\<SuppressWarning>true\</SuppressWarning> to \<SuppressWarning>false\</SuppressWarning>**.</span></span>  
  
4.  <span data-ttu-id="16b65-115">Redémarrez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16b65-115">Restart [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-unsuppress-the-drill-through-custom-report-warning-dialog-box"></a><span data-ttu-id="16b65-116">Pour annuler la suppression de la boîte de dialogue d'avertissement principale des rapports d'extraction personnalisés</span><span class="sxs-lookup"><span data-stu-id="16b65-116">To unsuppress the drill-through custom report warning dialog box</span></span>  
  
1.  <span data-ttu-id="16b65-117">Connectez-vous au \<*Server*> \\ < *partage* >| \<*Drive*> \Documents and Settings \\<UserProfile \> \Application Data\Microsoft\Microsoft SQL Server\120\Tools\Shell\reports.xml.</span><span class="sxs-lookup"><span data-stu-id="16b65-117">Connect to \<*Server*>\\<*Share*>|\<*Drive*>\Documents and Settings\\<UserProfile\>\Application Data\Microsoft\Microsoft SQL Server\120\Tools\Shell\reports.xml.</span></span>  
  
2.  <span data-ttu-id="16b65-118">Cliquez avec le bouton droit sur `reports.xml` , puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="16b65-118">Right-click `reports.xml`, and click **Edit**.</span></span>  
  
3.  <span data-ttu-id="16b65-119">Remplacez \*\* \<SuppressDrillthroughWarning> true \</SuppressDrillthroughWarning> par \<SuppressDrillthroughWarning> false \</SuppressDrillthroughWarning> \*\*.</span><span class="sxs-lookup"><span data-stu-id="16b65-119">Change **\<SuppressDrillthroughWarning>true\</SuppressDrillthroughWarning>to \<SuppressDrillthroughWarning>false\</SuppressDrillthroughWarning>**.</span></span>  
  
4.  <span data-ttu-id="16b65-120">Redémarrez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16b65-120">Restart [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16b65-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="16b65-121">See Also</span></span>  
 <span data-ttu-id="16b65-122">[Rapports personnalisés dans Management Studio](custom-reports-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="16b65-122">[Custom Reports in Management Studio](custom-reports-in-management-studio.md) </span></span>  
 <span data-ttu-id="16b65-123">[Ajouter un rapport personnalisé à Management Studio](add-a-custom-report-to-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="16b65-123">[Add a Custom Report to Management Studio](add-a-custom-report-to-management-studio.md) </span></span>  
 [<span data-ttu-id="16b65-124">Utiliser des rapports personnalisés avec les propriétés de nœud de l’Explorateur d’objets</span><span class="sxs-lookup"><span data-stu-id="16b65-124">Use Custom Reports with Object Explorer Node Properties</span></span>](use-custom-reports-with-object-explorer-node-properties.md)  
  
  
