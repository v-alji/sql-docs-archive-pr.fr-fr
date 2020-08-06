---
title: MSSQLSERVER_12329 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 12329 (Database Engine error)
ms.assetid: 43f90287-36d5-46c2-ac91-a37202dcf6d3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7576e32946ce0a453637273c449bbff20e5b6fac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605494"
---
# <a name="mssqlserver_12329"></a><span data-ttu-id="adece-102">MSSQLSERVER_12329</span><span class="sxs-lookup"><span data-stu-id="adece-102">MSSQLSERVER_12329</span></span>
    
## <a name="details"></a><span data-ttu-id="adece-103">Détails</span><span class="sxs-lookup"><span data-stu-id="adece-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="adece-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="adece-104">Product Name</span></span>|<span data-ttu-id="adece-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="adece-105">SQL Server</span></span>|  
|<span data-ttu-id="adece-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="adece-106">Event ID</span></span>|<span data-ttu-id="adece-107">12329</span><span class="sxs-lookup"><span data-stu-id="adece-107">12329</span></span>|  
|<span data-ttu-id="adece-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="adece-108">Event Source</span></span>|<span data-ttu-id="adece-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="adece-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="adece-110">Composant</span><span class="sxs-lookup"><span data-stu-id="adece-110">Component</span></span>|<span data-ttu-id="adece-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="adece-111">SQLEngine</span></span>|  
|<span data-ttu-id="adece-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="adece-112">Symbolic Name</span></span>|<span data-ttu-id="adece-113">HK_UNSUPPORTED_NON_LATIN_CODEPAGE</span><span class="sxs-lookup"><span data-stu-id="adece-113">HK_UNSUPPORTED_NON_LATIN_CODEPAGE</span></span>|  
|<span data-ttu-id="adece-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="adece-114">Message Text</span></span>|<span data-ttu-id="adece-115">Les types de données char(n) et varchar(n) qui utilisent un classement avec une page de codes différente de 1252 ne sont pas pris en charge par *construction*.</span><span class="sxs-lookup"><span data-stu-id="adece-115">The data types char(n) and varchar(n) using a collation that has a code page other than 1252 are not supported with  *construct*.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="adece-116">Explication</span><span class="sxs-lookup"><span data-stu-id="adece-116">Explanation</span></span>  
 <span data-ttu-id="adece-117">N'utilisez pas les types de données char(n) et varchar(n) qui utilisent un classement avec une page de codes différente de 1252.</span><span class="sxs-lookup"><span data-stu-id="adece-117">Do not use the data types char(n) and varchar(n) using a collation that has a code page other than 1252.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="adece-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="adece-118">User Action</span></span>  
 <span data-ttu-id="adece-119">Une situation inattendue pouvant générer cette erreur est :</span><span class="sxs-lookup"><span data-stu-id="adece-119">One unexpected situation that can generate this error is:</span></span>  
  
```  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = 'us_english')  
```  
  
 <span data-ttu-id="adece-120">Utilisez ceci à la place :</span><span class="sxs-lookup"><span data-stu-id="adece-120">Use this instead:</span></span>  
  
```  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
```  
  
  
