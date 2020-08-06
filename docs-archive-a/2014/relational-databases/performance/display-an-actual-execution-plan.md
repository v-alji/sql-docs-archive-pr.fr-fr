---
title: Afficher un plan d’exécution réel | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- displaying execution plans
- actual execution plans
- viewing execution plans
- execution plans [SQL Server], displaying
ms.assetid: 9e583a18-5f4a-4054-bfe1-4b2a76630db6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f384e2d2752b7601fbb46b8ee7f7b56a2615651c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698004"
---
# <a name="display-an-actual-execution-plan"></a><span data-ttu-id="8bf2e-102">Afficher un plan d'exécution réel</span><span class="sxs-lookup"><span data-stu-id="8bf2e-102">Display an Actual Execution Plan</span></span>
  <span data-ttu-id="8bf2e-103">Cette rubrique explique comment générer des plans d'exécution graphiques réels à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8bf2e-103">This topic describes how to generate actual graphical execution plans by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="8bf2e-104">Lorsque des plans d'exécution réels sont générés, les requêtes ou les traitements [!INCLUDE[tsql](../../includes/tsql-md.md)] sont exécutés.</span><span class="sxs-lookup"><span data-stu-id="8bf2e-104">When actual execution plans are generated, the [!INCLUDE[tsql](../../includes/tsql-md.md)] queries or batches execute.</span></span> <span data-ttu-id="8bf2e-105">Le plan d'exécution généré affiche le plan d'exécution réel que le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] utilise pour exécuter les requêtes.</span><span class="sxs-lookup"><span data-stu-id="8bf2e-105">The execution plan that is generated displays the actual query execution plan that the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses to execute the queries.</span></span>  
  
 <span data-ttu-id="8bf2e-106">Pour être en mesure d'utiliser cette fonction, les utilisateurs doivent bénéficier des autorisations permettant d'exécuter les requêtes [!INCLUDE[tsql](../../includes/tsql-md.md)] pour lesquelles un plan d'exécution graphique est actuellement généré. Qui plus est, les utilisateurs doivent se voir accorder l'autorisation SHOWPLAN pour toutes les bases de données référencées par la requête.</span><span class="sxs-lookup"><span data-stu-id="8bf2e-106">To use this feature, users must have the appropriate permissions to execute the [!INCLUDE[tsql](../../includes/tsql-md.md)] queries for which a graphical execution plan is being generated, and they must be granted the SHOWPLAN permission for all databases referenced by the query.</span></span>  
  
### <a name="to-include-an-execution-plan-for-a-query-during-execution"></a><span data-ttu-id="8bf2e-107">Pour inclure un plan d'exécution pour une requête durant l'exécution</span><span class="sxs-lookup"><span data-stu-id="8bf2e-107">To include an execution plan for a query during execution</span></span>  
  
1.  <span data-ttu-id="8bf2e-108">Dans la barre d’outils [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , cliquez sur **Requête de moteur de base de données**.</span><span class="sxs-lookup"><span data-stu-id="8bf2e-108">On the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] toolbar, click **Database Engine Query**.</span></span> <span data-ttu-id="8bf2e-109">Vous pouvez également ouvrir une requête existante et afficher le plan d’exécution estimé en cliquant sur le bouton **Ouvrir un fichier** dans la barre d’outils puis en choisissant la requête existante.</span><span class="sxs-lookup"><span data-stu-id="8bf2e-109">You can also open an existing query and display the estimated execution plan by clicking the **Open File** toolbar button and locating the existing query.</span></span>  
  
2.  <span data-ttu-id="8bf2e-110">Entrez la requête pour laquelle vous souhaitez afficher le plan d'exécution réel.</span><span class="sxs-lookup"><span data-stu-id="8bf2e-110">Enter the query for which you would like to display the actual execution plan.</span></span>  
  
3.  <span data-ttu-id="8bf2e-111">Dans le menu **requête** , cliquez sur **inclure le plan d’exécution réel** ou cliquez sur le bouton inclure le plan d' **exécution réel** .</span><span class="sxs-lookup"><span data-stu-id="8bf2e-111">On the **Query** menu, click **Include Actual Execution Plan** or click the **Include Actual Execution Plan** toolbar button</span></span>  
  
4.  <span data-ttu-id="8bf2e-112">Exécutez la requête en cliquant sur le bouton de la barre d’outils **Exécuter** .</span><span class="sxs-lookup"><span data-stu-id="8bf2e-112">Execute the query by clicking the **Execute** toolbar button.</span></span> <span data-ttu-id="8bf2e-113">Le plan utilisé par l’optimiseur de requête est affiché sous l’onglet **Plan d’exécution** dans le volet de résultats.</span><span class="sxs-lookup"><span data-stu-id="8bf2e-113">The plan used by the query optimizer is displayed on the **Execution Plan** tab in the results pane.</span></span> <span data-ttu-id="8bf2e-114">Placez le curseur de la souris sur les opérateurs logiques et physiques pour visualiser la description et les propriétés des opérateurs dans l'info-bulle affichée.</span><span class="sxs-lookup"><span data-stu-id="8bf2e-114">Pause the mouse over the logical and physical operators to view the description and properties of the operators in the displayed ToolTip.</span></span>  
  
     <span data-ttu-id="8bf2e-115">Il est également possible d'afficher les propriétés des opérateurs dans la fenêtre Propriétés.</span><span class="sxs-lookup"><span data-stu-id="8bf2e-115">Alternatively, you can view operator properties in the Properties window.</span></span> <span data-ttu-id="8bf2e-116">Si Propriétés n’est pas visible, cliquez avec le bouton droit sur un opérateur et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="8bf2e-116">If Properties is not visible, right-click an operator and select **Properties**.</span></span> <span data-ttu-id="8bf2e-117">Sélectionnez l'opérateur de votre choix.</span><span class="sxs-lookup"><span data-stu-id="8bf2e-117">Select an operator to view its properties.</span></span>  
  
5.  <span data-ttu-id="8bf2e-118">Si vous voulez modifier l’affichage du plan d’exécution, cliquez avec le bouton droit sur le plan d’exécution et sélectionnez **Zoom avant**, **Zoom arrière**, **Zoom personnalisé**ou **Zoom pour ajuster**.</span><span class="sxs-lookup"><span data-stu-id="8bf2e-118">You can alter the display of the execution plan by right-clicking the execution plan and selecting **Zoom In**, **Zoom Out**, **Custom Zoom**, or **Zoom to Fit**.</span></span> <span data-ttu-id="8bf2e-119">Les options**Zoom avant** et **Zoom arrière** vous permettent d’effectuer un zoom avant ou arrière sur le plan d’exécution. Quant à l’option **Zoom personnalisé** , elle vous permet de définir votre propre zoom, par exemple, un pourcentage de zoom de 80.</span><span class="sxs-lookup"><span data-stu-id="8bf2e-119">**Zoom In** and **Zoom Out** allow you to zoom in or out on the execution plan, while **Custom Zoom** allows you to define your own zoom, such as zooming at 80 percent.</span></span> <span data-ttu-id="8bf2e-120">Enfin, l’option**Zoom pour ajuster** agrandit le plan de sorte que sa taille soit ajustée en fonction de celle du volet de résultats.</span><span class="sxs-lookup"><span data-stu-id="8bf2e-120">**Zoom to Fit** magnifies the execution plan to fit the result pane.</span></span>  
  
  
