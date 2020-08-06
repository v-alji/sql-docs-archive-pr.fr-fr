---
title: '! (Non logique) (expression SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logical Not (!)
- '! (logical Not)'
ms.assetid: d5c4d1e1-7be4-4d25-bcd9-5b6ddb53b3b3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1bbf313930575e864f1556952425567fca96db15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604651"
---
# <a name="-logical-not-ssis-expression"></a>! (Non logique) (expression SSIS)
  Inverse un opérande booléen.  
  
> [!NOTE]  
>  L'opérateur « ! » ne peut pas être utilisé en combinaison avec d'autres opérateurs. Par exemple, vous ne pouvez pas combiner les opérateurs « ! » et > pour former l'opérateur « !> » .  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
!boolean_expression  
  
```  
  
## <a name="arguments"></a>Arguments  
 *boolean_expression*  
 Toute expression valide qui s'évalue à une valeur booléenne. Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).  
  
## <a name="result-types"></a>Types des résultats  
 DT_BOOL  
  
## <a name="remarks"></a>Notes  
 Le tableau suivant indique le résultat de l'opération « ! » .  
  
|Expression booléenne initiale|Après application de l'opérateur « ! » operator|  
|---------------------------------|------------------------------------|  
|TRUE|FALSE|  
|NULL|NULL|  
|FALSE|TRUE|  
  
## <a name="expression-examples"></a>Exemples d'expressions  
 L’exemple suivant donne la valeur FALSE si la colonne **Color** a pour valeur « red ».  
  
```  
!(Color == "red")  
```  
  
 L’exemple suivant donne la valeur TRUE si la valeur de la variable **MonthNumber** et celle de l’entier qui représente le mois actuel sont identiques. Pour plus d’informations, consultez [MONTH &#40;expression SSIS&#41;](month-ssis-expression.md) et [GETDATE &#40;expression SSIS&#41;](getdate-ssis-expression.md).  
  
```  
!(@MonthNumber != MONTH(GETDATE())  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Priorités et associativité des opérateurs](operator-precedence-and-associativity.md)   
 [Opérateurs &#40;expression SSIS&#41;](operators-ssis-expression.md)  
  
  
