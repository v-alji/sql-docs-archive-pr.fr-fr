---
title: Conception d’assemblys | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- designing assemblies [SQL Server]
- assemblies [CLR integration], designing
ms.assetid: 9c07f706-6508-41aa-a4d7-56ce354f9061
author: rothja
ms.author: jroth
ms.openlocfilehash: 785ab80a529140a52ec18ef96ccaaeafd03698cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704191"
---
# <a name="designing-assemblies"></a><span data-ttu-id="74797-102">Conception d'assemblys</span><span class="sxs-lookup"><span data-stu-id="74797-102">Designing Assemblies</span></span>
  <span data-ttu-id="74797-103">Cette rubrique décrit les facteurs suivants, à prendre en considération lors de la conception d'assemblys :</span><span class="sxs-lookup"><span data-stu-id="74797-103">This topic describes the following factors you should consider when you design assemblies:</span></span>  
  
-   <span data-ttu-id="74797-104">Empaqueter des assemblys</span><span class="sxs-lookup"><span data-stu-id="74797-104">Packaging assemblies</span></span>  
  
-   <span data-ttu-id="74797-105">Gestion de la sécurité des assemblys</span><span class="sxs-lookup"><span data-stu-id="74797-105">Managing assembly security</span></span>  
  
-   <span data-ttu-id="74797-106">Restrictions sur les assemblys</span><span class="sxs-lookup"><span data-stu-id="74797-106">Restrictions on assemblies</span></span>  
  
## <a name="packaging-assemblies"></a><span data-ttu-id="74797-107">Empaquetage d'assemblys</span><span class="sxs-lookup"><span data-stu-id="74797-107">Packaging Assemblies</span></span>  
 <span data-ttu-id="74797-108">Un assembly peut contenir des fonctionnalités pour plusieurs types ou routines [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans ses classes et méthodes.</span><span class="sxs-lookup"><span data-stu-id="74797-108">An assembly can contain functionality for more than one [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] routine or type in its classes and methods.</span></span> <span data-ttu-id="74797-109">En règle générale, il est opportun d'empaqueter les fonctionnalités de routines qui réalisent des fonctions apparentées dans le même assembly, notamment si ces routines partagent des classes dont les méthodes s'appellent les unes les autres.</span><span class="sxs-lookup"><span data-stu-id="74797-109">Most of the time, it makes sense to package the functionality of routines that perform related functions within the same assembly, especially if these routines share classes whose methods call one another.</span></span> <span data-ttu-id="74797-110">Par exemple, les classes qui exécutent des tâches de gestion d'entrée de données pour les déclencheurs CLR (Common Language Runtime) et les procédures stockées CLR peuvent être empaquetées dans le même assembly.</span><span class="sxs-lookup"><span data-stu-id="74797-110">For example, classes that perform data entry management tasks for common language runtime (CLR) triggers and CLR stored procedures can be packaged in the same assembly.</span></span> <span data-ttu-id="74797-111">En effet, les méthodes de ces classes sont davantage susceptibles de s'appeler les unes les autres que d'invoquer les méthodes de tâches moins apparentées.</span><span class="sxs-lookup"><span data-stu-id="74797-111">This is because the methods for these classes are more likely to call each other than those of less related tasks.</span></span>  
  
 <span data-ttu-id="74797-112">Lorsque vous empaquetez du code en assembly, vous devez prendre en considération les points suivants :</span><span class="sxs-lookup"><span data-stu-id="74797-112">When you are packaging code into assembly, you should consider the following:</span></span>  
  
-   <span data-ttu-id="74797-113">Les types et index CLR définis par l'utilisateur qui dépendent de fonctions CLR définies par l'utilisateur peuvent amener des données persistantes à figurer dans la base de données qui repose sur l'assembly.</span><span class="sxs-lookup"><span data-stu-id="74797-113">CLR user-defined types and indexes that depend on CLR user-defined functions can cause persisted data to be in the database that depends on the assembly.</span></span> <span data-ttu-id="74797-114">La modification du code d'un assembly est souvent plus complexe lorsque la base de données contient des données persistantes dépendant de l'assembly.</span><span class="sxs-lookup"><span data-stu-id="74797-114">Modifying the code of an assembly is frequently more complex when there is persisted data that depends on the assembly in the database.</span></span> <span data-ttu-id="74797-115">Par conséquent, il est généralement préférable de séparer le code sur lequel reposent les dépendances des données persistantes (par exemple des types et des index définis par l'utilisateur utilisant des fonctions définies par l'utilisateur) du code dépourvu de ces dépendances de données persistantes.</span><span class="sxs-lookup"><span data-stu-id="74797-115">Therefore, it is generally better to separate code on which persisted data dependencies rely (such as user-defined types and indexes using user-defined functions) from code that does not have such persisted data dependencies.</span></span> <span data-ttu-id="74797-116">Pour plus d’informations, consultez [implémentation d’assemblys](assemblies-implementing.md) et [ALTER assembly &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-assembly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="74797-116">For more information, see [Implementing Assemblies](assemblies-implementing.md) and [ALTER ASSEMBLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-assembly-transact-sql).</span></span>  
  
-   <span data-ttu-id="74797-117">Si une portion de code managé requiert une autorisation plus élevée, il est préférable de la placer dans un assembly distinct du code qui ne requiert pas une telle autorisation.</span><span class="sxs-lookup"><span data-stu-id="74797-117">If a piece of managed code requires higher permission, it is better to separate that code into a separate assembly from code that does not require higher permission.</span></span>  
  
## <a name="managing-assembly-security"></a><span data-ttu-id="74797-118">Gestion de la sécurité des assemblys</span><span class="sxs-lookup"><span data-stu-id="74797-118">Managing Assembly Security</span></span>  
 <span data-ttu-id="74797-119">Vous pouvez contrôler la façon dont un assembly peut accéder aux ressources protégées par la sécurité d’accès du code .NET lorsqu’il exécute du code managé.</span><span class="sxs-lookup"><span data-stu-id="74797-119">You can control how much an assembly can access resources protected by .NET Code Access Security when it runs managed code.</span></span> <span data-ttu-id="74797-120">Pour ce faire, vous spécifiez l'un des trois jeux d'autorisations lorsque vous créez ou modifiez un assembly : SAFE, EXTERNAL_ACCESS ou UNSAFE.</span><span class="sxs-lookup"><span data-stu-id="74797-120">You do this by specifying one of three permission sets when you create or modify an assembly: SAFE, EXTERNAL_ACCESS, or UNSAFE.</span></span>  
  
### <a name="safe"></a><span data-ttu-id="74797-121">SAFE</span><span class="sxs-lookup"><span data-stu-id="74797-121">SAFE</span></span>  
 <span data-ttu-id="74797-122">SAFE est le jeu d'autorisations par défaut et il s'agit du plus restrictif.</span><span class="sxs-lookup"><span data-stu-id="74797-122">SAFE is the default permission set and it is the most restrictive.</span></span> <span data-ttu-id="74797-123">Le code exécuté par un assembly avec des autorisations SAFE ne peut pas accéder aux ressources système externes telles que les fichiers, le réseau, les variables d'environnement ou le Registre.</span><span class="sxs-lookup"><span data-stu-id="74797-123">Code run by an assembly with SAFE permissions cannot access external system resources such as files, the network, environment variables, or the registry.</span></span> <span data-ttu-id="74797-124">Le code SAFE peut accéder aux données des bases de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] locales ou réaliser des calculs et une logique métier qui ne nécessitent pas l'accès aux ressources situées hors de ces bases de données.</span><span class="sxs-lookup"><span data-stu-id="74797-124">SAFE code can access data from the local [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases or perform computations and business logic that do not involve accessing resources outside the local databases.</span></span>  
  
 <span data-ttu-id="74797-125">La plupart des assemblys réalisent des calculs et des tâches de gestion de données sans devoir accéder aux ressources situées hors de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74797-125">Most assemblies perform computation and data management tasks without having to access resources outside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="74797-126">Par conséquent, il est recommandé d'utiliser SAFE comme jeu d'autorisations des assemblys.</span><span class="sxs-lookup"><span data-stu-id="74797-126">Therefore, we recommend SAFE as the assembly permission set.</span></span>  
  
### <a name="external_access"></a><span data-ttu-id="74797-127">EXTERNAL_ACCESS</span><span class="sxs-lookup"><span data-stu-id="74797-127">EXTERNAL_ACCESS</span></span>  
 <span data-ttu-id="74797-128">EXTERNAL_ACCESS permet aux assemblys d'accéder à certaines ressources système externes telles que les fichiers, les réseaux, les services Web, les variables d'environnement et le Registre.</span><span class="sxs-lookup"><span data-stu-id="74797-128">EXTERNAL_ACCESS allows for assemblies to access certain external system resources such as files, networks, Web services, environmental variables, and the registry.</span></span> <span data-ttu-id="74797-129">Seules les connexions [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] bénéficiant d'autorisations EXTERNAL ACCESS peuvent créer des assemblys EXTERNAL_ACCESS.</span><span class="sxs-lookup"><span data-stu-id="74797-129">Only [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins with EXTERNAL ACCESS permissions can create EXTERNAL_ACCESS assemblies.</span></span>  
  
 <span data-ttu-id="74797-130">Les assemblys SAFE et EXTERNAL_ACCESS ne peuvent contenir que du code de type sécurisé.</span><span class="sxs-lookup"><span data-stu-id="74797-130">SAFE and EXTERNAL_ACCESS assemblies can contain only code that is verifiably type-safe.</span></span> <span data-ttu-id="74797-131">Cela signifie que ces assemblys peuvent uniquement accéder à des classes par le biais de points d'entrée correctement définis et valides pour la définition de type.</span><span class="sxs-lookup"><span data-stu-id="74797-131">This means that these assemblies can only access classes through well-defined entry points that are valid for the type definition.</span></span> <span data-ttu-id="74797-132">Par conséquent, ils ne peuvent pas accéder arbitrairement à des zones de mémoire tampon non détenues par le code.</span><span class="sxs-lookup"><span data-stu-id="74797-132">Therefore, they cannot arbitrarily access memory buffers not owned by the code.</span></span> <span data-ttu-id="74797-133">En outre, ils ne peuvent pas réaliser des opérations susceptibles de nuire à la robustesse du processus [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74797-133">Additionally, they cannot perform operations that might have an adverse effect on the robustness of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] process.</span></span>  
  
### <a name="unsafe"></a><span data-ttu-id="74797-134">UNSAFE</span><span class="sxs-lookup"><span data-stu-id="74797-134">UNSAFE</span></span>  
 <span data-ttu-id="74797-135">UNSAFE accorde aux assemblys un accès non restreint aux ressources, à la fois à l'intérieur et à l'extérieur de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74797-135">UNSAFE gives assemblies unrestricted access to resources, both within and outside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="74797-136">Le code exécuté depuis un assembly UNSAFE peut appeler du code non managé.</span><span class="sxs-lookup"><span data-stu-id="74797-136">Code that is running from within an UNSAFE assembly can call unmanaged code.</span></span>  
  
 <span data-ttu-id="74797-137">En outre, la spécification de UNSAFE permet au code de l'assembly de réaliser des opérations considérées comme étant de type non sécurisé par le vérificateur CLR.</span><span class="sxs-lookup"><span data-stu-id="74797-137">Also, specifying UNSAFE allows for the code in the assembly to perform operations that are considered type-unsafe by the CLR verifier.</span></span> <span data-ttu-id="74797-138">Ces opérations sont susceptibles d'accéder de manière incontrôlée aux zones de tampon mémoire de l'espace réservé aux processus [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74797-138">These operations can potentially access memory buffers in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] process space in an uncontrolled manner.</span></span> <span data-ttu-id="74797-139">Les assemblys UNSAFE peuvent également corrompre le système de sécurité de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ou de CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="74797-139">UNSAFE assemblies can also potentially subvert the security system of either [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or the common language runtime.</span></span> <span data-ttu-id="74797-140">Les autorisations UNSAFE ne doivent être accordées par des administrateurs ou des développeurs expérimentés qu'aux assemblys hautement approuvés.</span><span class="sxs-lookup"><span data-stu-id="74797-140">UNSAFE permissions should be granted only to highly trusted assemblies by experienced developers or administrators.</span></span> <span data-ttu-id="74797-141">Seuls les membres du rôle serveur fixe **sysadmin** peuvent créer des assemblys non sécurisés.</span><span class="sxs-lookup"><span data-stu-id="74797-141">Only members of the **sysadmin** fixed server role can create UNSAFE assemblies.</span></span>  
  
## <a name="restrictions-on-assemblies"></a><span data-ttu-id="74797-142">Restrictions associées aux assemblys</span><span class="sxs-lookup"><span data-stu-id="74797-142">Restrictions on Assemblies</span></span>  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="74797-143">impose certaines restrictions au code managé des assemblys afin que ceux-ci puissent s'exécuter de manière fiable et évolutive.</span><span class="sxs-lookup"><span data-stu-id="74797-143">puts certain restrictions on managed code in assemblies to make sure that they can run in a reliable and scalable manner.</span></span> <span data-ttu-id="74797-144">Cela signifie que certaines opérations pouvant compromettre la robustesse du serveur ne sont pas autorisées dans les assemblys SAFE et EXTERNAL_ACCESS.</span><span class="sxs-lookup"><span data-stu-id="74797-144">This means that certain operations that can compromise the robustness of the server are not permitted in SAFE and EXTERNAL_ACCESS assemblies.</span></span>  
  
### <a name="disallowed-custom-attributes"></a><span data-ttu-id="74797-145">Attributs personnalisés interdits</span><span class="sxs-lookup"><span data-stu-id="74797-145">Disallowed Custom Attributes</span></span>  
 <span data-ttu-id="74797-146">Les assemblys ne peuvent pas être annotés avec les attributs personnalisés suivants :</span><span class="sxs-lookup"><span data-stu-id="74797-146">Assemblies cannot be annotated with the following custom attributes:</span></span>  
  
```  
System.ContextStaticAttribute  
System.MTAThreadAttribute  
System.Runtime.CompilerServices.MethodImplAttribute  
System.Runtime.CompilerServices.CompilationRelaxationsAttribute  
System.Runtime.Remoting.Contexts.ContextAttribute  
System.Runtime.Remoting.Contexts.SynchronizationAttribute  
System.Runtime.InteropServices.DllImportAttribute   
System.Security.Permissions.CodeAccessSecurityAttribute  
System.STAThreadAttribute  
System.ThreadStaticAttribute  
```  
  
 <span data-ttu-id="74797-147">En outre, les assemblys SAFE et EXTERNAL_ACCESS ne peuvent pas être annotés avec les attributs personnalisés suivants :</span><span class="sxs-lookup"><span data-stu-id="74797-147">Additionally, SAFE and EXTERNAL_ACCESS assemblies cannot be annotated with the following custom attributes:</span></span>  
  
```  
System.Security.SuppressUnmanagedCodeSecurityAttribute  
System.Security.UnverifiableCodeAttribute  
```  
  
### <a name="disallowed-net-framework-apis"></a><span data-ttu-id="74797-148">API .NET Framework interdites</span><span class="sxs-lookup"><span data-stu-id="74797-148">Disallowed .NET Framework APIs</span></span>  
 <span data-ttu-id="74797-149">Toute [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] API annotée avec l’un des **attributs HostProtectionAttributes** interdits ne peut pas être appelée à partir d’assemblys SAFE et EXTERNAL_ACCESS.</span><span class="sxs-lookup"><span data-stu-id="74797-149">Any [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] API that is annotated with one of the disallowed **HostProtectionAttributes** cannot be called from SAFE and EXTERNAL_ACCESS assemblies.</span></span>  
  
```  
eSelfAffectingProcessMgmt  
eSelfAffectingThreading  
eSynchronization  
eSharedState   
eExternalProcessMgmt  
eExternalThreading  
eSecurityInfrastructure  
eMayLeakOnAbort  
eUI  
```  
  
### <a name="supported-net-framework-assemblies"></a><span data-ttu-id="74797-150">Assemblys .NET Framework pris en charge</span><span class="sxs-lookup"><span data-stu-id="74797-150">Supported .NET Framework Assemblies</span></span>  
 <span data-ttu-id="74797-151">Tout assembly référencé par votre assembly personnalisé doit être chargé dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à l'aide de CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="74797-151">Any assembly that is referenced by your custom assembly must be loaded into [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using CREATE ASSEMBLY.</span></span> <span data-ttu-id="74797-152">Les assemblys [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] ci-dessous sont déjà chargés dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] et peuvent, par conséquent, être référencés par les assemblys personnalisés sans qu'il soit nécessaire d'utiliser CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="74797-152">The following [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] assemblies are already loaded into [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and, therefore, can be referenced by custom assemblies without having to use CREATE ASSEMBLY.</span></span>  
  
```  
custommarshallers.dll  
Microsoft.visualbasic.dll  
Microsoft.visualc.dll  
mscorlib.dll  
system.data.dll  
System.Data.SqlXml.dll  
system.dll  
system.security.dll  
system.web.services.dll  
system.xml.dll  
System.Transactions  
System.Data.OracleClient  
System.Configuration  
```  
  
## <a name="see-also"></a><span data-ttu-id="74797-153">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="74797-153">See Also</span></span>  
 <span data-ttu-id="74797-154">[Assemblys &#40;Moteur de base de données&#41;](../../relational-databases/clr-integration/assemblies-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="74797-154">[Assemblies &#40;Database Engine&#41;](../../relational-databases/clr-integration/assemblies-database-engine.md) </span></span>  
 [<span data-ttu-id="74797-155">Sécurité de l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="74797-155">CLR Integration Security</span></span>](security/clr-integration-security.md)  
  
  
