---
title: Ajout d'une colonne à une table SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- columns [OLE DB]
- AddColumn function
- SQL Server Native Client OLE DB provider, columns
- adding columns
ms.assetid: 22bae18a-bc9d-4617-8660-ed8b17a468d4
author: rothja
ms.author: jroth
ms.openlocfilehash: 97aa2656ccde662a34e1dd80fd662b22f601d4ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707443"
---
# <a name="adding-a-column-to-a-sql-server-table"></a><span data-ttu-id="4d85b-102">Ajout d'une colonne à une table SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4d85b-102">Adding a Column to a SQL Server Table</span></span>
  <span data-ttu-id="4d85b-103">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client expose la fonction **ITableDefinition :: AddColumn** .</span><span class="sxs-lookup"><span data-stu-id="4d85b-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **ITableDefinition::AddColumn** function.</span></span> <span data-ttu-id="4d85b-104">Cela permet aux consommateurs d’ajouter une colonne à une table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d85b-104">This allows consumers to add a column to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="4d85b-105">Lorsque vous ajoutez une colonne à une [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consommateur du fournisseur OLE DB Native Client est restreint comme suit :</span><span class="sxs-lookup"><span data-stu-id="4d85b-105">When you add a column to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer is constrained as follows:</span></span>  
  
-   <span data-ttu-id="4d85b-106">Si DBPROP_COL_AUTOINCREMENT est VARIANT_TRUE, DBPROP_COL_NULLABLE doit être VARIANT_FALSE.</span><span class="sxs-lookup"><span data-stu-id="4d85b-106">If DBPROP_COL_AUTOINCREMENT is VARIANT_TRUE, DBPROP_COL_NULLABLE must be VARIANT_FALSE.</span></span>  
  
-   <span data-ttu-id="4d85b-107">Si la colonne est définie en utilisant le type de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **timestamp**, DBPROP_COL_NULLABLE doit être VARIANT_FALSE.</span><span class="sxs-lookup"><span data-stu-id="4d85b-107">If the column is defined by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **timestamp** data type, DBPROP_COL_NULLABLE must be VARIANT_FALSE.</span></span>  
  
-   <span data-ttu-id="4d85b-108">Pour toute autre définition de colonne, DBPROP_COL_NULLABLE doit être VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="4d85b-108">For any other column definition, DBPROP_COL_NULLABLE must be VARIANT_TRUE.</span></span>  
  
 <span data-ttu-id="4d85b-109">Les consommateurs spécifient le nom de table en tant que chaîne de caractères Unicode dans le membre *pwszName* de l’union *uName* dans le paramètre *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="4d85b-109">Consumers specify the table name as a Unicode character string in the *pwszName* member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="4d85b-110">Le membre *eKind* de *pTableID* doit être DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="4d85b-110">The *eKind* member of *pTableID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="4d85b-111">Le nouveau nom de colonne est spécifié en tant que chaîne de caractères Unicode dans le membre *pwszName* de l’union *uName* dans le membre *dbcid* du paramètre DBCOLUMNDESC *pColumnDesc*.</span><span class="sxs-lookup"><span data-stu-id="4d85b-111">The new column name is specified as a Unicode character string in the *pwszName* member of the *uName* union in the *dbcid* member of the DBCOLUMNDESC parameter *pColumnDesc*.</span></span> <span data-ttu-id="4d85b-112">Le membre *eKind* doit être DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="4d85b-112">The *eKind* member must be DBKIND_NAME.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d85b-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4d85b-113">See Also</span></span>  
 <span data-ttu-id="4d85b-114">[Tables et index](tables-and-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="4d85b-114">[Tables and Indexes](tables-and-indexes.md) </span></span>  
 [<span data-ttu-id="4d85b-115">ALTER TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4d85b-115">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
  
