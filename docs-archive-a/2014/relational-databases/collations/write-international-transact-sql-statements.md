---
title: Rédiger des instructions Transact-SQL internationales | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- writing international statements
- Transact-SQL international considerations
- international considerations [SQL Server], Transact-SQL
- Database Engine international considerations [SQL Server], Transact-SQL
- statements [SQL Server], international
- database international considerations [SQL Server], Transact-SQL
- dates [SQL Server], international considerations
ms.assetid: f0b10fee-27f7-45fe-aece-ccc3f63bdcdb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1888d1045e43e0a9839fd76a21c51500af63539a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614642"
---
# <a name="write-international-transact-sql-statements"></a><span data-ttu-id="fcf71-102">Rédiger des instructions Transact-SQL internationales</span><span class="sxs-lookup"><span data-stu-id="fcf71-102">Write International Transact-SQL Statements</span></span>
  <span data-ttu-id="fcf71-103">Les directives suivantes facilitent la transition d'une langue à l'autre des bases de données et applications de bases de données qui utilisent des instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] , ou leur permettent de prendre en charge directement plusieurs langues :</span><span class="sxs-lookup"><span data-stu-id="fcf71-103">Databases and database applications that use [!INCLUDE[tsql](../../includes/tsql-md.md)] statements will become more portable from one language to another, or will support multiple languages, if the following guidelines are followed:</span></span>  
  
-   <span data-ttu-id="fcf71-104">Remplacez toutes les utilisations des types de données `char`, `varchar`, et `text` par `nchar`, `nvarchar`, et `nvarchar(max)`.</span><span class="sxs-lookup"><span data-stu-id="fcf71-104">Replace all uses of the `char`, `varchar`, and `text` data types with `nchar`, `nvarchar`, and `nvarchar(max)`.</span></span> <span data-ttu-id="fcf71-105">Vous réglez ainsi le problème de conversion des pages de codes.</span><span class="sxs-lookup"><span data-stu-id="fcf71-105">By doing this, you do not have to consider code page conversion issues.</span></span> <span data-ttu-id="fcf71-106">Pour plus d’informations, consultez [Prise en charge d’Unicode et du classement](collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="fcf71-106">For more information, see [Collation and Unicode Support](collation-and-unicode-support.md).</span></span>  
  
-   <span data-ttu-id="fcf71-107">Lors des comparaisons et opérations sur les mois et jours de la semaine, utilisez la partie numérique de la date plutôt que les chaînes de noms.</span><span class="sxs-lookup"><span data-stu-id="fcf71-107">When you perform month and day-of-week comparisons and operations, use the numeric date parts instead of the name strings.</span></span> <span data-ttu-id="fcf71-108">Selon les paramètres de langue, des noms de mois et de jours de la semaine différents sont retournés.</span><span class="sxs-lookup"><span data-stu-id="fcf71-108">Different language settings return different names for the months and weekdays.</span></span> <span data-ttu-id="fcf71-109">Par exemple, DATENAME(MONTH,GETDATE()) retourne « May » pour l'anglais (États-Unis), « Mai » pour l'allemand et « mai » pour le français.</span><span class="sxs-lookup"><span data-stu-id="fcf71-109">For example, DATENAME(MONTH,GETDATE()) returns May when the language is set to U.S. English, returns Mai when the language is set to German, and returns mai when the language is set to French.</span></span> <span data-ttu-id="fcf71-110">Utilisez à la place une fonction comme DATEPART qui utilise le numéro du mois plutôt que son nom.</span><span class="sxs-lookup"><span data-stu-id="fcf71-110">Instead, use a function such as DATEPART that uses the number of the month instead of the name.</span></span> <span data-ttu-id="fcf71-111">Utilisez les noms DATEPART lorsque vous générez des ensembles de résultats qui seront affichés par un utilisateur, car les noms de date sont souvent plus clairs qu'une représentation numérique.</span><span class="sxs-lookup"><span data-stu-id="fcf71-111">Use the DATEPART names when you build result sets to be displayed to a user, because the date names are frequently more meaningful than a numeric representation.</span></span> <span data-ttu-id="fcf71-112">Pour autant, ne codez aucun élément logique dépendant des noms affichés d'une langue spécifique.</span><span class="sxs-lookup"><span data-stu-id="fcf71-112">However, do not code any logic that depends on the displayed names being from a specific language.</span></span>  
  
-   <span data-ttu-id="fcf71-113">Pour spécifier des dates dans des comparaisons ou comme entrées d'instructions INSERT ou UPDATE, utilisez des constantes qui sont interprétées de la même manière, quelle que soit la langue définie :</span><span class="sxs-lookup"><span data-stu-id="fcf71-113">When you specify dates in comparisons or for input to INSERT or UPDATE statements, use constants that are interpreted the same way for all language settings:</span></span>  
  
    -   <span data-ttu-id="fcf71-114">Les applications ADO, OLE DB et ODBC doivent utiliser les clauses ODBC d'échappement de temps, de date et d'horodateur :</span><span class="sxs-lookup"><span data-stu-id="fcf71-114">ADO, OLE DB, and ODBC applications should use the ODBC timestamp, date, and time escape clauses of:</span></span>  
  
         <span data-ttu-id="fcf71-115">**{ts'** yyyy **-** _mm_ **-** _DDHH_**:**_mm_**:**_SS_[**.** _fff_] **'}** par exemple : **{ts'** 1998 **-** 09 **-** 24 10 **:** 02 **:** 20 **'}**</span><span class="sxs-lookup"><span data-stu-id="fcf71-115">**{ ts'** yyyy**-**_mm_**-**_ddhh_**:**_mm_**:**_ss_[**.**_fff_] **'}** such as: **{ ts'** 1998**-** 09**-** 24 10 **:** 02 **:** 20 **' }**</span></span>  
  
         <span data-ttu-id="fcf71-116">**{ d'** _yyyy_ **-** _mm_ **-** _dd_ **'}** tel que : **{ d'** 1998**-** 09**-** 24 **'}**</span><span class="sxs-lookup"><span data-stu-id="fcf71-116">**{ d'** _yyyy_ **-** _mm_ **-** _dd_ **'}** such as: **{ d'** 1998**-** 09**-** 24 **'}**</span></span>  
  
         <span data-ttu-id="fcf71-117">**{t'** _hh_ **:** _mm_ **:** _SS_ **'}** tel que : **{t'** 10:02:20 **'}**</span><span class="sxs-lookup"><span data-stu-id="fcf71-117">**{ t'** _hh_ **:** _mm_ **:** _ss_ **'}** such as: **{ t'** 10:02:20 **'}**</span></span>  
  
    -   <span data-ttu-id="fcf71-118">Les applications qui utilisent d'autres API, ou encore des scripts, des procédures stockées ou des déclencheurs [!INCLUDE[tsql](../../includes/tsql-md.md)] , doivent utiliser les chaînes numériques non séparées.</span><span class="sxs-lookup"><span data-stu-id="fcf71-118">Applications that use other APIs, or [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, stored procedures, and triggers, should use the unseparated numeric strings.</span></span> <span data-ttu-id="fcf71-119">Par exemple, *yyyymmdd* comme 19980924.</span><span class="sxs-lookup"><span data-stu-id="fcf71-119">For example, *yyyymmdd* as 19980924.</span></span>  
  
    -   <span data-ttu-id="fcf71-120">Les applications qui utilisent d’autres API, ou des [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, des procédures stockées et des déclencheurs doivent utiliser l’instruction CONVERT avec un paramètre de style explicite pour toutes les conversions entre les `time` types de `date` données,, `smalldate` , `datetime` , **datetime2**et de type `datetimeoffset` chaîne de caractères.</span><span class="sxs-lookup"><span data-stu-id="fcf71-120">Applications that use other APIs, or [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, stored procedures, and triggers should use the CONVERT statement with an explicit style parameter for all conversions between the `time`, `date`, `smalldate`, `datetime`, **datetime2**, and `datetimeoffset` data types and character string data types.</span></span> <span data-ttu-id="fcf71-121">Par exemple, l'instruction suivante est interprétée de la même façon, quels que soient les paramètres de connexion concernant la langue et le format de date :</span><span class="sxs-lookup"><span data-stu-id="fcf71-121">For example, the following statement is interpreted in the same way for all language or date format connection settings:</span></span>  
  
        ```  
        SELECT *  
        FROM AdventureWorks2012.Sales.SalesOrderHeader  
        WHERE OrderDate = CONVERT(DATETIME, '20060719', 101)  
        ```  
  
         <span data-ttu-id="fcf71-122">Pour plus d’informations, consultez [CAST et CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fcf71-122">For more information, see [CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
  
