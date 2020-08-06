---
title: Options des attributs d’historique (Assistant Dimension à variation lente) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.histattriboption.f1
ms.assetid: a176ec66-ec39-4c99-99d1-c1afa8450e1e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fad005d6b8f80973abeb47dd881ef02b669d7b27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613063"
---
# <a name="historical-attribute-options-slowly-changing-dimension-wizard"></a><span data-ttu-id="6c2ca-102">Options des attributs d'historique (Assistant Dimension à variation lente)</span><span class="sxs-lookup"><span data-stu-id="6c2ca-102">Historical Attribute Options (Slowly Changing Dimension Wizard)</span></span>
  <span data-ttu-id="6c2ca-103">Utilisez la boîte de dialogue **Options des attributs d'historique** pour afficher les attributs d'historique par dates de début et de fin ou pour enregistrer les attributs d'historique dans une colonne créée spécialement à cet effet.</span><span class="sxs-lookup"><span data-stu-id="6c2ca-103">Use the **Historical Attributes Options** dialog box to show historical attributes by start and end dates, or to record historical attributes in a column specially created for this purpose.</span></span>  
  
 <span data-ttu-id="6c2ca-104">Pour en savoir plus sur cet Assistant, consultez [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="6c2ca-104">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="6c2ca-105">Options</span><span class="sxs-lookup"><span data-stu-id="6c2ca-105">Options</span></span>  
 <span data-ttu-id="6c2ca-106">**Utiliser une seule colonne pour afficher les enregistrements actifs et expirés**</span><span class="sxs-lookup"><span data-stu-id="6c2ca-106">**Use a single column to show current and expired records**</span></span>  
 <span data-ttu-id="6c2ca-107">Si vous choisissez d'utiliser une seule colonne pour enregistrer l'état des attributs d'historique, les options suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="6c2ca-107">If you choose to use a single column to record the status of historical attributes, the following options are available:</span></span>  
  
|<span data-ttu-id="6c2ca-108">Option</span><span class="sxs-lookup"><span data-stu-id="6c2ca-108">Option</span></span>|<span data-ttu-id="6c2ca-109">Description</span><span class="sxs-lookup"><span data-stu-id="6c2ca-109">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="6c2ca-110">**Colonne d'indicateur d'enregistrement actif**</span><span class="sxs-lookup"><span data-stu-id="6c2ca-110">**Column to indicate current record**</span></span>|<span data-ttu-id="6c2ca-111">Sélectionnez une colonne dans laquelle indiquer l'enregistrement actif.</span><span class="sxs-lookup"><span data-stu-id="6c2ca-111">Select a column in which to indicate the current record.</span></span>|  
|<span data-ttu-id="6c2ca-112">**Valeur si actif**</span><span class="sxs-lookup"><span data-stu-id="6c2ca-112">**Value when current**</span></span>|<span data-ttu-id="6c2ca-113">Utilisez soit **True** soit **Current** pour indiquer que l'enregistrement est actif.</span><span class="sxs-lookup"><span data-stu-id="6c2ca-113">Use either **True** or **Current** to show whether the record is current.</span></span>|  
|<span data-ttu-id="6c2ca-114">**Valeur d'expiration**</span><span class="sxs-lookup"><span data-stu-id="6c2ca-114">**Expiration value**</span></span>|<span data-ttu-id="6c2ca-115">Utilisez soit **False** soit **Expired** pour indiquer que l'enregistrement est une valeur historique.</span><span class="sxs-lookup"><span data-stu-id="6c2ca-115">Use either **False** or **Expired** to show whether the record is a historical value.</span></span>|  
  
 <span data-ttu-id="6c2ca-116">**Utiliser les dates de début et de fin pour identifier les enregistrements actifs et expirés**</span><span class="sxs-lookup"><span data-stu-id="6c2ca-116">**Use start and end dates to identify current and expired records**</span></span>  
 <span data-ttu-id="6c2ca-117">La table de dimension pour cette option doit comprendre une colonne de date.</span><span class="sxs-lookup"><span data-stu-id="6c2ca-117">The dimension table for this option must include a date column.</span></span> <span data-ttu-id="6c2ca-118">Si vous choisissez d'afficher les attributs d'historique par dates de début et de fin, les options suivantes sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="6c2ca-118">If you choose to show historical attributes by start and end dates, the following options are available:</span></span>  
  
|<span data-ttu-id="6c2ca-119">Option</span><span class="sxs-lookup"><span data-stu-id="6c2ca-119">Option</span></span>|<span data-ttu-id="6c2ca-120">Description</span><span class="sxs-lookup"><span data-stu-id="6c2ca-120">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="6c2ca-121">**Colonne de date de début**</span><span class="sxs-lookup"><span data-stu-id="6c2ca-121">**Start date column**</span></span>|<span data-ttu-id="6c2ca-122">Sélectionnez la colonne de la table de dimension qui doit contenir la date de début.</span><span class="sxs-lookup"><span data-stu-id="6c2ca-122">Select the column in the dimension table to contain the start date.</span></span>|  
|<span data-ttu-id="6c2ca-123">**Colonne de date de fin**</span><span class="sxs-lookup"><span data-stu-id="6c2ca-123">**End date column**</span></span>|<span data-ttu-id="6c2ca-124">Sélectionnez la colonne de la table de dimension qui doit contenir la date de fin.</span><span class="sxs-lookup"><span data-stu-id="6c2ca-124">Select the column in the dimension table to contain the end date.</span></span>|  
|<span data-ttu-id="6c2ca-125">**Variable de définition des valeurs de date**</span><span class="sxs-lookup"><span data-stu-id="6c2ca-125">**Variable to set date values**</span></span>|<span data-ttu-id="6c2ca-126">Sélectionnez une variable de date dans la liste.</span><span class="sxs-lookup"><span data-stu-id="6c2ca-126">Select a date variable from the list.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6c2ca-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6c2ca-127">See Also</span></span>  
 [<span data-ttu-id="6c2ca-128">Configurer les sorties à l'aide de l'Assistant Dimension à variation lente</span><span class="sxs-lookup"><span data-stu-id="6c2ca-128">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
