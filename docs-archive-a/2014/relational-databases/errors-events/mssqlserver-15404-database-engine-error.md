---
title: MSSQLSERVER_15404 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 15404 (Database Engine error)
ms.assetid: 69677f02-bc81-4e4a-99b8-5c1bd1de36df
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: beb854c866256728574e06f8c9efb50fb354e15a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612902"
---
# <a name="mssqlserver_15404"></a><span data-ttu-id="c408e-102">MSSQLSERVER_15404</span><span class="sxs-lookup"><span data-stu-id="c408e-102">MSSQLSERVER_15404</span></span>
    
## <a name="details"></a><span data-ttu-id="c408e-103">Détails</span><span class="sxs-lookup"><span data-stu-id="c408e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c408e-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="c408e-104">Product Name</span></span>|<span data-ttu-id="c408e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c408e-105">SQL Server</span></span>|  
|<span data-ttu-id="c408e-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="c408e-106">Event ID</span></span>|<span data-ttu-id="c408e-107">15404</span><span class="sxs-lookup"><span data-stu-id="c408e-107">15404</span></span>|  
|<span data-ttu-id="c408e-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="c408e-108">Event Source</span></span>|<span data-ttu-id="c408e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c408e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c408e-110">Composant</span><span class="sxs-lookup"><span data-stu-id="c408e-110">Component</span></span>|<span data-ttu-id="c408e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c408e-111">SQLEngine</span></span>|  
|<span data-ttu-id="c408e-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="c408e-112">Symbolic Name</span></span>|<span data-ttu-id="c408e-113">SEC_NTGRP_ERROR</span><span class="sxs-lookup"><span data-stu-id="c408e-113">SEC_NTGRP_ERROR</span></span>|  
|<span data-ttu-id="c408e-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="c408e-114">Message Text</span></span>|<span data-ttu-id="c408e-115">Impossible d’obtenir des informations sur l’utilisateur ou le groupe ’*utilisateur*’, code d’erreur *code*.</span><span class="sxs-lookup"><span data-stu-id="c408e-115">Could not obtain information about Windows NT group/user '*user*', error code *code*.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c408e-116">Explication</span><span class="sxs-lookup"><span data-stu-id="c408e-116">Explanation</span></span>  
 <span data-ttu-id="c408e-117">15404 est utilisé dans l'authentification lorsqu'un principal non valide est spécifié.</span><span class="sxs-lookup"><span data-stu-id="c408e-117">15404 is used in authentication when an invalid principal is specified.</span></span> <span data-ttu-id="c408e-118">Sinon, l'emprunt d'identité d'un compte Windows échoue car il n'existe aucune relation de confiance totale entre le compte de service de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et le domaine du compte Windows.</span><span class="sxs-lookup"><span data-stu-id="c408e-118">Or, impersonation of a Windows account fails because there is no full trust relationship between the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and the domain of the Windows account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c408e-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="c408e-119">User Action</span></span>  
 <span data-ttu-id="c408e-120">Vérifiez que le principal Windows existe et qu'il est orthographié correctement.</span><span class="sxs-lookup"><span data-stu-id="c408e-120">Check that the Windows principal exists and is not misspelled.</span></span>  
  
 <span data-ttu-id="c408e-121">Si cette erreur est due à un échec d'une relation de confiance totale entre le compte de service de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et le domaine du compte Windows, une des actions suivantes peut résoudre l'erreur :</span><span class="sxs-lookup"><span data-stu-id="c408e-121">If this error is the result of a lack of a full trust relationship between the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and the domain of the Windows account, one of the following actions can resolve the error:</span></span>  
  
-   <span data-ttu-id="c408e-122">Utilisez un compte du même domaine que l'utilisateur Windows pour le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c408e-122">Use an account from the same domain as the Windows user for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
-   <span data-ttu-id="c408e-123">Si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilise un compte d'ordinateur tel que Service réseau ou Système local, l'ordinateur doit être approuvé par le domaine contenant l'utilisateur Windows.</span><span class="sxs-lookup"><span data-stu-id="c408e-123">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is using a machine account such as Network Service or Local System, the machine must be trusted by the domain containing the Windows User.</span></span>  
  
-   <span data-ttu-id="c408e-124">Utilisez un compte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c408e-124">Use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
  
