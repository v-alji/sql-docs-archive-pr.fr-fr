---
title: Accès aux données à partir des objets de base de données CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- common language runtime [SQL Server], data access
- routines [CLR integration]
- data access [CLR integration]
- ADO.NET [CLR integration]
- internal data access [CLR integration]
- common language runtime [SQL Server], ADO.NET
- database objects [CLR integration], data access
- managed code [SQL Server], database objects
- .NET Data Access Provider for SQL Server [CLR integration]
- managed code [SQL Server], data access
- SqlClient provider
- in-process data access providers [CLR integration]
ms.assetid: 9a0f4dee-71c1-42e9-a85e-52382807010f
author: rothja
ms.author: jroth
ms.openlocfilehash: d229d490a9f3a7bc6f613259ee0535218de47975
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613468"
---
# <a name="data-access-from-clr-database-objects"></a><span data-ttu-id="16f01-102">Accès aux données à partir d'objets de base de données CLR</span><span class="sxs-lookup"><span data-stu-id="16f01-102">Data Access from CLR Database Objects</span></span>
  <span data-ttu-id="16f01-103">Une routine de common language runtime (CLR) peut accéder facilement aux données stockées dans l’instance de [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] dans laquelle elles s’exécutent, ainsi qu’aux données stockées dans des instances distantes.</span><span class="sxs-lookup"><span data-stu-id="16f01-103">A common language runtime (CLR) routine may easily access data stored in the instance of [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] in which it runs, as well as data stored in remote instances.</span></span> <span data-ttu-id="16f01-104">Les données particulières auxquelles la routine peut accéder sont déterminées par le contexte utilisateur dans lequel le code s'exécute.</span><span class="sxs-lookup"><span data-stu-id="16f01-104">Which particular data the routine can access is determined by the user context in which the code is running.</span></span> <span data-ttu-id="16f01-105">Accédez aux données à partir d’un objet de base de données CLR à l’aide de la .NET Framework Fournisseur de données pour les [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] données du client géré et des applications de couche intermédiaire.</span><span class="sxs-lookup"><span data-stu-id="16f01-105">Access data from within a CLR database object by using the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data from managed client and middle-tier applications.</span></span> <span data-ttu-id="16f01-106">C'est la raison pour laquelle vous pouvez tirer parti de vos connaissances d'ADO.NET et de `SqlClient` dans les applications clientes managées et de couche intermédiaire.</span><span class="sxs-lookup"><span data-stu-id="16f01-106">Because of this, you can leverage your knowledge of ADO.NET and `SqlClient` in client and middle-tier applications.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="16f01-107">Les méthodes de type défini par l'utilisateur et les fonctions définies par l'utilisateur ne sont pas autorisées à effectuer un accès aux données par défaut.</span><span class="sxs-lookup"><span data-stu-id="16f01-107">User-defined type methods and user-defined functions are not allowed to perform data access by default.</span></span> <span data-ttu-id="16f01-108">Vous devez définir la propriété `DataAccess` de `SqlMethodAttribute` ou `SqlFunctionAttribute` à `DataAccessKind.Read` pour permettre l'accès aux données en lecture seule à partir des méthodes de type défini par l'utilisateur ou des fonctions définies par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="16f01-108">You must set the `DataAccess` property of `SqlMethodAttribute` or `SqlFunctionAttribute` to `DataAccessKind.Read` to enable read-only data access from user-defined type (UDT) methods or user-defined functions.</span></span> <span data-ttu-id="16f01-109">Les opérations de modification des données ne sont pas autorisées à partir des types définis par l'utilisateur ou des fonctions définies par l'utilisateur ; par ailleurs, elles lèvent des exceptions au moment de l'exécution, à la moindre tentative.</span><span class="sxs-lookup"><span data-stu-id="16f01-109">Data modification operations are not allowed from UDTs or user-defined functions, and throws exceptions at execution time if attempted.</span></span>  
  
 <span data-ttu-id="16f01-110">Cette section décrit uniquement les différences spécifiques en matière de fonctionnement et de comportement lors de l'accès aux données à partir d'un objet de base de données CLR.</span><span class="sxs-lookup"><span data-stu-id="16f01-110">This section discusses only the specific functional and behavioral differences when accessing data from within a CLR database object.</span></span> <span data-ttu-id="16f01-111">Pour plus d'informations sur les fonctionnalités d'ADO.NET, consultez la documentation ADO.NET incluse dans le Kit de développement logiciel .NET Framework (SDK).</span><span class="sxs-lookup"><span data-stu-id="16f01-111">For more information about the features and functionality of ADO.NET, see the ADO.NET documentation included in the .NET Framework SDK.</span></span>  
  
 <span data-ttu-id="16f01-112">Le tableau suivant décrit les rubriques de cette section.</span><span class="sxs-lookup"><span data-stu-id="16f01-112">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="16f01-113">Connexion contextuelle</span><span class="sxs-lookup"><span data-stu-id="16f01-113">Context Connection</span></span>](context-connection.md)  
 <span data-ttu-id="16f01-114">Décrit la connexion contextuelle à SQL Server.</span><span class="sxs-lookup"><span data-stu-id="16f01-114">Describes the context connection to SQL Server.</span></span>  
  
 [<span data-ttu-id="16f01-115">Emprunt d'identité et informations d'identification pour les connexions</span><span class="sxs-lookup"><span data-stu-id="16f01-115">Impersonation and Credentials for Connections</span></span>](impersonation-and-credentials-for-connections.md)  
 <span data-ttu-id="16f01-116">Décrit l'emprunt d'identité et les informations d'identification des connexions.</span><span class="sxs-lookup"><span data-stu-id="16f01-116">Describes impersonating connections and connection credentials.</span></span>  
  
 [<span data-ttu-id="16f01-117">Extensions spécifiques in-process de SQL Server à ADO.NET</span><span class="sxs-lookup"><span data-stu-id="16f01-117">SQL Server In-Process Specific Extensions to ADO.NET</span></span>](../../clr-integration-data-access-in-process-ado-net/sql-server-in-process-specific-extensions-to-ado-net.md)  
 <span data-ttu-id="16f01-118">Décrit les objets in-process `SqlPipe`, `SqlContext`, `SqlTriggerContext` et `SqlDataRecord` spécifiques.</span><span class="sxs-lookup"><span data-stu-id="16f01-118">Discusses the in-process specific `SqlPipe`, `SqlContext`, `SqlTriggerContext`, and `SqlDataRecord` objects.</span></span>  
  
 [<span data-ttu-id="16f01-119">Intégration et transactions du CLR</span><span class="sxs-lookup"><span data-stu-id="16f01-119">CLR Integration and Transactions</span></span>](../../native-client-ole-db-transactions/transactions.md)  
 <span data-ttu-id="16f01-120">Explique comment la nouvelle infrastructure de transaction fournie dans l'espace de noms System.Transactions s'intègre à ADO.NET et décrit l'intégration du CLR de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16f01-120">Describes how the new transaction framework provided in the System.Transactions namespace integrates with ADO.NET and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] CLR integration.</span></span>  
  
 [<span data-ttu-id="16f01-121">Sérialisation XML à partir d'objets de base de données CLR</span><span class="sxs-lookup"><span data-stu-id="16f01-121">XML Serialization from CLR Database Objects</span></span>](../../../database-engine/dev-guide/xml-serialization-from-clr-database-objects.md)  
 <span data-ttu-id="16f01-122">Explique comment activer les scénarios de sérialisation XML des objets de base de données CLR dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16f01-122">Explains how to enable XML serialization scenarios of CLR database objects inside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
  
