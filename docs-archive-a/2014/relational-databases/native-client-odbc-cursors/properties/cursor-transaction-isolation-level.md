---
title: Niveau d’isolation des transactions de curseur | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- isolation levels [ODBC]
- ODBC applications, row versioning
- cursors [ODBC], isolation levels
- ODBC cursors, isolation levels
- row versioning [SQL Server], ODBC
ms.assetid: 0c6663a4-5a25-44aa-8fe4-e35af9bf4a83
author: rothja
ms.author: jroth
ms.openlocfilehash: 30f3dc8a9136a7cbe1d5897cb0bcc9fff8c35ab2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706484"
---
# <a name="cursor-transaction-isolation-level"></a><span data-ttu-id="1a658-102">Niveau d'isolation des transactions de curseur</span><span class="sxs-lookup"><span data-stu-id="1a658-102">Cursor Transaction Isolation Level</span></span>
  <span data-ttu-id="1a658-103">Le comportement de verrouillage complet des curseurs est basé sur une interaction entre les attributs de concurrence et le niveau d'isolation de la transaction défini par le client.</span><span class="sxs-lookup"><span data-stu-id="1a658-103">The complete locking behavior of cursors is based on an interaction between concurrency attributes and the transaction isolation level set by the client.</span></span> <span data-ttu-id="1a658-104">Les clients ODBC définissent le niveau d’isolation des transactions à l’aide des attributs [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) SQL_ATTR_TXN_ISOLATION ou SQL_COPT_SS_TXN_ISOLATION.</span><span class="sxs-lookup"><span data-stu-id="1a658-104">ODBC clients set the transaction isolation level using the [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) SQL_ATTR_TXN_ISOLATION or SQL_COPT_SS_TXN_ISOLATION attributes.</span></span> <span data-ttu-id="1a658-105">Vous pouvez déterminer le comportement de verrouillage d'un environnement de curseur particulier en associant les comportements de verrouillage des options de concurrence et de niveaux d'isolation des transactions.</span><span class="sxs-lookup"><span data-stu-id="1a658-105">The locking behavior of a specific cursor environment is determined by combining the locking behaviors of the concurrency and transaction isolation level options.</span></span>  
  
 <span data-ttu-id="1a658-106">Les niveaux d’isolation des transactions de curseurs suivants sont pris en charge par le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pilote ODBC Native Client :</span><span class="sxs-lookup"><span data-stu-id="1a658-106">The following cursor transaction isolation levels are supported by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver:</span></span>  
  
-   <span data-ttu-id="1a658-107">Lecture validée (SQL_TXN_READ_COMMITTED)</span><span class="sxs-lookup"><span data-stu-id="1a658-107">Read committed (SQL_TXN_READ_COMMITTED)</span></span>  
  
-   <span data-ttu-id="1a658-108">Lecture non validée (SQL_TXN_READ_UNCOMMITTED)</span><span class="sxs-lookup"><span data-stu-id="1a658-108">Read uncommitted (SQL_TXN_READ_UNCOMMITTED)</span></span>  
  
-   <span data-ttu-id="1a658-109">Lecture renouvelée (SQL_TXN_REPEATABLE_READ)</span><span class="sxs-lookup"><span data-stu-id="1a658-109">Repeatable read (SQL_TXN_REPEATABLE_READ)</span></span>  
  
-   <span data-ttu-id="1a658-110">Sérialisable (SQL_TXN_SERIALIZABLE)</span><span class="sxs-lookup"><span data-stu-id="1a658-110">Serializable (SQL_TXN_SERIALIZABLE)</span></span>  
  
-   <span data-ttu-id="1a658-111">Instantané (SQL_TXN_SS_SNAPSHOT)</span><span class="sxs-lookup"><span data-stu-id="1a658-111">Snapshot (SQL_TXN_SS_SNAPSHOT)</span></span>  
  
 <span data-ttu-id="1a658-112">Notez que l’API ODBC spécifie des niveaux d’isolation des transactions supplémentaires, mais ceux-ci ne sont pas pris en charge par [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ou par le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pilote ODBC Native Client.</span><span class="sxs-lookup"><span data-stu-id="1a658-112">Note that the ODBC API specifies additional transaction isolation levels, but these are not supported by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a658-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1a658-113">See Also</span></span>  
 [<span data-ttu-id="1a658-114">Propriétés de curseur</span><span class="sxs-lookup"><span data-stu-id="1a658-114">Cursor Properties</span></span>](cursor-properties.md)  
  
  
