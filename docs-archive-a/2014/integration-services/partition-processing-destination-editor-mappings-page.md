---
title: Éditeur de destination de traitement de partition (page Mappages) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.partprocessingtransformation.mapping.f1
helpviewer_keywords:
- Partition Processing Destination Editor
ms.assetid: e75b766c-85ba-453e-9576-4a1a34f91ecc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3855b15c7ebf1f6fa95c941931869064d552680e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613530"
---
# <a name="partition-processing-destination-editor-mappings-page"></a><span data-ttu-id="ef2ec-102">Éditeur de destination de traitement de partition (page Mappages)</span><span class="sxs-lookup"><span data-stu-id="ef2ec-102">Partition Processing Destination Editor (Mappings Page)</span></span>
  <span data-ttu-id="ef2ec-103">Utilisez la page **Mappages** de la boîte de dialogue **Éditeur de destination de traitement de partition** pour mapper des colonnes d'entrée sur des colonnes de partition.</span><span class="sxs-lookup"><span data-stu-id="ef2ec-103">Use the **Mappings** page of the **Partition Processing Destination Editor** dialog box to map input columns to partition columns.</span></span>  
  
 <span data-ttu-id="ef2ec-104">Pour en savoir plus sur la destination de traitement de partition, consultez [Partition Processing Destination](data-flow/partition-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="ef2ec-104">To learn more abou the Partition Processing destination, see [Partition Processing Destination](data-flow/partition-processing-destination.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ef2ec-105">Les tâches décrites ici ne s’appliquent pas aux modèles tabulaires Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="ef2ec-105">Tasks described here do not apply to Analysis Services tabular models.</span></span>  <span data-ttu-id="ef2ec-106">Vous ne pouvez pas mapper des colonnes d’entrée aux colonnes de partition pour les modèles tabulaires.</span><span class="sxs-lookup"><span data-stu-id="ef2ec-106">You cannot map input columns to partition columns for tabular models.</span></span> <span data-ttu-id="ef2ec-107">Vous pouvez en revanche utiliser la tâche DDL d'exécution [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) d'Analysis Services pour traiter la partition.</span><span class="sxs-lookup"><span data-stu-id="ef2ec-107">You can instead use the Analysis Services Execute DDL task [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) to process the partition.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ef2ec-108">Options</span><span class="sxs-lookup"><span data-stu-id="ef2ec-108">Options</span></span>  
 <span data-ttu-id="ef2ec-109">**Colonnes d'entrée disponibles**</span><span class="sxs-lookup"><span data-stu-id="ef2ec-109">**Available Input Columns**</span></span>  
 <span data-ttu-id="ef2ec-110">Affichez la liste des colonnes d'entrée disponibles.</span><span class="sxs-lookup"><span data-stu-id="ef2ec-110">View the list of available input columns.</span></span> <span data-ttu-id="ef2ec-111">Au moyen du glisser-déplacer, mappez les colonnes d'entrée disponibles dans la table sur des colonnes de destination.</span><span class="sxs-lookup"><span data-stu-id="ef2ec-111">Use a drag-and-drop operation to map available input columns in the table to destination columns.</span></span>  
  
 <span data-ttu-id="ef2ec-112">**Colonnes de destination disponibles**</span><span class="sxs-lookup"><span data-stu-id="ef2ec-112">**Available Destination Columns**</span></span>  
 <span data-ttu-id="ef2ec-113">Affichez la liste des colonnes de destination disponibles.</span><span class="sxs-lookup"><span data-stu-id="ef2ec-113">View the list of available destination columns.</span></span> <span data-ttu-id="ef2ec-114">Utilisez une opération de glisser-déplacer pour mapper les colonnes de destination disponibles dans la table aux colonnes d'entrée.</span><span class="sxs-lookup"><span data-stu-id="ef2ec-114">Use a drag-and-drop operation to map available destination columns in the table to input columns.</span></span>  
  
 <span data-ttu-id="ef2ec-115">**Colonne d'entrée**</span><span class="sxs-lookup"><span data-stu-id="ef2ec-115">**Input Column**</span></span>  
 <span data-ttu-id="ef2ec-116">Affiche les colonnes d'entrée sélectionnées dans le tableau ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="ef2ec-116">View input columns selected from the table above.</span></span> <span data-ttu-id="ef2ec-117">Vous pouvez modifier les mappages au moyen de la liste **Colonnes d'entrée disponibles**.</span><span class="sxs-lookup"><span data-stu-id="ef2ec-117">You can change the mappings by using the list of **Available Input Columns**.</span></span>  
  
 <span data-ttu-id="ef2ec-118">**Colonne de destination**</span><span class="sxs-lookup"><span data-stu-id="ef2ec-118">**Destination Column**</span></span>  
 <span data-ttu-id="ef2ec-119">Affiche chaque colonne de destination disponible, qu'elle soit mappée ou non.</span><span class="sxs-lookup"><span data-stu-id="ef2ec-119">View each available destination column, whether it is mapped or not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef2ec-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ef2ec-120">See Also</span></span>  
 <span data-ttu-id="ef2ec-121">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ef2ec-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="ef2ec-122">[Éditeur de destination de traitement de partition &#40;page Gestionnaire de connexions&#41;](../../2014/integration-services/partition-processing-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="ef2ec-122">[Partition Processing Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/partition-processing-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="ef2ec-123">Éditeur de destination de traitement de partition &#40;page Avancé&#41;</span><span class="sxs-lookup"><span data-stu-id="ef2ec-123">Partition Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../../2014/integration-services/partition-processing-destination-editor-advanced-page.md)  
  
  
