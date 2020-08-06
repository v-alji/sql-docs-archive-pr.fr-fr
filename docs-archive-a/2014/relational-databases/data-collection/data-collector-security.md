---
title: Sécurité du collecteur de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collection [SQL Server]
- security [data collector]
- data collector [SQL Server], security
ms.assetid: e75d6975-641e-440a-a642-cb39a583359a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c89f1658f6ae1b5bd79de96f20222b0b19529df2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602158"
---
# <a name="data-collector-security"></a><span data-ttu-id="bf0e8-102">Sécurité du collecteur de données</span><span class="sxs-lookup"><span data-stu-id="bf0e8-102">Data Collector Security</span></span>
  <span data-ttu-id="bf0e8-103">Le collecteur de données utilise le modèle de sécurité basée sur les rôles implémenté par l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bf0e8-103">The data collector uses the role-based security model implemented by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="bf0e8-104">Ce modèle permet à l'administrateur de base de données d'exécuter les différentes tâches du collecteur de données dans un contexte de sécurité qui ne dispose que des autorisations requises pour effectuer ces tâches.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-104">This model lets the database administrator run the various data collector tasks in a security context that has only the permissions required to perform that task.</span></span> <span data-ttu-id="bf0e8-105">Cette méthode est également utilisée pour les opérations qui impliquent des tables internes, uniquement accessibles à l'aide d'une procédure stockée ou d'une vue.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-105">This approach is also used for operations involving internal tables, which can only be accessed by using a stored procedure or view.</span></span> <span data-ttu-id="bf0e8-106">Aucune autorisation n'est accordée aux tables internes.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-106">No permissions are granted to internal tables.</span></span> <span data-ttu-id="bf0e8-107">En revanche, il est procédé à une vérification des autorisations de l'utilisateur de la procédure stockée ou de la vue utilisée pour accéder à une table.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-107">Instead, permissions are checked on the user of the stored procedure or view that is used to access a table.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bf0e8-108">Les autorisations concentriques constituent un autre aspect clé de ce modèle de sécurité.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-108">Another key aspect of this security model is concentric permissions.</span></span> <span data-ttu-id="bf0e8-109">Dans le cadre des autorisations concentriques, les rôles les plus privilégiés héritent des autorisations des rôles les moins privilégiés sur des objets (notamment les alertes, les opérateurs, les travaux, les planifications et les proxys).</span><span class="sxs-lookup"><span data-stu-id="bf0e8-109">Under concentric permissions, more privileged roles inherit the permissions of less privileged roles on objects (including alerts, operators, jobs, schedules, and proxies).</span></span> <span data-ttu-id="bf0e8-110">Pour plus d'informations, consultez [SQL Server Agent Fixed Database Roles](../../ssms/agent/sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="bf0e8-110">For more information, see [SQL Server Agent Fixed Database Roles](../../ssms/agent/sql-server-agent-fixed-database-roles.md).</span></span>  
  
 <span data-ttu-id="bf0e8-111">Les sections suivantes offrent une description générale de la sécurité de la collecte de données, ainsi que des rôles que vous devez attribuer aux utilisateurs pour qu'ils puissent configurer et utiliser le collecteur de données, et effectuer des tâches associées à l'entrepôt de données de gestion.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-111">The following sections describe data collection security in general, as well as the roles you must grant to users so they can configure and use the data collector, and carry out tasks associated with the management data warehouse.</span></span>  
  
## <a name="general-security"></a><span data-ttu-id="bf0e8-112">Sécurité générale</span><span class="sxs-lookup"><span data-stu-id="bf0e8-112">General Security</span></span>  
 <span data-ttu-id="bf0e8-113">Le collecteur de données est installé en fonction des normes documentées spécifiées pour [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf0e8-113">The data collector is installed according to the documented standards specified for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
### <a name="network-security"></a><span data-ttu-id="bf0e8-114">Sécurité réseau</span><span class="sxs-lookup"><span data-stu-id="bf0e8-114">Network Security</span></span>  
 <span data-ttu-id="bf0e8-115">Des informations sensibles peuvent être transmises entre des instances cibles, l'instance relationnelle associée au serveur de configuration, les jeux d'éléments de collection en cours d'exécution et le serveur hébergeant l'entrepôt de données de gestion.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-115">Sensitive information can be passed between target instances, the relational instance associated with the configuration server, the collection sets that are running, and the server that hosts the management data warehouse.</span></span>  
  
 <span data-ttu-id="bf0e8-116">Pour protéger des données quelconques transférées sur un réseau, les mécanismes de sécurité standard sont implémentés, tels que le chiffrement de protocole pour [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf0e8-116">To protect any data that is transferred over a network, the standard security mechanisms are implemented, such as protocol encryption for [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
## <a name="permissions-for-configuring-and-using-the-data-collector"></a><span data-ttu-id="bf0e8-117">Autorisations de configuration et d'utilisation du collecteur de données</span><span class="sxs-lookup"><span data-stu-id="bf0e8-117">Permissions for Configuring and Using the Data Collector</span></span>  
 <span data-ttu-id="bf0e8-118">En fonction de la tâche, les utilisateurs doivent être membres d'un ou plusieurs des rôles de base de données fixes fournis pour le collecteur de données.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-118">Depending on the task, users must be members of one or more of the fixed database roles provided for the data collector.</span></span> <span data-ttu-id="bf0e8-119">Ces rôles, présentés ici du plus privilégié au moins privilégié en termes d'accès, sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="bf0e8-119">In order of most-privileged to least-privileged access, the roles are as follows:</span></span>  
  
-   `dc_admin`  
  
-   <span data-ttu-id="bf0e8-120">**dc_operator**</span><span class="sxs-lookup"><span data-stu-id="bf0e8-120">**dc_operator**</span></span>  
  
-   <span data-ttu-id="bf0e8-121">**dc_proxy**</span><span class="sxs-lookup"><span data-stu-id="bf0e8-121">**dc_proxy**</span></span>  
  
 <span data-ttu-id="bf0e8-122">Ces rôles sont stockés dans la base de données msdb.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-122">These roles are stored in the msdb database.</span></span> <span data-ttu-id="bf0e8-123">Par défaut, aucun utilisateur n'est membre de ces rôles de base de données.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-123">By default, no user is a member of these database roles.</span></span> <span data-ttu-id="bf0e8-124">L'appartenance d'un utilisateur à ces rôles doit être accordée explicitement.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-124">User membership in these roles must be granted explicitly.</span></span>  
  
 <span data-ttu-id="bf0e8-125">Les utilisateurs qui sont membres du `sysadmin` rôle serveur fixe ont un accès complet aux [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objets de l’agent et aux vues du collecteur de données.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-125">Users who are members of the `sysadmin` fixed server role have full access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent objects and data collector views.</span></span> <span data-ttu-id="bf0e8-126">Ils doivent toutefois être ajoutés explicitement aux rôles de collecteur de données.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-126">However, they need to be explicitly added to data collector roles.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bf0e8-127">Les membres du rôle db_ssisadmin et du rôle dc_admin peuvent être en mesure d'élever leurs privilèges à sysadmin.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-127">Members of the db_ssisadmin role and the dc_admin role may be able to elevate their privileges to sysadmin.</span></span> <span data-ttu-id="bf0e8-128">Cette élévation de privilège peut se produire, car ces rôles peuvent modifier les packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] et les packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] peuvent être exécutés par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l’aide du contexte de sécurité sysadmin de l’Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bf0e8-128">This elevation of privilege can occur because these roles can modify [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages can be executed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the sysadmin security context of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="bf0e8-129">Pour vous prémunir contre cette élévation de privilège lors de l'exécution de plans de maintenance, de jeux d'éléments de collecte de données et d'autres packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , configurez des travaux de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui exécutent des packages pour l'utilisation d'un compte proxy doté de privilèges limités ou ajoutez uniquement des membres sysadmin aux rôles db_ssisadmin et dc_admin.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-129">To guard against this elevation of privilege when running maintenance plans, data collection sets, and other [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs that run packages to use a proxy account with limited privileges or only add sysadmin members to the db_ssisadmin and dc_admin roles.</span></span>  
  
### <a name="dc_admin-role"></a><span data-ttu-id="bf0e8-130">Rôle dc_admin</span><span class="sxs-lookup"><span data-stu-id="bf0e8-130">dc_admin Role</span></span>  
 <span data-ttu-id="bf0e8-131">Les utilisateurs affectés au `dc_admin` rôle disposent d’un accès administrateur complet (création, lecture, mise à jour et suppression) à la configuration du collecteur de données sur une instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-131">Users assigned to the `dc_admin` role have full administrator access (Create, Read, Update, and Delete) to the data collector configuration on a server instance.</span></span> <span data-ttu-id="bf0e8-132">Les membres de ce rôle peuvent effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="bf0e8-132">Members of this role can perform the following operations:</span></span>  
  
-   <span data-ttu-id="bf0e8-133">définir des propriétés au niveau du collecteur ;</span><span class="sxs-lookup"><span data-stu-id="bf0e8-133">Set collector-level properties.</span></span>  
  
-   <span data-ttu-id="bf0e8-134">ajouter des jeux d'éléments de collection ;</span><span class="sxs-lookup"><span data-stu-id="bf0e8-134">Add new collection sets.</span></span>  
  
-   <span data-ttu-id="bf0e8-135">installer de nouveaux types de collections ;</span><span class="sxs-lookup"><span data-stu-id="bf0e8-135">Install new collection types.</span></span>  
  
-   <span data-ttu-id="bf0e8-136">effectuer toutes les opérations autorisées pour le rôle **dc_operator** .</span><span class="sxs-lookup"><span data-stu-id="bf0e8-136">Perform all the operations permitted to the **dc_operator** role.</span></span>  
  
 <span data-ttu-id="bf0e8-137">Le `dc_admin` rôle est membre des rôles suivants :</span><span class="sxs-lookup"><span data-stu-id="bf0e8-137">The `dc_admin` role is a member of the following roles:</span></span>  
  
-   <span data-ttu-id="bf0e8-138">**SQLAgentUserRole**.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-138">**SQLAgentUserRole**.</span></span> <span data-ttu-id="bf0e8-139">Ce rôle est requis pour créer des planifications et exécuter des travaux.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-139">This role is required to create schedules and run jobs.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bf0e8-140">Les proxies créés pour le collecteur de données doivent accorder l’accès à `dc_admin` pour les créer et les utiliser dans toutes les étapes de travail qui requièrent un proxy.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-140">Proxies created for the data collector must grant access to `dc_admin` to create them and use them in any job steps that require a proxy.</span></span>  
  
-   <span data-ttu-id="bf0e8-141">**dc_operator**.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-141">**dc_operator**.</span></span> <span data-ttu-id="bf0e8-142">Les membres de `dc_admin` héritent des autorisations accordées à **dc_operator**.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-142">Members of `dc_admin` inherit the permissions given to **dc_operator**.</span></span>  
  
### <a name="dc_operator-role"></a><span data-ttu-id="bf0e8-143">Rôle dc_operator</span><span class="sxs-lookup"><span data-stu-id="bf0e8-143">dc_operator Role</span></span>  
 <span data-ttu-id="bf0e8-144">Les membres du rôle **dc_operator** disposent d’un accès en lecture et mise à jour.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-144">Members of the **dc_operator** role have Read and Update access.</span></span> <span data-ttu-id="bf0e8-145">Ce rôle prend en charge les tâches d'opérations liées à l'exécution et la configuration des jeux d'éléments de collection.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-145">This role supports operations tasks related to running and configuring collection sets.</span></span> <span data-ttu-id="bf0e8-146">Les membres de ce rôle peuvent effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="bf0e8-146">Members of this role can perform the following operations:</span></span>  
  
-   <span data-ttu-id="bf0e8-147">démarrer ou arrêter un jeu d'éléments de collection ;</span><span class="sxs-lookup"><span data-stu-id="bf0e8-147">Start or stop a collection set.</span></span>  
  
-   <span data-ttu-id="bf0e8-148">énumérer les jeux d'éléments de collection existants ;</span><span class="sxs-lookup"><span data-stu-id="bf0e8-148">Enumerate existing collection sets.</span></span>  
  
-   <span data-ttu-id="bf0e8-149">afficher les informations détaillées (par exemple, les éléments de collection et la fréquence de collecte) associées à un jeu d'éléments de collection ;</span><span class="sxs-lookup"><span data-stu-id="bf0e8-149">View the detailed information (for example, collection items, and collection frequency) associated with a collection set.</span></span>  
  
-   <span data-ttu-id="bf0e8-150">modifier la fréquence de téléchargement des jeux d'éléments de collection existants ;</span><span class="sxs-lookup"><span data-stu-id="bf0e8-150">Change the upload frequency for existing collection sets.</span></span>  
  
-   <span data-ttu-id="bf0e8-151">modifier la fréquence de collecte des éléments de collecte appartenant à un jeu d'éléments de collecte existant.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-151">Change the collection frequency for collection items that are part of an existing collection set.</span></span>  
  
 <span data-ttu-id="bf0e8-152">Le rôle **dc_operator** est membre des rôles suivants, requis pour énumérer et afficher les packages du collecteur de données :</span><span class="sxs-lookup"><span data-stu-id="bf0e8-152">The **dc_operator** role is a member of the following roles that are required for enumerating and viewing data collector packages:</span></span>  
  
-   <span data-ttu-id="bf0e8-153">**db_ssisltduser**</span><span class="sxs-lookup"><span data-stu-id="bf0e8-153">**db_ssisltduser**</span></span>  
  
-   <span data-ttu-id="bf0e8-154">**db_ssisoperator**</span><span class="sxs-lookup"><span data-stu-id="bf0e8-154">**db_ssisoperator**</span></span>  
  
 <span data-ttu-id="bf0e8-155">Pour plus d’informations, consultez [Rôles Integration Services &#40;Service SSIS&#41;](../../integration-services/security/integration-services-roles-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="bf0e8-155">For more information, see [Integration Services Roles &#40;SSIS Service&#41;](../../integration-services/security/integration-services-roles-ssis-service.md).</span></span>  
  
### <a name="dc_proxy-role"></a><span data-ttu-id="bf0e8-156">Rôle dc_proxy</span><span class="sxs-lookup"><span data-stu-id="bf0e8-156">dc_proxy Role</span></span>  
 <span data-ttu-id="bf0e8-157">Les membres du rôle **dc_proxy** disposent d’un accès en lecture aux jeux d’éléments de collecte du collecteur de données et aux propriétés au niveau du collecteur.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-157">Members of the **dc_proxy** role have Read access to data collector collection sets and collector-level properties.</span></span> <span data-ttu-id="bf0e8-158">Les membres de ce rôle peuvent également exécuter les travaux dont ils sont propriétaires, et créer des étapes de travail qui s'exécutent comme un compte proxy existant.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-158">Members of this role can also execute jobs that they own and create job steps that run as an existing proxy account.</span></span>  
  
 <span data-ttu-id="bf0e8-159">Les membres de ce rôle peuvent effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="bf0e8-159">Members of this role can perform the following operations:</span></span>  
  
-   <span data-ttu-id="bf0e8-160">consulter des informations sur la configuration des jeux d'éléments de collection (par exemple, les paramètres d'entrée des éléments de collection et la fréquence de collecte de ces éléments) ;</span><span class="sxs-lookup"><span data-stu-id="bf0e8-160">View collection set configuration information (for example, input parameters for collection items, and the collection frequency for these items).</span></span>  
  
-   <span data-ttu-id="bf0e8-161">obtenir des informations chiffrées internes uniquement accessibles par l'intermédiaire d'une procédure stockée signée (par exemple, les informations de connexion d'entrepôt de données utilisées pour les téléchargements de données) ;</span><span class="sxs-lookup"><span data-stu-id="bf0e8-161">Obtain internal encrypted information that can only be accessed by a signed stored procedure (for example, data warehouse connection information used for data uploads).</span></span>  
  
-   <span data-ttu-id="bf0e8-162">enregistrer des événements d'exécution de jeu d'éléments de collecte.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-162">Log collection-set run-time events.</span></span>  
  
 <span data-ttu-id="bf0e8-163">Le rôle **dc_proxy** est membre des rôles suivants requis pour énumérer et afficher les packages du collecteur de données :</span><span class="sxs-lookup"><span data-stu-id="bf0e8-163">The **dc_proxy** role is a member of the following roles that are required for enumerating and viewing data collector packages:</span></span>  
  
-   <span data-ttu-id="bf0e8-164">**db_ssisltduser**.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-164">**db_ssisltduser**.</span></span>  
  
-   <span data-ttu-id="bf0e8-165">**db_ssisoperator**</span><span class="sxs-lookup"><span data-stu-id="bf0e8-165">**db_ssisoperator**</span></span>  
  
 <span data-ttu-id="bf0e8-166">Pour plus d’informations, consultez [Rôles Integration Services &#40;Service SSIS&#41;](../../integration-services/security/integration-services-roles-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="bf0e8-166">For more information, see [Integration Services Roles &#40;SSIS Service&#41;](../../integration-services/security/integration-services-roles-ssis-service.md).</span></span>  
  
## <a name="permissions-for-configuring-and-using-the-management-data-warehouse"></a><span data-ttu-id="bf0e8-167">Autorisations de configuration et d'utilisation de l'entrepôt de données de gestion</span><span class="sxs-lookup"><span data-stu-id="bf0e8-167">Permissions for Configuring and Using the Management Data Warehouse</span></span>  
 <span data-ttu-id="bf0e8-168">En fonction de la tâche, les utilisateurs doivent être membres d'un ou plusieurs des rôles de base de données fixes fournis pour accéder à l'entrepôt de données de gestion.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-168">Depending on the task, users must be members of one or more of the fixed database roles provided for accessing the management data warehouse.</span></span> <span data-ttu-id="bf0e8-169">Ces rôles, présentés ici du plus privilégié au moins privilégié en termes d'accès, sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="bf0e8-169">In order of most-privileged to least-privileged access, the roles are as follows:</span></span>  
  
-   <span data-ttu-id="bf0e8-170">**mdw_admin**</span><span class="sxs-lookup"><span data-stu-id="bf0e8-170">**mdw_admin**</span></span>  
  
-   <span data-ttu-id="bf0e8-171">**mdw_writer**</span><span class="sxs-lookup"><span data-stu-id="bf0e8-171">**mdw_writer**</span></span>  
  
-   <span data-ttu-id="bf0e8-172">**mdw_reader**</span><span class="sxs-lookup"><span data-stu-id="bf0e8-172">**mdw_reader**</span></span>  
  
 <span data-ttu-id="bf0e8-173">Ces rôles sont stockés dans la base de données msdb.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-173">These roles are stored in the msdb database.</span></span> <span data-ttu-id="bf0e8-174">Par défaut, aucun utilisateur n'est membre de ces rôles de base de données.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-174">By default, no user is a member of these database roles.</span></span> <span data-ttu-id="bf0e8-175">L'appartenance d'un utilisateur à ces rôles doit être accordée explicitement.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-175">User membership in these roles must be granted explicitly.</span></span>  
  
 <span data-ttu-id="bf0e8-176">Les utilisateurs qui sont membres du `sysadmin` rôle serveur fixe ont un accès complet aux vues du collecteur de données.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-176">Users who are members of the `sysadmin` fixed server role have full access to data collector views.</span></span> <span data-ttu-id="bf0e8-177">Toutefois, ils doivent être ajoutés explicitement aux rôles de base de données pour effectuer d'autres opérations.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-177">However, they need to be explicitly added to database roles to perform other operations.</span></span>  
  
### <a name="mdw_admin-role"></a><span data-ttu-id="bf0e8-178">Rôle mdw_admin</span><span class="sxs-lookup"><span data-stu-id="bf0e8-178">mdw_admin Role</span></span>  
 <span data-ttu-id="bf0e8-179">Les membres du rôle **mdw_admin** disposent d’un accès en lecture, écriture, mise à jour et suppression à l’entrepôt de données de gestion.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-179">Members of the **mdw_admin** role have Read, Write, Update, and Delete access to the management data warehouse.</span></span>  
  
 <span data-ttu-id="bf0e8-180">Les membres de ce rôle peuvent effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="bf0e8-180">Members of this role can perform the following operations:</span></span>  
  
-   <span data-ttu-id="bf0e8-181">modifier le schéma de l'entrepôt de données de gestion lorsque cela est nécessaire (par exemple, ajouter une table lorsqu'un nouveau type de collecte est installé) ;</span><span class="sxs-lookup"><span data-stu-id="bf0e8-181">Change the management data warehouse schema when required (for example, adding a new table when a new collection type is installed).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bf0e8-182">En cas de modification de schéma, l’utilisateur doit également être membre du `dc_admin` rôle pour installer un nouveau type de collecteur, car cette action nécessite l’autorisation de mettre à jour la configuration du collecteur de données dans msdb.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-182">Where there is a schema change, the user must also be a member of the `dc_admin` role to install a new collector type, since this action requires permission to update the data collector configuration in msdb.</span></span>  
  
-   <span data-ttu-id="bf0e8-183">exécuter des travaux de maintenance sur l'entrepôt de données de gestion, tels que l'archivage ou le nettoyage.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-183">Run maintenance jobs on the management data warehouse, such as archive or cleanup.</span></span>  
  
### <a name="mdw_writer-role"></a><span data-ttu-id="bf0e8-184">Rôle mdw_writer</span><span class="sxs-lookup"><span data-stu-id="bf0e8-184">mdw_writer Role</span></span>  
 <span data-ttu-id="bf0e8-185">Les membres du rôle **mdw_writer** peuvent télécharger et écrire des données dans l’entrepôt de données de gestion.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-185">Members of the **mdw_writer** role can upload and write data to the management data warehouse.</span></span> <span data-ttu-id="bf0e8-186">Tout collecteur de données qui stocke des données dans l'entrepôt de données de gestion doit être membre de ce rôle.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-186">Any data collector that stores data in the management data warehouse has to be a member of this role.</span></span>  
  
### <a name="mdw_reader-role"></a><span data-ttu-id="bf0e8-187">Rôle mdw_reader</span><span class="sxs-lookup"><span data-stu-id="bf0e8-187">mdw_reader Role</span></span>  
 <span data-ttu-id="bf0e8-188">Les membres du rôle **mdw_reader** disposent d’un accès en lecture à l’entrepôt de données de gestion.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-188">Members of the **mdw_reader** role have Read access to the management data warehouse.</span></span> <span data-ttu-id="bf0e8-189">Comme ce rôle a pour but de prendre en charge la résolution de problèmes en fournissant l'accès aux données historiques, les membres de ce rôle ne peuvent pas consulter les autres éléments du schéma de l'entrepôt de données de gestion.</span><span class="sxs-lookup"><span data-stu-id="bf0e8-189">Because the purpose of this role is to support troubleshooting by providing access to historical data, members of this role cannot view other elements of the management data warehouse schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf0e8-190">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bf0e8-190">See Also</span></span>  
 [<span data-ttu-id="bf0e8-191">Implémenter la sécurité de l'Agent SQL Server</span><span class="sxs-lookup"><span data-stu-id="bf0e8-191">Implement SQL Server Agent Security</span></span>](../../ssms/agent/implement-sql-server-agent-security.md)  
  
  
