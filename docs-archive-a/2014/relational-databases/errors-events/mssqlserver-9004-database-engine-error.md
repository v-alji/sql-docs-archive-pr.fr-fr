---
title: MSSQLSERVER_9004 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9004 (Database Engine error)
ms.assetid: b528bb49-340c-4a81-9c8d-cefce6562f16
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 910665b4349e5b13c5abb4fd687dcf0c6fc122cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604492"
---
# <a name="mssqlserver_9004"></a>MSSQLSERVER_9004
    
## <a name="details"></a>Détails  
  
|||  
|-|-|  
|Nom du produit|SQL Server|  
|ID de l’événement|9004|  
|Source de l’événement|MSSQLSERVER|  
|Composant|SQLEngine|  
|Nom symbolique|LOG_CORRUPT|  
|Texte du message|Une erreur s'est produite lors du traitement du journal de la base de données '%.*ls'.  If possible, restore from backup. Si aucune sauvegarde n'est disponible, vous devrez peut-être recréer le journal.|  
  
## <a name="explanation"></a>Explication  
 Une erreur s'est produite lors du traitement du journal, au cours d'une annulation, d'une récupération ou d'une réplication. Cela peut indiquer une erreur détectée par le système d'exploitation ou une erreur de cohérence interne détectée par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
## <a name="user-action"></a>Action de l'utilisateur  
 L'une des actions ci-dessous corrigera cette erreur :  
  
-   Effectuez la restauration à partir d'une sauvegarde.  
  
-   Régénérez le journal.  
  
 Vérifiez également les journaux des événements et les journaux des erreurs du système qui peuvent être à l'origine du problème.  
  
  
