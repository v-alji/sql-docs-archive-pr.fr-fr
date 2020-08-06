---
title: Boîte de dialogue Sélectionner une colonne clé de table imbriquée (vue structure d’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.structure.addnestedtable.f1
helpviewer_keywords:
- Select a Nested Table Key Column dialog box
ms.assetid: f68b89a7-17df-45f8-ba7f-b458cd9b1ec3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4dc524f6913b7be15e87869355515397a3e0b65c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612522"
---
# <a name="select-a-nested-table-key-column-dialog-box-mining-structure-view"></a><span data-ttu-id="f1e12-102">Boîte de dialogue Sélectionner la colonne clé de table imbriquée (vue Structure d'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="f1e12-102">Select a Nested Table Key Column Dialog Box (Mining Structure View)</span></span>
  <span data-ttu-id="f1e12-103">Utilisez la boîte de dialogue **Sélectionner la colonne de clé de table imbriquée** pour désigner une colonne qui sera la clé de la nouvelle table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="f1e12-103">Use the **Select a Nested Table Key Column** dialog box to designate a column that will act as the key for the new nested table.</span></span> <span data-ttu-id="f1e12-104">Lorsque vous fermez cette boîte de dialogue, une nouvelle table est ajoutée à la structure d'exploration de données qui contient la colonne clé désignée.</span><span class="sxs-lookup"><span data-stu-id="f1e12-104">When you exit the dialog box, a new table is added to the mining structure that contains the designated key column.</span></span> <span data-ttu-id="f1e12-105">Vous pouvez ajouter des colonnes supplémentaires à la table imbriquée en cliquant avec le bouton droit sur la structure et en sélectionnant **Ajouter une colonne**.</span><span class="sxs-lookup"><span data-stu-id="f1e12-105">You can add additional columns to the nested table by right-clicking the structure and selecting **Add a Column**.</span></span> <span data-ttu-id="f1e12-106">Cette boîte de dialogue contient différentes options, selon que vous utilisez un modèle d'exploration de données OLAP ou relationnel.</span><span class="sxs-lookup"><span data-stu-id="f1e12-106">The dialog box contains different options depending on whether you are working with an OLAP mining model or a relational mining model.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f1e12-107">Options</span><span class="sxs-lookup"><span data-stu-id="f1e12-107">Options</span></span>  
 <span data-ttu-id="f1e12-108">**Table source**</span><span class="sxs-lookup"><span data-stu-id="f1e12-108">**Source table**</span></span>  
 <span data-ttu-id="f1e12-109">Table sur laquelle est basé le modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="f1e12-109">The table on which the mining model is based.</span></span>  
  
 <span data-ttu-id="f1e12-110">Cette option est utilisée uniquement pour les modèles d'exploration de données relationnels.</span><span class="sxs-lookup"><span data-stu-id="f1e12-110">This is only used for relational mining models.</span></span>  
  
 <span data-ttu-id="f1e12-111">**Colonne source**</span><span class="sxs-lookup"><span data-stu-id="f1e12-111">**Source column**</span></span>  
 <span data-ttu-id="f1e12-112">Liste de toutes les colonnes disponibles dans la table source que vous pouvez utiliser comme clé de la table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="f1e12-112">A list of all the available columns in the source table that you can use as the key of the nested table.</span></span>  
  
 <span data-ttu-id="f1e12-113">Cette option est utilisée uniquement pour les modèles d'exploration de données relationnels.</span><span class="sxs-lookup"><span data-stu-id="f1e12-113">This is only used for relational mining models.</span></span>  
  
 <span data-ttu-id="f1e12-114">**Afficher les types de colonnes**</span><span class="sxs-lookup"><span data-stu-id="f1e12-114">**Show column types**</span></span>  
 <span data-ttu-id="f1e12-115">Liste des types disponibles de colonnes de données.</span><span class="sxs-lookup"><span data-stu-id="f1e12-115">A list of available column data types.</span></span> <span data-ttu-id="f1e12-116">Sélectionnez ou effacez les types de données pour filtrer la liste des colonnes dans **Colonne source**.</span><span class="sxs-lookup"><span data-stu-id="f1e12-116">Select or clear data types to filter the list of columns in **Source column**.</span></span> <span data-ttu-id="f1e12-117">Seules les colonnes qui correspondent aux types de données cochés sont affichées dans la liste **Colonne source** .</span><span class="sxs-lookup"><span data-stu-id="f1e12-117">Only columns that match the checked data types will be shown in the **Source column** list.</span></span>  
  
 <span data-ttu-id="f1e12-118">Cette option est utilisée uniquement pour les modèles d'exploration de données relationnels.</span><span class="sxs-lookup"><span data-stu-id="f1e12-118">This is only used for relational mining models.</span></span>  
  
 <span data-ttu-id="f1e12-119">**Attributs**</span><span class="sxs-lookup"><span data-stu-id="f1e12-119">**Attributes**</span></span>  
 <span data-ttu-id="f1e12-120">Liste des attributs utilisables comme clé de la table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="f1e12-120">A list of attributes that you can use as the key of the nested table.</span></span>  
  
 <span data-ttu-id="f1e12-121">Cette option est utilisée uniquement pour les modèles d'exploration de données OLAP.</span><span class="sxs-lookup"><span data-stu-id="f1e12-121">This is only used for OLAP mining models.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1e12-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f1e12-122">See Also</span></span>  
 [<span data-ttu-id="f1e12-123">Vue structure d’exploration de données &#40;le concepteur de modèle d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f1e12-123">Mining Structure View &#40;Data Mining Model Designer&#41;</span></span>](mining-structure-view-data-mining-model-designer.md)  
  
  
