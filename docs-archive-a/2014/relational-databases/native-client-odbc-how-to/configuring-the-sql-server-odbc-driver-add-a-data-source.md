---
title: Ajouter une source de données (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data sources [ODBC]
ms.assetid: b4ac6f0e-8e6a-4b1a-9a7e-60e0a69b2180
author: rothja
ms.author: jroth
ms.openlocfilehash: 519990e9dd9d84f75c4efc6c76b910f0a359f52f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603495"
---
# <a name="add-a-data-source-odbc"></a><span data-ttu-id="afe22-102">Ajouter une source de données (ODBC)</span><span class="sxs-lookup"><span data-stu-id="afe22-102">Add a Data Source (ODBC)</span></span>
  <span data-ttu-id="afe22-103">Vous pouvez ajouter une source de données à l’aide de l’administrateur ODBC, par programmation (à l’aide de [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md)) ou en créant un fichier.</span><span class="sxs-lookup"><span data-stu-id="afe22-103">You can add a data source by using ODBC Administrator, programmatically (by using [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md)), or by creating a file.</span></span>  
  
### <a name="to-add-a-data-source-by-using-odbc-administrator"></a><span data-ttu-id="afe22-104">Pour ajouter une source de données à l'aide de l'Administrateur ODBC</span><span class="sxs-lookup"><span data-stu-id="afe22-104">To add a data source by using ODBC Administrator</span></span>  
  
1.  <span data-ttu-id="afe22-105">Dans le **panneau de configuration**, accédez à **Outils d’administration** , puis à **sources de données (ODBC)**.</span><span class="sxs-lookup"><span data-stu-id="afe22-105">From the **Control Panel**, access **Administrative Tools** and then **Data Sources (ODBC)**.</span></span> <span data-ttu-id="afe22-106">Vous pouvez également appeler l'exécutable odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="afe22-106">Alternatively, you can invoke odbcad32.exe.</span></span>  
  
2.  <span data-ttu-id="afe22-107">Cliquez sur l’onglet **DSN utilisateur**, **système DSN**ou **fichier DSN** , puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="afe22-107">Click the **User DSN**, **System DSN**, or **File DSN** tab, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="afe22-108">Cliquez sur **SQL Server**, puis sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="afe22-108">Click **SQL Server**, and then click **Finish**.</span></span>  
  
4.  <span data-ttu-id="afe22-109">Suivez les étapes de l'Assistant Créer une nouvelle source de données vers SQL Server.</span><span class="sxs-lookup"><span data-stu-id="afe22-109">Complete the Steps in the Create a New Data Source to SQL Server Wizard.</span></span>  
  
### <a name="to-add-a-data-source-programmatically"></a><span data-ttu-id="afe22-110">Pour ajouter une source de données par programme</span><span class="sxs-lookup"><span data-stu-id="afe22-110">To add a data source programmatically</span></span>  
  
1.  <span data-ttu-id="afe22-111">Appelez [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md) avec le deuxième paramètre défini sur ODBC_ADD_DSN ou ODBC_ADD_SYS_DSN.</span><span class="sxs-lookup"><span data-stu-id="afe22-111">Call [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md) with the second parameter set to either ODBC_ADD_DSN or ODBC_ADD_SYS_DSN.</span></span>  
  
### <a name="to-add-a-file-data-source"></a><span data-ttu-id="afe22-112">Pour ajouter une source de données de fichier</span><span class="sxs-lookup"><span data-stu-id="afe22-112">To add a file data source</span></span>  
  
1.  <span data-ttu-id="afe22-113">Appelez [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) avec un paramètre SAVEFILE = file_name dans la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="afe22-113">Call [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) with a SAVEFILE=file_name parameter in the connect string.</span></span> <span data-ttu-id="afe22-114">Si la connexion est un succès, le pilote ODBC crée une source de données de fichier avec les paramètres de connexion dans l'emplacement désigné par le paramètre SAVEFILE.</span><span class="sxs-lookup"><span data-stu-id="afe22-114">If the connect is successful, the ODBC driver creates a file data source with the connection parameters in the location pointed to by the SAVEFILE parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afe22-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="afe22-115">See Also</span></span>  
 [<span data-ttu-id="afe22-116">Rubriques des procédures relatives à la configuration du pilote ODBC SQL Server</span><span class="sxs-lookup"><span data-stu-id="afe22-116">Configuring the SQL Server ODBC Driver How-to Topics</span></span>](../../database-engine/dev-guide/configuring-the-sql-server-odbc-driver-how-to-topics.md)  
  
  
