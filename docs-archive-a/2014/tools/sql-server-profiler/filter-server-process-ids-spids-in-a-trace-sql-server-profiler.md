---
title: Filtrer des identificateurs de processus serveur dans une trace (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], traces
- filters [SQL Server], SPIDs
- traces [SQL Server], filters
ms.assetid: f5945c39-be6b-4632-91cb-92066c80e188
author: stevestein
ms.author: sstein
ms.openlocfilehash: 99ae7eac6f19bd942a04f97b0a7da580eadc9dbf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706923"
---
# <a name="filter-server-process-ids-spids-in-a-trace-sql-server-profiler"></a>Filtrer des identificateurs de processus serveur (SPID, Server Process ID) dans une trace (SQL Server Profiler)
  Cette rubrique décrit comment filtrer les identificateurs de processus serveur (SPID, Server Process ID) dans une trace grâce au [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].  
  
### <a name="to-filter-system-ids-in-a-trace"></a>Pour filtrer des ID système dans une trace  
  
1.  Dans le menu **Fichier** , cliquez sur **Nouvelle trace**, puis connectez-vous à une instance de SQL Server.  
  
     La boîte de dialogue **Propriétés de la trace**apparaît.  
  
    > [!NOTE]  
    >  Si l’option **Démarrer le suivi juste après avoir fait la connexion**est sélectionnée, la boîte de dialogue Propriétés de la **trace**ne s’affiche pas et la trace démarre à la place. Pour désactiver ce paramètre, accédez au menu **Outils**, cliquez sur **Options**et désactivez la case à cocher **Démarrer le suivi juste après avoir établi la connexion** .  
  
2.  Dans la zone **Nom de la trace** , tapez un nom pour la trace.  
  
3.  Dans la liste de noms **Utiliser le modèle**, sélectionnez un modèle de trace.  
  
4.  Le cas échéant, spécifiez un fichier ou une table de destination pour y enregistrer les résultats du suivi.  
  
5.  Sous l’onglet **Sélection des événements**, cliquez sur l’en-tête de la colonne **SPID**pour ouvrir la boîte de dialogue **Modifier le filtre** . Vous pouvez également cliquer avec le bouton droit de la souris sur l’en-tête de colonne et choisir **Modifier le filtre des colonnes**parmi les éléments du menu contextuel. Si la colonne **SPID** n’apparaît pas, cochez la case **Afficher toutes les colonnes** .  
  
6.  Dans la boîte de dialogue **Modifier le filtre** , développez l’opérateur de comparaison voulu et entrez le SPID correspondant à la valeur de comparaison.  
  
## <a name="see-also"></a>Voir aussi  
 [SQL Server Profiler](sql-server-profiler.md)  
  
  
