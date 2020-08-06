---
title: Types et membres interdits dans System.Data.dll | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- host protection attributes [CLR integration]
- common language runtime [SQL Server], host protection attributes
ms.assetid: ee5f55e9-fbef-401a-be18-a2e5873c8720
author: rothja
ms.author: jroth
ms.openlocfilehash: cd62f6f0a90bd167f20a33f8de749acc982f39b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603555"
---
# <a name="disallowed-types-and-members-in-systemdatadll"></a><span data-ttu-id="0b6d7-102">Types et membres non autorisés dans System.Data.dll</span><span class="sxs-lookup"><span data-stu-id="0b6d7-102">Disallowed Types and Members in System.Data.dll</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="0b6d7-103">la programmation CLR (Common Language Integration) interdit l’utilisation d’un type ou d’un membre ayant un `HostProtectionAttribute` qui spécifie une `System.Security.Permissions.HostProtectionResource` énumération avec la valeur `ExternalProcessMgmt` , `ExternalThreading` ,, `MayLeakOnAbort` `SecurityInfrastructure` , `SelfAffectingProcessMgmnt` , `SelfAffectingThreading` , **SharedState**, `Synchronization` ou `UI` .</span><span class="sxs-lookup"><span data-stu-id="0b6d7-103">common language integration (CLR) programming disallows the use of a type or member that has a `HostProtectionAttribute` that specifies a `System.Security.Permissions.HostProtectionResource` enumeration with a value of `ExternalProcessMgmt`, `ExternalThreading`, `MayLeakOnAbort`, `SecurityInfrastructure`, `SelfAffectingProcessMgmnt`, `SelfAffectingThreading`, **SharedState**, `Synchronization`, or `UI`.</span></span> <span data-ttu-id="0b6d7-104">Le tableau suivant répertorie les membres et les types de l'assembly System.Data dll dont les valeurs d'attribut de protection de l'hôte (HPA) sont interdites.</span><span class="sxs-lookup"><span data-stu-id="0b6d7-104">The following table lists the members and types of the System.Data.dll assembly whose Host Protection Attribute (HPA) values are disallowed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0b6d7-105">Cette liste a été générée à partir des assemblys pris en charge.</span><span class="sxs-lookup"><span data-stu-id="0b6d7-105">This list was generated from the supported assemblies.</span></span> <span data-ttu-id="0b6d7-106">Pour plus d’informations, consultez [.NET Framework les bibliothèques prises en charge](../clr-integration/database-objects/supported-net-framework-libraries.md).</span><span class="sxs-lookup"><span data-stu-id="0b6d7-106">For more information, see [Supported .NET Framework Libraries](../clr-integration/database-objects/supported-net-framework-libraries.md).</span></span>  
  
|<span data-ttu-id="0b6d7-107">Type ou membre</span><span class="sxs-lookup"><span data-stu-id="0b6d7-107">Type or Member</span></span>|<span data-ttu-id="0b6d7-108">Valeur(s) HPA</span><span class="sxs-lookup"><span data-stu-id="0b6d7-108">HPA Value(s)</span></span>|  
|--------------------|--------------------|  
|<span data-ttu-id="0b6d7-109">System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery()</span><span class="sxs-lookup"><span data-stu-id="0b6d7-109">System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery()</span></span>|<span data-ttu-id="0b6d7-110">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="0b6d7-110">ExternalThreading</span></span>|  
|<span data-ttu-id="0b6d7-111">System.Data.SqlClient.SqlCommand.BeginExecuteReader()</span><span class="sxs-lookup"><span data-stu-id="0b6d7-111">System.Data.SqlClient.SqlCommand.BeginExecuteReader()</span></span>|<span data-ttu-id="0b6d7-112">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="0b6d7-112">ExternalThreading</span></span>|  
|<span data-ttu-id="0b6d7-113">System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader()</span><span class="sxs-lookup"><span data-stu-id="0b6d7-113">System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader()</span></span>|<span data-ttu-id="0b6d7-114">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="0b6d7-114">ExternalThreading</span></span>|  
|<span data-ttu-id="0b6d7-115">System.Data.SqlClient.SqlDependency..ctor()</span><span class="sxs-lookup"><span data-stu-id="0b6d7-115">System.Data.SqlClient.SqlDependency..ctor()</span></span>|<span data-ttu-id="0b6d7-116">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="0b6d7-116">ExternalThreading</span></span>|  
|<span data-ttu-id="0b6d7-117">System.Data.SqlClient.SqlDependency.Start()</span><span class="sxs-lookup"><span data-stu-id="0b6d7-117">System.Data.SqlClient.SqlDependency.Start()</span></span>|<span data-ttu-id="0b6d7-118">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="0b6d7-118">ExternalThreading</span></span>|  
|<span data-ttu-id="0b6d7-119">System.Data.SqlClient.SqlDependency.Stop()</span><span class="sxs-lookup"><span data-stu-id="0b6d7-119">System.Data.SqlClient.SqlDependency.Stop()</span></span>|<span data-ttu-id="0b6d7-120">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="0b6d7-120">ExternalThreading</span></span>|  
|<span data-ttu-id="0b6d7-121">System.Data.TypedDataSetGenerator</span><span class="sxs-lookup"><span data-stu-id="0b6d7-121">System.Data.TypedDataSetGenerator</span></span>|<span data-ttu-id="0b6d7-122">SharedState, Synchronization</span><span class="sxs-lookup"><span data-stu-id="0b6d7-122">SharedState, Synchronization</span></span>|  
|<span data-ttu-id="0b6d7-123">System.Xml.XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="0b6d7-123">System.Xml.XmlDataDocument</span></span>|<span data-ttu-id="0b6d7-124">Synchronization</span><span class="sxs-lookup"><span data-stu-id="0b6d7-124">Synchronization</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0b6d7-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0b6d7-125">See Also</span></span>  
 <span data-ttu-id="0b6d7-126">[Attributs de protection de l’hôte et programmation de l’intégration du CLR](host-protection-attributes-and-clr-integration-programming.md) </span><span class="sxs-lookup"><span data-stu-id="0b6d7-126">[Host Protection Attributes and CLR Integration Programming](host-protection-attributes-and-clr-integration-programming.md) </span></span>  
 <span data-ttu-id="0b6d7-127">[Types et membres interdits dans Microsoft.VisualBasic.dll](disallowed-types-and-members-in-microsoft-visualbasic-dll.md) </span><span class="sxs-lookup"><span data-stu-id="0b6d7-127">[Disallowed Types and Members in Microsoft.VisualBasic.dll](disallowed-types-and-members-in-microsoft-visualbasic-dll.md) </span></span>  
 <span data-ttu-id="0b6d7-128">[Types et membres interdits dans mscorlib.dll](disallowed-types-and-members-in-mscorlib-dll.md) </span><span class="sxs-lookup"><span data-stu-id="0b6d7-128">[Disallowed Types and Members in mscorlib.dll](disallowed-types-and-members-in-mscorlib-dll.md) </span></span>  
 <span data-ttu-id="0b6d7-129">[Types et membres interdits dans System.dll](disallowed-types-and-members-in-system-dll.md) </span><span class="sxs-lookup"><span data-stu-id="0b6d7-129">[Disallowed Types and Members in System.dll](disallowed-types-and-members-in-system-dll.md) </span></span>  
 [<span data-ttu-id="0b6d7-130">Types et membres interdits dans System.Core.dll</span><span class="sxs-lookup"><span data-stu-id="0b6d7-130">Disallowed Types and Members in System.Core.dll</span></span>](disallowed-types-and-members-in-system-core-dll.md)  
  
  
