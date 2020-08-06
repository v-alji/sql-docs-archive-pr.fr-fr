---
title: Connexion contextuelle | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- context connections [CLR integration]
- database objects [CLR integration], connections
- connections [CLR integration]
- context [CLR integration]
ms.assetid: 67dd1925-d672-4986-a85f-bce4fe832ef7
author: rothja
ms.author: jroth
ms.openlocfilehash: 82c739aa9c1952c71e9a16aaa68ec999851b3202
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604568"
---
# <a name="context-connection"></a><span data-ttu-id="a2455-102">Connexion contextuelle</span><span class="sxs-lookup"><span data-stu-id="a2455-102">Context Connection</span></span>
  <span data-ttu-id="a2455-103">Le problème d'accès aux données interne est un scénario relativement courant.</span><span class="sxs-lookup"><span data-stu-id="a2455-103">The problem of internal data access is a fairly common scenario.</span></span> <span data-ttu-id="a2455-104">Autrement dit, vous souhaitez accéder au même serveur que celui sur lequel votre fonction ou procédure stockée CLR s'exécute.</span><span class="sxs-lookup"><span data-stu-id="a2455-104">That is, you wish to access the same server on which your common language runtime (CLR) stored procedure or function is executing.</span></span> <span data-ttu-id="a2455-105">Une option consiste à créer une connexion à l'aide de `System.Data.SqlClient.SqlConnection`, en spécifiant une chaîne de connexion qui pointe sur le serveur local, et à ouvrir la connexion.</span><span class="sxs-lookup"><span data-stu-id="a2455-105">One option is to create a connection using `System.Data.SqlClient.SqlConnection`, specify a connection string that points to the local server, and open the connection.</span></span> <span data-ttu-id="a2455-106">Cela requiert la spécification d'informations d'identification pour se connecter.</span><span class="sxs-lookup"><span data-stu-id="a2455-106">This requires specifying credentials for logging in.</span></span> <span data-ttu-id="a2455-107">La connexion se trouve dans une autre session de base de données que la procédure stockée ou la fonction, elle peut avoir des options `SET` différentes, elle figure dans une transaction distincte, elle ne consulte pas vos tables temporaires, et ainsi de suite</span><span class="sxs-lookup"><span data-stu-id="a2455-107">The connection is in a different database session than the stored procedure or function, it may have different `SET` options, it is in a separate transaction, it does not see your temporary tables, and so on.</span></span> <span data-ttu-id="a2455-108">Si le code de votre procédure stockée managée ou de votre fonction exécute dans le processus SQL Server, la raison en est que quelqu'un s'est connecté à ce serveur et a exécuté une instruction SQL pour l'appeler.</span><span class="sxs-lookup"><span data-stu-id="a2455-108">If your managed stored procedure or function code is executing in the SQL Server process, it is because someone connected to that server and executed a SQL statement to invoke it.</span></span> <span data-ttu-id="a2455-109">Vous souhaitez probablement que la procédure stockée ou la fonction s'exécute dans le contexte de cette connexion, avec sa transaction, ses options `SET`, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="a2455-109">You probably want the stored procedure or function to execute in the context of that connection, along with its transaction, `SET` options, and so on.</span></span> <span data-ttu-id="a2455-110">Une telle connexion est appelée connexion du contexte, ou connexion contextuelle.</span><span class="sxs-lookup"><span data-stu-id="a2455-110">This is called the context connection.</span></span>  
  
 <span data-ttu-id="a2455-111">La connexion contextuelle permet d'exécuter des instructions Transact-SQL dans le même contexte que celui où votre code a été appelé en premier lieu.</span><span class="sxs-lookup"><span data-stu-id="a2455-111">The context connection lets you execute Transact-SQL statements in the same context that your code was invoked in the first place.</span></span> <span data-ttu-id="a2455-112">Pour obtenir la connexion contextuelle, vous devez utiliser le mot clé "context connection" de la chaîne de connexion, comme dans l'exemple ci-après :</span><span class="sxs-lookup"><span data-stu-id="a2455-112">In order to obtain the context connection, you must use the "context connection" connection string keyword, as in the example below:</span></span>  
  
 <span data-ttu-id="a2455-113">[C#]</span><span class="sxs-lookup"><span data-stu-id="a2455-113">[C#]</span></span>  
  
```  
using(SqlConnection connection = new SqlConnection("context connection=true"))   
{  
    connection.Open();  
    // Use the connection  
}  
```  
  
 <span data-ttu-id="a2455-114">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="a2455-114">[Visual Basic]</span></span>  
  
```  
Using connection as new SqlConnection("context connection=true")  
    connection.Open()  
    ' Use the connection  
End Using  
  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="a2455-115">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="a2455-115">In This Section</span></span>  
 [<span data-ttu-id="a2455-116">Connexions normales et Connexions contextuelles</span><span class="sxs-lookup"><span data-stu-id="a2455-116">Regular vs. Context Connections</span></span>](context-connections-vs-regular-connections.md)  
 <span data-ttu-id="a2455-117">Décrit les différences entre les connexions régulières et les connexions contextuelles.</span><span class="sxs-lookup"><span data-stu-id="a2455-117">Describes the differences between regular and context connections.</span></span>  
  
 [<span data-ttu-id="a2455-118">Restrictions applicables aux connexions normales et contextuelles</span><span class="sxs-lookup"><span data-stu-id="a2455-118">Restrictions on Regular and Context Connections</span></span>](context-connections-and-regular-connections-restrictions.md)  
 <span data-ttu-id="a2455-119">Décrit les restrictions sur les connexions régulières et les connexions contextuelles.</span><span class="sxs-lookup"><span data-stu-id="a2455-119">Describes the restrictions on regular and context connections.</span></span>  
  
  
