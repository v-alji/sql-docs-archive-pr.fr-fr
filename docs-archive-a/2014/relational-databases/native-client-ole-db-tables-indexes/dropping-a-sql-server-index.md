---
title: Suppression d'un index SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- removing indexes
- deleting indexes
- DropIndex function
- dropping indexes
- SQL Server Native Client OLE DB provider, indexes
- indexes [OLE DB]
ms.assetid: add3ba14-10b1-4723-b7c0-3e83689e9fdd
author: rothja
ms.author: jroth
ms.openlocfilehash: 1267cc92645ff8b28757ad2d266e58917fcb4b28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611039"
---
# <a name="dropping-a-sql-server-index"></a><span data-ttu-id="a313d-102">Suppression d'un index SQL Server</span><span class="sxs-lookup"><span data-stu-id="a313d-102">Dropping a SQL Server Index</span></span>
  <span data-ttu-id="a313d-103">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client expose la fonction **IIndexDefinition ::D ropindex** .</span><span class="sxs-lookup"><span data-stu-id="a313d-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **IIndexDefinition::DropIndex** function.</span></span> <span data-ttu-id="a313d-104">Cela permet aux consommateurs de supprimer un index d’une table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a313d-104">This allows consumers to remove an index from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="a313d-105">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client expose certaines [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] contraintes de clé primaire et uniques en tant qu’index.</span><span class="sxs-lookup"><span data-stu-id="a313d-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes some [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PRIMARY KEY and UNIQUE constraints as indexes.</span></span> <span data-ttu-id="a313d-106">Le propriétaire de la table, le propriétaire de la base de données et certains membres munis de rôles d’administration peuvent modifier une table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en supprimant une contrainte.</span><span class="sxs-lookup"><span data-stu-id="a313d-106">The table owner, database owner, and some administrative role members can modify a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table, dropping a constraint.</span></span> <span data-ttu-id="a313d-107">Par défaut, seul le propriétaire de la table peut supprimer un index existant.</span><span class="sxs-lookup"><span data-stu-id="a313d-107">By default, only the table owner can drop an existing index.</span></span> <span data-ttu-id="a313d-108">Le succès ou l’échec de la fonction **DropIndex** ne dépend pas uniquement des droits d’accès de l’utilisateur de l’application, mais également du type d’index indiqué.</span><span class="sxs-lookup"><span data-stu-id="a313d-108">Therefore, **DropIndex** success or failure depends not only on the application user's access rights but also on the type of index indicated.</span></span>  
  
 <span data-ttu-id="a313d-109">Les consommateurs spécifient le nom de table en tant que chaîne de caractères Unicode dans le membre *pwszName* de l’union *uName* dans le paramètre *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="a313d-109">Consumers specify the table name as a Unicode character string in the *pwszName* member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="a313d-110">Le membre *eKind* de *pTableID* doit être DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="a313d-110">The *eKind* member of *pTableID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="a313d-111">Les consommateurs spécifient le nom d’index comme une chaîne de caractères Unicode dans le membre *pwszName* de l’union *uName* dans le paramètre *pIndexID*.</span><span class="sxs-lookup"><span data-stu-id="a313d-111">Consumers specify the index name as a Unicode character string in the *pwszName* member of the *uName* union in the *pIndexID* parameter.</span></span> <span data-ttu-id="a313d-112">Le membre *eKind* de *pIndexID* doit être DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="a313d-112">The *eKind* member of *pIndexID* must be DBKIND_NAME.</span></span> <span data-ttu-id="a313d-113">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client ne prend pas en charge la fonctionnalité de OLE DB de suppression de tous les index d’une table lorsque *pIndexID* a la valeur null.</span><span class="sxs-lookup"><span data-stu-id="a313d-113">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support the OLE DB feature of dropping all indexes on a table when *pIndexID* is null.</span></span> <span data-ttu-id="a313d-114">Si *pIndexID* a la valeur Null, E_INVALIDARG est retourné.</span><span class="sxs-lookup"><span data-stu-id="a313d-114">If *pIndexID* is null, E_INVALIDARG is returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a313d-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a313d-115">See Also</span></span>  
 <span data-ttu-id="a313d-116">[Tables et index](tables-and-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="a313d-116">[Tables and Indexes](tables-and-indexes.md) </span></span>  
 <span data-ttu-id="a313d-117">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a313d-117">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span></span>  
 [<span data-ttu-id="a313d-118">DROP INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a313d-118">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
  
