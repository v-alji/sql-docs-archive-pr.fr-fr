---
title: 'Tâche 5 : définition des relations à base de termes | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6569d512-637d-4f7b-82e1-1e8582278b37
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 1589ec5843053baa6c42a0b9b0dec019c887da9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704411"
---
# <a name="task-5-setting-term-based-relationships"></a><span data-ttu-id="18c5f-102">Tâche 5 : Définition des relations basées sur des termes</span><span class="sxs-lookup"><span data-stu-id="18c5f-102">Task 5: Setting Term Based Relationships</span></span>
  <span data-ttu-id="18c5f-103">Au cours de cette tâche, vous allez définir quelques relations à base de termes pour les valeurs du domaine **nom du fournisseur** .</span><span class="sxs-lookup"><span data-stu-id="18c5f-103">In this task, you define a few term-based relations for values for the **Supplier Name** domain.</span></span> <span data-ttu-id="18c5f-104">Une relation à base de termes vous permet d’effectuer une correction sur un terme qui fait partie d’une valeur dans un domaine.</span><span class="sxs-lookup"><span data-stu-id="18c5f-104">A term-based relation enables you to make a correction to a term that is part of a value in a domain.</span></span> <span data-ttu-id="18c5f-105">Plusieurs valeurs qui sont identiques à l'exception de l'orthographe d'une partie commune peuvent ainsi être considérées comme synonymes identiques.</span><span class="sxs-lookup"><span data-stu-id="18c5f-105">It enables multiple values that are identical except for the spelling of a common part of them to be considered identical synonyms.</span></span> <span data-ttu-id="18c5f-106">Par exemple, **Inc.** peut être corrigé pour être **incorporé**.</span><span class="sxs-lookup"><span data-stu-id="18c5f-106">For example, **Inc.** can be corrected to **Incorporated**.</span></span> <span data-ttu-id="18c5f-107">DQS utilise ces relations lors des processus de découverte des connaissances, de nettoyage, ou de mise en correspondance.</span><span class="sxs-lookup"><span data-stu-id="18c5f-107">DQS uses these relations in the knowledge discovery, cleansing, or matching processes.</span></span> <span data-ttu-id="18c5f-108">Pour plus d’informations, consultez [créer des relations à base de termes](https://msdn.microsoft.com/library/hh510404.aspx) .</span><span class="sxs-lookup"><span data-stu-id="18c5f-108">See [Create Term-based Relations](https://msdn.microsoft.com/library/hh510404.aspx) for more details.</span></span>  
  
1.  <span data-ttu-id="18c5f-109">Sélectionnez **nom du fournisseur** dans la **liste domaine**.</span><span class="sxs-lookup"><span data-stu-id="18c5f-109">Select **Supplier Name** in the **Domain list**.</span></span>  
  
2.  <span data-ttu-id="18c5f-110">Basculez vers l’onglet **relations à base de termes** dans le volet droit.</span><span class="sxs-lookup"><span data-stu-id="18c5f-110">Switch to the **Term-Based Relationships** tab in the right pane.</span></span>  
  
3.  <span data-ttu-id="18c5f-111">Cliquez sur le bouton **Ajouter une nouvelle relation** dans la barre d’outils pour ajouter une relation à la table.</span><span class="sxs-lookup"><span data-stu-id="18c5f-111">Click **Add new relation** button on the toolbar to add a relation to the table.</span></span>  
  
4.  <span data-ttu-id="18c5f-112">Tapez **Co.** dans le champ **valeur** et **société** pour le champ **corriger vers** .</span><span class="sxs-lookup"><span data-stu-id="18c5f-112">Type **Co.** for the **Value** field and **Company** for the **Correct To** field.</span></span>  
  
5.  <span data-ttu-id="18c5f-113">Répétez les deux étapes précédentes pour les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="18c5f-113">Repeat the previous two steps for the following values:</span></span>  
  
    |<span data-ttu-id="18c5f-114">Valeur</span><span class="sxs-lookup"><span data-stu-id="18c5f-114">Value</span></span>|<span data-ttu-id="18c5f-115">Corriger vers</span><span class="sxs-lookup"><span data-stu-id="18c5f-115">Correct To</span></span>|  
    |-----------|----------------|  
    |<span data-ttu-id="18c5f-116">Corp.</span><span class="sxs-lookup"><span data-stu-id="18c5f-116">Corp.</span></span>|<span data-ttu-id="18c5f-117">Corporation</span><span class="sxs-lookup"><span data-stu-id="18c5f-117">Corporation</span></span>|  
    |<span data-ttu-id="18c5f-118">Inc.</span><span class="sxs-lookup"><span data-stu-id="18c5f-118">Inc.</span></span>|<span data-ttu-id="18c5f-119">Incorporated</span><span class="sxs-lookup"><span data-stu-id="18c5f-119">Incorporated</span></span>|  
  
     <span data-ttu-id="18c5f-120">![Relations à base de termes](../../2014/tutorials/media/et-settingtermbasedrelations.jpg "Relations à base de termes")</span><span class="sxs-lookup"><span data-stu-id="18c5f-120">![Term Based Relations](../../2014/tutorials/media/et-settingtermbasedrelations.jpg "Term Based Relations")</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="18c5f-121">étape suivante</span><span class="sxs-lookup"><span data-stu-id="18c5f-121">Next Step</span></span>  
 [<span data-ttu-id="18c5f-122">Tâche 6 : Définition des synonymes</span><span class="sxs-lookup"><span data-stu-id="18c5f-122">Task 6: Setting Synonyms</span></span>](../../2014/tutorials/task-6-setting-synonyms.md)  
  
  
