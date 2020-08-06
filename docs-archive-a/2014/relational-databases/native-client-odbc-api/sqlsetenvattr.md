---
title: SQLSetEnvAttr | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLSetEnvAttr function
ms.assetid: d4114571-feca-4330-b2e4-7bfd1050b812
author: rothja
ms.author: jroth
ms.openlocfilehash: f0dbd4d01de9ca769c46a93f810f0149f5b86981
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613997"
---
# <a name="sqlsetenvattr"></a><span data-ttu-id="ebee2-102">SQLSetEnvAttr</span><span class="sxs-lookup"><span data-stu-id="ebee2-102">SQLSetEnvAttr</span></span>
  <span data-ttu-id="ebee2-103">Le [Guide de référence du programmeur OLE DB](https://go.microsoft.com/fwlink/?LinkId=45250) définit comment les pilotes ODBC doivent interpréter les spécifications d'attribut **SQLSetEnvAttr** à partir des applications écrites dans l'API ODBC 2.*x* ou ODBC 3.*x* .</span><span class="sxs-lookup"><span data-stu-id="ebee2-103">The [ODBC Programmer's Reference](https://go.microsoft.com/fwlink/?LinkId=45250) defines how ODBC drivers should interpret the **SQLSetEnvAttr** attribute specifications from applications written to either the ODBC 2.*x* or ODBC 3.*x* API.</span></span> <span data-ttu-id="ebee2-104">Le pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client est conforme à ces règles.</span><span class="sxs-lookup"><span data-stu-id="ebee2-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver complies with those rules.</span></span>  
  
 <span data-ttu-id="ebee2-105">L'un des attributs contrôlé par **SQLSetEnvAttr** indique si le regroupement de connexions sera utilisé.</span><span class="sxs-lookup"><span data-stu-id="ebee2-105">One of the attributes controlled by **SQLSetEnvAttr** is whether connection pooling is to be used.</span></span> <span data-ttu-id="ebee2-106">Si le regroupement de connexions est utilisé avec le pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, il faut affecter au paramètre *DriverCompletion* la valeur SQL_DRIVER_NOPROMPT lors de la connexion à [SQLDriverConnect](sqldriverconnect.md) ou **SQLConnect**.</span><span class="sxs-lookup"><span data-stu-id="ebee2-106">If connection pooling is used with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver, the *DriverCompletion* parameter must be set to SQL_DRIVER_NOPROMPT when connecting with either [SQLDriverConnect](sqldriverconnect.md) or **SQLConnect**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebee2-107">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ebee2-107">See Also</span></span>  
 <span data-ttu-id="ebee2-108">[SQLSetEnvAttr fonction)](https://go.microsoft.com/fwlink/?LinkId=59369) </span><span class="sxs-lookup"><span data-stu-id="ebee2-108">[SQLSetEnvAttr Function](https://go.microsoft.com/fwlink/?LinkId=59369) </span></span>  
 [<span data-ttu-id="ebee2-109">Détails de l’implémentation d’API ODBC</span><span class="sxs-lookup"><span data-stu-id="ebee2-109">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
