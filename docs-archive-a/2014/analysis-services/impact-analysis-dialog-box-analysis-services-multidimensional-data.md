---
title: Boîte de dialogue analyse d’impact (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.process.impactanalysisdialog.f1
ms.assetid: 208268eb-4e14-44db-9c64-6f74b776adb6
author: minewiskan
ms.author: owend
ms.openlocfilehash: e47ab806b9bd10afc812113b69fe0849437068b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696288"
---
# <a name="impact-analysis-dialog-box-analysis-services---multidimensional-data"></a>Boîte de dialogue Analyse d'impact (Analysis Services - Données multidimensionnelles)
  Utilisez la boîte de dialogue **Analyse d'impact** dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] et [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] pour identifier et éventuellement traiter les objets dépendants affectés si les objets figurant dans la boîte de dialogue **Traiter** sont traités. Pour afficher la boîte de dialogue **Analyse d'impact** , cliquez sur **Analyse d'impact** dans la boîte de dialogue **Traiter** .  
  
> [!NOTE]  
>  Un objet apparaît plusieurs fois s'il est affecté de différentes manières.  
  
## <a name="options"></a>Options  
 **Liste d’objets**  
 Affiche la liste des objets dépendants dans une grille. Cette grille comporte les colonnes suivantes :  
  
 **Nom de l’objet**  
 Affiche le nom des objets dépendants qui devront peut-être être traités. L'icône à gauche du nom indique le type de l'objet.  
  
 **Type**  
 Affiche le type des objets dépendants qui devront peut-être être traités.  
  
 **Type d'impact**  
 Affiche l’effet que le traitement des objets mentionnés dans la boîte de dialogue **Traiter** aura sur l’objet dépendant. Le tableau suivant répertorie les effets possibles du traitement et indique si chaque traitement génère un avertissement ou une erreur.  
  
|Impact|Message|  
|------------|-------------|  
|L'objet sera exclu (non traité)|Warning|  
|L'objet serait non valide|Error|  
|L'agrégation serait supprimée|Warning|  
|L'agrégation flexible serait supprimée|Warning|  
|Les index vont être supprimés|Warning|  
|L'objet non enfant va être traité|Warning|  
  
 **Traiter l'objet**  
 Sélectionnez les objets dépendants à traiter. Les objets dépendants non sélectionnés doivent être traités une fois le traitement terminé. Sinon, ils ne pourront pas être utilisés.  
  
## <a name="see-also"></a>Voir aussi  
 [Analysis Services les concepteurs et les boîtes de dialogue &#40;les données multidimensionnelles&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)   
 [Boîte de dialogue traiter &#40;Analysis Services-données multidimensionnelles&#41;](process-dialog-box-analysis-services-multidimensional-data.md)  
  
  
