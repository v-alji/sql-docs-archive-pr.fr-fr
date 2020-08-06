---
title: Attributs de protection de l’hôte et programmation de l’intégration du CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- host protection attributes [CLR integration]
- HostProtectionAttribute [CLR integration]
- common language runtime [SQL Server], host protection attributes
- disallowed types and members [CLR integration]
- common language runtime [SQL Server], disallowed types and members
- HPAs [CLR integration]
ms.assetid: 268078df-63ca-4c03-a8e7-7108bcea9697
author: rothja
ms.author: jroth
ms.openlocfilehash: 16ca1e4734e66b0eca85523764739e8f8b32634a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704196"
---
# <a name="host-protection-attributes-and-clr-integration-programming"></a><span data-ttu-id="499ca-102">Attributs de protection de l'hôte et programmation de l'intégration CLR</span><span class="sxs-lookup"><span data-stu-id="499ca-102">Host Protection Attributes and CLR Integration Programming</span></span>
  <span data-ttu-id="499ca-103">Le Common Language Runtime (CLR) fournit un mécanisme pour annoter des interfaces de programmation d'applications (API) managées qui font partie du .NET Framework avec certains attributs qui peuvent intéresser un hôte du CLR, tel que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], à compter de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="499ca-103">The common language runtime (CLR) provides a mechanism to annotate managed application programming interfaces (APIs) that are part of the .NET Framework with certain attributes that may be of interest to a host of the CLR, such as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="499ca-104">Voici quelques exemples d'attributs de protection de l'hôte (HPA, Host Protection Attribute) :</span><span class="sxs-lookup"><span data-stu-id="499ca-104">Examples of such host protection attributes (HPAs) include:</span></span>  
  
-   <span data-ttu-id="499ca-105">`SharedState`, qui indique si l'API expose la capacité à créer ou gérer l'état partagé (par exemple, champs de classe statique).</span><span class="sxs-lookup"><span data-stu-id="499ca-105">`SharedState`, which indicates whether the API exposes the ability to create or manage shared state (for example, static class fields).</span></span>  
  
-   <span data-ttu-id="499ca-106">`Synchronization`, qui indique si l'API expose la capacité à effectuer la synchronisation entre des threads.</span><span class="sxs-lookup"><span data-stu-id="499ca-106">`Synchronization`, which indicates whether the API exposes the ability to perform synchronization between threads.</span></span>  
  
-   <span data-ttu-id="499ca-107">`ExternalProcessMgmt`, qui indique si l'API expose une méthode pour contrôler le processus hôte.</span><span class="sxs-lookup"><span data-stu-id="499ca-107">`ExternalProcessMgmt`, which indicates whether the API exposes a way to control the host process.</span></span>  
  
 <span data-ttu-id="499ca-108">Étant donné ces attributs, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] spécifie une liste de HPA rejetés dans l'environnement hébergé par le biais de la sécurité d'accès du code.</span><span class="sxs-lookup"><span data-stu-id="499ca-108">Given these attributes, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] specifies a list of HPAs that are disallowed in the hosted environment through code access security (CAS).</span></span> <span data-ttu-id="499ca-109">Les spécifications de sécurité d'accès du code sont indiquées par l'un des trois jeux d'autorisations [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] : `SAFE`, `EXTERNAL_ACCESS` ou `UNSAFE`.</span><span class="sxs-lookup"><span data-stu-id="499ca-109">The CAS requirements are specified by one of three [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permission sets: `SAFE`, `EXTERNAL_ACCESS`, or `UNSAFE`.</span></span> <span data-ttu-id="499ca-110">L'un de ces trois niveaux de sécurité est spécifié lorsque l'assembly est inscrit sur le serveur, à l'aide de l'instruction `CREATE ASSEMBLY`.</span><span class="sxs-lookup"><span data-stu-id="499ca-110">One of these three security levels is specified when the assembly is registered on the server, using the `CREATE ASSEMBLY` statement.</span></span> <span data-ttu-id="499ca-111">Le code exécuté dans les jeux d'autorisations `SAFE` ou `EXTERNAL_ACCESS` doit éviter certains types ou membres dont l'attribut `System.Security.Permissions.HostProtectionAttribute` est appliqué.</span><span class="sxs-lookup"><span data-stu-id="499ca-111">Code executing within the `SAFE` or `EXTERNAL_ACCESS` permission sets must avoid certain types or members that have the `System.Security.Permissions.HostProtectionAttribute` attribute applied.</span></span> <span data-ttu-id="499ca-112">Pour plus d’informations, consultez [création d’un assembly](../clr-integration/assemblies/creating-an-assembly.md) et [restrictions du modèle de programmation](../clr-integration/database-objects/clr-integration-programming-model-restrictions.md)de l’intégration du CLR.</span><span class="sxs-lookup"><span data-stu-id="499ca-112">For more information, see [Creating an Assembly](../clr-integration/assemblies/creating-an-assembly.md) and [CLR Integration Programming Model Restrictions](../clr-integration/database-objects/clr-integration-programming-model-restrictions.md).</span></span>  
  
 <span data-ttu-id="499ca-113">`HostProtectionAttribute` n'est pas tant une autorisation de sécurité qu'une façon d'améliorer la fiabilité, dans le sens où il identifie des constructions de code spécifiques, à savoir des types ou des méthodes, que l'hôte peut rejeter.</span><span class="sxs-lookup"><span data-stu-id="499ca-113">The `HostProtectionAttribute` is not a security permission as much as a way to improve reliability, in that it identifies specific code constructs, either types or methods, that the host may disallow.</span></span> <span data-ttu-id="499ca-114">L'utilisation de `HostProtectionAttribute` applique un modèle de programmation qui contribue à protéger la stabilité de l'hôte.</span><span class="sxs-lookup"><span data-stu-id="499ca-114">The use of the `HostProtectionAttribute` enforces a programming model that helps protect the stability of the host.</span></span>  
  
## <a name="host-protection-attributes"></a><span data-ttu-id="499ca-115">Attributs de protection de l'hôte</span><span class="sxs-lookup"><span data-stu-id="499ca-115">Host Protection Attributes</span></span>  
 <span data-ttu-id="499ca-116">Les attributs de protection de l'hôte identifient des types ou des membres qui ne sont pas adaptés au modèle de programmation hôte et représentent les niveaux croissants suivants de menace en termes de fiabilité :</span><span class="sxs-lookup"><span data-stu-id="499ca-116">HPAs identify types or members that do not fit the host programming model and represent the following increasing levels of reliability threat:</span></span>  
  
-   <span data-ttu-id="499ca-117">Sans gravité par ailleurs.</span><span class="sxs-lookup"><span data-stu-id="499ca-117">Are otherwise benign.</span></span>  
  
-   <span data-ttu-id="499ca-118">Susceptible de déstabiliser le code utilisateur géré par le serveur.</span><span class="sxs-lookup"><span data-stu-id="499ca-118">Could lead to destabilization of server-managed user code.</span></span>  
  
-   <span data-ttu-id="499ca-119">Susceptible de déstabiliser le processus serveur lui-même.</span><span class="sxs-lookup"><span data-stu-id="499ca-119">Could lead to destabilization of the server process itself.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="499ca-120">interdit l’utilisation d’un type ou d’un membre ayant un `HostProtectionAttribute` qui spécifie une `System.Security.Permissions.HostProtectionResource` énumération avec la valeur `ExternalProcessMgmt` , `ExternalThreading` , `MayLeakOnAbort` , `SecurityInfrastructure` , `SelfAffectingProcessMgmnt` , `SelfAffectingThreading` , `SharedState` , `Synchronization` ou `UI` .</span><span class="sxs-lookup"><span data-stu-id="499ca-120">disallows the use of a type or member that has a `HostProtectionAttribute` that specifies a `System.Security.Permissions.HostProtectionResource` enumeration with a value of `ExternalProcessMgmt`, `ExternalThreading`, `MayLeakOnAbort`, `SecurityInfrastructure`, `SelfAffectingProcessMgmnt`, `SelfAffectingThreading`, `SharedState`, `Synchronization`, or `UI`.</span></span> <span data-ttu-id="499ca-121">Cela empêche les assemblys d'appeler des membres qui activent l'état de partage, exécutent la synchronisation, peuvent entraîner une fuite de ressources ou affectent l'intégrité du processus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="499ca-121">This prevents the assemblies from calling members that enable sharing state, perform synchronization, might cause a resource leak on termination, or affect the integrity of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process.</span></span>  
  
### <a name="disallowed-types-and-members"></a><span data-ttu-id="499ca-122">Types et membres rejetés</span><span class="sxs-lookup"><span data-stu-id="499ca-122">Disallowed Types and Members</span></span>  
 <span data-ttu-id="499ca-123">Les rubriques suivantes identifient les types et membres dont les valeurs `HostProtectionResource` sont rejetées par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="499ca-123">The following topics identify types and members whose `HostProtectionResource` values are disallowed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="499ca-124">Les listes de ces rubriques ont été générées à partir des assemblys pris en charge.</span><span class="sxs-lookup"><span data-stu-id="499ca-124">The lists in these topics were generated from the supported assemblies.</span></span>  <span data-ttu-id="499ca-125">Pour plus d’informations, consultez [.NET Framework les bibliothèques prises en charge](../clr-integration/database-objects/supported-net-framework-libraries.md).</span><span class="sxs-lookup"><span data-stu-id="499ca-125">For more information, see [Supported .NET Framework Libraries](../clr-integration/database-objects/supported-net-framework-libraries.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="499ca-126">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="499ca-126">In This Section</span></span>  
 [<span data-ttu-id="499ca-127">Types et membres interdits dans Microsoft.VisualBasic.dll</span><span class="sxs-lookup"><span data-stu-id="499ca-127">Disallowed Types and Members in Microsoft.VisualBasic.dll</span></span>](disallowed-types-and-members-in-microsoft-visualbasic-dll.md)  
 <span data-ttu-id="499ca-128">Répertorie les types et membres dans Microsoft.VisualBasic.dll dont les valeurs HPA sont rejetées.</span><span class="sxs-lookup"><span data-stu-id="499ca-128">Lists the types and members in Microsoft.VisualBasic.dll whose HPA values are disallowed.</span></span>  
  
 [<span data-ttu-id="499ca-129">Types et membres interdits dans mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="499ca-129">Disallowed Types and Members in mscorlib.dll</span></span>](disallowed-types-and-members-in-mscorlib-dll.md)  
 <span data-ttu-id="499ca-130">Répertorie les types et membres dans mscorlib.dll dont les valeurs HPA sont rejetées.</span><span class="sxs-lookup"><span data-stu-id="499ca-130">Lists the types and members in mscorlib.dll whose HPA values are disallowed.</span></span>  
  
 [<span data-ttu-id="499ca-131">Types et membres non autorisés dans System.dll</span><span class="sxs-lookup"><span data-stu-id="499ca-131">Disallowed Types and Members in System.dll</span></span>](disallowed-types-and-members-in-system-dll.md)  
 <span data-ttu-id="499ca-132">Répertorie les types et membres dans System.dll dont les valeurs HPA sont rejetées.</span><span class="sxs-lookup"><span data-stu-id="499ca-132">Lists the types and members in System.dll whose HPA values are disallowed.</span></span>  
  
 [<span data-ttu-id="499ca-133">Types et membres non autorisés dans System.Data.dll</span><span class="sxs-lookup"><span data-stu-id="499ca-133">Disallowed Types and Members in System.Data.dll</span></span>](disallowed-types-and-members-in-system-data-dll.md)  
 <span data-ttu-id="499ca-134">Répertorie les types et membres dans System.Data.dll dont les valeurs HPA sont rejetées.</span><span class="sxs-lookup"><span data-stu-id="499ca-134">Lists the types and members in System.Data.dll whose HPA values are disallowed.</span></span>  
  
 [<span data-ttu-id="499ca-135">Types et membres interdits dans System.Core.dll</span><span class="sxs-lookup"><span data-stu-id="499ca-135">Disallowed Types and Members in System.Core.dll</span></span>](disallowed-types-and-members-in-system-core-dll.md)  
 <span data-ttu-id="499ca-136">Répertorie les types et membres dans System.Core.dll dont les valeurs HPA sont rejetées.</span><span class="sxs-lookup"><span data-stu-id="499ca-136">Lists the types and members in System.Core.dll whose HPA values are disallowed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="499ca-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="499ca-137">See Also</span></span>  
 <span data-ttu-id="499ca-138">[Sécurité d’accès du code d’intégration du CLR](../clr-integration/security/clr-integration-code-access-security.md) </span><span class="sxs-lookup"><span data-stu-id="499ca-138">[CLR Integration Code Access Security](../clr-integration/security/clr-integration-code-access-security.md) </span></span>  
 <span data-ttu-id="499ca-139">[Restrictions du modèle de programmation de l’intégration du CLR](../clr-integration/database-objects/clr-integration-programming-model-restrictions.md) </span><span class="sxs-lookup"><span data-stu-id="499ca-139">[CLR Integration Programming Model Restrictions](../clr-integration/database-objects/clr-integration-programming-model-restrictions.md) </span></span>  
 [<span data-ttu-id="499ca-140">Création d'un assembly</span><span class="sxs-lookup"><span data-stu-id="499ca-140">Creating an Assembly</span></span>](../clr-integration/assemblies/creating-an-assembly.md)  
  
  
