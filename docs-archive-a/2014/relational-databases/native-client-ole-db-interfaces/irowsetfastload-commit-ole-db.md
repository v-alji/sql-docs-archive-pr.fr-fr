---
title: IRowsetFastLoad::Commit (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IRowsetFastLoad::Commit (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- Commit method
ms.assetid: 19de9128-b91a-4626-847f-af721edaa24e
author: rothja
ms.author: jroth
ms.openlocfilehash: cfdf355919f65fd2cedacd09249e2aae59321390
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613442"
---
# <a name="irowsetfastloadcommit-ole-db"></a><span data-ttu-id="2a626-102">IRowsetFastLoad::Commit (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="2a626-102">IRowsetFastLoad::Commit (OLE DB)</span></span>
  <span data-ttu-id="2a626-103">Marque la fin d'un lot de lignes insérées et écrit les lignes dans la table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2a626-103">Marks the end of a batch of inserted rows and writes the rows to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="2a626-104">Pour obtenir des exemples, consultez [Copier des données en bloc avec IRowsetFastLoad &#40;OLE DB&#41;](irowsetfastload-ole-db.md) et [Envoyer des données BLOB vers SQL Server en utilisant IROWSETFASTLOAD et ISEQUENTIALSTREAM &#40;OLE DB&#41;](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="2a626-104">For samples, see [Bulk Copy Data Using IRowsetFastLoad &#40;OLE DB&#41;](irowsetfastload-ole-db.md) and [Send BLOB Data to SQL SERVER Using IROWSETFASTLOAD and ISEQUENTIALSTREAM &#40;OLE DB&#41;](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a626-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2a626-105">Syntax</span></span>  
  
```  
  
HRESULT Commit(  
BOOL   
fDone  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="2a626-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="2a626-106">Arguments</span></span>  
 <span data-ttu-id="2a626-107">*fDone*[in]</span><span class="sxs-lookup"><span data-stu-id="2a626-107">*fDone*[in]</span></span>  
 <span data-ttu-id="2a626-108">Si FALSE, l'ensemble de lignes conserve la validation et peut être utilisé par le consommateur pour l'insertion de ligne supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="2a626-108">If FALSE, the rowset maintains validity and can be used by the consumer for additional row insertion.</span></span> <span data-ttu-id="2a626-109">Si TRUE, l'ensemble de lignes perd la validation et aucune insertion supplémentaire ne peut être effectuée par le consommateur.</span><span class="sxs-lookup"><span data-stu-id="2a626-109">If TRUE, the rowset loses validity and no further insertion can be done by the consumer.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="2a626-110">Codet de retour</span><span class="sxs-lookup"><span data-stu-id="2a626-110">Return Code Values</span></span>  
 <span data-ttu-id="2a626-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2a626-111">S_OK</span></span>  
 <span data-ttu-id="2a626-112">La méthode a réussi et toutes les données insérées ont été écrites dans la table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a626-112">The method succeeded and all inserted data has been written to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="2a626-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2a626-113">E_FAIL</span></span>  
 <span data-ttu-id="2a626-114">Une erreur spécifique au fournisseur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="2a626-114">A provider-specific error occurred.</span></span> <span data-ttu-id="2a626-115">Extrayez les informations sur l'erreur pour le texte d'erreur spécifique à partir du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="2a626-115">Retrieve error information for the specific error text from the provider.</span></span>  
  
 <span data-ttu-id="2a626-116">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="2a626-116">E_UNEXPECTED</span></span>  
 <span data-ttu-id="2a626-117">La méthode a été appelée sur un ensemble de lignes de copie en bloc précédemment invalidé par la méthode **IRowsetFastLoad::Commit**.</span><span class="sxs-lookup"><span data-stu-id="2a626-117">The method was called on a bulk copy rowset previously invalidated by the **IRowsetFastLoad::Commit** method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a626-118">Notes</span><span class="sxs-lookup"><span data-stu-id="2a626-118">Remarks</span></span>  
 <span data-ttu-id="2a626-119">Un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ensemble de lignes de copie en bloc du fournisseur Native Client OLE DB se comporte comme un ensemble de lignes en mode de mise à jour différée.</span><span class="sxs-lookup"><span data-stu-id="2a626-119">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider bulk copy rowset behaves as a delayed-update mode rowset.</span></span> <span data-ttu-id="2a626-120">Quand l’utilisateur insère des données de ligne dans l’ensemble de lignes, les lignes insérées sont traitées de la même façon que les insertions en attente sur un ensemble de lignes prenant en charge **IRowsetUpdate**.</span><span class="sxs-lookup"><span data-stu-id="2a626-120">As the user inserts row data through the rowset, inserted rows are treated in the same fashion as pending inserts on a rowset supporting **IRowsetUpdate**.</span></span>  
  
 <span data-ttu-id="2a626-121">Le consommateur doit appeler la méthode **Commit** sur l’ensemble de lignes de copie en bloc pour écrire les lignes insérées dans la table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], de la même façon que la méthode **IRowsetUpdate::Update** est utilisée pour soumettre des lignes en attente à une instance de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2a626-121">The consumer must call the **Commit** method on the bulk copy rowset to write inserted rows to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table in the same way as the **IRowsetUpdate::Update** method is used to submit pending rows to an instance of SQL Server.</span></span>  
  
 <span data-ttu-id="2a626-122">Si le consommateur libère sa référence sur l’ensemble de lignes de copie en bloc sans appeler la méthode **Commit**, toutes les lignes insérées non écrites précédemment sont perdues.</span><span class="sxs-lookup"><span data-stu-id="2a626-122">If the consumer releases its reference on the bulk copy rowset without calling the **Commit** method, all inserted rows not previously written are lost.</span></span>  
  
 <span data-ttu-id="2a626-123">Le consommateur peut insérer des lignes par lot en appelant la méthode **Commit** avec l’argument *fDone* défini sur FALSE.</span><span class="sxs-lookup"><span data-stu-id="2a626-123">The consumer can batch inserted rows by calling the **Commit** method with the *fDone* argument set to FALSE.</span></span> <span data-ttu-id="2a626-124">Quand *fDone* est défini sur TRUE, l’ensemble de lignes devient non valide.</span><span class="sxs-lookup"><span data-stu-id="2a626-124">When *fDone*is set to TRUE, the rowset becomes invalid.</span></span> <span data-ttu-id="2a626-125">Un ensemble de lignes de copie en bloc non valide prend en charge seulement l’interface **ISupportErrorInfo** et la méthode **IRowsetFastLoad::Release**.</span><span class="sxs-lookup"><span data-stu-id="2a626-125">An invalid bulk copy rowset supports only the **ISupportErrorInfo** interface and **IRowsetFastLoad::Release** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a626-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2a626-126">See Also</span></span>  
 [<span data-ttu-id="2a626-127">IRowsetFastLoad &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="2a626-127">IRowsetFastLoad &#40;OLE DB&#41;</span></span>](irowsetfastload-ole-db.md)  
  
  
