---
title: Sérialisation XML à partir d’objets de base de données CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- serialization
- XML serialization [CLR integration]
- common language runtime [SQL Server], XML serialization
- XmlSerializer class
ms.assetid: ac84339b-9384-4710-bebc-01607864a344
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ee93ee4b7bf9cba3f11b329244d4523636cb7704
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701651"
---
# <a name="xml-serialization-from-clr-database-objects"></a><span data-ttu-id="9a244-102">Sérialisation XML à partir d'objets de base de données CLR</span><span class="sxs-lookup"><span data-stu-id="9a244-102">XML Serialization from CLR Database Objects</span></span>
  <span data-ttu-id="9a244-103">La sérialisation XML est nécessaire dans deux scénarios :</span><span class="sxs-lookup"><span data-stu-id="9a244-103">XML serialization is required for two scenarios:</span></span>  
  
-   <span data-ttu-id="9a244-104">Appel de services Web à partir d'objets CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="9a244-104">Invoking Web Services from common language runtime (CLR) objects.</span></span>  
  
-   <span data-ttu-id="9a244-105">Conversion d'un type défini par l'utilisateur (UDT) en XML.</span><span class="sxs-lookup"><span data-stu-id="9a244-105">Converting a user-defined type (UDT) to XML.</span></span>  
  
 <span data-ttu-id="9a244-106">La sérialisation XML réalisée par appel de la classe `XmlSerializer` génère normalement un assembly de sérialisation supplémentaire qui est surchargé dans le projet avec l'assembly source.</span><span class="sxs-lookup"><span data-stu-id="9a244-106">Performing XML serialization by invoking the `XmlSerializer` class normally generates an additional serialization assembly that is overloaded into the project with the source assembly.</span></span> <span data-ttu-id="9a244-107">Toutefois, pour des raisons de sécurité, cette surcharge est désactivée dans le CLR.</span><span class="sxs-lookup"><span data-stu-id="9a244-107">However, for security purposes, this overload is disabled in the CLR.</span></span> <span data-ttu-id="9a244-108">Par conséquent, pour appeler un service Web ou effectuer une conversion d’UDT en XML à l’intérieur de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , l’assembly doit être créé manuellement à l’aide d’un outil appelé **Sgen.exe** fourni avec le .NET Framework qui génère les assemblys de sérialisation nécessaires.</span><span class="sxs-lookup"><span data-stu-id="9a244-108">Therefore, to call a web service or perform conversion from UDT to XML inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the assembly must be created manually using a tool called **Sgen.exe** provided with the .NET Framework that generates the necessary serialization assemblies.</span></span> <span data-ttu-id="9a244-109">Lors de l'appel de `XmlSerializer`, l'assembly de sérialisation doit être créé manuellement en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="9a244-109">When invoking `XmlSerializer`, the serialization assembly must be created manually by following these steps:</span></span>  
  
1.  <span data-ttu-id="9a244-110">Exécutez l’outil **Sgen.exe** fourni avec le kit de développement logiciel (SDK) .NET Framework pour créer l’assembly contenant les sérialiseurs XML de l’assembly source.</span><span class="sxs-lookup"><span data-stu-id="9a244-110">Run the **Sgen.exe** tool that is provided with the .NET Framework SDK to create the assembly containing the XML serializers for the source assembly.</span></span>  
  
2.  <span data-ttu-id="9a244-111">Inscrivez l'assembly généré dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'aide de l'instruction `CREATE ASSEMBLY`.</span><span class="sxs-lookup"><span data-stu-id="9a244-111">Register the generated assembly in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the `CREATE ASSEMBLY` statement.</span></span>  
  
 <span data-ttu-id="9a244-112">Pour plus d’informations sur les erreurs que vous pouvez recevoir lors de la sérialisation XML, consultez l’article Support Microsoft suivant : [« Impossible de charger l’assembly de sérialisation généré dynamiquement »](https://support.microsoft.com/kb/913668).</span><span class="sxs-lookup"><span data-stu-id="9a244-112">For information about errors that you may receive when performing XML serialization, see the following Microsoft Support article: ["Cannot load dynamically generated serialization assembly"](https://support.microsoft.com/kb/913668).</span></span>  
  
 <span data-ttu-id="9a244-113">Pour plus d'informations sur les types de données qui ne sont pas pris en charge par le sérialiseur XML, consultez la rubrique consacrée à la prise en charge de la liaison de schéma XML dans le .NET Framework dans la documentation de ce dernier.</span><span class="sxs-lookup"><span data-stu-id="9a244-113">For information on data types that are not supported by XMLSerializer, see XML Schema Binding Support in the .NET Framework in the .NET Framework documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a244-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9a244-114">See Also</span></span>  
 <span data-ttu-id="9a244-115">[Accès aux données à partir des objets de base de données CLR](../../relational-databases/clr-integration/data-access/data-access-from-clr-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="9a244-115">[Data Access from CLR Database Objects](../../relational-databases/clr-integration/data-access/data-access-from-clr-database-objects.md) </span></span>  
 [<span data-ttu-id="9a244-116">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a244-116">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-assembly-transact-sql)  
  
  
