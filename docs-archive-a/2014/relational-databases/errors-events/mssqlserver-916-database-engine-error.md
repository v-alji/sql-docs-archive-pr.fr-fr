---
title: MSSQLSERVER_916 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 916 (Database Engine error)
ms.assetid: 73eb6581-99fe-49a5-9b42-e239d7ffe27f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ee67c1e2f67c3c7903c67082ec3793d9d9820061
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604489"
---
# <a name="mssqlserver_916"></a><span data-ttu-id="f4a88-102">MSSQLSERVER_916</span><span class="sxs-lookup"><span data-stu-id="f4a88-102">MSSQLSERVER_916</span></span>
    
## <a name="details"></a><span data-ttu-id="f4a88-103">Détails</span><span class="sxs-lookup"><span data-stu-id="f4a88-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f4a88-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="f4a88-104">Product Name</span></span>|<span data-ttu-id="f4a88-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f4a88-105">SQL Server</span></span>|  
|<span data-ttu-id="f4a88-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="f4a88-106">Event ID</span></span>|<span data-ttu-id="f4a88-107">916</span><span class="sxs-lookup"><span data-stu-id="f4a88-107">916</span></span>|  
|<span data-ttu-id="f4a88-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="f4a88-108">Event Source</span></span>|<span data-ttu-id="f4a88-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f4a88-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f4a88-110">Composant</span><span class="sxs-lookup"><span data-stu-id="f4a88-110">Component</span></span>|<span data-ttu-id="f4a88-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f4a88-111">SQLEngine</span></span>|  
|<span data-ttu-id="f4a88-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="f4a88-112">Symbolic Name</span></span>|<span data-ttu-id="f4a88-113">NOTUSER</span><span class="sxs-lookup"><span data-stu-id="f4a88-113">NOTUSER</span></span>|  
|<span data-ttu-id="f4a88-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="f4a88-114">Message Text</span></span>|<span data-ttu-id="f4a88-115">Le principal de serveur « %.\*ls » ne peut pas accéder à la base de données « %.\*ls » dans le contexte de sécurité actuel.</span><span class="sxs-lookup"><span data-stu-id="f4a88-115">The server principal "%.\*ls" is not able to access the database "%.\*ls" under the current security context.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f4a88-116">Explication</span><span class="sxs-lookup"><span data-stu-id="f4a88-116">Explanation</span></span>  
 <span data-ttu-id="f4a88-117">La connexion n'a pas les autorisations suffisantes pour se connecter à la base de données nommée.</span><span class="sxs-lookup"><span data-stu-id="f4a88-117">The login does not have sufficient permissions to connect to the named database.</span></span> <span data-ttu-id="f4a88-118">Les connexions qui peuvent se connecter à cette instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mais ne disposent pas d'autorisations spécifiques dans une base de données reçoivent les autorisations de l'utilisateur invité.</span><span class="sxs-lookup"><span data-stu-id="f4a88-118">Logins that can connect to this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] but that do not have specific permissions in a database receive the permissions of the guest user.</span></span> <span data-ttu-id="f4a88-119">Il s'agit d'une mesure de sécurité pour empêcher les utilisateurs d'une base de données de se connecter à d'autres bases de données où ils n'ont pas de privilèges.</span><span class="sxs-lookup"><span data-stu-id="f4a88-119">This is a security measure to prevent users in one database from connecting to other databases where they do not have privileges.</span></span> <span data-ttu-id="f4a88-120">Ce message d'erreur peut se produire lorsque l'utilisateur invité n'a pas l'autorisation CONNECT à la base de données nommée et la propriété TRUSTWORTHY n'est pas définie.</span><span class="sxs-lookup"><span data-stu-id="f4a88-120">This error message can occur when the guest user does not have CONNECT permission to the named database and the trustworthy property is not set.</span></span> <span data-ttu-id="f4a88-121">Ce message d'erreur peut se produire lorsque l'utilisateur invité n'a pas l'autorisation CONNECT à la base de données nommée.</span><span class="sxs-lookup"><span data-stu-id="f4a88-121">This error message can occur when the guest user does not have CONNECT permission to the named database.</span></span>  
  
 <span data-ttu-id="f4a88-122">Quand l’autorisation CONNECT à la base de données msdb est refusée ou révoquée, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] peut recevoir cette erreur quand l’Explorateur d’objets essaie d’afficher l’état de la gestion basée sur des stratégies de chaque base de données.</span><span class="sxs-lookup"><span data-stu-id="f4a88-122">When CONNECT permission to the msdb database is denied or revoked, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] can receive this error when Object Explorer tries to show the Policy Based Management status of each database.</span></span> <span data-ttu-id="f4a88-123">L’Explorateur d’objets utilise les autorisations de la connexion actuelle pour interroger la base de données msdb afin d’obtenir ces informations, ce qui provoque l’erreur.</span><span class="sxs-lookup"><span data-stu-id="f4a88-123">Object Explorer uses the permissions of the current login to query the msdb database for this information, which causes the error.</span></span> <span data-ttu-id="f4a88-124">Le message d'erreur suivant est également généré :</span><span class="sxs-lookup"><span data-stu-id="f4a88-124">The following error message also occurs:</span></span>  
  
 <span data-ttu-id="f4a88-125">Échec de la récupération de données pour cette demande.</span><span class="sxs-lookup"><span data-stu-id="f4a88-125">Failed to retrieve data for this request.</span></span> <span data-ttu-id="f4a88-126">(Microsoft.SqlServer.Management.Sdk.Sfc)</span><span class="sxs-lookup"><span data-stu-id="f4a88-126">(Microsoft.SqlServer.Management.Sdk.Sfc)</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f4a88-127">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="f4a88-127">User Action</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="f4a88-128">Avant de contourner cette mesure de sécurité vous devez avoir une vision claire des utilisateurs authentifiés dans diverses bases de données.</span><span class="sxs-lookup"><span data-stu-id="f4a88-128">Before circumventing this security measure be sure to have a clear understanding of users are authenticated in various databases.</span></span> <span data-ttu-id="f4a88-129">Les méthodes suivantes peuvent autoriser les utilisateurs qui ont des autorisations dans une base de données à se connecter à d'autres bases de données qui pourraient exposer des données à un utilisateur malveillant.</span><span class="sxs-lookup"><span data-stu-id="f4a88-129">The following methods may allow users that have permissions in one database to connect to other databases which could expose data to a malicious user.</span></span> <span data-ttu-id="f4a88-130">Lorsque des bases de données autonomes sont activées, les étapes suivantes peuvent permettre à des propriétaires de base de données dans une base de données d'octroyer l'accès à une autre base de données sur l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4a88-130">When contained databases are enabled, the following steps can allow database owners in one database to grant access to other database on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="f4a88-131">Vous pouvez vous connecter à la base de données de l'une des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="f4a88-131">You can connect to the database in one of the following ways:</span></span>  
  
-   <span data-ttu-id="f4a88-132">Accordez l'accès de connexion spécifique à la base de données nommée.</span><span class="sxs-lookup"><span data-stu-id="f4a88-132">Grant the specific login access to the named database.</span></span> <span data-ttu-id="f4a88-133">Dans l'exemple ci-dessous, la connexion `Adventure-Works\Larry` se voit accorder l'accès à la base de données `msdb`.</span><span class="sxs-lookup"><span data-stu-id="f4a88-133">The following example grants the login `Adventure-Works\Larry` access to the `msdb` database.</span></span>  
  
     <span data-ttu-id="f4a88-134">USE msdb ;</span><span class="sxs-lookup"><span data-stu-id="f4a88-134">USE msdb ;</span></span>  
  
     <span data-ttu-id="f4a88-135">GO</span><span class="sxs-lookup"><span data-stu-id="f4a88-135">GO</span></span>  
  
     <span data-ttu-id="f4a88-136">GRANT CONNECT TO [Adventure-Works\Larry] ;</span><span class="sxs-lookup"><span data-stu-id="f4a88-136">GRANT CONNECT TO [Adventure-Works\Larry] ;</span></span>  
  
-   <span data-ttu-id="f4a88-137">Accordez l'autorisation CONNECT à la base de données nommée dans le message d'erreur pour l'utilisateur invité.</span><span class="sxs-lookup"><span data-stu-id="f4a88-137">Grant the CONNECT permission to the database named in the error message for the guest user.</span></span> <span data-ttu-id="f4a88-138">Dans l'exemple ci-dessous, l'autorisation `CONNECT` sur la base de données `msdb` est accordée à l'utilisateur `guest`.</span><span class="sxs-lookup"><span data-stu-id="f4a88-138">The following example grants the `CONNECT` permission to the `msdb` database for the user `guest`.</span></span>  
  
     <span data-ttu-id="f4a88-139">USE msdb ;</span><span class="sxs-lookup"><span data-stu-id="f4a88-139">USE msdb ;</span></span>  
  
     <span data-ttu-id="f4a88-140">GO</span><span class="sxs-lookup"><span data-stu-id="f4a88-140">GO</span></span>  
  
     <span data-ttu-id="f4a88-141">GRANT CONNECT TO guest ;</span><span class="sxs-lookup"><span data-stu-id="f4a88-141">GRANT CONNECT TO guest ;</span></span>  
  
-   <span data-ttu-id="f4a88-142">Activez la propriété TRUSTWORTHY sur la base de données qui a authentifié l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f4a88-142">Enable the TRUSTWORTHY property on the database that has authenticated the user.</span></span>  
  
     `ALTER DATABASE AdventureWorks SET TRUSTWORTHY ON;`  
  
  
