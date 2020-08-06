---
title: Allocation d’un handle d’environnement | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, environment handles
- ODBC applications, connections
- handles [SQL Server Native Client]
- environment handles [SQLNCLI]
ms.assetid: 15c1b428-ea6d-4672-894c-f0e289e2da3f
author: rothja
ms.author: jroth
ms.openlocfilehash: 1c655b5e9a406c3e1881c9dd199a92666377918f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611057"
---
# <a name="allocating-an-environment-handle"></a><span data-ttu-id="e6575-102">Allocation d'un handle d'environnement</span><span class="sxs-lookup"><span data-stu-id="e6575-102">Allocating an Environment Handle</span></span>
  <span data-ttu-id="e6575-103">Avant qu'une application puisse appeler toute fonction ODBC, elle doit initialiser l'environnement ODBC et allouer un handle d'environnement.</span><span class="sxs-lookup"><span data-stu-id="e6575-103">Before an application can call any ODBC function, it must initialize the ODBC environment and allocate an environment handle.</span></span> <span data-ttu-id="e6575-104">Il s'agit du handle de contexte global et de l'espace réservé pour les autres handles dans ODBC.</span><span class="sxs-lookup"><span data-stu-id="e6575-104">This is the global context handle and placeholder for the other handles in ODBC.</span></span> <span data-ttu-id="e6575-105">Pour ce faire, appelez **SQLAllocHandle** avec le paramètre *comme handletype* défini sur SQL_HANDLE_ENV et *InputHandle* défini sur SQL_NULL_HANDLE.</span><span class="sxs-lookup"><span data-stu-id="e6575-105">You do this by calling **SQLAllocHandle** with the *HandleType* parameter set to SQL_HANDLE_ENV and *InputHandle* set to SQL_NULL_HANDLE.</span></span>  
  
 <span data-ttu-id="e6575-106">Après avoir alloué le handle d'environnement, l'application doit définir des attributs d'environnement afin d'indiquer la version des appels de fonction ODBC qu'elle utilisera.</span><span class="sxs-lookup"><span data-stu-id="e6575-106">After allocating the environment handle, the application must set environment attributes to indicate which version of ODBC function calls it will be using.</span></span> <span data-ttu-id="e6575-107">Pour utiliser ODBC 3. *x* , appelez [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) avec le paramètre d' *attribut* défini sur SQL_ATTR_ODBC_VERSION et *ValuePtr* défini sur SQL_OV_ODBC3.</span><span class="sxs-lookup"><span data-stu-id="e6575-107">To use the ODBC 3.*x* functions, call [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) with the *Attribute* parameter set to SQL_ATTR_ODBC_VERSION and *ValuePtr* set to SQL_OV_ODBC3.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6575-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e6575-108">See Also</span></span>  
 [<span data-ttu-id="e6575-109">Communication avec SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="e6575-109">Communicating with SQL Server &#40;ODBC&#41;</span></span>](communicating-with-sql-server-odbc.md)  
  
  
