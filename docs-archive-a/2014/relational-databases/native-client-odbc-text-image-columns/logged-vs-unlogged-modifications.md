---
title: Modifications journalisées et non journalisées | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- text columns [ODBC]
- SQL Server Native Client ODBC driver, image columns
- SQL Server Native Client ODBC driver, text columns
- data types [ODBC], image
- data types [ODBC], text
- logged vs. nonlogged modifications [SQL Server Native Client]
- columns [ODBC]
- ODBC data types, image columns
- nonlogged vs. logged modifications
- ODBC data types, text columns
- image columns [ODBC]
ms.assetid: 20aa5b27-4a2c-46e7-8356-beb0eebf4b7e
author: rothja
ms.author: jroth
ms.openlocfilehash: 8768acc75d18ea2236f0e9280e5d0c805e688107
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709300"
---
# <a name="logged-vs-unlogged-modifications"></a><span data-ttu-id="356c8-102">Modifications enregistrées ou non enregistrées</span><span class="sxs-lookup"><span data-stu-id="356c8-102">Logged vs. Unlogged Modifications</span></span>
  <span data-ttu-id="356c8-103">Une application peut demander que le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client n’enregistre pas les modifications **Text**, **ntext**et **image** .</span><span class="sxs-lookup"><span data-stu-id="356c8-103">An application can request that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver not log **text**, **ntext**, and **image** modifications.</span></span> <span data-ttu-id="356c8-104">Il convient toutefois d'être prudent lors de l'utilisation de cette option.</span><span class="sxs-lookup"><span data-stu-id="356c8-104">Care should be used with this option, however.</span></span> <span data-ttu-id="356c8-105">Elle ne doit être utilisée que dans les cas où les données **Text**, **ntext**ou **image** ne sont pas critiques et que les propriétaires de données sont prêts à échanger la possibilité de récupérer les données pour des performances supérieures.</span><span class="sxs-lookup"><span data-stu-id="356c8-105">It should be used only for those situations where the **text**, **ntext**, or **image** data is not critical and data owners are willing to trade off the ability to recover data for higher performance.</span></span>  
  
 <span data-ttu-id="356c8-106">La journalisation des modifications de **texte**, **ntext**et **image** est contrôlée en appelant [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) avec le paramètre d' *attribut* défini sur SQL_SOPT_SS_ TEXTPTR_LOGGING et *ValuePtr* défini sur SQL_TL_ON ou SQL_TL_OFF.</span><span class="sxs-lookup"><span data-stu-id="356c8-106">The logging of **text**, **ntext**, and **image** modifications is controlled by calling [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) with the *Attribute* parameter set to SQL_SOPT_SS_ TEXTPTR_LOGGING and *ValuePtr* set to either SQL_TL_ON or SQL_TL_OFF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="356c8-107">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="356c8-107">See Also</span></span>  
 [<span data-ttu-id="356c8-108">Gestion des colonnes texte et image</span><span class="sxs-lookup"><span data-stu-id="356c8-108">Managing Text and Image Columns</span></span>](managing-text-and-image-columns.md)  
  
  
