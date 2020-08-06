---
title: SQLColumnPrivileges | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLColumnPrivileges function
ms.assetid: c78acd4e-8668-4abc-9bc9-6ad381965863
author: rothja
ms.author: jroth
ms.openlocfilehash: bf46fed47817ed94ea2382f2147df254f2986aec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602129"
---
# <a name="sqlcolumnprivileges"></a><span data-ttu-id="b54b0-102">SQLColumnPrivileges</span><span class="sxs-lookup"><span data-stu-id="b54b0-102">SQLColumnPrivileges</span></span>
  <span data-ttu-id="b54b0-103">**SQLColumnPrivileges** retourne SQL_SUCCESS si des valeurs existent pour les paramètres*nomcatalogue*, *SchemaName*, *TableName*ou *ColumnName* .</span><span class="sxs-lookup"><span data-stu-id="b54b0-103">**SQLColumnPrivileges** returns SQL_SUCCESS whether or not values exist for the*CatalogName*, *SchemaName*, *TableName*, or *ColumnName* parameters.</span></span> <span data-ttu-id="b54b0-104">**SQLFetch** retourne SQL_NO_DATA lorsque des valeurs non valides sont utilisées dans ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="b54b0-104">**SQLFetch** returns SQL_NO_DATA when invalid values are used in these parameters.</span></span>  
  
 <span data-ttu-id="b54b0-105">**SQLColumnPrivileges** peut être exécuté sur un curseur côté serveur statique.</span><span class="sxs-lookup"><span data-stu-id="b54b0-105">**SQLColumnPrivileges** can be executed on a static server cursor.</span></span> <span data-ttu-id="b54b0-106">Une tentative d’exécution de **SQLColumnPrivileges** sur un curseur pouvant être mis à jour (dynamique ou de jeu de clés) retourne SQL_SUCCESS_WITH_INFO indiquant que le type de curseur a été modifié.</span><span class="sxs-lookup"><span data-stu-id="b54b0-106">An attempt to execute **SQLColumnPrivileges** on an updatable (dynamic or keyset) cursor will return SQL_SUCCESS_WITH_INFO indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="b54b0-107">Le pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client prend en charge les informations de création de rapport pour les tables des serveurs liés en acceptant un nom en deux parties pour le paramètre *CatalogName* : *Linked_Server_Name.Catalog_Name*.</span><span class="sxs-lookup"><span data-stu-id="b54b0-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *CatalogName* parameter: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b54b0-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b54b0-108">See Also</span></span>  
 <span data-ttu-id="b54b0-109">[SQLColumnPrivileges fonction)](https://go.microsoft.com/fwlink/?LinkId=59335) </span><span class="sxs-lookup"><span data-stu-id="b54b0-109">[SQLColumnPrivileges Function](https://go.microsoft.com/fwlink/?LinkId=59335) </span></span>  
 [<span data-ttu-id="b54b0-110">Détails de l’implémentation d’API ODBC</span><span class="sxs-lookup"><span data-stu-id="b54b0-110">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
