---
title: Allouer des descripteurs et se connecter à SQL Server (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- handles [ODBC]
- handles [ODBC], connection
- handles [ODBC], about handles
ms.assetid: 6172cd52-9c9a-467d-992f-def07f3f3bb1
author: rothja
ms.author: jroth
ms.openlocfilehash: 615a6dbe966b4c681e9cd4285ff55864d7a13370
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709364"
---
# <a name="allocate-handles-and-connect-to-sql-server-odbc"></a><span data-ttu-id="23656-102">Allouer des handles et se connecter à SQL Server (ODBC)</span><span class="sxs-lookup"><span data-stu-id="23656-102">Allocate Handles and Connect to SQL Server (ODBC)</span></span>
    
### <a name="to-allocate-handles-and-connect-to-sql-server"></a><span data-ttu-id="23656-103">Pour allouer les handles et se connecter à SQL Server</span><span class="sxs-lookup"><span data-stu-id="23656-103">To allocate handles and connect to SQL Server</span></span>  
  
1.  <span data-ttu-id="23656-104">Incluez les fichiers d'en-tête ODBC Sql.h, Sqlext.h, Sqltypes.h.</span><span class="sxs-lookup"><span data-stu-id="23656-104">Include the ODBC header files Sql.h, Sqlext.h, Sqltypes.h.</span></span>  
  
2.  <span data-ttu-id="23656-105">Incluez le fichier d'en-tête spécifique au pilote [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Odbcss.h.</span><span class="sxs-lookup"><span data-stu-id="23656-105">Include the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver-specific header file, Odbcss.h.</span></span>  
  
3.  <span data-ttu-id="23656-106">Appelez [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) avec un `HandleType` de SQL_HANDLE_ENV pour initialiser ODBC et allouer un handle d’environnement.</span><span class="sxs-lookup"><span data-stu-id="23656-106">Call [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) with a `HandleType` of SQL_HANDLE_ENV to initialize ODBC and allocate an environment handle.</span></span>  
  
4.  <span data-ttu-id="23656-107">Appelez [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) avec la `Attribute` valeur SQL_ATTR_ODBC_VERSION et `ValuePtr` définissez sur SQL_OV_ODBC3 pour indiquer que l’application utilisera les appels de fonction ODBC 3. x-format.</span><span class="sxs-lookup"><span data-stu-id="23656-107">Call [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) with `Attribute` set to SQL_ATTR_ODBC_VERSION and `ValuePtr` set to SQL_OV_ODBC3 to indicate the application will use ODBC 3.x-format function calls.</span></span>  
  
5.  <span data-ttu-id="23656-108">Si vous le souhaitez, appelez [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) pour définir d’autres options d’environnement, ou appelez [SQLGetEnvAttr](https://go.microsoft.com/fwlink/?LinkId=58403) pour accéder aux options d’environnement.</span><span class="sxs-lookup"><span data-stu-id="23656-108">Optionally, call [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) to set other environment options, or call [SQLGetEnvAttr](https://go.microsoft.com/fwlink/?LinkId=58403) to get environment options.</span></span>  
  
6.  <span data-ttu-id="23656-109">Appelez [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) avec un `HandleType` de SQL_HANDLE_DBC pour allouer un handle de connexion.</span><span class="sxs-lookup"><span data-stu-id="23656-109">Call [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) with a `HandleType` of SQL_HANDLE_DBC to allocate a connection handle.</span></span>  
  
7.  <span data-ttu-id="23656-110">Vous pouvez également appeler [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) pour définir les options de connexion ou appeler [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) pour accéder aux options de connexion.</span><span class="sxs-lookup"><span data-stu-id="23656-110">Optionally, call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) to set connection options, or call [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) to get connection options.</span></span>  
  
8.  <span data-ttu-id="23656-111">Appelez SQLConnect pour utiliser une source de données existante à laquelle se connecter [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23656-111">Call SQLConnect to use an existing data source to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="23656-112">ou</span><span class="sxs-lookup"><span data-stu-id="23656-112">Or</span></span>  
  
     <span data-ttu-id="23656-113">Appelez [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) pour utiliser une chaîne de connexion à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23656-113">Call [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) to use a connection string to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="23656-114">Une chaîne de connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] minimale complète revêt l'une des deux formes :</span><span class="sxs-lookup"><span data-stu-id="23656-114">A minimum complete [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection string has one of two forms:</span></span>  
  
    ```  
    DSN=dsn_name;Trusted_connection=yes;  
    DRIVER={SQL Server Native Client 10.0};SERVER=server;Trusted_connection=yes;  
    ```  
  
     <span data-ttu-id="23656-115">Si la chaîne de connexion n'est pas complète, `SQLDriverConnect` peut demander les informations nécessaires.</span><span class="sxs-lookup"><span data-stu-id="23656-115">If the connection string is not complete, `SQLDriverConnect` can prompt for the required information.</span></span> <span data-ttu-id="23656-116">Cela est contrôlé par la valeur spécifiée pour le paramètre *DriverCompletion* .</span><span class="sxs-lookup"><span data-stu-id="23656-116">This is controlled by the value specified for the *DriverCompletion* parameter.</span></span>  
  
     <span data-ttu-id="23656-117">\- ou -</span><span class="sxs-lookup"><span data-stu-id="23656-117">\- or -</span></span>  
  
     <span data-ttu-id="23656-118">Appelez plusieurs fois [SQLBrowseConnect](../native-client-odbc-api/sqlbrowseconnect.md) de manière itérative pour créer la chaîne de connexion et vous connecter à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23656-118">Call [SQLBrowseConnect](../native-client-odbc-api/sqlbrowseconnect.md) multiple times in an iterative fashion to build the connection string and connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
9. <span data-ttu-id="23656-119">Vous pouvez également appeler [SQLGetInfo](../native-client-odbc-api/sqlgetinfo.md) pour obtenir les attributs de pilote et le comportement de la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source de données.</span><span class="sxs-lookup"><span data-stu-id="23656-119">Optionally, call [SQLGetInfo](../native-client-odbc-api/sqlgetinfo.md) to get driver attributes and behavior for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source.</span></span>  
  
10. <span data-ttu-id="23656-120">Allouez et utilisez les instructions.</span><span class="sxs-lookup"><span data-stu-id="23656-120">Allocate and use statements.</span></span>  
  
11. <span data-ttu-id="23656-121">Appelez SQLDisconnect pour vous déconnecter [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et rendre le descripteur de connexion disponible pour une nouvelle connexion.</span><span class="sxs-lookup"><span data-stu-id="23656-121">Call SQLDisconnect to disconnect from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and make the connection handle available for a new connection.</span></span>  
  
12. <span data-ttu-id="23656-122">Appelez [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) avec un `HandleType` de SQL_HANDLE_DBC pour libérer le handle de connexion.</span><span class="sxs-lookup"><span data-stu-id="23656-122">Call [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) with a `HandleType` of SQL_HANDLE_DBC to free the connection handle.</span></span>  
  
13. <span data-ttu-id="23656-123">Appelez `SQLFreeHandle` avec un `HandleType` de SQL_HANDLE_ENV pour libérer le handle d'environnement.</span><span class="sxs-lookup"><span data-stu-id="23656-123">Call `SQLFreeHandle` with a `HandleType` of SQL_HANDLE_ENV to free the environment handle.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="23656-124">Lorsque c'est possible, utilisez l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="23656-124">When possible, use Windows Authentication.</span></span> <span data-ttu-id="23656-125">Si l'authentification Windows n'est pas disponible, invitez les utilisateurs à entrer leurs informations d'identification au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="23656-125">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="23656-126">Évitez de stocker ces informations dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="23656-126">Avoid storing credentials in a file.</span></span> <span data-ttu-id="23656-127">Si vous devez conserver des informations d’identification, vous devez les chiffrer avec l' [API de chiffrement Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="23656-127">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
## <a name="example"></a><span data-ttu-id="23656-128">Exemple</span><span class="sxs-lookup"><span data-stu-id="23656-128">Example</span></span>  
 <span data-ttu-id="23656-129">Cet exemple illustre un appel de `SQLDriverConnect` pour se connecter à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sans requérir une source de données ODBC existante.</span><span class="sxs-lookup"><span data-stu-id="23656-129">This example shows a call to `SQLDriverConnect` to connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without requiring an existing ODBC data source.</span></span> <span data-ttu-id="23656-130">En passant une chaîne de connexion incomplète à `SQLDriverConnect`, le pilote ODBC est contraint de demander à l'utilisateur d'entrer les informations manquantes.</span><span class="sxs-lookup"><span data-stu-id="23656-130">By passing an incomplete connection string to `SQLDriverConnect`, it causes the ODBC driver to prompt the user to enter the missing information.</span></span>  
  
```  
#define MAXBUFLEN   255  
  
SQLHENV      henv = SQL_NULL_HENV;  
SQLHDBC      hdbc1 = SQL_NULL_HDBC;  
SQLHSTMT      hstmt1 = SQL_NULL_HSTMT;  
  
SQLCHAR      ConnStrIn[MAXBUFLEN] =  
         "DRIVER={SQL Server Native Client 10.0};SERVER=MyServer";  
  
SQLCHAR      ConnStrOut[MAXBUFLEN];  
SQLSMALLINT   cbConnStrOut = 0;  
  
// Make connection without data source. Ask that driver   
// prompt if insufficient information. Driver returns  
// SQL_ERROR and application prompts user  
// for missing information. Window handle not needed for  
// SQL_DRIVER_NOPROMPT.  
retcode = SQLDriverConnect(hdbc1,      // Connection handle  
                  NULL,         // Window handle  
                  ConnStrIn,      // Input connect string  
                  SQL_NTS,         // Null-terminated string  
                  ConnStrOut,      // Address of output buffer  
                  MAXBUFLEN,      // Size of output buffer  
                  &cbConnStrOut,   // Address of output length  
                  SQL_DRIVER_PROMPT);  
```  
  
  
