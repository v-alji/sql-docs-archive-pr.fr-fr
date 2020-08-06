---
title: Traitement des résultats | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, results processing
- OLE DB, processing results
- rowsets [SQL Server], results processing
- results [SQL Server Native Client]
ms.assetid: 20887ac4-f649-4e7f-92e6-f929e2e70952
author: rothja
ms.author: jroth
ms.openlocfilehash: b9e5bf00b4d2e554536c9f2ba1a328390b93a8a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612785"
---
# <a name="processing-results"></a><span data-ttu-id="cbd97-102">Traitement des résultats</span><span class="sxs-lookup"><span data-stu-id="cbd97-102">Processing Results</span></span>
  <span data-ttu-id="cbd97-103">Si un objet d'ensemble de ligne est produit par l'exécution d'une commande ou la génération d'un objet d'ensemble de ligne directement à partir du fournisseur, le consommateur doit extraire et accéder aux données dans l'ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="cbd97-103">If a rowset object is produced by either the execution of a command or the generation of a rowset object directly from the provider, the consumer needs to retrieve and access data in the rowset.</span></span>  
  
 <span data-ttu-id="cbd97-104">Les ensembles de lignes sont les objets centraux qui permettent au fournisseur OLE DB [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client d'exposer des données au format tabulaire.</span><span class="sxs-lookup"><span data-stu-id="cbd97-104">Rowsets are the central objects that enable the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider to expose data in tabular form.</span></span> <span data-ttu-id="cbd97-105">Conceptuellement, un ensemble de lignes est un jeu de lignes dans lequel chaque ligne possède des données de colonne.</span><span class="sxs-lookup"><span data-stu-id="cbd97-105">Conceptually, a rowset is a set of rows in which each row has column data.</span></span> <span data-ttu-id="cbd97-106">Un objet d’ensemble de ligne expose des interfaces comme **IRowset** (contient des méthodes pour extraire des lignes de l’ensemble de lignes de manière séquentielle), **IAccessor** (autorise la définition d’un groupe de liaisons de colonnes qui décrivent la manière dont les données tabulaires sont liées aux variables du programme de consommateur), **IColumnsInfo** (fournit des informations sur les colonnes de l’ensemble de lignes) et **IRowsetInfo** (fournit des informations sur l’ensemble de lignes).</span><span class="sxs-lookup"><span data-stu-id="cbd97-106">A rowset object exposes interfaces such as **IRowset** (contains methods for fetching rows from the rowset sequentially), **IAccessor** (permits the definition of a group of column bindings describing the way tabular data is bound to consumer program variables), **IColumnsInfo** (provides information about columns in the rowset), and **IRowsetInfo** (provides information about rowset).</span></span>  
  
 <span data-ttu-id="cbd97-107">Un consommateur peut appeler la méthode **IRowset::GetData** pour extraire une ligne de données de l’ensemble de lignes dans une mémoire tampon.</span><span class="sxs-lookup"><span data-stu-id="cbd97-107">A consumer can call the **IRowset::GetData** method to retrieve a row of data from the rowset into a buffer.</span></span> <span data-ttu-id="cbd97-108">Avant que **GetData** ne soit appelé, le consommateur décrit la mémoire tampon à l’aide d’un jeu de structures DBBINDING.</span><span class="sxs-lookup"><span data-stu-id="cbd97-108">Before **GetData** is called, the consumer describes the buffer using a set of DBBINDING structures.</span></span> <span data-ttu-id="cbd97-109">Chaque liaison décrit la manière dont une colonne dans un ensemble de lignes est stockée dans une mémoire tampon de consommateur et contient les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="cbd97-109">Each binding describes how a column in a rowset is stored in a consumer buffer and contains the following:</span></span>  
  
-   <span data-ttu-id="cbd97-110">ordinal de la colonne (ou paramètre) auquel la liaison s'applique ;</span><span class="sxs-lookup"><span data-stu-id="cbd97-110">Ordinal of the column (or parameter) to which the binding applies.</span></span>  
  
-   <span data-ttu-id="cbd97-111">informations concernant ce qui est lié (par exemple, valeur des données, longueur des données et leur état de liaison) ;</span><span class="sxs-lookup"><span data-stu-id="cbd97-111">Information about what is bound (for example, data value, length of the data, and its binding status).</span></span>  
  
-   <span data-ttu-id="cbd97-112">informations concernant ce qui est décalé dans la mémoire tampon à chacune de ces parties ;</span><span class="sxs-lookup"><span data-stu-id="cbd97-112">Information about what is offset in the buffer to each of these parts.</span></span>  
  
-   <span data-ttu-id="cbd97-113">longueur et type des valeurs de données telles qu'elles existent dans la mémoire tampon du consommateur.</span><span class="sxs-lookup"><span data-stu-id="cbd97-113">Length and type of the data values as they exist in the consumer buffer.</span></span>  
  
 <span data-ttu-id="cbd97-114">Lors de l'obtention des données, le fournisseur utilise les informations dans chaque liaison afin de déterminer où et comment extraire des données de la mémoire tampon du consommateur.</span><span class="sxs-lookup"><span data-stu-id="cbd97-114">When getting the data, the provider uses information in each binding to determine where and how to retrieve data from the consumer buffer.</span></span> <span data-ttu-id="cbd97-115">Lors de la définition des données dans la mémoire tampon du consommateur, le fournisseur utilise les informations dans chaque liaison afin de déterminer où et comment retourner des données dans la mémoire tampon du consommateur.</span><span class="sxs-lookup"><span data-stu-id="cbd97-115">When setting data in the consumer buffer, the provider uses information in each binding to determine where and how to return data in the consumer's buffer.</span></span>  
  
 <span data-ttu-id="cbd97-116">Une fois les structures DBBINDING spécifiées, un accesseur est créé (**IAccessor::CreateAccessor**).</span><span class="sxs-lookup"><span data-stu-id="cbd97-116">After the DBBINDING structures are specified, an accessor is created (**IAccessor::CreateAccessor**).</span></span> <span data-ttu-id="cbd97-117">Un accesseur est une collection de liaisons utilisée pour obtenir ou définir les données dans la mémoire tampon du consommateur.</span><span class="sxs-lookup"><span data-stu-id="cbd97-117">An accessor is a collection of bindings and is used to get or set the data in the consumer buffer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbd97-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cbd97-118">See Also</span></span>  
 <span data-ttu-id="cbd97-119">[Création d’une application SQL Server Native Client OLE DB Provider](creating-a-sql-server-native-client-ole-db-provider-application.md) </span><span class="sxs-lookup"><span data-stu-id="cbd97-119">[Creating a SQL Server Native Client OLE DB Provider Application](creating-a-sql-server-native-client-ole-db-provider-application.md) </span></span>  
 [<span data-ttu-id="cbd97-120">Rubriques de procédures liées à OLE DB</span><span class="sxs-lookup"><span data-stu-id="cbd97-120">OLE DB How-to Topics</span></span>](../native-client-ole-db-how-to/ole-db-how-to-topics.md)  
  
  
