---
title: Définir une taille maximale de table de trace (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- size [SQL Server], trace tables
- maximum table size for traces
ms.assetid: d0ae83e5-1c88-4a2e-be05-2c341280b978
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5f48efbe02e300e06faf857ed0fb36ae340ad979
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694919"
---
# <a name="set-a-maximum-table-size-for-a-trace-table-sql-server-profiler"></a><span data-ttu-id="5f835-102">Définir une taille maximale de table de trace (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="5f835-102">Set a Maximum Table Size for a Trace Table (SQL Server Profiler)</span></span>
  <span data-ttu-id="5f835-103">Cette rubrique explique comment définir une taille maximale de table de trace à l'aide du [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f835-103">This topic describes how to set a maximum table size for trace tables by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-set-a-maximum-table-size-for-a-trace-table"></a><span data-ttu-id="5f835-104">Pour définir une taille maximale de table de trace</span><span class="sxs-lookup"><span data-stu-id="5f835-104">To set a maximum table size for a trace table</span></span>  
  
1.  <span data-ttu-id="5f835-105">Dans le menu **Fichier** , cliquez sur **Nouvelle trace**, puis connectez-vous à une instance de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5f835-105">On the **File** menu, click **New Trace**, and then connect to an instance of SQL Server.</span></span>  
  
     <span data-ttu-id="5f835-106">La boîte de dialogue **Propriétés de la trace**apparaît.</span><span class="sxs-lookup"><span data-stu-id="5f835-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5f835-107">Si la case **Démarrer le suivi juste après avoir établi la connexion**est cochée, la boîte de dialogue **Propriétés de la trace**ne s’affiche pas et le suivi se lance.</span><span class="sxs-lookup"><span data-stu-id="5f835-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="5f835-108">Pour désactiver ce paramètre, accédez au menu **Outils**, cliquez sur **Options**et désactivez la case à cocher **Démarrer le suivi juste après avoir établi la connexion** .</span><span class="sxs-lookup"><span data-stu-id="5f835-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="5f835-109">Dans la zone **Nom de la trace** , tapez un nom pour la trace.</span><span class="sxs-lookup"><span data-stu-id="5f835-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="5f835-110">Dans la liste **Nom du modèle**, sélectionnez un modèle de trace.</span><span class="sxs-lookup"><span data-stu-id="5f835-110">In the **Template name**list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="5f835-111">Cochez la case **Enregistrer dans la table**.</span><span class="sxs-lookup"><span data-stu-id="5f835-111">Select the **Save to table**check box.</span></span>  
  
5.  <span data-ttu-id="5f835-112">Connectez-vous au serveur sur lequel vous voulez stocker la trace.</span><span class="sxs-lookup"><span data-stu-id="5f835-112">Connect to the server on which you want the trace to be stored.</span></span>  
  
     <span data-ttu-id="5f835-113">La boîte de dialogue **Table de destination** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="5f835-113">The **Destination Table** dialog box appears.</span></span>  
  
6.  <span data-ttu-id="5f835-114">Sélectionnez une base de données pour la trace dans la liste **Base de données** .</span><span class="sxs-lookup"><span data-stu-id="5f835-114">Select a database for the trace from the **Database** list.</span></span>  
  
7.  <span data-ttu-id="5f835-115">Dans la zone **Table** , tapez ou sélectionnez un nom pour la table.</span><span class="sxs-lookup"><span data-stu-id="5f835-115">In the **Table** box, type or select a table name.</span></span>  
  
8.  <span data-ttu-id="5f835-116">Sélectionnez **Définir le nombre de lignes maximal** , puis spécifiez un nombre de lignes maximal pour la table de trace.</span><span class="sxs-lookup"><span data-stu-id="5f835-116">Select the **Set maximum rows** check box, and specify a maximum number of rows for the trace table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5f835-117">Quand le nombre de lignes dans la table dépasse le maximum spécifié, les événements de la trace ne sont plus enregistrés,</span><span class="sxs-lookup"><span data-stu-id="5f835-117">When the number of rows in the table exceeds the maximum that you have specified, the trace events are no longer recorded.</span></span> <span data-ttu-id="5f835-118">mais la trace continue.</span><span class="sxs-lookup"><span data-stu-id="5f835-118">However, tracing continues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f835-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5f835-119">See Also</span></span>  
 <span data-ttu-id="5f835-120">[SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="5f835-120">[SQL Server Profiler](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="5f835-121">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="5f835-121">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
