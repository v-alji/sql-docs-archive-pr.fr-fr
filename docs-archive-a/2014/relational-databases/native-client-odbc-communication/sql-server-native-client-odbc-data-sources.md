---
title: SQL Server Native Client des sources de données ODBC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC data sources, about data sources
- ODBC data sources, names
- data sources [SQL Server Native Client]
- names [ODBC]
- ODBC applications, data sources
- SQL Server Native Client ODBC driver, data sources
- ODBC data sources
ms.assetid: a6a50fd0-d439-43fd-b76f-16ec02f478c5
author: rothja
ms.author: jroth
ms.openlocfilehash: 6960118e13f0843640b18056bda655726cbbbd29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605393"
---
# <a name="sql-server-native-client-odbc-data-sources"></a><span data-ttu-id="94adb-102">Sources de données ODBC SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="94adb-102">SQL Server Native Client ODBC Data Sources</span></span>
  <span data-ttu-id="94adb-103">Un nom de source de données (DSN) [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] identifie une source de données ODBC qui contient toutes les informations nécessaires à une application ODBC pour se connecter à une base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur un serveur spécifique.</span><span class="sxs-lookup"><span data-stu-id="94adb-103">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source name (DSN) identifies an ODBC data source containing all of the information that an ODBC application needs to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database on a specific server.</span></span> <span data-ttu-id="94adb-104">Il existe deux moyens de définir un nom de source de données ODBC :</span><span class="sxs-lookup"><span data-stu-id="94adb-104">There are two ways you can define an ODBC data source name:</span></span>  
  
-   <span data-ttu-id="94adb-105">Sur un ordinateur client, ouvrez outils d’administration dans le panneau de configuration, puis double-cliquez sur **sources de données (ODBC)**.</span><span class="sxs-lookup"><span data-stu-id="94adb-105">On a client computer, open Administrative Tools in Control Panel, and double-click **Data Sources (ODBC)**.</span></span> <span data-ttu-id="94adb-106">L'Administrateur de sources de données ODBC qui vous permet de créer un DSN s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="94adb-106">This will open the ODBC Data Source Administrator, which you can use to create a DSN.</span></span>  
  
-   <span data-ttu-id="94adb-107">Dans une application ODBC, appelez [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md).</span><span class="sxs-lookup"><span data-stu-id="94adb-107">In an ODBC application, call [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md).</span></span>  
  
 <span data-ttu-id="94adb-108">Une source de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] contient les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="94adb-108">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source contains:</span></span>  
  
-   <span data-ttu-id="94adb-109">Nom de la source de données.</span><span class="sxs-lookup"><span data-stu-id="94adb-109">The name of the data source.</span></span>  
  
-   <span data-ttu-id="94adb-110">Toutes les informations nécessaires pour se connecter à une instance spécifique de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94adb-110">Any information needed to connect to a specific instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="94adb-111">Base de données par défaut à utiliser dans une instance spécifique de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (facultatif).</span><span class="sxs-lookup"><span data-stu-id="94adb-111">The default database to use on a specific instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (optional).</span></span>  
  
-   <span data-ttu-id="94adb-112">Paramètres tels que les options ANSI à utiliser, le besoin ou non d'enregistrer des statistiques de performance, et ainsi de suite (facultatif).</span><span class="sxs-lookup"><span data-stu-id="94adb-112">Settings such as which ANSI options to use, whether to log performance statistics, and so on (optional).</span></span>  
  
 <span data-ttu-id="94adb-113">Aucune application ODBC n'est requise pour se connecter via une source de données.</span><span class="sxs-lookup"><span data-stu-id="94adb-113">An ODBC application is not required to connect through a data source.</span></span> <span data-ttu-id="94adb-114">En revanche, l'application doit fournir les mêmes informations de connectivité à une fonction de connexion ODBC que celles que trouverait le pilote dans un DSN.</span><span class="sxs-lookup"><span data-stu-id="94adb-114">However, the application must provide the same connectivity information to an ODBC connect function that the driver would otherwise find in a DSN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94adb-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="94adb-115">See Also</span></span>  
 [<span data-ttu-id="94adb-116">Communication avec SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="94adb-116">Communicating with SQL Server &#40;ODBC&#41;</span></span>](communicating-with-sql-server-odbc.md)  
  
  
