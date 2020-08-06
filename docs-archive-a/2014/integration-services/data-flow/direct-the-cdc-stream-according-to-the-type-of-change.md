---
title: Diriger le flux de capture de données modifiées en fonction du type de modification | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3afa531e-f425-40a4-a1bf-1c3e1727287e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4a9b4e0c6a196669e4cedafcecf0477b228f3001
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602941"
---
# <a name="direct-the-cdc-stream-according-to-the-type-of-change"></a><span data-ttu-id="64d44-102">Diriger le flux de capture de données modifiées en fonction du type de modification</span><span class="sxs-lookup"><span data-stu-id="64d44-102">Direct the CDC Stream According to the Type of Change</span></span>
  <span data-ttu-id="64d44-103">Pour pouvoir ajouter et configurer une transformation de séparateur de capture de données modifiées, le package doit contenir au moins une tâche de flux de données et une source CDC.</span><span class="sxs-lookup"><span data-stu-id="64d44-103">To add and configure a CDC splitter Transformation, the package must contain at least one Data Flow task and a CDC source.</span></span>  
  
 <span data-ttu-id="64d44-104">La source CDC ajoutée au package doit avoir un mode de traitement NetCDC sélectionné.</span><span class="sxs-lookup"><span data-stu-id="64d44-104">The CDC source added to the package must have a NetCDC processing mode selected.</span></span> <span data-ttu-id="64d44-105">Pour plus d’informations sur la sélection des modes de traitement, consultez [Éditeur de source CDC &#40;page Gestionnaire de connexions&#41;](../cdc-source-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="64d44-105">For more information on selecting processing modes, see [CDC Source Editor &#40;Connection Manager Page&#41;](../cdc-source-editor-connection-manager-page.md).</span></span>  
  
### <a name="to-direct-the-cdc-stream-according-to-the-type-of-change"></a><span data-ttu-id="64d44-106">Pour diriger le flux de données de capture de données modifiées en fonction du type de modification</span><span class="sxs-lookup"><span data-stu-id="64d44-106">To direct the CDC stream according to the type of change</span></span>  
  
1.  <span data-ttu-id="64d44-107">Dans [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], ouvrez le projet [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="64d44-107">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="64d44-108">Dans l’Explorateur de solutions, double-cliquez sur le package pour l’ouvrir.</span><span class="sxs-lookup"><span data-stu-id="64d44-108">In the Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="64d44-109">Cliquez sur l'onglet **Flux de données** , puis dans la **Boîte à outils**, faites glisser le séparateur de capture de données modifiées sur l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="64d44-109">Click the **Data Flow** tab, and then from the **Toolbox**, drag the CDC splitter to the design surface.</span></span>  
  
4.  <span data-ttu-id="64d44-110">Connectez la source CDC incluse dans le package au séparateur de capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="64d44-110">Connect the CDC source that is included in the package to the CDC Splitter.</span></span>  
  
5.  <span data-ttu-id="64d44-111">Connectez le séparateur de capture de données modifiées à une ou plusieurs destinations.</span><span class="sxs-lookup"><span data-stu-id="64d44-111">Connect the CDC splitter to one or more destinations.</span></span> <span data-ttu-id="64d44-112">vous pouvez connecter jusqu'à trois sorties différentes.</span><span class="sxs-lookup"><span data-stu-id="64d44-112">You can connect up to three different outputs.</span></span>  
  
6.  <span data-ttu-id="64d44-113">Sélectionnez l'une des sorties suivantes :</span><span class="sxs-lookup"><span data-stu-id="64d44-113">Select one of the following outputs:</span></span>  
  
    -   <span data-ttu-id="64d44-114">Sortie de suppression : sortie vers laquelle les lignes de modification DELETE sont dirigées.</span><span class="sxs-lookup"><span data-stu-id="64d44-114">Delete output: The output where DELETE change rows are directed.</span></span>  
  
    -   <span data-ttu-id="64d44-115">Sortie d'insertion : sortie vers laquelle les lignes de modification INSERT sont dirigées.</span><span class="sxs-lookup"><span data-stu-id="64d44-115">Insert output: The output where INSERT change rows are directed.</span></span>  
  
    -   <span data-ttu-id="64d44-116">Sortie de mise à jour : sortie vers laquelle les lignes de modification avant/après UPDATE et les lignes de modification MERGE sont dirigées.</span><span class="sxs-lookup"><span data-stu-id="64d44-116">Update output: The output where before/after UPDATE change rows and Merge change rows are directed.</span></span>  
  
7.  <span data-ttu-id="64d44-117">Éventuellement, vous pouvez configurer les propriétés avancées à l'aide de la boîte de dialogue **Éditeur avancé** .</span><span class="sxs-lookup"><span data-stu-id="64d44-117">Optionally, you can configure the advanced properties using the **Advanced Editor** dialog box.</span></span>  
  
     <span data-ttu-id="64d44-118">La boîte de dialogue **Éditeur avancé** contient les propriétés qui peuvent être définies par programme.</span><span class="sxs-lookup"><span data-stu-id="64d44-118">The **Advanced Editor** dialog box contains the properties that can be set programmatically.</span></span>  
  
     <span data-ttu-id="64d44-119">Pour ouvrir la boîte de dialogue **Éditeur avancé** :</span><span class="sxs-lookup"><span data-stu-id="64d44-119">To open the **Advanced Editor** dialog box:</span></span>  
  
    -   <span data-ttu-id="64d44-120">Sur l'écran **Flux de données** de votre projet [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] , cliquez avec le bouton droit sur le séparateur de capture de données modifiées, puis sélectionnez **Afficher l'éditeur avancé**.</span><span class="sxs-lookup"><span data-stu-id="64d44-120">In the **Data Flow** screen of your [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project, right click the CDC splitter and select **Show Advanced Editor**.</span></span>  
  
     <span data-ttu-id="64d44-121">Pour plus d'informations sur l'utilisation du séparateur de capture de données modifiées, consultez Composants de capture de données modifiées pour Microsoft SQL Server Integration Services.</span><span class="sxs-lookup"><span data-stu-id="64d44-121">For more information about using the CDC splitter see CDC Components for Microsoft SQL Server Integration Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64d44-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="64d44-122">See Also</span></span>  
 [<span data-ttu-id="64d44-123">Séparateur de capture de données modifiées</span><span class="sxs-lookup"><span data-stu-id="64d44-123">CDC Splitter</span></span>](cdc-splitter.md)  
  
  
