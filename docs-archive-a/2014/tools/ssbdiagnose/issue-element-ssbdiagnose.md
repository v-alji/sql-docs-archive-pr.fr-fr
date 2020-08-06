---
title: Élément issue (ssbdiagnose) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- issue element
- XML output file format [ssbdiagnose], issue element
- ssbdiagnose
ms.assetid: 2246a886-686b-44ca-9771-b155cedad8be
author: stevestein
ms.author: sstein
ms.openlocfilehash: a178c1323c1c20f84e67d4d7699fc313090a4c71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694891"
---
# <a name="issue-element-ssbdiagnose"></a><span data-ttu-id="25801-102">Élément Issue (ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="25801-102">Issue Element (ssbdiagnose)</span></span>
  <span data-ttu-id="25801-103">Signale un problème identifié par l’utilitaire **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="25801-103">Reports an issue that was found by the **ssbdiagnose** utility.</span></span> <span data-ttu-id="25801-104">Le fichier de sortie XML de **ssbdiagnose** comporte un élément Issue par problème signalé.</span><span class="sxs-lookup"><span data-stu-id="25801-104">The **ssbdiagnose** XML output file has one Issue element per issue reported.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25801-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="25801-105">Syntax</span></span>  
  
```  
  
<Issue  
    type="..."   
    code="..."   
    server="..."   
    database="..."   
    object="...">   
    ...   
</Issue>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="25801-106">Attributs des éléments</span><span class="sxs-lookup"><span data-stu-id="25801-106">Element Attributes</span></span>  
  
|<span data-ttu-id="25801-107">Attribut</span><span class="sxs-lookup"><span data-stu-id="25801-107">Attribute</span></span>|<span data-ttu-id="25801-108">Description</span><span class="sxs-lookup"><span data-stu-id="25801-108">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="25801-109">Identifie la catégorie de problème signalée par l’élément Issue :</span><span class="sxs-lookup"><span data-stu-id="25801-109">Identifies which category of problem the Issue element is reporting:</span></span><br /><br /> <span data-ttu-id="25801-110">**« Diagnosis »** Signale un problème de configuration identifié lors de l'analyse d'une configuration [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25801-110">**"Diagnosis"** Reports a configuration issue found when you analyze a [!INCLUDE[ssSB](../../includes/sssb-md.md)] configuration.</span></span><br /><br /> <span data-ttu-id="25801-111">**« Problem »** Signale un problème qui a empêché **ssbdiagnose** d’effectuer son analyse.</span><span class="sxs-lookup"><span data-stu-id="25801-111">**"Problem"** Reports an issue that has prevented **ssbdiagnose** from completing its analysis.</span></span> <span data-ttu-id="25801-112">Résolvez le problème et exécutez de nouveau **ssbdiagnose**.</span><span class="sxs-lookup"><span data-stu-id="25801-112">Correct the problem and rerun **ssbdiagnose**.</span></span><br /><br /> <span data-ttu-id="25801-113">**« Event »** Signale un événement [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] identifié lors de l’exécution d’une vérification **-RUNTIME** .</span><span class="sxs-lookup"><span data-stu-id="25801-113">**"Event"** Reports a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] event found when you run a **-RUNTIME** check.</span></span> <span data-ttu-id="25801-114">Les événements sont signalés uniquement si **-SHOWEVENTS** est spécifié.</span><span class="sxs-lookup"><span data-stu-id="25801-114">Events are only reported if **-SHOWEVENTS** is specified.</span></span>|  
|`code`|<span data-ttu-id="25801-115">Identifie le numéro d'erreur du message.</span><span class="sxs-lookup"><span data-stu-id="25801-115">Identifies the error number for the message.</span></span>|  
|`server`|<span data-ttu-id="25801-116">Identifie l'instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] dans laquelle le problème a été trouvé.</span><span class="sxs-lookup"><span data-stu-id="25801-116">Identifies the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] in which the problem was found.</span></span> <span data-ttu-id="25801-117">Si le problème a été identifié dans une instance par défaut, l'attribut de serveur porte uniquement le nom de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="25801-117">If the problem was in a default instance, the server attribute only has the computer name.</span></span> <span data-ttu-id="25801-118">Si le problème a été identifié dans une instance nommée, l'attribut de serveur prend la forme NomOrdinateur\NomInstance.</span><span class="sxs-lookup"><span data-stu-id="25801-118">If the problem was in a named instance, the server attribute is in the form ComputerName\InstanceName.</span></span>|  
|`database`|<span data-ttu-id="25801-119">Identifie le nom de la base de données dans laquelle le problème a été trouvé.</span><span class="sxs-lookup"><span data-stu-id="25801-119">Identifies the name of the database in which the problem was found.</span></span>|  
|`object`|<span data-ttu-id="25801-120">Identifie le nom de l'objet dans lequel le problème a été trouvé.</span><span class="sxs-lookup"><span data-stu-id="25801-120">Identifies the name of the object in which the problem was found.</span></span> <span data-ttu-id="25801-121">Si le problème était un problème de niveau instance ou base de données, l'attribut de l'objet répète le nom de l'instance ou de la base de données.</span><span class="sxs-lookup"><span data-stu-id="25801-121">If the problem was an instance or database level issue, the object attribute repeats the instance or database name.</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="25801-122">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="25801-122">Element Characteristics</span></span>  
  
|<span data-ttu-id="25801-123">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="25801-123">Characteristic</span></span>|<span data-ttu-id="25801-124">Description</span><span class="sxs-lookup"><span data-stu-id="25801-124">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="25801-125">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="25801-125">**Data type and length**</span></span>|<span data-ttu-id="25801-126">`string`, la longueur est illimitée.</span><span class="sxs-lookup"><span data-stu-id="25801-126">`string`, length is unlimited.</span></span>|  
|<span data-ttu-id="25801-127">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="25801-127">**Value**</span></span>|<span data-ttu-id="25801-128">Retourne le texte du message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="25801-128">Returns the text of the error message.</span></span>|  
|<span data-ttu-id="25801-129">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="25801-129">**Occurrence**</span></span>|<span data-ttu-id="25801-130">Une fois par erreur signalée.</span><span class="sxs-lookup"><span data-stu-id="25801-130">Once per reported error.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="25801-131">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="25801-131">Element Relationships</span></span>  
  
|<span data-ttu-id="25801-132">Relation</span><span class="sxs-lookup"><span data-stu-id="25801-132">Relationship</span></span>|<span data-ttu-id="25801-133">Éléments</span><span class="sxs-lookup"><span data-stu-id="25801-133">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="25801-134">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="25801-134">**Parent element**</span></span>|[<span data-ttu-id="25801-135">Élément DiagnosticInformation &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="25801-135">DiagnosticInformation Element &#40;ssbdiagnose&#41;</span></span>](diagnosticinformation-element-ssbdiagnose.md)|  
|<span data-ttu-id="25801-136">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="25801-136">**Child elements**</span></span>|<span data-ttu-id="25801-137">None</span><span class="sxs-lookup"><span data-stu-id="25801-137">None</span></span>|  
  
## <a name="example"></a><span data-ttu-id="25801-138">Exemple</span><span class="sxs-lookup"><span data-stu-id="25801-138">Example</span></span>  
 <span data-ttu-id="25801-139">Cet élément signale une erreur 1102 pour une base de données ne possédant pas de clé principale, où l'erreur a été détectée lors de l'analyse d'une configuration [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25801-139">This element reports an 1102 error for a database that does not have a master key, where the error was found when you analyzed a [!INCLUDE[ssSB](../../includes/sssb-md.md)] configuration.</span></span>  
  
```  
<Issue type="Diagnosis" code="1102" server="TestComputer" database="TargetDB" object="TargetDB">The master key was not found</diagnostic>  
```  
  
## <a name="see-also"></a><span data-ttu-id="25801-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="25801-140">See Also</span></span>  
 [<span data-ttu-id="25801-141">Utilitaire ssbdiagnose &#40;Service Broker&#41;</span><span class="sxs-lookup"><span data-stu-id="25801-141">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](ssbdiagnose-utility-service-broker.md)  
  
  
