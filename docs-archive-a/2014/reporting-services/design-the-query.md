---
title: Concevoir la requête | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptwizard.designquery.f1
ms.assetid: 2dad800f-10a1-453c-8761-2935b9826d84
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9b56d99ec11b50ce53ef223a01eb5fc2766238ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703927"
---
# <a name="design-the-query"></a>Concevoir la requête
  Utilisez cette page de l'Assistant Rapport pour créer une requête en la tapant manuellement, en utilisant le Générateur de requêtes pour créer une requête de manière interactive ou en important une requête à partir d'un autre rapport.  
  
 Le type de source de données sélectionné dans la page Sélectionner la source de données, à la page précédente de l'Assistant Rapport, détermine la requête que vous pouvez spécifier dans cette page. Par exemple, si le type de source de données est [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , vous pouvez entrer des [!INCLUDE[tsql](../includes/tsql-md.md)] instructions ou des noms de procédure stockée. Si le type de source de données est [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , le volet requête est désactivé et vous ne pouvez pas entrer de requête directement. Vous pouvez spécifier la requête en utilisant le Générateur de requêtes.  
  
## <a name="options"></a>Options  
 **Chaîne de requête**  
 Tapez une requête qui extrait les données que vous voulez utiliser dans votre rapport.  
  
 **Générateur de requêtes**  
 Cliquez sur **Générateur de requêtes** pour ouvrir un concepteur de requêtes pour la source de données ou pour importer une requête à partir d’un autre rapport.  
  
 Pour plus d'informations sur les concepteurs de requêtes, consultez [Reporting Services Query Designers](../../2014/reporting-services/reporting-services-query-designers.md).  
  
## <a name="example"></a>Exemple  
 Pour le type de source de données **Microsoft SQL Server**, la requête suivante extrait une liste des noms de la [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] table de base de données `Person` .  
  
```  
SELECT LastName FROM Person.Person;  
```  
  
 Pour le type de source de données **Microsoft SQL Server**, la requête suivante exécute la [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] procédure stockée `uspGetEmployeeManagers` pour l’employé dont le numéro d’identification est 1 :  
  
```  
EXEC uspgetEmployeeManagers '1';  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Aide de l’Assistant Rapport](../../2014/reporting-services/report-wizard-help.md)   
 [Datasets incorporés dans le rapport et datasets partagés &#40;Générateur de rapports et SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)   
 [Ajouter des données à un rapport &#40;Générateur de rapports et SSRS&#41;](report-data/report-datasets-ssrs.md)  
  
  
