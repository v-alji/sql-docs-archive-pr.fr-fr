---
title: MSSQLSERVER_948 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "948"
helpviewer_keywords:
- 948 (Database Engine error)
ms.assetid: 95c4ad45-a518-4165-a5c4-6e6b932b0570
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e8461069a3fceb7bdca318b82a522f7f51af83d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604486"
---
# <a name="mssqlserver_948"></a><span data-ttu-id="68045-102">MSSQLSERVER_948</span><span class="sxs-lookup"><span data-stu-id="68045-102">MSSQLSERVER_948</span></span>
    
## <a name="details"></a><span data-ttu-id="68045-103">Détails</span><span class="sxs-lookup"><span data-stu-id="68045-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="68045-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="68045-104">Product Name</span></span>|<span data-ttu-id="68045-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="68045-105">SQL Server</span></span>|  
|<span data-ttu-id="68045-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="68045-106">Event ID</span></span>|<span data-ttu-id="68045-107">948</span><span class="sxs-lookup"><span data-stu-id="68045-107">948</span></span>|  
|<span data-ttu-id="68045-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="68045-108">Event Source</span></span>|<span data-ttu-id="68045-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="68045-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="68045-110">Composant</span><span class="sxs-lookup"><span data-stu-id="68045-110">Component</span></span>|<span data-ttu-id="68045-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="68045-111">SQLEngine</span></span>|  
|<span data-ttu-id="68045-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="68045-112">Symbolic Name</span></span>|<span data-ttu-id="68045-113">N/D</span><span class="sxs-lookup"><span data-stu-id="68045-113">NA</span></span>|  
|<span data-ttu-id="68045-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="68045-114">Message Text</span></span>|<span data-ttu-id="68045-115">La base de données '%.\*ls' ne peut pas être ouverte, car sa version est %d.</span><span class="sxs-lookup"><span data-stu-id="68045-115">The database '%.\*ls' cannot be opened because it is version %d.</span></span> <span data-ttu-id="68045-116">Ce serveur prend en charge la version %d et les versions précédentes.</span><span class="sxs-lookup"><span data-stu-id="68045-116">This server supports version %d and earlier.</span></span> <span data-ttu-id="68045-117">Un chemin de mise à niveau vers une version antérieure n'est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="68045-117">A downgrade path is not supported.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="68045-118">Explication</span><span class="sxs-lookup"><span data-stu-id="68045-118">Explanation</span></span>  
 <span data-ttu-id="68045-119">Certaines fonctionnalités de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] affectent la structure des fichiers de base de données.</span><span class="sxs-lookup"><span data-stu-id="68045-119">Certain features in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] affect the structure of the database files.</span></span> <span data-ttu-id="68045-120">Lorsque vous attachez une base de données à une autre instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], le format de fichier peut ne pas être compatible avec une autre version du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68045-120">When you attach a database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the file format might not be compatible with a different version of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="68045-121">Par exemple, cette erreur peut se produire si vous utilisez le format de stockage vardecimal dans une version plus récente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], puis que vous essayez d'attacher les fichiers de base de données dans une version antérieure à [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 2.</span><span class="sxs-lookup"><span data-stu-id="68045-121">For example, this error can be caused by using the vardecimal storage format in a later version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and then trying to attach the database files in a version earlier than [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 2.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="68045-122">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="68045-122">User Action</span></span>  
 <span data-ttu-id="68045-123">Identifiez la version de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui s'exécute sur le serveur d'origine.</span><span class="sxs-lookup"><span data-stu-id="68045-123">Determine the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on the originating server.</span></span> <span data-ttu-id="68045-124">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , cliquez avec le bouton droit sur le serveur, puis cliquez sur **Propriétés** ou tapez `SELECT @@VERSION` dans une fenêtre de requête.</span><span class="sxs-lookup"><span data-stu-id="68045-124">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], either right-click the server and then click **Properties** or type `SELECT @@VERSION` in a query window.</span></span> <span data-ttu-id="68045-125">Ouvrez la base de données en utilisant la version d'origine de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68045-125">Open the database by using the original version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="68045-126">Examinez les fonctionnalités qui sont activées sur la base de données d'origine dans l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68045-126">Investigate the features that are enabled on the original database in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="68045-127">Modifiez ces paramètres de façon à utiliser la version de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans laquelle la base de données sera attachée.</span><span class="sxs-lookup"><span data-stu-id="68045-127">Modify these settings to work with the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in which the database will be attached.</span></span>  
  
  
