---
title: SQLFreeHandle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLFreeHandle function
ms.assetid: d374e5c8-ed35-43bf-8dd6-c37e38d9b5f1
author: rothja
ms.author: jroth
ms.openlocfilehash: f51f031bec05715e0345507278113f4f16179a77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603965"
---
# <a name="sqlfreehandle"></a><span data-ttu-id="e31af-102">SQLFreeHandle</span><span class="sxs-lookup"><span data-stu-id="e31af-102">SQLFreeHandle</span></span>
  <span data-ttu-id="e31af-103">En mode de validation manuelle, l'appel de **SQLFreeHandle** sur un descripteur d'instruction avec une transaction ouverte provoque une restauration des modifications en attente de la base de données.</span><span class="sxs-lookup"><span data-stu-id="e31af-103">In manual-commit mode, calling **SQLFreeHandle** on a statement handle with an open transaction causes a rollback of pending changes to the database.</span></span> <span data-ttu-id="e31af-104">L'appel de **SQLFreeHandle** sur un descripteur d'instruction ferme toujours tous les curseurs ouverts et ignore les résultats en attente, libérant toutes les ressources associées au descripteur d'instruction.</span><span class="sxs-lookup"><span data-stu-id="e31af-104">Calling **SQLFreeHandle** on a statement handle always closes any open cursors and discards pending results, freeing all resources associated with the statement handle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e31af-105">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e31af-105">See Also</span></span>  
 <span data-ttu-id="e31af-106">[SQLFreeHandle, fonction](https://go.microsoft.com/fwlink/?LinkId=59345) </span><span class="sxs-lookup"><span data-stu-id="e31af-106">[SQLFreeHandle Function](https://go.microsoft.com/fwlink/?LinkId=59345) </span></span>  
 [<span data-ttu-id="e31af-107">Détails de l’implémentation d’API ODBC</span><span class="sxs-lookup"><span data-stu-id="e31af-107">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
