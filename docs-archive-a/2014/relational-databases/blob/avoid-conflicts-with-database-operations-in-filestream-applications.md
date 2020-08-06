---
title: Éviter les conflits avec les opérations de base de données dans les applications FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], Win32 and Transact-SQL Conflicts
ms.assetid: 8b1ee196-69af-4f9b-9bf5-63d8ac2bc39b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0ac7e681766396d3a3b4412d91a968b4cdc653c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612984"
---
# <a name="avoid-conflicts-with-database-operations-in-filestream-applications"></a><span data-ttu-id="d8e2f-102">Éviter les conflits avec les opérations de base de données dans les applications FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="d8e2f-102">Avoid Conflicts with Database Operations in FILESTREAM Applications</span></span>
  <span data-ttu-id="d8e2f-103">Les applications qui utilisent SqlOpenFilestream() pour ouvrir des descripteurs de fichiers Win32 afin de lire ou d’écrire des données BLOB FILESTREAM peuvent rencontrer des erreurs de conflit avec les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] gérées dans une transaction commune.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-103">Applications that use SqlOpenFilestream() to open Win32 file handles for reading or writing FILESTREAM BLOB data can encounter conflict errors with [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that are managed in a common transaction.</span></span> <span data-ttu-id="d8e2f-104">Cela inclut [!INCLUDE[tsql](../../includes/tsql-md.md)] ou les requêtes MARS dont l'exécution dure longtemps.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-104">This includes [!INCLUDE[tsql](../../includes/tsql-md.md)] or MARS queries that take a long time to finish execution.</span></span> <span data-ttu-id="d8e2f-105">Les applications doivent être conçues avec soin afin de mieux éviter ces types de conflits.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-105">Applications must be carefully designed to help avoid these types of conflicts.</span></span>  
  
 <span data-ttu-id="d8e2f-106">Lorsque [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] ou des applications essaient d’ouvrir des FILESTREAM BLOB, le [!INCLUDE[ssDE](../../includes/ssde-md.md)] vérifie le contexte de transaction associé.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-106">When [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] or applications try to open FILESTREAM BLOBs, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] checks the associated transaction context.</span></span> <span data-ttu-id="d8e2f-107">[!INCLUDE[ssDE](../../includes/ssde-md.md)] autorise ou refuse la demande selon que l’opération en cours fonctionne avec des instructions DDL, des instructions DML, la récupération de données ou la gestion de transactions.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-107">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] allows or denies the request based on whether the open operation is working with DDL statements, DML statements, retrieving data, or managing transactions.</span></span> <span data-ttu-id="d8e2f-108">Le tableau suivant indique comment le [!INCLUDE[ssDE](../../includes/ssde-md.md)] détermine si une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] sera autorisée ou refusée selon les types de fichiers qui sont ouverts pendant la transaction.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-108">The following table shows how the [!INCLUDE[ssDE](../../includes/ssde-md.md)] determines whether a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement will be allowed or denied based on the type of files that are open in the transaction.</span></span>  
  
|<span data-ttu-id="d8e2f-109">instructions Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d8e2f-109">Transact-SQL statements</span></span>|<span data-ttu-id="d8e2f-110">Ouvert pour la lecture</span><span class="sxs-lookup"><span data-stu-id="d8e2f-110">Opened for read</span></span>|<span data-ttu-id="d8e2f-111">Ouvert pour l'écriture</span><span class="sxs-lookup"><span data-stu-id="d8e2f-111">Opened for write</span></span>|  
|------------------------------|---------------------|----------------------|  
|<span data-ttu-id="d8e2f-112">Instructions DDL qui fonctionnent avec des métadonnées de base de données, telles que CREATE TABLE, CREATE INDEX, DROP TABLE et ALTER TABLE.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-112">DDL statements that work with database metadata, such as CREATE TABLE, CREATE INDEX, DROP TABLE, and ALTER TABLE.</span></span>|<span data-ttu-id="d8e2f-113">Autorisé</span><span class="sxs-lookup"><span data-stu-id="d8e2f-113">Allowed</span></span>|<span data-ttu-id="d8e2f-114">Sont bloquées et échouent à la suite d'un délai d'expiration.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-114">Are blocked and fail with a time-out.</span></span>|  
|<span data-ttu-id="d8e2f-115">Instructions DML qui fonctionnent avec les données qui sont stockées dans la base de données, telles qu'UPDATE, DELETE et INSERT.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-115">DML statements that work with the data that is stored in the database, such as UPDATE, DELETE, and INSERT.</span></span>|<span data-ttu-id="d8e2f-116">Autorisé</span><span class="sxs-lookup"><span data-stu-id="d8e2f-116">Allowed</span></span>|<span data-ttu-id="d8e2f-117">Refusée</span><span class="sxs-lookup"><span data-stu-id="d8e2f-117">Denied</span></span>|  
|<span data-ttu-id="d8e2f-118">SELECT</span><span class="sxs-lookup"><span data-stu-id="d8e2f-118">SELECT</span></span>|<span data-ttu-id="d8e2f-119">Autorisé</span><span class="sxs-lookup"><span data-stu-id="d8e2f-119">Allowed</span></span>|<span data-ttu-id="d8e2f-120">Autorisé</span><span class="sxs-lookup"><span data-stu-id="d8e2f-120">Allowed</span></span>|  
|<span data-ttu-id="d8e2f-121">COMMIT TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="d8e2f-121">COMMIT TRANSACTION</span></span>|<span data-ttu-id="d8e2f-122">Refusées\*</span><span class="sxs-lookup"><span data-stu-id="d8e2f-122">Denied\*</span></span>|<span data-ttu-id="d8e2f-123">Refusées\*</span><span class="sxs-lookup"><span data-stu-id="d8e2f-123">Denied\*.</span></span>|  
|<span data-ttu-id="d8e2f-124">SAVE TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="d8e2f-124">SAVE TRANSACTION</span></span>|<span data-ttu-id="d8e2f-125">Refusées\*</span><span class="sxs-lookup"><span data-stu-id="d8e2f-125">Denied\*</span></span>|<span data-ttu-id="d8e2f-126">Refusées\*</span><span class="sxs-lookup"><span data-stu-id="d8e2f-126">Denied\*</span></span>|  
|<span data-ttu-id="d8e2f-127">ROLLBACK</span><span class="sxs-lookup"><span data-stu-id="d8e2f-127">ROLLBACK</span></span>|<span data-ttu-id="d8e2f-128">Autorisées\*</span><span class="sxs-lookup"><span data-stu-id="d8e2f-128">Allowed\*</span></span>|<span data-ttu-id="d8e2f-129">Autorisées\*</span><span class="sxs-lookup"><span data-stu-id="d8e2f-129">Allowed\*</span></span>|  
  
 <span data-ttu-id="d8e2f-130">\* La transaction est annulée, et les descripteurs ouverts pour le contexte de transaction sont invalidés.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-130">\* The transaction is canceled, and open handles for the transaction context are invalidated.</span></span> <span data-ttu-id="d8e2f-131">L'application doit fermer tous les descripteurs ouverts.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-131">The application must close all open handles.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d8e2f-132">Exemples</span><span class="sxs-lookup"><span data-stu-id="d8e2f-132">Examples</span></span>  
 <span data-ttu-id="d8e2f-133">Les exemples suivants illustrent comment les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] et l’accès FILESTREAM Win32 peut provoquer des conflits.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-133">The following examples show how [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and FILESTREAM Win32 access can cause conflicts.</span></span>  
  
### <a name="a-opening-a-filestream-blob-for-write-access"></a><span data-ttu-id="d8e2f-134">R.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-134">A.</span></span> <span data-ttu-id="d8e2f-135">Ouverture d'un BLOB FILESTREAM pour un accès en écriture</span><span class="sxs-lookup"><span data-stu-id="d8e2f-135">Opening a FILESTREAM BLOB for write access</span></span>  
 <span data-ttu-id="d8e2f-136">L'exemple suivant montre l'effet d'ouverture d'un fichier pour un accès uniquement en écriture.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-136">The following example shows the effect of opening a file for write access only.</span></span>  
  
```  
dstHandle =  OpenSqlFilestream(dstFilePath, Write, 0,  
    transactionToken, cbTransactionToken, 0);  
  
//Write some date to the FILESTREAM BLOB.  
WriteFile(dstHandle, updateData, ...);  
  
//DDL statements will be denied.  
//DML statements will be denied.  
//SELECT statements will be allowed. The FILESTREAM BLOB is  
//returned without the modifications that are made by  
//WriteFile(dstHandle, updateData, ...).  
CloseHandle(dstHandle);  
  
//DDL statements will be allowed.  
//DML statements will be allowed.  
//SELECT statements will be allowed. The FILESTREAM BLOB  
//is returned with the updateData applied.  
```  
  
### <a name="b-opening-a-filestream-blob-for-read-access"></a><span data-ttu-id="d8e2f-137">B.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-137">B.</span></span> <span data-ttu-id="d8e2f-138">Ouverture d'un BLOB FILESTREAM pour un accès en lecture</span><span class="sxs-lookup"><span data-stu-id="d8e2f-138">Opening a FILESTREAM BLOB for read access</span></span>  
 <span data-ttu-id="d8e2f-139">L'exemple suivant montre l'effet d'ouverture d'un fichier pour un accès uniquement en lecture.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-139">The following example shows the effect of opening a file for read access only.</span></span>  
  
```  
dstHandle =  OpenSqlFilestream(dstFilePath, Read, 0,  
    transactionToken, cbTransactionToken, 0);  
//DDL statements will be denied.  
//DML statements will be allowed. Any changes that are  
//made to the FILESTREAM BLOB will not be returned until  
//the dstHandle is closed.  
//SELECT statements will be allowed.  
CloseHandle(dstHandle);  
  
//DDL statements will be allowed.  
//DML statements will be allowed.  
//SELECT statements will be allowed.  
```  
  
### <a name="c-opening-and-closing-multiple-filestream-blob-files"></a><span data-ttu-id="d8e2f-140">C.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-140">C.</span></span> <span data-ttu-id="d8e2f-141">Ouverture et fermeture de plusieurs fichiers BLOB FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="d8e2f-141">Opening and closing multiple FILESTREAM BLOB files</span></span>  
 <span data-ttu-id="d8e2f-142">Si plusieurs fichiers sont ouverts, c'est la règle la plus restrictive qui est utilisée.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-142">If multiple files are open, the most restrictive rule is used.</span></span> <span data-ttu-id="d8e2f-143">L'exemple suivant ouvre deux fichiers.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-143">The following example opens two files.</span></span> <span data-ttu-id="d8e2f-144">Le premier fichier est ouvert pour la lecture et le second pour l'écriture.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-144">The first file is opened for read and the second for write.</span></span> <span data-ttu-id="d8e2f-145">Les instructions DML seront refusées jusqu'à ce que le deuxième fichier soit ouvert.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-145">DML statements will be denied until the second file is opened.</span></span>  
  
```  
dstHandle =  OpenSqlFilestream(dstFilePath, Read, 0,  
    transactionToken, cbTransactionToken, 0);  
//DDL statements will be denied.  
//DML statements will be allowed.  
//SELECT statements will be allowed.  
  
dstHandle1 =  OpenSqlFilestream(dstFilePath1, Write, 0,  
    transactionToken, cbTransactionToken, 0);  
  
//DDL statements will be denied.  
//DML statements will be denied.  
//SELECT statements will be allowed.  
  
//Close the read handle. The write handle is still open.  
CloseHandle(dstHandle);  
//DML statements are still denied because the write handle is open.  
  
//DDL statements will be denied.  
//DML statements will be denied.  
//SELECT statements will be allowed.  
  
CloseHandle(dstHandle1);  
//DDL statements will be allowed.  
//DML statements will be allowed.  
//SELECT statements will be allowed.  
```  
  
### <a name="d-failing-to-close-a-cursor"></a><span data-ttu-id="d8e2f-146">D.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-146">D.</span></span> <span data-ttu-id="d8e2f-147">Échec de fermeture d'un curseur</span><span class="sxs-lookup"><span data-stu-id="d8e2f-147">Failing to close a cursor</span></span>  
 <span data-ttu-id="d8e2f-148">L'exemple suivant montre comment un curseur d'instruction qui n'est pas fermé peut empêcher `OpenSqlFilestream()` d'ouvrir le BLOB pour l'accès en écriture.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-148">The following example shows how a statement cursor that is not closed can prevent `OpenSqlFilestream()` from opening the BLOB for write access.</span></span>  
  
```  
TCHAR *sqlDBQuery =  
TEXT("SELECT GET_FILESTREAM_TRANSACTION_CONTEXT(),")  
TEXT("Chart.PathName() FROM Archive.dbo.Records");  
  
//Execute a long-running Transact-SQL statement. Do not allow  
//the statement to complete before trying to  
//open the file.  
  
SQLExecDirect(hstmt, sqlDBQuery, SQL_NTS);  
  
//Before you call OpenSqlFilestream() any open files  
//that the Cursor the Transact-SQL statement is using  
// must be closed. In this example,  
//SQLCloseCursor(hstmt) is not called so that  
//the transaction will indicate that there is a file  
//open for reading. This will cause the call to  
//OpenSqlFilestream() to fail because the file is  
//still open.  
  
HANDLE srcHandle =  OpenSqlFilestream(srcFilePath,  
     Write, 0,  transactionToken,  cbTransactionToken,  0);  
  
//srcHandle will == INVALID_HANDLE_VALUE because the  
//cursor is still open.  
```  
  
## <a name="see-also"></a><span data-ttu-id="d8e2f-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d8e2f-149">See Also</span></span>  
 <span data-ttu-id="d8e2f-150">[Accéder à des données FILESTREAM avec OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) </span><span class="sxs-lookup"><span data-stu-id="d8e2f-150">[Access FILESTREAM Data with OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) </span></span>  
 [<span data-ttu-id="d8e2f-151">Utilisation de MARS &#40;Multiple Active Result Sets&#41;</span><span class="sxs-lookup"><span data-stu-id="d8e2f-151">Using Multiple Active Result Sets &#40;MARS&#41;</span></span>](../native-client/features/using-multiple-active-result-sets-mars.md)  
  
  
