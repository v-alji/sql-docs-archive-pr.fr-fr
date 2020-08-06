---
title: Définir l’intelligence comptable (Assistant Business Intelligence) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.acctintelligence.mapaccounttype.f1
ms.assetid: fe4c204b-1031-4ac4-9916-8052ce2301cc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 17b8136e79097cd502d6b239ba6867c4e678c70f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696320"
---
# <a name="define-account-intelligence-business-intelligence-wizard"></a><span data-ttu-id="1e052-102">Définir l'intelligence comptable (Assistant Business Intelligence)</span><span class="sxs-lookup"><span data-stu-id="1e052-102">Define Account Intelligence (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="1e052-103">Utilisez la page **Définir l'intelligence comptable** pour faire correspondre les types de comptes définis dans l'instance [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] avec ceux définis par une table source de la source de données qui fournit les données de dimension du compte.</span><span class="sxs-lookup"><span data-stu-id="1e052-103">Use the **Define Account Intelligence** page to map account types defined on the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance to account types defined by a source table in the data source that supplies the data for the account dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1e052-104">Cette page s’affiche si un attribut de dimension a été mis en correspondance avec le type d’attribut **Type de compte** dans la page **Configurer les attributs de la dimension** .</span><span class="sxs-lookup"><span data-stu-id="1e052-104">This page will appear if a dimension attribute was mapped to the **Account Type** attribute type on the **Configure Dimension Attributes** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1e052-105">Options</span><span class="sxs-lookup"><span data-stu-id="1e052-105">Options</span></span>  
 <span data-ttu-id="1e052-106">**Types de comptes de la table source**</span><span class="sxs-lookup"><span data-stu-id="1e052-106">**Source Table Account Types**</span></span>  
 <span data-ttu-id="1e052-107">Affiche les valeurs contenues dans l’attribut de dimension affecté au type d’attribut **Type de compte** défini dans la page **Configurer les attributs de la dimension** .</span><span class="sxs-lookup"><span data-stu-id="1e052-107">Displays the values that are contained in the dimension attribute assigned to the **Account Type** attribute type on the **Configure Dimension Attributes** page.</span></span>  
  
 <span data-ttu-id="1e052-108">**Types de comptes intégrés**</span><span class="sxs-lookup"><span data-stu-id="1e052-108">**Built-In Account Types**</span></span>  
 <span data-ttu-id="1e052-109">Sélectionnez le type de compte défini dans l'instance [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] qui correspond aux types de comptes de la table source.</span><span class="sxs-lookup"><span data-stu-id="1e052-109">Select the account type defined on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that maps to the account types in the source table.</span></span>  
  
 <span data-ttu-id="1e052-110">Le tableau ci-dessous répertorie les types de comptes définis dans une instance [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1e052-110">The following table lists the account types that are defined on an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span>  
  
|<span data-ttu-id="1e052-111">Valeur</span><span class="sxs-lookup"><span data-stu-id="1e052-111">Value</span></span>|<span data-ttu-id="1e052-112">Description</span><span class="sxs-lookup"><span data-stu-id="1e052-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1e052-113">**Asset**</span><span class="sxs-lookup"><span data-stu-id="1e052-113">**Asset**</span></span>|<span data-ttu-id="1e052-114">Valeur des biens possédés à un moment donné.</span><span class="sxs-lookup"><span data-stu-id="1e052-114">Value of things owned at a specific time.</span></span>|  
|<span data-ttu-id="1e052-115">**Balance**</span><span class="sxs-lookup"><span data-stu-id="1e052-115">**Balance**</span></span>|<span data-ttu-id="1e052-116">Comptage d'une grandeur à un moment donné.</span><span class="sxs-lookup"><span data-stu-id="1e052-116">Count of something at a specific time.</span></span>|  
|<span data-ttu-id="1e052-117">**Dépenses**</span><span class="sxs-lookup"><span data-stu-id="1e052-117">**Expense**</span></span>|<span data-ttu-id="1e052-118">Valeur des dépenses engagées.</span><span class="sxs-lookup"><span data-stu-id="1e052-118">Value of things spent.</span></span>|  
|<span data-ttu-id="1e052-119">**Flux**</span><span class="sxs-lookup"><span data-stu-id="1e052-119">**Flow**</span></span>|<span data-ttu-id="1e052-120">Comptage incrémental de biens.</span><span class="sxs-lookup"><span data-stu-id="1e052-120">Incremental count of things.</span></span>|  
|<span data-ttu-id="1e052-121">**Revenu**</span><span class="sxs-lookup"><span data-stu-id="1e052-121">**Income**</span></span>|<span data-ttu-id="1e052-122">Valeur des biens reçus.</span><span class="sxs-lookup"><span data-stu-id="1e052-122">Value of things received.</span></span>|  
|<span data-ttu-id="1e052-123">**Dettes**</span><span class="sxs-lookup"><span data-stu-id="1e052-123">**Liability**</span></span>|<span data-ttu-id="1e052-124">Valeur des biens dus à un moment donné.</span><span class="sxs-lookup"><span data-stu-id="1e052-124">Value of things owed at a specific time.</span></span>|  
|<span data-ttu-id="1e052-125">**Statistique**</span><span class="sxs-lookup"><span data-stu-id="1e052-125">**Statistical**</span></span>|<span data-ttu-id="1e052-126">Rapport calculé d'une grandeur, ou comptage d'une grandeur qu'il n'est pas possible d'agréger.</span><span class="sxs-lookup"><span data-stu-id="1e052-126">Calculated ratio of something, or count of something that does not aggregate.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1e052-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1e052-127">See Also</span></span>  
 <span data-ttu-id="1e052-128">[Aide (F1) de l’Assistant Business Intelligence](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="1e052-128">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="1e052-129">[Concepteur de cube &#40;Analysis Services-données multidimensionnelles&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="1e052-129">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="1e052-130">Concepteur de dimensions &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="1e052-130">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
