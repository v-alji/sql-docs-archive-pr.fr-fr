---
title: Définir l’analyse rapide | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: dcd1dc09-6eaf-440b-9ce6-fef779ff794f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e6ff2c6ecd536dd5ecc34dceb358ffcf578ff3a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600145"
---
# <a name="set-fast-parse"></a><span data-ttu-id="daaf6-102">Définir l'analyse rapide</span><span class="sxs-lookup"><span data-stu-id="daaf6-102">Set Fast Parse</span></span>
  <span data-ttu-id="daaf6-103">La propriété d'analyse rapide doit être définie pour chaque colonne de la source ou de la transformation utilisant l'analyse rapide.</span><span class="sxs-lookup"><span data-stu-id="daaf6-103">The fast parse property must be set for each column of the source or transformation that uses fast parse.</span></span> <span data-ttu-id="daaf6-104">Pour définir cette propriété, faites appel à l'éditeur avancé de la source de fichier plat et de la transformation de conversion de données.</span><span class="sxs-lookup"><span data-stu-id="daaf6-104">To set the property, use the Advanced editor of the Flat File source and Data Conversion transformation.</span></span>  
  
### <a name="to-set-fast-parse"></a><span data-ttu-id="daaf6-105">Pour définir l'analyse rapide</span><span class="sxs-lookup"><span data-stu-id="daaf6-105">To set fast parse</span></span>  
  
1.  <span data-ttu-id="daaf6-106">Cliquez avec le bouton droit sur la source de fichier plat ou sur la transformation de conversion de données, puis cliquez sur **Afficher l’éditeur avancé**.</span><span class="sxs-lookup"><span data-stu-id="daaf6-106">Right-click the Flat File source or Data Conversion transformation, and then click **Show Advanced Editor**.</span></span>  
  
2.  <span data-ttu-id="daaf6-107">Dans la boîte de dialogue **Éditeur avancé** , cliquez sur l'onglet **Propriétés d'entrée et de sortie** .</span><span class="sxs-lookup"><span data-stu-id="daaf6-107">In the **Advanced Editor** dialog box, click the **Input and Output Properties** tab.</span></span>  
  
3.  <span data-ttu-id="daaf6-108">Dans le volet **Entrées et sorties** , cliquez sur la colonne pour laquelle vous souhaitez activer l'analyse rapide.</span><span class="sxs-lookup"><span data-stu-id="daaf6-108">In the **Inputs and Outputs** pane, click the column for which you want to enable fast parse.</span></span>  
  
4.  <span data-ttu-id="daaf6-109">Dans le Fenêtre Propriétés, développez le nœud **propriétés personnalisées** , puis affectez à la propriété la valeur `FastParse` `True` .</span><span class="sxs-lookup"><span data-stu-id="daaf6-109">In the Properties window, expand the **Custom Properties** node, and then set the `FastParse` property to `True`.</span></span>  
  
5.  <span data-ttu-id="daaf6-110">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="daaf6-110">Click **OK**.</span></span>  
  
  
