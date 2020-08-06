---
title: Prise en charge SQL Server Native Client pour la base de données locale | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 127569d1-a9f7-49bf-a561-c084986a8871
author: rothja
ms.author: jroth
ms.openlocfilehash: b08ea46e8db1b665280116a439b95748f69d03ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602810"
---
# <a name="sql-server-native-client-support-for-localdb"></a><span data-ttu-id="da894-102">Prise en charge de SQL Server Native Client pour LocalDB</span><span class="sxs-lookup"><span data-stu-id="da894-102">SQL Server Native Client Support for LocalDB</span></span>
  <span data-ttu-id="da894-103">À compter de [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], une version légère de SQL Server, appelée LocalDB, sera disponible.</span><span class="sxs-lookup"><span data-stu-id="da894-103">Beginning in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], a lightweight version of SQL Server, called LocalDB, will be available.</span></span> <span data-ttu-id="da894-104">Cette rubrique explique comment se connecter à une base de données dans une instance LocalDB.</span><span class="sxs-lookup"><span data-stu-id="da894-104">This topic discusses how to connect to a database in a LocalDB instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da894-105">Notes</span><span class="sxs-lookup"><span data-stu-id="da894-105">Remarks</span></span>  
 <span data-ttu-id="da894-106">Pour plus d'informations sur LocalDB, notamment comment installer LocalDB et configurer votre instance LocalDB, consultez :</span><span class="sxs-lookup"><span data-stu-id="da894-106">For more information about LocalDB, including how to install LocalDB and configure your LocalDB instance, see:</span></span>  
  
-   [<span data-ttu-id="da894-107">Référence SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="da894-107">SQL Server Express LocalDB Reference</span></span>](../../sql-server-express-localdb-reference.md)  
  
-   [<span data-ttu-id="da894-108">SQL Server 2014 Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="da894-108">SQL Server 2014 Express LocalDB</span></span>](../../../database-engine/configure-windows/sql-server-2016-express-localdb.md)  
  
 <span data-ttu-id="da894-109">Pour résumer, LocalDB vous permet d'effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="da894-109">To summarize, LocalDB allows you to:</span></span>  
  
-   <span data-ttu-id="da894-110">Utiliser `sqllocaldb.exe i` pour déterminer le nom de l'instance par défaut.</span><span class="sxs-lookup"><span data-stu-id="da894-110">Use `sqllocaldb.exe i` to discover the name of the default instance.</span></span>  
  
-   <span data-ttu-id="da894-111">Utiliser le mot clé de chaîne de connexion `AttachDBFilename` pour spécifier le fichier de base de données auquel le serveur doit se rattacher.</span><span class="sxs-lookup"><span data-stu-id="da894-111">Use the `AttachDBFilename` connection string keyword to specify which database file the server should attach.</span></span> <span data-ttu-id="da894-112">Lorsque `AttachDBFilename` vous utilisez, si vous ne spécifiez pas le nom de la base de données avec le mot clé **de chaîne de connexion de base de données** , la base de données est supprimée de l’instance de base de données locale lorsque l’application se ferme.</span><span class="sxs-lookup"><span data-stu-id="da894-112">When using `AttachDBFilename`, if you do not specify the name of the database with the **Database** connection string keyword, the database will be removed from the LocalDB instance when the application closes.</span></span>  
  
-   <span data-ttu-id="da894-113">Spécifiez une instance LocalDB dans votre chaîne de connexion :</span><span class="sxs-lookup"><span data-stu-id="da894-113">Specify a LocalDB instance in your connection string:</span></span>  
  
```  
SERVER=(localdb)\v11.0  
```  
  
 <span data-ttu-id="da894-114">Si nécessaire, vous pouvez créer une instance LocalDB avec sqllocaldb.exe.</span><span class="sxs-lookup"><span data-stu-id="da894-114">If necessary, you can create a LocalDB instance with sqllocaldb.exe.</span></span> <span data-ttu-id="da894-115">Vous pouvez également utiliser sqlcmd.exe pour ajouter et modifier des bases de données dans une instance LocalDB.</span><span class="sxs-lookup"><span data-stu-id="da894-115">You can also use sqlcmd.exe to add and modify databases in a LocalDB instance.</span></span> <span data-ttu-id="da894-116">Par exemple : `sqlcmd -S (localdb)\v11.0`.</span><span class="sxs-lookup"><span data-stu-id="da894-116">For example, `sqlcmd -S (localdb)\v11.0`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da894-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="da894-117">See Also</span></span>  
 [<span data-ttu-id="da894-118">Fonctionnalités de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="da894-118">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
