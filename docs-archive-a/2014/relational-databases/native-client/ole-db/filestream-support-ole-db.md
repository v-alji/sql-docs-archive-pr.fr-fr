---
title: Prise en charge de FILESTREAM (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB [FILESTREAM support]
- FILESTREAM [SQL Server], OLE DB
ms.assetid: c2bd3dfd-6103-43d1-859e-8ed8d19c58d3
author: rothja
ms.author: jroth
ms.openlocfilehash: cde3c2cd1b72773cfcf17eacedeb3276dd2f63da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611746"
---
# <a name="filestream-support-ole-db"></a><span data-ttu-id="80c1b-102">Prise en charge de FILESTREAM (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="80c1b-102">FILESTREAM Support (OLE DB)</span></span>
  <span data-ttu-id="80c1b-103">Depuis [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] et [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10,0, OLE DB prend en charge la fonctionnalité FileStream améliorée.</span><span class="sxs-lookup"><span data-stu-id="80c1b-103">Beginning with [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10.0, OLE DB supports the enhanced FILESTREAM feature.</span></span> <span data-ttu-id="80c1b-104">Pour plus d’informations sur cette fonctionnalité, consultez [prise en charge de FileStream](../features/filestream-support.md).</span><span class="sxs-lookup"><span data-stu-id="80c1b-104">For more information about this feature, see [FILESTREAM Support](../features/filestream-support.md).</span></span> <span data-ttu-id="80c1b-105">Pour obtenir des exemples, consultez [Filestream et OLE DB](../../native-client-ole-db-how-to/filestream/filestream-and-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="80c1b-105">For samples, see [Filestream and OLE DB](../../native-client-ole-db-how-to/filestream/filestream-and-ole-db.md).</span></span>  
  
 <span data-ttu-id="80c1b-106">Pour envoyer et recevoir des valeurs `varbinary(max)` supérieures à 2 Go, une application utilise `DBTYPE_IUNKNOWN` dans les liaisons de résultat et de paramètre.</span><span class="sxs-lookup"><span data-stu-id="80c1b-106">To send and receive `varbinary(max)` values greater than 2 GB, an application uses `DBTYPE_IUNKNOWN` in parameter and result bindings.</span></span> <span data-ttu-id="80c1b-107">Pour les paramètres, le fournisseur doit appeler IUnknown::QueryInterface pour ISequentialStream et pour les résultats qui retournent ISequentialStream.</span><span class="sxs-lookup"><span data-stu-id="80c1b-107">For parameters the provider must call IUnknown::QueryInterface for ISequentialStream and for results that return ISequentialStream.</span></span>  
  
 <span data-ttu-id="80c1b-108">Pour OLE DB, la vérification en rapport avec les valeurs ISequentialStream sera levée.</span><span class="sxs-lookup"><span data-stu-id="80c1b-108">For OLE DB, checking related to ISequentialStream values will be relaxed.</span></span> <span data-ttu-id="80c1b-109">Quand *wType* se trouve `DBTYPE_IUNKNOWN` dans le `DBBINDING` struct, la vérification de la longueur peut être désactivée en omettant `DBPART_LENGTH` de *dwPart* ou en définissant la longueur des données (au niveau du décalage *obLength* dans le tampon de données) sur ~ 0.</span><span class="sxs-lookup"><span data-stu-id="80c1b-109">When *wType* is `DBTYPE_IUNKNOWN` in the `DBBINDING` struct, length checking can be disabled either by omitting `DBPART_LENGTH` from *dwPart* or by setting the length of the data (at offset *obLength* in the data buffer) to ~0.</span></span> <span data-ttu-id="80c1b-110">Dans ce cas, le fournisseur ne vérifiera pas la longueur de la valeur et demandera et retournera toutes les données disponibles par le biais du flux de données.</span><span class="sxs-lookup"><span data-stu-id="80c1b-110">In this case, the provider will not check the length of the value and will request and return all of the data available through the stream.</span></span> <span data-ttu-id="80c1b-111">Cette modification sera appliquée à tous les types d'objets volumineux (LOB) et XML, mais uniquement en cas de connexion à des serveurs [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] (ou ultérieurs).</span><span class="sxs-lookup"><span data-stu-id="80c1b-111">This change will be applied to all large object (LOB) types and XML, but only when connected to [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] (or later) servers.</span></span> <span data-ttu-id="80c1b-112">Cela offrira une plus grande souplesse aux développeurs, tout en maintenant la cohérence et la compatibilité descendante des applications existantes et des serveurs de niveau inférieur.</span><span class="sxs-lookup"><span data-stu-id="80c1b-112">This will provide greater flexibility for developers, while maintaining consistency and backwards compatibility for existing applications and downlevel servers.</span></span>  
  
 <span data-ttu-id="80c1b-113">Cette modification affecte toutes les interfaces qui transfèrent des données, principalement IRowset::GetData, ICommand::Execute et IRowsetFastLoad::InsertRow.</span><span class="sxs-lookup"><span data-stu-id="80c1b-113">This change affects all interfaces that transfer data, principally IRowset::GetData, ICommand::Execute, and IRowsetFastLoad::InsertRow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80c1b-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="80c1b-114">See Also</span></span>  
 [<span data-ttu-id="80c1b-115">Programmation de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="80c1b-115">SQL Server Native Client Programming</span></span>](../sql-server-native-client-programming.md)  
  
  
