---
title: Traitement des résultats de la procédure stockée | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC, stored procedures
- SQL Server Native Client ODBC driver, stored procedures
- stored procedures [ODBC], results
ms.assetid: 788ef2a4-17de-4526-960b-46bf29aafc9f
author: rothja
ms.author: jroth
ms.openlocfilehash: 5f37a6d8beff88748fa944293bd67f449d29eff2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709316"
---
# <a name="processing-stored-procedure-results"></a><span data-ttu-id="6ac0b-102">Traitement des résultats des procédures stockées</span><span class="sxs-lookup"><span data-stu-id="6ac0b-102">Processing Stored Procedure Results</span></span>
  <span data-ttu-id="6ac0b-103">Les procédures stockées [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilisent quatre mécanismes pour retourner les données :</span><span class="sxs-lookup"><span data-stu-id="6ac0b-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures have four mechanisms used to return data:</span></span>  
  
-   <span data-ttu-id="6ac0b-104">Chaque instruction SELECT de la procédure génère un jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="6ac0b-104">Each SELECT statement in the procedure generates a result set.</span></span>  
  
-   <span data-ttu-id="6ac0b-105">La procédure peut retourner des données par l'intermédiaire de paramètres de sortie.</span><span class="sxs-lookup"><span data-stu-id="6ac0b-105">The procedure can return data through output parameters.</span></span>  
  
-   <span data-ttu-id="6ac0b-106">Un paramètre de sortie de curseur peut retourner un curseur côté serveur [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6ac0b-106">A cursor output parameter can pass back a [!INCLUDE[tsql](../../includes/tsql-md.md)] server cursor.</span></span>  
  
-   <span data-ttu-id="6ac0b-107">La procédure peut avoir un code de retour de type entier.</span><span class="sxs-lookup"><span data-stu-id="6ac0b-107">The procedure can have an integer return code.</span></span>  
  
 <span data-ttu-id="6ac0b-108">Les applications doivent être en mesure de gérer toutes les sorties provenant des procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="6ac0b-108">Applications must be able to handle all these outputs from stored procedures.</span></span> <span data-ttu-id="6ac0b-109">L'instruction CALL ou EXECUTE doit inclure des marqueurs de paramètre pour le code de retour et les paramètres de sortie.</span><span class="sxs-lookup"><span data-stu-id="6ac0b-109">The CALL or EXECUTE statement should include parameter markers for the return code and output parameters.</span></span> <span data-ttu-id="6ac0b-110">Utilisez [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) pour les lier tous en tant que paramètres de sortie et le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client transférera les valeurs de sortie vers les variables liées.</span><span class="sxs-lookup"><span data-stu-id="6ac0b-110">Use [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) to bind them all as output parameters and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver will transfer the output values to the bound variables.</span></span> <span data-ttu-id="6ac0b-111">Les paramètres de sortie et les codes de retour sont les derniers éléments retournés au client par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ; ils ne sont pas retournés à l’application tant que [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) n’a pas retourné SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="6ac0b-111">Output parameters and return codes are the last items returned to the client by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]; they are not returned to the application until [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) returns SQL_NO_DATA.</span></span>  
  
 <span data-ttu-id="6ac0b-112">ODBC ne prend pas en charge la liaison des paramètres [!INCLUDE[tsql](../../includes/tsql-md.md)] de type cursor.</span><span class="sxs-lookup"><span data-stu-id="6ac0b-112">ODBC does not support binding [!INCLUDE[tsql](../../includes/tsql-md.md)] cursor parameters.</span></span> <span data-ttu-id="6ac0b-113">Comme tous les paramètres de sortie doivent être liés avant d'exécuter une procédure, toute procédure stockée [!INCLUDE[tsql](../../includes/tsql-md.md)] qui contient un paramètre de curseur de sortie ne peut pas être appelée par les applications ODBC.</span><span class="sxs-lookup"><span data-stu-id="6ac0b-113">Because all output parameters must be bound before executing a procedure, any [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure that contains an output cursor parameter cannot be called by ODBC applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ac0b-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6ac0b-114">See Also</span></span>  
 [<span data-ttu-id="6ac0b-115">Exécution de procédures stockées</span><span class="sxs-lookup"><span data-stu-id="6ac0b-115">Running Stored Procedures</span></span>](running-stored-procedures.md)  
  
  
