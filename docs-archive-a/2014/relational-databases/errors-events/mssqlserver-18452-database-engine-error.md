---
title: MSSQLSERVER_18452 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 18456 (Database Engine error)
- 18452 (Database Engine error)
ms.assetid: 21da332c-e81d-4dee-a9d2-95598911b3be
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5786d5de4748f6bbf59d2bd4acecd7ca77977f11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611101"
---
# <a name="mssqlserver_18452"></a><span data-ttu-id="8ef18-102">MSSQLSERVER_18452</span><span class="sxs-lookup"><span data-stu-id="8ef18-102">MSSQLSERVER_18452</span></span>
    
## <a name="details"></a><span data-ttu-id="8ef18-103">Détails</span><span class="sxs-lookup"><span data-stu-id="8ef18-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8ef18-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="8ef18-104">Product Name</span></span>|<span data-ttu-id="8ef18-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8ef18-105">SQL Server</span></span>|  
|<span data-ttu-id="8ef18-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="8ef18-106">Event ID</span></span>|<span data-ttu-id="8ef18-107">18452</span><span class="sxs-lookup"><span data-stu-id="8ef18-107">18452</span></span>|  
|<span data-ttu-id="8ef18-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="8ef18-108">Event Source</span></span>|<span data-ttu-id="8ef18-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8ef18-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8ef18-110">Composant</span><span class="sxs-lookup"><span data-stu-id="8ef18-110">Component</span></span>|<span data-ttu-id="8ef18-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8ef18-111">SQLEngine</span></span>|  
|<span data-ttu-id="8ef18-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="8ef18-112">Symbolic Name</span></span>|<span data-ttu-id="8ef18-113">LOGON_INVALID_CONNECT</span><span class="sxs-lookup"><span data-stu-id="8ef18-113">LOGON_INVALID_CONNECT</span></span>|  
|<span data-ttu-id="8ef18-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="8ef18-114">Message Text</span></span>|<span data-ttu-id="8ef18-115">Échec de l'ouverture de session pour l'utilisateur '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="8ef18-115">Login failed for user '%.\*ls'.</span></span> <span data-ttu-id="8ef18-116">Il s’agit d’un compte de connexion SQL Server, qui ne peut pas être utilisé avec l’authentification Windows.%.\*ls.</span><span class="sxs-lookup"><span data-stu-id="8ef18-116">The login is a SQL Server login and cannot be used with Windows Authentication.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8ef18-117">Explication</span><span class="sxs-lookup"><span data-stu-id="8ef18-117">Explanation</span></span>  
 <span data-ttu-id="8ef18-118">L'utilisateur a essayé de se connecter à l'aide d'informations d'identification qui ne peuvent pas être validées.</span><span class="sxs-lookup"><span data-stu-id="8ef18-118">The user attempted to login with credentials that cannot be validated.</span></span> <span data-ttu-id="8ef18-119">Les causes possibles sont :</span><span class="sxs-lookup"><span data-stu-id="8ef18-119">Possible causes are:</span></span>  
  
-   <span data-ttu-id="8ef18-120">La connexion peut être une connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mais le serveur accepte uniquement l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="8ef18-120">The login may be a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login but the server only accepts Windows Authentication.</span></span>  
  
-   <span data-ttu-id="8ef18-121">Vous essayez de vous connecter à l'aide de l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mais la connexion utilisée n'existe pas sur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ef18-121">You are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication but the login used does not exist on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="8ef18-122">La connexion peut utiliser l'authentification Windows mais elle constitue un principal Windows non reconnu.</span><span class="sxs-lookup"><span data-stu-id="8ef18-122">The login may use Windows Authentication but the login is an unrecognized Windows principal.</span></span> <span data-ttu-id="8ef18-123">Un principal Windows non reconnu signifie que la connexion ne peut pas être vérifiée par Windows.</span><span class="sxs-lookup"><span data-stu-id="8ef18-123">An unrecognized Windows principal means that the login cannot be verified by Windows.</span></span> <span data-ttu-id="8ef18-124">Cela peut être dû au fait que la connexion Windows s'effectue à partir d'un domaine non approuvé.</span><span class="sxs-lookup"><span data-stu-id="8ef18-124">This could be because the Windows login is from an untrusted domain.</span></span>  
  
 <span data-ttu-id="8ef18-125">Des problèmes similaires peuvent provoquer l'erreur 18456 moins spécifique.</span><span class="sxs-lookup"><span data-stu-id="8ef18-125">Similar problems can cause the less-specific error 18456.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8ef18-126">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="8ef18-126">User Action</span></span>  
 <span data-ttu-id="8ef18-127">Si vous essayez de vous connecter à l'aide de l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vérifiez que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est configuré en mode Authentification mixte.</span><span class="sxs-lookup"><span data-stu-id="8ef18-127">If you are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, verify that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured in Mixed Authentication Mode.</span></span>  
  
 <span data-ttu-id="8ef18-128">Si vous essayez de vous connecter à l'aide de l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vérifiez que la connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] existe.</span><span class="sxs-lookup"><span data-stu-id="8ef18-128">If you are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, verify that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login exists.</span></span>  
  
 <span data-ttu-id="8ef18-129">Si vous essayez de vous connecter à l'aide de l'authentification Windows, vérifiez que vous êtes correctement connecté au domaine approprié.</span><span class="sxs-lookup"><span data-stu-id="8ef18-129">If you are trying to connect using Windows Authentication, verify that you are properly logged into the correct domain.</span></span>  
  
  
