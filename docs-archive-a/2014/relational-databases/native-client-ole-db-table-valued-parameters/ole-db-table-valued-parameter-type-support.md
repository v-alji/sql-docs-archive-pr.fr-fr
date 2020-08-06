---
title: Prise en charge des types de paramètre table OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (OLE DB), API support (OLE DB)
ms.assetid: 147036a0-260e-4f81-8b3b-89209e023a32
author: rothja
ms.author: jroth
ms.openlocfilehash: 48d5fd780b2eaa2fc18e39071d3b10fde897b82c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603473"
---
# <a name="ole-db-table-valued-parameter-type-support"></a><span data-ttu-id="b8794-102">Prise en charge du type de paramètre table OLE DB</span><span class="sxs-lookup"><span data-stu-id="b8794-102">OLE DB Table-Valued Parameter Type Support</span></span>
  <span data-ttu-id="b8794-103">Cette rubrique décrit la prise en charge du type OLE DB pour les paramètres table.</span><span class="sxs-lookup"><span data-stu-id="b8794-103">This topic describes OLE DB type support for table-value parameters.</span></span>  
  
## <a name="table-valued-parameter-rowset-object"></a><span data-ttu-id="b8794-104">Objet d'ensemble de lignes de paramètre table</span><span class="sxs-lookup"><span data-stu-id="b8794-104">Table-Valued Parameter Rowset Object</span></span>  
 <span data-ttu-id="b8794-105">Vous pouvez créer un objet d'ensemble de lignes spécialisé pour des paramètres table.</span><span class="sxs-lookup"><span data-stu-id="b8794-105">You can create a specialized rowset object for table-valued parameters.</span></span> <span data-ttu-id="b8794-106">Vous créez l’objet d’ensemble de lignes de paramètre table à l’aide de ITableDefinitionWithConstraints::CreateTableWithConstraints ou IOpenRowset::OpenRowset.</span><span class="sxs-lookup"><span data-stu-id="b8794-106">You create the table-valued parameter rowset object by using ITableDefinitionWithConstraints::CreateTableWithConstraints or IOpenRowset::OpenRowset.</span></span> <span data-ttu-id="b8794-107">Pour ce faire, définissez le membre *eKind* du paramètre *pTableID* sur DBKIND_GUID_NAME, et fournissez CLSID_ROWSET_INMEMORY comme membre *guid*.</span><span class="sxs-lookup"><span data-stu-id="b8794-107">To do this, set the *eKind* member of the *pTableID* parameter to DBKIND_GUID_NAME, and provide the CLSID_ROWSET_INMEMORY as the *guid* member.</span></span> <span data-ttu-id="b8794-108">Le nom de type de serveur pour le paramètre table doit être spécifié dans le membre *pwszName* de *pTableID* lors de l’utilisation de IOpenRowset::OpenRowset.</span><span class="sxs-lookup"><span data-stu-id="b8794-108">The server type name for the table-valued parameter must be specified in the *pwszName* member of *pTableID* when using IOpenRowset::OpenRowset.</span></span> <span data-ttu-id="b8794-109">L'objet d'ensemble de lignes de paramètre table se comporte comme un objet Fournisseur OLE DB SQL Server Native Client normal.</span><span class="sxs-lookup"><span data-stu-id="b8794-109">The table-valued parameter rowset object behaves like a regular SQL Server Native Client OLE DB Provider object.</span></span>  
  
```  
const GUID CLSID_ROWSET_TVP =   
{0xc7ef28d5, 0x7bee, 0x443f, {0x86, 0xda, 0xe3, 0x98, 0x4f, 0xcd, 0x4d, 0xf9}};  
  
CoType RowsetTVP  
{  
[mandatory] interface IAccessor;  
[mandatory] interface IColumnsInfo;  
[mandatory] interface IConvertType;  
[mandatory] interface IRowset;  
[mandatory] interface IRowsetInfo;  
[optional]  interface IColumnsRowset;  
[optional]  interface IRowsetChange;  
[optional]  interface ISupportErrorInfo;  
};  
```  
  
## <a name="dbtype_table"></a><span data-ttu-id="b8794-110">DBTYPE_TABLE</span><span class="sxs-lookup"><span data-stu-id="b8794-110">DBTYPE_TABLE</span></span>  
 <span data-ttu-id="b8794-111">DBTYPE_TABLE est un nouveau type qui représente un type de table.</span><span class="sxs-lookup"><span data-stu-id="b8794-111">A new type, DBTYPE_TABLE, represents a table type.</span></span> <span data-ttu-id="b8794-112">Ce type spécifie des paramètres table dans différentes interfaces OLE DB où un DBTYPE est requis.</span><span class="sxs-lookup"><span data-stu-id="b8794-112">This type specifies table-valued parameters in various OLE DB interfaces where a DBTYPE is required.</span></span>  
  
```  
#define DBTYPE_TABLE (143)  
```  
  
 <span data-ttu-id="b8794-113">DBTYPE_TABLE a le même format que DBTYPE_IUNKNOWN.</span><span class="sxs-lookup"><span data-stu-id="b8794-113">DBTYPE_TABLE has the same format as DBTYPE_IUNKNOWN.</span></span> <span data-ttu-id="b8794-114">Il s'agit d'un pointeur vers un objet dans le tampon de données.</span><span class="sxs-lookup"><span data-stu-id="b8794-114">It is a pointer to an object in the data buffer.</span></span> <span data-ttu-id="b8794-115">Pour une spécification complète dans les liaisons, le consommateur remplit la mémoire tampon DBOBJECT, avec *iid* défini sur l’une des interfaces d’objet d’ensemble de lignes (IID_IRowset).</span><span class="sxs-lookup"><span data-stu-id="b8794-115">For complete specification in the bindings, the consumer fills up the DBOBJECT buffer, with *iid* set to one of the rowset object interfaces (IID_IRowset).</span></span> <span data-ttu-id="b8794-116">Si aucun DBOBJECT n’est spécifié dans les liaisons, IID_IRowset est supposé.</span><span class="sxs-lookup"><span data-stu-id="b8794-116">If no DBOBJECT is specified in the bindings, IID_IRowset will be assumed.</span></span>  
  
 <span data-ttu-id="b8794-117">Les conversions vers et depuis DBTYPE_TABLE pour tout autre type ne sont pas prises en charge.</span><span class="sxs-lookup"><span data-stu-id="b8794-117">Conversions to and from DBTYPE_TABLE for any other types are not supported.</span></span> <span data-ttu-id="b8794-118">IConvertType::CanConvert retourne S_FALSE pour les conversions non prises en charge, pour toute demande autre qu’une conversion DBTYPE_TABLE en DBTYPE_TABLE.</span><span class="sxs-lookup"><span data-stu-id="b8794-118">IConvertType::CanConvert will return S_FALSE for unsupported conversion for any request other than DBTYPE_TABLE to DBTYPE_TABLE conversion.</span></span> <span data-ttu-id="b8794-119">Cela suppose DBCONVERTFLAGS_PARAMETER sur l’objet Command.</span><span class="sxs-lookup"><span data-stu-id="b8794-119">This assumes DBCONVERTFLAGS_PARAMETER on the Command object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b8794-120">Méthodes</span><span class="sxs-lookup"><span data-stu-id="b8794-120">Methods</span></span>  
 <span data-ttu-id="b8794-121">Pour plus d’informations sur les méthodes de OLE DB qui prennent en charge les paramètres table, consultez [Prise en charge des types de paramètre table OLE DB &#40;Méthodes&#41;](ole-db-table-valued-parameter-type-support-methods.md).</span><span class="sxs-lookup"><span data-stu-id="b8794-121">For information about OLE DB methods that support table-valued parameters, see [OLE DB Table-Valued Parameter Type Support &#40;Methods&#41;](ole-db-table-valued-parameter-type-support-methods.md).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b8794-122">Propriétés</span><span class="sxs-lookup"><span data-stu-id="b8794-122">Properties</span></span>  
 <span data-ttu-id="b8794-123">Pour plus d’informations sur les propriétés de OLE DB qui prennent en charge les paramètres table, consultez [Prise en charge des types de paramètre table OLE DB &#40;Propriétés&#41;](ole-db-table-valued-parameter-type-support-properties.md).</span><span class="sxs-lookup"><span data-stu-id="b8794-123">For information about OLE DB properties that support table-valued parameters, see [OLE DB Table-Valued Parameter Type Support &#40;Properties&#41;](ole-db-table-valued-parameter-type-support-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8794-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b8794-124">See Also</span></span>  
 <span data-ttu-id="b8794-125">[Paramètres table &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="b8794-125">[Table-Valued Parameters &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span></span>  
 [<span data-ttu-id="b8794-126">Utiliser les paramètres table &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="b8794-126">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
