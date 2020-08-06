---
title: Définir une relation de fait et des propriétés de relation de fait | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- fact dimensions [Analysis Services]
ms.assetid: d8e41724-da77-4ac1-bc42-956b5d91ea5d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 15f67a4bdf699bbc6443fc76ce54bcfb35831827
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698645"
---
# <a name="define-a-fact-relationship-and-fact-relationship-properties"></a><span data-ttu-id="36b2c-102">Définir une relation de fait et des propriétés de relation de fait</span><span class="sxs-lookup"><span data-stu-id="36b2c-102">Define a Fact Relationship and Fact Relationship Properties</span></span>
  <span data-ttu-id="36b2c-103">Quand vous définissez une nouvelle dimension de cube ou un nouveau groupe de mesures, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] tente de détecter si une relation de dimension de fait existe et attribut la valeur `Fact` au paramètre d'utilisation de la dimension.</span><span class="sxs-lookup"><span data-stu-id="36b2c-103">When you define a new cube dimension or a new measure group, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will try to detect if a fact dimension relationship exists and then set the dimension usage setting to `Fact`.</span></span> <span data-ttu-id="36b2c-104">Vous pouvez afficher ou modifier une relation de dimension de fait sur l'onglet **Utilisation de la dimension** du Concepteur de cube.</span><span class="sxs-lookup"><span data-stu-id="36b2c-104">You can view or edit a fact dimension relationship on the **Dimension Usage** tab of Cube Designer.</span></span> <span data-ttu-id="36b2c-105">La relation de fait entre une dimension et un groupe de mesures a les contraintes suivantes :</span><span class="sxs-lookup"><span data-stu-id="36b2c-105">The fact relationship between a dimension and a measure group has the following constraints:</span></span>  
  
-   <span data-ttu-id="36b2c-106">Une dimension de cube ne peut avoir qu'une seule relation de fait avec un groupe de mesures donné.</span><span class="sxs-lookup"><span data-stu-id="36b2c-106">A cube dimension can have only one fact relationship to a particular measure group.</span></span>  
  
-   <span data-ttu-id="36b2c-107">Une dimension de cube peut avoir des relations de fait distinctes avec plusieurs groupes de mesures.</span><span class="sxs-lookup"><span data-stu-id="36b2c-107">A cube dimension can have separate fact relationships to multiple measure groups.</span></span>  
  
-   <span data-ttu-id="36b2c-108">L'attribut de granularité de la relation doit correspondre à l'attribut clé (comme le numéro de transaction) de la dimension.</span><span class="sxs-lookup"><span data-stu-id="36b2c-108">The granularity attribute for the relationship must be the key attribute (such as Transaction Number) for the dimension.</span></span> <span data-ttu-id="36b2c-109">Cela crée une relation de type un-à-un entre les faits et la dimension de la table de faits.</span><span class="sxs-lookup"><span data-stu-id="36b2c-109">This creates a one-to-one relationship between the dimension and facts in the fact table.</span></span>  
  
  
