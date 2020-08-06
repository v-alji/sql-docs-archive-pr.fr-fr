---
title: Représentation de la base de données (tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 16a233fb-f83b-4ca1-acb5-6186eca0a62c
author: minewiskan
ms.author: owend
ms.openlocfilehash: c327e07685e98e6fa9f992025510e869d909e5ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603679"
---
# <a name="database-representationtabular"></a><span data-ttu-id="33857-102">Représentation de la base de données (tabulaire)</span><span class="sxs-lookup"><span data-stu-id="33857-102">Database Representation(Tabular)</span></span>
  <span data-ttu-id="33857-103">En mode tabulaire, la base de données est le conteneur de tous les objets dans le modèle tabulaire.</span><span class="sxs-lookup"><span data-stu-id="33857-103">In Tabular Mode, the database is the container for all objects in the tabular model.</span></span>  
  
## <a name="database-representation"></a><span data-ttu-id="33857-104">Représentation de la base de données</span><span class="sxs-lookup"><span data-stu-id="33857-104">Database Representation</span></span>  
 <span data-ttu-id="33857-105">La base de données est l'emplacement où tous les objets qui forment un modèle tabulaire résident.</span><span class="sxs-lookup"><span data-stu-id="33857-105">The database is the place where all objects that form a tabular model reside.</span></span> <span data-ttu-id="33857-106">À l'intérieur de la base de données le développeur trouve des objets tels que des connexions, des tables, des rôles et bien plus.</span><span class="sxs-lookup"><span data-stu-id="33857-106">Contained by the database, the developer finds objects like connections, tables, roles and many more.</span></span>  
  
### <a name="database-in-amo"></a><span data-ttu-id="33857-107">Base de données dans AMO</span><span class="sxs-lookup"><span data-stu-id="33857-107">Database in AMO</span></span>  
 <span data-ttu-id="33857-108">Lorsque vous utilisez AMO pour gérer une base de données de modèle tabulaire, l'objet <xref:Microsoft.AnalysisServices.Database> dans AMO a une correspondance un-à-un avec l'objet logique de base de données dans un modèle tabulaire.</span><span class="sxs-lookup"><span data-stu-id="33857-108">When using AMO to manage a tabular model database, the <xref:Microsoft.AnalysisServices.Database> object in AMO matches one-to-one the database logical object in a tabular model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="33857-109">Pour accéder à un objet de base de données, dans AMO, l'utilisateur a besoin d'avoir accès à un objet serveur et de se connecter à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="33857-109">In order to gain access to a database object, in AMO, the user needs to have access to a server object and connect to it.</span></span>  
  
### <a name="database-in-adomdnet"></a><span data-ttu-id="33857-110">Base de données dans ADOMD.Net</span><span class="sxs-lookup"><span data-stu-id="33857-110">Database in ADOMD.Net</span></span>  
 <span data-ttu-id="33857-111">Lorsque vous utilisez ADOMD pour consulter et interroger une base de données de modèle tabulaire, la connexion à une base de données spécifique est obtenue par l'objet <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection>.</span><span class="sxs-lookup"><span data-stu-id="33857-111">When using ADOMD to consult and query a tabular model database, connection to a specific database is obtained through the <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection> object.</span></span>  
  
 <span data-ttu-id="33857-112">Connectez-vous directement à une certaine base de données à l'aide de l'extrait de code suivant :</span><span class="sxs-lookup"><span data-stu-id="33857-112">You can connect directly to a certain database using the following code snippet:</span></span>  
  
```csharp  
using ADOMD = Microsoft.AnalysisServices.AdomdClient;  
...  
   ADOMD.AdomdConnection currrentCnx = new ADOMD.AdomdConnection("Data Source=<<server\instance>>;Catalog=<<database>>");  
   currrentCnx.Open();  
...  
  
```  
  
 <span data-ttu-id="33857-113">En outre, sur un objet de connexion existant (qui n'a pas été fermé), remplacez la base de données active par une autre comme indiqué dans l'extrait de code suivant :</span><span class="sxs-lookup"><span data-stu-id="33857-113">Also, over an existing connection object (that hasn't been closed), you can change the current database to another as shown in the following code snippet:</span></span>  
  
```csharp  
currentCnx.ChangeDatabase("myOtherDatabase");  
  
```  
  
## <a name="database-in-amo"></a><span data-ttu-id="33857-114">Base de données dans AMO</span><span class="sxs-lookup"><span data-stu-id="33857-114">Database in AMO</span></span>  
 <span data-ttu-id="33857-115">Lorsque vous utilisez AMO pour gérer un objet de base de données, commencez par un objet <xref:Microsoft.AnalysisServices.Server>.</span><span class="sxs-lookup"><span data-stu-id="33857-115">When using AMO to manage a database object, start with a <xref:Microsoft.AnalysisServices.Server> object.</span></span> <span data-ttu-id="33857-116">Puis, recherchez votre base de données dans la collection de bases de données, ou créez une nouvelle base de données et ajoutez-la à la collection.</span><span class="sxs-lookup"><span data-stu-id="33857-116">Then search for your database in the databases collection or create a new database by adding one to the collection.</span></span>  
  
 <span data-ttu-id="33857-117">L’extrait de code suivant montre les étapes permettant de se connecter à un serveur et de créer une base de données vide, après avoir vérifié que la base de données n’existe pas :</span><span class="sxs-lookup"><span data-stu-id="33857-117">The following code snippet shows the steps to connect to a server and create an empty database, after checking the database doesn't exist:</span></span>  
  
```  
  
AMO.Server CurrentServer = new AMO.Server();  
try  
{  
    CurrentServer.Connect(currentServerName);  
}  
catch (Exception cnxException)  
{  
    MessageBox.Show(string.Format("Error while trying to connect to server: [{0}]\nError message: {1}", currentServerName, cnxException.Message), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
    return;  
}  
newDatabaseName = DatabaseName.Text;  
if (CurrentServer.Databases.Contains(newDatabaseName))  
{  
    return;  
}  
try  
{  
    AMO.Database newDatabase = CurrentServer.Databases.Add(newDatabaseName);  
  
    CurrentServer.Update();  
}  
catch (Exception createDBxc)  
{  
    MessageBox.Show(String.Format("Database [{0}] couldn't be created.\n{1}", newDatabaseName, createDBxc.Message), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
    newDatabaseAvailable = false;  
}  
  
```  
  
 <span data-ttu-id="33857-118">Pour savoir comment utiliser AMO pour créer et manipuler des représentations de base de données, consultez le code source de l'exemple AMO 2012 tabulaire ; plus précisément, archivez le fichier source suivant : Database.cs.</span><span class="sxs-lookup"><span data-stu-id="33857-118">For a practical understanding on how to use AMO to create and manipulate database representations, see source code in the Tabular AMO 2012 sample; specifically check in the following source file: Database.cs.</span></span> <span data-ttu-id="33857-119">Le code est fourni uniquement comme un support aux concepts logiques expliqués ici et ne doit pas être utilisé dans un environnement de production, ni à des fins autres que pédagogiques.</span><span class="sxs-lookup"><span data-stu-id="33857-119">Sample code is provided only as a support to the logical concepts explained here, and should not be used in a production environment.</span></span>  
  
  
