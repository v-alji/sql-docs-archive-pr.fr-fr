---
title: Utilisation des curseurs côté serveur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC applications, cursors
- cursors [ODBC], server cursors
- ODBC cursors, server cursors
- server cursors [SQL Server]
ms.assetid: 8a6d99b7-10b8-4474-8639-4914b25ba170
author: rothja
ms.author: jroth
ms.openlocfilehash: e596af3c46849313d813ce2d7f1dab2a7425c090
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603515"
---
# <a name="using-server-cursors"></a><span data-ttu-id="ed798-102">Utilisation des curseurs côté serveur</span><span class="sxs-lookup"><span data-stu-id="ed798-102">Using Server Cursors</span></span>
  <span data-ttu-id="ed798-103">Si une application ODBC définit l’un des attributs de curseur ODBC sur une valeur autre que les valeurs par défaut, le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pilote ODBC native client demande au serveur d’implémenter un curseur côté serveur d’API du même type.</span><span class="sxs-lookup"><span data-stu-id="ed798-103">If an ODBC application sets any of the ODBC cursor attributes to anything other than the defaults, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver requests the server to implement an API server cursor of the same type.</span></span> <span data-ttu-id="ed798-104">L'utilisation de curseurs côté serveur d'API libère la mémoire sur le client et peut réduire considérablement le trafic réseau entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="ed798-104">Using API server cursors frees memory on the client and can significantly reduce network traffic between the client and server.</span></span>  
  
 <span data-ttu-id="ed798-105">Un inconvénient possible des curseurs côté serveur d'API est qu'ils ne prennent pas en charge toutes les instructions SQL.</span><span class="sxs-lookup"><span data-stu-id="ed798-105">A potential drawback of API server cursors is that they currently do not support all SQL statements.</span></span> <span data-ttu-id="ed798-106">Les curseurs côté serveur d'API ne peuvent pas être utilisés pour exécuter :</span><span class="sxs-lookup"><span data-stu-id="ed798-106">API server cursors cannot be used to execute:</span></span>  
  
-   <span data-ttu-id="ed798-107">Les lots ou les procédures stockées qui retournent plusieurs ensembles de résultats.</span><span class="sxs-lookup"><span data-stu-id="ed798-107">Batches or stored procedures that return multiple result sets.</span></span>  
  
-   <span data-ttu-id="ed798-108">Les instructions SELECT contenant les clauses COMPUTE, COMPUTE BY, FOR BROWSE ou INTO.</span><span class="sxs-lookup"><span data-stu-id="ed798-108">SELECT statements that contain COMPUTE, COMPUTE BY, FOR BROWSE, or INTO clauses.</span></span>  
  
-   <span data-ttu-id="ed798-109">Une instruction EXECUTE faisant référence à une procédure stockée distante.</span><span class="sxs-lookup"><span data-stu-id="ed798-109">An EXECUTE statement referencing a remote stored procedure.</span></span>  
  
 <span data-ttu-id="ed798-110">En cas de connexion à une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], l'exécution d'une instruction avec ces caractéristiques à l'aide d'un curseur côté serveur provoque la conversion du curseur en un jeu de résultats par défaut.</span><span class="sxs-lookup"><span data-stu-id="ed798-110">When connected to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], executing a statement with these characteristics using a server cursor causes the cursor being converted to a default result set.</span></span> <span data-ttu-id="ed798-111">En cas de connexion aux versions antérieures de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], il s'ensuit une erreur.</span><span class="sxs-lookup"><span data-stu-id="ed798-111">When connected to earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], it causes an error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed798-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ed798-112">See Also</span></span>  
 [<span data-ttu-id="ed798-113">Comment les curseurs sont implémentés</span><span class="sxs-lookup"><span data-stu-id="ed798-113">How Cursors Are Implemented</span></span>](how-cursors-are-implemented.md)  
  
  
