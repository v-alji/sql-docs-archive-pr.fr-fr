---
title: Communication avec SQL Server (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, communicating with SQL Server
- ODBC applications, communicating with SQL Server
- ODBC, communicating with SQL Server
ms.assetid: cca3dcf0-2a7e-465a-84de-7ce055360eb6
author: rothja
ms.author: jroth
ms.openlocfilehash: c41ac2dcce9c5bdbdd351148d16bcaa8f067d22f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706488"
---
# <a name="communicating-with-sql-server-odbc"></a><span data-ttu-id="8a51d-102">Communication avec SQL Server (ODBC)</span><span class="sxs-lookup"><span data-stu-id="8a51d-102">Communicating with SQL Server (ODBC)</span></span>
  <span data-ttu-id="8a51d-103">Pour qu’une application ODBC communique avec une instance de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , elle doit allouer des handles d’environnement et de connexion et se connecter à la source de données.</span><span class="sxs-lookup"><span data-stu-id="8a51d-103">For an ODBC application to communicate with an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], it must allocate environment and connection handles and connect to the data source.</span></span> <span data-ttu-id="8a51d-104">Après avoir établi une connexion, l'application peut envoyer des requêtes au serveur et traiter tous les jeux de résultats.</span><span class="sxs-lookup"><span data-stu-id="8a51d-104">After a connection is established, the application can send queries to the server and process any result sets.</span></span> <span data-ttu-id="8a51d-105">Lorsque l'application a terminé d'utiliser la source de données, elle se déconnecte de la source de données et libère le handle de connexion.</span><span class="sxs-lookup"><span data-stu-id="8a51d-105">When the application has finished using the data source, it disconnects from the data source and frees the connection handle.</span></span> <span data-ttu-id="8a51d-106">Lorsque l'application a libéré tous ses handles de connexion, elle libère le handle d'environnement.</span><span class="sxs-lookup"><span data-stu-id="8a51d-106">When the application has freed all its connection handles, it frees the environment handle.</span></span>  
  
 <span data-ttu-id="8a51d-107">Une application peut se connecter à un nombre quelconque de sources de données.</span><span class="sxs-lookup"><span data-stu-id="8a51d-107">An application can connect to any number of data sources.</span></span> <span data-ttu-id="8a51d-108">L'application peut utiliser une combinaison de pilotes et de sources de données, le même pilote et une combinaison de sources de données, voire le même pilote et plusieurs connexions à la même source de données.</span><span class="sxs-lookup"><span data-stu-id="8a51d-108">The application can use a combination of drivers and data sources, the same driver and a combination of data sources, or even the same driver and multiple connections to the same data source.</span></span>  
  
 <span data-ttu-id="8a51d-109">Vous pouvez télécharger [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] les exemples ODBC Native Client à partir de la page de [téléchargements de SQL Server](https://go.microsoft.com/fwlink/?LinkId=62796) sur MSDN.</span><span class="sxs-lookup"><span data-stu-id="8a51d-109">You can download [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC samples from the [SQL Server Downloads](https://go.microsoft.com/fwlink/?LinkId=62796) page on MSDN.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8a51d-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="8a51d-110">In This Section</span></span>  
  
-   [<span data-ttu-id="8a51d-111">Allocation d'un handle d'environnement</span><span class="sxs-lookup"><span data-stu-id="8a51d-111">Allocating an Environment Handle</span></span>](allocating-an-environment-handle.md)  
  
-   [<span data-ttu-id="8a51d-112">Allocation d'un handle de connexion</span><span class="sxs-lookup"><span data-stu-id="8a51d-112">Allocating a Connection Handle</span></span>](allocating-a-connection-handle.md)  
  
-   [<span data-ttu-id="8a51d-113">Sources de données ODBC SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="8a51d-113">SQL Server Native Client ODBC Data Sources</span></span>](../../integration-services/connection-manager/data-sources.md)  
  
-   [<span data-ttu-id="8a51d-114">Connexion à une source de données &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="8a51d-114">Connecting to a Data Source &#40;ODBC&#41;</span></span>](connecting-to-a-data-source-odbc.md)  
  
-   [<span data-ttu-id="8a51d-115">Déconnexion d'une source de données</span><span class="sxs-lookup"><span data-stu-id="8a51d-115">Disconnecting from a Data Source</span></span>](disconnecting-from-a-data-source.md)  
  
## <a name="see-also"></a><span data-ttu-id="8a51d-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8a51d-116">See Also</span></span>  
 <span data-ttu-id="8a51d-117">[SQL Server Native Client &#40;&#41;ODBC](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="8a51d-117">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="8a51d-118">SQLSetEnvAttr</span><span class="sxs-lookup"><span data-stu-id="8a51d-118">SQLSetEnvAttr</span></span>](../native-client-odbc-api/sqlsetenvattr.md)  
  
  
