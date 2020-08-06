---
title: Traitement par lot des appels de procédure stockée | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- stored procedures [ODBC], batching
- ODBC, stored procedures
- SQL Server Native Client ODBC driver, stored procedures
- batches [ODBC]
- ODBC CALL escape sequence
ms.assetid: b7f53e11-15f0-4602-8134-b166160888f0
author: rothja
ms.author: jroth
ms.openlocfilehash: a0df58ce59853ee15b863cbc7bce34041c37fee4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709324"
---
# <a name="batching-stored-procedure-calls"></a><span data-ttu-id="b080e-102">Traitement par lot des appels aux procédures stockées</span><span class="sxs-lookup"><span data-stu-id="b080e-102">Batching Stored Procedure Calls</span></span>
  <span data-ttu-id="b080e-103">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client regroupe automatiquement les appels de procédure stockée au serveur, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="b080e-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver automatically batches stored procedure calls to the server when appropriate.</span></span> <span data-ttu-id="b080e-104">Il le fait uniquement en cas d'utilisation de la séquence d'échappement ODBC CALL ; il ne le fait pas pour l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="b080e-104">The driver only does this when the ODBC CALL escape sequence is used; it does not do this for the [!INCLUDE[tsql](../../includes/tsql-md.md)] EXECUTE statement.</span></span> <span data-ttu-id="b080e-105">Le traitement par lot des appels aux procédures stockées peut réduire le nombre de boucles sur le serveur et augmenter considérablement les performances.</span><span class="sxs-lookup"><span data-stu-id="b080e-105">Batching stored procedure calls can reduce the number of round trips to the server and significantly increase performance.</span></span>  
  
 <span data-ttu-id="b080e-106">Le pilote traite par lot les appels de procédure sur le serveur lorsque vous exécutez un lot qui contient plusieurs séquences d'échappement ODBC CALL.</span><span class="sxs-lookup"><span data-stu-id="b080e-106">The driver batches procedure calls to the server when you execute a batch that contains multiple ODBC CALL escape sequences.</span></span> <span data-ttu-id="b080e-107">Il traite également par lot les appels de procédure lorsque vous utilisez des tableaux de paramètres liés dans une séquence d'échappement ODBC CALL.</span><span class="sxs-lookup"><span data-stu-id="b080e-107">It also batches procedure calls when bound parameter arrays are used with an ODBC CALL escape sequence.</span></span> <span data-ttu-id="b080e-108">Par exemple, si vous utilisez une liaison de paramètre selon les lignes ou les colonnes pour lier un tableau avec cinq éléments aux paramètres d’une instruction ODBC CALL SQL, lorsque **SQLExecute** ou **SQLExecDirect** est appelé, le pilote envoie un seul lot avec cinq appels de procédure au serveur.</span><span class="sxs-lookup"><span data-stu-id="b080e-108">For example, if you use either row-wise or column-wise parameter binding to bind an array with five elements to the parameters of an ODBC CALL SQL statement, when **SQLExecute** or **SQLExecDirect** is called, the driver sends a single batch with five procedure calls to the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b080e-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b080e-109">See Also</span></span>  
 [<span data-ttu-id="b080e-110">Exécution de procédures stockées</span><span class="sxs-lookup"><span data-stu-id="b080e-110">Running Stored Procedures</span></span>](running-stored-procedures.md)  
  
  
