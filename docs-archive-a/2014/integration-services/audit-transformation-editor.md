---
title: Éditeur de transformation d’audit | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.audittransformation.f1
helpviewer_keywords:
- Audit Transformation Editor
ms.assetid: 32786a34-5870-4fde-83c7-ec74d62404b8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: af6490643a0bef60cca961dc9a0564c5f6b46484
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707736"
---
# <a name="audit-transformation-editor"></a>Éditeur de transformation d'audit
  La transformation d'audit permet au flux de données d'un package de contenir des données relatives à l'environnement d'exécution du package. Par exemple, le nom du package, de l'ordinateur et de l'opérateur peuvent être ajoutés au flux de données. [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] comprend des variables système qui fournissent ces informations.  
  
 Pour en savoir plus sur la transformation d'audit, consultez [Audit Transformation](data-flow/transformations/audit-transformation.md).  
  
## <a name="options"></a>Options  
 **Nom de la colonne de sortie**  
 Indique le nom de la nouvelle colonne de sortie qui va contenir les informations d'audit.  
  
 **Type d’audit**  
 Sélectionne une variable système disponible pour fournir les informations d'audit.  
  
|Valeur|Description|  
|-----------|-----------------|  
|**GUID d'instance d'exécution**|Insérez le GUID qui identifie de manière unique l'instance d'exécution du package.|  
|**ID du package**|Insérez le GUID qui identifie de manière unique le package.|  
|**Nom du package**|Insérez le nom du package.|  
|**ID de version**|Insérez le GUID qui identifie de manière unique la version du package.|  
|**Heure de début de l'exécution**|Insérez l'heure à laquelle l'exécution du package a commencé.|  
|**Nom de l'ordinateur**|Insérez le nom de l'ordinateur sur lequel le package a été lancé.|  
|**Nom d'utilisateur**|Insérez le nom de connexion de l'utilisateur qui a lancé le package.|  
|**Nom de la tâche**|Insérez le nom de la tâche de flux de données à laquelle la transformation d'audit est associée.|  
|**ID de la tâche**|Insérez le GUID qui identifie de manière unique le flux de données à laquelle la transformation d'audit est associée.|  
  
## <a name="see-also"></a>Voir aussi  
 [Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
