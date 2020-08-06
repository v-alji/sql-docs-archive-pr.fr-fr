---
title: Rubriques de procédures relatives à ODBC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 151f2066-1c37-410f-88f4-b27dfca66031
author: rothja
ms.author: jroth
ms.openlocfilehash: cfeb120b9fa1fedb5358b5e12dabed7835f9a6b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706447"
---
# <a name="odbc-how-to-topics"></a><span data-ttu-id="c166a-102">Rubriques de procédures ODBC</span><span class="sxs-lookup"><span data-stu-id="c166a-102">ODBC How-to Topics</span></span>
  <span data-ttu-id="c166a-103">Pour utiliser le pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vous devez être en mesure de créer des sources de données ODBC et de vous assurer que le serveur a la version correcte des procédures stockées de catalogue.</span><span class="sxs-lookup"><span data-stu-id="c166a-103">To use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC driver, you must be able to create ODBC data sources and ensure that the server has the correct version of the catalog stored procedures.</span></span> <span data-ttu-id="c166a-104">Pour coder une application ODBC qui utilise SQL Server, vous devez savoir comment allouer des handles ODBC, définir des attributs, vous connecter à une instance de SQL Server, exécuter des requêtes et traiter les résultats.</span><span class="sxs-lookup"><span data-stu-id="c166a-104">To code an ODBC application that uses SQL Server, you must know how to allocate ODBC handles, set attributes, connect to an instance of SQL Server, execute queries, and process results.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c166a-105">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="c166a-105">In This Section</span></span>  
  
-   [<span data-ttu-id="c166a-106">Rubriques des procédures relatives à la configuration du pilote ODBC SQL Server</span><span class="sxs-lookup"><span data-stu-id="c166a-106">Configuring the SQL Server ODBC Driver How-to Topics</span></span>](../../database-engine/dev-guide/configuring-the-sql-server-odbc-driver-how-to-topics.md)  
  
-   [<span data-ttu-id="c166a-107">Allouez des descripteurs et connectez-vous à SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="c166a-107">Allocate Handles and Connect to SQL Server &#40;ODBC&#41;</span></span>](allocate-handles-and-connect-to-sql-server-odbc.md)  
  
-   [<span data-ttu-id="c166a-108">Rubriques de procédures relatives à l’exécution de requêtes &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="c166a-108">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](execute-queries/executing-queries-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="c166a-109">Rubriques de procédures relatives au traitement des résultats &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="c166a-109">Processing Results How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="c166a-110">Rubriques de procédures relatives à l’utilisation des curseurs &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="c166a-110">Using Cursors How-to Topics &#40;ODBC&#41;</span></span>](cursors/using-cursors-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="c166a-111">Utiliser Microsoft Distributed Transaction Coordinator &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="c166a-111">Use Microsoft Distributed Transaction Coordinator &#40;ODBC&#41;</span></span>](use-microsoft-distributed-transaction-coordinator-odbc.md)  
  
-   [<span data-ttu-id="c166a-112">Rubriques de procédures relatives à l’exécution de procédures stockées &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="c166a-112">Running Stored Procedures How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/running-stored-procedures-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="c166a-113">Rubriques de procédures relatives à la gestion des colonnes de texte et d’image &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="c166a-113">Managing text and image Columns How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/managing-text-and-image-columns-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="c166a-114">Rubriques de procédures relatives au profilage des performances du pilote ODBC &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="c166a-114">Profiling ODBC Driver Performance How-to Topics &#40;ODBC&#41;</span></span>](profiling-odbc-driver-performance-odbc.md)  
  
-   [<span data-ttu-id="c166a-115">Traiter les erreurs ODBC &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="c166a-115">Process ODBC Errors &#40;ODBC&#41;</span></span>](process-odbc-errors-odbc.md)  
  
-   [<span data-ttu-id="c166a-116">Rubriques de procédures relatives à la copie en bloc avec le SQL Server ODBC Driver &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="c166a-116">Bulk Copying with the SQL Server ODBC Driver How-to Topics &#40;ODBC&#41;</span></span>](bulk-copy/bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md)  
  
## <a name="see-also"></a><span data-ttu-id="c166a-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c166a-117">See Also</span></span>  
 [<span data-ttu-id="c166a-118">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="c166a-118">SQL Server Native Client &#40;ODBC&#41;</span></span>](../native-client/odbc/sql-server-native-client-odbc.md)  
  
  
