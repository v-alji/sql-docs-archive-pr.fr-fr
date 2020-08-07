---
title: Formats de données pour l’importation en bloc ou l’exportation en bloc (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- data formats [SQL Server], choosing
- bulk importing [SQL Server], data formats
ms.assetid: 73fe6741-9437-4b26-b030-28b863e74399
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1b92ac8c038362ff18a1459a8bf3c55b6b596a17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600009"
---
# <a name="data-formats-for-bulk-import-or-bulk-export-sql-server"></a><span data-ttu-id="e05aa-102">Formats de données pour l'importation en bloc ou l'exportation en bloc (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e05aa-102">Data Formats for Bulk Import or Bulk Export (SQL Server)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e05aa-103">peut accepter des données dans un format caractère ou binaire natif.</span><span class="sxs-lookup"><span data-stu-id="e05aa-103">can accept data in character data format or native binary data format.</span></span> <span data-ttu-id="e05aa-104">Utilisez le format caractère lorsque vous déplacez des données entre [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et une autre application (telle que [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel) ou un autre serveur de base de données (tel que Oracle ou [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="e05aa-104">Use character format when you move data between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and another application (such as [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel) or another database server (such as Oracle or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]).</span></span> <span data-ttu-id="e05aa-105">Vous ne pouvez utiliser le format natif que lorsque vous transférez des données entre des instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e05aa-105">You can use native format only when you transfer data between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="e05aa-106">**Dans cette rubrique :**</span><span class="sxs-lookup"><span data-stu-id="e05aa-106">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="e05aa-107">Formats de données pour l'importation ou l'exportation en bloc</span><span class="sxs-lookup"><span data-stu-id="e05aa-107">Data Formats for Bulk Import or Export</span></span>](#ComponentsAndConcepts)  
  
-   [<span data-ttu-id="e05aa-108">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="e05aa-108">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="data-formats-for-bulk-import-or-export"></a><a name="ComponentsAndConcepts"></a> <span data-ttu-id="e05aa-109">Formats de données pour l'importation ou l'exportation en bloc</span><span class="sxs-lookup"><span data-stu-id="e05aa-109">Data Formats for Bulk Import or Export</span></span>  
 <span data-ttu-id="e05aa-110">Le tableau suivant indique le format de données à utiliser en fonction de la représentation des données et de la source ou de la cible de l'opération.</span><span class="sxs-lookup"><span data-stu-id="e05aa-110">The following table indicates what data format is generally appropriate to use depending on how the data is represented and the source or target of the operation.</span></span>  
  
|<span data-ttu-id="e05aa-111">Opération</span><span class="sxs-lookup"><span data-stu-id="e05aa-111">Operation</span></span>|<span data-ttu-id="e05aa-112">Natif</span><span class="sxs-lookup"><span data-stu-id="e05aa-112">Native</span></span>|<span data-ttu-id="e05aa-113">Natif Unicode</span><span class="sxs-lookup"><span data-stu-id="e05aa-113">Unicode native</span></span>|<span data-ttu-id="e05aa-114">Caractère</span><span class="sxs-lookup"><span data-stu-id="e05aa-114">Character</span></span>|<span data-ttu-id="e05aa-115">Caractère Unicode</span><span class="sxs-lookup"><span data-stu-id="e05aa-115">Unicode character</span></span>|  
|---------------|------------|--------------------|---------------|-----------------------|  
|<span data-ttu-id="e05aa-116">Transferts en bloc de données entre plusieurs instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'aide d'un fichier de données qui ne contient aucun caractère étendu ou codé sur deux octets (DBCS).</span><span class="sxs-lookup"><span data-stu-id="e05aa-116">Bulk transfers of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that does not contain any extended or double-byte character set (DBCS) characters.</span></span> <span data-ttu-id="e05aa-117">Sauf si un fichier de format est utilisé, ces tables doivent être définies de façon identique.</span><span class="sxs-lookup"><span data-stu-id="e05aa-117">Unless a format file is used, these tables must be identically defined.</span></span>|<span data-ttu-id="e05aa-118">Oui<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e05aa-118">Yes<sup>1</sup></span></span>|-|-|-|  
|<span data-ttu-id="e05aa-119">Pour les colonnes `sql_variant`, il est préférable d'utiliser le format de données natif, car il conserve les métadonnées de chaque valeur `sql_variant`, à la différence des formats caractère ou Unicode.</span><span class="sxs-lookup"><span data-stu-id="e05aa-119">For `sql_variant` columns, use of native data format is best, because native data format preserves the metadata for each `sql_variant` value, unlike character or Unicode formats.</span></span>|<span data-ttu-id="e05aa-120">Oui</span><span class="sxs-lookup"><span data-stu-id="e05aa-120">Yes</span></span>|-|-|-|  
|<span data-ttu-id="e05aa-121">Transferts en bloc de données entre plusieurs instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'aide d'un fichier de données qui contient des caractères étendus ou DBCS.</span><span class="sxs-lookup"><span data-stu-id="e05aa-121">Bulk transfers of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains extended or DBCS characters.</span></span>|-|<span data-ttu-id="e05aa-122">Oui</span><span class="sxs-lookup"><span data-stu-id="e05aa-122">Yes</span></span>|-|-|  
|<span data-ttu-id="e05aa-123">Importation en bloc de données à partir d'un fichier texte généré par un autre programme.</span><span class="sxs-lookup"><span data-stu-id="e05aa-123">Bulk import of data from a text file that is generated by another program.</span></span>|-|-|<span data-ttu-id="e05aa-124">Oui</span><span class="sxs-lookup"><span data-stu-id="e05aa-124">Yes</span></span>|-|  
|<span data-ttu-id="e05aa-125">Exportation en bloc de données vers un fichier texte à utiliser dans un autre programme.</span><span class="sxs-lookup"><span data-stu-id="e05aa-125">Bulk export of data to a text file that is to be used in another program.</span></span>|-|-|<span data-ttu-id="e05aa-126">Oui</span><span class="sxs-lookup"><span data-stu-id="e05aa-126">Yes</span></span>|-|  
|<span data-ttu-id="e05aa-127">Transferts en bloc de données entre plusieurs instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'aide d'un fichier de données qui contient des données Unicode et qui ne comporte aucun caractère étendu ou DBCS.</span><span class="sxs-lookup"><span data-stu-id="e05aa-127">Bulk transfers of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains Unicode data and does not contain any extended or DBCS characters.</span></span>|-|-|-|<span data-ttu-id="e05aa-128">Oui</span><span class="sxs-lookup"><span data-stu-id="e05aa-128">Yes</span></span>|  
  
 <span data-ttu-id="e05aa-129"><sup>1</sup> méthode la plus rapide pour l’exportation en bloc de données à partir de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] lors de l’utilisation de **BCP**.</span><span class="sxs-lookup"><span data-stu-id="e05aa-129"><sup>1</sup> Fastest method for the bulk export of data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] when using **bcp**.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="e05aa-130">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="e05aa-130">Related Tasks</span></span>  
  
-   [<span data-ttu-id="e05aa-131">Utiliser le format natif pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e05aa-131">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="e05aa-132">Utiliser le format caractère pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e05aa-132">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="e05aa-133">Utiliser le format natif Unicode pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e05aa-133">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="e05aa-134">Utiliser le format caractère Unicode pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e05aa-134">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="e05aa-135">Importer des données au format natif et caractère à partir de versions antérieures de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e05aa-135">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="e05aa-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e05aa-136">See Also</span></span>  
 <span data-ttu-id="e05aa-137">[Types de données &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e05aa-137">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 [<span data-ttu-id="e05aa-138">Spécifier des formats de données pour la compatibilité lors de l’utilisation de bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e05aa-138">Specify Data Formats for Compatibility when Using bcp &#40;SQL Server&#41;</span></span>](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md)  
  
  
