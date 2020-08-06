---
title: 'Étape 8 : Comment rendre le package de la leçon 1 plus facile à assimiler | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: e3751e53-77c7-47d0-8fe8-73ed1a53413a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 67fb8e2adb9062b5b777acc14df0ddc5b45884ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605574"
---
# <a name="step-8-making-the-lesson-1-package-easier-to-understand"></a><span data-ttu-id="8e7bf-102">Étape 8 : Comment rendre le package de la leçon 1 plus facile à assimiler</span><span class="sxs-lookup"><span data-stu-id="8e7bf-102">Step 8: Making the Lesson 1 Package Easier to Understand</span></span>
  <span data-ttu-id="8e7bf-103">Une fois la configuration du package de la leçon 1 terminée; il peut être judicieux de mettre un peu d'ordre dans la disposition du package.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-103">Now that you have completed the configuration of the Lesson 1 package, it is a good idea to tidy up the package layout.</span></span> <span data-ttu-id="8e7bf-104">Si les formes dans la disposition des flux de contrôle et de données affichent des tailles aléatoires, ou si elles ne sont pas alignées ou groupées, la maîtrise des fonctionnalités du package peut s'avérer plus délicate.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-104">If the shapes in the control and data flow layouts are random sizes, or if the shapes are not aligned or grouped, the functionality of package can be more difficult to understand.</span></span>  
  
 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="8e7bf-105">Data Tools fournit des outils qui facilitent et accélèrent le processus de mise en forme de la disposition des packages.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-105">Data Tools provides tools that make it easy and quick to format the package layout.</span></span> <span data-ttu-id="8e7bf-106">Les fonctionnalités de mise en forme offrent notamment la possibilité d'attribuer la même taille aux formes, de les aligner et de manipuler l'espace horizontal et vertical entre elles.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-106">The formatting features include the ability to make shapes the same size, align shapes, and manipulate the horizontal and vertical spacing between shapes.</span></span>  
  
 <span data-ttu-id="8e7bf-107">Une autre manière d'améliorer la compréhension des fonctionnalités des packages est d'ajouter des annotations décrivant ces fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-107">Another way to improve the understanding of package functionality is to add annotations that describe package functionality.</span></span>  
  
 <span data-ttu-id="8e7bf-108">Au cours de cette tâche, vous allez exploiter les fonctionnalités de mise en forme disponibles dans [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools pour améliorer la disposition du flux de données et ajouter une annotation à ce dernier.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-108">In this task, you will use the formatting features in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools to improve the layout of the data flow and also add an annotation to the data flow.</span></span>  
  
### <a name="to-format-the-layout-of-the-data-flow"></a><span data-ttu-id="8e7bf-109">Pour mettre en forme la disposition du flux de données</span><span class="sxs-lookup"><span data-stu-id="8e7bf-109">To format the layout of the data flow</span></span>  
  
1.  <span data-ttu-id="8e7bf-110">Si le package de la leçon 1 n'est pas encore ouvert, double-cliquez sur le fichier Lesson 1.dtsx dans l'Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-110">If the Lesson 1 package is not already open, double-click Lesson 1.dtsx in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="8e7bf-111">Cliquez sur l'onglet **Flux de données** .</span><span class="sxs-lookup"><span data-stu-id="8e7bf-111">Click the **Data Flow** tab.</span></span>  
  
3.  <span data-ttu-id="8e7bf-112">Placez le curseur en haut et à droite de la transformation Extract Sample Currency, cliquez, puis faites glisser le curseur sur tous les composants du flux de données.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-112">Place the cursor to the top and to the right of the Extract Sample Currency transformation, click, and then drag the cursor across all the data flow components.</span></span>  
  
4.  <span data-ttu-id="8e7bf-113">Dans le menu **Format** , pointez sur **Uniformiser la taille**, puis cliquez sur **Les deux**.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-113">On the **Format** menu, point to **Make Same Size**, and then click **Both**.</span></span>  
  
5.  <span data-ttu-id="8e7bf-114">Avec les objets du flux de données sélectionnés, dans le menu **Format** , pointez sur **Aligner**, puis cliquez sur **Gauche**.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-114">With the data flow objects selected, on the **Format** menu, point to **Align**, and then click **Lefts**.</span></span>  
  
### <a name="to-add-an-annotation-to-the-data-flow"></a><span data-ttu-id="8e7bf-115">Pour ajouter une annotation au flux de données</span><span class="sxs-lookup"><span data-stu-id="8e7bf-115">To add an annotation to the data flow</span></span>  
  
1.  <span data-ttu-id="8e7bf-116">Cliquez avec le bouton droit n’importe où sur l’arrière-plan de la zone de conception du flux de données, puis cliquez sur **Ajouter une annotation**.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-116">Right-click anywhere in the background of the data flow design surface and then click **Add Annotation**.</span></span>  
  
2.  <span data-ttu-id="8e7bf-117">Tapez ou collez le texte suivant dans la zone de l'annotation.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-117">Type or paste the following text in the annotation box.</span></span>  
  
     <span data-ttu-id="8e7bf-118">**Le flux de données extrait les données d'un fichier, recherche des valeurs dans la colonne CurrencyKey de la table DimCurrency et dans la colonne DateKey de la table DimDate, puis écrit les données dans la table NewFactCurrencyRate.**</span><span class="sxs-lookup"><span data-stu-id="8e7bf-118">**The data flow extracts data from a file, looks up values in the CurrencyKey column in the DimCurrency table and the DateKey column in the DimDate table, and writes the data to the NewFactCurrencyRate table.**</span></span>  
  
     <span data-ttu-id="8e7bf-119">Pour renvoyer à la ligne le texte de la zone d'annotation, placez le curseur à l'endroit où vous souhaitez démarrer une nouvelle ligne, puis appuyez sur la touche Entrée.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-119">To wrap the text in the annotation box, place the cursor where you want to start a new line and press the Enter key.</span></span>  
  
     <span data-ttu-id="8e7bf-120">Si vous n'ajoutez aucun texte dans la zone de l'annotation, cette dernière disparaît lorsque vous cliquez en dehors.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-120">If you do not add text to the annotation box, it disappears when you click outside the box.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8e7bf-121">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="8e7bf-121">Next Steps</span></span>  
 [<span data-ttu-id="8e7bf-122">Étape 9 : Test du package du tutoriel de la leçon 1</span><span class="sxs-lookup"><span data-stu-id="8e7bf-122">Step 9: Testing the Lesson 1 Tutorial Package</span></span>](../integration-services/lesson-1-9-testing-the-lesson-1-tutorial-package.md)  
  
  
