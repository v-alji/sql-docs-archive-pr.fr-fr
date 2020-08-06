---
title: Détails des perspectives (onglet perspectives, concepteur de cube) (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.perspectives.perspectivespane.perspectivedetails.f2
ms.assetid: b4d0ff9e-5ee7-470c-abc2-d748ac4c04e7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6fb28b5d4d833ec66e84f17f54237b4866adcdbb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613177"
---
# <a name="perspective-details-perspectives-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="50f4f-102">Détails des perspectives (onglet Perspectives, Concepteur de cube) (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="50f4f-102">Perspective Details (Perspectives Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="50f4f-103">Utilisez le volet des **détails des perspectives** sous l’onglet **Perspectives** accessible dans le Concepteur de cube pour gérer les métadonnées mises à disposition des utilisateurs qui exécutent des requêtes sur la perspective sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="50f4f-103">Use the **Perspective Details** pane on the **Perspectives** tab in Cube Designer to manage the metadata available to users who query the selected perspective.</span></span>  
  
## <a name="options"></a><span data-ttu-id="50f4f-104">Options</span><span class="sxs-lookup"><span data-stu-id="50f4f-104">Options</span></span>  
 <span data-ttu-id="50f4f-105">**Objets de cube**</span><span class="sxs-lookup"><span data-stu-id="50f4f-105">**Cube Objects**</span></span>  
 <span data-ttu-id="50f4f-106">Permet d'afficher la liste hiérarchique des objets et des propriétés contenus dans le cube pouvant être inclus dans la perspective.</span><span class="sxs-lookup"><span data-stu-id="50f4f-106">Displays a hierarchical list of objects and properties contained in the cube that can be included in the perspective.</span></span>  
  
 <span data-ttu-id="50f4f-107">**Type d'objet**</span><span class="sxs-lookup"><span data-stu-id="50f4f-107">**Object Type**</span></span>  
 <span data-ttu-id="50f4f-108">Affiche le type de l'objet ou le nom de la propriété à partir du cube et pouvant être inclus dans la perspective.</span><span class="sxs-lookup"><span data-stu-id="50f4f-108">Displays the object type or property name from the cube that can be included in the perspective.</span></span>  
  
 <span data-ttu-id="50f4f-109">**Nom de perspective**</span><span class="sxs-lookup"><span data-stu-id="50f4f-109">**Perspective Name**</span></span>  
 <span data-ttu-id="50f4f-110">Affiche les valeurs des propriétés et si un objet du cube est inclus ou non dans la perspective représentée par la colonne **Nom de perspective** .</span><span class="sxs-lookup"><span data-stu-id="50f4f-110">Displays the property values and whether a cube object is included in the perspective represented by the **Perspective Name** column.</span></span> <span data-ttu-id="50f4f-111">Une colonne **Nom de perspective** représente chaque perspective du cube.</span><span class="sxs-lookup"><span data-stu-id="50f4f-111">One **Perspective Name** column is listed for each perspective in the cube.</span></span>  
  
 <span data-ttu-id="50f4f-112">Tapez le nom de la perspective dans la cellule correspondant à la propriété **Nom** du cube pour la perspective sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="50f4f-112">Type the name of the perspective in the cell for the **Name** property of the cube for the selected perspective.</span></span>  
  
 <span data-ttu-id="50f4f-113">Sélectionnez la mesure par défaut de la perspective dans la cellule correspondant à la propriété **DefaultMeasure** du cube pour la perspective sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="50f4f-113">Select the default measure of the perspective in the cell for the **DefaultMeasure** property of the cube for the selected perspective.</span></span>  
  
 <span data-ttu-id="50f4f-114">Sélectionnez un objet à inclure à la perspective.</span><span class="sxs-lookup"><span data-stu-id="50f4f-114">Select an object to include it in the perspective.</span></span>  
  
## <a name="context-menu"></a><span data-ttu-id="50f4f-115">Menu contextuel</span><span class="sxs-lookup"><span data-stu-id="50f4f-115">Context Menu</span></span>  
 <span data-ttu-id="50f4f-116">Les options suivantes sont disponibles dans le menu contextuel qui s’affiche quand vous cliquez avec le bouton droit sur une cellule visible dans le volet des **détails des perspectives** :</span><span class="sxs-lookup"><span data-stu-id="50f4f-116">The following options are available in the context menu displayed by right-clicking any cell in a perspective displayed in the **Perspective Details** pane:</span></span>  
  
|<span data-ttu-id="50f4f-117">Option</span><span class="sxs-lookup"><span data-stu-id="50f4f-117">Option</span></span>|<span data-ttu-id="50f4f-118">Description</span><span class="sxs-lookup"><span data-stu-id="50f4f-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="50f4f-119">**Nouvelle perspective**</span><span class="sxs-lookup"><span data-stu-id="50f4f-119">**New Perspective**</span></span>|<span data-ttu-id="50f4f-120">Permet de créer une perspective dans le cube sélectionné.</span><span class="sxs-lookup"><span data-stu-id="50f4f-120">Click to create a new perspective in the selected cube.</span></span>|  
|<span data-ttu-id="50f4f-121">**Supprimer la perspective**</span><span class="sxs-lookup"><span data-stu-id="50f4f-121">**Delete Perspective**</span></span>|<span data-ttu-id="50f4f-122">Cliquez pour afficher la boîte de dialogue **Supprimer les objets** et supprimer la perspective sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="50f4f-122">Click to display the **Delete Objects** dialog box and delete the selected perspective</span></span>|  
  
  
