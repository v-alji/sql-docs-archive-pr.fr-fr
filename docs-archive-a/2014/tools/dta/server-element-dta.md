---
title: Server, élément (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Server element
ms.assetid: 9fe0bfb4-3aa6-4eb2-a83e-c0d0e7d4e9f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: ab67e0303c2b629c3774886441474f5ef5b10a43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612048"
---
# <a name="server-element-dta"></a><span data-ttu-id="11cea-102">Server, élément (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="11cea-102">Server Element (DTA)</span></span>
  <span data-ttu-id="11cea-103">Contient les informations d'identification du serveur sur lequel résident les bases de données que vous souhaitez paramétrer.</span><span class="sxs-lookup"><span data-stu-id="11cea-103">Contains the identifying information for the server on which the databases reside that you want to tune.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11cea-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="11cea-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
    <Server>  
    ...code removed here...  
    </Server>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="11cea-105">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="11cea-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="11cea-106">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="11cea-106">Characteristic</span></span>|<span data-ttu-id="11cea-107">Description</span><span class="sxs-lookup"><span data-stu-id="11cea-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="11cea-108">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="11cea-108">**Data type and length**</span></span>|<span data-ttu-id="11cea-109">Aucun.</span><span class="sxs-lookup"><span data-stu-id="11cea-109">None.</span></span>|  
|<span data-ttu-id="11cea-110">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="11cea-110">**Default value**</span></span>|<span data-ttu-id="11cea-111">Aucun.</span><span class="sxs-lookup"><span data-stu-id="11cea-111">None.</span></span>|  
|<span data-ttu-id="11cea-112">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="11cea-112">**Occurrence**</span></span>|<span data-ttu-id="11cea-113">Obligatoire une fois par élément `DTAInput`.</span><span class="sxs-lookup"><span data-stu-id="11cea-113">Required once per `DTAInput` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="11cea-114">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="11cea-114">Element Relationships</span></span>  
  
|<span data-ttu-id="11cea-115">Relation</span><span class="sxs-lookup"><span data-stu-id="11cea-115">Relationship</span></span>|<span data-ttu-id="11cea-116">Éléments</span><span class="sxs-lookup"><span data-stu-id="11cea-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="11cea-117">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="11cea-117">**Parent element**</span></span>|[<span data-ttu-id="11cea-118">DTAInput, élément &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="11cea-118">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)|  
|<span data-ttu-id="11cea-119">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="11cea-119">**Child elements**</span></span>|[<span data-ttu-id="11cea-120">Name, élément pour les serveurs &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="11cea-120">Name Element for Server &#40;DTA&#41;</span></span>](name-element-for-server-dta.md)<br /><br /> [<span data-ttu-id="11cea-121">Database, élément pour les serveurs &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="11cea-121">Database Element for Server &#40;DTA&#41;</span></span>](database-element-for-server-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="11cea-122">Notes</span><span class="sxs-lookup"><span data-stu-id="11cea-122">Remarks</span></span>  
 <span data-ttu-id="11cea-123">Vous ne pouvez spécifier qu’un seul `Server` élément pour l' `DTAInput` élément.</span><span class="sxs-lookup"><span data-stu-id="11cea-123">You can specify only one `Server` element for the `DTAInput` element.</span></span> <span data-ttu-id="11cea-124">Cet élément porte le nom de **ServerDetailsTypecomplexType** dans le schéma XML de l’Assistant Paramétrage de base de données.</span><span class="sxs-lookup"><span data-stu-id="11cea-124">This element is of the **ServerDetailsTypecomplexType** name in the DTA XML schema.</span></span> <span data-ttu-id="11cea-125">Ne confondez pas cet élément `Server` avec l'élément enfant de l'élément `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="11cea-125">Do not confuse this `Server` element with the one that is the child of the `Configuration` element.</span></span> <span data-ttu-id="11cea-126">Pour plus d’informations, consultez [Server, élément pour les configurations &#40;Assistant Paramétrage de base de données&#41;](server-element-for-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="11cea-126">For more information, see [Server Element for Configuration &#40;DTA&#41;](server-element-for-configuration-dta.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="11cea-127">Exemple</span><span class="sxs-lookup"><span data-stu-id="11cea-127">Example</span></span>  
 <span data-ttu-id="11cea-128">L’exemple suivant montre comment spécifier la table **Sales.SalesPerson** dans la base de données **AdventureWorks** située sur SERVER001 :</span><span class="sxs-lookup"><span data-stu-id="11cea-128">The following example shows how to specify the **Sales.SalesPerson** table in the **AdventureWorks** database on SERVER001:</span></span>  
  
```xml  
<Server>  
  <Name>SERVER001</Name>  
  <Database>  
    <Name>AdventureWorks</Name>  
    <Schema>  
      <Name>Sales</Name>  
      <Table>  
        <Name>SalesPerson</Name>  
      </Table>  
    </Schema>  
  </Database>  
</Server  
```  
  
## <a name="see-also"></a><span data-ttu-id="11cea-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="11cea-129">See Also</span></span>  
 [<span data-ttu-id="11cea-130">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="11cea-130">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
