---
title: Importer en bloc des données d’objet volumineux à l’aide du fournisseur d’ensembles de lignes OPENROWSET (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- SINGLE_NCLOB option
- bulk rowset providers [SQL Server]
- bulk importing [SQL Server], data formats
- OPENROWSET function, bulk importing large data
- SINGLE_CLOB option
- data formats [SQL Server], large-object data
- large data, bulk imports
- SINGLE_BLOB option
ms.assetid: 171cdd5c-1e47-4bd7-b99a-4f0fd4e10526
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0f43aa2fa5e7f7ef0b2c8f1f6e5e6ff28e02f9f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604446"
---
# <a name="bulk-import-large-object-data-by-using-the-openrowset-bulk-rowset-provider-sql-server"></a><span data-ttu-id="494aa-102">Importer en bloc des données LOB au moyen du fournisseur d'ensembles de lignes OPENROWSET (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="494aa-102">Bulk Import Large-Object Data by using the OPENROWSET Bulk Rowset Provider (SQL Server)</span></span>
  <span data-ttu-id="494aa-103">Le fournisseur d'ensembles de lignes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] OPENROWSET vous permet d'importer en bloc un fichier de données en données LOB.</span><span class="sxs-lookup"><span data-stu-id="494aa-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] OPENROWSET Bulk Rowset Provider enables you to bulk import a data file as large-object data.</span></span>  
  
 <span data-ttu-id="494aa-104">Les types de données LOB pris en charge par le fournisseur d’ensembles de lignes OPENROWSET sont **varbinary**(max) ou **image**, **varchar**(max) ou **text**et **nvarchar**(max) ou **ntext**.</span><span class="sxs-lookup"><span data-stu-id="494aa-104">The large-object data types supported by OPENROWSET Bulk Rowset Provider are **varbinary**(max) or **image**, **varchar**(max) or **text**, and **nvarchar**(max) or **ntext**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="494aa-105">Les types de données **image**, **text** et **ntext** sont déconseillés.</span><span class="sxs-lookup"><span data-stu-id="494aa-105">The **image**, **text** and **ntext** data types are deprecated.</span></span>  
  
 <span data-ttu-id="494aa-106">La clause OPENROWSET BULK prend en charge trois options pour importer le contenu d'un fichier de données sous forme d'un ensemble d'une seule ligne et d'une seule colonne.</span><span class="sxs-lookup"><span data-stu-id="494aa-106">The OPENROWSET BULK clause supports three options for importing the contents of a data file as a single-row, single-column rowset.</span></span> <span data-ttu-id="494aa-107">Vous pouvez spécifier une de ces options au lieu d'utiliser un fichier de format.</span><span class="sxs-lookup"><span data-stu-id="494aa-107">You can specify one of these large-object options instead of using a format file.</span></span> <span data-ttu-id="494aa-108">Ces options sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="494aa-108">These options are as follows:</span></span>  
  
 <span data-ttu-id="494aa-109">SINGLE_BLOB</span><span class="sxs-lookup"><span data-stu-id="494aa-109">SINGLE_BLOB</span></span>  
 <span data-ttu-id="494aa-110">Lit le contenu de *data_file* comme une seule ligne, retourne le contenu comme un ensemble de lignes à une seule colonne de type **varbinary(max)** .</span><span class="sxs-lookup"><span data-stu-id="494aa-110">Reads the contents of *data_file* as a single-row, returns the contents as a single-column rowset of type **varbinary(max)**.</span></span>  
  
 <span data-ttu-id="494aa-111">SINGLE_CLOB</span><span class="sxs-lookup"><span data-stu-id="494aa-111">SINGLE_CLOB</span></span>  
 <span data-ttu-id="494aa-112">Lit le contenu du fichier de données spécifié comme des caractères, retourne le contenu sous la forme d’un ensemble de lignes à une seule ligne et une seule colonne de type **varchar(max)** en utilisant le classement de la base de données actuelle (texte ou document [!INCLUDE[msCoName](../../includes/msconame-md.md)] Word).</span><span class="sxs-lookup"><span data-stu-id="494aa-112">Reads the contents of the specified data file as characters, returns the contents as a single-row, single-column rowset of type **varchar(max)**, using the collation of the current database; such as a text or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Word document.</span></span>  
  
 <span data-ttu-id="494aa-113">SINGLE_NCLOB</span><span class="sxs-lookup"><span data-stu-id="494aa-113">SINGLE_NCLOB</span></span>  
 <span data-ttu-id="494aa-114">Lit le contenu du fichier de données spécifié comme de l’unicode, retourne le contenu sous la forme d’un ensemble de lignes à une seule ligne et une seule colonne de type **nvarchar(max)** en utilisant le classement de la base de données active.</span><span class="sxs-lookup"><span data-stu-id="494aa-114">Reads the contents of the specified data file as Unicode, returns the contents as a single-row, single-column rowset of type **nvarchar(max)**, using the collation of the current database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="494aa-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="494aa-115">See Also</span></span>  
 <span data-ttu-id="494aa-116">[Importer des données en bloc à l’aide de BULK INSERT ou OPENROWSET&#40;BULK...&#41; &#40;SQL Server&#41;](import-bulk-data-by-using-bulk-insert-or-openrowset-bulk-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="494aa-116">[Import Bulk Data by Using BULK INSERT or OPENROWSET&#40;BULK...&#41; &#40;SQL Server&#41;](import-bulk-data-by-using-bulk-insert-or-openrowset-bulk-sql-server.md) </span></span>  
 <span data-ttu-id="494aa-117">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="494aa-117">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="494aa-118">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="494aa-118">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="494aa-119">[Conserver les valeurs NULL ou utiliser la valeur par défaut lors de l’importation en bloc &#40;SQL Server&#41;](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="494aa-119">[Keep Nulls or Use Default Values During Bulk Import &#40;SQL Server&#41;](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md) </span></span>  
 <span data-ttu-id="494aa-120">[Utilitaire bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="494aa-120">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 [<span data-ttu-id="494aa-121">BULK INSERT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="494aa-121">BULK INSERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/bulk-insert-transact-sql)  
  
  
