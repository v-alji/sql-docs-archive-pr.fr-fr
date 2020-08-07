---
title: Charge de travail, élément (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Workload element
ms.assetid: 68ffd473-6546-4015-98d0-3763165de65c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 20184760c3fcb5eed6c02b8f8fd9b63f5586c9af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604334"
---
# <a name="workload-element-dta"></a><span data-ttu-id="29639-102">Workload, élément (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="29639-102">Workload Element (DTA)</span></span>
  <span data-ttu-id="29639-103">Spécifie la charge de travail à utiliser pour une session de paramétrage.</span><span class="sxs-lookup"><span data-stu-id="29639-103">Specifies the workload to be used for a tuning session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29639-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="29639-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
    <Server>  
...code removed...  
    <Workload>...</Workload>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="29639-105">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="29639-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="29639-106">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="29639-106">Characteristic</span></span>|<span data-ttu-id="29639-107">Description</span><span class="sxs-lookup"><span data-stu-id="29639-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="29639-108">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="29639-108">**Data type and length**</span></span>|<span data-ttu-id="29639-109">Aucun.</span><span class="sxs-lookup"><span data-stu-id="29639-109">None.</span></span>|  
|<span data-ttu-id="29639-110">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="29639-110">**Default value**</span></span>|<span data-ttu-id="29639-111">Aucun.</span><span class="sxs-lookup"><span data-stu-id="29639-111">None.</span></span>|  
|<span data-ttu-id="29639-112">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="29639-112">**Occurrence**</span></span>|<span data-ttu-id="29639-113">Obligatoire une fois pour chaque `DTAInput` élément.</span><span class="sxs-lookup"><span data-stu-id="29639-113">Required once for each `DTAInput` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="29639-114">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="29639-114">Element Relationships</span></span>  
  
|<span data-ttu-id="29639-115">Relation</span><span class="sxs-lookup"><span data-stu-id="29639-115">Relationship</span></span>|<span data-ttu-id="29639-116">Éléments</span><span class="sxs-lookup"><span data-stu-id="29639-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="29639-117">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="29639-117">**Parent element**</span></span>|[<span data-ttu-id="29639-118">Démarrer et utiliser l’Assistant Paramétrage du moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="29639-118">Start and Use the Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md)|  
|<span data-ttu-id="29639-119">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="29639-119">**Child elements**</span></span>|[<span data-ttu-id="29639-120">Élément File &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="29639-120">File Element &#40;DTA&#41;</span></span>](file-element-dta.md)<br /><br /> [<span data-ttu-id="29639-121">Élément Database &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="29639-121">Database Element for Workload &#40;DTA&#41;</span></span>](database-element-for-workload-dta.md)<br /><br /> [<span data-ttu-id="29639-122">Élément EventString &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="29639-122">EventString Element &#40;DTA&#41;</span></span>](eventstring-element-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="29639-123">Notes</span><span class="sxs-lookup"><span data-stu-id="29639-123">Remarks</span></span>  
 <span data-ttu-id="29639-124">Une charge de travail est un ensemble d'instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] qui s'exécute sur une ou plusieurs bases de données que vous souhaitez paramétrer.</span><span class="sxs-lookup"><span data-stu-id="29639-124">A workload is a set of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that execute against a database or databases that you want to tune.</span></span> <span data-ttu-id="29639-125">L'Assistant Paramétrage du moteur de base de données peut utiliser des scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] , des fichiers de trace et des tables de trace en tant que charges de travail.</span><span class="sxs-lookup"><span data-stu-id="29639-125">The Database Engine Tuning Advisor can use [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, trace files, and trace tables as workloads.</span></span>  
  
 <span data-ttu-id="29639-126">Si vous spécifiez une charge de travail dans un fichier d'entrée XML et une charge de travail dans une ligne de commande avec l'outil **dta** , la charge de travail spécifiée dans la ligne de commande est utilisée pour le paramétrage.</span><span class="sxs-lookup"><span data-stu-id="29639-126">If you specify a workload in an XML input file and a workload on the command line with the **dta** tool, the workload specified on the command line will be used for tuning.</span></span> <span data-ttu-id="29639-127">Toutes les options de paramétrage de la ligne de commande remplacent celles spécifiées dans un fichier d'entrée XML.</span><span class="sxs-lookup"><span data-stu-id="29639-127">All tuning options specified on the command line override those that are specified in an XML input file.</span></span> <span data-ttu-id="29639-128">Une seule exception : configuration spécifiée par l'utilisateur entrée dans le mode évaluation dans le fichier d'entrée XML.</span><span class="sxs-lookup"><span data-stu-id="29639-128">The only exception is if a user-specified configuration is entered in the evaluate mode in the XML input file.</span></span> <span data-ttu-id="29639-129">Par exemple, si une configuration est entrée dans l'élément `Configuration` du fichier d'entrée XML et que l'élément `EvaluateConfiguration` est également configuré en tant qu'une des options de paramétrage, les options de paramétrage spécifiées dans le fichier d'entrée remplacent toute option de paramétrage saisie dans la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="29639-129">For example, if a configuration is entered in the `Configuration` element of the XML input file and the `EvaluateConfiguration` element is also specified as one of the tuning options, the tuning options specified in the XML input file will override any tuning options entered at the command line.</span></span>  
  
 <span data-ttu-id="29639-130">Une charge de travail doit être spécifiée pour chaque session de paramétrage.</span><span class="sxs-lookup"><span data-stu-id="29639-130">One workload must be specified for each tuning session.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29639-131">Exemple</span><span class="sxs-lookup"><span data-stu-id="29639-131">Example</span></span>  
 <span data-ttu-id="29639-132">L’exemple de code suivant spécifie la table de trace **mydatabase. MyDBOwner. TuningTable001** pour l' `Workload` élément.</span><span class="sxs-lookup"><span data-stu-id="29639-132">The following code example specifies the **MyDatabase.MyDBOwner.TuningTable001** trace table for the `Workload` element.</span></span> <span data-ttu-id="29639-133">La table **TuningTable001** a été créée à l'aide du modèle de paramétrage (Tuning) utilisé dans le Générateur de profils SQL Server et dont le résultat de trace a été enregistré comme table.</span><span class="sxs-lookup"><span data-stu-id="29639-133">The **TuningTable001** was created by using the Tuning template with SQL Server Profiler and saving the trace output as a table.</span></span>  
  
```  
<DTAXML ...>  
  <DTAInput>  
    <Server>  
...code removed here...  
    </Server>  
    <Workload>  
      <Database>  
        <Name>MyDatabase</Name>  
        <Schema>  
          <Name>MyDBOwner</Name>  
            <Table>  
              <Name>TuningTable001</Name>  
            </Table>  
        </Schema>  
      </Database>  
    </Workload>  
...code removed here...  
  </DTAInput>  
</DTAXML>  
```  
  
## <a name="see-also"></a><span data-ttu-id="29639-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="29639-134">See Also</span></span>  
 [<span data-ttu-id="29639-135">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="29639-135">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
