---
title: Configurer les attributs de la dimension (Assistant Business Intelligence) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.acctintelligence.selectattributes.f1
ms.assetid: 3d046e63-bcb1-4ab1-9c37-652463fa68c3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1d2e9bc83b7a6d83b6d2808b472d67169266ff07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602494"
---
# <a name="configure-dimension-attributes-business-intelligence-wizard"></a><span data-ttu-id="d76cd-102">Configurer les attributs de la dimension (Assistant Business Intelligence)</span><span class="sxs-lookup"><span data-stu-id="d76cd-102">Configure Dimension Attributes (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="d76cd-103">Utilisez la page **Configurer les attributs de la dimension** pour associer les attributs de dimensions aux types d'attributs qu'utilise [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] pour identifier les attributs des dimensions de compte.</span><span class="sxs-lookup"><span data-stu-id="d76cd-103">Use the **Configure Dimension Attributes** page to map the dimension attributes to the attribute types that [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses to identify attributes for account dimensions.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d76cd-104">Options</span><span class="sxs-lookup"><span data-stu-id="d76cd-104">Options</span></span>  
 <span data-ttu-id="d76cd-105">**Type de dimension**</span><span class="sxs-lookup"><span data-stu-id="d76cd-105">**Dimension type**</span></span>  
 <span data-ttu-id="d76cd-106">Affiche le type de dimension sélectionné.</span><span class="sxs-lookup"><span data-stu-id="d76cd-106">Displays the selected dimension type.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d76cd-107">Cette option n’est pas disponible, car la `Type` propriété de la dimension ne peut pas être remplacée par une valeur autre que *compte* pour les dimensions de compte.</span><span class="sxs-lookup"><span data-stu-id="d76cd-107">This option is not available because the `Type` property of the dimension cannot be changed to a value other than *Account* for account dimensions.</span></span>  
  
 <span data-ttu-id="d76cd-108">**Attributs de dimensions**</span><span class="sxs-lookup"><span data-stu-id="d76cd-108">**Dimension attributes**</span></span>  
 <span data-ttu-id="d76cd-109">Affiche les types d'attributs valides qui peuvent être associés aux attributs de dimension existants dans la dimension.</span><span class="sxs-lookup"><span data-stu-id="d76cd-109">Displays the valid attribute types that can be mapped to existing dimension attributes in the dimension.</span></span>  
  
 <span data-ttu-id="d76cd-110">**Inclusion**</span><span class="sxs-lookup"><span data-stu-id="d76cd-110">**Include**</span></span>  
 <span data-ttu-id="d76cd-111">Activez une case à cocher pour inclure le type d'attribut correspondant dans la dimension.</span><span class="sxs-lookup"><span data-stu-id="d76cd-111">Select a check box to include the corresponding attribute type in the dimension.</span></span>  
  
 <span data-ttu-id="d76cd-112">**Type d’attribut**</span><span class="sxs-lookup"><span data-stu-id="d76cd-112">**Attribute Type**</span></span>  
 <span data-ttu-id="d76cd-113">Affiche les types d'attributs qui peuvent être associés aux attributs de dimension existants dans la dimension.</span><span class="sxs-lookup"><span data-stu-id="d76cd-113">Lists the attribute types that can be mapped to existing dimension attributes in the dimension.</span></span>  
  
 <span data-ttu-id="d76cd-114">**Attribut de dimension**</span><span class="sxs-lookup"><span data-stu-id="d76cd-114">**Dimension Attribute**</span></span>  
 <span data-ttu-id="d76cd-115">Sélectionnez l'attribut de dimension qui doit être associé au type d'attribut correspondant.</span><span class="sxs-lookup"><span data-stu-id="d76cd-115">Select the dimension attribute that should be mapped to the corresponding attribute type.</span></span>  
  
 <span data-ttu-id="d76cd-116">**Définissez les mesures semi-additives en fonction du type de compte**</span><span class="sxs-lookup"><span data-stu-id="d76cd-116">**Set measures to be semiadditive based on account type**</span></span>  
 <span data-ttu-id="d76cd-117">Sélectionnez cette option pour changer chaque mesure associée à cette dimension à agréger par type de compte.</span><span class="sxs-lookup"><span data-stu-id="d76cd-117">Select to change every measure associated with this dimension to be aggregated by account type.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d76cd-118">Cette option ne s'affiche pas si l'Assistant Business Intelligence a été démarré à partir du Concepteur de dimensions ou en cliquant avec le bouton droit sur une dimension dans l'Explorateur de solutions dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d76cd-118">This option does not appear if the Business Intelligence Wizard was started from Dimension Designer or by right-clicking a dimension in Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d76cd-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d76cd-119">See Also</span></span>  
 <span data-ttu-id="d76cd-120">[Aide (F1) de l’Assistant Business Intelligence](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="d76cd-120">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="d76cd-121">[Concepteur de cube &#40;Analysis Services-données multidimensionnelles&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="d76cd-121">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="d76cd-122">Concepteur de dimensions &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="d76cd-122">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
