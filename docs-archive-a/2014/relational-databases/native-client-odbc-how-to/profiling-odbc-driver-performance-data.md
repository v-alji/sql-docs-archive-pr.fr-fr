---
title: Données de performances du pilote de profil (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- driver performance data [ODBC]
ms.assetid: b997790a-8cc6-4800-8867-74c1bef07be3
author: rothja
ms.author: jroth
ms.openlocfilehash: 3575cfd304d526bdb25eee6a2578d67c6bb67bc9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698160"
---
# <a name="profile-driver-performance-data-odbc"></a><span data-ttu-id="3de66-102">Définir le profil des données de performances du pilote (ODBC)</span><span class="sxs-lookup"><span data-stu-id="3de66-102">Profile Driver Performance Data (ODBC)</span></span>
  <span data-ttu-id="3de66-103">Cet exemple présente les options [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] spécifiques aux pilotes ODBC et destinées à l'enregistrement des statistiques de performances.</span><span class="sxs-lookup"><span data-stu-id="3de66-103">This sample shows the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC driver-specific options to record performance statistics.</span></span> <span data-ttu-id="3de66-104">Cet exemple crée un fichier odbcperf.log. Il illustre à la fois la création d'un fichier journal des données de performances et l'affichage de ces données directement à partir de la structure de données SQLPERF. (La structure SQLPERF est définie dans Odbcss.h.).</span><span class="sxs-lookup"><span data-stu-id="3de66-104">The sample creates one file: odbcperf.log.This sample shows both the creation of a performance data log file and displaying performance data directly from the SQLPERF data structure (The SQLPERF structure is defined in Odbcss.h.).</span></span> <span data-ttu-id="3de66-105">Cet exemple a été développé pour la version 3.0 d'ODBC ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="3de66-105">This sample was developed for ODBC version 3.0 or later.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3de66-106">Lorsque c'est possible, utilisez l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="3de66-106">When possible, use Windows Authentication.</span></span> <span data-ttu-id="3de66-107">Si l'authentification Windows n'est pas disponible, invitez les utilisateurs à entrer leurs informations d'identification au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="3de66-107">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="3de66-108">Évitez de stocker ces informations dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="3de66-108">Avoid storing credentials in a file.</span></span> <span data-ttu-id="3de66-109">Si vous devez conserver des informations d’identification, vous devez les chiffrer avec l' [API de chiffrement Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="3de66-109">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-log-driver-performance-data-using-odbc-administrator"></a><span data-ttu-id="3de66-110">Pour enregistrer les données de performances du pilote à l'aide de l'Administrateur ODBC</span><span class="sxs-lookup"><span data-stu-id="3de66-110">To log driver performance data using ODBC Administrator</span></span>  
  
1.  <span data-ttu-id="3de66-111">Dans **le panneau de configuration**, double-cliquez sur **Outils d’administration** , puis sur **sources de données (ODBC)**.</span><span class="sxs-lookup"><span data-stu-id="3de66-111">In **Control Panel**, double-click **Administrative Tools** and then double-click **Data Sources (ODBC)**.</span></span> <span data-ttu-id="3de66-112">Vous pouvez également appeler l'exécutable odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="3de66-112">Alternatively, you can invoke odbcad32.exe.</span></span>  
  
2.  <span data-ttu-id="3de66-113">Cliquez sur l’onglet **DSN utilisateur**, **système DSN**ou **fichier DSN** .</span><span class="sxs-lookup"><span data-stu-id="3de66-113">Click the **User DSN**, **System DSN**, or **File DSN** tab.</span></span>  
  
3.  <span data-ttu-id="3de66-114">Cliquez sur la source de données dont vous souhaitez consigner les performances.</span><span class="sxs-lookup"><span data-stu-id="3de66-114">Click the data source for which to log performance.</span></span>  
  
4.  <span data-ttu-id="3de66-115">Cliquez sur **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="3de66-115">Click **Configure**.</span></span>  
  
5.  <span data-ttu-id="3de66-116">Dans l’Assistant Microsoft SQL Server configurer un DSN, accédez à la page contenant les **statistiques du pilote ODBC du journal dans le fichier journal**.</span><span class="sxs-lookup"><span data-stu-id="3de66-116">In the Microsoft SQL Server Configure DSN Wizard, navigate to the page with **Log ODBC driver statistics to the log file**.</span></span>  
  
6.  <span data-ttu-id="3de66-117">Sélectionnez **enregistrer les statistiques du pilote ODBC dans le fichier journal**.</span><span class="sxs-lookup"><span data-stu-id="3de66-117">Select **Log ODBC driver statistics to the log file**.</span></span> <span data-ttu-id="3de66-118">Dans la zone, tapez le nom du fichier dans lequel les statistiques sont à enregistrer.</span><span class="sxs-lookup"><span data-stu-id="3de66-118">In the box, place the name of the file where the statistics should be logged.</span></span> <span data-ttu-id="3de66-119">Si vous le souhaitez, cliquez sur **Parcourir** pour rechercher le journal des statistiques dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="3de66-119">Optionally, click **Browse** to browse the file system for the statistics log.</span></span>  
  
### <a name="to-log-driver-performance-data-programmatically"></a><span data-ttu-id="3de66-120">Pour enregistrer les données de performances du pilote par programme</span><span class="sxs-lookup"><span data-stu-id="3de66-120">To log driver performance data programmatically</span></span>  
  
1.  <span data-ttu-id="3de66-121">Appelez [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) avec SQL_COPT_SS_PERF_DATA_LOG et le chemin d’accès complet et le nom du fichier journal des données de performances.</span><span class="sxs-lookup"><span data-stu-id="3de66-121">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA_LOG and the full path and file name of the performance data log file.</span></span> <span data-ttu-id="3de66-122">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="3de66-122">For example:</span></span>  
  
    ```  
    "C:\\Odbcperf.log"  
    ```  
  
2.  <span data-ttu-id="3de66-123">Appelez [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) avec SQL_COPT_SS_PERF_DATA et SQL_PERF_START pour commencer l’enregistrement des données de performances.</span><span class="sxs-lookup"><span data-stu-id="3de66-123">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA and SQL_PERF_START to start logging performance data.</span></span>  
  
3.  <span data-ttu-id="3de66-124">Vous pouvez également appeler [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) avec SQL_COPT_SS_LOG_NOW et null pour écrire un enregistrement délimité par des tabulations de données de performances dans le fichier journal des données de performances.</span><span class="sxs-lookup"><span data-stu-id="3de66-124">Optionally, call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_LOG_NOW and NULL to write a tab-delimited record of performance data to the performance data log file.</span></span> <span data-ttu-id="3de66-125">Vous pouvez effectuer plusieurs fois cette opération en cours d'exécution de l'application.</span><span class="sxs-lookup"><span data-stu-id="3de66-125">This can be done multiple times as the application runs.</span></span>  
  
4.  <span data-ttu-id="3de66-126">Appelez [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) avec SQL_COPT_SS_PERF_DATA et SQL_PERF_STOP pour arrêter l’enregistrement des données de performances.</span><span class="sxs-lookup"><span data-stu-id="3de66-126">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA and SQL_PERF_STOP to stop logging performance data.</span></span>  
  
### <a name="to-pull-driver-performance-data-into-an-application"></a><span data-ttu-id="3de66-127">Pour extraire les données de performances du pilote dans une application</span><span class="sxs-lookup"><span data-stu-id="3de66-127">To pull driver performance data into an application</span></span>  
  
1.  <span data-ttu-id="3de66-128">Appelez [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) avec SQL_COPT_SS_PERF_DATA et SQL_PERF_START pour démarrer le profilage des données de performances.</span><span class="sxs-lookup"><span data-stu-id="3de66-128">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA and SQL_PERF_START to start profiling performance data.</span></span>  
  
2.  <span data-ttu-id="3de66-129">Appelez [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) avec SQL_COPT_SS_PERF_DATA et l’adresse d’un pointeur vers une structure SQLPERF.</span><span class="sxs-lookup"><span data-stu-id="3de66-129">Call [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) with SQL_COPT_SS_PERF_DATA and the address of a pointer to a SQLPERF structure.</span></span> <span data-ttu-id="3de66-130">Le premier appel définit le pointeur sur l'adresse d'une structure SQLPERF valide qui contient les données de performances actuelles.</span><span class="sxs-lookup"><span data-stu-id="3de66-130">The first such call sets the pointer to the address of a valid SQLPERF structure that contains current performance data.</span></span> <span data-ttu-id="3de66-131">Le pilote n'actualise pas en permanence les données dans la structure de performance.</span><span class="sxs-lookup"><span data-stu-id="3de66-131">The driver does not continually refresh the data in the performance structure.</span></span> <span data-ttu-id="3de66-132">L’application doit répéter l’appel à [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) chaque fois qu’elle a besoin d’actualiser la structure avec des données de performances plus récentes.</span><span class="sxs-lookup"><span data-stu-id="3de66-132">The application must repeat the call to [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) any time it needs to refresh the structure with more current performance data.</span></span>  
  
3.  <span data-ttu-id="3de66-133">Appelez [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) avec SQL_COPT_SS_PERF_DATA et SQL_PERF_STOP pour arrêter l’enregistrement des données de performances.</span><span class="sxs-lookup"><span data-stu-id="3de66-133">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA and SQL_PERF_STOP to stop logging performance data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3de66-134">Exemple</span><span class="sxs-lookup"><span data-stu-id="3de66-134">Example</span></span>  
 <span data-ttu-id="3de66-135">Vous aurez besoin d'une source de données ODBC nommée AdventureWorks, dont la base de données par défaut est l'exemple de base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="3de66-135">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="3de66-136">(Vous pouvez télécharger l’exemple de base de données AdventureWorks à partir de la page d’hébergement [exemples et projets de la communauté Microsoft SQL Server](https://go.microsoft.com/fwlink/?LinkID=85384) .) Cette source de données doit être basée sur le pilote ODBC fourni par le système d’exploitation (le nom du pilote est « SQL Server »).</span><span class="sxs-lookup"><span data-stu-id="3de66-136">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="3de66-137">Si vous générez et exécutez cet exemple comme une application 32 bits sur un système d'exploitation 64 bits, vous devez créer la source de données ODBC avec l'administrateur ODBC dans %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="3de66-137">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="3de66-138">Cet exemple vous permet de vous connecter à l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] par défaut de votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="3de66-138">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="3de66-139">Pour vous connecter à une instance nommée, modifiez la définition de la source de données ODBC pour spécifier l'instance en utilisant le format suivant : serveur\namedinstance.</span><span class="sxs-lookup"><span data-stu-id="3de66-139">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="3de66-140">Par défaut, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] est installé dans une instance nommée.</span><span class="sxs-lookup"><span data-stu-id="3de66-140">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="3de66-141">Compilez avec odbc32.lib.</span><span class="sxs-lookup"><span data-stu-id="3de66-141">Compile with odbc32.lib.</span></span>  
  
```  
// compile with: odbc32.lib  
#include <stdio.h>  
#include <string.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
SQLHENV henv = SQL_NULL_HENV;  
SQLHDBC hdbc1 = SQL_NULL_HDBC;       
SQLHSTMT hstmt1 = SQL_NULL_HSTMT;  
  
void Cleanup() {  
   if (hstmt1 != SQL_NULL_HSTMT)  
      SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
  
   if (hdbc1 != SQL_NULL_HDBC) {  
      SQLDisconnect(hdbc1);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   }  
  
   if (henv != SQL_NULL_HENV)  
      SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
int main() {  
   RETCODE retcode;  
  
   // Pointer to the ODBC driver performance structure.  
   SQLPERF *PerfPtr;  
   SQLINTEGER cbPerfPtr;  
  
   // Allocate the ODBC environment and save handle.  
   retcode = SQLAllocHandle (SQL_HANDLE_ENV, NULL, &henv);  
   if( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(Env) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Notify ODBC that this is an ODBC 3.0 app.  
   retcode = SQLSetEnvAttr(henv, SQL_ATTR_ODBC_VERSION, (SQLPOINTER) SQL_OV_ODBC3, SQL_IS_INTEGER);  
   if( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetEnvAttr(ODBC version) Failed\n\n");  
      Cleanup();  
      return(9);      
   }  
  
   // Allocate ODBC connection handle and connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // This sample use Integrated Security. Please create the SQL Server   
   // DSN by using the Windows NT authentication.   
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Set options to log performance statistics.  Specify file to use for the log.  
   retcode = SQLSetConnectAttr( hdbc1, SQL_COPT_SS_PERF_DATA_LOG, &"odbcperf.log", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLSetConnectAttr() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Start the performance statistics log.  
   retcode =   
      SQLSetConnectAttr( hdbc1, SQL_COPT_SS_PERF_DATA, (SQLPOINTER)SQL_PERF_START, SQL_IS_UINTEGER);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLSetConnectAttr() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Allocate statement handle, then execute command.  
   retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLAllocHandle() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"SELECT * FROM Purchasing.Vendor", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA ) {  
      if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLMoreResults() Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }  
  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"SELECT * FROM Sales.Store", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA ) {  
      if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLMoreResults() Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }  
  
   // Generate a long-running query.  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"waitfor delay '00:00:04' ", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA ) {  
      if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLMoreResults() Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }  
  
   // Write current statistics to the performance log.  
   retcode =   
      SQLSetConnectAttr( hdbc1, SQL_COPT_SS_PERF_DATA_LOG_NOW, (SQLPOINTER)NULL, SQL_IS_UINTEGER);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLSetConnectAttr() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Get pointer to current SQLPerf structure.  
   // Print a couple of statistics.  
   retcode =   
      SQLGetConnectAttr( hdbc1, SQL_COPT_SS_PERF_DATA, (SQLPOINTER)&PerfPtr, SQL_IS_POINTER, &cbPerfPtr);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLGetConnectAttr() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   printf("SQLSelects = %d, SQLSelectRows = %d\n", PerfPtr->SQLSelects, PerfPtr->SQLSelectRows);  
  
   // Cleanup  
   SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="3de66-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3de66-142">See Also</span></span>  
 <span data-ttu-id="3de66-143">[Rubriques de procédures relatives au profilage des performances du pilote ODBC &#40;ODBC&#41;](profiling-odbc-driver-performance-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="3de66-143">[Profiling ODBC Driver Performance How-to Topics &#40;ODBC&#41;](profiling-odbc-driver-performance-odbc.md) </span></span>  
 [<span data-ttu-id="3de66-144">Profilage des performances du pilote ODBC</span><span class="sxs-lookup"><span data-stu-id="3de66-144">Profiling ODBC Driver Performance</span></span>](../native-client/odbc/profiling-odbc-driver-performance.md)  
  
  
