---
title: Définir l’intelligence comptable (Assistant Dimension) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.accountintelligencetypemapping.f1
ms.assetid: cbcff072-3a7e-4e98-858f-1b4265461561
author: minewiskan
ms.author: owend
ms.openlocfilehash: 90871e2299d1531db1b678b1f4b16ddd7f1db767
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612007"
---
# <a name="define-account-intelligence-dimension-wizard"></a><span data-ttu-id="45cca-102">Définir l'intelligence comptable (Assistant Dimension)</span><span class="sxs-lookup"><span data-stu-id="45cca-102">Define Account Intelligence (Dimension Wizard)</span></span>
  <span data-ttu-id="45cca-103">Utilisez la page **Définir l'intelligence comptable** pour faire correspondre les types de comptes définis dans l'instance [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] avec ceux définis dans l'attribut de dimension associé à l'attribut **Type de compte** de la dimension.</span><span class="sxs-lookup"><span data-stu-id="45cca-103">Use the **Define Account Intelligence** page to map account types defined on the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance to account types defined in the dimension attribute associated with the **Account Type** attribute type in the dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45cca-104"> Cette page s'affiche uniquement si vous avez sélectionné **Dimension standard** dans la page **Sélectionner le type de la dimension** et si vous avez mappé un attribut de dimension au type d'attribut **Type de compte** dans la page **Spécifier le type de la dimension** .</span><span class="sxs-lookup"><span data-stu-id="45cca-104">This page is displayed only if you selected **Standard dimension** on the **Select the Dimension Type** page and if you mapped a dimension attribute to the **Account Type** attribute type on the **Specify Dimension Type** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="45cca-105">Options</span><span class="sxs-lookup"><span data-stu-id="45cca-105">Options</span></span>  
 <span data-ttu-id="45cca-106">**Types de comptes de la table source**</span><span class="sxs-lookup"><span data-stu-id="45cca-106">**Source Table Account Types**</span></span>  
 <span data-ttu-id="45cca-107">Affiche les valeurs contenues dans l’attribut de dimension affecté au type d’attribut du **Type de compte** dans la page **Spécifier la clé et le type de la dimension** .</span><span class="sxs-lookup"><span data-stu-id="45cca-107">Displays the values contained in the dimension attribute assigned to the **Account Type** attribute type in the **Specify Dimension Key and Type** page.</span></span>  
  
 <span data-ttu-id="45cca-108">**Types de comptes intégrés**</span><span class="sxs-lookup"><span data-stu-id="45cca-108">**Built-In Account Types**</span></span>  
 <span data-ttu-id="45cca-109">Sélectionnez le type de compte défini dans l'instance [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] qui correspond aux types de comptes de la table source.</span><span class="sxs-lookup"><span data-stu-id="45cca-109">Select the account type defined on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that maps to the account types in the source table.</span></span>  
  
 <span data-ttu-id="45cca-110">Le tableau ci-dessous répertorie les types de comptes définis dans une instance [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="45cca-110">The following table lists the account types that are defined on an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span>  
  
|<span data-ttu-id="45cca-111">Valeur</span><span class="sxs-lookup"><span data-stu-id="45cca-111">Value</span></span>|<span data-ttu-id="45cca-112">Description</span><span class="sxs-lookup"><span data-stu-id="45cca-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="45cca-113">**Asset**</span><span class="sxs-lookup"><span data-stu-id="45cca-113">**Asset**</span></span>|<span data-ttu-id="45cca-114">Valeur des biens possédés à un moment donné.</span><span class="sxs-lookup"><span data-stu-id="45cca-114">Value of things owned at a specific time.</span></span>|  
|<span data-ttu-id="45cca-115">**Balance**</span><span class="sxs-lookup"><span data-stu-id="45cca-115">**Balance**</span></span>|<span data-ttu-id="45cca-116">Comptage d'une grandeur à un moment donné.</span><span class="sxs-lookup"><span data-stu-id="45cca-116">Count of something at a specific time.</span></span>|  
|<span data-ttu-id="45cca-117">**Dépenses**</span><span class="sxs-lookup"><span data-stu-id="45cca-117">**Expense**</span></span>|<span data-ttu-id="45cca-118">Valeur des dépenses engagées.</span><span class="sxs-lookup"><span data-stu-id="45cca-118">Value of things spent.</span></span>|  
|<span data-ttu-id="45cca-119">**Flux**</span><span class="sxs-lookup"><span data-stu-id="45cca-119">**Flow**</span></span>|<span data-ttu-id="45cca-120">Comptage incrémental de biens.</span><span class="sxs-lookup"><span data-stu-id="45cca-120">Incremental count of things.</span></span>|  
|<span data-ttu-id="45cca-121">**Revenu**</span><span class="sxs-lookup"><span data-stu-id="45cca-121">**Income**</span></span>|<span data-ttu-id="45cca-122">Valeur des biens reçus.</span><span class="sxs-lookup"><span data-stu-id="45cca-122">Value of things received.</span></span>|  
|<span data-ttu-id="45cca-123">**Dettes**</span><span class="sxs-lookup"><span data-stu-id="45cca-123">**Liability**</span></span>|<span data-ttu-id="45cca-124">Valeur des biens dus à un moment donné.</span><span class="sxs-lookup"><span data-stu-id="45cca-124">Value of things owed at a specific time.</span></span>|  
|<span data-ttu-id="45cca-125">**Statistique**</span><span class="sxs-lookup"><span data-stu-id="45cca-125">**Statistical**</span></span>|<span data-ttu-id="45cca-126">Rapport calculé d'une grandeur, ou comptage d'une grandeur qu'il n'est pas possible d'agréger.</span><span class="sxs-lookup"><span data-stu-id="45cca-126">Calculated ratio of something, or count of something that does not aggregate.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="45cca-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="45cca-127">See Also</span></span>  
 <span data-ttu-id="45cca-128">[Aide (F1) de l’Assistant Dimension](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="45cca-128">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="45cca-129">[Dimensions &#40;Analysis Services-données multidimensionnelles&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="45cca-129">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="45cca-130">Dimensions dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="45cca-130">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
