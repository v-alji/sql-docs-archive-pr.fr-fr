---
title: Afficher et enregistrer des plans d’exécution | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Showplan results
- execution plans [SQL Server]
- queries [SQL Server], tuning
- execution plans [SQL Server], how-to topics
- SQL Server Management Studio [SQL Server], execution plans
- tuning queries [SQL Server]
ms.assetid: bcd6f094-c613-4835-ae19-4caaadb4bb17
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e236ed2a298bc8fc9a829948a864f6f5c27a2ba2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698015"
---
# <a name="display-and-save-execution-plans"></a><span data-ttu-id="f9da2-102">Afficher et enregistrer des plans d'exécution</span><span class="sxs-lookup"><span data-stu-id="f9da2-102">Display and Save Execution Plans</span></span>
  <span data-ttu-id="f9da2-103">Cette section explique comment afficher des plans d'exécution et les enregistrer dans un fichier au format XML en utilisant Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9da2-103">This section explains how to display execution plans and how to save execution plans to a file in XML format by using Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="f9da2-104">Les plans d'exécution affichent graphiquement les méthodes de récupération des données choisies par l'optimiseur de requête de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f9da2-104">Execution plans graphically display the data retrieval methods chosen by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] query optimizer.</span></span> <span data-ttu-id="f9da2-105">Les plans d'exécution représentent le coût d'exécution de requêtes et d'instructions spécifiques dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] par des icônes plutôt que par la représentation tabulaire résultant des instructions SET SHOWPLAN_ALL ou SET SHOWPLAN_TEXT.</span><span class="sxs-lookup"><span data-stu-id="f9da2-105">Execution plans represent the execution cost of specific statements and queries in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using icons rather than the tabular representation produced by the SET SHOWPLAN_ALL or SET SHOWPLAN_TEXT statements.</span></span> <span data-ttu-id="f9da2-106">Cette approche graphique s'avère très utile pour la compréhension des caractéristiques de performances d'une requête.</span><span class="sxs-lookup"><span data-stu-id="f9da2-106">This graphical approach is very useful for understanding the performance characteristics of a query.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f9da2-107">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="f9da2-107">In This Section</span></span>  
  
-   [<span data-ttu-id="f9da2-108">Afficher le plan d’exécution estimé</span><span class="sxs-lookup"><span data-stu-id="f9da2-108">Display the Estimated Execution Plan</span></span>](display-the-estimated-execution-plan.md)  
  
-   [<span data-ttu-id="f9da2-109">Afficher un plan d'exécution réel</span><span class="sxs-lookup"><span data-stu-id="f9da2-109">Display an Actual Execution Plan</span></span>](display-an-actual-execution-plan.md)  
  
-   [<span data-ttu-id="f9da2-110">Enregistrer un plan d’exécution au format XML</span><span class="sxs-lookup"><span data-stu-id="f9da2-110">Save an Execution Plan in XML Format</span></span>](save-an-execution-plan-in-xml-format.md)  
  
  
