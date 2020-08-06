---
title: Enregistrer des résultats d’une trace dans une table (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- saving traces
- traces [SQL Server], saving
ms.assetid: edbecf74-683b-4e43-a1ef-7a3d5f5e27f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 08acfb4e7136f8b28d1c990d508b8578f96a57b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705700"
---
# <a name="save-trace-results-to-a-table-sql-server-profiler"></a><span data-ttu-id="9e910-102">Enregistrer des résultats d'une trace dans une table (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="9e910-102">Save Trace Results to a Table (SQL Server Profiler)</span></span>
  <span data-ttu-id="9e910-103">Cette rubrique explique comment enregistrer les résultats d'une trace dans une table de base de données à l'aide du [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9e910-103">This topic describes how to save trace results to a database table by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-save-trace-results-to-a-table"></a><span data-ttu-id="9e910-104">Pour enregistrer les résultats d'une trace dans une table</span><span class="sxs-lookup"><span data-stu-id="9e910-104">To save trace results to a table</span></span>  
  
1.  <span data-ttu-id="9e910-105">Dans le menu **Fichier** , cliquez sur **Nouvelle trace**, puis connectez-vous à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9e910-105">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="9e910-106">La boîte de dialogue **Propriétés de la trace**apparaît.</span><span class="sxs-lookup"><span data-stu-id="9e910-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9e910-107">Si la case **Démarrer le suivi juste après avoir établi la connexion**est cochée, la boîte de dialogue **Propriétés de la trace**ne s’affiche pas et le suivi se lance.</span><span class="sxs-lookup"><span data-stu-id="9e910-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="9e910-108">Pour désactiver ce paramètre, accédez au menu **Outils**, cliquez sur **Options**et désactivez la case à cocher **Démarrer le suivi juste après avoir établi la connexion** .</span><span class="sxs-lookup"><span data-stu-id="9e910-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="9e910-109">Dans la zone **Nom de la trace** , entrez le nom de la trace, puis cliquez sur **Enregistrer dans la table**.</span><span class="sxs-lookup"><span data-stu-id="9e910-109">In the **Trace name** box, type a name for the trace, and then click **Save to table**.</span></span>  
  
3.  <span data-ttu-id="9e910-110">Dans la boîte de dialogue **Se connecter au serveur** , connectez-vous à la base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui contiendra la table.</span><span class="sxs-lookup"><span data-stu-id="9e910-110">In the **Connect to server** dialog box, connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that will contain the trace table.</span></span>  
  
4.  <span data-ttu-id="9e910-111">Dans la boîte de dialogue **Table de destination** , sélectionnez le nom d’une base de données dans la liste **Base de données**.</span><span class="sxs-lookup"><span data-stu-id="9e910-111">In the **Destination Table** dialog box, select a database from the **Database**list.</span></span>  
  
5.  <span data-ttu-id="9e910-112">Dans la liste **Propriétaire** , sélectionnez le propriétaire de la trace.</span><span class="sxs-lookup"><span data-stu-id="9e910-112">In the **Owner** list, select the owner for the trace.</span></span>  
  
6.  <span data-ttu-id="9e910-113">Dans la liste **Table** , tapez ou sélectionnez le nom de la table dans laquelle seront enregistrés les résultats de la trace.</span><span class="sxs-lookup"><span data-stu-id="9e910-113">In the **Table** list, type or select the table name for the trace results.</span></span> <span data-ttu-id="9e910-114">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9e910-114">Click **OK.**</span></span>  
  
7.  <span data-ttu-id="9e910-115">Dans la boîte de dialogue Propriétés de la **trace** , activez la case à cocher définir le nombre maximal de lignes **(en milliers)** pour spécifier le nombre maximal de lignes à enregistrer.</span><span class="sxs-lookup"><span data-stu-id="9e910-115">In the **Trace Properties** dialog box, select the **Set maximum rows (in thousands)** check box to specify the maximum number of rows to save.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e910-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9e910-116">See Also</span></span>  
 [<span data-ttu-id="9e910-117">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="9e910-117">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
