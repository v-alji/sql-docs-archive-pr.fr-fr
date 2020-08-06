---
title: Implémentation d’IDENTITY dans une table optimisée en mémoire | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: c0a704a3-3a31-4c2c-b967-addacda62ef8
author: rothja
ms.author: jroth
ms.openlocfilehash: 955f9f1a905a9d0c71304320f60abe300e430e4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604010"
---
# <a name="implementing-identity-in-a-memory-optimized-table"></a><span data-ttu-id="9ac94-102">Implémentation d'IDENTITY dans une table optimisée en mémoire</span><span class="sxs-lookup"><span data-stu-id="9ac94-102">Implementing IDENTITY in a Memory-Optimized Table</span></span>
  <span data-ttu-id="9ac94-103">IDENTITY(1, 1) est pris en charge sur une table mémoire optimisée.</span><span class="sxs-lookup"><span data-stu-id="9ac94-103">IDENTITY(1, 1) is supported on a memory-optimized table.</span></span> <span data-ttu-id="9ac94-104">Cependant, les colonnes d'identité avec définition IDENTITY(x, y) où x != 1 ou y != 1 ne sont pas prises en charge sur les tables mémoire optimisées.</span><span class="sxs-lookup"><span data-stu-id="9ac94-104">However, identity columns with definition of IDENTITY(x, y) where x != 1 or y != 1 are not supported on memory-optimized tables.</span></span> <span data-ttu-id="9ac94-105">La solution pour les valeurs IDENTITY utilise l'objet SEQUENCE ([Sequence Numbers](../sequence-numbers/sequence-numbers.md)).</span><span class="sxs-lookup"><span data-stu-id="9ac94-105">The workaround for IDENTITY values uses the SEQUENCE object ([Sequence Numbers](../sequence-numbers/sequence-numbers.md)).</span></span>  
  
 <span data-ttu-id="9ac94-106">Supprimez d'abord la propriété IDENTITY de la table que vous convertissez en OLTP en mémoire.</span><span class="sxs-lookup"><span data-stu-id="9ac94-106">First remove the IDENTITY property from the table you are converting to In-Memory OLTP.</span></span> <span data-ttu-id="9ac94-107">Ensuite, définissez un nouvel objet SEQUENCE pour la colonne de la table.</span><span class="sxs-lookup"><span data-stu-id="9ac94-107">Then, define a new SEQUENCE object for the column in the table.</span></span> <span data-ttu-id="9ac94-108">Les objets SEQUENCE en tant que colonnes d'identité s'appuient sur la possibilité de créer des valeurs PAR DÉFAUT pour les colonnes qui utilisent la syntaxe NEXT VALUE FOR pour obtenir une nouvelle valeur d'identité.</span><span class="sxs-lookup"><span data-stu-id="9ac94-108">SEQUENCE objects as identity columns rely on the ability to create DEFAULT values for columns that use the NEXT VALUE FOR syntax to get a new identity value.</span></span> <span data-ttu-id="9ac94-109">Étant donné que les valeurs par défaut ne sont pas prises en charge dans OLTP en mémoire, vous devez passer la valeur SEQUENCE récemment générée à l'instruction INSERT ou à une procédure stockée compilée en mode natif qui exécute l'insertion.</span><span class="sxs-lookup"><span data-stu-id="9ac94-109">Since DEFAULTs are not supported in In-Memory OLTP, you need to pass the newly-generated SEQUENCE value either to the INSERT statement or to a natively compiled stored procedure that does the insert.</span></span> <span data-ttu-id="9ac94-110">L'exemple ci-dessous illustre ce modèle.</span><span class="sxs-lookup"><span data-stu-id="9ac94-110">The following example demonstrates this pattern.</span></span>  
  
```sql  
-- Create a new In-Memory OLTP table to simulate IDENTITY insert  
-- Here the column C1 was the identity column in the original table  
--  
create table T1  
(  
  
[c1] integer not null primary key T1_c1 nonclustered,  
[c2] varchar(32) not null,  
[c3] datetime not null  
  
) with (memory_optimized = on)  
go  
  
-- This is a sequence provider that will give us values for column [c1]  
--  
create sequence usq_SequenceForT1 as integer start with 2 increment by 1  
go  
  
--   insert a sample row using the sequence  
--   note that a new value needs to be retrieved form   
--   the sequence object for every insert  
--  
declare @c1 integer = next value for [dbo].[usq_SequenceForT1]  
insert into T1 values (@c1, 'test', getdate())  
```  
  
 <span data-ttu-id="9ac94-111">Après avoir effectué l'insertion plusieurs fois, vous voyez les valeurs à croissance monotone valides dans la colonne [c1].</span><span class="sxs-lookup"><span data-stu-id="9ac94-111">After performing the insert several times, you see valid monotonically increasing values in column [c1].</span></span> <span data-ttu-id="9ac94-112">Ce jeu de résultats est généré à l'aide de l'analyse de table et de l'index de hachage sans `ORDER BY` ; par conséquent, les lignes ne sont pas ordonnées.</span><span class="sxs-lookup"><span data-stu-id="9ac94-112">This result set is generated using table scan and hash index without `ORDER BY` so the rows are not ordered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ac94-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9ac94-113">See Also</span></span>  
 [<span data-ttu-id="9ac94-114">Migration vers OLTP en mémoire</span><span class="sxs-lookup"><span data-stu-id="9ac94-114">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
