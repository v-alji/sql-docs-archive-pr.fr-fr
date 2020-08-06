---
title: Définir l’étendue de synchronisation (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6f4a11e6-6151-47be-a43f-e3dbf6c0e737
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3efbb7774d5116c9b3a18457291434f2a05aac7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600534"
---
# <a name="set-synchronization-scope-report-builder-and-ssrs"></a><span data-ttu-id="a1d95-102">Définir l'étendue de synchronisation (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="a1d95-102">Set Synchronization Scope (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a1d95-103">Les indicateurs transmettent les valeurs des données en synchronisant la plage des valeurs d'indicateur dans une étendue spécifiée.</span><span class="sxs-lookup"><span data-stu-id="a1d95-103">Indicators convey data values by synchronizing across the range of indicator values within a specified scope.</span></span> <span data-ttu-id="a1d95-104">Par défaut, l'étendue est le conteneur parent de l'indicateur, tel que la table ou matrice qui contient l'indicateur.</span><span class="sxs-lookup"><span data-stu-id="a1d95-104">By default, the scope is the parent container of the indicator such as the table or matrix that contains the indicator.</span></span> <span data-ttu-id="a1d95-105">Vous pouvez modifier la synchronisation de l'indicateur selon la disposition de votre rapport.</span><span class="sxs-lookup"><span data-stu-id="a1d95-105">You can change the synchronization of the indicator depending on the layout of your report.</span></span> <span data-ttu-id="a1d95-106">Par exemple, si une région de données, comme une table, a un groupe de lignes, vous pouvez spécifier ce groupe comme étendue de l'indicateur.</span><span class="sxs-lookup"><span data-stu-id="a1d95-106">For example, if a data region such as a table has a row group, you can specify the group as the indicator scope.</span></span> <span data-ttu-id="a1d95-107">L'indicateur peut également omettre la synchronisation.</span><span class="sxs-lookup"><span data-stu-id="a1d95-107">The indicator can also omit synchronization.</span></span>  
  
 <span data-ttu-id="a1d95-108">Les options telles que les unités de mesure peuvent être définies à l'aide d'expressions.</span><span class="sxs-lookup"><span data-stu-id="a1d95-108">Options such as measurement units can be set by using expressions.</span></span> <span data-ttu-id="a1d95-109">Pour plus d’informations, consultez [Expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a1d95-109">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="a1d95-110">Pour obtenir des informations générales sur le fonctionnement et la définition de l’étendue dans les rapports, consultez [Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="a1d95-110">For general information about understanding and setting scope within reports, see [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-synchronization-scope-of-an-indicator"></a><span data-ttu-id="a1d95-111">Pour modifier l'étendue de synchronisation d'un indicateur</span><span class="sxs-lookup"><span data-stu-id="a1d95-111">To change the synchronization scope of an indicator</span></span>  
  
1.  <span data-ttu-id="a1d95-112">Cliquez avec le bouton droit sur l’indicateur que vous souhaitez modifier, puis cliquez sur Propriétés de l' **indicateur**.</span><span class="sxs-lookup"><span data-stu-id="a1d95-112">Right click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="a1d95-113">Cliquez sur **Valeur et états** dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="a1d95-113">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="a1d95-114">Dans la liste **Étendue de synchronisation** , cliquez sur l’étendue à appliquer.</span><span class="sxs-lookup"><span data-stu-id="a1d95-114">In the **Synchronization scope** list, click the scope that you want to apply.</span></span>  
  
     <span data-ttu-id="a1d95-115">L’option **(Aucune)** , qui supprime l’étendue de synchronisation de l’indicateur, est toujours disponible.</span><span class="sxs-lookup"><span data-stu-id="a1d95-115">The **(None)** option, which removes synchronization scope from the indicator, is always available.</span></span> <span data-ttu-id="a1d95-116">D'autres options dépendent de la disposition de votre rapport.</span><span class="sxs-lookup"><span data-stu-id="a1d95-116">Other options depend on the layout of your report.</span></span>  
  
     <span data-ttu-id="a1d95-117">Cliquez éventuellement sur le bouton **Expression** (*fx*) pour modifier une expression qui définit l’étendue.</span><span class="sxs-lookup"><span data-stu-id="a1d95-117">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the scope.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a1d95-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a1d95-118">See Also</span></span>  
 [<span data-ttu-id="a1d95-119">Indicateurs &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a1d95-119">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
