---
title: Boîte de dialogue Définir la valeur du paramètre | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ce9c2201-4e9a-4495-948f-b68deeaa7955
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 637267603c66921a566ca0d2a3f49f6142cfd203
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705355"
---
# <a name="set-parameter-value-dialog-box"></a>Boîte de dialogue Définir la valeur du paramètre
  Utilisez la boîte de dialogue **Définir la valeur du paramètre** pour définir les valeurs des paramètres et les propriétés des gestionnaires de connexions, pour les projets et packages.  
  
 **Que voulez-vous faire ?**  
  
-   [Ouvrir la boîte de dialogue Définir la valeur du paramètre](#open_dialog)  
  
-   [Configurer les options](#option)  
  
##  <a name="open-the-set-parameter-value-dialog-box"></a><a name="open_dialog"></a> Ouvrir la boîte de dialogue Définir la valeur du paramètre  
  
1.  Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connectez-vous au serveur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .  
  
     Vous vous connectez à l’instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] qui héberge la base de données SSISDB.  
  
2.  Dans l'Explorateur d'objets, développez l'arborescence pour afficher le nœud **Integration Services Catalogues** .  
  
3.  Développez le nœud **SSISDB** .  
  
4.  Cliquez avec le bouton droit sur un package ou un projet, cliquez sur **Configurer**, puis cliquez sur le bouton de sélection sous l’onglet **Paramètres** ou l’onglet **Gestionnaires de connexions** .  
  
##  <a name="configure-the-options"></a><a name="option"></a> Configurer les options  
 **Paramètre**  
 Indique le nom du paramètre.  
  
 **Type**  
 Indique le type de données de la valeur de paramètre.  
  
 **Description**  
 Affiche une description facultative du paramètre.  
  
 **Modifier la valeur**  
 Sélectionnez cette option pour modifier la valeur du paramètre.  
  
 **Utiliser la valeur par défaut du package**  
 Sélectionnez cette option afin d'utiliser le paramètre par défaut stocké dans le package.  
  
 **Utiliser la variable d'environnement**  
 Sélectionnez cette option pour utiliser une valeur de variable stockée dans l'environnement, qui est référencé par le projet ou le package. Pour ajouter une référence d'environnement à un projet ou package, utilisez la boîte de dialogue **Configurer** . Pour plus d'informations, consultez [Configure Dialog Box](configure-dialog-box.md).  
  
  
