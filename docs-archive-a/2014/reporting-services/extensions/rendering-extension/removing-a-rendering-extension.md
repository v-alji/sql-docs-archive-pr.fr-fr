---
title: Suppression d’une extension de rendu | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- deleting rendering extensions
- removing rendering extensions
- rendering extensions [Reporting Services], removing
ms.assetid: 2abfebfb-065f-45cc-a904-c914394cf900
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 77a8a9ac44b35f338f978913985617e4f264ddb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610484"
---
# <a name="removing-a-rendering-extension"></a>Suppression d'une extension de rendu
  Pour supprimer une [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] extension de rendu, supprimez simplement l' `Extension` élément pour votre extension de rendu du fichier rsreportserver.config, situé dans **%programfiles%\microsoft SQL Server \ MSRS10_50. \<Instance Name> Dossier \Reporting Services\ReportServer** . Si vous avez créé des entrées pour un Concepteur de rapports, ainsi qu’un serveur de rapports, supprimez `Extension` également l’élément du [fichier de configuration RSReportDesigner](../../report-server/rsreportdesigner-configuration-file.md) . Une fois les informations de configuration supprimées, l'extension de rendu n'est plus accessible au composant.  
  
## <a name="see-also"></a>Voir aussi  
 [Fichiers de configuration de Reporting Services](../../report-server/reporting-services-configuration-files.md)   
 [Implémentation d’une extension de rendu](implementing-a-rendering-extension.md)   
 [Vue d’ensemble des extensions de rendu](rendering-extensions-overview.md)   
 [Mise en œuvre de l’interface IRenderingExtension](implementing-the-irenderingextension-interface.md)   
 [Considérations sur la sécurité pour les extensions](../security-considerations-for-extensions.md)   
 [Déploiement d'une extension de rendu](deploying-a-rendering-extension.md)  
  
  
