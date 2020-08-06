---
title: Modification des noms de tables par défaut | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ddd97483-a76d-43c1-8b40-fc7cc57fb0c2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 254f797be95f60211983400b019415431d4cf39c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600300"
---
# <a name="modifying-default-table-names"></a><span data-ttu-id="348fd-102">Modification des noms de tables par défaut</span><span class="sxs-lookup"><span data-stu-id="348fd-102">Modifying Default Table Names</span></span>
  <span data-ttu-id="348fd-103">Vous pouvez modifier la valeur de la propriété **FriendlyName** des objets de la vue de source de données pour en faciliter l'utilisation et la compréhension.</span><span class="sxs-lookup"><span data-stu-id="348fd-103">You can change the value of the **FriendlyName** property for objects in the data source view to make them easier to notice and use.</span></span>  
  
 <span data-ttu-id="348fd-104">Au cours de la tâche suivante, vous allez modifier le nom de chaque table dans la vue de source de données en supprimant les préfixes «**Dim**» et «**Fact**» de ces tables.</span><span class="sxs-lookup"><span data-stu-id="348fd-104">In the following task, you will change the friendly name of each table in the data source view by removing the "**Dim**" and "**Fact**" prefixes from these tables.</span></span> <span data-ttu-id="348fd-105">Cela rendre le cube et les objets de la dimension (que vous allez définir dans la leçon suivante) plus faciles à comprendre et à utiliser.</span><span class="sxs-lookup"><span data-stu-id="348fd-105">This will make the cube and dimension objects (that you will define in the next lesson) easier to notice and use.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="348fd-106">Vous pouvez également modifier les noms des colonnes, définir des colonnes calculées et joindre des tables ou des vues dans la vue de source de données pour en faciliter l'utilisation.</span><span class="sxs-lookup"><span data-stu-id="348fd-106">You can also change the friendly names of columns, define calculated columns, and join tables or views in the data source view to make them easier to use.</span></span>  
  
### <a name="to-modify-the-default-name-of-a-table"></a><span data-ttu-id="348fd-107">Pour modifier le nom par défaut d'une table</span><span class="sxs-lookup"><span data-stu-id="348fd-107">To modify the default name of a table</span></span>  
  
1.  <span data-ttu-id="348fd-108">Dans le volet **Tables** du **Concepteur de source de données**, cliquez avec le bouton droit sur la table **FactInternetSales** , puis cliquez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="348fd-108">In the **Tables** pane of **Data Source View Designer**, right-click the **FactInternetSales** table, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="348fd-109">Si la fenêtre Propriétés à droite de la fenêtre Microsoft Visual Studio ne s'affiche pas, cliquez sur le bouton **Masquer automatiquement** dans la barre de titre de la fenêtre Propriétés afin que cette fenêtre reste visible.</span><span class="sxs-lookup"><span data-stu-id="348fd-109">If the Properties window on the right side of the Microsoft Visual Studio window is not displayed, click the **Auto Hide** button on the title bar of the Properties window so that this window remains visible.</span></span>  
  
     <span data-ttu-id="348fd-110">Il est plus facile de modifier les propriétés de chaque table dans la vue de source de données si la fenêtre des propriétés reste ouverte.</span><span class="sxs-lookup"><span data-stu-id="348fd-110">It is easier to change the properties for each table in the data source view when the Properties window remains open.</span></span> <span data-ttu-id="348fd-111">Si vous n'ouvrez pas la fenêtre en utilisant le bouton **Masquer automatiquement** , elle se ferme lorsque vous cliquez sur un autre objet dans le volet **Diagramme** .</span><span class="sxs-lookup"><span data-stu-id="348fd-111">If you do not pin the window open by using the **Auto Hide** button, the window will close when you click a different object in the **Diagram** pane.</span></span>  
  
3.  <span data-ttu-id="348fd-112">Modifiez la propriété **FriendlyName** de l’objet **FactInternetSales** en *`InternetSales`* .</span><span class="sxs-lookup"><span data-stu-id="348fd-112">Change the **FriendlyName** property for the **FactInternetSales** object to *`InternetSales`*.</span></span>  
  
     <span data-ttu-id="348fd-113">Lorsque vous cliquez en dehors de la cellule correspondant à la propriété **FriendlyName** , la modification est appliquée.</span><span class="sxs-lookup"><span data-stu-id="348fd-113">When you click away from the cell for the **FriendlyName** property, the change is applied.</span></span> <span data-ttu-id="348fd-114">Dans la leçon suivante, vous définirez un groupe de mesures basé sur cette table de faits.</span><span class="sxs-lookup"><span data-stu-id="348fd-114">In the next lesson, you will define a measure group that is based on this fact table.</span></span> <span data-ttu-id="348fd-115">Le nom de la table de faits sera InternetSales au lieu de FactInternetSales à cause de la modification que vous avez apportée dans cette leçon.</span><span class="sxs-lookup"><span data-stu-id="348fd-115">The name of the fact table will be InternetSales instead of FactInternetSales because of the change you made in this lesson.</span></span>  
  
4.  <span data-ttu-id="348fd-116">Cliquez sur **DimProduct** dans le volet **Tables** .</span><span class="sxs-lookup"><span data-stu-id="348fd-116">Click **DimProduct** in the **Tables** pane.</span></span> <span data-ttu-id="348fd-117">Dans la Fenêtre Propriétés, remplacez la valeur de la propriété **FriendlyName** par *`Product`* .</span><span class="sxs-lookup"><span data-stu-id="348fd-117">In the Properties window, change the **FriendlyName** property to *`Product`*.</span></span>  
  
5.  <span data-ttu-id="348fd-118">Modifiez la propriété **FriendlyName** de chaque table restante dans la vue de source de données en procédant de la même façon, pour supprimer le préfixe «**Dim**».</span><span class="sxs-lookup"><span data-stu-id="348fd-118">Change the **FriendlyName** property of each remaining table in the data source view in the same way, to remove the "**Dim**" prefix.</span></span>  
  
6.  <span data-ttu-id="348fd-119">Une fois terminé, cliquez sur le bouton **Masquer automatiquement** pour masquer à nouveau la fenêtre des propriétés.</span><span class="sxs-lookup"><span data-stu-id="348fd-119">When you have finished, click the **Auto Hide** button to hide the Properties window again.</span></span>  
  
7.  <span data-ttu-id="348fd-120">Dans le menu **Fichier** , ou dans la barre d'outils de [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], cliquez sur **Enregistrer tout** pour enregistrer les modifications vous avez faites à ce stade dans le projet Didacticiel [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="348fd-120">On the **File** menu, or on the toolbar of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Save All** to save the changes you have made to this point in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project.</span></span> <span data-ttu-id="348fd-121">Vous pouvez arrêter le didacticiel ici si vous le souhaitez et le reprendre ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="348fd-121">You can stop the tutorial here if you want and resume it later.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="348fd-122">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="348fd-122">Next Lesson</span></span>  
 [<span data-ttu-id="348fd-123">Leçon 2 : Définition et déploiement d'un cube</span><span class="sxs-lookup"><span data-stu-id="348fd-123">Lesson 2: Defining and Deploying a Cube</span></span>](lesson-2-defining-and-deploying-a-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="348fd-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="348fd-124">See Also</span></span>  
 <span data-ttu-id="348fd-125">[Vues de sources de données dans les modèles multidimensionnels](multidimensional-models/data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="348fd-125">[Data Source Views in Multidimensional Models](multidimensional-models/data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="348fd-126">Modifier les propriétés d’une vue de source de données &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="348fd-126">Change Properties in a Data Source View &#40;Analysis Services&#41;</span></span>](multidimensional-models/change-properties-in-a-data-source-view-analysis-services.md)  
  
  
