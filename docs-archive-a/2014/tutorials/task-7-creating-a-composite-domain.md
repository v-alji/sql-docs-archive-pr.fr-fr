---
title: 'Tâche 7 : création d’un domaine composite | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: ae778647-1df0-4952-9a69-0ef6177eea9c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 42936d25e267bcad5ba8ae512750f9e12f041579
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600381"
---
# <a name="task-7-creating-a-composite-domain"></a><span data-ttu-id="0654d-102">Tâche 7 : Création d’un domaine composite</span><span class="sxs-lookup"><span data-stu-id="0654d-102">Task 7: Creating a Composite Domain</span></span>
  <span data-ttu-id="0654d-103">Au cours de cette tâche, vous allez créer un domaine composite, **validation d’adresse**, qui comprend les domaines **adresse**, **ville**, **État**et **Code postal** .</span><span class="sxs-lookup"><span data-stu-id="0654d-103">In this task, you create a composite domain, **Address Validation**, which comprises **Address Line**, **City**, **State**, and **Zip** domains.</span></span> <span data-ttu-id="0654d-104">Un domaine composite permet de définir une règle interdomaines qui implique plusieurs domaines.</span><span class="sxs-lookup"><span data-stu-id="0654d-104">A composite domain lets you define a cross-domain rule that involves multiple domains in a rule.</span></span> <span data-ttu-id="0654d-105">Un domaine composite présente d'autres avantages, notamment, il permet d'analyser une valeur de champ dans plusieurs domaines.</span><span class="sxs-lookup"><span data-stu-id="0654d-105">There are other advantages to a composite domain such as being able to parse a field value into multiple domains.</span></span>  <span data-ttu-id="0654d-106">Par exemple, une valeur d'un champ Nom complet peut être analysée dans des domaines Prénom, Deuxième prénom et Nom de famille distincts.</span><span class="sxs-lookup"><span data-stu-id="0654d-106">For example, a value for a Full Name field can be parsed into separate First Name, Middle Name, and Last Name domains.</span></span> <span data-ttu-id="0654d-107">Dans ce didacticiel, vous allez uniquement définir une règle interdomaines.</span><span class="sxs-lookup"><span data-stu-id="0654d-107">In this tutorial, you only define a cross-domain rule.</span></span> <span data-ttu-id="0654d-108">Pour plus d’informations, consultez [gestion d’un domaine composite](https://msdn.microsoft.com/library/hh510399.aspx) .</span><span class="sxs-lookup"><span data-stu-id="0654d-108">See [Managing a Composite Domain](https://msdn.microsoft.com/library/hh510399.aspx) for more details.</span></span>  
  
1.  <span data-ttu-id="0654d-109">Dans le volet gauche, cliquez sur le bouton **créer un domaine composite** dans la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="0654d-109">In the left pane, click **Create a composite domain** button on the toolbar.</span></span>  
  
     <span data-ttu-id="0654d-110">![Bouton à la barre d'outils Créer un domaine composite](../../2014/tutorials/media/et-creatingacompositedomain-01.jpg "Bouton à la barre d'outils Créer un domaine composite")</span><span class="sxs-lookup"><span data-stu-id="0654d-110">![Create a Composite Domain Toolbar Button](../../2014/tutorials/media/et-creatingacompositedomain-01.jpg "Create a Composite Domain Toolbar Button")</span></span>  
  
2.  <span data-ttu-id="0654d-111">Entrez la **validation d’adresse** pour le nom de **domaine composite**.</span><span class="sxs-lookup"><span data-stu-id="0654d-111">Enter **Address Validation** for the **Composite Domain Name**.</span></span>  
  
     <span data-ttu-id="0654d-112">![Domaine composite de validation d'adresses](../../2014/tutorials/media/et-creatingacompositedomain-02.jpg "Domaine composite de validation d'adresses")</span><span class="sxs-lookup"><span data-stu-id="0654d-112">![Address Validation Composite Domain](../../2014/tutorials/media/et-creatingacompositedomain-02.jpg "Address Validation Composite Domain")</span></span>  
  
3.  <span data-ttu-id="0654d-113">Dans la liste domaine, sélectionnez **adresse**, **ville**, **État**et **Code postal** , puis cliquez sur la **flèche droite** pour les ajouter à la liste **domaines dans le domaine composite** .</span><span class="sxs-lookup"><span data-stu-id="0654d-113">From the domain list select **Address Line**, **City**, **State**, and **Zip** and click **right arrow** to add them to the **Domains in Composite Domain** list.</span></span>  
  
4.  <span data-ttu-id="0654d-114">Cliquez sur **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="0654d-114">Click **OK** to close the dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="0654d-115">étape suivante</span><span class="sxs-lookup"><span data-stu-id="0654d-115">Next Step</span></span>  
 [<span data-ttu-id="0654d-116">Tâche 8 : Création d’une règle de domaine composite</span><span class="sxs-lookup"><span data-stu-id="0654d-116">Task 8: Creating a Composite Domain Rule</span></span>](../../2014/tutorials/task-8-creating-a-composite-domain-rule.md)  
  
  
