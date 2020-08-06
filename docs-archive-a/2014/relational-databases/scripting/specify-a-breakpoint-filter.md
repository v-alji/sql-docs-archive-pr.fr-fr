---
title: Spécifier un filtre de point d'arrêt
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoint filter
ms.assetid: 7bf1dddd-7b0b-4c47-8a7b-28a5569b4fa5
author: rothja
ms.author: jroth
ms.openlocfilehash: 9fc320397da1bddc0d28191c359c4d311b23e044
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610575"
---
# <a name="specify-a-breakpoint-filter"></a><span data-ttu-id="d5d5d-102">Spécifier un filtre de point d'arrêt</span><span class="sxs-lookup"><span data-stu-id="d5d5d-102">Specify a Breakpoint Filter</span></span>
  <span data-ttu-id="d5d5d-103">Un filtre de point d'arrêt limite l'action du point d'arrêt uniquement aux ordinateurs, aux processus du système d'exploitation et aux threads spécifiés.</span><span class="sxs-lookup"><span data-stu-id="d5d5d-103">A breakpoint filter limits the breakpoint to acting only on specified computers, operating system processes, and threads.</span></span> <span data-ttu-id="d5d5d-104">Les filtres de point d'arrêt sont utilisés en général lors du débogage d'applications parallèles.</span><span class="sxs-lookup"><span data-stu-id="d5d5d-104">Breakpoint filters are typically used when debugging parallel applications.</span></span>  
  
##  <a name="filter-considerations"></a><a name="BKMK_ActionConsiderations"></a> <span data-ttu-id="d5d5d-105">Règles de filtre</span><span class="sxs-lookup"><span data-stu-id="d5d5d-105">Filter Considerations</span></span>  
 <span data-ttu-id="d5d5d-106">Les filtres de point d'arrêt ne sont en général pas utilisés avec le débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] parce que les scripts et les procédures stockées [!INCLUDE[tsql](../../includes/tsql-md.md)] ne sont pas des applications parallèles.</span><span class="sxs-lookup"><span data-stu-id="d5d5d-106">Breakpoint filters are not typically used with the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger because [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts and stored procedures are not parallel applications.</span></span>  
  
#### <a name="to-specify-a-breakpoint-filter"></a><span data-ttu-id="d5d5d-107">Pour spécifier un filtre de point d'arrêt</span><span class="sxs-lookup"><span data-stu-id="d5d5d-107">To Specify a Breakpoint Filter</span></span>  
  
1.  <span data-ttu-id="d5d5d-108">Dans la fenêtre de l’éditeur, cliquez avec le bouton droit sur le glyphe du point d’arrêt, puis cliquez sur **Filtre** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="d5d5d-108">In the editor window, right-click the breakpoint glyph, and then click **Filter** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="d5d5d-109">-ou-</span><span class="sxs-lookup"><span data-stu-id="d5d5d-109">-or-</span></span>  
  
     <span data-ttu-id="d5d5d-110">Dans la fenêtre **Points d’arrêt** , cliquez avec le bouton droit sur le glyphe du point d’arrêt, puis cliquez sur **Filtre** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="d5d5d-110">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Filter** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="d5d5d-111">Dans la boîte de dialogue **Filtres de point d’arrêt** , utilisez la zone **Filtre** pour spécifier des ordinateurs par nom, ou des processus du système d’exploitation et des threads par nom ou numéro d’ID :</span><span class="sxs-lookup"><span data-stu-id="d5d5d-111">In the **Breakpoint Filters** dialog box, use the **Filter** box to specify computers by name, or operating system processes and threads by either name or ID number:</span></span>  
  
    -   <span data-ttu-id="d5d5d-112">`MachineName` est l'ordinateur qui exécute l'instance du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="d5d5d-112">`MachineName` is the computer running the instance of the Database Engine.</span></span>  
  
    -   <span data-ttu-id="d5d5d-113">`ProcessID` et `ProcessName` correspondent au processus de système d'exploitation qui exécute l'instance du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="d5d5d-113">`ProcessID`, and `ProcessName` are the operating system process running the instance of the Database Engine.</span></span>  
  
    -   <span data-ttu-id="d5d5d-114">`ThreadID` et `ThreadName` correspondent au thread de système d'exploitation qui exécute le lot, la procédure ou la fonction [!INCLUDE[tsql](../../includes/tsql-md.md)] dans l'instance du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="d5d5d-114">`ThreadID` and `ThreadName` are the operating system thread running the [!INCLUDE[tsql](../../includes/tsql-md.md)] batch, procedure, or function in the instance of the Database Engine.</span></span>  
  
3.  <span data-ttu-id="d5d5d-115">Cliquez sur **OK** pour implémenter les modifications ou sur **Annuler** pour fermer sans appliquer les modifications.</span><span class="sxs-lookup"><span data-stu-id="d5d5d-115">Click **OK** to implement the changes, or **Cancel** to exit without applying the changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5d5d-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d5d5d-116">See Also</span></span>  
 <span data-ttu-id="d5d5d-117">[Spécifier une condition de point d'arrêt](specify-a-breakpoint-condition.md) </span><span class="sxs-lookup"><span data-stu-id="d5d5d-117">[Specify a Breakpoint Condition](specify-a-breakpoint-condition.md) </span></span>  
 <span data-ttu-id="d5d5d-118">[Spécifier un nombre d'accès](specify-a-hit-count.md) </span><span class="sxs-lookup"><span data-stu-id="d5d5d-118">[Specify a Hit Count](specify-a-hit-count.md) </span></span>  
 [<span data-ttu-id="d5d5d-119">Spécifier une action de point d’arrêt</span><span class="sxs-lookup"><span data-stu-id="d5d5d-119">Specify a Breakpoint Action</span></span>](specify-a-breakpoint-action.md)  
