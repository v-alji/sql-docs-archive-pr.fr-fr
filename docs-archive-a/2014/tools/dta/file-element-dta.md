---
title: File, élément (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- File element
ms.assetid: 73dce835-9a80-4aef-8e0f-9dcf07dd5b80
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0eeb2bdcc9513ca6283447daca63c8bbc4fa1726
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704583"
---
# <a name="file-element-dta"></a><span data-ttu-id="0fcd3-102">File, élément (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="0fcd3-102">File Element (DTA)</span></span>
  <span data-ttu-id="0fcd3-103">Spécifie le fichier de charge de travail.</span><span class="sxs-lookup"><span data-stu-id="0fcd3-103">Specifies the workload file.</span></span> <span data-ttu-id="0fcd3-104">Une charge de travail est un ensemble d'instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] qui s'exécute sur une ou plusieurs bases de données que vous souhaitez paramétrer.</span><span class="sxs-lookup"><span data-stu-id="0fcd3-104">A workload is a set of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that execute against a database or databases that you want to tune.</span></span> <span data-ttu-id="0fcd3-105">Les fichiers de charge de travail peuvent être des scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] (.sql) ou des fichiers de trace (.trc).</span><span class="sxs-lookup"><span data-stu-id="0fcd3-105">Workload files can be [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts (.sql) or trace files (.trc).</span></span> <span data-ttu-id="0fcd3-106">Pour plus d’informations, consultez [Démarrer et utiliser l'Assistant Paramétrage du moteur de base de données](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="0fcd3-106">For more information, see [Start and Use the Database Engine Tuning Advisor](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fcd3-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="0fcd3-107">Syntax</span></span>  
  
```  
  
<DTAInput>  
  <Server>...</Server>  
  <Workload>  
    <File>...</File>  
  </Workload>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="0fcd3-108">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="0fcd3-108">Element Characteristics</span></span>  
  
|<span data-ttu-id="0fcd3-109">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="0fcd3-109">Characteristic</span></span>|<span data-ttu-id="0fcd3-110">Description</span><span class="sxs-lookup"><span data-stu-id="0fcd3-110">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="0fcd3-111">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="0fcd3-111">**Data type and length**</span></span>|<span data-ttu-id="0fcd3-112">Utilisez le type de données `string` pour spécifier le chemin d'accès au répertoire de votre fichier de charge de travail.</span><span class="sxs-lookup"><span data-stu-id="0fcd3-112">Use the `string` data type to specify the directory path to your workload file.</span></span> <span data-ttu-id="0fcd3-113">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="0fcd3-113">For example:</span></span><br /><br /> `<File>C:\Tuning\tun.sql</File>`<br /><br /> <span data-ttu-id="0fcd3-114">Limite de longueur appliquée par le serveur.</span><span class="sxs-lookup"><span data-stu-id="0fcd3-114">Length limit is enforced by the server.</span></span>|  
|<span data-ttu-id="0fcd3-115">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="0fcd3-115">**Default value**</span></span>|<span data-ttu-id="0fcd3-116">Aucun.</span><span class="sxs-lookup"><span data-stu-id="0fcd3-116">None.</span></span>|  
|<span data-ttu-id="0fcd3-117">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="0fcd3-117">**Occurrence**</span></span>|<span data-ttu-id="0fcd3-118">Obligatoire une fois si aucun autre type de charge de travail n'est spécifié.</span><span class="sxs-lookup"><span data-stu-id="0fcd3-118">Required once if no other type of workload is specified.</span></span> <span data-ttu-id="0fcd3-119">Vous devez spécifier un élément enfant **EventString**, **File**ou **Database** pour le parent **Workload** , mais un seul type peut être utilisé.</span><span class="sxs-lookup"><span data-stu-id="0fcd3-119">You must specify an **EventString**, a **File**, or a **Database** child element for the **Workload** parent, but only one type can be used.</span></span> <span data-ttu-id="0fcd3-120">Par exemple, si vous spécifiez une charge de travail avec l’élément **File** , vous ne pouvez pas spécifier une charge de travail avec l’élément **Database** dans le même fichier d’entrée XML.</span><span class="sxs-lookup"><span data-stu-id="0fcd3-120">For example, if you specify a workload with the **File** element, then you cannot also specify a workload with the **Database** element in the same XML input file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="0fcd3-121">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="0fcd3-121">Element Relationships</span></span>  
  
|<span data-ttu-id="0fcd3-122">Relation</span><span class="sxs-lookup"><span data-stu-id="0fcd3-122">Relationship</span></span>|<span data-ttu-id="0fcd3-123">Éléments</span><span class="sxs-lookup"><span data-stu-id="0fcd3-123">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="0fcd3-124">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="0fcd3-124">**Parent element**</span></span>|[<span data-ttu-id="0fcd3-125">Workload, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="0fcd3-125">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)|  
|<span data-ttu-id="0fcd3-126">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="0fcd3-126">**Child elements**</span></span>|<span data-ttu-id="0fcd3-127">Aucun.</span><span class="sxs-lookup"><span data-stu-id="0fcd3-127">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0fcd3-128">Exemple</span><span class="sxs-lookup"><span data-stu-id="0fcd3-128">Example</span></span>  
 <span data-ttu-id="0fcd3-129">Pour obtenir un exemple d’utilisation de cet élément, consultez [Exemple de fichier d’entrée XML simple &#40;Assistant Paramétrage de base de données&#41;](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="0fcd3-129">For a usage example of this element, see [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fcd3-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0fcd3-130">See Also</span></span>  
 [<span data-ttu-id="0fcd3-131">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="0fcd3-131">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
