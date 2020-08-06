---
title: IRowsetFastLoad::InsertRow (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IRowsetFastLoad::InsertRow (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- InsertRow method
ms.assetid: 594d3461-34d2-41e7-8ad4-bd2753601ab6
author: rothja
ms.author: jroth
ms.openlocfilehash: 4e9ea952f27574270ee333919f778814ff3de462
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613438"
---
# <a name="irowsetfastloadinsertrow-ole-db"></a><span data-ttu-id="61685-102">IRowsetFastLoad::InsertRow (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="61685-102">IRowsetFastLoad::InsertRow (OLE DB)</span></span>
  <span data-ttu-id="61685-103">Ajoute une ligne à l'ensemble de lignes de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="61685-103">Adds a row to the bulk copy rowset.</span></span> <span data-ttu-id="61685-104">Pour obtenir des exemples, consultez [Copier des données en bloc avec IRowsetFastLoad &#40;OLE DB&#41;](../native-client-ole-db-how-to/bulk-copy-data-using-irowsetfastload-ole-db.md) et [Envoyer des données BLOB vers SQL Server en utilisant IROWSETFASTLOAD et ISEQUENTIALSTREAM &#40;OLE DB&#41;](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="61685-104">For samples, see [Bulk Copy Data Using IRowsetFastLoad &#40;OLE DB&#41;](../native-client-ole-db-how-to/bulk-copy-data-using-irowsetfastload-ole-db.md) and [Send BLOB Data to SQL SERVER Using IROWSETFASTLOAD and ISEQUENTIALSTREAM &#40;OLE DB&#41;](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61685-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="61685-105">Syntax</span></span>  
  
```  
  
HRESULT InsertRow(  
HACCESSOR  
hAccessor  
,  
void*  
pData  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="61685-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="61685-106">Arguments</span></span>  
 <span data-ttu-id="61685-107">*hAccessor*[in]</span><span class="sxs-lookup"><span data-stu-id="61685-107">*hAccessor*[in]</span></span>  
 <span data-ttu-id="61685-108">Handle de l'accesseur définissant les données de ligne pour la copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="61685-108">The handle of the accessor defining the row data for bulk copy.</span></span> <span data-ttu-id="61685-109">L'accesseur référencé est un accesseur de ligne, liant la mémoire dont le consommateur est propriétaire et qui contient les valeurs des données.</span><span class="sxs-lookup"><span data-stu-id="61685-109">The accessor referenced is a row accessor, binding consumer-owned memory containing data values.</span></span>  
  
 <span data-ttu-id="61685-110">*pData*[in]</span><span class="sxs-lookup"><span data-stu-id="61685-110">*pData*[in]</span></span>  
 <span data-ttu-id="61685-111">Pointeur vers la mémoire dont le consommateur est propriétaire et qui contient les valeurs des données.</span><span class="sxs-lookup"><span data-stu-id="61685-111">A pointer to the consumer-owned memory containing data values.</span></span> <span data-ttu-id="61685-112">Pour plus d'informations, consultez [Structures DBBINDING](https://go.microsoft.com/fwlink/?LinkId=65955).</span><span class="sxs-lookup"><span data-stu-id="61685-112">For more information, see [DBBINDING Structures](https://go.microsoft.com/fwlink/?LinkId=65955).</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="61685-113">Codet de retour</span><span class="sxs-lookup"><span data-stu-id="61685-113">Return Code Values</span></span>  
 <span data-ttu-id="61685-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="61685-114">S_OK</span></span>  
 <span data-ttu-id="61685-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="61685-115">The method succeeded.</span></span> <span data-ttu-id="61685-116">Les valeurs d'état liées de toutes les colonnes ont la valeur DBSTATUS_S_OK ou DBSTATUS_S_NULL.</span><span class="sxs-lookup"><span data-stu-id="61685-116">Any bound status values for all columns have value DBSTATUS_S_OK or DBSTATUS_S_NULL.</span></span>  
  
 <span data-ttu-id="61685-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="61685-117">E_FAIL</span></span>  
 <span data-ttu-id="61685-118">Une erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="61685-118">An error occurred.</span></span> <span data-ttu-id="61685-119">Les informations sur l'erreur sont disponibles depuis les interfaces d'erreur de l'ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="61685-119">Error information is available from the rowset's error interfaces.</span></span>  
  
 <span data-ttu-id="61685-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="61685-120">E_INVALIDARG</span></span>  
 <span data-ttu-id="61685-121">L'argument *pData* a été défini sur un pointeur NULL.</span><span class="sxs-lookup"><span data-stu-id="61685-121">The *pData* argument was set to a NULL pointer.</span></span>  
  
 <span data-ttu-id="61685-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="61685-122">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="61685-123">SQLNCLI11 ne pouvait pas allouer la mémoire suffisante pour compléter la demande.</span><span class="sxs-lookup"><span data-stu-id="61685-123">SQLNCLI11 was unable to allocate sufficient memory to complete the request.</span></span>  
  
 <span data-ttu-id="61685-124">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="61685-124">E_UNEXPECTED</span></span>  
 <span data-ttu-id="61685-125">La méthode a été appelée sur un ensemble de lignes de copie en bloc précédemment invalidé par la méthode [IRowsetFastLoad::Commit](irowsetfastload-commit-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="61685-125">The method was called on a bulk copy rowset previously invalidated by the [IRowsetFastLoad::Commit](irowsetfastload-commit-ole-db.md) method.</span></span>  
  
 <span data-ttu-id="61685-126">DB_E_BADACCESSORHANDLE</span><span class="sxs-lookup"><span data-stu-id="61685-126">DB_E_BADACCESSORHANDLE</span></span>  
 <span data-ttu-id="61685-127">L'argument *hAccessor* fourni par le consommateur n'était pas valide.</span><span class="sxs-lookup"><span data-stu-id="61685-127">The *hAccessor* argument provided by the consumer was invalid.</span></span>  
  
 <span data-ttu-id="61685-128">DB_E_BADACCESSORTYPE</span><span class="sxs-lookup"><span data-stu-id="61685-128">DB_E_BADACCESSORTYPE</span></span>  
 <span data-ttu-id="61685-129">L'accesseur spécifié n'était pas un accesseur de ligne ou ne spécifiait pas une mémoire dont le consommateur était propriétaire.</span><span class="sxs-lookup"><span data-stu-id="61685-129">The specified accessor was not a row accessor or did not specify consumer-owned memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61685-130">Notes</span><span class="sxs-lookup"><span data-stu-id="61685-130">Remarks</span></span>  
 <span data-ttu-id="61685-131">Une erreur lors de la conversion des données du consommateur en type de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour une colonne provoque un retour E_FAIL du fournisseur OLE DB [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="61685-131">An error converting consumer data to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type for a column causes an E_FAIL return from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="61685-132">Les données peuvent être transmises à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur n’importe quelle méthode **InsertRow** ou seulement sur la méthode **Commit**.</span><span class="sxs-lookup"><span data-stu-id="61685-132">Data can be transmitted to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on any **InsertRow** method or only on **Commit** method.</span></span> <span data-ttu-id="61685-133">L'application du consommateur peut appeler la méthode **InsertRow** plusieurs fois avec des données erronées avant de recevoir le message qu'une erreur de conversion de type de données s'est produite.</span><span class="sxs-lookup"><span data-stu-id="61685-133">The consumer application can call the **InsertRow** method many times with erroneous data before it receives notice that a data type conversion error exists.</span></span> <span data-ttu-id="61685-134">Comme la méthode **Commit** garantit que toutes les données sont spécifiées correctement par le consommateur, celui-ci peut utiliser la méthode **Commit** de façon appropriée pour valider les données comme nécessaire.</span><span class="sxs-lookup"><span data-stu-id="61685-134">Because the **Commit** method ensures that all data is correctly specified by the consumer, the consumer can use the **Commit** method appropriately to validate data as necessary.</span></span>  
  
 <span data-ttu-id="61685-135">Les ensembles de lignes de la copie en bloc du fournisseur OLE DB [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client sont en écriture seule.</span><span class="sxs-lookup"><span data-stu-id="61685-135">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider bulk copy rowsets are write-only.</span></span> <span data-ttu-id="61685-136">Le fournisseur OLE DB [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client n'expose aucune méthode qui autorise l'interrogation de l'ensemble de lignes par le consommateur.</span><span class="sxs-lookup"><span data-stu-id="61685-136">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes no methods allowing consumer query of the rowset.</span></span> <span data-ttu-id="61685-137">Pour terminer le traitement, le consommateur peut libérer sa référence sur l’interface [IRowsetFastLoad](irowsetfastload-ole-db.md) sans appeler la méthode **Commit**.</span><span class="sxs-lookup"><span data-stu-id="61685-137">To terminate processing, the consumer can release its reference on the [IRowsetFastLoad](irowsetfastload-ole-db.md) interface without calling the **Commit** method.</span></span> <span data-ttu-id="61685-138">Il n'existe pas d'utilitaires permettant d'accéder à une ligne insérée par le consommateur dans l'ensemble de lignes et de modifier ses valeurs, ou de la supprimer individuellement de l'ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="61685-138">There are no facilities for accessing a consumer-inserted row in the rowset and changing its values, or removing it individually from the rowset.</span></span>  
  
 <span data-ttu-id="61685-139">Les lignes copiées en bloc sont mises en forme sur le serveur pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61685-139">Bulk copied rows are formatted on the server for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="61685-140">Le format de ligne est affecté par les options qui ont pu être définies pour la connexion ou la session, telles que ANSI_PADDING.</span><span class="sxs-lookup"><span data-stu-id="61685-140">The row format is affected by any options that may have been set for the connection or session such as ANSI_PADDING.</span></span> <span data-ttu-id="61685-141">Cette option est activée par défaut pour toute connexion établie à travers le fournisseur OLE DB [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="61685-141">This option is set on by default for any connection made through the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61685-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="61685-142">See Also</span></span>  
 [<span data-ttu-id="61685-143">IRowsetFastLoad &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="61685-143">IRowsetFastLoad &#40;OLE DB&#41;</span></span>](irowsetfastload-ole-db.md)  
  
  
