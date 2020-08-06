---
title: Création d’un assembly | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- creating assemblies
- UNSAFE assemblies
- CREATE ASSEMBLY statement
- SAFE assemblies
- EXTERNAL_ACCESS assemblies
- assemblies [CLR integration], creating
ms.assetid: a2bc503d-b6b2-4963-8beb-c11c323f18e0
author: rothja
ms.author: jroth
ms.openlocfilehash: 9dea1f8fe57691f05274cac353a1064420309e06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704167"
---
# <a name="creating-an-assembly"></a><span data-ttu-id="2cd8f-102">Création d'un assembly</span><span class="sxs-lookup"><span data-stu-id="2cd8f-102">Creating an Assembly</span></span>
  <span data-ttu-id="2cd8f-103">Les objets de base de données managés, tels que les procédures stockées ou les déclencheurs, sont successivement compilés et déployés dans des unités appelées « assemblys ».</span><span class="sxs-lookup"><span data-stu-id="2cd8f-103">Managed database objects, such as stored procedures or triggers, are compiled and then deployed in units called an assembly.</span></span> <span data-ttu-id="2cd8f-104">Les assemblys DLL managés doivent être enregistrés dans [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cd8f-104">Managed DLL assemblies must be registered in [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] before the functionality the assembly provides can be used.</span></span> <span data-ttu-id="2cd8f-105">Pour enregistrer un assembly dans une base de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , utilisez l'instruction CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-105">To register an assembly in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database, use the CREATE ASSEMBLY statement.</span></span> <span data-ttu-id="2cd8f-106">Cette rubrique explique comment enregistrer un assembly dans une base de données à l'aide de l'instruction CREATE ASSEMBLY, puis comment spécifier les paramètres de sécurité de l'assembly.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-106">This topic discusses how to register an assembly in a database using the CREATE ASSEMBLY statement, and how to specify the security settings for the assembly.</span></span>  
  
## <a name="the-create-assembly-statement"></a><span data-ttu-id="2cd8f-107">Instruction CREATE ASSEMBLY</span><span class="sxs-lookup"><span data-stu-id="2cd8f-107">The CREATE ASSEMBLY Statement</span></span>  
 <span data-ttu-id="2cd8f-108">L'instruction CREATE ASSEMBLY permet de créer un assembly dans une base de données.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-108">The CREATE ASSEMBLY statement is used to create an assembly in a database.</span></span> <span data-ttu-id="2cd8f-109">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="2cd8f-109">Here is an example:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll';  
```  
  
 <span data-ttu-id="2cd8f-110">La clause FROM spécifie le nom du chemin d'accès de l'assembly à créer.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-110">The FROM clause specifies the pathname of the assembly to create.</span></span> <span data-ttu-id="2cd8f-111">Ce chemin d'accès peut être soit un chemin UNC (Universal Naming Convention), soit le chemin d'accès d'un fichier physique stocké localement sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-111">This path can either be a Universal Naming Convention (UNC) path or a physical file path that is local to the machine.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="2cd8f-112">n'autorise pas l'inscription de différentes versions d'un assembly avec le même nom, la même culture et la même clé publique.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-112">does not allow registering different versions of an assembly with the same name, culture and public key.</span></span>  
  
 <span data-ttu-id="2cd8f-113">Il est possible de créer des assemblys qui référencent d'autres assemblys.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-113">It is possible to create assemblies that reference other assemblies.</span></span> <span data-ttu-id="2cd8f-114">Lorsqu’un assembly est créé dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , crée également les assemblys référencés par l’assembly de niveau racine, si les assemblys référencés ne sont pas déjà créés dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-114">When an assembly is created in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] also creates the assemblies referenced by the root-level assembly, if the referenced assemblies are not already created into the database.</span></span>  
  
 <span data-ttu-id="2cd8f-115">Les utilisateurs ou les rôles d'utilisateurs de base de données se voient accorder des autorisations pour créer, et de ce fait acquérir, des assemblys dans une base de données.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-115">Database users or user roles are given permissions to create, and thereby own, assemblies in a database.</span></span> <span data-ttu-id="2cd8f-116">Pour être en mesure de créer des assemblys, l'utilisateur ou le rôle d'utilisateur de base de données doit bénéficier de l'autorisation CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-116">In order to create assemblies, the database user or role should have the CREATE ASSEMBLY permission.</span></span>  
  
 <span data-ttu-id="2cd8f-117">Un assembly peut parvenir à référencer d'autres assemblys uniquement si :</span><span class="sxs-lookup"><span data-stu-id="2cd8f-117">An assembly can only succeed in referencing other assemblies if:</span></span>  
  
-   <span data-ttu-id="2cd8f-118">l'assembly appelé ou référencé est possédé par le même utilisateur ou rôle ;</span><span class="sxs-lookup"><span data-stu-id="2cd8f-118">The assembly that is called or referenced is owned by the same user or role.</span></span>  
  
-   <span data-ttu-id="2cd8f-119">l'assembly appelé ou référencé a été créé dans la même base de données.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-119">The assembly that is called or referenced was created in the same database.</span></span>  
  
## <a name="specifying-security-when-creating-assemblies"></a><span data-ttu-id="2cd8f-120">Définition de la sécurité lors de la création d'assemblys</span><span class="sxs-lookup"><span data-stu-id="2cd8f-120">Specifying Security When Creating Assemblies</span></span>  
 <span data-ttu-id="2cd8f-121">Lorsque vous créez un assembly dans une base de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], vous pouvez spécifier un des trois niveaux différents de sécurité dans lesquels votre code peut être exécuté : `SAFE`, `EXTERNAL_ACCESS` ou `UNSAFE`.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-121">When creating an assembly into a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database, you can specify one of three different levels of security in which your code can run: `SAFE`, `EXTERNAL_ACCESS`, or `UNSAFE`.</span></span> <span data-ttu-id="2cd8f-122">Au moment de l'exécution de l'instruction `CREATE ASSEMBLY`, l'assembly de code est soumis à certains contrôles qui peuvent entraîner l'échec de l'enregistrement de l'assembly sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-122">When the `CREATE ASSEMBLY` statement is run, certain checks are performed on the code assembly which may cause the assembly to fail to register on the server.</span></span> <span data-ttu-id="2cd8f-123">Pour plus d'informations, consultez l'exemple d'emprunt d'identité sur [CodePlex](https://msftengprodsamples.codeplex.com/).</span><span class="sxs-lookup"><span data-stu-id="2cd8f-123">For more information, see the Impersonation sample on [CodePlex](https://msftengprodsamples.codeplex.com/).</span></span>  
  
 <span data-ttu-id="2cd8f-124">`SAFE` est le jeu d'autorisations par défaut et fonctionne pour la majorité des scénarios.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-124">`SAFE` is the default permission set and works for the majority of scenarios.</span></span> <span data-ttu-id="2cd8f-125">Pour spécifier un niveau de sécurité donné, vous devez modifier la syntaxe de l'instruction CREATE ASSEMBLY comme suit :</span><span class="sxs-lookup"><span data-stu-id="2cd8f-125">To specify a given security level, you modify the syntax of the CREATE ASSEMBLY statement as follows:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll'  
WITH PERMISSION_SET = SAFE;  
```  
  
 <span data-ttu-id="2cd8f-126">Il est également possible de créer un assembly à l'aide du jeu d'autorisations `SAFE` par simple omission de la troisième ligne de code ci-dessus :</span><span class="sxs-lookup"><span data-stu-id="2cd8f-126">It is also possible to create an assembly with the `SAFE` permission set by simply omitting the third line of code above:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll';  
```  
  
 <span data-ttu-id="2cd8f-127">Lorsque le code dans un assembly s'exécute sous le jeu d'autorisations `SAFE`, tout calcul ou accès aux données sur le serveur ne peut avoir lieu que par l'entremise du fournisseur managé in-process.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-127">When code in an assembly runs under the `SAFE` permission set, it can only do computation and data access within the server through the in-process managed provider.</span></span>  
  
### <a name="creating-external_access-and-unsafe-assemblies"></a><span data-ttu-id="2cd8f-128">Création d'assemblys EXTERNAL_ACCESS et UNSAFE</span><span class="sxs-lookup"><span data-stu-id="2cd8f-128">Creating EXTERNAL_ACCESS and UNSAFE Assemblies</span></span>  
 <span data-ttu-id="2cd8f-129">`EXTERNAL_ACCESS` propose des scénarios dans lesquels le code doit accéder à des ressources externes au serveur, tel que des fichiers, le réseau, le Registre et des variables d'environnement.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-129">`EXTERNAL_ACCESS` addresses scenarios in which the code needs to access resources outside the server, such as files, network, registry, and environment variables.</span></span> <span data-ttu-id="2cd8f-130">Lorsque le serveur accède à une ressource externe, il emprunte l'identité du contexte de sécurité de l'utilisateur appelant le code managé.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-130">Whenever the server accesses an external resource, it impersonates the security context of the user calling the managed code.</span></span>  
  
 <span data-ttu-id="2cd8f-131">L'autorisation de code `UNSAFE` convient dans des situations où la sécurité d'un assembly ne peut être vérifiée ou exige un accès supplémentaire à des ressources restreintes, telles que l'API Win32 [!INCLUDE[msCoName](../../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2cd8f-131">`UNSAFE` code permission is for those situations in which an assembly is not verifiably safe or requires additional access to restricted resources, such as the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Win32 API.</span></span>  
  
 <span data-ttu-id="2cd8f-132">Pour la création d'un assembly `EXTERNAL_ACCESS` ou `UNSAFE` dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], l'une des deux conditions suivantes doit être remplie :</span><span class="sxs-lookup"><span data-stu-id="2cd8f-132">To create an `EXTERNAL_ACCESS` or `UNSAFE` assembly in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], one of the following two conditions must be met:</span></span>  
  
1.  <span data-ttu-id="2cd8f-133">L'assembly est signé avec un nom fort ou porte une signature Authenticode avec certificat.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-133">The assembly is strong name signed or Authenticode signed with a certificate.</span></span> <span data-ttu-id="2cd8f-134">Ce nom fort (ou certificat) est créé dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en tant que clé asymétrique (ou certificat) et dispose d'une connexion correspondante avec l'autorisation `EXTERNAL ACCESS ASSEMBLY` (pour les assemblys à accès externe) ou l'autorisation `UNSAFE ASSEMBLY` (pour les assemblys non sécurisés).</span><span class="sxs-lookup"><span data-stu-id="2cd8f-134">This strong name (or certificate) is created inside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as an asymmetric key (or certificate), and has a corresponding login with `EXTERNAL ACCESS ASSEMBLY` permission (for external access assemblies) or `UNSAFE ASSEMBLY` permission (for unsafe assemblies).</span></span>  
  
2.  <span data-ttu-id="2cd8f-135">Le propriétaire de la base de données (DBO) dispose de l' `EXTERNAL ACCESS ASSEMBLY` autorisation (pour les `EXTERNAL ACCESS` assemblys) ou `UNSAFE ASSEMBLY` (pour `UNSAFE` les assemblys), et la [propriété de base](../../security/trustworthy-database-property.md) de données Trustworthy de la base de données a la valeur `ON` .</span><span class="sxs-lookup"><span data-stu-id="2cd8f-135">The database owner (DBO) has `EXTERNAL ACCESS ASSEMBLY` (for `EXTERNAL ACCESS` assemblies) or `UNSAFE ASSEMBLY` (for `UNSAFE` assemblies) permission, and the database has the [TRUSTWORTHY Database Property](../../security/trustworthy-database-property.md) set to `ON`.</span></span>  
  
 <span data-ttu-id="2cd8f-136">Les deux conditions mentionnées ci-dessus sont également vérifiées au moment du chargement de l'assembly (exécution incluse).</span><span class="sxs-lookup"><span data-stu-id="2cd8f-136">The two conditions listed above are also checked at assembly load time (which includes execution).</span></span> <span data-ttu-id="2cd8f-137">Une des conditions doit au minimum être satisfaite pour le chargement de l'assembly.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-137">At least one of the conditions must be met in order to load the assembly.</span></span>  
  
 <span data-ttu-id="2cd8f-138">Nous recommandons que la [propriété de base de données Trustworthy](../../security/trustworthy-database-property.md) sur une base de données ne soit pas définie sur `ON` uniquement pour exécuter le code Common Language Runtime (CLR) dans le processus serveur.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-138">We recommend that the [TRUSTWORTHY Database Property](../../security/trustworthy-database-property.md) on a database not be set to `ON` only to run common language runtime (CLR) code in the server process.</span></span> <span data-ttu-id="2cd8f-139">Il est préférable, à la place, de créer une clé asymétrique à partir du fichier d'assembly dans la base de données master.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-139">Instead, we recommend that an asymmetric key be created from the assembly file in the master database.</span></span> <span data-ttu-id="2cd8f-140">Une connexion mappée à cette clé asymétrique doit ensuite être créée. Cette connexion doit disposer de l'autorisation `EXTERNAL ACCESS ASSEMBLY` ou `UNSAFE ASSEMBLY`.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-140">A login mapped to this asymmetric key must then be created, and the login must be granted `EXTERNAL ACCESS ASSEMBLY` or `UNSAFE ASSEMBLY` permission.</span></span>  
  
 <span data-ttu-id="2cd8f-141">Les [!INCLUDE[tsql](../../../includes/tsql-md.md)] instructions suivantes avant d’exécuter l’instruction CREATE assembly.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-141">The following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements before running the CREATE ASSEMBLY statement.</span></span>  
  
```  
USE master;   
GO    
  
CREATE ASYMMETRIC KEY SQLCLRTestKey FROM EXECUTABLE FILE = 'C:\MyDBApp\SQLCLRTest.dll'     
CREATE LOGIN SQLCLRTestLogin FROM ASYMMETRIC KEY SQLCLRTestKey     
GRANT EXTERNAL ACCESS ASSEMBLY TO SQLCLRTestLogin;   
GO   
```  
  
> [!NOTE]  
>  <span data-ttu-id="2cd8f-142">Vous devez créer une connexion à associer à la clé asymétrique.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-142">You must create a new login to associate with the asymmetric key.</span></span> <span data-ttu-id="2cd8f-143">Cette connexion permet uniquement d'accorder des autorisations ; elle ne doit pas être associée à un utilisateur ni utilisée dans l'application.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-143">This login is only used to grant permissions; it does not have to be associated with a user, or used within the application.</span></span>  
  
 <span data-ttu-id="2cd8f-144">Pour créer un assembly `EXTERNAL ACCESS`, la personne chargée de le créer doit posséder l'autorisation `EXTERNAL ACCESS`.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-144">To create an `EXTERNAL ACCESS` assembly, the creator needs to have `EXTERNAL ACCESS` permission.</span></span> <span data-ttu-id="2cd8f-145">Elle est spécifiée au moment de créer l'assembly :</span><span class="sxs-lookup"><span data-stu-id="2cd8f-145">This is specified when creating the assembly:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll'  
WITH PERMISSION_SET = EXTERNAL_ACCESS;  
```  
  
 <span data-ttu-id="2cd8f-146">Les [!INCLUDE[tsql](../../../includes/tsql-md.md)] instructions suivantes avant d’exécuter l’instruction CREATE assembly.</span><span class="sxs-lookup"><span data-stu-id="2cd8f-146">The following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements before running the CREATE ASSEMBLY statement.</span></span>  
  
```  
USE master;   
GO    
  
CREATE ASYMMETRIC KEY SQLCLRTestKey FROM EXECUTABLE FILE = 'C:\MyDBApp\SQLCLRTest.dll';     
CREATE LOGIN SQLCLRTestLogin FROM ASYMMETRIC KEY SQLCLRTestKey ;    
GRANT UNSAFE ASSEMBLY TO SQLCLRTestLogin ;  
GO  
```  
  
 <span data-ttu-id="2cd8f-147">Pour préciser qu'un assembly est chargé avec l'autorisation `UNSAFE`, vous devez spécifier l'autorisation `UNSAFE` définie lors du chargement de l'assembly sur le serveur :</span><span class="sxs-lookup"><span data-stu-id="2cd8f-147">To specify that an assembly loads with `UNSAFE` permission, you specify the `UNSAFE` permission set when loading the assembly into the server:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll'  
WITH PERMISSION_SET = UNSAFE;  
```  
  
 <span data-ttu-id="2cd8f-148">Pour obtenir des informations détaillées sur les autorisations pour chacun de ces paramètres, consultez [CLR Integration Security](../security/clr-integration-security.md).</span><span class="sxs-lookup"><span data-stu-id="2cd8f-148">For more details about the permissions for each of the settings, see [CLR Integration Security](../security/clr-integration-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cd8f-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2cd8f-149">See Also</span></span>  
 <span data-ttu-id="2cd8f-150">[Gestion des assemblys d’intégration du CLR](managing-clr-integration-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="2cd8f-150">[Managing CLR Integration Assemblies](managing-clr-integration-assemblies.md) </span></span>  
 <span data-ttu-id="2cd8f-151">[Modification d’un assembly](altering-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="2cd8f-151">[Altering an Assembly](altering-an-assembly.md) </span></span>  
 <span data-ttu-id="2cd8f-152">[Suppression d’un assembly](dropping-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="2cd8f-152">[Dropping an Assembly](dropping-an-assembly.md) </span></span>  
 <span data-ttu-id="2cd8f-153">[Sécurité d’accès du code d’intégration du CLR](../security/clr-integration-code-access-security.md) </span><span class="sxs-lookup"><span data-stu-id="2cd8f-153">[CLR Integration Code Access Security](../security/clr-integration-code-access-security.md) </span></span>  
 <span data-ttu-id="2cd8f-154">[Propriété de base de données TRUSTWORTHY](../../security/trustworthy-database-property.md) </span><span class="sxs-lookup"><span data-stu-id="2cd8f-154">[TRUSTWORTHY Database Property](../../security/trustworthy-database-property.md) </span></span>  
 [<span data-ttu-id="2cd8f-155">Autorisation d'appelants partiellement approuvés</span><span class="sxs-lookup"><span data-stu-id="2cd8f-155">Allowing Partially Trusted Callers</span></span>](../../../database-engine/dev-guide/allowing-partially-trusted-callers.md)  
  
