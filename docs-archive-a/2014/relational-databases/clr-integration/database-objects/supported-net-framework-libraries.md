---
title: Bibliothèques de .NET Framework prises en charge | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- common language runtime [SQL Server], .NET Framework libraries
- .NET Framework [CLR Integration]
ms.assetid: 417544ff-c25c-496e-add4-2f278f8a4911
author: rothja
ms.author: jroth
ms.openlocfilehash: 22f92e3eadccc869452cf35534f786724c8e259a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600079"
---
# <a name="supported-net-framework-libraries"></a><span data-ttu-id="90b32-102">Bibliothèques .NET Framework prises en charge</span><span class="sxs-lookup"><span data-stu-id="90b32-102">Supported .NET Framework Libraries</span></span>
  <span data-ttu-id="90b32-103">Avec le CLR (Common Language Runtime) hébergé dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], vous pouvez créer des procédures stockées, des déclencheurs, des fonctions définies par l'utilisateur, des types définis par l'utilisateur et des agrégats définis par l'utilisateur en code managé.</span><span class="sxs-lookup"><span data-stu-id="90b32-103">With the common language runtime (CLR) hosted in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], you can author stored procedures, triggers, user-defined functions, user-defined types, and user-defined aggregates in managed code.</span></span> <span data-ttu-id="90b32-104">Avec les fonctionnalités présentes dans les bibliothèques de classes .NET Framework, vous avez accès à des classes prégénérées qui fournissent des fonctionnalités pour la manipulation de chaînes, des opérations de mathématique avancées, l'accès au fichier, le chiffrement, etc.</span><span class="sxs-lookup"><span data-stu-id="90b32-104">With the functionality found in the .NET Framework class libraries, you have access to pre-built classes that provide functionality for string manipulation, advanced math operations, file access, cryptography, and more.</span></span> <span data-ttu-id="90b32-105">Ces classes sont accessibles à partir de procédures stockées managées, de types définis par l'utilisateur, de déclencheurs, de fonctions définies par l'utilisateur ou d'agrégats définis par l'utilisateur, quels qu'ils soient.</span><span class="sxs-lookup"><span data-stu-id="90b32-105">These classes can be accessed from any managed stored procedure, user-defined type, trigger, user-defined function, or user-defined aggregate.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="90b32-106">Si vous mettez en service ou mettez à niveau des assemblys non pris en charge dans le Global Assembly Cache (GAC), votre [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="90b32-106">If you service or upgrade unsupported assemblies in the global assembly cache (GAC), your [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="90b32-107">Si un assembly existe dans une [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] intégration du CLR.</span><span class="sxs-lookup"><span data-stu-id="90b32-107">If an assembly exists both in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] CLR integration.</span></span> <span data-ttu-id="90b32-108">Si vous effectuez la maintenance ou mettez à niveau des assemblys dans le GAC qui sont également inscrits dans la base de données, y compris des assemblys .NET Framework non pris en charge, veillez également à effectuer la maintenance ou à mettre à niveau la copie de l'assembly à l'intérieur de vos bases de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] avec l'instruction `ALTER ASSEMBLY`</span><span class="sxs-lookup"><span data-stu-id="90b32-108">If you service or upgrade any assemblies in the GAC that are also registered in the database, including unsupported .NET Framework assemblies, make sure to also service or upgrade the copy of the assembly inside your [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases with the `ALTER ASSEMBLY` statement.</span></span> <span data-ttu-id="90b32-109">Pour plus d’informations, consultez [l’article 949080](https://support.microsoft.com/kb/949080)de la base de connaissances.</span><span class="sxs-lookup"><span data-stu-id="90b32-109">For more information, see [Knowledge Base article 949080](https://support.microsoft.com/kb/949080).</span></span>  
  
## <a name="supported-libraries"></a><span data-ttu-id="90b32-110">Bibliothèques prises en charge</span><span class="sxs-lookup"><span data-stu-id="90b32-110">Supported Libraries</span></span>  
 <span data-ttu-id="90b32-111">À partir [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] de, la liste des bibliothèques de .NET Framework prises en charge, qui ont été testées pour s’assurer qu’elles répondent aux normes de fiabilité et de sécurité pour l’interaction avec, les [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] charge directement à partir du global assembly cache (GAC).</span><span class="sxs-lookup"><span data-stu-id="90b32-111">Beginning with [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] has a list of supported .NET Framework libraries, which have been tested to ensure that they meet reliability and security standards for interaction with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] loads them directly from the Global Assembly Cache (GAC).</span></span>  
  
 <span data-ttu-id="90b32-112">Les bibliothèques/espaces de noms pris en charge par l'intégration du CLR dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="90b32-112">The libraries/namespaces supported by CLR integration in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] are:</span></span>  
  
-   <span data-ttu-id="90b32-113">CustomMarshalers</span><span class="sxs-lookup"><span data-stu-id="90b32-113">CustomMarshalers</span></span>  
  
-   <span data-ttu-id="90b32-114">Microsoft.VisualBasic</span><span class="sxs-lookup"><span data-stu-id="90b32-114">Microsoft.VisualBasic</span></span>  
  
-   <span data-ttu-id="90b32-115">Microsoft.VisualC</span><span class="sxs-lookup"><span data-stu-id="90b32-115">Microsoft.VisualC</span></span>  
  
-   <span data-ttu-id="90b32-116">mscorlib</span><span class="sxs-lookup"><span data-stu-id="90b32-116">mscorlib</span></span>  
  
-   <span data-ttu-id="90b32-117">Système</span><span class="sxs-lookup"><span data-stu-id="90b32-117">System</span></span>  
  
-   <span data-ttu-id="90b32-118">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="90b32-118">System.Configuration</span></span>  
  
-   <span data-ttu-id="90b32-119">System.Data</span><span class="sxs-lookup"><span data-stu-id="90b32-119">System.Data</span></span>  
  
-   <span data-ttu-id="90b32-120">System.Data.OracleClient</span><span class="sxs-lookup"><span data-stu-id="90b32-120">System.Data.OracleClient</span></span>  
  
-   <span data-ttu-id="90b32-121">System.Data.SqlXml</span><span class="sxs-lookup"><span data-stu-id="90b32-121">System.Data.SqlXml</span></span>  
  
-   <span data-ttu-id="90b32-122">System.Deployment</span><span class="sxs-lookup"><span data-stu-id="90b32-122">System.Deployment</span></span>  
  
-   <span data-ttu-id="90b32-123">System.Security</span><span class="sxs-lookup"><span data-stu-id="90b32-123">System.Security</span></span>  
  
-   <span data-ttu-id="90b32-124">System.Transactions</span><span class="sxs-lookup"><span data-stu-id="90b32-124">System.Transactions</span></span>  
  
-   <span data-ttu-id="90b32-125">System.Web.Services</span><span class="sxs-lookup"><span data-stu-id="90b32-125">System.Web.Services</span></span>  
  
-   <span data-ttu-id="90b32-126">System.Xml</span><span class="sxs-lookup"><span data-stu-id="90b32-126">System.Xml</span></span>  
  
-   <span data-ttu-id="90b32-127">System.Core.dll</span><span class="sxs-lookup"><span data-stu-id="90b32-127">System.Core.dll</span></span>  
  
-   <span data-ttu-id="90b32-128">System.Xml.Linq.dll</span><span class="sxs-lookup"><span data-stu-id="90b32-128">System.Xml.Linq.dll</span></span>  
  
## <a name="unsupported-libraries"></a><span data-ttu-id="90b32-129">Bibliothèques non prises en charge</span><span class="sxs-lookup"><span data-stu-id="90b32-129">Unsupported Libraries</span></span>  
 <span data-ttu-id="90b32-130">Il est toujours possible d'appeler des bibliothèques non prises en charge à partir de vos procédures stockées managées, déclencheurs, fonctions définies par l'utilisateur, types définis par l'utilisateur et agrégats définis par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="90b32-130">Unsupported libraries can still be called from your managed stored procedures, triggers, user-defined functions, user-defined types, and user-defined aggregates.</span></span> <span data-ttu-id="90b32-131">Vous devez d'abord inscrire la bibliothèque non prise en charge dans la base de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à l'aide de l'instruction `CREATE ASSEMBLY` avant de pouvoir l'utiliser dans votre code.</span><span class="sxs-lookup"><span data-stu-id="90b32-131">The unsupported library must first be registered in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database, using the `CREATE ASSEMBLY` statement, before it can be used in your code.</span></span> <span data-ttu-id="90b32-132">Toute bibliothèque non prise en charge qui est inscrite et exécutée sur le serveur doit être examinée et testée en termes de sécurité et de fiabilité.</span><span class="sxs-lookup"><span data-stu-id="90b32-132">Any unsupported library that is registered and run on the server should be reviewed and tested for security and reliability.</span></span>  
  
 <span data-ttu-id="90b32-133">Par exemple, l'espace de noms `System.DirectoryServices` n'est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="90b32-133">For example, the `System.DirectoryServices` namespace is not supported.</span></span> <span data-ttu-id="90b32-134">Vous devez inscrire l'assembly System.DirectoryServices.dll avec les autorisations `UNSAFE` avant de pouvoir l'appeler de votre code.</span><span class="sxs-lookup"><span data-stu-id="90b32-134">You must register the System.DirectoryServices.dll assembly with `UNSAFE` permissions before you can call it from your code.</span></span> <span data-ttu-id="90b32-135">L'autorisation `UNSAFE` est nécessaire parce que les classes dans l'espace de noms `System.DirectoryServices` ne répondent pas aux conditions requises par `SAFE` ou `EXTERNAL_ACCESS`.</span><span class="sxs-lookup"><span data-stu-id="90b32-135">The `UNSAFE` permission is necessary because classes in the `System.DirectoryServices` namespace do not meet the requirements for `SAFE` or `EXTERNAL_ACCESS`.</span></span> <span data-ttu-id="90b32-136">Pour plus d’informations, consultez [restrictions du modèle de programmation](clr-integration-programming-model-restrictions.md) de l’intégration du CLR et sécurité d’accès du code d’intégration du [CLR](../security/clr-integration-code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="90b32-136">For more information, see [CLR Integration Programming Model Restrictions](clr-integration-programming-model-restrictions.md) and [CLR Integration Code Access Security](../security/clr-integration-code-access-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90b32-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="90b32-137">See Also</span></span>  
 <span data-ttu-id="90b32-138">[Création d’un assembly](../assemblies/creating-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="90b32-138">[Creating an Assembly](../assemblies/creating-an-assembly.md) </span></span>  
 <span data-ttu-id="90b32-139">[Sécurité d’accès du code d’intégration du CLR](../security/clr-integration-code-access-security.md) </span><span class="sxs-lookup"><span data-stu-id="90b32-139">[CLR Integration Code Access Security](../security/clr-integration-code-access-security.md) </span></span>  
 [<span data-ttu-id="90b32-140">Restrictions du modèle de programmation de l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="90b32-140">CLR Integration Programming Model Restrictions</span></span>](clr-integration-programming-model-restrictions.md)  
  
  
