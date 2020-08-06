---
title: Attributs personnalisés pour les routines CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- routines [CLR integration]
- SqlFacet attribute
- SqlTrigger attribute
- SqlProcedure attribute
- custom attributes [CLR integration]
- SqlUserDefinedAggregate attribute
- attributes [CLR integration]
- SqlMethod attribute
- SqlFunction attribute
- common language runtime [SQL Server], attributes
- SqlUserDefinedTypeAttribute attribute
ms.assetid: 95069d22-b05d-4670-b053-15ee2a664e33
author: rothja
ms.author: jroth
ms.openlocfilehash: 058bbec7f0f1f63fbd96258a0abe7a6c3d543d88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600085"
---
# <a name="custom-attributes-for-clr-routines"></a><span data-ttu-id="0d2a6-102">Attributs personnalisés pour les routines CLR</span><span class="sxs-lookup"><span data-stu-id="0d2a6-102">Custom Attributes for CLR Routines</span></span>
  <span data-ttu-id="0d2a6-103">Les attributs répertoriés peuvent être appliqués à des routines de common language runtime (CLR), des types définis par l’utilisateur et des agrégats définis par l’utilisateur qui sont inscrits dans [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0d2a6-103">The attributes listed can be applied to common language runtime (CLR) routines, user-defined types, and user-defined aggregates that are registered in [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0d2a6-104">Si l'attribut n'est pas appliqué, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utilise la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="0d2a6-104">If the attribute is not applied, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] assumes the default value.</span></span> <span data-ttu-id="0d2a6-105">Les attributs répertoriés sont définis dans l'espace de noms `Microsoft.SqlServer.Server`.</span><span class="sxs-lookup"><span data-stu-id="0d2a6-105">The attributes listed are defined in the `Microsoft.SqlServer.Server` namespace.</span></span>  
  
## <a name="the-sqluserdefinedaggregate-attribute"></a><span data-ttu-id="0d2a6-106">Attribut SqlUserDefinedAggregate</span><span class="sxs-lookup"><span data-stu-id="0d2a6-106">The SqlUserDefinedAggregate Attribute</span></span>  
 <span data-ttu-id="0d2a6-107">L'attribut `SqlUserDefinedAggregate` indique que la méthode doit être inscrite en tant qu'agrégat défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0d2a6-107">The `SqlUserDefinedAggregate` attribute indicates that the method should be registered as a user-defined aggregate.</span></span> <span data-ttu-id="0d2a6-108">Chaque agrégat défini par l'utilisateur doit être annoté avec cet attribut.</span><span class="sxs-lookup"><span data-stu-id="0d2a6-108">Every user-defined aggregate must be annotated with this attribute.</span></span>  
  
 <span data-ttu-id="0d2a6-109">Pour plus d’informations, consultez [SqlUserDefinedAggregateAttribute](https://go.microsoft.com/fwlink/?LinkId=124626).</span><span class="sxs-lookup"><span data-stu-id="0d2a6-109">For more information, see [SqlUserDefinedAggregateAttribute](https://go.microsoft.com/fwlink/?LinkId=124626).</span></span>  
  
## <a name="the-sqlfunction-attribute"></a><span data-ttu-id="0d2a6-110">Attribut SqlFunction</span><span class="sxs-lookup"><span data-stu-id="0d2a6-110">The SqlFunction Attribute</span></span>  
 <span data-ttu-id="0d2a6-111">L'attribut `SqlFunction` indique que la méthode doit être inscrite en tant que fonction, avec les attributs de fonctions appropriés définis.</span><span class="sxs-lookup"><span data-stu-id="0d2a6-111">The `SqlFunction` attribute indicates the method should be registered as a function, with the appropriate function attributes set.</span></span>  
  
 <span data-ttu-id="0d2a6-112">Pour plus d’informations, consultez [SqlFunctionAttribute](https://go.microsoft.com/fwlink/?LinkId=128019).</span><span class="sxs-lookup"><span data-stu-id="0d2a6-112">For more information, see [SqlFunctionAttribute](https://go.microsoft.com/fwlink/?LinkId=128019).</span></span>  
  
## <a name="the-sqlfacet-attribute"></a><span data-ttu-id="0d2a6-113">Attribut SqlFacet</span><span class="sxs-lookup"><span data-stu-id="0d2a6-113">The SqlFacet Attribute</span></span>  
 <span data-ttu-id="0d2a6-114">L'attribut `SqlFacet` est utilisé pour retourner des informations sur le type de retour d'une expression de type défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0d2a6-114">The `SqlFacet` attribute is used to return information about the return type of a user-defined type (UDT) expression.</span></span>  
  
 <span data-ttu-id="0d2a6-115">Pour plus d’informations, consultez [SqlFacetAttribute](https://go.microsoft.com/fwlink/?LinkId=128020).</span><span class="sxs-lookup"><span data-stu-id="0d2a6-115">For more information, see [SqlFacetAttribute](https://go.microsoft.com/fwlink/?LinkId=128020).</span></span>  
  
## <a name="the-sqlprocedure-attribute"></a><span data-ttu-id="0d2a6-116">Attribut SqlProcedure</span><span class="sxs-lookup"><span data-stu-id="0d2a6-116">The SqlProcedure Attribute</span></span>  
 <span data-ttu-id="0d2a6-117">L'attribut `SqlProcedure` indique que la méthode doit être inscrite en tant que procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="0d2a6-117">The `SqlProcedure` attribute indicates the method should be registered as a stored procedure.</span></span> <span data-ttu-id="0d2a6-118">Cet attribut est utilisé uniquement par Visual Studio pour inscrire automatiquement la méthode spécifiée en tant que procédure stockée ; il n'est pas utilisé par [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d2a6-118">This attribute is used only by Visual Studio to register the specified method as a stored procedure automatically; it is not used by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0d2a6-119">Pour plus d’informations, consultez [SqlProcedureAttribute](https://go.microsoft.com/fwlink/?LinkId=128021).</span><span class="sxs-lookup"><span data-stu-id="0d2a6-119">For more information, see [SqlProcedureAttribute](https://go.microsoft.com/fwlink/?LinkId=128021).</span></span>  
  
## <a name="the-sqltrigger-attribute"></a><span data-ttu-id="0d2a6-120">Attribut SqlTrigger</span><span class="sxs-lookup"><span data-stu-id="0d2a6-120">The SqlTrigger Attribute</span></span>  
 <span data-ttu-id="0d2a6-121">L'attribut `SqlTrigger` indique que la méthode doit être inscrite en tant que déclencheur.</span><span class="sxs-lookup"><span data-stu-id="0d2a6-121">The `SqlTrigger` attribute indicates the method should be registered as a trigger.</span></span>  
  
 <span data-ttu-id="0d2a6-122">Pour plus d’informations, consultez [SqlTriggerContext](https://go.microsoft.com/fwlink/?LinkId=128022) et [il manque SqlTriggerAttribute](https://go.microsoft.com/fwlink/?LinkId=203898).</span><span class="sxs-lookup"><span data-stu-id="0d2a6-122">For more information, see [SqlTriggerContext](https://go.microsoft.com/fwlink/?LinkId=128022) and [SqlTriggerAttribute](https://go.microsoft.com/fwlink/?LinkId=203898).</span></span>  
  
## <a name="the-sqluserdefinedtypeattribute"></a><span data-ttu-id="0d2a6-123">SqlUserDefinedTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="0d2a6-123">The SqlUserDefinedTypeAttribute</span></span>  
 <span data-ttu-id="0d2a6-124">Vous pouvez appliquer SqlUserDefinedTypeAttribute à une définition de classe dans l'assembly.</span><span class="sxs-lookup"><span data-stu-id="0d2a6-124">You can apply the SqlUserDefinedTypeAttribute to a class definition in the assembly.</span></span> <span data-ttu-id="0d2a6-125">Cela oblige [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à créer un type défini par l'utilisateur et lié à la définition de classe qui possède cet attribut personnalisé.</span><span class="sxs-lookup"><span data-stu-id="0d2a6-125">It causes [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to create a user-defined type that is bound to the class definition which has this custom attribute.</span></span>  
  
 <span data-ttu-id="0d2a6-126">Pour plus d’informations, consultez [SqlUserDefinedTypeAttribute](https://go.microsoft.com/fwlink/?LinkId=128024).</span><span class="sxs-lookup"><span data-stu-id="0d2a6-126">For more information, see [SqlUserDefinedTypeAttribute](https://go.microsoft.com/fwlink/?LinkId=128024).</span></span>  
  
## <a name="the-sqlmethod-attribute"></a><span data-ttu-id="0d2a6-127">Attribut SqlMethod</span><span class="sxs-lookup"><span data-stu-id="0d2a6-127">The SqlMethod Attribute</span></span>  
 <span data-ttu-id="0d2a6-128">L'attribut `SqlMethod` est utilisé pour indiquer les propriétés de déterminisme et d'accès aux données d'une méthode ou d'une propriété sur un type défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0d2a6-128">The `SqlMethod` attribute is used to indicate the determinism and data access properties of a method or a property on a UDT.</span></span>  
  
 <span data-ttu-id="0d2a6-129">Pour plus d’informations, consultez [SqlMethodAttribute](https://go.microsoft.com/fwlink/?LinkId=128025).</span><span class="sxs-lookup"><span data-stu-id="0d2a6-129">For more information, see [SqlMethodAttribute](https://go.microsoft.com/fwlink/?LinkId=128025).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d2a6-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0d2a6-130">See Also</span></span>  
 <span data-ttu-id="0d2a6-131">[Agrégats CLR définis par l’utilisateur](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md) </span><span class="sxs-lookup"><span data-stu-id="0d2a6-131">[CLR User-Defined Aggregates](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md) </span></span>  
 <span data-ttu-id="0d2a6-132">[Fonctions CLR définies par l’utilisateur](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md) </span><span class="sxs-lookup"><span data-stu-id="0d2a6-132">[CLR User-Defined Functions](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md) </span></span>  
 <span data-ttu-id="0d2a6-133">[Types CLR définis par l’utilisateur](../../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md) </span><span class="sxs-lookup"><span data-stu-id="0d2a6-133">[CLR User-Defined Types](../../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md) </span></span>  
 <span data-ttu-id="0d2a6-134">[Procédures stockées CLR](../../../database-engine/dev-guide/clr-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="0d2a6-134">[CLR Stored Procedures](../../../database-engine/dev-guide/clr-stored-procedures.md) </span></span>  
 [<span data-ttu-id="0d2a6-135">Déclencheurs CLR</span><span class="sxs-lookup"><span data-stu-id="0d2a6-135">CLR Triggers</span></span>](../../../database-engine/dev-guide/clr-triggers.md)  
  
  
