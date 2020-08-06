---
title: MSSQLSERVER_1101 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1101 (Database Engine error)
ms.assetid: d63b67d5-59f5-4f77-904e-5ba67f2dd850
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 631b0ab1466815cbacfd71b4f9fd714fabd0f7b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612922"
---
# <a name="mssqlserver_1101"></a><span data-ttu-id="ad533-102">MSSQLSERVER_1101</span><span class="sxs-lookup"><span data-stu-id="ad533-102">MSSQLSERVER_1101</span></span>
    
## <a name="details"></a><span data-ttu-id="ad533-103">Détails</span><span class="sxs-lookup"><span data-stu-id="ad533-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ad533-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="ad533-104">Product Name</span></span>|<span data-ttu-id="ad533-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ad533-105">SQL Server</span></span>|  
|<span data-ttu-id="ad533-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="ad533-106">Event ID</span></span>|<span data-ttu-id="ad533-107">1101</span><span class="sxs-lookup"><span data-stu-id="ad533-107">1101</span></span>|  
|<span data-ttu-id="ad533-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="ad533-108">Event Source</span></span>|<span data-ttu-id="ad533-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ad533-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ad533-110">Composant</span><span class="sxs-lookup"><span data-stu-id="ad533-110">Component</span></span>|<span data-ttu-id="ad533-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ad533-111">SQLEngine</span></span>|  
|<span data-ttu-id="ad533-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="ad533-112">Symbolic Name</span></span>|<span data-ttu-id="ad533-113">NOALLOCPG</span><span class="sxs-lookup"><span data-stu-id="ad533-113">NOALLOCPG</span></span>|  
|<span data-ttu-id="ad533-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="ad533-114">Message Text</span></span>|<span data-ttu-id="ad533-115">Impossible d’allouer une nouvelle page pour la base de données ’%.\*ls’ en raison d’un espace disque insuffisant dans le groupe de fichiers ’%.\*ls’.</span><span class="sxs-lookup"><span data-stu-id="ad533-115">Could not allocate a new page for database '%.\*ls' because of insufficient disk space in filegroup '%.\*ls'.</span></span> <span data-ttu-id="ad533-116">Créez l'espace nécessaire en supprimant des objets dans le groupe de fichiers, en ajoutant des fichiers supplémentaires au groupe de fichiers ou en définissant Autogrowth à ON pour les fichiers existants dans le groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="ad533-116">Create the necessary space by dropping objects in the filegroup, adding additional files to the filegroup, or setting autogrowth on for existing files in the filegroup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ad533-117">Explication</span><span class="sxs-lookup"><span data-stu-id="ad533-117">Explanation</span></span>  
 <span data-ttu-id="ad533-118">Il n’y a pas d’espace disque disponible dans un groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="ad533-118">No disk space available in a filegroup.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ad533-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="ad533-119">User Action</span></span>  
 <span data-ttu-id="ad533-120">Les actions ci-dessous peuvent éventuellement créer de l'espace disponible dans le groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="ad533-120">The following actions may make space available in the filegroup.</span></span>  
  
-   <span data-ttu-id="ad533-121">Activez la croissance automatique.</span><span class="sxs-lookup"><span data-stu-id="ad533-121">Turn on AUTOGROW.</span></span>  
  
-   <span data-ttu-id="ad533-122">Ajoutez d'autres fichiers au groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="ad533-122">Add more files to the file group.</span></span>  
  
-   <span data-ttu-id="ad533-123">Libérez de l'espace disque en supprimant les index ou les tables inutiles dans le groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="ad533-123">Free up disk space by dropping unnecessary indexes or tables in the filegroup.</span></span>  
  
  
