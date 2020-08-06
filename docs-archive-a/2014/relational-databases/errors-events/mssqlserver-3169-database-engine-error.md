---
title: MSSQLSERVER_3169 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "3169"
helpviewer_keywords:
- 3169 (Database Engine error)
ms.assetid: 7d4dbed6-bb94-4908-bc03-2040a9cf63bc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8b13d9c1c17eddb34648bc4a536e2fccf371b99a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605472"
---
# <a name="mssqlserver_3169"></a><span data-ttu-id="f3ed7-102">MSSQLSERVER_3169</span><span class="sxs-lookup"><span data-stu-id="f3ed7-102">MSSQLSERVER_3169</span></span>
    
## <a name="details"></a><span data-ttu-id="f3ed7-103">Détails</span><span class="sxs-lookup"><span data-stu-id="f3ed7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f3ed7-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="f3ed7-104">Product Name</span></span>|<span data-ttu-id="f3ed7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f3ed7-105">SQL Server</span></span>|  
|<span data-ttu-id="f3ed7-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="f3ed7-106">Event ID</span></span>|<span data-ttu-id="f3ed7-107">3169</span><span class="sxs-lookup"><span data-stu-id="f3ed7-107">3169</span></span>|  
|<span data-ttu-id="f3ed7-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="f3ed7-108">Event Source</span></span>|<span data-ttu-id="f3ed7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f3ed7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f3ed7-110">Composant</span><span class="sxs-lookup"><span data-stu-id="f3ed7-110">Component</span></span>|<span data-ttu-id="f3ed7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f3ed7-111">SQLEngine</span></span>|  
|<span data-ttu-id="f3ed7-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="f3ed7-112">Symbolic Name</span></span>|<span data-ttu-id="f3ed7-113">N/D</span><span class="sxs-lookup"><span data-stu-id="f3ed7-113">NA</span></span>|  
|<span data-ttu-id="f3ed7-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="f3ed7-114">Message Text</span></span>|<span data-ttu-id="f3ed7-115">La base de données a été sauvegardée sur un serveur exécutant la version %ls.</span><span class="sxs-lookup"><span data-stu-id="f3ed7-115">The database was backed up on a server running version %ls.</span></span> <span data-ttu-id="f3ed7-116">Cette version est incompatible avec ce serveur, qui exécute la version %ls.</span><span class="sxs-lookup"><span data-stu-id="f3ed7-116">That version is incompatible with this server, which is running version %ls.</span></span> <span data-ttu-id="f3ed7-117">Restaurez la base de données sur un serveur qui prend en charge la sauvegarde ou utilisez une sauvegarde compatible avec ce serveur.</span><span class="sxs-lookup"><span data-stu-id="f3ed7-117">Either restore the database on a server that supports the backup, or use a backup that is compatible with this server.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f3ed7-118">Explication</span><span class="sxs-lookup"><span data-stu-id="f3ed7-118">Explanation</span></span>  
 <span data-ttu-id="f3ed7-119">Certaines fonctionnalités de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] affectent la structure des fichiers de base de données.</span><span class="sxs-lookup"><span data-stu-id="f3ed7-119">Certain features in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] affect the structure of the database files.</span></span> <span data-ttu-id="f3ed7-120">Lorsque vous restaurez une base de données dans une autre instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], le format de fichier peut ne pas être compatible avec une autre version du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3ed7-120">When you restore a database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the file format might not be compatible with a different version of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
 <span data-ttu-id="f3ed7-121">Par exemple, cette erreur peut se produire si vous utilisez le format de stockage vardecimal dans une version plus récente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], puis que vous essayez de restaurer les fichiers de base de données dans une version antérieure à [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 2.</span><span class="sxs-lookup"><span data-stu-id="f3ed7-121">For example, this error can be caused by using the vardecimalstorage format in a later version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and then trying to restore the database files in a version earlier than [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 2.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f3ed7-122">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="f3ed7-122">User Action</span></span>  
 <span data-ttu-id="f3ed7-123">Identifiez la version de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui s'exécute sur le serveur d'origine.</span><span class="sxs-lookup"><span data-stu-id="f3ed7-123">Determine the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on the originating server.</span></span> <span data-ttu-id="f3ed7-124">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , cliquez avec le bouton droit sur le serveur, puis cliquez sur **Propriétés** ou tapez `SELECT @@VERSION` dans une fenêtre de requête.</span><span class="sxs-lookup"><span data-stu-id="f3ed7-124">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], either right-click the server and then click **Properties** or type `SELECT @@VERSION` in a query window.</span></span> <span data-ttu-id="f3ed7-125">Ouvrez la base de données en utilisant la version d'origine de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3ed7-125">Open the database by using the original version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f3ed7-126">Examinez les fonctionnalités qui sont activées sur la base de données d'origine dans l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3ed7-126">Investigate the features that are enabled on the original database in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f3ed7-127">Modifiez ces paramètres de façon à utiliser la version de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans laquelle la base de données sera restaurée.</span><span class="sxs-lookup"><span data-stu-id="f3ed7-127">Modify these settings to work with the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in which the database will be restored.</span></span>  
  
  
