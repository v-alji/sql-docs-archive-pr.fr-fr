---
title: Jeux de résultats OLE Automation | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: conceptual
helpviewer_keywords:
- data types [SQL Server], OLE Automation
- two-dimensional arrays
- one-dimensional arrays
- result sets [SQL Server], OLE Automation
- OLE Automation [SQL Server], result sets
- arrays [SQL Server]
ms.assetid: b2f99e33-2303-427c-94b9-9d55f8e2a6ab
author: stevestein
ms.author: sstein
ms.openlocfilehash: f7c9bdc4d51d989db2d4d676b29e0824c0e5b59a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615119"
---
# <a name="ole-automation-result-sets"></a><span data-ttu-id="3520f-102">Jeux de résultats OLE Automation</span><span class="sxs-lookup"><span data-stu-id="3520f-102">OLE Automation Result Sets</span></span>
  <span data-ttu-id="3520f-103">Si une propriété ou une méthode OLE Automation retourne des données dans un tableau à une ou deux dimensions, ce tableau est retourné au client sous la forme d'un jeu de résultats :</span><span class="sxs-lookup"><span data-stu-id="3520f-103">If an OLE Automation property or method returns data in an array with one or two dimensions, the array is returned to the client as a result set:</span></span>  
  
-   <span data-ttu-id="3520f-104">Un tableau à une dimension est retourné au client sous la forme d'un jeu de résultats d'une seule ligne avec autant de colonnes qu'il y a d'éléments dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="3520f-104">A one-dimensional array is returned to the client as a single-row result set with as many columns as there are elements in the array.</span></span> <span data-ttu-id="3520f-105">Par exemple, array(10) est retourné sous la forme d'une seule ligne de 10 colonnes.</span><span class="sxs-lookup"><span data-stu-id="3520f-105">For example, an array(10) is returned as a single row of 10 columns.</span></span>  
  
-   <span data-ttu-id="3520f-106">Un tableau à deux dimensions est retourné au client sous la forme d'un jeu de résultats qui contient autant de colonnes qu'il y a d'éléments dans la première dimension du tableau et autant de lignes qu'il y a d'éléments dans la seconde dimension du tableau.</span><span class="sxs-lookup"><span data-stu-id="3520f-106">A two-dimensional array is returned to the client as a result set with as many columns as there are elements in the first dimension of the array and with as many rows as there are elements in the second dimension of the array.</span></span> <span data-ttu-id="3520f-107">Par exemple, array(2,3) est retourné sous la forme de 2 colonnes sur 3 lignes.</span><span class="sxs-lookup"><span data-stu-id="3520f-107">For example, an array(2,3) is returned as 2 columns in 3 rows.</span></span>  
  
 <span data-ttu-id="3520f-108">Lorsque la valeur de retour d'une propriété ou d'une méthode est un tableau, sp_OAGetProperty ou sp_OAMethod retourne un jeu de résultats au client.</span><span class="sxs-lookup"><span data-stu-id="3520f-108">When a property return value or method return value is an array, sp_OAGetProperty or sp_OAMethod returns a result set to the client.</span></span> <span data-ttu-id="3520f-109">(Les paramètres de sortie de la méthode ne peuvent pas être des tableaux). Ces procédures analysent toutes les valeurs de données dans le tableau pour déterminer les types de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et les longueurs de données appropriés à utiliser pour chaque colonne du jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="3520f-109">(Method output parameters cannot be arrays.) These procedures scan all the data values in the array to determine the appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types and data lengths to use for each column in the result set.</span></span> <span data-ttu-id="3520f-110">Pour une colonne particulière, ces procédures utilisent le type de données et la longueur requis pour représenter toutes les valeurs des données de cette colonne.</span><span class="sxs-lookup"><span data-stu-id="3520f-110">For a particular column, these procedures use the data type and length required to represent all data values in that column.</span></span>  
  
 <span data-ttu-id="3520f-111">Lorsque toutes les valeurs de données d'une colonne partagent le même type de données, ce type est utilisé pour toute la colonne.</span><span class="sxs-lookup"><span data-stu-id="3520f-111">When all data values in a column share the same data type, that data type is used for the whole column.</span></span> <span data-ttu-id="3520f-112">Lorsque les valeurs de données d'une colonne utilisent des types de données différents, le choix du type de données pour l'ensemble de la colonne est basé sur le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="3520f-112">When data values in a column are different data types, the data type of the whole column is chosen based on the following table.</span></span> <span data-ttu-id="3520f-113">Pour utiliser le tableau suivant, recherchez un type de données le long de l'axe des lignes gauche et un second type de données le long de l'axe des colonnes supérieur.</span><span class="sxs-lookup"><span data-stu-id="3520f-113">To use the following table, find one data type along the left row axis and a second data type along the top column axis.</span></span> <span data-ttu-id="3520f-114">L'intersection de la ligne et de la colonne décrit le type de données de la colonne de jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="3520f-114">The intersection of the row and column describes the data type of the result set column.</span></span>  
  
||||||||  
|-|-|-|-|-|-|-|  
||`int`|`float`|`money`|`datetime`|`varchar`|`nvarchar`|  
|`int`|`int`|`float`|`money`|`varchar`|`varchar`|`nvarchar`|  
|`float`|`float`|`float`|`money`|`varchar`|`varchar`|`nvarchar`|  
|`money`|`money`|`money`|`money`|`varchar`|`varchar`|`nvarchar`|  
|`datetime`|`varchar`|`varchar`|`varchar`|`datetime`|`varchar`|`nvarchar`|  
|`varchar`|`varchar`|`varchar`|`varchar`|`varchar`|`varchar`|`nvarchar`|  
|`nvarchar`|`nvarchar`|`nvarchar`|`nvarchar`|`nvarchar`|`nvarchar`|`nvarchar`|  
  
## <a name="related-content"></a><span data-ttu-id="3520f-115">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="3520f-115">Related Content</span></span>  
 [<span data-ttu-id="3520f-116">Procédures stockées OLE Automation &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3520f-116">OLE Automation Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/ole-automation-stored-procedures-transact-sql)  
  
 [<span data-ttu-id="3520f-117">Procédures OLE Automation (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="3520f-117">Ole Automation Procedures Server Configuration Option</span></span>](../../database-engine/configure-windows/ole-automation-procedures-server-configuration-option.md)  
  
  
