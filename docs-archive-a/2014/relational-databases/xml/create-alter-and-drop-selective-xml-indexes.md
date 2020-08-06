---
title: Créer, modifier ou supprimer des index XML sélectifs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
ms.assetid: c398f396-f630-4a2d-a264-f243c5346de1
author: rothja
ms.author: jroth
ms.openlocfilehash: bf4123a46cc13359c936e6f9cfc0db3dcfdaa175
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697608"
---
# <a name="create-alter-and-drop-selective-xml-indexes"></a><span data-ttu-id="ab7cb-102">Créer, modifier ou supprimer des index XML sélectifs</span><span class="sxs-lookup"><span data-stu-id="ab7cb-102">Create, Alter, and Drop Selective XML Indexes</span></span>
  <span data-ttu-id="ab7cb-103">Décrit la procédure de création d'un index XML sélectif, ou de modification ou de suppression d'un index XML sélectif existant.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-103">Describes how to create a new selective XML index, or alter or drop an existing selective XML index.</span></span>  
  
 <span data-ttu-id="ab7cb-104">Pour plus d’informations sur les index XML sélectifs, consultez [Index XML sélectifs &#40;SXI&#41;](selective-xml-indexes-sxi.md).</span><span class="sxs-lookup"><span data-stu-id="ab7cb-104">For more information about selective XML indexes, see [Selective XML Indexes &#40;SXI&#41;](selective-xml-indexes-sxi.md).</span></span>  
  
##  <a name="creating-a-selective-xml-index"></a><a name="create"></a> <span data-ttu-id="ab7cb-105">Création d'un index XML sélectif</span><span class="sxs-lookup"><span data-stu-id="ab7cb-105">Creating a Selective XML Index</span></span>  
  
### <a name="how-to-create-a-selective-xml-index"></a><span data-ttu-id="ab7cb-106">Procédure : Créer un index XML sélectif</span><span class="sxs-lookup"><span data-stu-id="ab7cb-106">How to: Create a Selective XML Index</span></span>  
 <span data-ttu-id="ab7cb-107">**Créer un index XML sélectif à l'aide de Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="ab7cb-107">**Create a Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="ab7cb-108">Créez un index XML sélectif en appelant l'instruction CREATE SELECTIVE XML INDEX.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-108">Create a selective XML index by calling the CREATE SELECTIVE XML INDEX statement.</span></span> <span data-ttu-id="ab7cb-109">Pour plus d’informations, consultez [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ab7cb-109">For more information, see [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span></span>  
  
 <span data-ttu-id="ab7cb-110">**Exemple**</span><span class="sxs-lookup"><span data-stu-id="ab7cb-110">**Example**</span></span>  
  
 <span data-ttu-id="ab7cb-111">L'exemple suivant montre la syntaxe pour créer un index XML sélectif.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-111">The following example shows the syntax for creating a selective XML index.</span></span> <span data-ttu-id="ab7cb-112">Il montre également différentes variantes de la syntaxe pour décrire les chemins d'accès à indexer, avec des indicateurs facultatifs d'optimisation.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-112">It also shows several variations of the syntax for describing the paths to be indexed, with optional optimization hints.</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX sxi_index  
ON Tbl(xmlcol)  
  
FOR(  
    pathab   = '/a/b' as XQUERY 'node()'  
    pathabc  = '/a/b/c' as XQUERY 'xs:double',   
    pathdtext = '/a/b/d/text()' as XQUERY 'xs:string' MAXLENGTH(200) SINGLETON  
    pathabe = '/a/b/e' as SQL NVARCHAR(100)  
)  
```  
  
  
  
##  <a name="altering-a-selective-xml-index"></a><a name="alter"></a> <span data-ttu-id="ab7cb-113">Modification d'un index XML sélectif</span><span class="sxs-lookup"><span data-stu-id="ab7cb-113">Altering a Selective XML Index</span></span>  
  
### <a name="how-to-alter-a-selective-xml-index"></a><span data-ttu-id="ab7cb-114">Procédure : Modifier un index XML sélectif</span><span class="sxs-lookup"><span data-stu-id="ab7cb-114">How to: Alter a Selective XML Index</span></span>  
 <span data-ttu-id="ab7cb-115">**Modifier un index XML sélectif à l'aide de Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="ab7cb-115">**Alter a Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="ab7cb-116">Modifiez un index XML sélectif existant en appelant l'instruction ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-116">Alter an existing selective XML index by calling the ALTER INDEX statement.</span></span> <span data-ttu-id="ab7cb-117">Pour plus d’informations, consultez [ALTER INDEX &#40;index XML sélectifs&#41;](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="ab7cb-117">For more information, see [ALTER INDEX &#40;Selective XML Indexes&#41;](../indexes/indexes.md).</span></span>  
  
 <span data-ttu-id="ab7cb-118">**Exemple**</span><span class="sxs-lookup"><span data-stu-id="ab7cb-118">**Example**</span></span>  
  
 <span data-ttu-id="ab7cb-119">L'exemple suivant illustre une instruction ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-119">The following example shows an ALTER INDEX statement.</span></span> <span data-ttu-id="ab7cb-120">Cette instruction ajoute le chemin `'/a/b/m'` à la partie XQuery de l’index et supprime le chemin `'/a/b/e'` de la partie SQL de l’index créé dans l’exemple de la rubrique [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ab7cb-120">This statement adds the path `'/a/b/m'` to the XQuery part of the index and deletes the path `'/a/b/e'` from the SQL part of the index created in the example in the topic [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span></span> <span data-ttu-id="ab7cb-121">Le chemin d'accès à supprimer est identifié par le nom qui lui a été donné lors de sa création.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-121">The path to delete is identified by the name that was given to it when it was created.</span></span>  
  
```sql  
ALTER INDEX sxi_index  
ON Tbl  
FOR   
(  
    ADD pathm = '/a/b/m' as XQUERY 'node()' ,  
    REMOVE pathabe  
)  
```  
  
  
  
##  <a name="dropping-a-selective-xml-index"></a><a name="drop"></a> <span data-ttu-id="ab7cb-122">Suppression d'un index XML sélectif</span><span class="sxs-lookup"><span data-stu-id="ab7cb-122">Dropping a Selective XML Index</span></span>  
  
### <a name="how-to-drop-a-selective-xml-index"></a><span data-ttu-id="ab7cb-123">Procédure : Supprimer un index XML sélectif</span><span class="sxs-lookup"><span data-stu-id="ab7cb-123">How to: Drop a Selective XML Index</span></span>  
 <span data-ttu-id="ab7cb-124">**Supprimer un index XML sélectif à l'aide de Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="ab7cb-124">**Drop a Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="ab7cb-125">Supprimez un index XML sélectif en appelant l'instruction DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-125">Drop a selective XML index by calling the DROP INDEX statement.</span></span> <span data-ttu-id="ab7cb-126">Pour plus d’informations, consultez [DROP INDEX &#40;index XML sélectifs&#41;](/sql/t-sql/statements/drop-index-selective-xml-indexes).</span><span class="sxs-lookup"><span data-stu-id="ab7cb-126">For more information, see [DROP INDEX &#40;Selective XML Indexes&#41;](/sql/t-sql/statements/drop-index-selective-xml-indexes).</span></span>  
  
 <span data-ttu-id="ab7cb-127">**Exemple**</span><span class="sxs-lookup"><span data-stu-id="ab7cb-127">**Example**</span></span>  
  
 <span data-ttu-id="ab7cb-128">L'exemple suivant illustre une instruction DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-128">The following example shows a DROP INDEX statement.</span></span>  
  
```sql  
DROP INDEX sxi_index ON tbl  
```  
  
 
  
  
