---
title: Modifier les modèles de trace | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- templates [SQL Server], SQL Server Profiler
- Profiler [SQL Server Profiler], templates
- trace templates [SQL Server]
- modifying trace templates
- SQL Server Profiler, templates
ms.assetid: 75b62a54-8d16-4599-bd2d-c42cfcc209f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4a26d0a70f65b6ff60dcf42ffb98e67dc0d2b52d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601230"
---
# <a name="modify-trace-templates"></a><span data-ttu-id="01ebf-102">Modifier des modèles de trace</span><span class="sxs-lookup"><span data-stu-id="01ebf-102">Modify Trace Templates</span></span>
  <span data-ttu-id="01ebf-103">Vous pouvez modifier les modèles enregistrés dans un fichier sur l'ordinateur local sur lequel le [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] est en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="01ebf-103">You can modify templates that are saved in a file on the local computer on which [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] is running.</span></span> <span data-ttu-id="01ebf-104">Vous pouvez également modifier les modèles dérivés de ces fichiers.</span><span class="sxs-lookup"><span data-stu-id="01ebf-104">You can also modify templates derived from those files.</span></span> <span data-ttu-id="01ebf-105">Quand vous modifiez des modèles existants, vous modifiez leurs propriétés, telles que les classes d’événements et les colonnes de données, en suivant l’ordre de la définition initiale des propriétés, sous l’onglet **Sélection des événements** de la boîte de dialogue **Propriétés de la trace** .</span><span class="sxs-lookup"><span data-stu-id="01ebf-105">When you modify existing templates, you edit template properties such as event classes and data columns, in the same order that the properties were set originally, on the **Events Selection** tab of the **Trace Properties** dialog box.</span></span> <span data-ttu-id="01ebf-106">Les classes d'événements et les colonnes de données peuvent être ajoutées ou supprimées, et les filtres peuvent être modifiés.</span><span class="sxs-lookup"><span data-stu-id="01ebf-106">Event classes and data columns can be added or removed, and filters can be changed.</span></span> <span data-ttu-id="01ebf-107">Une fois le modèle modifié, un modèle spécifique à l'utilisateur est créé et le modèle système initial demeure intact.</span><span class="sxs-lookup"><span data-stu-id="01ebf-107">After the template is modified, a user-specific template is created and the original system template is left intact.</span></span> <span data-ttu-id="01ebf-108">Pour plus d’informations, consultez [Enregistrer des traces et des modèles de trace](save-traces-and-trace-templates.md).</span><span class="sxs-lookup"><span data-stu-id="01ebf-108">For more information, see [Save Traces and Trace Templates](save-traces-and-trace-templates.md).</span></span>  
  
 <span data-ttu-id="01ebf-109">Il se peut que vous deviez dériver un modèle d'un fichier de trace existant si vous ne vous rappelez pas (ou si n'avez pas effectué d'enregistrement) du modèle d'origine utilisé pour créer la trace, ou bien si vous voulez exécuter la même trace à une date ultérieure.</span><span class="sxs-lookup"><span data-stu-id="01ebf-109">You may need to derive a template from an existing trace file if you cannot remember (or have not saved) the original template that was used to create the trace, or if you want to run the same trace at a later date.</span></span> <span data-ttu-id="01ebf-110">Lorsque vous utilisez des traces existantes, vous pouvez afficher les propriétés, mais pas les modifier.</span><span class="sxs-lookup"><span data-stu-id="01ebf-110">When working with existing traces, you can view the properties, but you cannot modify the properties.</span></span> <span data-ttu-id="01ebf-111">Pour modifier les propriétés, arrêtez ou suspendez la trace.</span><span class="sxs-lookup"><span data-stu-id="01ebf-111">To modify the properties, stop or pause the trace.</span></span> <span data-ttu-id="01ebf-112">Pour plus d’informations, consultez [Dériver un modèle à partir d’un fichier de trace ou d’une table de trace &#40;SQL Server Profiler&#41;](sql-server-profiler.md) et [Dériver un modèle à partir d’une trace en cours d’exécution &#40;SQL Server Profiler&#41;](derive-a-template-from-a-running-trace-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="01ebf-112">For more information, see [Derive a Template from a Trace File or Trace Table &#40;SQL Server Profiler&#41;](sql-server-profiler.md) and [Derive a Template from a Running Trace &#40;SQL Server Profiler&#41;](derive-a-template-from-a-running-trace-sql-server-profiler.md).</span></span>  
  
 <span data-ttu-id="01ebf-113">**Pour créer un modèle de trace**</span><span class="sxs-lookup"><span data-stu-id="01ebf-113">**To create a trace template**</span></span>  
  
 [<span data-ttu-id="01ebf-114">Créer un modèle de trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="01ebf-114">Create a Trace Template &#40;SQL Server Profiler&#41;</span></span>](create-a-trace-template-sql-server-profiler.md)  
  
 <span data-ttu-id="01ebf-115">**Pour exécuter une trace à partir d'un modèle de trace**</span><span class="sxs-lookup"><span data-stu-id="01ebf-115">**To run a trace from a trace template**</span></span>  
  
 [<span data-ttu-id="01ebf-116">Créer une trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="01ebf-116">Create a Trace &#40;SQL Server Profiler&#41;</span></span>](create-a-trace-sql-server-profiler.md)  
  
 <span data-ttu-id="01ebf-117">**Pour modifier un modèle de trace**</span><span class="sxs-lookup"><span data-stu-id="01ebf-117">**To modify a trace template**</span></span>  
  
 [<span data-ttu-id="01ebf-118">Utilisation de SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="01ebf-118">Using SQL Server Profiler</span></span>](../../database-engine/modify-a-trace-template-sql-server-profiler.md)  
  
 [<span data-ttu-id="01ebf-119">Avec Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="01ebf-119">Using Transact-SQL</span></span>](../../relational-databases/sql-trace/modify-an-existing-trace-transact-sql.md)  
  
 <span data-ttu-id="01ebf-120">**Pour ajouter ou supprimer des événements dans un modèle de trace ou un fichier de trace**</span><span class="sxs-lookup"><span data-stu-id="01ebf-120">**To add or remove events from a trace template or trace file**</span></span>  
  
 [<span data-ttu-id="01ebf-121">Utilisation de SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="01ebf-121">Using SQL Server Profiler</span></span>](specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md)  
  
 [<span data-ttu-id="01ebf-122">Avec Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="01ebf-122">Using Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="01ebf-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="01ebf-123">See Also</span></span>  
 [<span data-ttu-id="01ebf-124">Démarrer une trace</span><span class="sxs-lookup"><span data-stu-id="01ebf-124">Start a Trace</span></span>](start-a-trace.md)  
  
  
