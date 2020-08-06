---
title: Supprimer une source de données (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data sources [ODBC]
ms.assetid: 910e3e16-7b91-49d8-80bb-b4243926afaa
author: rothja
ms.author: jroth
ms.openlocfilehash: 6e8acd6414b39b317ff0fcfe1b7b9fbab38ae0a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603493"
---
# <a name="delete-a-data-source-odbc"></a><span data-ttu-id="0f4ae-102">Supprimer une source de données (ODBC)</span><span class="sxs-lookup"><span data-stu-id="0f4ae-102">Delete a Data Source (ODBC)</span></span>
  <span data-ttu-id="0f4ae-103">Vous pouvez supprimer une source de données à l’aide de l’administrateur ODBC, par programmation (à l’aide de [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md)) ou en supprimant un fichier (si un nom de source de données de fichier).</span><span class="sxs-lookup"><span data-stu-id="0f4ae-103">You can delete a data source by using ODBC Administrator, programmatically (by using [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md)), or by deleting a file (if a file data source name).</span></span>  
  
### <a name="to-delete-a-data-source-by-using-odbc-administrator"></a><span data-ttu-id="0f4ae-104">Pour supprimer une source de données à l'aide de l'Administrateur ODBC</span><span class="sxs-lookup"><span data-stu-id="0f4ae-104">To delete a data source by using ODBC Administrator</span></span>  
  
1.  <span data-ttu-id="0f4ae-105">Dans **le panneau de configuration**, ouvrez **Outils d’administration**, puis double-cliquez sur **sources de données (ODBC)**.</span><span class="sxs-lookup"><span data-stu-id="0f4ae-105">In **Control Panel**, open **Administrative Tools**, and then double-click **Data Sources (ODBC)**.</span></span> <span data-ttu-id="0f4ae-106">Vous pouvez également exécuter odbcad32.exe à partir de l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="0f4ae-106">Alternatively, you can run odbcad32.exe from the command prompt.</span></span>  
  
2.  <span data-ttu-id="0f4ae-107">Cliquez sur l’onglet **DSN utilisateur**, **système DSN**ou **fichier DSN** .</span><span class="sxs-lookup"><span data-stu-id="0f4ae-107">Click the **User DSN**, **System DSN**, or **File DSN** tab.</span></span>  
  
3.  <span data-ttu-id="0f4ae-108">Cliquez sur la source de données à supprimer.</span><span class="sxs-lookup"><span data-stu-id="0f4ae-108">Click the data source to delete.</span></span>  
  
4.  <span data-ttu-id="0f4ae-109">Cliquez sur **supprimer**, puis confirmez la suppression.</span><span class="sxs-lookup"><span data-stu-id="0f4ae-109">Click **Remove**, and then confirm the deletion.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f4ae-110">Exemple</span><span class="sxs-lookup"><span data-stu-id="0f4ae-110">Example</span></span>  
 <span data-ttu-id="0f4ae-111">Pour supprimer par programmation une source de données, appelez [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md) en utilisant ODBC_REMOVE_DSN ou ODBC_REMOVE_SYS_DSN comme deuxième paramètre.</span><span class="sxs-lookup"><span data-stu-id="0f4ae-111">To programmatically delete a data source, call [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md) using either ODBC_REMOVE_DSN or ODBC_REMOVE_SYS_DSN as the second parameter.</span></span>  
  
 <span data-ttu-id="0f4ae-112">L'exemple suivant vous montre comment supprimer une source de données par programme.</span><span class="sxs-lookup"><span data-stu-id="0f4ae-112">The following sample shows how you can programmatically delete a data source.</span></span>  
  
```  
// remove_odbc_data_source.cpp  
// compile with: ODBCCP32.lib user32.lib  
#include <iostream>  
#include <windows.h>  
#include <odbcinst.h>  
  
int main() {   
   LPCSTR provider = "SQL Server";   // Windows SQL Server Driver  
   LPCSTR provider = "SQL Server";   // Windows SQL Server driver  
   LPCSTR provider2 = "SQL Server Native Client 11.0";   // SQL Server 2012 Native Client driver  
   LPCSTR dsnname = "DSN=data2";  
   BOOL retval = SQLConfigDataSource(NULL, ODBC_REMOVE_DSN, provider, dsnname);  
   std::cout << retval;   // 1 if successful  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f4ae-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0f4ae-113">See Also</span></span>  
 [<span data-ttu-id="0f4ae-114">Rubriques des procédures relatives à la configuration du pilote ODBC SQL Server</span><span class="sxs-lookup"><span data-stu-id="0f4ae-114">Configuring the SQL Server ODBC Driver How-to Topics</span></span>](../../database-engine/dev-guide/configuring-the-sql-server-odbc-driver-how-to-topics.md)  
  
  
