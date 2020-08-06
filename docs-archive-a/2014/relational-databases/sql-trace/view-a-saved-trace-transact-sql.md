---
title: Afficher une trace enregistrée (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], viewing
- displaying traces
- viewing traces
ms.assetid: 3a95a816-aa89-4d5f-858c-968a9cb3ee87
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f8b67760d575b651b089a6936adc945d74a1c62b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710503"
---
# <a name="view-a-saved-trace-transact-sql"></a><span data-ttu-id="80e82-102">Afficher une trace enregistrée (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="80e82-102">View a Saved Trace (Transact-SQL)</span></span>
  <span data-ttu-id="80e82-103">Cette rubrique décrit l'utilisation des fonctions intégrées pour afficher une trace enregistrée.</span><span class="sxs-lookup"><span data-stu-id="80e82-103">This topic describes how to use built-in functions to view a saved trace.</span></span>  
  
### <a name="to-view-a-specific-trace"></a><span data-ttu-id="80e82-104">Pour afficher une trace</span><span class="sxs-lookup"><span data-stu-id="80e82-104">To view a specific trace</span></span>  
  
1.  <span data-ttu-id="80e82-105">Exécutez **fn_trace_getinfo** en spécifiant l’identificateur de la trace sur laquelle vous souhaitez des informations.</span><span class="sxs-lookup"><span data-stu-id="80e82-105">Execute **fn_trace_getinfo** by specifying the ID of the trace about which information is needed.</span></span> <span data-ttu-id="80e82-106">Cette fonction retourne un tableau qui présente la trace, ses propriétés et des informations sur celle-ci.</span><span class="sxs-lookup"><span data-stu-id="80e82-106">This function returns a table that lists the trace, trace property, and information about the property.</span></span>  
  
     <span data-ttu-id="80e82-107">Appelez la fonction comme suit :</span><span class="sxs-lookup"><span data-stu-id="80e82-107">Invoke the function this way:</span></span>  
  
    ```  
    SELECT *  
    FROM ::fn_trace_getinfo(trace_id)  
    ```  
  
### <a name="to-view-all-existing-traces"></a><span data-ttu-id="80e82-108">Pour afficher toutes les traces existantes</span><span class="sxs-lookup"><span data-stu-id="80e82-108">To view all existing traces</span></span>  
  
1.  <span data-ttu-id="80e82-109">Exécutez **fn_trace_getinfo** en spécifiant `0` ou `default`.</span><span class="sxs-lookup"><span data-stu-id="80e82-109">Execute **fn_trace_getinfo** by specifying `0` or `default`.</span></span> <span data-ttu-id="80e82-110">Cette fonction retourne un tableau qui présente toutes les traces, leurs propriétés et des informations sur celles-ci.</span><span class="sxs-lookup"><span data-stu-id="80e82-110">This function returns a table that lists all the traces, their properties, and information about these properties.</span></span>  
  
     <span data-ttu-id="80e82-111">Appelez la fonction comme suit :</span><span class="sxs-lookup"><span data-stu-id="80e82-111">Invoke the function as follows:</span></span>  
  
    ```  
    SELECT *  
    FROM ::fn_trace_getinfo(default)  
    ```  
  
## <a name="net-framework-security"></a><span data-ttu-id="80e82-112">Sécurité du .NET Framework</span><span class="sxs-lookup"><span data-stu-id="80e82-112">.NET Framework Security</span></span>  
 <span data-ttu-id="80e82-113">Pour exécuter la fonction intégrée **fn_trace_getinfo**, l’utilisateur a besoin de l’autorisation suivante :</span><span class="sxs-lookup"><span data-stu-id="80e82-113">To run the built-in function **fn_trace_getinfo**, the user needs the following permission:</span></span>  
  
 <span data-ttu-id="80e82-114">ALTER TRACE sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="80e82-114">ALTER TRACE on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80e82-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="80e82-115">See Also</span></span>  
 <span data-ttu-id="80e82-116">[sys.fn_trace_getinfo &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-trace-getinfo-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="80e82-116">[sys.fn_trace_getinfo &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-trace-getinfo-transact-sql) </span></span>  
 [<span data-ttu-id="80e82-117">Afficher et analyser des traces avec SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="80e82-117">View and Analyze Traces with SQL Server Profiler</span></span>](../../tools/sql-server-profiler/view-and-analyze-traces-with-sql-server-profiler.md)  
  
  
