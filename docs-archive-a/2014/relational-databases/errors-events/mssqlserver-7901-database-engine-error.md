---
title: MSSQLSERVER_7901 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7901 (Database Engine error)
ms.assetid: 2d0d19b9-947b-4474-9ff8-7e03019ab93d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fae6e55cbe7170f795aff85400da2c5cdaef780a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605461"
---
# <a name="mssqlserver_7901"></a><span data-ttu-id="98b4a-102">MSSQLSERVER_7901</span><span class="sxs-lookup"><span data-stu-id="98b4a-102">MSSQLSERVER_7901</span></span>
    
## <a name="details"></a><span data-ttu-id="98b4a-103">Détails</span><span class="sxs-lookup"><span data-stu-id="98b4a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="98b4a-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="98b4a-104">Product Name</span></span>|<span data-ttu-id="98b4a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="98b4a-105">SQL Server</span></span>|  
|<span data-ttu-id="98b4a-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="98b4a-106">Event ID</span></span>|<span data-ttu-id="98b4a-107">7901</span><span class="sxs-lookup"><span data-stu-id="98b4a-107">7901</span></span>|  
|<span data-ttu-id="98b4a-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="98b4a-108">Event Source</span></span>|<span data-ttu-id="98b4a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="98b4a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="98b4a-110">Composant</span><span class="sxs-lookup"><span data-stu-id="98b4a-110">Component</span></span>|<span data-ttu-id="98b4a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="98b4a-111">SQLEngine</span></span>|  
|<span data-ttu-id="98b4a-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="98b4a-112">Symbolic Name</span></span>|<span data-ttu-id="98b4a-113">DBCC2_DATABASE_IN_EMERGENCY_MODE</span><span class="sxs-lookup"><span data-stu-id="98b4a-113">DBCC2_DATABASE_IN_EMERGENCY_MODE</span></span>|  
|<span data-ttu-id="98b4a-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="98b4a-114">Message Text</span></span>|<span data-ttu-id="98b4a-115">L’instruction de réparation n’a pas été traitée.</span><span class="sxs-lookup"><span data-stu-id="98b4a-115">The repair statement was not processed.</span></span> <span data-ttu-id="98b4a-116">Ce niveau de réparation n'est pas pris en charge lorsque la base de données est en mode d'urgence.</span><span class="sxs-lookup"><span data-stu-id="98b4a-116">This level of repair is not supported when the database is in emergency mode.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="98b4a-117">Explication</span><span class="sxs-lookup"><span data-stu-id="98b4a-117">Explanation</span></span>  
 <span data-ttu-id="98b4a-118">La base de données est en mode d'urgence et un niveau de réparation autre que REPAIR_ALLOW_DATA_LOSS a été spécifié.</span><span class="sxs-lookup"><span data-stu-id="98b4a-118">The database is in emergency mode and a repair level other than REPAIR_ALLOW_DATA_LOSS has been specified.</span></span> <span data-ttu-id="98b4a-119">Les réparations ne peuvent pas être effectuées en mode d'urgence si REPAIR_ALLOW_DATA_LOSS n'est pas spécifié.</span><span class="sxs-lookup"><span data-stu-id="98b4a-119">Repairs cannot be made in emergency mode unless REPAIR_ALLOW_DATA_LOSS is specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="98b4a-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="98b4a-120">User Action</span></span>  
 <span data-ttu-id="98b4a-121">Exécutez de nouveau la commande et spécifiez l'option REPAIR_ALLOW_DATA_LOSS.</span><span class="sxs-lookup"><span data-stu-id="98b4a-121">Rerun the command and specify the REPAIR_ALLOW_DATA_LOSS option.</span></span>  
  
  
