---
title: Numéros des erreurs natives | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC error handling, native error numbers
- SQL Server Native Client ODBC driver, errors
- native error numbers [SQL Server Native Client]
- messages [ODBC], native error numbers
- errors [ODBC], native error numbers
ms.assetid: 77cbc826-f47f-4803-8e7a-223d6df069b1
author: rothja
ms.author: jroth
ms.openlocfilehash: 7232a921027246c3ceb7d0ae1ffd5efbd3672895
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698178"
---
# <a name="native-error-numbers"></a><span data-ttu-id="59992-102">Numéros des erreurs natives</span><span class="sxs-lookup"><span data-stu-id="59992-102">Native Error Numbers</span></span>
  <span data-ttu-id="59992-103">Pour les erreurs qui se produisent dans la source de données (retournée par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ), le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client retourne le numéro d’erreur natif retourné par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="59992-103">For errors that occur in the data source (returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]), the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns the native error number returned to it by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="59992-104">Pour les erreurs détectées par le pilote, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client retourne le numéro d’erreur natif 0.</span><span class="sxs-lookup"><span data-stu-id="59992-104">For errors detected by the driver, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns a native error number of 0.</span></span> <span data-ttu-id="59992-105">Pour plus d’informations sur la liste des numéros d’erreur natifs, consultez la colonne erreur de la table système **sysmessages** dans la base de données **Master** dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="59992-105">For more information about a list of native error numbers, see the error column of the **sysmessages** system table in the **master** database in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="59992-106">Pour plus d’informations sur les codes d’erreur d’État, consultez [SQLSTATE &#40;codes d’erreur ODBC&#41;](sqlstate-odbc-error-codes.md).</span><span class="sxs-lookup"><span data-stu-id="59992-106">For information about the state error codes, see [SQLSTATE &#40;ODBC Error Codes&#41;](sqlstate-odbc-error-codes.md).</span></span> <span data-ttu-id="59992-107">Pour les erreurs retournées par le Net-Library, le numéro d'erreur natif provient du logiciel réseau sous-jacent.</span><span class="sxs-lookup"><span data-stu-id="59992-107">For errors returned by the Net-Library, the native error number is from the underlying network software.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59992-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="59992-108">See Also</span></span>  
 [<span data-ttu-id="59992-109">Gestion des erreurs et des messages</span><span class="sxs-lookup"><span data-stu-id="59992-109">Handling Errors and Messages</span></span>](handling-errors-and-messages.md)  
  
  
