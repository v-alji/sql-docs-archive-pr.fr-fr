---
title: Niveaux d’isolement (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, transactions
- isolation levels [OLE DB]
- transactions [OLE DB]
- SQL Server Native Client OLE DB provider, transactions
ms.assetid: d70ee72c-6e2a-4bcd-9456-4a697a866361
author: rothja
ms.author: jroth
ms.openlocfilehash: c7f6cbff4e68eaedd3e78a82cddd872ba5f8f19e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611034"
---
# <a name="isolation-levels-ole-db"></a><span data-ttu-id="a8d9b-102">Niveaux d'isolation (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="a8d9b-102">Isolation Levels (OLE DB)</span></span>
  <span data-ttu-id="a8d9b-103">Les clients [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peuvent contrôler les niveaux d'isolation des transactions pour une connexion.</span><span class="sxs-lookup"><span data-stu-id="a8d9b-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clients can control transaction-isolation levels for a connection.</span></span> <span data-ttu-id="a8d9b-104">Pour contrôler le niveau d’isolation des transactions, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consommateur du fournisseur OLE DB Native Client utilise :</span><span class="sxs-lookup"><span data-stu-id="a8d9b-104">To control transaction-isolation level, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer uses:</span></span>  
  
-   <span data-ttu-id="a8d9b-105">DBPROPSET_SESSION DBPROP_SESS_AUTOCOMMITISOLEVELS de propriété pour le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mode de validation automatique par défaut du fournisseur OLE DB Native Client.</span><span class="sxs-lookup"><span data-stu-id="a8d9b-105">DBPROPSET_SESSION property DBPROP_SESS_AUTOCOMMITISOLEVELS for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider default autocommit mode.</span></span>  
  
     <span data-ttu-id="a8d9b-106">La [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] valeur par défaut du fournisseur de OLE DB Native Client pour le niveau est DBPROPVAL_TI_READCOMMITTED.</span><span class="sxs-lookup"><span data-stu-id="a8d9b-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider default for the level is DBPROPVAL_TI_READCOMMITTED.</span></span>  
  
-   <span data-ttu-id="a8d9b-107">Le paramètre *isoLevel* de la méthode **ITransactionLocal::StartTransaction** pour les transactions de validation manuelle locales.</span><span class="sxs-lookup"><span data-stu-id="a8d9b-107">The *isoLevel* parameter of the **ITransactionLocal::StartTransaction** method for local manual-commit transactions.</span></span>  
  
-   <span data-ttu-id="a8d9b-108">Le paramètre *isoLevel* de la méthode **ITransactionDispenser::BeginTransaction** pour les transactions distribuées coordonnées par MS DTC.</span><span class="sxs-lookup"><span data-stu-id="a8d9b-108">The *isoLevel* parameter of the **ITransactionDispenser::BeginTransaction** method for MS DTC-coordinated distributed transactions.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a8d9b-109">autorise l'accès en lecture seule au niveau d'isolation de lecture erronée.</span><span class="sxs-lookup"><span data-stu-id="a8d9b-109">allows read-only access at the dirty read isolation level.</span></span> <span data-ttu-id="a8d9b-110">Tous les autres niveaux restreignent la concurrence en appliquant des verrous aux objets [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8d9b-110">All other levels restrict concurrency by applying locks to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objects.</span></span> <span data-ttu-id="a8d9b-111">Comme le client a besoin de niveaux d'accès concurrentiel supérieurs, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] applique des restrictions supérieures sur l'accès concurrentiel aux données.</span><span class="sxs-lookup"><span data-stu-id="a8d9b-111">As the client requires greater concurrency levels, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] applies greater restrictions on concurrent access to data.</span></span> <span data-ttu-id="a8d9b-112">Pour maintenir le plus haut niveau d’accès simultané aux données, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consommateur du fournisseur OLE DB Native Client doit contrôler intelligemment ses demandes de niveaux de concurrence spécifiques.</span><span class="sxs-lookup"><span data-stu-id="a8d9b-112">To maintain the highest level of concurrent access to data, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer should intelligently control its requests for specific concurrency levels.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="a8d9b-113">a introduit le niveau d'isolement d'instantané.</span><span class="sxs-lookup"><span data-stu-id="a8d9b-113">introduced snapshot isolation level.</span></span> <span data-ttu-id="a8d9b-114">Pour plus d’informations, consultez [Utilisation du niveau d’isolement d’instantané](../native-client/features/working-with-snapshot-isolation.md).</span><span class="sxs-lookup"><span data-stu-id="a8d9b-114">For more information, see [Working with Snapshot Isolation](../native-client/features/working-with-snapshot-isolation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8d9b-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a8d9b-115">See Also</span></span>  
 [<span data-ttu-id="a8d9b-116">Transactions</span><span class="sxs-lookup"><span data-stu-id="a8d9b-116">Transactions</span></span>](transactions.md)  
  
  
