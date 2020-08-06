---
title: Messages d’erreur | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, errors
- messages [ODBC], types
- ODBC error handling, message types
- errors [ODBC], types
ms.assetid: 46c0c22e-d105-4d5b-bb9d-5694472e8651
author: rothja
ms.author: jroth
ms.openlocfilehash: d004ba320b50896b6f57c5de335d7f7b3d33e87a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706456"
---
# <a name="error-messages"></a><span data-ttu-id="5d93f-102">Messages d'erreur</span><span class="sxs-lookup"><span data-stu-id="5d93f-102">Error Messages</span></span>
  <span data-ttu-id="5d93f-103">Le texte des messages renvoyés par le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client est placé dans le paramètre *MessageText* de **SQLGetDiagRec**.</span><span class="sxs-lookup"><span data-stu-id="5d93f-103">The text of messages returned by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver is placed in the *MessageText* parameter of **SQLGetDiagRec**.</span></span> <span data-ttu-id="5d93f-104">La source d'une erreur est indiquée par l'en-tête du message :</span><span class="sxs-lookup"><span data-stu-id="5d93f-104">The source of an error is indicated by the header of the message:</span></span>  
  
 <span data-ttu-id="5d93f-105">[Microsoft][Gestionnaire de pilotes ODBC]</span><span class="sxs-lookup"><span data-stu-id="5d93f-105">[Microsoft][ODBC Driver Manager]</span></span>  
 <span data-ttu-id="5d93f-106">Ces erreurs sont déclenchées par le gestionnaire de pilotes ODBC.</span><span class="sxs-lookup"><span data-stu-id="5d93f-106">These errors are raised by the ODBC Driver Manager.</span></span>  
  
 <span data-ttu-id="5d93f-107">[Microsoft][Bibliothèque de curseurs ODBC]</span><span class="sxs-lookup"><span data-stu-id="5d93f-107">[Microsoft][ODBC Cursor Library]</span></span>  
 <span data-ttu-id="5d93f-108">Ces erreurs sont déclenchées par la bibliothèque de curseurs ODBC.</span><span class="sxs-lookup"><span data-stu-id="5d93f-108">These errors are raised by the ODBC cursor library.</span></span>  
  
 <span data-ttu-id="5d93f-109">[Microsoft][SQL Server Native Client]</span><span class="sxs-lookup"><span data-stu-id="5d93f-109">[Microsoft][SQL Server Native Client]</span></span>  
 <span data-ttu-id="5d93f-110">Ces erreurs sont déclenchées par le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client.</span><span class="sxs-lookup"><span data-stu-id="5d93f-110">These errors are raised by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="5d93f-111">S'il n'y a pas d'autres nœuds avec le nom d'une Net-Library ou [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], l'erreur s'est produite dans le pilote.</span><span class="sxs-lookup"><span data-stu-id="5d93f-111">If there are no other nodes with either the name of a Net-Library or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], then the error was encountered in the driver.</span></span>  
  
 <span data-ttu-id="5d93f-112">Librairie [SQL Server Native Client] [*Net-Transportname*]</span><span class="sxs-lookup"><span data-stu-id="5d93f-112">[Microsoft][SQL Server Native Client][*Net-Transportname*]</span></span>  
 <span data-ttu-id="5d93f-113">Ces erreurs sont générées par la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Net-Library, où *net-Transportname* est le nom d’affichage d’un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] transport réseau client (par exemple, canaux nommés, mémoire partagée, Sockets TCP/IP ou via).</span><span class="sxs-lookup"><span data-stu-id="5d93f-113">These errors are raised by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Net-Library, where *Net-Transportname* is the display name of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client network transport (for example, Named Pipes, Shared Memory, TCP/IP Sockets, or VIA).</span></span> <span data-ttu-id="5d93f-114">Le reste du message d'erreur contient la fonction Net-Library appelée et la fonction appelée dans l'API du réseau sous-jacent par la fonction TDS.</span><span class="sxs-lookup"><span data-stu-id="5d93f-114">The remainder of the error message contains the Net-Library function called and the function called in the underlying network API by the TDS function.</span></span> <span data-ttu-id="5d93f-115">Le code d’erreur *pfNative* retourné avec ces erreurs est le code d’erreur de la pile de protocoles réseau sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="5d93f-115">The *pfNative* error code returned with these errors is the error code from the underlying network protocol stack.</span></span>  
  
 <span data-ttu-id="5d93f-116">[Microsoft][SQL Server Native Client][[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]]</span><span class="sxs-lookup"><span data-stu-id="5d93f-116">[Microsoft][SQL Server Native Client][[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]]</span></span>  
 <span data-ttu-id="5d93f-117">Ces erreurs sont déclenchées par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d93f-117">These errors are raised by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5d93f-118">Le reste du message d'erreur est le texte du message d'erreur de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d93f-118">The remainder of the error message is the text of the error message from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5d93f-119">Le code *pfNative* retourné avec ces erreurs est le numéro d’erreur de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5d93f-119">The *pfNative* code returned with these errors is the error number from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5d93f-120">Pour plus d’informations sur la liste des messages d’erreur (et leurs numéros) qui peuvent être retournés par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consultez les colonnes Description et erreur de la table système **sysmessages** dans la base de données **Master** dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5d93f-120">For more information about a list of error messages (and their numbers) that can be returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see the description and error columns of the **sysmessages** system table in the **master** database in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d93f-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5d93f-121">See Also</span></span>  
 [<span data-ttu-id="5d93f-122">Gestion des erreurs et des messages</span><span class="sxs-lookup"><span data-stu-id="5d93f-122">Handling Errors and Messages</span></span>](handling-errors-and-messages.md)  
  
  
