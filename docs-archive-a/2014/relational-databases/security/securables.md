---
title: Éléments sécurisables | Microsoft Docs
ms.custom: ''
ms.date: 10/14/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.roleproperties.selectobject.f1
helpviewer_keywords:
- securables [SQL Server]
- schemas [SQL Server], securables
- database securables [SQL Server]
- hierarchies [SQL Server], securables
- server securables [SQL Server]
ms.assetid: bfa748f0-70b0-453c-870a-04b7b205b9ff
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: ff2aaba72e2e5489694d31b35e594622c099acab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697699"
---
# <a name="securables"></a><span data-ttu-id="2df08-102">Éléments sécurisables</span><span class="sxs-lookup"><span data-stu-id="2df08-102">Securables</span></span>
  <span data-ttu-id="2df08-103">Les éléments sécurisables sont les ressources auxquelles le système d'autorisation du moteur de base de données [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] régule l'accès.</span><span class="sxs-lookup"><span data-stu-id="2df08-103">Securables are the resources to which the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] authorization system regulates access.</span></span> <span data-ttu-id="2df08-104">Par exemple, une table est un élément sécurisable.</span><span class="sxs-lookup"><span data-stu-id="2df08-104">For example, a table is a securable.</span></span> <span data-ttu-id="2df08-105">Certains éléments sécurisables peuvent être contenus dans d'autres, de façon à créer des hiérarchies imbriquées appelées « étendues », pouvant elles-mêmes être sécurisées.</span><span class="sxs-lookup"><span data-stu-id="2df08-105">Some securables can be contained within others, creating nested hierarchies called "scopes" that can themselves be secured.</span></span> <span data-ttu-id="2df08-106">L'étendue de ces éléments sécurisables est constituée par le **serveur**, la **base de données**et le **schéma**.</span><span class="sxs-lookup"><span data-stu-id="2df08-106">The securable scopes are **server**, **database**, and **schema**.</span></span>  
  
## <a name="securable-scope-server"></a><span data-ttu-id="2df08-107">Étendue sécurisable : Serveur</span><span class="sxs-lookup"><span data-stu-id="2df08-107">Securable scope: Server</span></span>  
 <span data-ttu-id="2df08-108">Les éléments sécurisables du **serveur** sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="2df08-108">The **server** securable scope contains the following securables:</span></span>  
  
-   <span data-ttu-id="2df08-109">Groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="2df08-109">Availability group</span></span>  
  
-   <span data-ttu-id="2df08-110">Point de terminaison</span><span class="sxs-lookup"><span data-stu-id="2df08-110">Endpoint</span></span>  
  
-   <span data-ttu-id="2df08-111">Connexion</span><span class="sxs-lookup"><span data-stu-id="2df08-111">Login</span></span>  
  
-   <span data-ttu-id="2df08-112">Rôle du serveur</span><span class="sxs-lookup"><span data-stu-id="2df08-112">Server role</span></span>  
  
-   <span data-ttu-id="2df08-113">Base de données</span><span class="sxs-lookup"><span data-stu-id="2df08-113">Database</span></span>  
  
## <a name="securable-scope-database"></a><span data-ttu-id="2df08-114">Étendue sécurisable : Base de données</span><span class="sxs-lookup"><span data-stu-id="2df08-114">Securable scope: Database</span></span>  
 <span data-ttu-id="2df08-115">Les éléments sécurisables de la **base de données** sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="2df08-115">The **database** securable scope contains the following securables:</span></span>  
  
-   <span data-ttu-id="2df08-116">Rôle d'application</span><span class="sxs-lookup"><span data-stu-id="2df08-116">Application role</span></span>  
  
-   <span data-ttu-id="2df08-117">Assembly</span><span class="sxs-lookup"><span data-stu-id="2df08-117">Assembly</span></span>  
  
-   <span data-ttu-id="2df08-118">Clé asymétrique</span><span class="sxs-lookup"><span data-stu-id="2df08-118">Asymmetric key</span></span>  
  
-   <span data-ttu-id="2df08-119">Certificat</span><span class="sxs-lookup"><span data-stu-id="2df08-119">Certificate</span></span>  
  
-   <span data-ttu-id="2df08-120">Contrat</span><span class="sxs-lookup"><span data-stu-id="2df08-120">Contract</span></span>  
  
-   <span data-ttu-id="2df08-121">Catalogue FullText</span><span class="sxs-lookup"><span data-stu-id="2df08-121">Fulltext catalog</span></span>  
  
-   <span data-ttu-id="2df08-122">Liste de mots vides</span><span class="sxs-lookup"><span data-stu-id="2df08-122">Fulltext stoplist</span></span>  
  
-   <span data-ttu-id="2df08-123">type de message</span><span class="sxs-lookup"><span data-stu-id="2df08-123">Message type</span></span>  
  
-   <span data-ttu-id="2df08-124">Liaisons de service distant</span><span class="sxs-lookup"><span data-stu-id="2df08-124">Remote Service Binding</span></span>  
  
-   <span data-ttu-id="2df08-125">Rôle (de base de données)</span><span class="sxs-lookup"><span data-stu-id="2df08-125">(Database) Role</span></span>  
  
-   <span data-ttu-id="2df08-126">Routage</span><span class="sxs-lookup"><span data-stu-id="2df08-126">Route</span></span>  
  
-   <span data-ttu-id="2df08-127">schéma</span><span class="sxs-lookup"><span data-stu-id="2df08-127">Schema</span></span>  
  
-   <span data-ttu-id="2df08-128">Liste des propriétés de recherche</span><span class="sxs-lookup"><span data-stu-id="2df08-128">Search property list</span></span>  
  
-   <span data-ttu-id="2df08-129">Service</span><span class="sxs-lookup"><span data-stu-id="2df08-129">Service</span></span>  
  
-   <span data-ttu-id="2df08-130">Clé symétrique</span><span class="sxs-lookup"><span data-stu-id="2df08-130">Symmetric key</span></span>  
  
-   <span data-ttu-id="2df08-131">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="2df08-131">User</span></span>  
  
## <a name="securable-scope-schema"></a><span data-ttu-id="2df08-132">Étendue sécurisable : schéma</span><span class="sxs-lookup"><span data-stu-id="2df08-132">Securable scope: Schema</span></span>  
 <span data-ttu-id="2df08-133">Les éléments sécurisables du **schéma** sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="2df08-133">The **schema** securable scope contains the following securables:</span></span>  
  
-   <span data-ttu-id="2df08-134">Type</span><span class="sxs-lookup"><span data-stu-id="2df08-134">Type</span></span>  
  
-   <span data-ttu-id="2df08-135">Collection de schémas XML</span><span class="sxs-lookup"><span data-stu-id="2df08-135">XML schema collection</span></span>  
  
-   <span data-ttu-id="2df08-136">Objet - La classe d’objet comprend les membres suivants :</span><span class="sxs-lookup"><span data-stu-id="2df08-136">Object - The object class has the following members:</span></span>  
  
    -   <span data-ttu-id="2df08-137">Agrégat</span><span class="sxs-lookup"><span data-stu-id="2df08-137">Aggregate</span></span>  
  
    -   <span data-ttu-id="2df08-138">Fonction</span><span class="sxs-lookup"><span data-stu-id="2df08-138">Function</span></span>  
  
    -   <span data-ttu-id="2df08-139">Procédure</span><span class="sxs-lookup"><span data-stu-id="2df08-139">Procedure</span></span>  
  
    -   <span data-ttu-id="2df08-140">File d'attente</span><span class="sxs-lookup"><span data-stu-id="2df08-140">Queue</span></span>  
  
    -   <span data-ttu-id="2df08-141">Synonyme</span><span class="sxs-lookup"><span data-stu-id="2df08-141">Synonym</span></span>  
  
    -   <span data-ttu-id="2df08-142">Table de charge de travail</span><span class="sxs-lookup"><span data-stu-id="2df08-142">Table</span></span>  
  
    -   <span data-ttu-id="2df08-143">Affichage</span><span class="sxs-lookup"><span data-stu-id="2df08-143">View</span></span>  
  
## <a name="controlling-access-to-a-securable"></a><span data-ttu-id="2df08-144">Contrôle de l'accès à un élément sécurisable</span><span class="sxs-lookup"><span data-stu-id="2df08-144">Controlling Access to a Securable</span></span>  
 <span data-ttu-id="2df08-145">L'entité qui reçoit l'autorisation d'accéder à un élément sécurisable est appelée « principal ».</span><span class="sxs-lookup"><span data-stu-id="2df08-145">The entity that receives permission to a securable is called a principal.</span></span> <span data-ttu-id="2df08-146">Les principaux les plus courants sont les connexions et les utilisateurs de base de données.</span><span class="sxs-lookup"><span data-stu-id="2df08-146">The most common principals are logins and database users.</span></span> <span data-ttu-id="2df08-147">Vous pouvez contrôler l'accès aux éléments sécurisables en accordant ou en refusant des autorisations, ou en ajoutant des connexions et des utilisateurs aux rôles auxquels ils ont accès.</span><span class="sxs-lookup"><span data-stu-id="2df08-147">Access to securables is controlled by granting or denying permissions, or by adding logins and user to roles which have access.</span></span> <span data-ttu-id="2df08-148">Pour plus d’informations sur le contrôle des autorisations, consultez [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql), [REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql), [DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql), [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql) et [sp_droprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droprolemember-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2df08-148">For information about controlling permissions, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql), [REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql), [DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql), [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql), and [sp_droprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droprolemember-transact-sql).</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="2df08-149">Les autorisations par défaut accordées aux objets système au moment de l'installation sont évaluées avec soin par rapport aux menaces potentielles et ne doivent pas être modifiées dans le cadre du renforcement de l'installation [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2df08-149">The default permissions that are granted to system objects at the time of setup are carefully evaluated against possible threats and need not be altered as part of hardening the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installation.</span></span> <span data-ttu-id="2df08-150">Les modifications apportées aux autorisations sur les objets système peuvent limiter ou rompre le fonctionnement et pourraient potentiellement laisser votre installation [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans un état non pris en charge.</span><span class="sxs-lookup"><span data-stu-id="2df08-150">Any changes to the permissions on the system objects could limit or break the functionality and could potentially leave your [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installation in an unsupported state.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="2df08-151">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="2df08-151">Related Content</span></span>  
 [<span data-ttu-id="2df08-152">Sécurisation de SQL Server</span><span class="sxs-lookup"><span data-stu-id="2df08-152">Securing SQL Server</span></span>](securing-sql-server.md)  
  
 [<span data-ttu-id="2df08-153">sys.database_principals &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2df08-153">sys.database_principals &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-principals-transact-sql)  
  
 [<span data-ttu-id="2df08-154">sys.database_role_members &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2df08-154">sys.database_role_members &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-role-members-transact-sql)  
  
 [<span data-ttu-id="2df08-155">sys.server_principals &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2df08-155">sys.server_principals &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql)  
  
 [<span data-ttu-id="2df08-156">sys.server_role_members &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2df08-156">sys.server_role_members &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-role-members-transact-sql)  
  
 [<span data-ttu-id="2df08-157">sys.sql_logins &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2df08-157">sys.sql_logins &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-logins-transact-sql)  
  
  
