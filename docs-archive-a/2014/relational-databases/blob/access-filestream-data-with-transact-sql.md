---
title: Accéder aux données FILESTREAM avec Transact-SQL | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], Transact-SQL
ms.assetid: a6bf0ce7-7e5e-4a07-8917-ee526c9d0a05
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 06d395f1acc3723fc6b45fdfa08efbae354d8014
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703000"
---
# <a name="access-filestream-data-with-transact-sql"></a><span data-ttu-id="70e9c-102">Accéder aux données FILESTREAM avec Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="70e9c-102">Access FILESTREAM Data with Transact-SQL</span></span>
  <span data-ttu-id="70e9c-103">Cette rubrique explique comment utiliser les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT, UPDATE et DELETE pour gérer des données FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="70e9c-103">This topic describes how to use the [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT, UPDATE, and DELETE statements to manage FILESTREAM data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="70e9c-104">Les exemples de cette rubrique nécessitent la base de données compatible FILESTREAM et la table qui sont créées dans [Créer une base de données compatible FILESTREAM](create-a-filestream-enabled-database.md) et [Créer une table pour le stockage de données FILESTREAM](create-a-table-for-storing-filestream-data.md).</span><span class="sxs-lookup"><span data-stu-id="70e9c-104">The examples in this topic require the FILESTREAM-enabled database and table that are created in [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md) and [Create a Table for Storing FILESTREAM Data](create-a-table-for-storing-filestream-data.md).</span></span>  
  
##  <a name="inserting-a-row-that-contains-filestream-data"></a><a name="ins"></a> <span data-ttu-id="70e9c-105">Insertion d'une ligne qui contient des données FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="70e9c-105">Inserting a Row That Contains FILESTREAM Data</span></span>  
 <span data-ttu-id="70e9c-106">Pour ajouter une ligne à une table prenant en charge les données FILESTREAM, utilisez l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT.</span><span class="sxs-lookup"><span data-stu-id="70e9c-106">To add a row to a table that supports FILESTREAM data, use the [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT statement.</span></span> <span data-ttu-id="70e9c-107">Lorsque vous insérez des données dans une colonne FILESTREAM, vous pouvez insérer une valeur NULL ou `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="70e9c-107">When you insert data into a FILESTREAM column, you can insert NULL or a `varbinary(max)` value.</span></span>  
  
### <a name="inserting-null"></a><span data-ttu-id="70e9c-108">Insertion de NULL</span><span class="sxs-lookup"><span data-stu-id="70e9c-108">Inserting NULL</span></span>  
 <span data-ttu-id="70e9c-109">L'exemple suivant montre comment insérer `NULL`.</span><span class="sxs-lookup"><span data-stu-id="70e9c-109">The following example shows how to insert `NULL`.</span></span> <span data-ttu-id="70e9c-110">Lorsque la valeur FILESTREAM est `NULL`, le [!INCLUDE[ssDE](../../includes/ssde-md.md)] ne crée pas de fichier dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="70e9c-110">When the FILESTREAM value is `NULL`, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] does not create a file in the file system.</span></span>  
  
 [!code-sql[FILESTREAM#FS_InsertNULL](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_insertnull)]  
  
### <a name="inserting-a-zero-length-record"></a><span data-ttu-id="70e9c-111">Insertion d'un enregistrement de longueur nulle</span><span class="sxs-lookup"><span data-stu-id="70e9c-111">Inserting a Zero-Length Record</span></span>  
 <span data-ttu-id="70e9c-112">L'exemple suivant illustre l'utilisation de `INSERT` pour créer un enregistrement de longueur nulle.</span><span class="sxs-lookup"><span data-stu-id="70e9c-112">The following example shows how to use `INSERT` to create a zero-length record.</span></span> <span data-ttu-id="70e9c-113">C'est utile lorsque vous souhaitez obtenir un descripteur de fichier, mais que vous manipulerez le fichier en utilisant des API Win32.</span><span class="sxs-lookup"><span data-stu-id="70e9c-113">This is useful for when you want to obtain a file handle, but will be manipulating the file by using Win32 APIs.</span></span>  
  
 [!code-sql[FILESTREAM#FS_InsertZero](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_insertzero)]  
  
### <a name="creating-a-data-file"></a><span data-ttu-id="70e9c-114">Création d'un fichier de données</span><span class="sxs-lookup"><span data-stu-id="70e9c-114">Creating a Data File</span></span>  
 <span data-ttu-id="70e9c-115">L'exemple suivant illustre l'utilisation de `INSERT` pour créer un fichier contenant des données.</span><span class="sxs-lookup"><span data-stu-id="70e9c-115">The following example shows how to use `INSERT` to create a file that contains data.</span></span> <span data-ttu-id="70e9c-116">Le [!INCLUDE[ssDE](../../includes/ssde-md.md)] convertit la chaîne `Seismic Data` en valeur `varbinary(max)` .</span><span class="sxs-lookup"><span data-stu-id="70e9c-116">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] converts the string `Seismic Data` to a `varbinary(max)` value.</span></span> <span data-ttu-id="70e9c-117">FILESTREAM crée le fichier Windows s'il n'existe pas déjà. Les données sont ensuite ajoutées au fichier de données.</span><span class="sxs-lookup"><span data-stu-id="70e9c-117">FILESTREAM creates the Windows file if it does not already exist.The data is then added to the data file.</span></span>  
  
 [!code-sql[FILESTREAM#FS_InsertData](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_insertdata)]  
  
 <span data-ttu-id="70e9c-118">Quand vous sélectionnez toutes les données de la table `Archive`,`dbo.Records`</span><span class="sxs-lookup"><span data-stu-id="70e9c-118">When you select all data from the `Archive`.`dbo.Records`</span></span> <span data-ttu-id="70e9c-119">les résultats sont semblables à ceux affichés dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="70e9c-119">table, the results are similar to the results that are shown in the following table.</span></span> <span data-ttu-id="70e9c-120">Toutefois, la colonne `Id` contiendra des GUID différents.</span><span class="sxs-lookup"><span data-stu-id="70e9c-120">However, the `Id` column will contain different GUIDs.</span></span>  
  
|<span data-ttu-id="70e9c-121">Id</span><span class="sxs-lookup"><span data-stu-id="70e9c-121">Id</span></span>|<span data-ttu-id="70e9c-122">SerialNumber</span><span class="sxs-lookup"><span data-stu-id="70e9c-122">SerialNumber</span></span>|<span data-ttu-id="70e9c-123">Reprendre</span><span class="sxs-lookup"><span data-stu-id="70e9c-123">Resume</span></span>|  
|--------|------------------|------------|  
|`C871B90F-D25E-47B3-A560-7CC0CA405DAC`|`1`|`NULL`|  
|`F8F5C314-0559-4927-8FA9-1535EE0BDF50`|`2`|`0x`|  
|`7F680840-B7A4-45D4-8CD5-527C44D35B3F`|`3`|`0x536569736D69632044617461`|  
  
##  <a name="updating-filestream-data"></a><a name="upd"></a> <span data-ttu-id="70e9c-124">Mise à jour de données FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="70e9c-124">Updating FILESTREAM Data</span></span>  
 <span data-ttu-id="70e9c-125">Vous pouvez utiliser [!INCLUDE[tsql](../../includes/tsql-md.md)] pour mettre à jour les données dans le fichier de système de fichiers, bien que cela soit plutôt déconseillé quand vous devez transmettre en continu de gros volumes de données à un fichier.</span><span class="sxs-lookup"><span data-stu-id="70e9c-125">You can use [!INCLUDE[tsql](../../includes/tsql-md.md)] to update the data in the file system file; although, you might not want to do this when you have to stream large amounts of data to a file.</span></span>  
  
 <span data-ttu-id="70e9c-126">L'exemple suivant remplace tout texte dans l'enregistrement de fichier par le texte `Xray 1`.</span><span class="sxs-lookup"><span data-stu-id="70e9c-126">The following example replaces any text in the file record with the text `Xray 1`.</span></span>  
  
 [!code-sql[FILESTREAM#FS_UpdateData](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_updatedata)]  
  
##  <a name="deleting-filestream-data"></a><a name="del"></a> <span data-ttu-id="70e9c-127">Suppression de données FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="70e9c-127">Deleting FILESTREAM Data</span></span>  
 <span data-ttu-id="70e9c-128">Lorsque vous supprimez une ligne qui contient un champ FILESTREAM, vous supprimez également ses fichiers de système de fichiers sous-jacents.</span><span class="sxs-lookup"><span data-stu-id="70e9c-128">When you delete a row that contains a FILESTREAM field, you also delete its underlying file system files.</span></span> <span data-ttu-id="70e9c-129">La seule façon de supprimer une ligne, et par conséquent le fichier, consiste à utiliser l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] DELETE.</span><span class="sxs-lookup"><span data-stu-id="70e9c-129">The only way to delete a row, and therefore the file, is to use the [!INCLUDE[tsql](../../includes/tsql-md.md)] DELETE statement.</span></span>  
  
 <span data-ttu-id="70e9c-130">L'exemple suivant montre comment supprimer une ligne et les fichiers de système de fichiers qui lui sont associés.</span><span class="sxs-lookup"><span data-stu-id="70e9c-130">The following example shows how to delete a row and its associated file system files.</span></span>  
  
 [!code-sql[FILESTREAM#FS_DeleteData](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_deletedata)]  
  
 <span data-ttu-id="70e9c-131">Lorsque vous sélectionnez toutes les données de la table `dbo.Archive` , la ligne disparaît.</span><span class="sxs-lookup"><span data-stu-id="70e9c-131">When you select all data from the `dbo.Archive` table, the row is gone.</span></span> <span data-ttu-id="70e9c-132">Vous ne pouvez plus utiliser le fichier associé.</span><span class="sxs-lookup"><span data-stu-id="70e9c-132">You can no longer use the associated file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="70e9c-133">Les fichiers sous-jacents sont supprimés par le garbage collector FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="70e9c-133">The underlying files are removed by the FILESTREAM garbage collector.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70e9c-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="70e9c-134">See Also</span></span>  
 <span data-ttu-id="70e9c-135">[Activer et configurer FILESTREAM](enable-and-configure-filestream.md) </span><span class="sxs-lookup"><span data-stu-id="70e9c-135">[Enable and Configure FILESTREAM](enable-and-configure-filestream.md) </span></span>  
 [<span data-ttu-id="70e9c-136">Éviter les conflits avec les opérations de base de données dans les applications FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="70e9c-136">Avoid Conflicts with Database Operations in FILESTREAM Applications</span></span>](avoid-conflicts-with-database-operations-in-filestream-applications.md)  
  
  
