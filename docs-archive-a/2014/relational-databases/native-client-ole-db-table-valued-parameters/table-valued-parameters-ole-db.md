---
title: Paramètres table (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, table-valued parameters
- table-valued parameters (OLE DB)
ms.assetid: 4298b73d-615b-4d28-9843-03b4d5fc489e
author: rothja
ms.author: jroth
ms.openlocfilehash: 41d125bcb254125d7f7562ca1873e8af03dab929
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706411"
---
# <a name="table-valued-parameters-ole-db"></a><span data-ttu-id="3acb2-102">Paramètres table (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="3acb2-102">Table-Valued Parameters (OLE DB)</span></span>
  <span data-ttu-id="3acb2-103">Cette section décrit la prise en charge des paramètres table dans le fournisseur OLE DB [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="3acb2-103">This section describes support for table-valued parameters in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider.</span></span> <span data-ttu-id="3acb2-104">Pour plus d’informations sur la vue d’ensemble, consultez [paramètres Table &#40;SQL Server Native Client&#41;](../native-client/features/table-valued-parameters-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="3acb2-104">For additional overview information, see [Table-Valued Parameters &#40;SQL Server Native Client&#41;](../native-client/features/table-valued-parameters-sql-server-native-client.md).</span></span> <span data-ttu-id="3acb2-105">Pour obtenir un exemple, consultez [Utiliser les paramètres table &#40;OLE DB&#41;](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="3acb2-105">For a sample, see [Use Table-Valued Parameters &#40;OLE DB&#41;](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3acb2-106">Notes</span><span class="sxs-lookup"><span data-stu-id="3acb2-106">Remarks</span></span>  
 <span data-ttu-id="3acb2-107">Vous pouvez actuellement envoyer des données à lignes multiples au serveur en tant que paramètres à une procédure avec des jeux de paramètres (le paramètre DBPARAMS dans `ICommand::Execute`).</span><span class="sxs-lookup"><span data-stu-id="3acb2-107">Currently, you can send multirow data to the server as parameters to a procedure with parameter sets (the DBPARAMS parameter in `ICommand::Execute`).</span></span> <span data-ttu-id="3acb2-108">Avec des jeux de paramètres, chaque élément du jeu doit être envoyé dans une demande d'appel de procédure distante séparée au serveur.</span><span class="sxs-lookup"><span data-stu-id="3acb2-108">With parameter sets, every element of the set has to be sent in a separate remote procedure call (RPC) request to the server.</span></span> <span data-ttu-id="3acb2-109">Les paramètres table fournissent des fonctionnalités semblables, mais l'intégration avec le serveur est meilleure.</span><span class="sxs-lookup"><span data-stu-id="3acb2-109">Table-valued parameters provide similar functionality, but there is better integration with the server.</span></span> <span data-ttu-id="3acb2-110">Cela réduit le nombre de demandes d'appel de procédure distante et autorise des opérations basées sur des jeux sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="3acb2-110">This reduces the number of RPC requests and enables set-based operations on the server.</span></span>  
  
 <span data-ttu-id="3acb2-111">Les paramètres table sont pris en charge dans le fournisseur OLE DB [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client en tant qu'objets `Rowset` OLE DB.</span><span class="sxs-lookup"><span data-stu-id="3acb2-111">Table-value parameters are supported in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider as OLE DB `Rowset` objects.</span></span> <span data-ttu-id="3acb2-112">Tout objet `Rowset` peut être fourni par le consommateur (autrement dit, l'application cliente utilisant le fournisseur OLE DB [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client) en tant qu'espace réservé pour les paramètres de paramètre table.</span><span class="sxs-lookup"><span data-stu-id="3acb2-112">Any `Rowset` object could be provided by the consumer (that is, the client application using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider) as a placeholder for table-valued parameter parameters.</span></span> <span data-ttu-id="3acb2-113">Les paramètres table sont traités comme tout autre type de paramètre [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3acb2-113">Table-valued parameters are treated like other [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] parameter types.</span></span> <span data-ttu-id="3acb2-114">Le fournisseur OLE DB [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client fournit des interfaces de création, de découverte, de spécification, de liaison et de schéma.</span><span class="sxs-lookup"><span data-stu-id="3acb2-114">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider provides creation, discovery, specification, binding and schema interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3acb2-115">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="3acb2-115">In This Section</span></span>  
  
-   [<span data-ttu-id="3acb2-116">Création d'un ensemble de lignes de paramètre table</span><span class="sxs-lookup"><span data-stu-id="3acb2-116">Table-Valued Parameter Rowset Creation</span></span>](table-valued-parameter-rowset-creation.md)  
  
-   [<span data-ttu-id="3acb2-117">Découverte du type de paramètre table</span><span class="sxs-lookup"><span data-stu-id="3acb2-117">Table-Valued Parameter Type Discovery</span></span>](../../database-engine/dev-guide/table-valued-parameter-type-discovery.md)  
  
-   [<span data-ttu-id="3acb2-118">Exécution de commandes contenant des paramètres table</span><span class="sxs-lookup"><span data-stu-id="3acb2-118">Executing Commands Containing Table-Valued Parameters</span></span>](executing-commands-containing-table-valued-parameters.md)  
  
-   [<span data-ttu-id="3acb2-119">Insertion de données dans des paramètres table</span><span class="sxs-lookup"><span data-stu-id="3acb2-119">Inserting Data into Table-Valued Parameters</span></span>](inserting-data-into-table-valued-parameters.md)  
  
-   [<span data-ttu-id="3acb2-120">Ensembles de lignes de schéma modifiés pour les paramètres table OLE DB</span><span class="sxs-lookup"><span data-stu-id="3acb2-120">Schema Rowsets Changed for OLE DB Table-Valued Parameters</span></span>](schema-rowsets-changed-for-ole-db-table-valued-parameters.md)  
  
-   [<span data-ttu-id="3acb2-121">Prise en charge du type de paramètre table OLE DB</span><span class="sxs-lookup"><span data-stu-id="3acb2-121">OLE DB Table-Valued Parameter Type Support</span></span>](ole-db-table-valued-parameter-type-support.md)  
  
-   [<span data-ttu-id="3acb2-122">Prise en charge des types de paramètre table OLE DB &#40;méthodes&#41;</span><span class="sxs-lookup"><span data-stu-id="3acb2-122">OLE DB Table-Valued Parameter Type Support &#40;Methods&#41;</span></span>](ole-db-table-valued-parameter-type-support-methods.md)  
  
-   [<span data-ttu-id="3acb2-123">Prise en charge des types de paramètre table OLE DB &#40;propriétés&#41;</span><span class="sxs-lookup"><span data-stu-id="3acb2-123">OLE DB Table-Valued Parameter Type Support &#40;Properties&#41;</span></span>](ole-db-table-valued-parameter-type-support-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="3acb2-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3acb2-124">See Also</span></span>  
 <span data-ttu-id="3acb2-125">[SQL Server Native Client &#40;OLE DB&#41;](../native-client/ole-db/sql-server-native-client-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="3acb2-125">[SQL Server Native Client &#40;OLE DB&#41;](../native-client/ole-db/sql-server-native-client-ole-db.md) </span></span>  
 [<span data-ttu-id="3acb2-126">Utiliser les paramètres table &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="3acb2-126">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
