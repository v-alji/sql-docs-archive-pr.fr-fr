---
title: Utiliser le concepteur de requêtes et de vues avec des données internationales (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Visual Database Tools [SQL Server], international data
- queries [SQL Server], international data
- languages [SQL Server], Query and View Designer
- international considerations [SQL Server], Query and View Designer
- Criteria pane
- View Designer, international data
- Query Designer [SQL Server], international data
- localized information in Query and View Designer [SQL Server]
- global considerations [SQL Server], Query and View Designer
- SQL pane [Visual Database Tools]
- multiple language support [SQL Server], Query and View Designer
ms.assetid: 4b51c56f-f902-4e72-b919-e36127369b63
author: stevestein
ms.author: sstein
ms.openlocfilehash: 905e4c6909c792b019c11ef95662a7ec1a113bb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703668"
---
# <a name="use-the-query-and-view-designer-with-international-data-visual-database-tools"></a><span data-ttu-id="6a683-102">Utiliser le Concepteur de requêtes et de vues avec des données internationales (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="6a683-102">Use the Query and View Designer with International Data (Visual Database Tools)</span></span>
  <span data-ttu-id="6a683-103">Vous pouvez utiliser le [Concepteur de requêtes et de vues](visual-database-tools.md) quelle que soit la langue utilisée dans les données et le système d’exploitation Windows.</span><span class="sxs-lookup"><span data-stu-id="6a683-103">You can use the [Query and View Designer](visual-database-tools.md) with data in any language and in any version of the Windows operating system.</span></span> <span data-ttu-id="6a683-104">Vous trouverez ci-dessous les quelques différences que vous pourrez rencontrer ainsi que des informations sur la gestion des données dans des applications internationales.</span><span class="sxs-lookup"><span data-stu-id="6a683-104">The following guidelines outline the differences you will notice and provide information about managing data in international applications.</span></span>  
  
## <a name="localized-information-in-the-criteria-and-sql-panes"></a><span data-ttu-id="6a683-105">Informations localisées dans les volets Critères et SQL</span><span class="sxs-lookup"><span data-stu-id="6a683-105">Localized Information in the Criteria and SQL Panes</span></span>  
 <span data-ttu-id="6a683-106">Si vous utilisez le volet Critères pour créer votre requête, vous pouvez entrer vos informations dans le format prévu sur votre ordinateur, dans les Paramètres régionaux de Windows.</span><span class="sxs-lookup"><span data-stu-id="6a683-106">If you are using the Criteria pane to create your query, you can enter information in the format that corresponds to the Windows Regional Settings for you computer.</span></span> <span data-ttu-id="6a683-107">Par exemple, si vous recherchez des données, vous pouvez entrer les données dans les colonnes Critères en utilisant le format auquel vous êtes habitué, avec les quelques exceptions suivantes :</span><span class="sxs-lookup"><span data-stu-id="6a683-107">For example, if you are searching for data, you can enter the data in the Criteria columns using whatever format you are accustomed to using, with these exceptions:</span></span>  
  
-   <span data-ttu-id="6a683-108">Les formats de données longs ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="6a683-108">Long data formats are not supported.</span></span>  
  
-   <span data-ttu-id="6a683-109">N'utilisez pas de symbole monétaire dans le volet Critères.</span><span class="sxs-lookup"><span data-stu-id="6a683-109">Currency symbols should not be entered in the Criteria pane.</span></span>  
  
-   <span data-ttu-id="6a683-110">Les symboles monétaires ne s'affichent pas dans le volet Résultats.</span><span class="sxs-lookup"><span data-stu-id="6a683-110">Currency symbols will not display in the Results pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6a683-111">Dans le volet Résultats, vous pouvez réellement entrer le symbole monétaire qui correspond aux Paramètres régionaux de Windows pour votre ordinateur, mais ce symbole sera supprimé et ne s'affichera pas dans le volet Résultats.</span><span class="sxs-lookup"><span data-stu-id="6a683-111">In the Results pane, you can actually enter the currency symbol that corresponds to the Windows Regional Settings for your computer, but the symbol will be removed and will not display in the Results pane.</span></span>  
  
-   <span data-ttu-id="6a683-112">L'opérateur moins unaire apparaît toujours à gauche (par exemple, -1) quelles que soient les options choisies dans les Paramètres régionaux.</span><span class="sxs-lookup"><span data-stu-id="6a683-112">Unary minus always appears on the left side (for example, -1) regardless of the Regional Settings options.</span></span>  
  
 <span data-ttu-id="6a683-113">Par contre, les données et les mots clés du volet SQL doivent toujours être au format ANSI (États-Unis).</span><span class="sxs-lookup"><span data-stu-id="6a683-113">In contrast, data and keywords in the SQL pane must always be in ANSI (U.S.) format.</span></span> <span data-ttu-id="6a683-114">Par exemple, lorsque le Concepteur de requêtes et de vues génère une requête, il insère tous les mots clés SQL, tels que SELECT et FROM, au format ANSI.</span><span class="sxs-lookup"><span data-stu-id="6a683-114">For example, as the Query and View Designer builds a query, it inserts the ANSI form of all SQL keywords such as SELECT and FROM.</span></span> <span data-ttu-id="6a683-115">Si vous ajoutez des éléments à l'instruction dans le volet SQL, veillez à ce qu'ils respectent le format ANSI.</span><span class="sxs-lookup"><span data-stu-id="6a683-115">If you add elements to the statement in the SQL pane, be sure to use the ANSI standard form for the elements.</span></span>  
  
 <span data-ttu-id="6a683-116">Lorsque vous entrez des données au format régional dans le volet Critères, le Concepteur de requêtes et de vues les convertit automatiquement au format ANSI dans le volet SQL.</span><span class="sxs-lookup"><span data-stu-id="6a683-116">When you enter data using local-specific format in the Criteria pane, the Query and View Designer automatically translates it to ANSI format in the SQL pane.</span></span> <span data-ttu-id="6a683-117">Par exemple, si le Français (standard) a été choisi dans vos Paramètres régionaux, vous pouvez entrer sur le volet Critères une date au format « 31/12/96 ».</span><span class="sxs-lookup"><span data-stu-id="6a683-117">For example, if your Regional Settings are set to Standard German, you can enter data in the Criteria pane in a format such as "31.12.96."</span></span> <span data-ttu-id="6a683-118">Toutefois, la date apparaîtra dans le volet SQL au format de date et heure ANSI `{ ts '1996-12-31 00:00:00' }.` . Si vous entrez directement des données dans le volet SQL, vous devez les entrer au format ANSI.</span><span class="sxs-lookup"><span data-stu-id="6a683-118">However, the date will appear in the SQL pane in ANSI datetime format as `{ ts '1996-12-31 00:00:00' }.` If you enter data directly in the SQL pane, you must enter it in ANSI format.</span></span>  
  
## <a name="sort-order"></a><span data-ttu-id="6a683-119">Ordre de tri</span><span class="sxs-lookup"><span data-stu-id="6a683-119">Sort Order</span></span>  
 <span data-ttu-id="6a683-120">L'ordre de tri des données d'une requête est déterminé par la base de données.</span><span class="sxs-lookup"><span data-stu-id="6a683-120">The sort order of data in your query is determined by the database.</span></span> <span data-ttu-id="6a683-121">Les options définies dans la boîte de dialogue Paramètres régionaux de Windows n'affectent pas l'ordre de tri des requêtes.</span><span class="sxs-lookup"><span data-stu-id="6a683-121">Options that you set in the Windows Regional Settings dialog box do not affect sort order for queries.</span></span> <span data-ttu-id="6a683-122">Cependant, à l'intérieur d'une requête, vous pouvez demander un tri selon un ordre particulier.</span><span class="sxs-lookup"><span data-stu-id="6a683-122">Within any particular query, however, you can request that rows be returned in a particular order.</span></span>  
  
## <a name="using-double-byte-characters"></a><span data-ttu-id="6a683-123">Utilisation de caractères codés sur deux octets</span><span class="sxs-lookup"><span data-stu-id="6a683-123">Using Double-Byte Characters</span></span>  
 <span data-ttu-id="6a683-124">Les caractères codés sur deux octets, ou caractères DBCS (Double Byte Character Set), peuvent être utilisés pour des noms d'objets de bases de données tels que des noms de tables et de vues ou d'alias.</span><span class="sxs-lookup"><span data-stu-id="6a683-124">You can enter DBCS characters for literals and for database object names such as table and view names or aliases.</span></span> <span data-ttu-id="6a683-125">Vous pouvez également les utiliser pour des noms de paramètres et des marqueurs de paramètres.</span><span class="sxs-lookup"><span data-stu-id="6a683-125">You can also use DBCS characters for parameter names and parameter marker characters.</span></span> <span data-ttu-id="6a683-126">Cependant, vous ne pouvez pas les utiliser dans des éléments du langage SQL tels que des noms de fonctions ou des mots clés SQL.</span><span class="sxs-lookup"><span data-stu-id="6a683-126">However, you cannot use DBCS characters in SQL language elements such as function names or SQL keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a683-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6a683-127">See Also</span></span>  
 [<span data-ttu-id="6a683-128">Rubriques de procédures relatives à la conception de requêtes et de vues &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="6a683-128">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
