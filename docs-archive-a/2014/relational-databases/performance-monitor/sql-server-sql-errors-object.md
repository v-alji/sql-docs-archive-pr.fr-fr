---
title: SQL Server, objet SQL Errors | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQL Errors object
- SQLServer:SQL Errors
ms.assetid: 6e5273ca-29cb-4618-88a2-70b9b8d6cf76
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 11bfb728e79b4fc175fb8a2fe16c9f1662a205ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696756"
---
# <a name="sql-server-sql-errors-object"></a><span data-ttu-id="718d2-102">Objet SQLServer:SQL Errors</span><span class="sxs-lookup"><span data-stu-id="718d2-102">SQL Server, SQL Errors Object</span></span>
  <span data-ttu-id="718d2-103">L'objet **SQLServer:SQL Errors** de Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournit des compteurs qui permettent de surveiller les **Erreurs SQL**.</span><span class="sxs-lookup"><span data-stu-id="718d2-103">The **SQLServer:SQL Errors** object in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides counters to monitor **SQL Errors**.</span></span>  
  
 <span data-ttu-id="718d2-104">Ce tableau décrit les compteurs **Erreurs SQL** de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="718d2-104">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **SQL Errors** counters.</span></span>  
  
|<span data-ttu-id="718d2-105">Compteurs d'erreurs SQL de SQL Server</span><span class="sxs-lookup"><span data-stu-id="718d2-105">SQL Server SQL Errors counters</span></span>|<span data-ttu-id="718d2-106">Description</span><span class="sxs-lookup"><span data-stu-id="718d2-106">Description</span></span>|  
|------------------------------------|-----------------|  
|<span data-ttu-id="718d2-107">**Erreurs/s**</span><span class="sxs-lookup"><span data-stu-id="718d2-107">**Errors/sec**</span></span>|<span data-ttu-id="718d2-108">Nombre d'erreurs par seconde.</span><span class="sxs-lookup"><span data-stu-id="718d2-108">Number of errors/sec.</span></span>|  
  
 <span data-ttu-id="718d2-109">Chaque compteur de l'objet contient les instances suivantes :</span><span class="sxs-lookup"><span data-stu-id="718d2-109">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="718d2-110">Élément</span><span class="sxs-lookup"><span data-stu-id="718d2-110">Item</span></span>|<span data-ttu-id="718d2-111">Définition</span><span class="sxs-lookup"><span data-stu-id="718d2-111">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="718d2-112">**_Total**</span><span class="sxs-lookup"><span data-stu-id="718d2-112">**_Total**</span></span>|<span data-ttu-id="718d2-113">Informations sur toutes les erreurs.</span><span class="sxs-lookup"><span data-stu-id="718d2-113">Information for all errors.</span></span>|  
|<span data-ttu-id="718d2-114">**DB Offline Errors**</span><span class="sxs-lookup"><span data-stu-id="718d2-114">**DB Offline Errors**</span></span>|<span data-ttu-id="718d2-115">Effectue le suivi des erreurs graves qui amènent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à mettre la base de données actuelle hors ligne.</span><span class="sxs-lookup"><span data-stu-id="718d2-115">Tracks severe errors that cause [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to take the current database offline.</span></span>|  
|<span data-ttu-id="718d2-116">**Info Errors**</span><span class="sxs-lookup"><span data-stu-id="718d2-116">**Info Errors**</span></span>|<span data-ttu-id="718d2-117">Informations relatives aux messages d'erreur qui fournissent des renseignements aux utilisateurs mais qui ne provoquent pas d'erreurs.</span><span class="sxs-lookup"><span data-stu-id="718d2-117">Information related to error messages that provide information to users but do not cause errors.</span></span>|  
|<span data-ttu-id="718d2-118">**Kill Connection Errors**</span><span class="sxs-lookup"><span data-stu-id="718d2-118">**Kill Connection Errors**</span></span>|<span data-ttu-id="718d2-119">Effectue le suivi des erreurs graves qui amènent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à mettre fin à la connexion actuelle.</span><span class="sxs-lookup"><span data-stu-id="718d2-119">Tracks severe errors that cause [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to kill the current connection.</span></span>|  
|<span data-ttu-id="718d2-120">**User Errors**</span><span class="sxs-lookup"><span data-stu-id="718d2-120">**User Errors**</span></span>|<span data-ttu-id="718d2-121">Informations relatives aux erreurs utilisateur.</span><span class="sxs-lookup"><span data-stu-id="718d2-121">Information about user errors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="718d2-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="718d2-122">See Also</span></span>  
 [<span data-ttu-id="718d2-123">Analyser l’utilisation des ressources &#40;Moniteur système&#41;</span><span class="sxs-lookup"><span data-stu-id="718d2-123">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
