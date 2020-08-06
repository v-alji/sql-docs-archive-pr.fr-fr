---
title: Créer une base de données compatible FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], FILESTREAM-enabled databases
ms.assetid: 0fc16356-76f7-44b8-a58b-f0b7c43694ec
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0fe6e5bc6e4f60bc0703482f3bf4d761104b3c5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701237"
---
# <a name="create-a-filestream-enabled-database"></a><span data-ttu-id="54484-102">Créer une base de données compatible FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="54484-102">Create a FILESTREAM-Enabled Database</span></span>
  <span data-ttu-id="54484-103">Cette rubrique montre comment créer une base de données qui prend en charge FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="54484-103">This topic shows how to create a database that supports FILESTREAM.</span></span> <span data-ttu-id="54484-104">Étant donné que FILESTREAM utilise un type de groupe de fichiers spécial, lors de la création de la base de données vous devez spécifier la clause CONTAINS FILESTREAM pour au moins un groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="54484-104">Because FILESTREAM uses a special type of filegroup, when you create the database, you must specify the CONTAINS FILESTREAM clause for at least one filegroup.</span></span>  
  
 <span data-ttu-id="54484-105">Un groupe de fichiers FILESTREAM peut contenir plusieurs fichiers.</span><span class="sxs-lookup"><span data-stu-id="54484-105">A FILESTREAM filegroup can contain more than one file.</span></span> <span data-ttu-id="54484-106">Pour obtenir un exemple de code qui illustre la création d’un groupe de fichiers FILESTREAM contenant plusieurs fichiers, consultez [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="54484-106">For a code example that demonstrates how to create a FILESTREAM filegroup that contains multiple files, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
### <a name="to-create-a-filestream-enabled-database"></a><span data-ttu-id="54484-107">Pour créer une base de données compatible FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="54484-107">To create a FILESTREAM-enabled database</span></span>  
  
1.  <span data-ttu-id="54484-108">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], cliquez sur **Nouvelle requête** pour afficher l'Éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="54484-108">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click **New Query** to display the Query Editor.</span></span>  
  
2.  <span data-ttu-id="54484-109">Copier le [!INCLUDE[tsql](../../includes/tsql-md.md)] code crée une base de données compatible FILESTREAM nommée archive.</span><span class="sxs-lookup"><span data-stu-id="54484-109">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] code creates a FILESTREAM-enabled database called Archive.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="54484-110">Pour ce script, le répertoire C:\Data doit exister.</span><span class="sxs-lookup"><span data-stu-id="54484-110">For this script, the directory C:\Data must exist.</span></span>  
  
3.  <span data-ttu-id="54484-111">Pour générer la base de données, cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="54484-111">To build the database, click **Execute**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54484-112">Exemple</span><span class="sxs-lookup"><span data-stu-id="54484-112">Example</span></span>  
 <span data-ttu-id="54484-113">L'exemple de code suivant crée une base de données nommée `Archive`.</span><span class="sxs-lookup"><span data-stu-id="54484-113">The following code example creates a database that is named `Archive`.</span></span> <span data-ttu-id="54484-114">La base de données contient trois groupes de fichiers : `PRIMARY`, `Arch1`et `FileStreamGroup1`.</span><span class="sxs-lookup"><span data-stu-id="54484-114">The database contains three filegroups: `PRIMARY`, `Arch1`, and `FileStreamGroup1`.</span></span> <span data-ttu-id="54484-115">`PRIMARY` et `Arch1` sont des groupes de fichiers ordinaires qui ne peuvent pas contenir de données FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="54484-115">`PRIMARY` and `Arch1` are regular filegroups that cannot contain FILESTREAM data.</span></span> <span data-ttu-id="54484-116">`FileStreamGroup1` est le groupe de fichiers `FILESTREAM` .</span><span class="sxs-lookup"><span data-stu-id="54484-116">`FileStreamGroup1` is the `FILESTREAM` filegroup.</span></span>  
  
```sql  
CREATE DATABASE Archive   
ON  
PRIMARY ( NAME = Arch1,  
    FILENAME = 'c:\data\archdat1.mdf'),  
FILEGROUP FileStreamGroup1 CONTAINS FILESTREAM( NAME = Arch3,  
    FILENAME = 'c:\data\filestream1')  
LOG ON  ( NAME = Archlog1,  
    FILENAME = 'c:\data\archlog1.ldf')  
GO  
```  
  
 <span data-ttu-id="54484-117">Pour un groupe de fichiers `FILESTREAM` , `FILENAME` fait référence à un chemin d'accès.</span><span class="sxs-lookup"><span data-stu-id="54484-117">For a `FILESTREAM` filegroup, `FILENAME` refers to a path.</span></span> <span data-ttu-id="54484-118">Le chemin d'accès jusqu'au dernier dossier doit exister, et le dernier dossier ne doit pas exister.</span><span class="sxs-lookup"><span data-stu-id="54484-118">The path up to the last folder must exist, and the last folder must not exist.</span></span> <span data-ttu-id="54484-119">Dans cet exemple, `c:\data` doit exister.</span><span class="sxs-lookup"><span data-stu-id="54484-119">In this example, `c:\data` must exist.</span></span> <span data-ttu-id="54484-120">Toutefois, le sous-dossier `filestream1` ne peut pas exister lorsque vous exécutez l'instruction `CREATE DATABASE` .</span><span class="sxs-lookup"><span data-stu-id="54484-120">However, the `filestream1` subfolder cannot exist when you execute the `CREATE DATABASE` statement.</span></span> <span data-ttu-id="54484-121">Pour plus d’informations sur la syntaxe, consultez [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="54484-121">For more information about the syntax, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
 <span data-ttu-id="54484-122">Après l'exécution de l'exemple précédent, un fichier filestream.hdr et un dossier $FSLOG apparaissent dans le dossier c:\Data\filestream1.</span><span class="sxs-lookup"><span data-stu-id="54484-122">After you run the previous example, a filestream.hdr file and an $FSLOG folder appears in the c:\Data\filestream1 folder.</span></span> <span data-ttu-id="54484-123">Le fichier filestream.hdr est un fichier d'en-tête pour le conteneur FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="54484-123">The filestream.hdr file is a header file for the FILESTREAM container.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="54484-124">Le fichier filestream.hdr est un fichier système important.</span><span class="sxs-lookup"><span data-stu-id="54484-124">The filestream.hdr file is an important system file.</span></span> <span data-ttu-id="54484-125">Il contient des informations d'en-tête FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="54484-125">It contains FILESTREAM header information.</span></span> <span data-ttu-id="54484-126">Vous ne devez ni le supprimer, ni le modifier.</span><span class="sxs-lookup"><span data-stu-id="54484-126">Do not remove or modify this file.</span></span>  
  
 <span data-ttu-id="54484-127">Pour les bases de données existantes, vous pouvez utiliser l'instruction [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) pour ajouter un groupe de fichiers FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="54484-127">For existing databases, you can use the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement to add a FILESTREAM filegroup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54484-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="54484-128">See Also</span></span>  
 <span data-ttu-id="54484-129">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="54484-129">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="54484-130">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="54484-130">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
