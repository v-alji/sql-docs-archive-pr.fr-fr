---
title: LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: c178a308-8d99-47fc-8a49-5a480dc592f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 32ae8ebe102008d08a6059328ed57cd118ece019
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614085"
---
# <a name="localdb_error_instance_folder_path_too_long"></a><span data-ttu-id="82286-102">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="82286-102">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>
    
## <a name="details"></a><span data-ttu-id="82286-103">Détails</span><span class="sxs-lookup"><span data-stu-id="82286-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="82286-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="82286-104">Product Name</span></span>|<span data-ttu-id="82286-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="82286-105">SQL Server</span></span>|  
|<span data-ttu-id="82286-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="82286-106">Event ID</span></span>|<span data-ttu-id="82286-107">260</span><span class="sxs-lookup"><span data-stu-id="82286-107">260</span></span>|  
|<span data-ttu-id="82286-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="82286-108">Event Source</span></span>|<span data-ttu-id="82286-109">Runtime de base de données locale SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="82286-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="82286-110">Composant</span><span class="sxs-lookup"><span data-stu-id="82286-110">Component</span></span>|<span data-ttu-id="82286-111">API d'exécution de la base de données locale</span><span class="sxs-lookup"><span data-stu-id="82286-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="82286-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="82286-112">Message Text</span></span>|<span data-ttu-id="82286-113">Le chemin complet du dossier d'instance de base de données locale est plus long que MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="82286-113">The full path length of the Local Database instance folder is longer than MAX_PATH.</span></span> <span data-ttu-id="82286-114">L’instance doit être stockée dans le dossier :%% LOCALAPPDATA%% \ Microsoft\Microsoft SQL Server DB\Instances local \\<nom de l’instance \> .</span><span class="sxs-lookup"><span data-stu-id="82286-114">The instance must be stored in folder: %%LOCALAPPDATA%%\Microsoft\Microsoft SQL Server Local DB\Instances\\<instance name\>.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="82286-115">Explication</span><span class="sxs-lookup"><span data-stu-id="82286-115">Explanation</span></span>  
 <span data-ttu-id="82286-116">Le chemin d'accès où l'instance doit être stockée est plus long que MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="82286-116">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="82286-117">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="82286-117">User Action</span></span>  
 <span data-ttu-id="82286-118">Créez un nouveau chemin d'accès plus court que MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="82286-118">Create a new path that is shorter than MAX_PATH.</span></span>  
  
  
