---
title: Simulation d’une clause EXISTs dans une procédure stockée compilée en mode natif | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: c0e187c1-cbd9-463c-b417-8a734574f102
author: rothja
ms.author: jroth
ms.openlocfilehash: 7b16491b9a3729ad4df71c7ddceaee6db21777ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709415"
---
# <a name="simulating-an-exists-clause-in-a-natively-compiled-stored-procedure"></a>Simulation d'une clause EXISTS dans une procédure stockée compilée en mode natif
  Les procédures stockées compilées en mode natif ne prennent pas en charge la clause `EXISTS`, mais il existe une solution :  
  
```sql  
DECLARE @exists BIT = 0  
SELECT TOP 1 @exists = 1 FROM MyTable WHERE ...  
IF @exists = 1  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Problèmes de migration pour les procédures stockées compilées en mode natif](migration-issues-for-natively-compiled-stored-procedures.md)   
 [Constructions Transact-SQL non prises en charge par In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md)  
  
  
