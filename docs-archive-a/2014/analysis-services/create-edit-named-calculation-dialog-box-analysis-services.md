---
title: Boîte de dialogue créer-modifier le calcul nommé (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dsveditor.createnamedcalculation.f1
helpviewer_keywords:
- Named Calculation dialog box
ms.assetid: 66fb30ae-f5c5-4bfc-80ca-8c8a3a9bb30d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0b6777feb47a1ce6b601d0190e413b4baae35f1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600355"
---
# <a name="create-edit-named-calculation-dialog-box-analysis-services"></a>Boîte de dialogue créer-modifier le calcul nommé (Analysis Services)
  Utilisez la boîte de dialogue **créer/modifier le calcul nommé** dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] pour définir ou modifier un calcul nommé pour une table dans une vue de source de données. Vous pouvez afficher la boîte de dialogue **Créer un calcul nommé/Modifier le calcul nommé** en :  
  
-   cliquant sur **Nouveau calculé nommé** dans le volet **Barre d’outils** du **Concepteur de vue de source de données** ;  
  
-   cliquant avec le bouton droit sur une table dans le volet **Tables** ou **Schéma** du **Concepteur de vue de source de données** et en sélectionnant **Nouveau calcul nommé** ;  
  
-   cliquant avec le bouton droit sur le nom d’un calcul nommé dans le volet **Schéma** du **Concepteur de vue de source de données** et en sélectionnant **Modifier le calcul nommé**.  
  
## <a name="options"></a>Options  
 **Nom de la colonne**  
 Entrez le nom du calcul nommé.  
  
 **Description**  
 Entrez la description facultative du calcul nommé.  
  
 **Expression**  
 Entrez une expression SQL valide qui retourne une valeur scalaire. L'expression est envoyée au fournisseur et validée dans l'expression suivante :  
  
```  
SELECT <Table Name in Data Source>.* , <Expression> AS <Column Name> FROM <Table Name in Data Source>AS <Table Name in Data Source View>  
```  
  
 L'expression peut contenir des références à d'autres tables via une instruction sub-select. If the expression would require parentheses in a SELECT statement, the expression entered must be enclosed between parentheses.  
  
## <a name="see-also"></a>Voir aussi  
 [Analysis Services les concepteurs et les boîtes de dialogue &#40;les données multidimensionnelles&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)   
 [Concepteur de vue de source de données &#40;Analysis Services - Données multidimensionnelles&#41;](data-source-view-designer-analysis-services-multidimensional-data.md)  
  
  
