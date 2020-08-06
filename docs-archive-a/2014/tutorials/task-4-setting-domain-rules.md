---
title: 'Tâche 4 : définition des règles de domaine | Microsoft Docs'
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 3a7162ba-cf2f-481f-830d-bb6a02823827
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 42bdbd0228fdd3515f68ce830581f445242768e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601189"
---
# <a name="task-4-setting-domain-rules"></a><span data-ttu-id="1c918-102">Tâche 4 : Définition de règles de domaine</span><span class="sxs-lookup"><span data-stu-id="1c918-102">Task 4: Setting Domain Rules</span></span>
  <span data-ttu-id="1c918-103">Dans cette tâche, vous allez créer une règle pour le domaine de **messagerie du contact** afin de vérifier si l’adresse de messagerie se termine par \*\* \@ Adventure-Works.com\*\*.</span><span class="sxs-lookup"><span data-stu-id="1c918-103">In this task, you create a rule for the **Contact Email** domain to verify if the email address ends with **\@adventure-works.com**.</span></span> <span data-ttu-id="1c918-104">Pour plus d’informations sur la page, consultez la rubrique [création d’une règle de domaine](https://msdn.microsoft.com/library/hh510397.aspx) .</span><span class="sxs-lookup"><span data-stu-id="1c918-104">See [Creating a Domain Rule](https://msdn.microsoft.com/library/hh510397.aspx) topic for more details on the page.</span></span>  
  
1.  <span data-ttu-id="1c918-105">Cliquez sur **adresse de messagerie du contact** dans la **liste domaine**.</span><span class="sxs-lookup"><span data-stu-id="1c918-105">Click **Contact Email** in the **Domain list**.</span></span>  
  
2.  <span data-ttu-id="1c918-106">Basculez vers l’onglet **règles de domaine** dans le volet droit.</span><span class="sxs-lookup"><span data-stu-id="1c918-106">Switch to the **Domain Rules** tab in the right pane.</span></span>  
  
     <span data-ttu-id="1c918-107">![Bouton de la barre d'outils Ajouter une nouvelle règle de domaine](../../2014/tutorials/media/et-settingdomainrules-01.jpg "Bouton de la barre d'outils Ajouter une nouvelle règle de domaine")</span><span class="sxs-lookup"><span data-stu-id="1c918-107">![Add a New Domain Rule Toolbar Button](../../2014/tutorials/media/et-settingdomainrules-01.jpg "Add a New Domain Rule Toolbar Button")</span></span>  
  
3.  <span data-ttu-id="1c918-108">Dans le volet droit, cliquez sur le bouton **Ajouter une nouvelle règle de domaine** dans la barre d’outils (Voir l’image) pour ajouter une règle.</span><span class="sxs-lookup"><span data-stu-id="1c918-108">In the right pane, click **Add a new domain rule** button on the toolbar (see the image) to add a rule.</span></span>  
  
4.  <span data-ttu-id="1c918-109">Tapez **validation** de l’adresse de messagerie pour le nom de la **règle** et appuyez sur **entrée**.</span><span class="sxs-lookup"><span data-stu-id="1c918-109">Type **Email Validation** for the **rule name** and press **ENTER**.</span></span> <span data-ttu-id="1c918-110">La case à cocher **active** doit être activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="1c918-110">The **Active** check box should be checked by default.</span></span> <span data-ttu-id="1c918-111">Ce contrôle vous permet de désactiver temporairement une règle.</span><span class="sxs-lookup"><span data-stu-id="1c918-111">This control allows you to deactivate a rule temporarily.</span></span>  
  
5.  <span data-ttu-id="1c918-112">Dans le volet **créer une règle** , cliquez sur **flèche bas**, puis sélectionnez la **valeur se termine par**.</span><span class="sxs-lookup"><span data-stu-id="1c918-112">In the **Build a Rule** pane, click **down arrow**, and select **Value ends with**.</span></span>  
  
6.  <span data-ttu-id="1c918-113">Tapez \*\* \@ Adventure-Works.com\*\* dans la zone de texte et appuyez sur la touche **Tab**.</span><span class="sxs-lookup"><span data-stu-id="1c918-113">Type **\@adventure-works.com** in the text box and press **TAB**.</span></span> <span data-ttu-id="1c918-114">Vous pouvez ajouter d’autres conditions en cliquant sur le bouton **Ajouter une nouvelle condition à la clause sélectionnée** dans le volet **créer une règle** .</span><span class="sxs-lookup"><span data-stu-id="1c918-114">You can add more conditions by clicking **Add a new condition to the selected clause** toolbar button in the **Build a Rule** pane.</span></span>  
  
     <span data-ttu-id="1c918-115">![Règle de validation du courrier électronique](../../2014/tutorials/media/et-settingdomainrules-02.jpg "Règle de validation du courrier électronique")</span><span class="sxs-lookup"><span data-stu-id="1c918-115">![Email Validation Rule](../../2014/tutorials/media/et-settingdomainrules-02.jpg "Email Validation Rule")</span></span>  
  
7.  <span data-ttu-id="1c918-116">Cliquez sur le bouton **exécuter la règle de domaine sélectionnée sur les données de test** dans la barre d’outils du volet droit pour tester la règle par rapport aux exemples de données.</span><span class="sxs-lookup"><span data-stu-id="1c918-116">Click **Run the selected domain rule on test data** button on the toolbar in the right pane to test the rule against sample data.</span></span>  
  
     <span data-ttu-id="1c918-117">![Bouton de la barre d'outils Exécuter la règle de domaine sur des données de test](../../2014/tutorials/media/et-settingdomainrules-03.jpg "Bouton de la barre d'outils Exécuter la règle de domaine sur des données de test")</span><span class="sxs-lookup"><span data-stu-id="1c918-117">![Run the Domain Rule on Test Data Toolbar Button](../../2014/tutorials/media/et-settingdomainrules-03.jpg "Run the Domain Rule on Test Data Toolbar Button")</span></span>  
  
8.  <span data-ttu-id="1c918-118">Dans la boîte de dialogue **tester la règle de domaine** , cliquez sur **ajoute un nouveau terme de test pour le bouton règle de domaine** dans la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="1c918-118">In the **Test Domain Rule** dialog box, click **Adds a new testing term for the domain rule** button on the toolbar.</span></span>  
  
     <span data-ttu-id="1c918-119">![Boîte de dialogue Tester une règle de domaine](../../2014/tutorials/media/et-settingdomainrules-04.jpg "Boîte de dialogue Tester une règle de domaine")</span><span class="sxs-lookup"><span data-stu-id="1c918-119">![Test Domain Rule Dialog Box](../../2014/tutorials/media/et-settingdomainrules-04.jpg "Test Domain Rule Dialog Box")</span></span>  
  
9. <span data-ttu-id="1c918-120">Tapez **frank7 \@ Adventure-Works.com** (une valeur valide) dans la colonne **adresse de messagerie du contact** .</span><span class="sxs-lookup"><span data-stu-id="1c918-120">Type **frank7\@adventure-works.com** (a valid value) in the **Contact Email** column.</span></span>  
  
10. <span data-ttu-id="1c918-121">Répétez les deux étapes précédentes pour ajouter **joe2 \@ Adventure-Work.com** (une valeur non valide, sans').</span><span class="sxs-lookup"><span data-stu-id="1c918-121">Repeat previous two steps to add **joe2\@adventure-work.com** (an invalid value with no 's').</span></span>  
  
11. <span data-ttu-id="1c918-122">Cliquez sur le dernier bouton (**tester la règle de domaine sur tous les termes**) de la barre d’outils pour tester les données d’entrée par rapport à la règle.</span><span class="sxs-lookup"><span data-stu-id="1c918-122">Click the last button (**Test the domain rule on all the terms**) on the toolbar to test the input data against the rule.</span></span>  
  
     <span data-ttu-id="1c918-123">![Bouton de la barre d'outils Tester la règle de domaine sur tous les termes](../../2014/tutorials/media/et-settingdomainrules-05.jpg "Bouton de la barre d'outils Tester la règle de domaine sur tous les termes")</span><span class="sxs-lookup"><span data-stu-id="1c918-123">![Test the Domain Rule on All Terms Toolbar Button](../../2014/tutorials/media/et-settingdomainrules-05.jpg "Test the Domain Rule on All Terms Toolbar Button")</span></span>  
  
12. <span data-ttu-id="1c918-124">Notez que la première entrée est affichée comme un élément valide, et la seconde comme un élément non valide.</span><span class="sxs-lookup"><span data-stu-id="1c918-124">Notice that the first entry is shown as a valid item and the second one as an invalid item.</span></span>  
  
     <span data-ttu-id="1c918-125">![Résultats du test de la règle de domaine](../../2014/tutorials/media/et-settingdomainrules-06.jpg "Résultats du test de la règle de domaine")</span><span class="sxs-lookup"><span data-stu-id="1c918-125">![Test Domain Rule Results](../../2014/tutorials/media/et-settingdomainrules-06.jpg "Test Domain Rule Results")</span></span>  
  
13. <span data-ttu-id="1c918-126">Cliquez sur **Fermer** pour fermer la boîte de dialogue **tester la règle de domaine** .</span><span class="sxs-lookup"><span data-stu-id="1c918-126">Click **Close** to close the **Test Domain Rule** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="1c918-127">étape suivante</span><span class="sxs-lookup"><span data-stu-id="1c918-127">Next Step</span></span>  
 [<span data-ttu-id="1c918-128">Tâche 5 : Définition des relations basées sur des termes</span><span class="sxs-lookup"><span data-stu-id="1c918-128">Task 5: Setting Term Based Relationships</span></span>](../../2014/tutorials/task-5-setting-term-based-relationships.md)  
  
  
