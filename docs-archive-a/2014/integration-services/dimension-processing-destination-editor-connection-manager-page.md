---
title: Éditeur de destination de traitement de dimension (page Gestionnaire de connexions) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dimprocessingtransformation.connection.f1
helpviewer_keywords:
- Dimension Processing Destination Editor
ms.assetid: 44aab631-d62d-4895-8fc7-7f1f3b1b68ce
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 50ba42292c1f48c9b1cdf2ba00c709dacd2f9675
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614185"
---
# <a name="dimension-processing-destination-editor-connection-manager-page"></a><span data-ttu-id="0b497-102">Éditeur de destination de traitement de dimension (page Gestionnaire de connexions)</span><span class="sxs-lookup"><span data-stu-id="0b497-102">Dimension Processing Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="0b497-103">La page **Gestionnaire de connexions** de la boîte de dialogue **Éditeur de destination de traitement de dimension** vous permet de spécifier une connexion à un projet [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ou à une instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b497-103">Use the **Connection Manager** page of the **Dimension Processing Destination Editor** dialog box to specify a connection to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project or to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0b497-104">Pour en savoir plus sur la destination de traitement de dimension, consultez [Dimension Processing Destination](data-flow/dimension-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="0b497-104">To learn more about the Dimension Processing destination, see [Dimension Processing Destination](data-flow/dimension-processing-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="0b497-105">Options</span><span class="sxs-lookup"><span data-stu-id="0b497-105">Options</span></span>  
 <span data-ttu-id="0b497-106">**Connection manager**</span><span class="sxs-lookup"><span data-stu-id="0b497-106">**Connection manager**</span></span>  
 <span data-ttu-id="0b497-107">Sélectionnez un gestionnaire de connexions existant dans la liste ou cliquez sur **Nouveau** pour créer un gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="0b497-107">Select an existing connection manager from the list, or click **New** to create a new connection manager.</span></span>  
  
 <span data-ttu-id="0b497-108">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="0b497-108">**New**</span></span>  
 <span data-ttu-id="0b497-109">Créez une connexion à l’aide de la boîte de dialogue **Ajout d’un gestionnaire de connexions Analysis Services** .</span><span class="sxs-lookup"><span data-stu-id="0b497-109">Create a new connection by using the **Add Analysis Services Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="0b497-110">**Liste des dimensions disponibles**</span><span class="sxs-lookup"><span data-stu-id="0b497-110">**List of available dimensions**</span></span>  
 <span data-ttu-id="0b497-111">Sélectionnez la dimension à traiter.</span><span class="sxs-lookup"><span data-stu-id="0b497-111">Select the dimension to process.</span></span>  
  
 <span data-ttu-id="0b497-112">**Méthode de traitement**</span><span class="sxs-lookup"><span data-stu-id="0b497-112">**Processing method**</span></span>  
 <span data-ttu-id="0b497-113">Sélectionnez la méthode de traitement à appliquer à la dimension sélectionnée dans la liste.</span><span class="sxs-lookup"><span data-stu-id="0b497-113">Select the processing method to apply to the dimension selected in the list.</span></span> <span data-ttu-id="0b497-114">La valeur par défaut de cette option est **Complète**.</span><span class="sxs-lookup"><span data-stu-id="0b497-114">The default value of this option is **Full**.</span></span>  
  
|<span data-ttu-id="0b497-115">Valeur</span><span class="sxs-lookup"><span data-stu-id="0b497-115">Value</span></span>|<span data-ttu-id="0b497-116">Description</span><span class="sxs-lookup"><span data-stu-id="0b497-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0b497-117">**Ajouter (incrémentiel)**</span><span class="sxs-lookup"><span data-stu-id="0b497-117">**Add (incremental)**</span></span>|<span data-ttu-id="0b497-118">Permet d'effectuer un traitement incrémentiel de la dimension.</span><span class="sxs-lookup"><span data-stu-id="0b497-118">Perform an incremental processing of the dimension.</span></span>|  
|<span data-ttu-id="0b497-119">**Complète**</span><span class="sxs-lookup"><span data-stu-id="0b497-119">**Full**</span></span>|<span data-ttu-id="0b497-120">Permet d'effectuer un traitement complet de la dimension.</span><span class="sxs-lookup"><span data-stu-id="0b497-120">Perform full processing of the dimension.</span></span>|  
|<span data-ttu-id="0b497-121">**Mettre à jour**</span><span class="sxs-lookup"><span data-stu-id="0b497-121">**Update**</span></span>|<span data-ttu-id="0b497-122">Permet d'effectuer un traitement de mise à jour de la dimension.</span><span class="sxs-lookup"><span data-stu-id="0b497-122">Perform an update processing of the dimension.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0b497-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0b497-123">See Also</span></span>  
 <span data-ttu-id="0b497-124">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="0b497-124">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="0b497-125">[Éditeur de destination de traitement de dimension &#40;page Mappages&#41;](../../2014/integration-services/dimension-processing-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="0b497-125">[Dimension Processing Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/dimension-processing-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="0b497-126">Éditeur de destination de traitement de dimension &#40;page Avancé&#41;</span><span class="sxs-lookup"><span data-stu-id="0b497-126">Dimension Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../../2014/integration-services/dimension-processing-destination-editor-advanced-page.md)  
  
  
