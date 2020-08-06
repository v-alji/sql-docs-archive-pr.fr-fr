---
title: MSSQLSERVER_17067 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17067 (Database Engine error)
ms.assetid: 32c1f0e8-db70-4836-95b2-8833be9e0ad1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4ff3de7ed2fbe54a32aaa501979a3acb6b452947
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612891"
---
# <a name="mssqlserver_17067"></a>MSSQLSERVER_17067
    
## <a name="details"></a>Détails  
  
|||  
|-|-|  
|Nom du produit|SQL Server|  
|ID de l’événement|17067|  
|Source de l’événement|MSSQLSERVER|  
|Composant|SQLEngine|  
|Nom symbolique|SQLASSERT_MESG|  
|Texte du message|Assertion SQL Server : Fichier : \<%s>, ligne =% d% s. Cette erreur est éventuellement liée à un délai d'attente. Si l'erreur persiste après une nouvelle exécution de l'instruction, utilisez DBCC CHECKDB pour vérifier l'intégrité structurelle de la base de données ou redémarrez le serveur pour vous assurer que les structures de données en mémoire ne sont pas corrompues.|  
  
## <a name="explanation"></a>Explication  
 Cette erreur peut être provoquée par des erreurs temporaires liées à un délai d'attente ou par une corruption des données en mémoire ou sur disque.  
  
## <a name="user-action"></a>Action de l'utilisateur  
 Réexécutez l'instruction qui a provoqué le déclenchement de l'exception. Si l'erreur a été provoquée par un événement lié à un délai d'attente, elle peut ne pas se reproduire. Si le problème persiste, exécutez DBCC CHECKDB pour rechercher une corruption sur disque. Redémarrez le serveur pour vérifier que les structures de données en mémoire ne sont pas endommagées.  
  
## <a name="see-also"></a>Voir aussi  
 [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
