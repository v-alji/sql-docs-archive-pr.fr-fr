---
title: Boîte de dialogue Propriétés du DataSet, champs | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.datasetproperties.fields.f1
- "10140"
ms.assetid: e1367556-736e-4a6b-b9e7-10432a3e50b5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1b9d315f85751c0f73896e809a522613fefece5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601985"
---
# <a name="dataset-properties-dialog-box-fields"></a><span data-ttu-id="5b491-102">Boîte de dialogue Propriétés du dataset, Champs</span><span class="sxs-lookup"><span data-stu-id="5b491-102">Dataset Properties Dialog Box, Fields</span></span>
  <span data-ttu-id="5b491-103">Sélectionnez **Champs** dans la boîte de dialogue **Propriétés du dataset** pour modifier la collection de champs pour le dataset du rapport.</span><span class="sxs-lookup"><span data-stu-id="5b491-103">Select **Fields** on the **Dataset Properties** dialog box to change the field collection for the report dataset.</span></span> <span data-ttu-id="5b491-104">La liste des champs est automatiquement remplie, mais vous pouvez utiliser **Champs** pour ajouter, modifier, et supprimer les champs de requête et les champs calculés.</span><span class="sxs-lookup"><span data-stu-id="5b491-104">The fields list is automatically populated, but you can use **Fields** to add, edit, and delete query and calculated fields.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5b491-105">Options</span><span class="sxs-lookup"><span data-stu-id="5b491-105">Options</span></span>  
 <span data-ttu-id="5b491-106">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="5b491-106">**Add**</span></span>  
 <span data-ttu-id="5b491-107">Ajoutez un nouveau champ de requête ou un champ calculé au dataset.</span><span class="sxs-lookup"><span data-stu-id="5b491-107">Add a new query field or calculated field to the dataset.</span></span>  
  
 <span data-ttu-id="5b491-108">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="5b491-108">**Delete**</span></span>  
 <span data-ttu-id="5b491-109">Supprimez le champ sélectionné du dataset.</span><span class="sxs-lookup"><span data-stu-id="5b491-109">Delete the selected field from the dataset.</span></span>  
  
 <span data-ttu-id="5b491-110">**Nom du champ**</span><span class="sxs-lookup"><span data-stu-id="5b491-110">**Field Name**</span></span>  
 <span data-ttu-id="5b491-111">Tapez le nom du champ.</span><span class="sxs-lookup"><span data-stu-id="5b491-111">Type a name for the field.</span></span> <span data-ttu-id="5b491-112">Ce champ doit être unique dans le dataset.</span><span class="sxs-lookup"><span data-stu-id="5b491-112">The field must be unique within the dataset.</span></span> <span data-ttu-id="5b491-113">Pour chaque champ existant dans la requête de dataset, le nom est pré-rempli.</span><span class="sxs-lookup"><span data-stu-id="5b491-113">For each existing field in the dataset query, the name is pre-populated.</span></span>  
  
 <span data-ttu-id="5b491-114">**Champ source**</span><span class="sxs-lookup"><span data-stu-id="5b491-114">**Field Source**</span></span>  
 <span data-ttu-id="5b491-115">Entrez une valeur pour le champ.</span><span class="sxs-lookup"><span data-stu-id="5b491-115">Enter a value for the field.</span></span>  
  
 <span data-ttu-id="5b491-116">Pour un champ calculé, la source du champ doit être le nom d'un champ existant récupéré par la requête de dataset ou une expression que vous créez.</span><span class="sxs-lookup"><span data-stu-id="5b491-116">For a calculated field, the field source must be the name of an existing field retrieved by the dataset query, or an expression that you create.</span></span> <span data-ttu-id="5b491-117">Par exemple, pour créer un champ qui représente 10 fois la valeur du champ de requête Sales, utilisez l'expression `=10 * Fields!Sales.Value`.</span><span class="sxs-lookup"><span data-stu-id="5b491-117">For example, to create a field that represents 10 times the value in the query field Sales, use the expression `=10 * Fields!Sales.Value`.</span></span>  
  
 <span data-ttu-id="5b491-118">Pour un champ de requête, la source du champ doit être le nom d'un champ existant récupéré par la requête de dataset.</span><span class="sxs-lookup"><span data-stu-id="5b491-118">For a query field, the field source must be the name of an existing field retrieved by the dataset query.</span></span>  
  
 <span data-ttu-id="5b491-119">**Expression (fx)**</span><span class="sxs-lookup"><span data-stu-id="5b491-119">**Expression (fx)**</span></span>  
 <span data-ttu-id="5b491-120">Ajoutez ou modifiez une expression pour le champ calculé.</span><span class="sxs-lookup"><span data-stu-id="5b491-120">Add or change an expression for the calculated field.</span></span> <span data-ttu-id="5b491-121">Ce bouton apparaît uniquement lorsque vous cliquez sur **Ajouter** et sélectionnez **Champ calculé**.</span><span class="sxs-lookup"><span data-stu-id="5b491-121">This button only appears when you click **Add** and select **Calculated Field**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b491-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5b491-122">See Also</span></span>  
 <span data-ttu-id="5b491-123">[Collection de champs de dataset &#40;Générateur de rapports et SSRS&#41;](report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5b491-123">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5b491-124">[Ajouter des données à un rapport &#40;Générateur de rapports et SSRS&#41;](report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5b491-124">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-data/report-datasets-ssrs.md) </span></span>  
 [<span data-ttu-id="5b491-125">Expressions &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5b491-125">Expressions &#40;Report Builder and SSRS&#41;</span></span>](report-design/expressions-report-builder-and-ssrs.md)  
  
  
