---
title: MSSQLSERVER_5515 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5515 (Database Engine error)
ms.assetid: ccd793bc-ba5d-4782-8d72-731fd01fc177
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 74df4571deba596a30a6dd3bd4c186bed03163e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610680"
---
# <a name="mssqlserver_5515"></a><span data-ttu-id="bb62b-102">MSSQLSERVER_5515</span><span class="sxs-lookup"><span data-stu-id="bb62b-102">MSSQLSERVER_5515</span></span>
    
## <a name="details"></a><span data-ttu-id="bb62b-103">Détails</span><span class="sxs-lookup"><span data-stu-id="bb62b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bb62b-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="bb62b-104">Product Name</span></span>|<span data-ttu-id="bb62b-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bb62b-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bb62b-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="bb62b-106">Event ID</span></span>|<span data-ttu-id="bb62b-107">5515</span><span class="sxs-lookup"><span data-stu-id="bb62b-107">5515</span></span>|  
|<span data-ttu-id="bb62b-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="bb62b-108">Event Source</span></span>|<span data-ttu-id="bb62b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bb62b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bb62b-110">Composant</span><span class="sxs-lookup"><span data-stu-id="bb62b-110">Component</span></span>|<span data-ttu-id="bb62b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bb62b-111">SQLEngine</span></span>|  
|<span data-ttu-id="bb62b-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="bb62b-112">Symbolic Name</span></span>|<span data-ttu-id="bb62b-113">FS_OPEN_CONTAINER_FAILED</span><span class="sxs-lookup"><span data-stu-id="bb62b-113">FS_OPEN_CONTAINER_FAILED</span></span>|  
|<span data-ttu-id="bb62b-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="bb62b-114">Message Text</span></span>|<span data-ttu-id="bb62b-115">Impossible d'ouvrir le répertoire conteneur « %.\*ls » du fichier FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="bb62b-115">Container directory ''%.\*ls'' of the FILESTREAM file cannot be opened.</span></span> <span data-ttu-id="bb62b-116">Le système d'exploitation a retourné le code d'état Windows 0x%x.</span><span class="sxs-lookup"><span data-stu-id="bb62b-116">The operating system has returned the Windows status code 0x%x.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bb62b-117">Explication</span><span class="sxs-lookup"><span data-stu-id="bb62b-117">Explanation</span></span>  
 <span data-ttu-id="bb62b-118">Le répertoire conteneur spécifié pour le fichier FILESTREAM ne peut pas être ouvert.</span><span class="sxs-lookup"><span data-stu-id="bb62b-118">The specified container directory for the FILESTREAM file cannot be opened.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bb62b-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="bb62b-119">User Action</span></span>  
 <span data-ttu-id="bb62b-120">Pour la cause de l'erreur, consultez le code d'état Windows spécifique.</span><span class="sxs-lookup"><span data-stu-id="bb62b-120">For the error cause, see the specific Windows status code.</span></span> <span data-ttu-id="bb62b-121">Pour plus d’informations, consultez le [Centre de support des messages d’erreur et d’événements](https://support.microsoft.com/search?query=events%20and%20errors).</span><span class="sxs-lookup"><span data-stu-id="bb62b-121">For more information, see the [Events and Errors Message Support Center](https://support.microsoft.com/search?query=events%20and%20errors).</span></span>  
  
  
