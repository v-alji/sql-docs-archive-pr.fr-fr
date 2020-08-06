---
title: Types de curseurs | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, cursors
- ODBC applications, cursors
- cursors [ODBC], types
- ODBC cursors, types
ms.assetid: 3a916cc7-f352-42cb-8b83-f78e06cef991
author: rothja
ms.author: jroth
ms.openlocfilehash: 6937dbb9ce42cd5631201e0c97be42b211742ada
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603526"
---
# <a name="cursor-types"></a><span data-ttu-id="467ed-102">Types de curseurs</span><span class="sxs-lookup"><span data-stu-id="467ed-102">Cursor Types</span></span>
  <span data-ttu-id="467ed-103">ODBC définit quatre types de curseurs pris en charge par Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client.</span><span class="sxs-lookup"><span data-stu-id="467ed-103">ODBC defines four cursor types supported by Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="467ed-104">Ces curseurs varient en fonction de leur capacité à détecter les modifications apportées au jeu de résultats et aux ressources qu’ils consomment, telles que la mémoire et l’espace dans **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="467ed-104">These cursors vary in their ability to detect changes to the result set and in the resources they consume, such as memory and space in **tempdb**.</span></span> <span data-ttu-id="467ed-105">Un curseur peut détecter des modifications apportées à des lignes uniquement lorsqu'il tente d'extraire à nouveau ces lignes ; il n'existe aucun moyen pour la source de données d'informer le curseur des modifications apportées aux lignes en cours d'extraction.</span><span class="sxs-lookup"><span data-stu-id="467ed-105">A cursor can detect changes to rows only when it tries to refetch those rows; there is no way for the data source to notify the cursor of changes to the currently fetched rows.</span></span> <span data-ttu-id="467ed-106">La capacité d'un curseur à détecter des modifications qui n'ont pas été apportées par le biais du curseur est également influencée par le niveau d'isolation de la transaction.</span><span class="sxs-lookup"><span data-stu-id="467ed-106">A cursor's ability to detect changes that were not made through the cursor is also influenced by the transaction isolation level.</span></span>  
  
 <span data-ttu-id="467ed-107">Les quatre types de curseurs ODBC pris en charge par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="467ed-107">These are the four ODBC cursor types supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="467ed-108">Les curseurs avant uniquement ne prennent pas en charge le défilement, mais seulement l'extraction de lignes en séquence à partir du début jusqu'à la fin du curseur.</span><span class="sxs-lookup"><span data-stu-id="467ed-108">Forward-only cursors do not support scrolling; they only support fetching rows serially from the start to the end of the cursor.</span></span>  
  
-   <span data-ttu-id="467ed-109">Les curseurs statiques sont créés dans **tempdb** lorsque le curseur est ouvert.</span><span class="sxs-lookup"><span data-stu-id="467ed-109">Static cursors are built in **tempdb** when the cursor is opened.</span></span> <span data-ttu-id="467ed-110">Ils affichent toujours l'ensemble de résultats tel qu'il était au moment où le curseur a été ouvert.</span><span class="sxs-lookup"><span data-stu-id="467ed-110">They always display the result set as it was when the cursor was opened.</span></span> <span data-ttu-id="467ed-111">Ils ne reflètent jamais les modifications apportées aux données.</span><span class="sxs-lookup"><span data-stu-id="467ed-111">They never reflect changes to the data.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="467ed-112">Les curseurs statiques sont toujours en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="467ed-112">static cursors are always read-only.</span></span> <span data-ttu-id="467ed-113">Étant donné qu’un curseur de serveur statique est créé en tant que table de travail dans **tempdb**, la taille du jeu de résultats du curseur ne peut pas dépasser la taille de ligne maximale autorisée par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="467ed-113">Because a static server cursor is built as a work table in **tempdb**, the size of the cursor result set cannot exceed the maximum row size allowed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="467ed-114">L'appartenance et l'ordre des lignes dans le jeu de résultats des curseurs de jeux de clés sont fixés au moment de l'ouverture du curseur.</span><span class="sxs-lookup"><span data-stu-id="467ed-114">Keyset-driven cursors have the membership and order of rows in the result set fixed when the cursor is opened.</span></span> <span data-ttu-id="467ed-115">Les modifications aux colonnes non-clés sont visibles à travers le curseur.</span><span class="sxs-lookup"><span data-stu-id="467ed-115">Changes to nonkey columns are visible through the cursor.</span></span>  
  
-   <span data-ttu-id="467ed-116">Les curseurs dynamiques sont le contraire des curseurs statiques.</span><span class="sxs-lookup"><span data-stu-id="467ed-116">Dynamic cursors are the opposite of static cursors.</span></span> <span data-ttu-id="467ed-117">Les curseurs dynamiques reflètent toutes les modifications apportées aux lignes de leur jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="467ed-117">Dynamic cursors reflect all changes made to the rows in their result set.</span></span> <span data-ttu-id="467ed-118">Les valeurs des données, l'ordre et l'appartenance des lignes du jeu de résultats peuvent changer à chaque extraction.</span><span class="sxs-lookup"><span data-stu-id="467ed-118">The data values, order, and membership of the rows in the result set can change on each fetch.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="467ed-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="467ed-119">See Also</span></span>  
 [<span data-ttu-id="467ed-120">Utilisation de curseurs &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="467ed-120">Using Cursors &#40;ODBC&#41;</span></span>](using-cursors-odbc.md)  
  
  
