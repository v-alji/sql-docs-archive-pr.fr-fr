---
title: SQLEndTran | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLEndTran function
ms.assetid: 95cff841-c2d5-4e1e-a18d-f3d4696a5b85
author: rothja
ms.author: jroth
ms.openlocfilehash: e5d44756131b6133baec69e34da11055a965e2da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698183"
---
# <a name="sqlendtran"></a><span data-ttu-id="32ebf-102">SQLEndTran</span><span class="sxs-lookup"><span data-stu-id="32ebf-102">SQLEndTran</span></span>
  <span data-ttu-id="32ebf-103">Par défaut, le pilote ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ferme le curseur associé à une instruction lorsque **SQLEndTran** valide ou restaure une opération.</span><span class="sxs-lookup"><span data-stu-id="32ebf-103">By default, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver closes a statement's associated cursor when **SQLEndTran** commits or rolls back an operation.</span></span> <span data-ttu-id="32ebf-104">Les curseurs côté serveur sont fermés à moins qu'ils ne soient statiques.</span><span class="sxs-lookup"><span data-stu-id="32ebf-104">Server cursors are closed unless they are static.</span></span> <span data-ttu-id="32ebf-105">Lorsque **SQLEndTran** valide ou restaure une opération, le comportement du curseur associé à l'instruction est déterminé par la valeur de l'attribut de connexion ODBC du pilote spécifique au fournisseur, SQL_COPT_SS_PRESERVE_CURSORS, défini par [SQLSetConnectAttr](sqlsetconnectattr.md).</span><span class="sxs-lookup"><span data-stu-id="32ebf-105">When **SQLEndTran** commits or rolls back an operation, the behavior of the statement's associated cursor is determined by the value of the driver-specific ODBC connection attribute SQL_COPT_SS_PRESERVE_CURSORS, set by [SQLSetConnectAttr](sqlsetconnectattr.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32ebf-106">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="32ebf-106">See Also</span></span>  
 <span data-ttu-id="32ebf-107">[Détails de l’implémentation de l’API ODBC](odbc-api-implementation-details.md) </span><span class="sxs-lookup"><span data-stu-id="32ebf-107">[ODBC API Implementation Details](odbc-api-implementation-details.md) </span></span>  
 [<span data-ttu-id="32ebf-108">Fonction SQLEndTran</span><span class="sxs-lookup"><span data-stu-id="32ebf-108">SQLEndTran Function</span></span>](https://go.microsoft.com/fwlink/?LinkId=59342)  
  
  
