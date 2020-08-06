---
title: MSSQLSERVER_945 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 945 (Database Engine error)
ms.assetid: ee501d13-0bd9-4627-896c-ed5b1bdb88b3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 51284cdcf48f1bf713a853f9c87457cb5291cc4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604488"
---
# <a name="mssqlserver_945"></a><span data-ttu-id="cfc62-102">MSSQLSERVER_945</span><span class="sxs-lookup"><span data-stu-id="cfc62-102">MSSQLSERVER_945</span></span>
    
## <a name="details"></a><span data-ttu-id="cfc62-103">Détails</span><span class="sxs-lookup"><span data-stu-id="cfc62-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cfc62-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="cfc62-104">Product Name</span></span>|<span data-ttu-id="cfc62-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="cfc62-105">SQL Server</span></span>|  
|<span data-ttu-id="cfc62-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="cfc62-106">Event ID</span></span>|<span data-ttu-id="cfc62-107">945</span><span class="sxs-lookup"><span data-stu-id="cfc62-107">945</span></span>|  
|<span data-ttu-id="cfc62-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="cfc62-108">Event Source</span></span>|<span data-ttu-id="cfc62-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cfc62-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cfc62-110">Composant</span><span class="sxs-lookup"><span data-stu-id="cfc62-110">Component</span></span>|<span data-ttu-id="cfc62-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="cfc62-111">SQLEngine</span></span>|  
|<span data-ttu-id="cfc62-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="cfc62-112">Symbolic Name</span></span>|<span data-ttu-id="cfc62-113">DB_IS_SHUTDOWN</span><span class="sxs-lookup"><span data-stu-id="cfc62-113">DB_IS_SHUTDOWN</span></span>|  
|<span data-ttu-id="cfc62-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="cfc62-114">Message Text</span></span>|<span data-ttu-id="cfc62-115">La base de données '%.\*ls' ne peut pas être ouverte, car des fichiers sont inaccessibles, ou la mémoire ou l'espace disque sont insuffisants.</span><span class="sxs-lookup"><span data-stu-id="cfc62-115">Database '%.\*ls' cannot be opened due to inaccessible files or insufficient memory or disk space.</span></span>  <span data-ttu-id="cfc62-116">Pour plus d’informations, consultez le journal des erreurs de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cfc62-116">See the SQL Server error log for details.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cfc62-117">Explication</span><span class="sxs-lookup"><span data-stu-id="cfc62-117">Explanation</span></span>  
 <span data-ttu-id="cfc62-118">Il n'a pas été possible d'accéder à la base de données car il manque des fichiers ou d'autres ressources.</span><span class="sxs-lookup"><span data-stu-id="cfc62-118">The database could not be accessed because files or other resources are missing.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cfc62-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="cfc62-119">User Action</span></span>  
 <span data-ttu-id="cfc62-120">Consultez le journal des erreurs pour trouver des informations supplémentaires sur les problèmes de mémoire, d'espace disque ou d'autorisation.</span><span class="sxs-lookup"><span data-stu-id="cfc62-120">Check the error log for additional information about memory, disk space, or permission failure.</span></span> <span data-ttu-id="cfc62-121">Vérifiez l’emplacement des fichiers .mdf et .ndf de la base de données affectée et assurez-vous que le compte utilisé par le [!INCLUDE[ssDE](../../includes/ssde-md.md)] est autorisé à accéder à ces fichiers.</span><span class="sxs-lookup"><span data-stu-id="cfc62-121">Confirm the location of the .mdf and .ndf files for the affected database and confirm that the account used by the [!INCLUDE[ssDE](../../includes/ssde-md.md)] has permission to access those files.</span></span> <span data-ttu-id="cfc62-122">Après avoir corrigé le problème, redémarrez la base de données en utilisant l'instruction ALTER DATABASE pour la mettre en ligne (ONLINE).</span><span class="sxs-lookup"><span data-stu-id="cfc62-122">After correcting the problem, restart the database by using ALTER DATABASE to set it ONLINE.</span></span>  
  
  
