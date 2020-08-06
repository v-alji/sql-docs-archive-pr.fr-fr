---
title: Déclaration d’autorisations dans les assemblys personnalisés | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- secure calls [Reporting Services]
- custom assemblies [Reporting Services], permissions
- permission sets [Reporting Services]
- asserting permissions
- permissions [Reporting Services], custom assemblies
- limited permission sets
- security configuration files [Reporting Services]
ms.assetid: 3afb9631-f15e-405e-990b-ee102828f298
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cba3c0b74712b6b4d0f6b5c58925cfd562f0df77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599790"
---
# <a name="asserting-permissions-in-custom-assemblies"></a><span data-ttu-id="db4e8-102">Déclaration d'autorisations dans les assemblys personnalisés</span><span class="sxs-lookup"><span data-stu-id="db4e8-102">Asserting Permissions in Custom Assemblies</span></span>
  <span data-ttu-id="db4e8-103">Par défaut, le code d’assembly personnalisé s’exécute avec le jeu d’autorisations limité **Execution**.</span><span class="sxs-lookup"><span data-stu-id="db4e8-103">By default, custom assembly code runs with the limited **Execution** permission set.</span></span> <span data-ttu-id="db4e8-104">Dans certaines situations, vous voudrez peut-être implémenter un assembly personnalisé qui effectue des appels sécurisés à des ressources protégées au sein de votre système de sécurité (comme un fichier ou le Registre).</span><span class="sxs-lookup"><span data-stu-id="db4e8-104">In some cases, you may wish to implement a custom assembly that makes secured calls to protected resources within your security system (such as a file or the registry).</span></span> <span data-ttu-id="db4e8-105">Pour ce faire, vous devez procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="db4e8-105">In order to accomplish this, you must do the following:</span></span>  
  
1.  <span data-ttu-id="db4e8-106">Identifiez les autorisations exactes dont votre code a besoin pour effectuer l'appel sécurisé.</span><span class="sxs-lookup"><span data-stu-id="db4e8-106">Identify the exact permissions that your code needs in order to make the secured call.</span></span> <span data-ttu-id="db4e8-107">Si cette méthode fait partie d’une [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] bibliothèque, ces informations doivent être incluses dans la documentation de la méthode.</span><span class="sxs-lookup"><span data-stu-id="db4e8-107">If this method is part of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] library, this information should be included in the method documentation.</span></span>  
  
2.  <span data-ttu-id="db4e8-108">Modifiez les fichiers de configuration de stratégie du serveur de rapports de manière à accorder les autorisations requises à l'assembly personnalisé.</span><span class="sxs-lookup"><span data-stu-id="db4e8-108">Modify the report server policy configuration files in order to grant the custom assembly the required permissions.</span></span> <span data-ttu-id="db4e8-109">Pour plus d’informations sur les fichiers de configuration de stratégie de sécurité, consultez [Utilisation des fichiers de stratégie de sécurité Reporting Services](../extensions/secure-development/using-reporting-services-security-policy-files.md).</span><span class="sxs-lookup"><span data-stu-id="db4e8-109">For more information about the security policy configuration files, see [Using Reporting Services Security Policy Files](../extensions/secure-development/using-reporting-services-security-policy-files.md).</span></span>  
  
3.  <span data-ttu-id="db4e8-110">Déclarez les autorisations requises dans le cadre de la méthode utilisée pour effectuer l'appel sécurisé.</span><span class="sxs-lookup"><span data-stu-id="db4e8-110">Assert the required permissions as part of the method in which the secure call is made.</span></span> <span data-ttu-id="db4e8-111">Cette étape est nécessaire car le code d’assembly personnalisé qui est appelé par le serveur de rapports fait partie de l’assembly hôte d’expressions du rapport, qui s’exécute par défaut avec l’autorisation **Execution**.</span><span class="sxs-lookup"><span data-stu-id="db4e8-111">This is required because the custom assembly code that is called by the report server is part of the report expression host assembly, which runs with **Execution** permission by default.</span></span> <span data-ttu-id="db4e8-112">Le jeu d’autorisations **Execution** permet au code de s’exécuter, mais pas d’utiliser des ressources protégées.</span><span class="sxs-lookup"><span data-stu-id="db4e8-112">The **Execution** permission set enables code to run, but not to use protected resources.</span></span>  
  
4.  <span data-ttu-id="db4e8-113">Marquez l’assembly personnalisé avec **AllowPartiallyTrustedCallersAttribute** s’il est signé avec un nom fort.</span><span class="sxs-lookup"><span data-stu-id="db4e8-113">Mark the custom assembly with **AllowPartiallyTrustedCallersAttribute** if it is signed with a strong name.</span></span> <span data-ttu-id="db4e8-114">Cette étape est nécessaire car les assemblys personnalisés sont appelés à partir d’une expression de rapport qui fait partie de l’assembly hôte d’expressions du rapport, à qui, par défaut, l’autorisation **FullTrust** n’est pas accordée. Il s’agit donc d’un appelant d’un niveau de confiance partiel.</span><span class="sxs-lookup"><span data-stu-id="db4e8-114">This is required because custom assemblies are called from a report expression that is part of the report expression host assembly, which, by default, is not granted **FullTrust**; thus it is a "partially trusted" caller.</span></span> <span data-ttu-id="db4e8-115">Pour plus d’informations, consultez [Utilisation d’assemblys personnalisés avec noms forts](using-strong-named-custom-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="db4e8-115">For more information, see [Using Strong-Named Custom Assemblies](using-strong-named-custom-assemblies.md).</span></span>  
  
## <a name="implementing-a-secure-call"></a><span data-ttu-id="db4e8-116">Implémentation d'un appel sécurisé</span><span class="sxs-lookup"><span data-stu-id="db4e8-116">Implementing a Secure Call</span></span>  
 <span data-ttu-id="db4e8-117">Vous pouvez modifier les fichiers de configuration de stratégie de manière à accorder des autorisations spécifiques à votre assembly.</span><span class="sxs-lookup"><span data-stu-id="db4e8-117">You can modify the policy configuration files to grant your assembly specific permissions.</span></span> <span data-ttu-id="db4e8-118">Par exemple, si vous écrivez un assembly personnalisé pour gérer la conversion de devises, vous aurez peut-être besoin de lire le taux de change de la devise actuelle dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="db4e8-118">For example, if you were writing a custom assembly to handle currency conversion, you might need to read the current currency exchange rates from a file.</span></span> <span data-ttu-id="db4e8-119">Pour extraire les informations sur les taux de change, vous aurez besoin d’ajouter une autorisation de sécurité supplémentaire, **FileIOPermission**, au jeu d’autorisations de l’assembly.</span><span class="sxs-lookup"><span data-stu-id="db4e8-119">To retrieve the rate information, you would need to add an additional security permission, **FileIOPermission**, to your permission set for the assembly.</span></span> <span data-ttu-id="db4e8-120">Vous pouvez ajouter l'entrée suivante au fichier de configuration de stratégie :</span><span class="sxs-lookup"><span data-stu-id="db4e8-120">You can make the following additional entry in the policy configuration file:</span></span>  
  
```  
<PermissionSet class="NamedPermissionSet"  
   version="1"  
   Name="CurrencyRatesFilePermissionSet"  
   Description="A special permission set that grants read access to my currency rates file.">  
      <IPermission class="FileIOPermission"  
         version="1"  
         Read="C:\CurrencyRates.xml"/>  
      <IPermission class="SecurityPermission"  
         version="1"  
         Flags="Execution, Assertion"/>  
</PermissionSet>  
```  
  
 <span data-ttu-id="db4e8-121">Vous pouvez ensuite ajouter une groupe de code qui référence ce jeu d'autorisations :</span><span class="sxs-lookup"><span data-stu-id="db4e8-121">You then add a code group that references that permission set:</span></span>  
  
```  
<CodeGroup class="UnionCodeGroup"  
   version="1"  
   PermissionSetName="CurrencyRatesFilePermissionSet"  
   Name="MyNewCodeGroup"  
   Description="A special code group for my custom assembly.">  
   <IMembershipCondition class="UrlMembershipCondition"  
      version="1"  
      Url="C:\Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\MSSQL\Reporting Services\ReportServer\bin\CurrencyConversion.dll"/>  
</CodeGroup>  
```  
  
 <span data-ttu-id="db4e8-122">Pour que votre code acquière l'autorisation appropriée, vous devez déclarer cette autorisation dans le code de votre assembly personnalisé.</span><span class="sxs-lookup"><span data-stu-id="db4e8-122">In order for your code to acquire the appropriate permission, you must assert the permission within your custom assembly code.</span></span> <span data-ttu-id="db4e8-123">Par exemple, si vous souhaitez ajouter l'accès en lecture seule à un fichier XML, C:\CurrencyRates.xml, vous devez ajouter le code suivant à votre méthode :</span><span class="sxs-lookup"><span data-stu-id="db4e8-123">For example, if you want to add read-only access to an XML file, C:\CurrencyRates.xml, you must add the following code to your method:</span></span>  
  
```  
// C#  
FileIOPermission permission = new FileIOPermission(FileIOPermissionAccess.Read, @"C:\CurrencyRates.xml");  
try  
{  
   permission.Assert();  
   // Load the XML currency rates file  
   XmlDocument doc = new XmlDocument();  
   doc.Load(@"C:\CurrencyRates.xml");  
...  
```  
  
 <span data-ttu-id="db4e8-124">Vous pouvez déclarer cette autorisation sous la forme d'un attribut de méthode :</span><span class="sxs-lookup"><span data-stu-id="db4e8-124">You can also add the assertion as a method attribute:</span></span>  
  
```  
[FileIOPermissionAttribute(SecurityAction.Assert, Read=@"C:\CurrencyRates.xml")]  
```  
  
 <span data-ttu-id="db4e8-125">Pour plus d'informations, consultez la rubrique « Sécurité du .NET Framework » dans le Guide du développeur .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="db4e8-125">For more information, see ".NET Framework Security" in the .NET Framework Developer's Guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db4e8-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="db4e8-126">See Also</span></span>  
 [<span data-ttu-id="db4e8-127">Utilisation d'assemblys personnalisés avec des rapports</span><span class="sxs-lookup"><span data-stu-id="db4e8-127">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
