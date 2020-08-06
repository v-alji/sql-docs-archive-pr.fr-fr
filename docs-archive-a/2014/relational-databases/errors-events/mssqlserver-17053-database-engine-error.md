---
title: MSSQLSERVER_17053 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17053 (Database Engine error)
ms.assetid: e0a01f3d-d0aa-4c38-8bcc-82e59de50512
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 11137ba334b66f20c7d9a6caaaf7d1ef42c15dec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600053"
---
# <a name="mssqlserver_17053"></a><span data-ttu-id="f2c1b-102">MSSQLSERVER_17053</span><span class="sxs-lookup"><span data-stu-id="f2c1b-102">MSSQLSERVER_17053</span></span>
    
## <a name="details"></a><span data-ttu-id="f2c1b-103">Détails</span><span class="sxs-lookup"><span data-stu-id="f2c1b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f2c1b-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="f2c1b-104">Product Name</span></span>|<span data-ttu-id="f2c1b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f2c1b-105">SQL Server</span></span>|  
|<span data-ttu-id="f2c1b-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="f2c1b-106">Event ID</span></span>|<span data-ttu-id="f2c1b-107">17053</span><span class="sxs-lookup"><span data-stu-id="f2c1b-107">17053</span></span>|  
|<span data-ttu-id="f2c1b-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="f2c1b-108">Event Source</span></span>|<span data-ttu-id="f2c1b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f2c1b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f2c1b-110">Composant</span><span class="sxs-lookup"><span data-stu-id="f2c1b-110">Component</span></span>|<span data-ttu-id="f2c1b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f2c1b-111">SQLEngine</span></span>|  
|<span data-ttu-id="f2c1b-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="f2c1b-112">Symbolic Name</span></span>|<span data-ttu-id="f2c1b-113">OS_ERROR</span><span class="sxs-lookup"><span data-stu-id="f2c1b-113">OS_ERROR</span></span>|  
|<span data-ttu-id="f2c1b-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="f2c1b-114">Message Text</span></span>|<span data-ttu-id="f2c1b-115">%ls : Erreur système %ls.</span><span class="sxs-lookup"><span data-stu-id="f2c1b-115">%ls: Operating system error %ls encountered.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f2c1b-116">Explication</span><span class="sxs-lookup"><span data-stu-id="f2c1b-116">Explanation</span></span>  
 <span data-ttu-id="f2c1b-117">Une erreur générique du système d'exploitation s'est produite.</span><span class="sxs-lookup"><span data-stu-id="f2c1b-117">Generic operating system error occurred.</span></span>  <span data-ttu-id="f2c1b-118">L'état résultant est indéfini.</span><span class="sxs-lookup"><span data-stu-id="f2c1b-118">Not clear what the resulting state is.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f2c1b-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="f2c1b-119">User Action</span></span>  
 <span data-ttu-id="f2c1b-120">Habituellement cette erreur apparaît conjointement avec une autre erreur et doit servir à diagnostiquer cet échec.</span><span class="sxs-lookup"><span data-stu-id="f2c1b-120">Usually this is in conjunction with some other error and should be used to help diagnose that failure.</span></span> <span data-ttu-id="f2c1b-121">Les exemples peuvent inclure des échecs de lecture ou d'écriture des données ou des fichiers journaux, des opérations en lecture/écriture du Registre, ou d'autres échecs Win32API inattendus.</span><span class="sxs-lookup"><span data-stu-id="f2c1b-121">Examples would include reads or writes to data or log files that fail, registry read/write operations, or other unexpected Win32API failures.</span></span>  
  
  
