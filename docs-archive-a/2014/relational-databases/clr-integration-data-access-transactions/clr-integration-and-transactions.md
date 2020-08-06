---
title: Intégration et transactions du CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- ADO.NET [CLR integration]
- common language runtime [SQL Server], ADO.NET
- managed code [SQL Server], transactions
- common language runtime [SQL Server], transactions
- System.Transactions namespace
- transactions [CLR integration]
ms.assetid: 381d206e-06e2-48d0-8206-295fcf06ac98
author: rothja
ms.author: jroth
ms.openlocfilehash: de72a2113aeb568decbdc9b5ee0174160cc0d3ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709660"
---
# <a name="clr-integration-and-transactions"></a><span data-ttu-id="75b28-102">Intégration et transactions du CLR</span><span class="sxs-lookup"><span data-stu-id="75b28-102">CLR Integration and Transactions</span></span>
  <span data-ttu-id="75b28-103">L'espace de noms `System.Transactions` fournit une infrastructure de transaction qui s'intègre entièrement à ADO.NET et au CLR (Common Language Runtime) de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75b28-103">The `System.Transactions` namespace provides a transaction framework that is fully integrated with ADO.NET and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] common language runtime (CLR) integration.</span></span> <span data-ttu-id="75b28-104">`System.Transactions` et ADO.NET fonctionnent conjointement pour étendre et simplifier l'utilisation de transactions locales et distribuées dans les applications managées.</span><span class="sxs-lookup"><span data-stu-id="75b28-104">`System.Transactions` and ADO.NET work together to extend and simplify the use of local and distributed transactions in managed applications.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="75b28-105">Une procédure CLR définie par l'utilisateur ne peut ni établir de connexion au serveur sur lequel elle s'exécute (connexion de bouclage) ni s'inscrire dans la même transaction.</span><span class="sxs-lookup"><span data-stu-id="75b28-105">A CLR user-defined procedure (UDP) cannot establish a connection to the same server it is running on (a loopback connection) and enlist in the same transaction.</span></span> <span data-ttu-id="75b28-106">Si cette opération est tentée, la tentative de connexion est bloquée et le contrôle n'est pas redonné à la procédure définie par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="75b28-106">If this is attempted, the connection attempt will be blocked and control will not be passed back to the UDP.</span></span> <span data-ttu-id="75b28-107">Il en résulte une erreur de délai d'attente (Msg 1206) sur la procédure définie par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="75b28-107">This will result in a timeout error (Msg 1206) on the UDP.</span></span>  
  
 <span data-ttu-id="75b28-108">Pour plus d'informations sur les transactions et le .NET Framework, consultez les rubriques relatives à l'exécution de transactions et à l'exploitation de transactions dans le Kit de développement logiciel (SDK) .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="75b28-108">For more information about transactions and the .NET Framework, see "Performing Transactions" and "Leveraging Transactions" in the .NET Framework SDK.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="75b28-109">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="75b28-109">In This Section</span></span>  
 [<span data-ttu-id="75b28-110">Promotion des transactions</span><span class="sxs-lookup"><span data-stu-id="75b28-110">Transaction Promotion</span></span>](transaction-promotion.md)  
 <span data-ttu-id="75b28-111">Décrit la possibilité de promouvoir des transactions et l'utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="75b28-111">Describes the ability to promote transactions, and how to use this feature.</span></span>  
  
 [<span data-ttu-id="75b28-112">Accès à la transaction actuelle</span><span class="sxs-lookup"><span data-stu-id="75b28-112">Accessing the Current Transaction</span></span>](accessing-the-current-transaction.md)  
 <span data-ttu-id="75b28-113">Décrit comment accéder à une transaction en cours d'exécution in-process sur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75b28-113">Describes how to access a transaction currently running in-process on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="75b28-114">Utilisation de System.Transactions</span><span class="sxs-lookup"><span data-stu-id="75b28-114">Using System.Transactions</span></span>](../native-client-ole-db-transactions/transactions.md)  
 <span data-ttu-id="75b28-115">Décrit comment utiliser l'interface de programmation d'applications (API) `System.Transactions` dans votre application managée.</span><span class="sxs-lookup"><span data-stu-id="75b28-115">Describes how to use the `System.Transactions` application programming interface (API) in your managed application.</span></span>  
  
 [<span data-ttu-id="75b28-116">Durées de vie des transactions</span><span class="sxs-lookup"><span data-stu-id="75b28-116">Transaction Lifetimes</span></span>](transaction-lifetimes.md)  
 <span data-ttu-id="75b28-117">Décrit la différence en termes de durée de vie entre les transactions démarrées dans les procédures stockées [!INCLUDE[tsql](../../includes/tsql-md.md)] et celles démarrées dans les applications CLR.</span><span class="sxs-lookup"><span data-stu-id="75b28-117">Describes the difference in lifetime between transactions started in [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures and transactions started in CLR applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75b28-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="75b28-118">See Also</span></span>  
 [<span data-ttu-id="75b28-119">Accès aux données à partir d'objets de base de données CLR</span><span class="sxs-lookup"><span data-stu-id="75b28-119">Data Access from CLR Database Objects</span></span>](../clr-integration/data-access/data-access-from-clr-database-objects.md)  
  
  
