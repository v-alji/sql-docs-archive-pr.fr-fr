---
title: Onglet gestionnaires d’événements | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.eventhandlerwindow.f1
ms.assetid: 94fc8916-8032-490c-b9d5-ded8b6217e49
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a5f25a9b0d602a3189feab797b7ef9c333decabb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610764"
---
# <a name="event-handlers-tab"></a>Onglet Gestionnaires d'événements
  Utilisez l’onglet **Gestionnaires d’événements** du concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] pour créer un flux de contrôle dans un package [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] . Un gestionnaire d'événements est exécuté en réponse à un événement déclenché par le package ou par une tâche ou un conteneur du package.  
  
## <a name="options"></a>Options  
 **Exécutable**  
 Sélectionnez l'exécutable pour lequel vous souhaitez créer un gestionnaire d'événements. L'exécutable peut être un package ou une tâche ou des conteneurs du package.  
  
 **Gestionnaire d’événements**  
 Sélectionnez un type de gestionnaire d'événements. Créez le gestionnaire d’événements en faisant glisser les éléments à partir de la **Boîte à outils**.  
  
 **Supprimer**  
 Sélectionnez un gestionnaire d’événements et supprimez-le du package en cliquant sur **Supprimer**.  
  
 **Cliquez ici pour créer un \<event handler name> pour l’exécutable \<executable name>**  
 Cliquez pour créer le gestionnaire d'événements.  
  
 Pour créer le flux de contrôle, faites glisser les objets graphiques qui représentent les tâches et les conteneurs [!INCLUDE[ssIS](../includes/ssis-md.md)] de la **Boîte à outils** vers l’onglet **Gestionnaires d’événements** , puis connectez-les en utilisant des contraintes de priorité pour définir leur ordre d’exécution.  
  
 Par ailleurs, pour ajouter des annotations, cliquez avec le bouton droit dans l’aire de conception puis, dans le menu qui s’affiche, cliquez sur **Ajouter une annotation**.  
  
## <a name="see-also"></a>Voir aussi  
 [Gestionnaires d’événements Integration Services &#40;SSIS&#41](integration-services-ssis-event-handlers.md)   
 [Flux de contrôle](control-flow/control-flow.md)   
 [Concepteur SSIS](ssis-designer.md)   
 [Gestionnaires d’événements Integration Services &#40;SSIS&#41](integration-services-ssis-event-handlers.md)  
  
  
