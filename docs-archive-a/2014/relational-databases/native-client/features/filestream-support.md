---
title: Support FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- FILESTREAM [SQL Server], SQL Server Native Client
- SQL Server Native Client [FILESTREAM support]
ms.assetid: 1ad3400d-7fcd-40c9-87ae-f5afc61e0374
author: rothja
ms.author: jroth
ms.openlocfilehash: 18e9a002bfb205e2c0807234550998fe48120d20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698088"
---
# <a name="filestream-support"></a><span data-ttu-id="82089-102">Prise en charge de FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="82089-102">FILESTREAM Support</span></span>
  <span data-ttu-id="82089-103">FILESTREAM permet de stocker et d'accéder à de grandes valeurs binaires, soit par le biais de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], soit par accès direct au système de fichiers Windows.</span><span class="sxs-lookup"><span data-stu-id="82089-103">FILESTREAM provides a way to store and access large binary values, either through [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or by direct access to the Windows file system.</span></span> <span data-ttu-id="82089-104">Une grande valeur binaire est une valeur supérieure à 2 gigaoctets (Go).</span><span class="sxs-lookup"><span data-stu-id="82089-104">A large binary value is a value larger than 2 gigabytes (GB).</span></span> <span data-ttu-id="82089-105">Pour plus d'informations sur la prise en charge FILESTREAM améliorée, consultez [FILESTREAM &#40;SQL Server&#41;](../../blob/filestream-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="82089-105">For more information about enhanced FILESTREAM support, see [FILESTREAM &#40;SQL Server&#41;](../../blob/filestream-sql-server.md).</span></span>  
  
 <span data-ttu-id="82089-106">Lorsqu'une connexion de base de données est ouverte, la valeur -1 (« illimité ») est affectée par défaut à `@@TEXTSIZE`.</span><span class="sxs-lookup"><span data-stu-id="82089-106">When a database connection is opened, `@@TEXTSIZE` will be set to -1 ("unlimited"), by default.</span></span>  
  
 <span data-ttu-id="82089-107">Il est également possible d'accéder et de mettre à jour des colonnes FILESTREAM à l'aide d'API de système de fichiers Windows.</span><span class="sxs-lookup"><span data-stu-id="82089-107">It is also possible to access and update FILESTREAM columns using Windows file system APIs.</span></span>  
  
 <span data-ttu-id="82089-108">Pour plus d'informations, voir les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="82089-108">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="82089-109">Prise en charge FILESTREAM &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="82089-109">FILESTREAM Support &#40;OLE DB&#41;</span></span>](../ole-db/filestream-support-ole-db.md)  
  
-   [<span data-ttu-id="82089-110">Prise en charge de FILESTREAM &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="82089-110">FILESTREAM Support &#40;ODBC&#41;</span></span>](../odbc/filestream-support-odbc.md)  
  
-   [<span data-ttu-id="82089-111">Accéder à des données FILESTREAM avec OpenSqlFilestream</span><span class="sxs-lookup"><span data-stu-id="82089-111">Access FILESTREAM Data with OpenSqlFilestream</span></span>](../../blob/access-filestream-data-with-opensqlfilestream.md)  
  
## <a name="querying-for-filestream-columns"></a><span data-ttu-id="82089-112">Interrogation de colonnes FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="82089-112">Querying for FILESTREAM Columns</span></span>  
 <span data-ttu-id="82089-113">Les ensembles de lignes de schéma dans OLE DB ne signalent pas si une colonne est une colonne FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="82089-113">Schema rowsets in OLE DB will not report whether a column is a FILESTREAM column.</span></span> <span data-ttu-id="82089-114">ITableDefinition dans OLE DB ne peut pas être utilisé pour créer une colonne FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="82089-114">ITableDefinition in OLE DB cannot be used to create a FILESTREAM column.</span></span>  
  
 <span data-ttu-id="82089-115">Les fonctions de catalogue telles que SQLColumns dans ODBC ne signalent pas si une colonne est une colonne FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="82089-115">Catalog functions such as SQLColumns in ODBC will not report whether a column is a FILESTREAM column.</span></span>  
  
 <span data-ttu-id="82089-116">Pour créer des colonnes FILESTREAM ou pour détecter les colonnes existantes qui sont des colonnes FILESTREAM, vous pouvez utiliser la `is_filestream` colonne de l’affichage catalogue [sys. Columns](/sql/relational-databases/system-catalog-views/sys-columns-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="82089-116">To create FILESTREAM columns or to detect which existing columns are FILESTREAM columns, you can use the `is_filestream` column of the [sys.columns](/sql/relational-databases/system-catalog-views/sys-columns-transact-sql) catalog view.</span></span>  
  
 <span data-ttu-id="82089-117">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="82089-117">The following is an example:</span></span>  
  
```  
-- Create a table with a FILESTREAM column.  
CREATE TABLE Bob_01 (GuidCol1 uniqueidentifier ROWGUIDCOL NOT NULL UNIQUE DEFAULT NEWID(), IntCol2 int, varbinaryCol3 varbinary(max) FILESTREAM);  
  
-- Find FILESTREAM columns.  
SELECT name FROM sys.columns WHERE is_filestream=1;  
  
-- Determine whether a column is a FILESTREAM column.  
SELECT is_filestream FROM sys.columns WHERE name = 'varbinaryCol3' AND object_id IN (SELECT object_id FROM sys.tables WHERE name='Bob_01');  
```  
  
## <a name="down-level-compatibility"></a><span data-ttu-id="82089-118">Compatibilité de bas niveau</span><span class="sxs-lookup"><span data-stu-id="82089-118">Down-Level Compatibility</span></span>  
 <span data-ttu-id="82089-119">Si votre client a été compilé à l’aide de la version de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client fournie avec [!INCLUDE[ssVersion2005](../../../includes/sscurrent-md.md)] , le comportement est `varbinary(max)` compatible avec [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="82089-119">If your client was compiled using the version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client that was included with [!INCLUDE[ssVersion2005](../../../includes/sscurrent-md.md)], `varbinary(max)` behavior will be compatible with [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="82089-120">Autrement dit, la taille maximale des données retournées est limitée à 2 Go.</span><span class="sxs-lookup"><span data-stu-id="82089-120">That is, the maximum size of returned data will be limited to 2 GB.</span></span> <span data-ttu-id="82089-121">Pour les valeurs de résultat supérieures à 2 Go, une troncation se produit et un avertissement « Troncation à droite de la chaîne de données » est retourné.</span><span class="sxs-lookup"><span data-stu-id="82089-121">For result values larger that 2 GB, truncation will occur and a "string data right truncation" warning will be returned.</span></span>  
  
 <span data-ttu-id="82089-122">Lorsque la compatibilité de type de données est définie à 80, le comportement client est cohérent avec le comportement client de bas niveau.</span><span class="sxs-lookup"><span data-stu-id="82089-122">When data-type compatibility is set to 80, client behavior will be consistent with down-level client behavior.</span></span>  
  
 <span data-ttu-id="82089-123">Pour les clients qui utilisent SQLOLEDB ou d’autres fournisseurs publiés avant [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] Native Client, `varbinary(max)` est mappé à image.</span><span class="sxs-lookup"><span data-stu-id="82089-123">For clients that use SQLOLEDB or other providers that were released before the [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] Native Client, `varbinary(max)` will be mapped to image.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82089-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="82089-124">See Also</span></span>  
 [<span data-ttu-id="82089-125">Fonctionnalités de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="82089-125">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
