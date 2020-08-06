---
title: Exécution d’une commande | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- commands [SQL Server Native Client]
- OLE DB, executing commands
- sessions [SQL Server Native Client]
- OLE DB extensions for XML
- SQL Server Native Client OLE DB provider, command execution
ms.assetid: bb0b3cbf-fe45-46ba-b2ec-c5a39e3c7081
author: rothja
ms.author: jroth
ms.openlocfilehash: 41e8da036d5a4b6469a31213247ad7d4edb7dbfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612786"
---
# <a name="executing-a-command"></a><span data-ttu-id="f45f4-102">Exécution d'une commande</span><span class="sxs-lookup"><span data-stu-id="f45f4-102">Executing a Command</span></span>
  <span data-ttu-id="f45f4-103">Une fois la connexion à une source de données établie, le consommateur appelle la méthode **IDBCreateSession::CreateSession** pour créer une session.</span><span class="sxs-lookup"><span data-stu-id="f45f4-103">After the connection to a data source is established, the consumer calls the **IDBCreateSession::CreateSession** method to create a session.</span></span> <span data-ttu-id="f45f4-104">La session agit en guise de commande, d'ensemble de lignes ou de fabrique de transactions.</span><span class="sxs-lookup"><span data-stu-id="f45f4-104">The session acts as a command, rowset, or transaction factory.</span></span>  
  
 <span data-ttu-id="f45f4-105">Pour utiliser directement des tables individuelles ou des index, le consommateur demande l'interface `IOpenRowset`.</span><span class="sxs-lookup"><span data-stu-id="f45f4-105">To work directly with individual tables or indexes, the consumer requests the `IOpenRowset` interface.</span></span> <span data-ttu-id="f45f4-106">La méthode `IOpenRowset::OpenRowset` ouvre et retourne un ensemble de lignes qui inclut toutes les lignes d'une table de base ou d'un index unique.</span><span class="sxs-lookup"><span data-stu-id="f45f4-106">The `IOpenRowset::OpenRowset` method opens and returns a rowset that includes all rows from a single base table or index.</span></span>  
  
 <span data-ttu-id="f45f4-107">Pour exécuter une commande (telle que SELECT \* from Authors), le consommateur demande l' `IDBCreateCommand` interface.</span><span class="sxs-lookup"><span data-stu-id="f45f4-107">To execute a command (such as SELECT \* FROM Authors), the consumer requests the `IDBCreateCommand` interface.</span></span> <span data-ttu-id="f45f4-108">Le consommateur peut exécuter la méthode `IDBCreateCommand::CreateCommand` pour créer un objet de commande et demander l'interface `ICommandText`.</span><span class="sxs-lookup"><span data-stu-id="f45f4-108">The consumer can execute the `IDBCreateCommand::CreateCommand` method to create a command object and request for the `ICommandText` interface.</span></span> <span data-ttu-id="f45f4-109">La méthode `ICommandText::SetCommandText` est utilisée pour spécifier la commande à exécuter.</span><span class="sxs-lookup"><span data-stu-id="f45f4-109">The `ICommandText::SetCommandText` method is used to specify the command that is to be executed.</span></span>  
  
 <span data-ttu-id="f45f4-110">La commande `Execute` permet d'exécuter la commande.</span><span class="sxs-lookup"><span data-stu-id="f45f4-110">The `Execute` command is used to execute the command.</span></span> <span data-ttu-id="f45f4-111">La commande peut être un nom de procédure ou une instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="f45f4-111">The command can be any SQL statement or procedure name.</span></span> <span data-ttu-id="f45f4-112">Toutes les commandes ne génèrent pas un objet de jeu de résultats (ensemble de lignes).</span><span class="sxs-lookup"><span data-stu-id="f45f4-112">Not all commands produce a result set (rowset) object.</span></span> <span data-ttu-id="f45f4-113">Les commandes, telles que SELECT \* FROM Authors, produisent un jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="f45f4-113">Commands such as SELECT \* FROM Authors produce a result set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f45f4-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f45f4-114">See Also</span></span>  
 [<span data-ttu-id="f45f4-115">Création d'une application de fournisseur OLE DB de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="f45f4-115">Creating a SQL Server Native Client OLE DB Provider Application</span></span>](creating-a-sql-server-native-client-ole-db-provider-application.md)  
  
  
