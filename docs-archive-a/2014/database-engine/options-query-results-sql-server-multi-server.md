---
title: Options (résultats de la requête-SQL Server-multi-serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqleditors.multiserverresultssettings
- VS.ToolsOptionsPages.QueryResults.SqlServer.SQLMultiServerResults
ms.assetid: d6768bd8-9cb5-4606-a726-a33a1df9e1bb
author: rothja
ms.author: jroth
ms.openlocfilehash: 8273ad5edc65dd7351533209e9fa670c49f75f7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705407"
---
# <a name="options-query-results-sql-server-multi-server"></a><span data-ttu-id="e6da4-102">Options (Résultats de la requête/SQL Server/Multiserveur)</span><span class="sxs-lookup"><span data-stu-id="e6da4-102">Options (Query Results-SQL Server-Multi-Server)</span></span>
  <span data-ttu-id="e6da4-103">Lorsque vous interrogez plusieurs serveurs en même temps, utilisez cette page pour spécifier les options d'affichage des jeux de résultats.</span><span class="sxs-lookup"><span data-stu-id="e6da4-103">When you are querying multiple servers at the same time, use this page to specify the options for displaying result sets.</span></span> <span data-ttu-id="e6da4-104">Les résultats de fusion combinent les jeux de résultats provenant de tous les serveurs en un jeu de résultats unique.</span><span class="sxs-lookup"><span data-stu-id="e6da4-104">Merge results combines the result sets from all servers into a single result set.</span></span> <span data-ttu-id="e6da4-105">Lors de la fusion de résultats, le premier serveur à répondre définit le schéma pour le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="e6da4-105">When merging results, the first server to respond sets the schema for the result set.</span></span> <span data-ttu-id="e6da4-106">Pour fusionner les jeux de résultats, la requête doit retourner le même nombre de colonnes avec les mêmes noms de colonnes à partir de chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="e6da4-106">To merge the result sets, the query must return the same number of columns with the same column names from each server.</span></span> <span data-ttu-id="e6da4-107">Lors de la fusion de résultats, un message s'affiche pour chaque serveur qui ne correspond pas au schéma (nombre de colonnes et noms des colonnes) retourné par le premier serveur ayant retourné des résultats.</span><span class="sxs-lookup"><span data-stu-id="e6da4-107">When merging results, a message is displayed for each server that does not match the schema (column count and column names) that is returned by the first server to return results.</span></span>  
  
 <span data-ttu-id="e6da4-108">Lorsque vous ne fusionnez pas de résultats, le jeu de résultats de chaque serveur est affiché dans sa propre grille avec son propre schéma.</span><span class="sxs-lookup"><span data-stu-id="e6da4-108">When you do not merge results, the result set from each server will be displayed in its own grid with its own schema.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="e6da4-109">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="e6da4-109">UI element list</span></span>  
 <span data-ttu-id="e6da4-110">**Fusionner les résultats**</span><span class="sxs-lookup"><span data-stu-id="e6da4-110">**Merge results**</span></span>  
 <span data-ttu-id="e6da4-111">Activez cette case à cocher pour combiner les jeux de résultats de plusieurs serveurs dans la même grille.</span><span class="sxs-lookup"><span data-stu-id="e6da4-111">Select this check box to combine the result sets from several servers into the same grid.</span></span>  
  
 <span data-ttu-id="e6da4-112">**Ajouter le nom de serveur aux résultats**</span><span class="sxs-lookup"><span data-stu-id="e6da4-112">**Add server name to the results**</span></span>  
 <span data-ttu-id="e6da4-113">Activez cette case à cocher pour inclure une colonne supplémentaire qui indique le nom du serveur ayant produit chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="e6da4-113">Select this check box to include an additional column that provides the name of the server that produced each row.</span></span>  
  
 <span data-ttu-id="e6da4-114">**Ajouter le nom de connexion aux résultats**</span><span class="sxs-lookup"><span data-stu-id="e6da4-114">**Add login name to the results**</span></span>  
 <span data-ttu-id="e6da4-115">Activez cette case à cocher pour inclure une colonne supplémentaire qui indique la connexion utilisée pour se connecter au serveur ayant fourni chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="e6da4-115">Select this check box to include an additional column that provides the login that was used to connect to the server that provided each row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6da4-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e6da4-116">See Also</span></span>  
 <span data-ttu-id="e6da4-117">[Créer un serveur de gestion centralisée et un groupe de serveurs &#40;SQL Server Management Studio&#41;](../ssms/register-servers/create-a-central-management-server-and-server-group.md) </span><span class="sxs-lookup"><span data-stu-id="e6da4-117">[Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;](../ssms/register-servers/create-a-central-management-server-and-server-group.md) </span></span>  
 [<span data-ttu-id="e6da4-118">Exécuter des instructions simultanément sur plusieurs serveurs &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="e6da4-118">Execute Statements Against Multiple Servers Simultaneously &#40;SQL Server Management Studio&#41;</span></span>](../ssms/register-servers/execute-statements-against-multiple-servers-simultaneously.md)  
  
  
