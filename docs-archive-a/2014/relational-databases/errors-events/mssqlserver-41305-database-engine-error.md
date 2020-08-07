---
title: MSSQLSERVER_41305 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41305 (Database Engine error)
ms.assetid: a96e5083-ff97-4003-a900-07942454151d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9c00e20ec220d7fcee0da4e99c2ef35817dae67f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611097"
---
# <a name="mssqlserver_41305"></a>MSSQLSERVER_41305
    
## <a name="details"></a>Détails  
  
|||  
|-|-|  
|Nom du produit|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|ID de l’événement|41305|  
|Source de l’événement|MSSQLSERVER|  
|Composant|SQLEngine|  
|Nom symbolique|HK_TX_COMMIT_RR_VALIDATION|  
|Texte du message|La transaction en cours n'a pas été validée en raison d'un échec de validation REPEATABLE READ.|  
  
## <a name="explanation"></a>Explication  
 La transaction a rencontré une erreur de validation, et est maintenant vouée à l'échec.  
  
 Pour plus d’informations, consultez [OLTP en mémoire &#40;optimisation en mémoire&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).  
  
## <a name="user-action"></a>Action de l'utilisateur  
 Réexécutez la transaction en échec.  
  
## <a name="see-also"></a>Voir aussi  
 [OLTP en mémoire &#40;Optimisation en mémoire&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
