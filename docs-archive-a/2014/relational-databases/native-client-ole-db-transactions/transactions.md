---
title: Transactions | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, transactions
- transactions [OLE DB]
- SQL Server Native Client OLE DB provider, transactions
ms.assetid: 3b41e33a-c1ca-4b2a-9464-312b0ed3ca89
author: rothja
ms.author: jroth
ms.openlocfilehash: 1067820e80f9c7a4e1af2c8a14c85bc9dbfdd6aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612777"
---
# <a name="transactions"></a><span data-ttu-id="2ff2e-102">Transactions</span><span class="sxs-lookup"><span data-stu-id="2ff2e-102">Transactions</span></span>
  <span data-ttu-id="2ff2e-103">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client implémente la prise en charge des transactions locales.</span><span class="sxs-lookup"><span data-stu-id="2ff2e-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements local transaction support.</span></span> <span data-ttu-id="2ff2e-104">Le consommateur peut utiliser des transactions distribuées ou coordonnées à l'aide de Microsoft Distributed Transaction Coordinator (MS DTC).</span><span class="sxs-lookup"><span data-stu-id="2ff2e-104">The consumer can use distributed or coordinated transactions by using Microsoft Distributed Transaction Coordinator (MS DTC).</span></span> <span data-ttu-id="2ff2e-105">Pour les consommateurs qui requièrent un contrôle des transactions qui s’étend sur plusieurs sessions, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client peut joindre des transactions initiées et gérées par MS DTC.</span><span class="sxs-lookup"><span data-stu-id="2ff2e-105">For consumers requiring transaction control that spans multiple sessions, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider can join transactions initiated and maintained by MS DTC.</span></span>  
  
 <span data-ttu-id="2ff2e-106">Par défaut, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client utilise un mode de transaction AutoCommit, où chaque action discrète sur une session de consommateur comprend une transaction complète sur une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2ff2e-106">By default, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider uses an autocommit transaction mode, where each discrete action on a consumer session comprises a complete transaction against an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2ff2e-107">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mode de validation automatique du fournisseur OLE DB Native Client est local, et les transactions de validation automatique ne s’étendent jamais sur plus d’une seule session.</span><span class="sxs-lookup"><span data-stu-id="2ff2e-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider autocommit mode is local, and autocommit transactions never span more than a single session.</span></span>  
  
 <span data-ttu-id="2ff2e-108">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client expose l’interface **ITransactionLocal** , ce qui permet au consommateur d’utiliser des transactions de démarrage explicite et implicite sur une connexion unique à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2ff2e-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **ITransactionLocal** interface, allowing the consumer to use explicitly and implicitly start transactions on a single connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2ff2e-109">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client ne prend pas en charge les transactions locales imbriquées.</span><span class="sxs-lookup"><span data-stu-id="2ff2e-109">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support nested local transactions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2ff2e-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="2ff2e-110">In This Section</span></span>  
  
-   [<span data-ttu-id="2ff2e-111">Prise en charge des transactions locales</span><span class="sxs-lookup"><span data-stu-id="2ff2e-111">Supporting Local Transactions</span></span>](supporting-local-transactions.md)  
  
-   [<span data-ttu-id="2ff2e-112">Prise en charge des transactions distribuées</span><span class="sxs-lookup"><span data-stu-id="2ff2e-112">Supporting Distributed Transactions</span></span>](supporting-distributed-transactions.md)  
  
-   [<span data-ttu-id="2ff2e-113">Niveaux d'isolation &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="2ff2e-113">Isolation Levels &#40;OLE DB&#41;</span></span>](isolation-levels-ole-db.md)  
  
## <a name="see-also"></a><span data-ttu-id="2ff2e-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2ff2e-114">See Also</span></span>  
 [<span data-ttu-id="2ff2e-115">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="2ff2e-115">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
