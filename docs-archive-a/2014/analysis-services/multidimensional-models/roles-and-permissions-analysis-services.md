---
title: Rôles et autorisations (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- security [Analysis Services], about security
- security [Analysis Services - multidimensional data], about security
ms.assetid: bb885447-868b-4686-853c-8241f63d4370
author: minewiskan
ms.author: owend
ms.openlocfilehash: d6595d931b2c2760e5fd3013ff6bec88f85106d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710903"
---
# <a name="roles-and-permissions-analysis-services"></a><span data-ttu-id="c9dc1-102">Rôles et autorisations (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="c9dc1-102">Roles and Permissions (Analysis Services)</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="c9dc1-103">fournit un modèle d’autorisation basé sur les rôles qui accorde l’accès aux opérations, aux objets, ainsi qu’aux données.</span><span class="sxs-lookup"><span data-stu-id="c9dc1-103">provides a role-based authorization model that grants access to operations, objects, and data.</span></span> <span data-ttu-id="c9dc1-104">Tous les utilisateurs qui accèdent à une instance ou à une base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] doivent effectuer cette opération dans le contexte d’un rôle.</span><span class="sxs-lookup"><span data-stu-id="c9dc1-104">All users who access an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance or database must do so within the context of a role.</span></span>  
  
 <span data-ttu-id="c9dc1-105">En tant qu’administrateur système d’ [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , vous êtes chargé d’accorder l’appartenance au **rôle d’administrateur de serveur** qui donne un accès sans restrictions aux opérations sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="c9dc1-105">As an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] system administrator, you are in charge of granting membership to the **server administrator role** that conveys unrestricted access to operations on the server.</span></span> <span data-ttu-id="c9dc1-106">Ce rôle comporte des autorisations fixes et ne peut pas être personnalisé.</span><span class="sxs-lookup"><span data-stu-id="c9dc1-106">This role has fixed permissions and cannot be customized.</span></span> <span data-ttu-id="c9dc1-107">Par défaut, les membres du groupe local Administrateurs sont automatiquement des administrateurs système d'Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="c9dc1-107">By default, members of the local Administrators group are automatically Analysis Services system administrators.</span></span>  
  
 <span data-ttu-id="c9dc1-108">L’accord de l’accès aux utilisateurs non-administrateurs qui interrogent ou traitent des données s’effectue par l’intermédiaire de **rôles de base de données**.</span><span class="sxs-lookup"><span data-stu-id="c9dc1-108">Non-administrative users who query or process data are granted access through **database roles**.</span></span> <span data-ttu-id="c9dc1-109">Les administrateurs système et les administrateurs de base de données peuvent tous deux créer les rôles qui décrivent les différents niveaux d'accès à une base de données spécifique, puis attribuer l'appartenance à chaque utilisateur qui a besoin de l'accès.</span><span class="sxs-lookup"><span data-stu-id="c9dc1-109">Both system administrators and database administrators can create the roles that describe different levels of access within a given database, and then assign membership to every user who requires access.</span></span> <span data-ttu-id="c9dc1-110">Chaque rôle dispose d'un ensemble personnalisé d'autorisations pour l'accès aux objets et aux opérations dans une base de données particulière.</span><span class="sxs-lookup"><span data-stu-id="c9dc1-110">Each role has a customized set of permissions for accessing objects and operations within a particular database.</span></span> <span data-ttu-id="c9dc1-111">Vous pouvez attribuer des autorisations au niveau des bases de données, des objets intérieurs tels que les cubes et les dimensions (mais pas les perspectives) et des lignes.</span><span class="sxs-lookup"><span data-stu-id="c9dc1-111">You can assign permissions at these levels: database, interior objects such as cubes and dimensions (but not perspectives), and rows.</span></span>  
  
 <span data-ttu-id="c9dc1-112">Il est courant de créer des rôles et d'affecter l'appartenance en tant qu'opération distincte.</span><span class="sxs-lookup"><span data-stu-id="c9dc1-112">It is common practice to create roles and assign membership as separate operations.</span></span> <span data-ttu-id="c9dc1-113">Souvent, le concepteur de modèles ajoute des rôles pendant la phase de conception.</span><span class="sxs-lookup"><span data-stu-id="c9dc1-113">Often, the model designer adds roles during the design phase.</span></span> <span data-ttu-id="c9dc1-114">De cette manière, toutes les définitions de rôles sont reflétées dans les fichiers de projet qui définissent le modèle.</span><span class="sxs-lookup"><span data-stu-id="c9dc1-114">This way, all role definitions are reflected in the project files that define the model.</span></span> <span data-ttu-id="c9dc1-115">L'appartenance au rôle est généralement transférée ultérieurement, quand la base de données entre en production, généralement par les administrateurs de base de données qui créent des scripts pouvant être développés, testés et exécutés comme une opération indépendante.</span><span class="sxs-lookup"><span data-stu-id="c9dc1-115">Role membership is typically rolled out later as the database moves into production, usually by database administrators who create scripts that can be developed, tested, and run as an independent operation.</span></span>  
  
 <span data-ttu-id="c9dc1-116">Toutes les autorisations sont établies sur une identité d'utilisateur Windows valide.</span><span class="sxs-lookup"><span data-stu-id="c9dc1-116">All authorization is predicated on a valid Windows user identity.</span></span> [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="c9dc1-117">utilise l’authentification Windows exclusivement pour authentifier les identités des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c9dc1-117">uses Windows authentication exclusively to authenticate user identities.</span></span> [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="c9dc1-118">ne fournit aucune méthode d’authentification propriétaire. Consultez [méthodologies d’authentification prises en charge par Analysis Services](../instances/authentication-methodologies-supported-by-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="c9dc1-118">provides no proprietary authentication method.See [Authentication methodologies supported by Analysis Services](../instances/authentication-methodologies-supported-by-analysis-services.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c9dc1-119">Les autorisations s'ajoutent pour chaque utilisateur ou groupe Windows, parmi tous les rôles de la base de données.</span><span class="sxs-lookup"><span data-stu-id="c9dc1-119">Permissions are additive for each Windows user or group, across all roles in the database.</span></span> <span data-ttu-id="c9dc1-120">Si un rôle interdit à un utilisateur ou à un groupe d'exécuter certaines tâches ou d'afficher certaines données, mais qu'un autre rôle lui permet de le faire, l'utilisateur ou le groupe est autorisé à exécuter la tâche ou à afficher les données.</span><span class="sxs-lookup"><span data-stu-id="c9dc1-120">If one role denies a user or group permission to perform certain tasks or view certain data, but another role grants this permission to that user or group, the user or group will have permission to perform the task or view the data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c9dc1-121">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="c9dc1-121">In this section</span></span>  
  
-   [<span data-ttu-id="c9dc1-122">Autorisation de l’accès à des objets et des opérations &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c9dc1-122">Authorizing access to objects and operations &#40;Analysis Services&#41;</span></span>](authorizing-access-to-objects-and-operations-analysis-services.md)  
  
-   [<span data-ttu-id="c9dc1-123">Octroyer des autorisations de base de données &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c9dc1-123">Grant database permissions &#40;Analysis Services&#41;</span></span>](grant-database-permissions-analysis-services.md)  
  
-   [<span data-ttu-id="c9dc1-124">Octroyer des autorisations de cube ou de modèle &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c9dc1-124">Grant cube or model permissions &#40;Analysis Services&#41;</span></span>](grant-cube-or-model-permissions-analysis-services.md)  
  
-   [<span data-ttu-id="c9dc1-125">Octroyer des autorisations de traitement &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c9dc1-125">Grant process permissions &#40;Analysis Services&#41;</span></span>](grant-process-permissions-analysis-services.md)  
  
-   [<span data-ttu-id="c9dc1-126">Octroyer des autorisations Lire la définition sur des métadonnées d’objets &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c9dc1-126">Grant read definition permissions on object metadata &#40;Analysis Services&#41;</span></span>](grant-read-definition-permissions-on-object-metadata-analysis-services.md)  
  
-   [<span data-ttu-id="c9dc1-127">Octroyer des autorisations sur un objet de source de données &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c9dc1-127">Grant permissions on a data source object &#40;Analysis Services&#41;</span></span>](grant-permissions-on-a-data-source-object-analysis-services.md)  
  
-   [<span data-ttu-id="c9dc1-128">Octroyer des autorisations sur des modèles et des structures d’exploration de données &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c9dc1-128">Grant permissions on data mining structures and models &#40;Analysis Services&#41;</span></span>](grant-permissions-on-data-mining-structures-and-models-analysis-services.md)  
  
-   [<span data-ttu-id="c9dc1-129">Octroyer des autorisations sur une dimension &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c9dc1-129">Grant permissions on a dimension &#40;Analysis Services&#41;</span></span>](grant-permissions-on-a-dimension-analysis-services.md)  
  
-   [<span data-ttu-id="c9dc1-130">Octroyer un accès personnalisé à des données de dimension &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c9dc1-130">Grant custom access to dimension data &#40;Analysis Services&#41;</span></span>](grant-custom-access-to-dimension-data-analysis-services.md)  
  
-   [<span data-ttu-id="c9dc1-131">Octroyer un accès personnalisé à des données de cellule &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c9dc1-131">Grant custom access to cell data &#40;Analysis Services&#41;</span></span>](grant-custom-access-to-cell-data-analysis-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="c9dc1-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c9dc1-132">See Also</span></span>  
 [<span data-ttu-id="c9dc1-133">Créer et gérer des rôles &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="c9dc1-133">Create and Manage Roles &#40;SSAS Tabular&#41;</span></span>](../tabular-models/roles-ssas-tabular.md)  
  
  
