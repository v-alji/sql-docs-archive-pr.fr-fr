---
title: Créer une table pour le stockage de données FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], table storage
ms.assetid: 029c3059-5c83-43e2-a859-9027031b7de1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 484d7b58ce949df79dc7e17ee4dc7307b70c0154
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699780"
---
# <a name="create-a-table-for-storing-filestream-data"></a><span data-ttu-id="fefb0-102">Créer une table pour le stockage de données FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="fefb0-102">Create a Table for Storing FILESTREAM Data</span></span>
  <span data-ttu-id="fefb0-103">Cette rubrique indique comment créer une table pour stocker des données FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="fefb0-103">This topic shows how to create a table for storing FILESTREAM data.</span></span>  
  
 <span data-ttu-id="fefb0-104">Lorsque la base de données comporte un groupe de fichiers FILESTREAM, vous pouvez créer ou modifier des tables pour stocker des données FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="fefb0-104">When the database has a FILESTREAM filegroup, you can create or modify tables to store FILESTREAM data.</span></span> <span data-ttu-id="fefb0-105">Pour spécifier qu'une colonne contient des données FILESTREAM, créez une colonne `varbinary(max)` et ajoutez l'attribut FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="fefb0-105">To specify that a column contains FILESTREAM data, you create a `varbinary(max)` column and add the FILESTREAM attribute.</span></span>  
  
### <a name="to-create-a-table-to-store-filestream-data"></a><span data-ttu-id="fefb0-106">Pour créer une table pour stocker des données FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="fefb0-106">To create a table to store FILESTREAM data</span></span>  
  
1.  <span data-ttu-id="fefb0-107">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], cliquez sur **Nouvelle requête** pour afficher l'Éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="fefb0-107">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click **New Query** to display the Query Editor.</span></span>  
  
2.  <span data-ttu-id="fefb0-108">Copiez le code [!INCLUDE[tsql](../../includes/tsql-md.md)] de l'exemple suivant dans l'éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="fefb0-108">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] code from the following example into the Query Editor.</span></span> <span data-ttu-id="fefb0-109">Ce code [!INCLUDE[tsql](../../includes/tsql-md.md)] crée une table compatible FILESTREAM appelée Enregistrements.</span><span class="sxs-lookup"><span data-stu-id="fefb0-109">This [!INCLUDE[tsql](../../includes/tsql-md.md)] code creates a FILESTREAM-enabled table called Records.</span></span>  
  
3.  <span data-ttu-id="fefb0-110">Pour créer la table, cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="fefb0-110">To create the table, click **Execute**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fefb0-111">Exemple</span><span class="sxs-lookup"><span data-stu-id="fefb0-111">Example</span></span>  
 <span data-ttu-id="fefb0-112">L'exemple de code suivant montre comment créer une table nommée `Records`.</span><span class="sxs-lookup"><span data-stu-id="fefb0-112">The following code example shows how to create a table that is named `Records`.</span></span> <span data-ttu-id="fefb0-113">La colonne `Id` est une colonne `ROWGUIDCOL` requise pour utiliser des données FILESTREAM avec les API Win32.</span><span class="sxs-lookup"><span data-stu-id="fefb0-113">The `Id` column is a `ROWGUIDCOL` column and is required to use FILESTREAM data with Win32 APIs.</span></span> <span data-ttu-id="fefb0-114">La colonne `SerialNumber` est une colonne `UNIQUE INTEGER`.</span><span class="sxs-lookup"><span data-stu-id="fefb0-114">The `SerialNumber` column is a `UNIQUE INTEGER`.</span></span> <span data-ttu-id="fefb0-115">La colonne `Chart` est une colonne `FILESTREAM` qui sert à stocker `Chart` dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="fefb0-115">The `Chart` column is a `FILESTREAM` column and is used to store the `Chart` in the file system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fefb0-116">Cette rubrique fait référence à la base de données Archive créée dans [Créer une base de données compatible FILESTREAM](create-a-filestream-enabled-database.md).</span><span class="sxs-lookup"><span data-stu-id="fefb0-116">This example refers to the Archive database that is created in [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md).</span></span>  
  
 [!code-sql[FILESTREAM#FS_CreateTable](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_createtable)]  
  
## <a name="see-also"></a><span data-ttu-id="fefb0-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fefb0-117">See Also</span></span>  
 <span data-ttu-id="fefb0-118">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fefb0-118">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span></span>  
 [<span data-ttu-id="fefb0-119">ALTER TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fefb0-119">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
  
