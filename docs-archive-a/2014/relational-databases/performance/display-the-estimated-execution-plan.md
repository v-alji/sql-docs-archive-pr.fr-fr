---
title: Afficher le plan d’exécution estimé | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- zoom [SQL Server]
- estimated execution plan [SQL Server]
- displaying execution plans
- viewing execution plans
- execution plans [SQL Server], displaying
- customizing execution plan display [SQL Server]
- modifying execution plan display
- custom zoom [SQL Server]
ms.assetid: e94aa576-4c0c-4c54-ad05-6c3432cc615b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 79c0972661d40eb9e359cf43f7a1f0b1b2ae4b0c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697986"
---
# <a name="display-the-estimated-execution-plan"></a><span data-ttu-id="df355-102">Affichage du plan d'exécution estimé</span><span class="sxs-lookup"><span data-stu-id="df355-102">Display the Estimated Execution Plan</span></span>
  <span data-ttu-id="df355-103">Cette rubrique décrit la génération d'un plan d'exécution estimé au format graphique à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df355-103">This topic describes how to generate graphical estimated execution plans by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="df355-104">Lors de la génération de ces plans, les traitements ou requêtes [!INCLUDE[tsql](../../includes/tsql-md.md)] ne sont pas exécutés,</span><span class="sxs-lookup"><span data-stu-id="df355-104">When estimated execution plans are generated, the [!INCLUDE[tsql](../../includes/tsql-md.md)] queries or batches do not execute.</span></span> <span data-ttu-id="df355-105">mais le plan d'exécution des requêtes que [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] utiliserait probablement si celles-ci étaient exécutées s'affiche.</span><span class="sxs-lookup"><span data-stu-id="df355-105">Instead, the execution plan that is generated displays the query execution plan that [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] would most probably use if the queries were actually executed.</span></span>  
  
 <span data-ttu-id="df355-106">Pour utiliser cette fonctionnalité, les utilisateurs doivent disposer des autorisations adéquates pour exécuter la requête [!INCLUDE[tsql](../../includes/tsql-md.md)] correspondant au plan d'exécution graphique à générer, et ils doivent posséder l'autorisation SHOWPLAN pour toutes les bases de données référencées par la requête.</span><span class="sxs-lookup"><span data-stu-id="df355-106">To use this feature, users must have the appropriate permissions to execute the [!INCLUDE[tsql](../../includes/tsql-md.md)] query for which a graphical execution plan is being generated, and they must be granted the SHOWPLAN permission for all databases referenced by the query.</span></span>  
  
### <a name="to-display-the-estimated-execution-plan-for-a-query"></a><span data-ttu-id="df355-107">Pour afficher le plan d'exécution estimé pour une requête</span><span class="sxs-lookup"><span data-stu-id="df355-107">To display the estimated execution plan for a query</span></span>  
  
1.  <span data-ttu-id="df355-108">Dans la barre d’outils, cliquez sur **Requête de moteur de base de données**.</span><span class="sxs-lookup"><span data-stu-id="df355-108">On the toolbar, click **Database Engine Query**.</span></span> <span data-ttu-id="df355-109">Vous pouvez également ouvrir une requête existante et afficher le plan d’exécution estimé en cliquant sur le bouton **Ouvrir un fichier** dans la barre d’outils puis en choisissant la requête existante.</span><span class="sxs-lookup"><span data-stu-id="df355-109">You can also open an existing query and display the estimated execution plan by clicking the **Open File** toolbar button and locating the existing query.</span></span>  
  
2.  <span data-ttu-id="df355-110">Entrez la requête pour laquelle afficher le plan d'exécution estimé.</span><span class="sxs-lookup"><span data-stu-id="df355-110">Enter the query for which you would like to display the estimated execution plan.</span></span>  
  
3.  <span data-ttu-id="df355-111">Dans le menu **Requête** , cliquez sur **Afficher le plan d’exécution estimé** ou cliquez sur le bouton **Afficher le plan d’exécution estimé** dans la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="df355-111">On the **Query** menu, click **Display Estimated Execution Plan** or click the **Display Estimated Execution Plan** toolbar button.</span></span> <span data-ttu-id="df355-112">Le plan d’exécution estimé s’affiche sous l’onglet **Plan d’exécution** du volet de résultats.</span><span class="sxs-lookup"><span data-stu-id="df355-112">The estimated execution plan is displayed on the **Execution Plan** tab in the results pane.</span></span> <span data-ttu-id="df355-113">Pour afficher des informations supplémentaires, placez le curseur sur les icônes des opérateurs logiques et physiques, et consultez la description et les propriétés de l'opérateur indiquées dans l'infobulle.</span><span class="sxs-lookup"><span data-stu-id="df355-113">To view additional information, pause the mouse over the logical and physical operator icons and view the description and properties of the operator in the displayed ToolTip.</span></span> <span data-ttu-id="df355-114">Il est également possible d'afficher les propriétés des opérateurs dans la fenêtre Propriétés.</span><span class="sxs-lookup"><span data-stu-id="df355-114">Alternatively, you can view operator properties in the Properties window.</span></span> <span data-ttu-id="df355-115">Si les propriétés ne sont pas visibles, cliquez avec le bouton droit sur un opérateur, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="df355-115">If Properties is not visible, right-click an operator and click **Properties**.</span></span> <span data-ttu-id="df355-116">Sélectionnez l'opérateur de votre choix.</span><span class="sxs-lookup"><span data-stu-id="df355-116">Select an operator to view its properties.</span></span>  
  
4.  <span data-ttu-id="df355-117">Pour modifier l’affichage du plan d’exécution, cliquez avec le bouton droit sur le plan d’exécution, puis sélectionnez **Zoom avant**, **Zoom arrière**, **Zoom personnalisé**ou **Zoom pour ajuster**.</span><span class="sxs-lookup"><span data-stu-id="df355-117">To alter the display of the execution plan, right-click the execution plan and select **Zoom In**, **Zoom Out**, **Custom Zoom**, or **Zoom to Fit**.</span></span> <span data-ttu-id="df355-118">**Zoom avant** et **Zoom arrière** permettent respectivement d’agrandir et de réduire l’affichage du plan d’exécution suivant des pourcentages fixes.</span><span class="sxs-lookup"><span data-stu-id="df355-118">**Zoom In** and **Zoom Out** allow you to magnify or reduce the execution plan by fixed amounts.</span></span> <span data-ttu-id="df355-119">**Zoom personnalisé** vous permet de définir votre propre facteur de zoom, par exemple 80 %.</span><span class="sxs-lookup"><span data-stu-id="df355-119">**Custom Zoom** allows you to define your own display magnification, such as zooming at 80 percent.</span></span> <span data-ttu-id="df355-120">Enfin, l’option**Zoom pour ajuster** agrandit le plan de sorte que sa taille soit ajustée en fonction de celle du volet de résultats.</span><span class="sxs-lookup"><span data-stu-id="df355-120">**Zoom to Fit** magnifies the execution plan to fit the result pane.</span></span>  
  
  
