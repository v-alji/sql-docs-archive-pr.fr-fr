---
title: MSSQLSERVER_1803 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1803 (Database Engine error)
ms.assetid: d4315390-82f1-4c4c-8d1b-1a4989537cca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 11302f882846c49c6e9998608967e7042ac9860c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611108"
---
# <a name="mssqlserver_1803"></a><span data-ttu-id="6b36f-102">MSSQLSERVER_1803</span><span class="sxs-lookup"><span data-stu-id="6b36f-102">MSSQLSERVER_1803</span></span>
    
## <a name="details"></a><span data-ttu-id="6b36f-103">Détails</span><span class="sxs-lookup"><span data-stu-id="6b36f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6b36f-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="6b36f-104">Product Name</span></span>|<span data-ttu-id="6b36f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6b36f-105">SQL Server</span></span>|  
|<span data-ttu-id="6b36f-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="6b36f-106">Event ID</span></span>|<span data-ttu-id="6b36f-107">1803</span><span class="sxs-lookup"><span data-stu-id="6b36f-107">1803</span></span>|  
|<span data-ttu-id="6b36f-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="6b36f-108">Event Source</span></span>|<span data-ttu-id="6b36f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6b36f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6b36f-110">Composant</span><span class="sxs-lookup"><span data-stu-id="6b36f-110">Component</span></span>|<span data-ttu-id="6b36f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6b36f-111">SQLEngine</span></span>|  
|<span data-ttu-id="6b36f-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="6b36f-112">Symbolic Name</span></span>|<span data-ttu-id="6b36f-113">NO_SPACE</span><span class="sxs-lookup"><span data-stu-id="6b36f-113">NO_SPACE</span></span>|  
|<span data-ttu-id="6b36f-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="6b36f-114">Message Text</span></span>|<span data-ttu-id="6b36f-115">Échec de CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="6b36f-115">CREATE DATABASE failed.</span></span> <span data-ttu-id="6b36f-116">Le fichier primaire doit être doté d’une capacité minimale de %d Mo pour recevoir une copie de la base de données model.</span><span class="sxs-lookup"><span data-stu-id="6b36f-116">Primary file must be at least %d MB to accommodate a copy of the model database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6b36f-117">Explication</span><span class="sxs-lookup"><span data-stu-id="6b36f-117">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6b36f-118">crée une base de données en effectuant une copie de la base de données model.</span><span class="sxs-lookup"><span data-stu-id="6b36f-118">creates a database by making a copy of the model database.</span></span> <span data-ttu-id="6b36f-119">Ensuite, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] renomme la copie et agrandit la nouvelle base de données à la taille demandée.</span><span class="sxs-lookup"><span data-stu-id="6b36f-119">Then [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] renames the copy, and enlarges the new database to the requested size.</span></span> <span data-ttu-id="6b36f-120">Dans le cas présent, l'utilisateur a essayé de créer une base de données plus petite que la base de données model.</span><span class="sxs-lookup"><span data-stu-id="6b36f-120">In this case, the user tried to create a database smaller than the model database.</span></span> <span data-ttu-id="6b36f-121">L'opération a échoué car la copie de la base de données model ne correspondait pas au fichier de données primaire, parce que le fichier était plus petit que la base de données model.</span><span class="sxs-lookup"><span data-stu-id="6b36f-121">The operation failed because the copy of the model database could not fit on the primary data file, because the file was smaller than the model database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6b36f-122">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="6b36f-122">User Action</span></span>  
 <span data-ttu-id="6b36f-123">Créez la base de données en utilisant une plus grande taille pour le fichier de base de données.</span><span class="sxs-lookup"><span data-stu-id="6b36f-123">Create the database by using a larger database file size.</span></span> <span data-ttu-id="6b36f-124">Réduisez ensuite si vous le souhaitez la base de données en utilisant [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou l'instruction DBCC SHRINKDATABASE.</span><span class="sxs-lookup"><span data-stu-id="6b36f-124">Then shrink the database if you want by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], or the DBCC SHRINKDATABASE statement.</span></span>  
  
  
