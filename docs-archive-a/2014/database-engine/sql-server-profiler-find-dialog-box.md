---
title: Boîte de dialogue SQL Server Profiler-Rechercher | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.find.f1
helpviewer_keywords:
- Find dialog box
ms.assetid: dfaeec04-93d3-4214-9fc1-38b80179b36b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cedf50930c06d211ebcee0c45a249667219f392c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705392"
---
# <a name="sql-server-profiler---find-dialog-box"></a><span data-ttu-id="6bc9f-102">Générateur de profils SQL Server (boîte de dialogue Rechercher)</span><span class="sxs-lookup"><span data-stu-id="6bc9f-102">SQL Server Profiler - Find Dialog Box</span></span>
  <span data-ttu-id="6bc9f-103">Utilisez la boîte de dialogue **Rechercher** pour rechercher une trace de caractères ou de mots spécifiques.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-103">Use the **Find** dialog box to search a trace for specific characters or words.</span></span> <span data-ttu-id="6bc9f-104">Pour annuler une recherche en cours, appuyez sur ÉCHAP.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-104">To cancel a search in progress, press ESC.</span></span>  
  
 <span data-ttu-id="6bc9f-105">Dans le menu [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)]Edition **, cliquez sur** Rechercher **pour ouvrir cette boîte de dialogue dans**.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-105">To open this dialog box in [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], on the **Edit** menu, click **Find**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6bc9f-106">Options</span><span class="sxs-lookup"><span data-stu-id="6bc9f-106">Options</span></span>  
 <span data-ttu-id="6bc9f-107">**Rechercher**</span><span class="sxs-lookup"><span data-stu-id="6bc9f-107">**Find what**</span></span>  
 <span data-ttu-id="6bc9f-108">Entrez le texte à rechercher.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-108">Enter the text that you want to search for.</span></span> <span data-ttu-id="6bc9f-109">La recherche retourne toute chaîne contenant la chaîne spécifiée.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-109">The search matches any string containing the specified string.</span></span> <span data-ttu-id="6bc9f-110">Par exemple, si vous recherchez "Completed", la chaîne "SQL:BatchCompleted" est retournée.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-110">For example, searching for "Completed" matches "SQL:BatchCompleted."</span></span> <span data-ttu-id="6bc9f-111">Les caractères génériques (\*, ?, etc.) ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-111">Wild card characters (\*, ?, etc.) are not supported.</span></span>  
  
 <span data-ttu-id="6bc9f-112">**Rechercher dans la colonne**</span><span class="sxs-lookup"><span data-stu-id="6bc9f-112">**Search in column**</span></span>  
 <span data-ttu-id="6bc9f-113">Cliquez sur une colonne de données à rechercher ou sur **\<All columns>** pour rechercher toutes les colonnes de données dans la trace.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-113">Click a data column to search, or click **\<All columns>** to search all the data columns in the trace.</span></span>  
  
 <span data-ttu-id="6bc9f-114">**Respecter la casse**</span><span class="sxs-lookup"><span data-stu-id="6bc9f-114">**Match case**</span></span>  
 <span data-ttu-id="6bc9f-115">Recherche du texte présentant la même casse que celui spécifié dans la zone **Rechercher** .</span><span class="sxs-lookup"><span data-stu-id="6bc9f-115">Finds text that has the same case as the **Find what** box.</span></span> <span data-ttu-id="6bc9f-116">Désactivez cette case à cocher pour rechercher dans la trace des correspondances avec les caractères indiqués mais sans distinction entre les majuscules et les minuscules.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-116">Clear this check box to find examples in the trace that are in both uppercase and lowercase text characters.</span></span>  
  
 <span data-ttu-id="6bc9f-117">**Mot entier**</span><span class="sxs-lookup"><span data-stu-id="6bc9f-117">**Match whole word**</span></span>  
 <span data-ttu-id="6bc9f-118">Restreint la recherche à des mots entiers.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-118">Restricts the search to entire words.</span></span> <span data-ttu-id="6bc9f-119">Décochez la case **Mot entier** pour rechercher des caractères spécifiques au sein d’un mot.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-119">Clear the **Match whole word** check box to search for characters within a word.</span></span>  
  
 <span data-ttu-id="6bc9f-120">**Suivant**</span><span class="sxs-lookup"><span data-stu-id="6bc9f-120">**Find Next**</span></span>  
 <span data-ttu-id="6bc9f-121">Recherche la correspondance suivante avec les caractères spécifiés dans la zone **Rechercher** .</span><span class="sxs-lookup"><span data-stu-id="6bc9f-121">Finds the next example of the characters in the **Find what** box.</span></span>  
  
 <span data-ttu-id="6bc9f-122">**Précédent**</span><span class="sxs-lookup"><span data-stu-id="6bc9f-122">**Find Previous**</span></span>  
 <span data-ttu-id="6bc9f-123">Recherche dans la trace la correspondance précédente avec les caractères spécifiés dans la zone **Rechercher** .</span><span class="sxs-lookup"><span data-stu-id="6bc9f-123">Searches backwards in the trace, to find the previous example of the characters in the **Find what** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bc9f-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6bc9f-124">See Also</span></span>  
 <span data-ttu-id="6bc9f-125">[Rechercher une valeur ou une colonne de données pendant le suivi &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/find-a-value-or-data-column-while-tracing-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="6bc9f-125">[Find a Value or Data Column While Tracing &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/find-a-value-or-data-column-while-tracing-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="6bc9f-126">[Créer un &#40;de trace SQL Server Profiler&#41;](../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="6bc9f-126">[Create a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="6bc9f-127">[Ouvrez une table de trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="6bc9f-127">[Open a Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="6bc9f-128">[Ouvrir un fichier de trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="6bc9f-128">[Open a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="6bc9f-129">[Modèles et autorisations du générateur de SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="6bc9f-129">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="6bc9f-130">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="6bc9f-130">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
