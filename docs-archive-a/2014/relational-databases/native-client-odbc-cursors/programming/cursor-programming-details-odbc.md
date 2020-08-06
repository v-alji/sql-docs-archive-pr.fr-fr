---
title: Détails de la programmation des curseurs (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, cursors
- ODBC applications, cursors
- ODBC cursors, programming
- cursors [ODBC], programming
ms.assetid: 6bae29c4-7f49-419c-8712-90db734f992e
author: rothja
ms.author: jroth
ms.openlocfilehash: 4108e195c16d321578a70852dd990f4f8d658832
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603511"
---
# <a name="cursor-programming-details-odbc"></a><span data-ttu-id="2345e-102">Détails de programmation de curseurs (ODBC)</span><span class="sxs-lookup"><span data-stu-id="2345e-102">Cursor Programming Details (ODBC)</span></span>
  <span data-ttu-id="2345e-103">Le choix du type de curseur approprié peut améliorer les performances de l'application.</span><span class="sxs-lookup"><span data-stu-id="2345e-103">Choosing the correct cursor type can improve application performance.</span></span> <span data-ttu-id="2345e-104">Sous certaines conditions, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] peut convertir implicitement un type de curseur lorsque vous exécutez une instruction SQL qui n'est pas prise en charge par le type de curseur demandé.</span><span class="sxs-lookup"><span data-stu-id="2345e-104">Under certain conditions, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] may implicitly convert a cursor type when you execute an SQL statement that is not supported by the cursor type you requested.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2345e-105">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="2345e-105">In This Section</span></span>  
  
-   [<span data-ttu-id="2345e-106">Conversions de curseurs implicites &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="2345e-106">Implicit Cursor Conversions &#40;ODBC&#41;</span></span>](implicit-cursor-conversions-odbc.md)  
  
-   [<span data-ttu-id="2345e-107">Utilisation de l’auto-extraction avec les curseurs ODBC</span><span class="sxs-lookup"><span data-stu-id="2345e-107">Using Autofetch with ODBC Cursors</span></span>](using-autofetch-with-odbc-cursors.md)  
  
-   [<span data-ttu-id="2345e-108">Curseurs avant uniquement rapides &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="2345e-108">Fast Forward-Only Cursors &#40;ODBC&#41;</span></span>](fast-forward-only-cursors-odbc.md)  
  
## <a name="see-also"></a><span data-ttu-id="2345e-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2345e-109">See Also</span></span>  
 [<span data-ttu-id="2345e-110">Utilisation de curseurs &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="2345e-110">Using Cursors &#40;ODBC&#41;</span></span>](../using-cursors-odbc.md)  
  
  
