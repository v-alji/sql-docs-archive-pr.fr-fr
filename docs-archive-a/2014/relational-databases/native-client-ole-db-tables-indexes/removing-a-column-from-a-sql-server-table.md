---
title: Suppression d'une colonne d'une table SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- columns [OLE DB]
- removing columns
- DropColumn function
- SQL Server Native Client OLE DB provider, columns
ms.assetid: 210811b7-cbd6-421e-bc6e-df9482236768
author: rothja
ms.author: jroth
ms.openlocfilehash: 8f40c466910aae7e0d349cd4a65ab265282bc8eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611037"
---
# <a name="removing-a-column-from-a-sql-server-table"></a><span data-ttu-id="958a2-102">Suppression d'une colonne d'une table SQL Server</span><span class="sxs-lookup"><span data-stu-id="958a2-102">Removing a Column from a SQL Server Table</span></span>
  <span data-ttu-id="958a2-103">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client expose la fonction **ITableDefinition ::D ropcolumn** .</span><span class="sxs-lookup"><span data-stu-id="958a2-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **ITableDefinition::DropColumn** function.</span></span> <span data-ttu-id="958a2-104">Cela permet aux consommateurs de supprimer une colonne d’une table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="958a2-104">This allows consumers to remove a column from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="958a2-105">Les consommateurs spécifient le nom de table en tant que chaîne de caractères Unicode dans le membre *pwszName* de l’union *uName* dans le paramètre *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="958a2-105">Consumers specify the table name as a Unicode character string in the *pwszName*member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="958a2-106">Le membre *eKind* de *pTableID* doit être DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="958a2-106">The *eKind*member of *pTableID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="958a2-107">Le consommateur indique un nom de colonne dans le membre *pwszName* de l'union *uName* dans le paramètre *pColumnID*.</span><span class="sxs-lookup"><span data-stu-id="958a2-107">The consumer indicates a column name in the *pwszName*member of the *uName* union in the *pColumnID* parameter.</span></span> <span data-ttu-id="958a2-108">Le nom de colonne est une chaîne de caractères Unicode.</span><span class="sxs-lookup"><span data-stu-id="958a2-108">The column name is a Unicode character string.</span></span> <span data-ttu-id="958a2-109">Le membre *eKind* de *pColumnID* doit être DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="958a2-109">The *eKind* member of *pColumnID* must be DBKIND_NAME.</span></span>  
  
## <a name="example"></a><span data-ttu-id="958a2-110">Exemple</span><span class="sxs-lookup"><span data-stu-id="958a2-110">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="958a2-111">Code</span><span class="sxs-lookup"><span data-stu-id="958a2-111">Code</span></span>  
  
```  
DBID TableID;  
DBID ColumnID;  
HRESULT hr;  
  
TableID.eKind = DBKIND_NAME;  
TableID.uName.pwszName = L"MyTableName";  
  
ColumnID.eKind = DBKIND_NAME;  
ColumnID.uName.pwszName = L"MyColumnName";  
  
hr = m_pITableDefinition->DropColumn(&TableID, &ColumnID);  
```  
  
## <a name="see-also"></a><span data-ttu-id="958a2-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="958a2-112">See Also</span></span>  
 [<span data-ttu-id="958a2-113">Tables et index</span><span class="sxs-lookup"><span data-stu-id="958a2-113">Tables and Indexes</span></span>](tables-and-indexes.md)  
  
  
