---
title: Filtrer des identificateurs de processus serveur dans une trace (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], traces
- filters [SQL Server], SPIDs
- traces [SQL Server], filters
ms.assetid: f5945c39-be6b-4632-91cb-92066c80e188
author: stevestein
ms.author: sstein
ms.openlocfilehash: 99ae7eac6f19bd942a04f97b0a7da580eadc9dbf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706923"
---
# <a name="filter-server-process-ids-spids-in-a-trace-sql-server-profiler"></a><span data-ttu-id="71a49-102">Filtrer des identificateurs de processus serveur (SPID, Server Process ID) dans une trace (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="71a49-102">Filter Server Process IDs (SPIDs) in a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="71a49-103">Cette rubrique décrit comment filtrer les identificateurs de processus serveur (SPID, Server Process ID) dans une trace grâce au [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="71a49-103">This topic describes how to filter server process identifiers (SPIDs) in a trace by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-filter-system-ids-in-a-trace"></a><span data-ttu-id="71a49-104">Pour filtrer des ID système dans une trace</span><span class="sxs-lookup"><span data-stu-id="71a49-104">To filter system IDs in a trace</span></span>  
  
1.  <span data-ttu-id="71a49-105">Dans le menu **Fichier** , cliquez sur **Nouvelle trace**, puis connectez-vous à une instance de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="71a49-105">On the **File** menu, click **New Trace**, and then connect to an instance of SQL Server.</span></span>  
  
     <span data-ttu-id="71a49-106">La boîte de dialogue **Propriétés de la trace**apparaît.</span><span class="sxs-lookup"><span data-stu-id="71a49-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="71a49-107">Si l’option **Démarrer le suivi juste après avoir fait la connexion**est sélectionnée, la boîte de dialogue Propriétés de la **trace**ne s’affiche pas et la trace démarre à la place.</span><span class="sxs-lookup"><span data-stu-id="71a49-107">if **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear, and the trace begins instead.</span></span> <span data-ttu-id="71a49-108">Pour désactiver ce paramètre, accédez au menu **Outils**, cliquez sur **Options**et désactivez la case à cocher **Démarrer le suivi juste après avoir établi la connexion** .</span><span class="sxs-lookup"><span data-stu-id="71a49-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="71a49-109">Dans la zone **Nom de la trace** , tapez un nom pour la trace.</span><span class="sxs-lookup"><span data-stu-id="71a49-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="71a49-110">Dans la liste de noms **Utiliser le modèle**, sélectionnez un modèle de trace.</span><span class="sxs-lookup"><span data-stu-id="71a49-110">In the **Use the template**name list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="71a49-111">Le cas échéant, spécifiez un fichier ou une table de destination pour y enregistrer les résultats du suivi.</span><span class="sxs-lookup"><span data-stu-id="71a49-111">Optionally, specify a destination file or table in which to save the trace results.</span></span>  
  
5.  <span data-ttu-id="71a49-112">Sous l’onglet **Sélection des événements**, cliquez sur l’en-tête de la colonne **SPID**pour ouvrir la boîte de dialogue **Modifier le filtre** .</span><span class="sxs-lookup"><span data-stu-id="71a49-112">On the **Events Selection**tab, click the **SPID**column heading to launch the **Edit Filter** dialog box.</span></span> <span data-ttu-id="71a49-113">Vous pouvez également cliquer avec le bouton droit de la souris sur l’en-tête de colonne et choisir **Modifier le filtre des colonnes**parmi les éléments du menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="71a49-113">You can also right-click the column heading and choose **Edit Column Filter**.</span></span> <span data-ttu-id="71a49-114">Si la colonne **SPID** n’apparaît pas, cochez la case **Afficher toutes les colonnes** .</span><span class="sxs-lookup"><span data-stu-id="71a49-114">If the **SPID** column does not appear, check the **Show all columns** box.</span></span>  
  
6.  <span data-ttu-id="71a49-115">Dans la boîte de dialogue **Modifier le filtre** , développez l’opérateur de comparaison voulu et entrez le SPID correspondant à la valeur de comparaison.</span><span class="sxs-lookup"><span data-stu-id="71a49-115">In the **Edit Filter** dialog box, expand the appropriate comparison operator, and enter a SPID as a value for the comparison.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71a49-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="71a49-116">See Also</span></span>  
 [<span data-ttu-id="71a49-117">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="71a49-117">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
