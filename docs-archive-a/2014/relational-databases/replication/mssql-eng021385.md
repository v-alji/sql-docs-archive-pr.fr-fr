---
title: MSSQL_ENG021385 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021385 error
ms.assetid: a2c0444f-d97b-4760-8905-3574791c2e26
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b73d3216f07cb44d750a37149634258648f1bd48
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697932"
---
# <a name="mssql_eng021385"></a><span data-ttu-id="1288a-102">MSSQL_ENG021385</span><span class="sxs-lookup"><span data-stu-id="1288a-102">MSSQL_ENG021385</span></span>
    
## <a name="message-details"></a><span data-ttu-id="1288a-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="1288a-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1288a-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="1288a-104">Product Name</span></span>|<span data-ttu-id="1288a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1288a-105">SQL Server</span></span>|  
|<span data-ttu-id="1288a-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="1288a-106">Event ID</span></span>|<span data-ttu-id="1288a-107">21385</span><span class="sxs-lookup"><span data-stu-id="1288a-107">21385</span></span>|  
|<span data-ttu-id="1288a-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="1288a-108">Event Source</span></span>|<span data-ttu-id="1288a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1288a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1288a-110">Composant</span><span class="sxs-lookup"><span data-stu-id="1288a-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="1288a-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="1288a-111">Symbolic Name</span></span>||  
|<span data-ttu-id="1288a-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="1288a-112">Message Text</span></span>|<span data-ttu-id="1288a-113">L'instantané n'a pas réussi à traiter la publication '%1!'.</span><span class="sxs-lookup"><span data-stu-id="1288a-113">Snapshot failed to process publication '%s'.</span></span> <span data-ttu-id="1288a-114">L'incident peut être dû à une activité de changement de schéma actif ou à l'ajout de nouveaux articles.</span><span class="sxs-lookup"><span data-stu-id="1288a-114">Possibly due to active schema change activity or new articles being added.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1288a-115">Explication</span><span class="sxs-lookup"><span data-stu-id="1288a-115">Explanation</span></span>  
 <span data-ttu-id="1288a-116">Cette erreur est générée si l'Agent d'instantané démarre au moment où des modifications de la base de données de publication sont en cours, par exemple l'ajout ou la suppression d'articles ou des modifications de schéma sur des objets publiés.</span><span class="sxs-lookup"><span data-stu-id="1288a-116">This error is raised if the Snapshot Agent starts running when there are ongoing changes to the publication database, including adding or dropping articles and performing schema changes on published objects.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1288a-117">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="1288a-117">User Action</span></span>  
 <span data-ttu-id="1288a-118">Redémarrez l'Agent d'instantané au terme de la modification de la base de données de publication.</span><span class="sxs-lookup"><span data-stu-id="1288a-118">Restart the Snapshot Agent after changes to the publication database are complete.</span></span> <span data-ttu-id="1288a-119">Pour plus d’informations, consultez [Démarrer et arrêter un Agent de réplication &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) et [Concepts des exécutables de l’agent de réplication](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="1288a-119">For more information, see [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) and [Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1288a-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1288a-120">See Also</span></span>  
 [<span data-ttu-id="1288a-121">Guide de référence des erreurs et des événements &#40;réplication&#41;</span><span class="sxs-lookup"><span data-stu-id="1288a-121">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
