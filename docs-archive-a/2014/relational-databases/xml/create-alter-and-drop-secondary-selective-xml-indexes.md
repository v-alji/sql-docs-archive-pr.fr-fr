---
title: Créer, modifier ou supprimer des index XML secondaires sélectifs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
ms.assetid: 45128105-833b-40a9-9cc9-1ae03ac0b52b
author: rothja
ms.author: jroth
ms.openlocfilehash: e6f7296896b6421db5329565403cdcbaf10b26a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697611"
---
# <a name="create-alter-and-drop-secondary-selective-xml-indexes"></a><span data-ttu-id="b6c4d-102">Créer, modifier ou supprimer des index XML secondaires sélectifs</span><span class="sxs-lookup"><span data-stu-id="b6c4d-102">Create, Alter, and Drop Secondary Selective XML Indexes</span></span>
  <span data-ttu-id="b6c4d-103">Décrit la procédure de création d'un index XML secondaire sélectif, ou de modification ou de suppression d'un index XML secondaire sélectif existant.</span><span class="sxs-lookup"><span data-stu-id="b6c4d-103">Describes how to create a new secondary selective XML index, or alter or drop an existing secondary selective XML index.</span></span>  
  
##  <a name="creating-a-secondary-selective-xml-index"></a><a name="create"></a> <span data-ttu-id="b6c4d-104">Création d'un index XML secondaire sélectif</span><span class="sxs-lookup"><span data-stu-id="b6c4d-104">Creating a Secondary Selective XML Index</span></span>  
  
### <a name="how-to-create-a-secondary-selective-xml-index"></a><span data-ttu-id="b6c4d-105">Procédure : Créer un index XML secondaire sélectif</span><span class="sxs-lookup"><span data-stu-id="b6c4d-105">How to: Create a Secondary Selective XML Index</span></span>  
 <span data-ttu-id="b6c4d-106">**Créer un index XML secondaire sélectif à l'aide de Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="b6c4d-106">**Create a Secondary Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="b6c4d-107">Créez un index XML secondaire sélectif en appelant l'instruction CREATE XML INDEX.</span><span class="sxs-lookup"><span data-stu-id="b6c4d-107">Create a secondary selective XML index by calling the CREATE XML INDEX statement.</span></span> <span data-ttu-id="b6c4d-108">Pour plus d’informations, consultez [CREATe XML INDEX &#40;Selective XML Indexes&#41;] (~/t-SQL/Statements/CREATE-XML-index-Selective-XML-indexes.</span><span class="sxs-lookup"><span data-stu-id="b6c4d-108">For more information, see [CREATE XML INDEX &#40;Selective XML Indexes&#41;](~/t-sql/statements/create-xml-index-selective-xml-indexes.</span></span>  
  
 <span data-ttu-id="b6c4d-109">**Exemple**</span><span class="sxs-lookup"><span data-stu-id="b6c4d-109">**Example**</span></span>  
  
 <span data-ttu-id="b6c4d-110">L'exemple suivant crée un index XML secondaire sélectif sur le chemin d'accès `'pathabc'`.</span><span class="sxs-lookup"><span data-stu-id="b6c4d-110">The following example creates a secondary selective XML index on the path `'pathabc'`.</span></span> <span data-ttu-id="b6c4d-111">Le chemin d'accès à l'index est identifié par le nom qui lui a été donné lors de sa création à l'aide de l'instruction CREATE SELECTIVE XML INDEX.</span><span class="sxs-lookup"><span data-stu-id="b6c4d-111">The path to index is identified by the name that was given to it when it was created with the CREATE SELECTIVE XML INDEX statement.</span></span> <span data-ttu-id="b6c4d-112">Pour plus d’informations, consultez [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b6c4d-112">For more information, see [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span></span>  
  
```sql  
CREATE XML INDEX filt_sxi_index_c  
ON Tbl(xmlcol)  
USING XML INDEX sxi_index  
FOR  
(  
    pathabc  
)  
```  
  
  
##  <a name="altering-a-secondary-selective-xml-index"></a><a name="alter"></a> <span data-ttu-id="b6c4d-113">Modification d'un index XML secondaire sélectif</span><span class="sxs-lookup"><span data-stu-id="b6c4d-113">Altering a Secondary Selective XML Index</span></span>  
 <span data-ttu-id="b6c4d-114">L'instruction ALTER n'est pas prise en charge pour les index XML secondaires sélectifs.</span><span class="sxs-lookup"><span data-stu-id="b6c4d-114">The ALTER statement is not supported for secondary selective XML indexes.</span></span> <span data-ttu-id="b6c4d-115">Pour modifier un index XML secondaire sélectif, supprimez l'index existant et recréez-le.</span><span class="sxs-lookup"><span data-stu-id="b6c4d-115">To change a secondary selective XML index, drop the existing index and recreate it.</span></span>  
  
### <a name="how-to-alter-a-secondary-selective-xml-index"></a><span data-ttu-id="b6c4d-116">Procédure : Modifier un index XML secondaire sélectif</span><span class="sxs-lookup"><span data-stu-id="b6c4d-116">How to: Alter a Secondary Selective XML Index</span></span>  
 <span data-ttu-id="b6c4d-117">**Modifier un index XML secondaire sélectif à l'aide de Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="b6c4d-117">**Alter a Secondary Selective XML Index by Using Transact-SQL**</span></span>  
 1.  <span data-ttu-id="b6c4d-118">Supprimez l'index XML secondaire sélectif existant en appelant l'instruction DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="b6c4d-118">Drop the existing secondary selective XML index by calling the DROP INDEX statement.</span></span> <span data-ttu-id="b6c4d-119">Pour plus d’informations, consultez [DROP INDEX &#40;index XML sélectifs&#41;](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="b6c4d-119">For more information, see [DROP INDEX &#40;Selective XML Indexes&#41;](../indexes/indexes.md).</span></span>  
  
2.  <span data-ttu-id="b6c4d-120">Recréez l'index avec les options de votre choix en appelant l'instruction CREATE XML INDEX.</span><span class="sxs-lookup"><span data-stu-id="b6c4d-120">Recreate the index with the desired options by calling the CREATE XML INDEX statement.</span></span> <span data-ttu-id="b6c4d-121">Pour plus d’informations, consultez [CREATe XML INDEX &#40;Selective XML Indexes&#41;] (~/t-SQL/Statements/CREATE-XML-index-Selective-XML-indexes.</span><span class="sxs-lookup"><span data-stu-id="b6c4d-121">For more information, see [CREATE XML INDEX &#40;Selective XML Indexes&#41;](~/t-sql/statements/create-xml-index-selective-xml-indexes.</span></span>  
  
 <span data-ttu-id="b6c4d-122">**Exemple**</span><span class="sxs-lookup"><span data-stu-id="b6c4d-122">**Example**</span></span>  
  
 <span data-ttu-id="b6c4d-123">L'exemple suivant modifie un index XML secondaire sélectif en le supprimant et en le recréant.</span><span class="sxs-lookup"><span data-stu-id="b6c4d-123">The following example changes a secondary selective XML index by dropping it and recreating it.</span></span>  
  
```sql  
DROP INDEX filt_sxi_index_c  
  
CREATE XML INDEX filt_sxi_index_c  
ON Tbl(xmlcol)  
USING XML INDEX sxi_index  
FOR  
(  
    pathabc  
)  
```  
  
  
##  <a name="dropping-a-secondary-selective-xml-index"></a><a name="drop"></a> <span data-ttu-id="b6c4d-124">Suppression d'un index XML secondaire sélectif</span><span class="sxs-lookup"><span data-stu-id="b6c4d-124">Dropping a Secondary Selective XML Index</span></span>  
  
### <a name="how-to-drop-a-secondary-selective-xml-index"></a><span data-ttu-id="b6c4d-125">Procédure : Supprimer un index XML secondaire sélectif</span><span class="sxs-lookup"><span data-stu-id="b6c4d-125">How to: Drop a Secondary Selective XML Index</span></span>  
 <span data-ttu-id="b6c4d-126">**Supprimer un index XML secondaire sélectif à l'aide de Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="b6c4d-126">**Drop a Secondary Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="b6c4d-127">Supprimez un index XML secondaire sélectif en appelant l'instruction DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="b6c4d-127">Drop a secondary selective XML index by calling the DROP INDEX statement.</span></span> <span data-ttu-id="b6c4d-128">Pour plus d’informations, consultez [DROP INDEX &#40;index XML sélectifs&#41;](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="b6c4d-128">For more information, see [DROP INDEX &#40;Selective XML Indexes&#41;](../indexes/indexes.md).</span></span>  
  
 <span data-ttu-id="b6c4d-129">**Exemple**</span><span class="sxs-lookup"><span data-stu-id="b6c4d-129">**Example**</span></span>  
  
 <span data-ttu-id="b6c4d-130">L'exemple suivant illustre une instruction DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="b6c4d-130">The following example shows a DROP INDEX statement.</span></span>  
  
```sql  
DROP INDEX ssxi_index  
ON tbl  
```  
  
  
## <a name="see-also"></a><span data-ttu-id="b6c4d-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b6c4d-131">See Also</span></span>  
 [<span data-ttu-id="b6c4d-132">Index XML sélectifs &#40;SXI&#41;</span><span class="sxs-lookup"><span data-stu-id="b6c4d-132">Selective XML Indexes &#40;SXI&#41;</span></span>](selective-xml-indexes-sxi.md)  
  
  
