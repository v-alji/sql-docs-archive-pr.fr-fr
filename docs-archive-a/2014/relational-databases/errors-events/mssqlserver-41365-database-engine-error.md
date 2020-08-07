---
title: MSSQLSERVER_41365 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41365 (Database Engine error)
ms.assetid: 4fc7ec15-b722-4e3d-b7f9-3d39d171e96e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1382a6395f1929a5d5552113e07376bcbf80bf35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611096"
---
# <a name="mssqlserver_41365"></a>MSSQLSERVER_41365
    
## <a name="details"></a>Détails  
  
|||  
|-|-|  
|Nom du produit|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|ID de l’événement|41365|  
|Source de l’événement|MSSQLSERVER|  
|Composant|SQLEngine|  
|Nom symbolique|HK_MERGE_SCHEDULE_ERROR|  
|Texte du message|La demande de fusion de la plage des transactions [%d, %d] dans la base de données %.*ls n'a pas été planifiée. Les fichiers de point de contrôle représentant la plage sont soit indisponibles pour la fusion, soit ils font partie d'une fusion en cours.|  
  
## <a name="explanation"></a>Explication  
 Les fichiers de point de contrôle représentant la plage sont soit indisponibles pour la fusion, soit ils font partie d'une fusion en cours.  
  
## <a name="user-action"></a>Action de l'utilisateur  
 Optimisez la plage de transactions pour les opérations de fusion/attente avant de réexécuter la même demande. Pour plus d’informations, consultez [OLTP en mémoire &#40;optimisation en mémoire&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).  
  
## <a name="see-also"></a>Voir aussi  
 [OLTP en mémoire &#40;Optimisation en mémoire&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
