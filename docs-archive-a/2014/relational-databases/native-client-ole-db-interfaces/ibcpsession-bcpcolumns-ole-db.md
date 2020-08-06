---
title: IBCPSession::BCPColumns (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPColumns (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPColumns method
ms.assetid: c338abe8-9e30-4853-a7c6-b1a6c00095e1
author: rothja
ms.author: jroth
ms.openlocfilehash: c842b2a815074c0db7e6ab21e0a85eac68a986a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707456"
---
# <a name="ibcpsessionbcpcolumns-ole-db"></a><span data-ttu-id="e069e-102">IBCPSession::BCPColumns (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="e069e-102">IBCPSession::BCPColumns (OLE DB)</span></span>
  <span data-ttu-id="e069e-103">Définit le nombre de champs qui doivent être liés aux colonnes dans une table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e069e-103">Sets the number of fields that are to be bound to the columns in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e069e-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="e069e-104">Syntax</span></span>  
  
```  
  
HRESULT BCPColumns(   
DBCOUNTITEMnColumns);  
```  
  
## <a name="remarks"></a><span data-ttu-id="e069e-105">Notes</span><span class="sxs-lookup"><span data-stu-id="e069e-105">Remarks</span></span>  
 <span data-ttu-id="e069e-106">En interne, il appelle [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) afin de définir les valeurs par défaut pour les données du champ.</span><span class="sxs-lookup"><span data-stu-id="e069e-106">Internally it calls [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) to set the default values for field data.</span></span> <span data-ttu-id="e069e-107">Ces valeurs par défaut sont obtenues à partir des informations de colonne SQL Server que le fournisseur récupère en interne lorsque le nom de la table est spécifié par le biais de [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="e069e-107">These default values are obtained from the SQL Server column information that the provider internally retrieves when the table name is specified through [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e069e-108"> Cette méthode peut être appelée uniquement après que **BCPInit** a été appelé avec un nom de fichier valide.</span><span class="sxs-lookup"><span data-stu-id="e069e-108">This method can be called only after **BCPInit** has been called with a valid file name.</span></span>  
  
 <span data-ttu-id="e069e-109">Vous devez appeler cette méthode uniquement si vous envisagez d'utiliser un format de fichier utilisateur qui diffère du format par défaut.</span><span class="sxs-lookup"><span data-stu-id="e069e-109">You should call this method only if you intend to use a user-file format that differs from the default.</span></span> <span data-ttu-id="e069e-110">Pour plus d'informations sur une description du format de fichier utilisateur par défaut, consultez la méthode **BCPInit** .</span><span class="sxs-lookup"><span data-stu-id="e069e-110">For more information about a description of the default user-file format, see the **BCPInit** method.</span></span>  
  
 <span data-ttu-id="e069e-111">Après avoir appelé la méthode **BCPColumns** , vous devez appeler la méthode **BCPColFmt** pour chaque colonne dans le fichier utilisateur afin de définir complètement un format de fichier personnalisé.</span><span class="sxs-lookup"><span data-stu-id="e069e-111">After calling the **BCPColumns** method, you must call the **BCPColFmt** method for each column in the user file to completely define a custom file format.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="e069e-112">Arguments</span><span class="sxs-lookup"><span data-stu-id="e069e-112">Arguments</span></span>  
 <span data-ttu-id="e069e-113">*nColumns*[in]</span><span class="sxs-lookup"><span data-stu-id="e069e-113">*nColumns*[in]</span></span>  
 <span data-ttu-id="e069e-114">Nombre total de champs dans le fichier utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e069e-114">The total number of fields in the user file.</span></span> <span data-ttu-id="e069e-115">Même si vous vous préparez à copier en bloc les données provenant du fichier utilisateur dans une table SQL Server et n'envisagez pas de copier tous les champs dans le fichier utilisateur, vous devez définir l'argument *nColumns* en spécifiant le nombre total de champs de fichier utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e069e-115">Even if you are preparing to bulk copy data from the user file to a SQL Server table and do not intend to copy all fields in the user file, you must still set the *nColumns* argument to the total number of user-file fields.</span></span> <span data-ttu-id="e069e-116">Les champs omis peuvent alors être spécifiés par le biais de **BCPColFmt**.</span><span class="sxs-lookup"><span data-stu-id="e069e-116">The skipped fields can then be specified through **BCPColFmt**.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="e069e-117">Codet de retour</span><span class="sxs-lookup"><span data-stu-id="e069e-117">Return Code Values</span></span>  
 <span data-ttu-id="e069e-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="e069e-118">S_OK</span></span>  
 <span data-ttu-id="e069e-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="e069e-119">The method succeeded.</span></span>  
  
 <span data-ttu-id="e069e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e069e-120">E_FAIL</span></span>  
 <span data-ttu-id="e069e-121">Une erreur spécifique au fournisseur s’est produite ; Pour plus d’informations, utilisez l’interface [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="e069e-121">A provider-specific error occurred; for detailed information, use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="e069e-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="e069e-122">E_UNEXPECTED</span></span>  
 <span data-ttu-id="e069e-123">L'appel à la méthode était inattendu.</span><span class="sxs-lookup"><span data-stu-id="e069e-123">The call to the method was unexpected.</span></span> <span data-ttu-id="e069e-124">Par exemple, la méthode **BCPInit** n'a pas été appelée avant cette méthode.</span><span class="sxs-lookup"><span data-stu-id="e069e-124">For example, the **BCPInit** method was not called before calling this method.</span></span> <span data-ttu-id="e069e-125">Cela se produit également lorsque cette méthode est appelée plus d'une fois pour une opération de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="e069e-125">Also occurs when this method is called more than once for a bulk copy operation.</span></span>  
  
 <span data-ttu-id="e069e-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="e069e-126">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="e069e-127">Erreur de mémoire insuffisante.</span><span class="sxs-lookup"><span data-stu-id="e069e-127">Out-of-memory error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e069e-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e069e-128">See Also</span></span>  
 <span data-ttu-id="e069e-129">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="e069e-129">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span></span>  
 [<span data-ttu-id="e069e-130">Exécution d'opérations de copie en bloc</span><span class="sxs-lookup"><span data-stu-id="e069e-130">Performing Bulk Copy Operations</span></span>](../native-client/features/performing-bulk-copy-operations.md)  
  
  
