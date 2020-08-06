---
title: Définir et configurer des unités de mesure (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a15a96c3-7d2c-433e-a440-4ea051e967a9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c01523dad9a96d2d45b96474d36873bac2484343
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600535"
---
# <a name="set-and-configure-measurement-units-report-builder-and-ssrs"></a><span data-ttu-id="7fda0-102">Définir et configurer des unités de mesure (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="7fda0-102">Set and Configure Measurement Units (Report Builder and SSRS)</span></span>
  <span data-ttu-id="7fda0-103">Les indicateurs fournissent deux unités de mesure : valeurs en pourcentage et valeurs numériques.</span><span class="sxs-lookup"><span data-stu-id="7fda0-103">Indicators provide two measurement units: percentage and numeric.</span></span> <span data-ttu-id="7fda0-104">Par défaut, les indicateurs sont configurés pour utiliser des pourcentages comme unité de mesure.</span><span class="sxs-lookup"><span data-stu-id="7fda0-104">By default, indicators are configured to use percentages as the measurement unit.</span></span> <span data-ttu-id="7fda0-105">Cela signifie que les valeurs d'indicateur affectées à chaque icône dans le jeu d'indicateurs sont déterminées par une plage de pourcentages.</span><span class="sxs-lookup"><span data-stu-id="7fda0-105">This means that the indicator values assigned to each icon in the indicator set are determined by a percentage range.</span></span> <span data-ttu-id="7fda0-106">Les plages de pourcentages sont réparties de façon égale entre les icônes dans le jeu d'indicateurs.</span><span class="sxs-lookup"><span data-stu-id="7fda0-106">The percentage ranges are evenly divided across the icons in the indicator set.</span></span> <span data-ttu-id="7fda0-107">Chaque icône représente un état d'indicateur.</span><span class="sxs-lookup"><span data-stu-id="7fda0-107">Each icon represents an indicator state.</span></span> <span data-ttu-id="7fda0-108">Vous pouvez modifier les pourcentages pour chaque icône du jeu d'indicateurs en spécifiant différents pourcentages de début et de fin.</span><span class="sxs-lookup"><span data-stu-id="7fda0-108">You can change the percentages for each icon in the indicator set by specifying different start and end percentages.</span></span> <span data-ttu-id="7fda0-109">Les indicateurs détectent également automatiquement les valeurs maximale et minimale des données.</span><span class="sxs-lookup"><span data-stu-id="7fda0-109">Indicators also automatically detect the minimum and maximum values in the data.</span></span>  
  
 <span data-ttu-id="7fda0-110">Vous pouvez remplacer l'unité de mesure par une valeur numérique.</span><span class="sxs-lookup"><span data-stu-id="7fda0-110">You can change the measurement unit to be a numeric value.</span></span> <span data-ttu-id="7fda0-111">Dans ce cas, vous ne spécifiez pas de valeur minimale ou maximale pour les données ; à la place, vous fournissez uniquement les valeurs de début et de fin pour chaque icône utilisée par l'indicateur.</span><span class="sxs-lookup"><span data-stu-id="7fda0-111">In this case, you do not specify minimum or maximum for the data; instead, you provide only the start and end values for each icon that the indicator uses.</span></span>  
  
 <span data-ttu-id="7fda0-112">Les options telles que les unités de mesure peuvent être définies à l'aide d'expressions.</span><span class="sxs-lookup"><span data-stu-id="7fda0-112">Options such as measurement units can be set by using expressions.</span></span> <span data-ttu-id="7fda0-113">Pour plus d’informations, consultez [Expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7fda0-113">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-use-the-numeric-state-measurement-unit"></a><span data-ttu-id="7fda0-114">Pour utiliser l'unité de mesure des états de type numérique</span><span class="sxs-lookup"><span data-stu-id="7fda0-114">To use the numeric state measurement unit</span></span>  
  
1.  <span data-ttu-id="7fda0-115">Cliquez avec le bouton droit sur l’indicateur à modifier, puis cliquez sur **Propriétés de l’indicateur**.</span><span class="sxs-lookup"><span data-stu-id="7fda0-115">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="7fda0-116">Cliquez sur **Valeur et états** dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="7fda0-116">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="7fda0-117">Dans la liste **Unité de mesure des états** , cliquez sur **Numérique**.</span><span class="sxs-lookup"><span data-stu-id="7fda0-117">In the **States Measurement Unit** list, click **Numeric**.</span></span>  
  
     <span data-ttu-id="7fda0-118">Cliquez éventuellement sur le bouton **Expression** (*fx*) pour modifier une expression qui définit la valeur de l’option.</span><span class="sxs-lookup"><span data-stu-id="7fda0-118">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the value of the option.</span></span>  
  
4.  <span data-ttu-id="7fda0-119">Pour chaque icône du jeu d’indicateurs, mettez à jour les valeurs dans les zones de texte **Début** et **Fin** .</span><span class="sxs-lookup"><span data-stu-id="7fda0-119">For each icon in the indicator set, update the values in the **Start** and **End** text boxes.</span></span>  
  
     <span data-ttu-id="7fda0-120">Cliquez éventuellement sur le bouton **Expression** (*fx*) pour modifier une expression qui définit les valeurs des options **Début** et **Fin** .</span><span class="sxs-lookup"><span data-stu-id="7fda0-120">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the values of the **Start** and **End** options.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7fda0-121">Les valeurs des zones de texte **Début** et **Fin** doivent être numériques.</span><span class="sxs-lookup"><span data-stu-id="7fda0-121">The values in the **Start** and **End** text boxes must be numeric.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-use-the-percentage-measurement-unit"></a><span data-ttu-id="7fda0-122">Pour utiliser l'unité de mesure en pourcentage</span><span class="sxs-lookup"><span data-stu-id="7fda0-122">To use the percentage measurement unit</span></span>  
  
1.  <span data-ttu-id="7fda0-123">Cliquez avec le bouton droit sur l’indicateur à modifier, puis cliquez sur **Propriétés de l’indicateur**.</span><span class="sxs-lookup"><span data-stu-id="7fda0-123">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="7fda0-124">Cliquez sur **Valeur et états** dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="7fda0-124">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="7fda0-125">Dans la liste **Unité de mesure des états** , cliquez sur **Pourcentage**.</span><span class="sxs-lookup"><span data-stu-id="7fda0-125">In the **States Measurement Unit** list, click **Percentage**.</span></span>  
  
     <span data-ttu-id="7fda0-126">Cliquez éventuellement sur le bouton **Expression** (*fx*) pour modifier une expression qui définit la valeur de l’option.</span><span class="sxs-lookup"><span data-stu-id="7fda0-126">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the value of the option.</span></span>  
  
4.  <span data-ttu-id="7fda0-127">Vous pouvez éventuellement modifier les options **Minimum** et **Maximum** pour utiliser des valeurs spécifiques au lieu de détecter automatiquement les valeurs minimale et maximale des données que l’indicateur utilise.</span><span class="sxs-lookup"><span data-stu-id="7fda0-127">Optionally, change the **Minimum** and **Maximum** options to use specific values instead of automatically detecting the minimum and maximum values of the data that the indicator uses.</span></span> <span data-ttu-id="7fda0-128">La valeur de l’option **Minimum** doit être inférieure à celle de l’option **Maximum**.</span><span class="sxs-lookup"><span data-stu-id="7fda0-128">The value of **Minimum** must be smaller than the value of **Maximum**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7fda0-129">Si vous définissez explicitement les valeurs minimale et maximale, cette plage de valeurs est utilisée par l'indicateur indépendamment des valeurs minimale et maximale réelles des données.</span><span class="sxs-lookup"><span data-stu-id="7fda0-129">If you explicitly set minimum and maximum values, that value range is used by the indicator regardless of the actual the minimum and maximum values in the data.</span></span> <span data-ttu-id="7fda0-130">Cela signifie que les valeurs inférieures à la valeur minimale et celles supérieures à la valeur maximale sont exclues de l'évaluation qui détermine l'icône d'indicateur à afficher dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="7fda0-130">This means that values lower than the minimum and higher than the maximum are excluded from the evaluation that determine what indictor icon to show in the report.</span></span>  
  
     <span data-ttu-id="7fda0-131">Cliquez éventuellement sur le bouton **Expression** (*fx*) pour modifier une expression qui définit les valeurs de l’option.</span><span class="sxs-lookup"><span data-stu-id="7fda0-131">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the values of the option.</span></span>  
  
5.  <span data-ttu-id="7fda0-132">Pour chaque icône du jeu d’indicateurs, mettez à jour les valeurs dans les zones de texte **Début** et **Fin** .</span><span class="sxs-lookup"><span data-stu-id="7fda0-132">For each icon in the indicator set, update the values in the **Start** and **End** text boxes.</span></span>  
  
     <span data-ttu-id="7fda0-133">Cliquez éventuellement sur le bouton **Expression** (*fx*) pour modifier une expression qui définit les valeurs des options **Début** et **Fin** .</span><span class="sxs-lookup"><span data-stu-id="7fda0-133">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the values of the **Start** and **End** options.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7fda0-134">Les valeurs des zones de texte **Début** et **Fin** doivent être numériques.</span><span class="sxs-lookup"><span data-stu-id="7fda0-134">The values in the **Start** and **End** text boxes must be numeric.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7fda0-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7fda0-135">See Also</span></span>  
 [<span data-ttu-id="7fda0-136">Indicateurs &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7fda0-136">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
