---
title: Création d'un ensemble de lignes avec IOpenRowset | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- IOpenRowset interface
- rowsets [OLE DB], creating
- SQL Server Native Client OLE DB provider, rowsets
- OLE DB rowsets, creating
ms.assetid: e8bc3de7-4b97-4de9-8df8-e11947d24045
author: rothja
ms.author: jroth
ms.openlocfilehash: bf74466a698d39f74b9531adaa54c79c75e50ef2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707451"
---
# <a name="creating-a-rowset-with-iopenrowset"></a><span data-ttu-id="3f2c9-102">Création d'un ensemble de lignes avec IOpenRowset</span><span class="sxs-lookup"><span data-stu-id="3f2c9-102">Creating a Rowset with IOpenRowset</span></span>
  <span data-ttu-id="3f2c9-103">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client prend en charge la méthode **IOpenRowset :: OpenRowset** avec les restrictions suivantes :</span><span class="sxs-lookup"><span data-stu-id="3f2c9-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports the **IOpenRowset::OpenRowset** method with the following restrictions:</span></span>  
  
-   <span data-ttu-id="3f2c9-104">Une vue ou une table de base doit être spécifiée dans une structure d’ID de base de données (DBID) vers laquelle pointe le paramètre *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="3f2c9-104">A base table or view must be specified in a database ID (DBID) structure that the *pTableID* parameter points to.</span></span>  
  
-   <span data-ttu-id="3f2c9-105">Le membre *eKind* DBID doit indiquer DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="3f2c9-105">The DBID *eKind* member must indicate DBKIND_NAME.</span></span>  
  
-   <span data-ttu-id="3f2c9-106">Le membre *uName* DBID doit spécifier le nom d’une vue ou d’une table de base existante sous forme de chaîne de caractères Unicode.</span><span class="sxs-lookup"><span data-stu-id="3f2c9-106">The DBID *uName* member must specify the name of an existing base table or a view as a Unicode character string.</span></span>  
  
-   <span data-ttu-id="3f2c9-107">Le paramètre *pIndexID* de **OpenRowset** doit être Null.</span><span class="sxs-lookup"><span data-stu-id="3f2c9-107">The *pIndexID* parameter of **OpenRowset** must be NULL.</span></span>  
  
 <span data-ttu-id="3f2c9-108">Le jeu de résultats de **IOpenRowset::OpenRowset** contient un seul ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="3f2c9-108">The result set of **IOpenRowset::OpenRowset** contains a single rowset.</span></span> <span data-ttu-id="3f2c9-109">Les jeux de résultats qui contiennent un seul ensemble de lignes peuvent être pris en charge par les [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] curseurs.</span><span class="sxs-lookup"><span data-stu-id="3f2c9-109">Result sets that contain a single rowset can be supported by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursors.</span></span> <span data-ttu-id="3f2c9-110">La prise en charge des curseurs permet au développeur d'utiliser les mécanismes d'accès concurrentiel de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f2c9-110">Cursor support allows the developer to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] concurrency mechanisms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f2c9-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3f2c9-111">See Also</span></span>  
 [<span data-ttu-id="3f2c9-112">Ensembles de lignes</span><span class="sxs-lookup"><span data-stu-id="3f2c9-112">Rowsets</span></span>](rowsets.md)  
  
  
