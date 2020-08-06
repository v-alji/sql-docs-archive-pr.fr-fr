---
title: bcp_init | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_init
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_init function
ms.assetid: 6a25862c-7f31-4873-ab65-30f3abde89d2
author: rothja
ms.author: jroth
ms.openlocfilehash: 72d48b2a07e425e0863084c700c4de93d2776739
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603508"
---
# <a name="bcp_init"></a><span data-ttu-id="94078-102">bcp_init</span><span class="sxs-lookup"><span data-stu-id="94078-102">bcp_init</span></span>
  <span data-ttu-id="94078-103">Initialise l'opération de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="94078-103">Initializes the bulk copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94078-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="94078-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_init (  
HDBC   
hdbc  
,  
LPCTSTR   
szTable  
,  
LPCTSTR   
szDataFile  
,  
LPCTSTR   
szErrorFile  
,  
INT   
eDirection  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="94078-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="94078-105">Arguments</span></span>  
 <span data-ttu-id="94078-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="94078-106">*hdbc*</span></span>  
 <span data-ttu-id="94078-107">Handle de connexion ODBC compatible avec la copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="94078-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="94078-108">*szTable*</span><span class="sxs-lookup"><span data-stu-id="94078-108">*szTable*</span></span>  
 <span data-ttu-id="94078-109">Nom de la table de base de données depuis ou vers laquelle s'effectue la copie.</span><span class="sxs-lookup"><span data-stu-id="94078-109">Is the name of the database table to be copied into or out of.</span></span> <span data-ttu-id="94078-110">Ce nom peut aussi inclure le nom de la base de données ou le nom du propriétaire.</span><span class="sxs-lookup"><span data-stu-id="94078-110">This name can also include the database name or the owner name.</span></span> <span data-ttu-id="94078-111">Par exemple, **pubs. Gracie. titles**, **pubs.. les titres,** **Gracie. titles**et **titles** sont tous des noms de table autorisés.</span><span class="sxs-lookup"><span data-stu-id="94078-111">For example, **pubs.gracie.titles**, **pubs..titles**, **gracie.titles**, and **titles** are all legal table names.</span></span>  
  
 <span data-ttu-id="94078-112">Si *eDirection* est DB_OUT, *szTable* peut également être le nom d’une vue de base de données.</span><span class="sxs-lookup"><span data-stu-id="94078-112">If *eDirection* is DB_OUT, *szTable* can also be the name of a database view.</span></span>  
  
 <span data-ttu-id="94078-113">Si *eDirection* est DB_OUT et qu’une instruction SELECT est spécifiée à l’aide de [bcp_control](bcp-control.md) avant l’appel de [bcp_exec](bcp-exec.md) , **bcp_init**_szTable_ doit avoir la valeur null.</span><span class="sxs-lookup"><span data-stu-id="94078-113">If *eDirection* is DB_OUT and a SELECT statement is specified using [bcp_control](bcp-control.md) before [bcp_exec](bcp-exec.md) is called, **bcp_init**_szTable_ must be set to NULL.</span></span>  
  
 <span data-ttu-id="94078-114">*szDataFile*</span><span class="sxs-lookup"><span data-stu-id="94078-114">*szDataFile*</span></span>  
 <span data-ttu-id="94078-115">Nom du fichier utilisateur depuis ou vers lequel s'effectue la copie.</span><span class="sxs-lookup"><span data-stu-id="94078-115">Is the name of the user file to be copied into or out of.</span></span> <span data-ttu-id="94078-116">Si les données sont copiées directement à partir de variables à l’aide de [bcp_sendrow](bcp-sendrow.md), affectez la valeur null à *szDataFile* .</span><span class="sxs-lookup"><span data-stu-id="94078-116">If data is being copied directly from variables by using [bcp_sendrow](bcp-sendrow.md), set *szDataFile* to NULL.</span></span>  
  
 <span data-ttu-id="94078-117">*szErrorFile*</span><span class="sxs-lookup"><span data-stu-id="94078-117">*szErrorFile*</span></span>  
 <span data-ttu-id="94078-118">Nom du fichier d'erreurs à remplir avec les messages de progression, les messages d'erreur et les copies des lignes qui, pour quelque raison que ce soit, n'ont pas pu être copiées d'un fichier utilisateur vers une table.</span><span class="sxs-lookup"><span data-stu-id="94078-118">Is the name of the error file to be filled with progress messages, error messages, and copies of any rows that, for any reason, could not be copied from a user file to a table.</span></span> <span data-ttu-id="94078-119">Si la valeur NULL est transmise en tant que *szErrorFile*, aucun fichier d’erreur n’est utilisé.</span><span class="sxs-lookup"><span data-stu-id="94078-119">If NULL is passed as *szErrorFile*, no error file is used.</span></span>  
  
 <span data-ttu-id="94078-120">*eDirection*</span><span class="sxs-lookup"><span data-stu-id="94078-120">*eDirection*</span></span>  
 <span data-ttu-id="94078-121">Direction de la copie, DB_IN ou DB_OUT.</span><span class="sxs-lookup"><span data-stu-id="94078-121">Is the direction of the copy, either DB_IN or DB_OUT.</span></span> <span data-ttu-id="94078-122">DB_IN indique la copie de variables de programme ou d'un fichier utilisateur dans une table.</span><span class="sxs-lookup"><span data-stu-id="94078-122">DB_IN indicates a copy from program variables or a user file to a table.</span></span> <span data-ttu-id="94078-123">DB_OUT indique la copie d'une table de base de données dans un fichier utilisateur.</span><span class="sxs-lookup"><span data-stu-id="94078-123">DB_OUT indicates a copy from a database table to a user file.</span></span> <span data-ttu-id="94078-124">Vous devez spécifier un nom de fichier utilisateur avec DB_OUT.</span><span class="sxs-lookup"><span data-stu-id="94078-124">You must specify a user file name with DB_OUT.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="94078-125">Retours</span><span class="sxs-lookup"><span data-stu-id="94078-125">Returns</span></span>  
 <span data-ttu-id="94078-126">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="94078-126">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94078-127">Notes</span><span class="sxs-lookup"><span data-stu-id="94078-127">Remarks</span></span>  
 <span data-ttu-id="94078-128">Appelez **bcp_init** avant d’appeler une autre fonction de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="94078-128">Call **bcp_init** before calling any other bulk-copy function.</span></span> <span data-ttu-id="94078-129">**bcp_init** effectue les initialisations nécessaires pour une copie en bloc de données entre la station de travail et [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="94078-129">**bcp_init** performs the necessary initializations for a bulk copy of data between the workstation and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="94078-130">La fonction **bcp_init** doit être fournie avec un handle de connexion ODBC activé pour une utilisation avec des fonctions de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="94078-130">The **bcp_init** function must be provided with an ODBC connection handle enabled for use with bulk copy functions.</span></span> <span data-ttu-id="94078-131">Pour activer le descripteur, utilisez [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) avec SQL_COPT_SS_BCP défini sur SQL_BCP_ON sur un handle de connexion alloué, mais non connecté.</span><span class="sxs-lookup"><span data-stu-id="94078-131">To enable the handle, use [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_BCP set to SQL_BCP_ON on an allocated, but not connected, connection handle.</span></span> <span data-ttu-id="94078-132">La tentative d'assigner l'attribut sur un handle connecté provoque une erreur.</span><span class="sxs-lookup"><span data-stu-id="94078-132">Attempting to assign the attribute on a connected handle results in an error.</span></span>  
  
 <span data-ttu-id="94078-133">Lorsqu’un fichier de données est spécifié, **bcp_init** examine la structure de la source de la base de données ou de la table cible, et non pas le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="94078-133">When a data file is specified, **bcp_init** examines the structure of the database source or target table, not the data file.</span></span> <span data-ttu-id="94078-134">**bcp_init** spécifie des valeurs de format de données pour le fichier de données en fonction de chaque colonne de la table de base de données, de la vue ou du jeu de résultats Select.</span><span class="sxs-lookup"><span data-stu-id="94078-134">**bcp_init** specifies data format values for the data file based on each column in the database table, view, or SELECT result set.</span></span> <span data-ttu-id="94078-135">Cette spécification inclut le type de données de chaque colonne, la présence ou l'absence d'un indicateur de longueur ou null et des chaînes d'octet de terminateur dans les données, et la largeur des types de données de longueur fixe.</span><span class="sxs-lookup"><span data-stu-id="94078-135">This specification includes the data type of each column, the presence or absence of a length or null indicator and terminator byte strings in the data, and the width of fixed-length data types.</span></span> <span data-ttu-id="94078-136">**bcp_init** définit ces valeurs comme suit :</span><span class="sxs-lookup"><span data-stu-id="94078-136">**bcp_init** sets these values as follows:</span></span>  
  
-   <span data-ttu-id="94078-137">Le type de données spécifié est le type de données de la colonne dans la table de base de données, la vue ou le jeu de résultats SELECT.</span><span class="sxs-lookup"><span data-stu-id="94078-137">The data type specified is the data type of the column in the database table, view, or SELECT result set.</span></span> <span data-ttu-id="94078-138">Le type de données est énuméré par les types de données natifs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] spécifiés dans sqlncli.h.</span><span class="sxs-lookup"><span data-stu-id="94078-138">The data type is enumerated by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data types specified in sqlncli.h.</span></span> <span data-ttu-id="94078-139">Les données elles-mêmes sont représentées dans leur forme informatique.</span><span class="sxs-lookup"><span data-stu-id="94078-139">Data itself is represented in its computer form.</span></span> <span data-ttu-id="94078-140">Autrement dit, les données d’une colonne de type de données **Integer** sont représentées par une séquence de quatre octets qui est Big-endian ou Little-endian, en fonction de l’ordinateur qui a créé le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="94078-140">That is, data from a column of **integer** data type is represented by a four-byte sequence that is big-or little-endian based on the computer that created the data file.</span></span>  
  
-   <span data-ttu-id="94078-141">Si un type de données de base de données est de longueur fixe, les données du fichier de données sont également de longueur fixe.</span><span class="sxs-lookup"><span data-stu-id="94078-141">If a database data type is fixed in length, the data file data is also fixed in length.</span></span> <span data-ttu-id="94078-142">Les fonctions de copie en bloc qui traitent les données (par exemple, [bcp_exec](bcp-exec.md)) analysent les lignes de données, en attendant que la longueur des données dans le fichier de données soit identique à la longueur des données spécifiées dans la liste de la base de données, de la vue ou de la colonne Select.</span><span class="sxs-lookup"><span data-stu-id="94078-142">Bulk-copy functions that process data (for example, [bcp_exec](bcp-exec.md)) parse data rows expecting the length of the data in the data file to be identical to the length of the data specified in the database table, view, or SELECT column list.</span></span> <span data-ttu-id="94078-143">Par exemple, les données d’une colonne de base de données définie en tant que **char (13)** doivent être représentées par 13 caractères pour chaque ligne de données dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="94078-143">For example, data for a database column defined as **char(13)** must be represented by 13 characters for each row of data in the file.</span></span> <span data-ttu-id="94078-144">Les données de longueur fixe peuvent être préfixées avec un indicateur null si la colonne de base de données autorise les valeurs NULL.</span><span class="sxs-lookup"><span data-stu-id="94078-144">Fixed-length data can be prefixed with a null indicator if the database column allows null values.</span></span>  
  
-   <span data-ttu-id="94078-145">Lorsque la séquence d'octet de terminateur est définie, la longueur de la séquence d'octet de terminateur est définie avec la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="94078-145">When terminator-byte sequence is defined, the length of the terminator-byte sequence is set to 0.</span></span>  
  
-   <span data-ttu-id="94078-146">Lors de la copie vers [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], le fichier de données doit avoir les données de chaque colonne de la table de base de données.</span><span class="sxs-lookup"><span data-stu-id="94078-146">When copying to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the data file must have data for each column in the database table.</span></span> <span data-ttu-id="94078-147">Lors de la copie depuis [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], les données de toutes les colonnes de la table de base de données, de la vue ou du jeu de résultats SELECT, sont copiées vers le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="94078-147">When copying from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], data from all columns in the database table, view, or SELECT result set are copied to the data file.</span></span>  
  
-   <span data-ttu-id="94078-148">Lors de la copie vers [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], la position ordinale d'une colonne du fichier de données doit être identique à la position ordinale de la colonne de la table de base de données.</span><span class="sxs-lookup"><span data-stu-id="94078-148">When copying to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the ordinal position of a column in the data file must be identical to the ordinal position of the column in the database table.</span></span> <span data-ttu-id="94078-149">Lors de la copie à partir de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , **bcp_exec** place les données en fonction de la position ordinale de la colonne dans la table de base de données.</span><span class="sxs-lookup"><span data-stu-id="94078-149">When copying from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], **bcp_exec** places data based on the ordinal position of the column in the database table.</span></span>  
  
-   <span data-ttu-id="94078-150">Si le type de données d’une base de données est variable en longueur (par exemple, **varbinary (22)**) ou si une colonne de base de données peut contenir des valeurs NULL, les données du fichier de données sont précédées d’un indicateur de longueur/null.</span><span class="sxs-lookup"><span data-stu-id="94078-150">If a database data type is variable in length (for example, **varbinary(22)**) or if a database column can contain null values, data in the data file is prefixed by a length/null indicator.</span></span> <span data-ttu-id="94078-151">La largeur de l'indicateur varie selon le type de données et la version de la copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="94078-151">The width of the indicator varies based on the data type and version of bulk copy.</span></span>  
  
 <span data-ttu-id="94078-152">Pour modifier les valeurs de format de données spécifiées pour un fichier de données, appelez [bcp_columns](bcp-columns.md) et [bcp_colfmt](bcp-colfmt.md).</span><span class="sxs-lookup"><span data-stu-id="94078-152">To change data format values specified for a data file, call [bcp_columns](bcp-columns.md) and [bcp_colfmt](bcp-colfmt.md).</span></span>  
  
 <span data-ttu-id="94078-153">Les copies en bloc vers [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peuvent être optimisées pour les tables qui ne contiennent pas d'index en définissant le mode de récupération de base de données avec la valeur SIMPLE ou BULK_LOGGED.</span><span class="sxs-lookup"><span data-stu-id="94078-153">Bulk copies to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can be optimized for tables that do not contain indexes by setting the database recovery model to SIMPLE or BULK_LOGGED.</span></span> <span data-ttu-id="94078-154">Pour plus d’informations, consultez [Configuration requise pour la journalisation minimale dans l’importation en bloc](../import-export/prerequisites-for-minimal-logging-in-bulk-import.md) et [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="94078-154">For more information, see [Prerequisites for Minimal Logging in Bulk Import](../import-export/prerequisites-for-minimal-logging-in-bulk-import.md) and [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
 <span data-ttu-id="94078-155">Si aucun fichier de données n’est utilisé, vous devez appeler [bcp_bind](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md) pour spécifier le format et l’emplacement en mémoire des données de chaque colonne, puis copier les lignes de données dans le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [bcp_sendrow](bcp-sendrow.md)à l’aide de.</span><span class="sxs-lookup"><span data-stu-id="94078-155">If no data file is used, you must call [bcp_bind](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md) to specify the format and location in memory of the data fsor each column, then copy data rows to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="94078-156">Exemple</span><span class="sxs-lookup"><span data-stu-id="94078-156">Example</span></span>  
 <span data-ttu-id="94078-157">Cet exemple montre comment utiliser la fonction ODBC bcp_init avec un fichier de format.</span><span class="sxs-lookup"><span data-stu-id="94078-157">This sample shows how to use the ODBC bcp_init function with a format file.</span></span>  
  
 <span data-ttu-id="94078-158">Avant de compiler et d'exécuter le code C++, vous devez procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="94078-158">Before you compile and run the C++ code, you need to do the following:</span></span>  
  
-   <span data-ttu-id="94078-159">Créez une source de données ODBC nommée Test.</span><span class="sxs-lookup"><span data-stu-id="94078-159">Create an ODBC data source called Test.</span></span> <span data-ttu-id="94078-160">Vous pouvez associer cette source de données à toute base de données.</span><span class="sxs-lookup"><span data-stu-id="94078-160">You can associate this data source with any database.</span></span>  
  
-   <span data-ttu-id="94078-161">Exécutez l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] suivante sur la base de données :</span><span class="sxs-lookup"><span data-stu-id="94078-161">Run the following [!INCLUDE[tsql](../../includes/tsql-md.md)] on the database:</span></span>  
  
    ```  
    CREATE TABLE BCPDate (cola int, colb datetime);  
    ```  
  
-   <span data-ttu-id="94078-162">Dans le répertoire dans lequel l'application sera exécutée, ajoutez un fichier nommé Bcpfmt.fmt, puis ajoutez le code suivant au fichier :</span><span class="sxs-lookup"><span data-stu-id="94078-162">In the directory where you will run the application, add a file called Bcpfmt.fmt, and add this to the file:</span></span>  
  
    ```  
    8.0  
    2  
    1SQLCHAR04"\t"1colaSQL_Latin1_General_Cp437_Bin  
    2SQLCHAR08"\r\n"2colbSQL_Latin1_General_Cp437_Bin  
    ```  
  
-   <span data-ttu-id="94078-163">Dans le répertoire dans lequel l'application sera exécutée, ajoutez un fichier nommé Bcpodbc.bcp, puis ajoutez le code suivant au fichier :</span><span class="sxs-lookup"><span data-stu-id="94078-163">In the directory where you will run the application, add a file called Bcpodbc.bcp, and add this to the file:</span></span>  
  
    ```  
    1  
    2  
    ```  
  
 <span data-ttu-id="94078-164">Vous êtes à présent prêt à compiler et exécuter le code C++.</span><span class="sxs-lookup"><span data-stu-id="94078-164">Now you are ready to compile and run the C++ code.</span></span>  
  
```  
// compile with: odbc32.lib sqlncli11.lib  
#include <stdio.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
SQLHENV henv = SQL_NULL_HENV;  
HDBC hdbc1 = SQL_NULL_HDBC;   
  
void Cleanup() {  
   if (hdbc1 != SQL_NULL_HDBC) {  
      SQLDisconnect(hdbc1);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   }  
  
   if (henv != SQL_NULL_HENV)  
      SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
int main() {  
   RETCODE retcode;  
   SDWORD cRows;  
  
   // Allocate the ODBC environment and save handle.  
   retcode = SQLAllocHandle (SQL_HANDLE_ENV, NULL, &henv);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(Env) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Notify ODBC that this is an ODBC 3.0 app.  
   retcode = SQLSetEnvAttr(henv, SQL_ATTR_ODBC_VERSION, (SQLPOINTER) SQL_OV_ODBC3, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetEnvAttr(ODBC version) Failed\n\n");  
      Cleanup();  
      return(9);      
   }  
  
   // Allocate ODBC connection handle, set BCP mode, and connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLSetConnectAttr(hdbc1, SQL_COPT_SS_BCP, (void *)SQL_BCP_ON, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetConnectAttr(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Sample uses Integrated Security. Create SQL Server DSN using Windows NT authentication.  
   retcode = SQLConnect(hdbc1, (UCHAR*)"Test", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Initialize the bulk copy.  
   retcode = bcp_init(hdbc1, "BCPDate", "BCPODBC.bcp", NULL, DB_IN);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_init(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Read the format file.  
   retcode = bcp_readfmt(hdbc1, "BCPFMT.fmt");  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_readfmt(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Execute the bulk copy.  
   retcode = bcp_exec(hdbc1, &cRows);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_exec(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   printf("Number of rows bulk copied in = %d.\n", cRows);  
  
   // Cleanup  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="94078-165">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="94078-165">See Also</span></span>  
 [<span data-ttu-id="94078-166">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="94078-166">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
