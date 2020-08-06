---
title: Restrictions du modèle de programmation de l’intégration du CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- common language runtime [SQL Server], programming model restrictions
- assemblies [CLR integration], CREATE ASSEMBLY checks
- programming model restrictions [CLR integration]
- assemblies [CLR integration], runtime checks
ms.assetid: 2446afc2-9d21-42d3-9847-7733d3074de9
author: rothja
ms.author: jroth
ms.openlocfilehash: 01a32e1460ad9c49061b39b1bdc419c7cd2f1342
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600083"
---
# <a name="clr-integration-programming-model-restrictions"></a><span data-ttu-id="c6ceb-102">Restrictions du modèle de programmation de l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="c6ceb-102">CLR Integration Programming Model Restrictions</span></span>
  <span data-ttu-id="c6ceb-103">Lors de la génération d’une procédure stockée managée ou d’un autre objet de base de données managée, certaines vérifications du code effectuées par [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] effectuent des vérifications sur l’assembly de code managé lorsqu’il est inscrit pour la première fois dans la base de données, à l’aide de l' `CREATE ASSEMBLY` instruction et également au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="c6ceb-103">When you are building a managed stored procedure or other managed database object, there are certain code checks performed by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] performs checks on the managed code assembly when it is first registered in the database, using the `CREATE ASSEMBLY` statement, and also at runtime.</span></span> <span data-ttu-id="c6ceb-104">Le code managé est également vérifié pendant l'exécution, car dans un assembly il peut y avoir des chemins d'accès de code qui peuvent ne jamais être atteints pendant l'exécution.</span><span class="sxs-lookup"><span data-stu-id="c6ceb-104">The managed code is also checked at runtime because in an assembly there may be code paths that may never actually be reached at runtime.</span></span>  <span data-ttu-id="c6ceb-105">Cela fournit la souplesse nécessaire pour inscrire notamment des assemblys tiers, afin qu'un assembly ne soit pas bloqué là où il y a du code « potentiellement dangereux » conçu pour s'exécuter dans un environnement client, mais ne soit jamais exécuté dans le CLR hébergé.</span><span class="sxs-lookup"><span data-stu-id="c6ceb-105">This provides flexibility for registering third party assemblies, especially, so that an assembly wouldn't be blocked where there is 'unsafe' code designed to run in a client environment but would never be executed in the hosted CLR.</span></span> <span data-ttu-id="c6ceb-106">Les exigences que le code managé doit respecter varient selon que l’assembly est inscrit en tant que `SAFE` , `EXTERNAL_ACCESS` ou, et qu’il est `UNSAFE` le plus `SAFE` strict, et est répertorié ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="c6ceb-106">The requirements that the managed code must meet depend on whether the assembly is registered as `SAFE`, `EXTERNAL_ACCESS`, or `UNSAFE`, `SAFE` being the strictest, and are listed below.</span></span>  
  
 <span data-ttu-id="c6ceb-107">En plus des restrictions imposées sur les assemblys de code managé, des autorisations de sécurité du code sont également accordées.</span><span class="sxs-lookup"><span data-stu-id="c6ceb-107">In addition to restrictions being placed on the managed code assemblies, there are also code security permissions that are granted.</span></span> <span data-ttu-id="c6ceb-108">Le Common Language Runtime (CLR) prend en charge un modèle de sécurité appelé sécurité d'accès du code pour le code managé.</span><span class="sxs-lookup"><span data-stu-id="c6ceb-108">The common language runtime (CLR) supports a security model called code access security (CAS) for managed code.</span></span> <span data-ttu-id="c6ceb-109">Dans ce modèle, les autorisations sont accordées aux assemblys selon l'identité du code.</span><span class="sxs-lookup"><span data-stu-id="c6ceb-109">In this model, permissions are granted to assemblies based on the identity of the code.</span></span> <span data-ttu-id="c6ceb-110">Les assemblys `SAFE`, `EXTERNAL_ACCESS` et `UNSAFE` ont des autorisations de sécurité d'accès du code différentes.</span><span class="sxs-lookup"><span data-stu-id="c6ceb-110">`SAFE`, `EXTERNAL_ACCESS`, and `UNSAFE` assemblies have different CAS permissions.</span></span> <span data-ttu-id="c6ceb-111">Pour plus d’informations, consultez [sécurité d’accès du code d’intégration du CLR](../security/clr-integration-code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="c6ceb-111">For more information, see [CLR Integration Code Access Security](../security/clr-integration-code-access-security.md).</span></span>  
  
## <a name="create-assembly-checks"></a><span data-ttu-id="c6ceb-112">Contrôles CREATE ASSEMBLY</span><span class="sxs-lookup"><span data-stu-id="c6ceb-112">CREATE ASSEMBLY Checks</span></span>  
 <span data-ttu-id="c6ceb-113">Lorsque l'instruction `CREATE ASSEMBLY` est exécutée, les contrôles suivants sont effectués pour chaque niveau de sécurité.</span><span class="sxs-lookup"><span data-stu-id="c6ceb-113">When the `CREATE ASSEMBLY` statement is run, the following checks are performed for each security level.</span></span>  <span data-ttu-id="c6ceb-114">Si un contrôle échoue, `CREATE ASSEMBLY` échoue avec un message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="c6ceb-114">If any check fails, `CREATE ASSEMBLY` will fail with an error message.</span></span>  
  
### <a name="global-any-security-level"></a><span data-ttu-id="c6ceb-115">Global (tout niveau de sécurité)</span><span class="sxs-lookup"><span data-stu-id="c6ceb-115">Global (any security level)</span></span>  
 <span data-ttu-id="c6ceb-116">Tous les assemblys référencés doivent satisfaire un ou plusieurs des critères suivants :</span><span class="sxs-lookup"><span data-stu-id="c6ceb-116">All referenced assemblies must meet one or more of the following criteria:</span></span>  
  
-   <span data-ttu-id="c6ceb-117">L'assembly est déjà inscrit dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="c6ceb-117">The assembly is already registered in the database.</span></span>  
  
-   <span data-ttu-id="c6ceb-118">L'assembly est l'un des assemblys pris en charge.</span><span class="sxs-lookup"><span data-stu-id="c6ceb-118">The assembly is one of the supported assemblies.</span></span> <span data-ttu-id="c6ceb-119">Pour plus d’informations, consultez [.NET Framework les bibliothèques prises en charge](supported-net-framework-libraries.md).</span><span class="sxs-lookup"><span data-stu-id="c6ceb-119">For more information, see [Supported .NET Framework Libraries](supported-net-framework-libraries.md).</span></span>  
  
-   <span data-ttu-id="c6ceb-120">Vous utilisez `CREATE ASSEMBLY FROM` \* \<location> ,\* et tous les assemblys référencés et leurs dépendances sont disponibles dans *\<location>* .</span><span class="sxs-lookup"><span data-stu-id="c6ceb-120">You are using `CREATE ASSEMBLY FROM`*\<location>,* and all the referenced assemblies and their dependencies are available in *\<location>*.</span></span>  
  
-   <span data-ttu-id="c6ceb-121">Vous utilisez `CREATE ASSEMBLY FROM` \* \<bytes ...> ,\* et toutes les références sont spécifiées via des octets séparés par des espaces.</span><span class="sxs-lookup"><span data-stu-id="c6ceb-121">You are using `CREATE ASSEMBLY FROM`*\<bytes ...>,* and all the references are specified via space separated bytes.</span></span>  
  
### <a name="external_access"></a><span data-ttu-id="c6ceb-122">EXTERNAL_ACCESS</span><span class="sxs-lookup"><span data-stu-id="c6ceb-122">EXTERNAL_ACCESS</span></span>  
 <span data-ttu-id="c6ceb-123">Tous les assemblys `EXTERNAL_ACCESS` doivent répondre aux critères suivants :</span><span class="sxs-lookup"><span data-stu-id="c6ceb-123">All `EXTERNAL_ACCESS` assemblies must meet the following criteria:</span></span>  
  
-   <span data-ttu-id="c6ceb-124">Les champs statiques ne sont pas utilisés pour stocker des informations.</span><span class="sxs-lookup"><span data-stu-id="c6ceb-124">Static fields are not used to store information.</span></span> <span data-ttu-id="c6ceb-125">Les champs statiques en lecture seule sont autorisés.</span><span class="sxs-lookup"><span data-stu-id="c6ceb-125">Read-only static fields are allowed.</span></span>  
  
-   <span data-ttu-id="c6ceb-126">Le test PEVerify est réussi.</span><span class="sxs-lookup"><span data-stu-id="c6ceb-126">PEVerify test is passed.</span></span> <span data-ttu-id="c6ceb-127">L'outil PEVerify (peverify.exe), qui vérifie que le code MSIL et les métadonnées associées satisfont les spécifications de sécurité de type, est fourni dans le Kit de développement SDK .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c6ceb-127">The PEVerify tool (peverify.exe), which checks that the MSIL code and associated metadata meet type safety requirements, is provided with the .NET Framework SDK.</span></span>  
  
-   <span data-ttu-id="c6ceb-128">La synchronisation, par exemple avec la classe `SynchronizationAttribute`, n'est pas utilisée.</span><span class="sxs-lookup"><span data-stu-id="c6ceb-128">Synchronization, for example with the `SynchronizationAttribute` class, is not used.</span></span>  
  
-   <span data-ttu-id="c6ceb-129">Les méthodes finaliseurs ne sont pas utilisées.</span><span class="sxs-lookup"><span data-stu-id="c6ceb-129">Finalizer methods are not used.</span></span>  
  
 <span data-ttu-id="c6ceb-130">Les attributs personnalisés suivants sont interdits dans les assemblys `EXTERNAL_ACCESS` :</span><span class="sxs-lookup"><span data-stu-id="c6ceb-130">The following custom attributes are disallowed in `EXTERNAL_ACCESS` assemblies:</span></span>  
  
-   <span data-ttu-id="c6ceb-131">System.ContextStaticAttribute</span><span class="sxs-lookup"><span data-stu-id="c6ceb-131">System.ContextStaticAttribute</span></span>  
  
-   <span data-ttu-id="c6ceb-132">System.MTAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="c6ceb-132">System.MTAThreadAttribute</span></span>  
  
-   <span data-ttu-id="c6ceb-133">System.Runtime.CompilerServices.MethodImplAttribute</span><span class="sxs-lookup"><span data-stu-id="c6ceb-133">System.Runtime.CompilerServices.MethodImplAttribute</span></span>  
  
-   <span data-ttu-id="c6ceb-134">System.Runtime.CompilerServices.CompilationRelaxationsAttribute</span><span class="sxs-lookup"><span data-stu-id="c6ceb-134">System.Runtime.CompilerServices.CompilationRelaxationsAttribute</span></span>  
  
-   <span data-ttu-id="c6ceb-135">System.Runtime.Remoting.Contexts.ContextAttribute</span><span class="sxs-lookup"><span data-stu-id="c6ceb-135">System.Runtime.Remoting.Contexts.ContextAttribute</span></span>  
  
-   <span data-ttu-id="c6ceb-136">System.Runtime.Remoting.Contexts.SynchronizationAttribute</span><span class="sxs-lookup"><span data-stu-id="c6ceb-136">System.Runtime.Remoting.Contexts.SynchronizationAttribute</span></span>  
  
-   <span data-ttu-id="c6ceb-137">System.Runtime.InteropServices.DllImportAttribute</span><span class="sxs-lookup"><span data-stu-id="c6ceb-137">System.Runtime.InteropServices.DllImportAttribute</span></span>  
  
-   <span data-ttu-id="c6ceb-138">System.Security.Permissions.CodeAccessSecurityAttribute</span><span class="sxs-lookup"><span data-stu-id="c6ceb-138">System.Security.Permissions.CodeAccessSecurityAttribute</span></span>  
  
-   <span data-ttu-id="c6ceb-139">System.Security.SuppressUnmanagedCodeSecurityAttribute</span><span class="sxs-lookup"><span data-stu-id="c6ceb-139">System.Security.SuppressUnmanagedCodeSecurityAttribute</span></span>  
  
-   <span data-ttu-id="c6ceb-140">System.Security.UnverifiableCodeAttribute</span><span class="sxs-lookup"><span data-stu-id="c6ceb-140">System.Security.UnverifiableCodeAttribute</span></span>  
  
-   <span data-ttu-id="c6ceb-141">System.STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="c6ceb-141">System.STAThreadAttribute</span></span>  
  
-   <span data-ttu-id="c6ceb-142">System.ThreadStaticAttribute</span><span class="sxs-lookup"><span data-stu-id="c6ceb-142">System.ThreadStaticAttribute</span></span>  
  
### <a name="safe"></a><span data-ttu-id="c6ceb-143">SAFE</span><span class="sxs-lookup"><span data-stu-id="c6ceb-143">SAFE</span></span>  
  
-   <span data-ttu-id="c6ceb-144">Toutes les conditions d'assembly `EXTERNAL_ACCESS` sont vérifiées.</span><span class="sxs-lookup"><span data-stu-id="c6ceb-144">All `EXTERNAL_ACCESS` assembly conditions are checked.</span></span>  
  
## <a name="runtime-checks"></a><span data-ttu-id="c6ceb-145">Contrôles d'exécution</span><span class="sxs-lookup"><span data-stu-id="c6ceb-145">Runtime Checks</span></span>  
 <span data-ttu-id="c6ceb-146">Pendant l'exécution, les conditions suivantes sont vérifiées pour l'assembly de code.</span><span class="sxs-lookup"><span data-stu-id="c6ceb-146">At runtime, the code assembly is checked for the following conditions.</span></span> <span data-ttu-id="c6ceb-147">Si l'une de ces conditions est remplie, le code managé n'est pas autorisé à s'exécuter et une exception est levée.</span><span class="sxs-lookup"><span data-stu-id="c6ceb-147">If any of these conditions are found, the managed code will not be allowed to run and an exception will be thrown.</span></span>  
  
### <a name="unsafe"></a><span data-ttu-id="c6ceb-148">UNSAFE</span><span class="sxs-lookup"><span data-stu-id="c6ceb-148">UNSAFE</span></span>  
 <span data-ttu-id="c6ceb-149">Le chargement d’un assembly, qu’il soit explicitement en appelant la `System.Reflection.Assembly.Load()` méthode à partir d’un tableau d’octets, ou implicitement par le biais de l’utilisation de l' `Reflection.Emit` espace de noms, n’est pas autorisé.</span><span class="sxs-lookup"><span data-stu-id="c6ceb-149">Loading an assembly-either explicitly by calling the `System.Reflection.Assembly.Load()` method from a byte array, or implicitly through the use of `Reflection.Emit` namespace-is not permitted.</span></span>  
  
### <a name="external_access"></a><span data-ttu-id="c6ceb-150">EXTERNAL_ACCESS</span><span class="sxs-lookup"><span data-stu-id="c6ceb-150">EXTERNAL_ACCESS</span></span>  
 <span data-ttu-id="c6ceb-151">Toutes les conditions `UNSAFE` sont vérifiées.</span><span class="sxs-lookup"><span data-stu-id="c6ceb-151">All `UNSAFE` conditions are checked.</span></span>  
  
 <span data-ttu-id="c6ceb-152">Tous les types et méthodes annotés avec les valeurs d'attribut de protection de l'hôte suivantes dans la liste d'assemblys prise en charge sont interdits.</span><span class="sxs-lookup"><span data-stu-id="c6ceb-152">All types and methods annotated with the following host protection attribute (HPA) values in the supported list of assemblies are disallowed.</span></span>  
  
-   <span data-ttu-id="c6ceb-153">SelfAffectingProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="c6ceb-153">SelfAffectingProcessMgmt</span></span>  
  
-   <span data-ttu-id="c6ceb-154">SelfAffectingThreading</span><span class="sxs-lookup"><span data-stu-id="c6ceb-154">SelfAffectingThreading</span></span>  
  
-   <span data-ttu-id="c6ceb-155">Synchronization</span><span class="sxs-lookup"><span data-stu-id="c6ceb-155">Synchronization</span></span>  
  
-   <span data-ttu-id="c6ceb-156">SharedState</span><span class="sxs-lookup"><span data-stu-id="c6ceb-156">SharedState</span></span>  
  
-   <span data-ttu-id="c6ceb-157">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="c6ceb-157">ExternalProcessMgmt</span></span>  
  
-   <span data-ttu-id="c6ceb-158">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="c6ceb-158">ExternalThreading</span></span>  
  
-   <span data-ttu-id="c6ceb-159">SecurityInfrastructure</span><span class="sxs-lookup"><span data-stu-id="c6ceb-159">SecurityInfrastructure</span></span>  
  
-   <span data-ttu-id="c6ceb-160">MayLeakOnAbort</span><span class="sxs-lookup"><span data-stu-id="c6ceb-160">MayLeakOnAbort</span></span>  
  
-   <span data-ttu-id="c6ceb-161">UI</span><span class="sxs-lookup"><span data-stu-id="c6ceb-161">UI</span></span>  
  
 <span data-ttu-id="c6ceb-162">Pour plus d’informations sur hPa et pour obtenir la liste des types et des membres non autorisés dans les assemblys pris en charge, consultez attributs de protection de l' [hôte et programmation](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md)de l’intégration du CLR.</span><span class="sxs-lookup"><span data-stu-id="c6ceb-162">For more information about HPAs and a list of disallowed types and members in the supported assemblies, see [Host Protection Attributes and CLR Integration Programming](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md).</span></span>  
  
### <a name="safe"></a><span data-ttu-id="c6ceb-163">SAFE</span><span class="sxs-lookup"><span data-stu-id="c6ceb-163">SAFE</span></span>  
 <span data-ttu-id="c6ceb-164">Toutes les conditions `EXTERNAL_ACCESS` sont vérifiées.</span><span class="sxs-lookup"><span data-stu-id="c6ceb-164">All `EXTERNAL_ACCESS` conditions are checked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6ceb-165">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c6ceb-165">See Also</span></span>  
 <span data-ttu-id="c6ceb-166">[Bibliothèques de .NET Framework prises en charge](supported-net-framework-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="c6ceb-166">[Supported .NET Framework Libraries](supported-net-framework-libraries.md) </span></span>  
 <span data-ttu-id="c6ceb-167">[Sécurité d’accès du code d’intégration du CLR](../security/clr-integration-code-access-security.md) </span><span class="sxs-lookup"><span data-stu-id="c6ceb-167">[CLR Integration Code Access Security](../security/clr-integration-code-access-security.md) </span></span>  
 <span data-ttu-id="c6ceb-168">[Attributs de protection de l’hôte et programmation de l’intégration du CLR](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md) </span><span class="sxs-lookup"><span data-stu-id="c6ceb-168">[Host Protection Attributes and CLR Integration Programming](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md) </span></span>  
 [<span data-ttu-id="c6ceb-169">Création d'un assembly</span><span class="sxs-lookup"><span data-stu-id="c6ceb-169">Creating an Assembly</span></span>](../assemblies/creating-an-assembly.md)  
  
  
