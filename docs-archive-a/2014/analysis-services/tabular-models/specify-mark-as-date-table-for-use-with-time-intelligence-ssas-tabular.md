---
title: Spécifier la marque comme table de dates pour l’utiliser avec Time Intelligence (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 30841d1f-0c3b-4575-8f4a-27a1492e248c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 81038369b8cb8636a2aa216f1c26783a96d5f7ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694720"
---
# <a name="specify-mark-as-date-table-for-use-with-time-intelligence-ssas-tabular"></a><span data-ttu-id="50aee-102">Spécifier la marque comme table de dates pour l'utiliser avec Time Intelligence (SSAS - Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="50aee-102">Specify Mark as Date Table for use with Time Intelligence (SSAS Tabular)</span></span>
  <span data-ttu-id="50aee-103">Pour utiliser des fonctions Time Intelligence dans les formules DAX, vous devez spécifier une table de dates et une colonne (datetime) d'identification unique pour le type de données Date.</span><span class="sxs-lookup"><span data-stu-id="50aee-103">In order to use time intelligence functions in DAX formulas, you must specify a date table and a unique identifier (datetime) column of the Date data type.</span></span> <span data-ttu-id="50aee-104">Une fois qu'une colonne dans la table de dates est spécifiée comme identificateur unique, vous pouvez créer des relations entre les colonnes de cette table et de toutes les tables de faits.</span><span class="sxs-lookup"><span data-stu-id="50aee-104">Once a column in the date table is specified as a unique identifier, you can create relationships between columns in the date table and any fact tables.</span></span>  
  
 <span data-ttu-id="50aee-105">Lorsque vous utilisez les fonctions Time Intelligence, les règles suivantes s'appliquent :</span><span class="sxs-lookup"><span data-stu-id="50aee-105">When using time intelligence functions, the following rules apply:</span></span>  
  
-   <span data-ttu-id="50aee-106">Lorsque vous utilisez les fonctions Time Intelligence DAX, ne spécifiez jamais une colonne datetime à partir d'une table de faits.</span><span class="sxs-lookup"><span data-stu-id="50aee-106">When using DAX time intelligence functions, never specify a datetime column from a fact table.</span></span> <span data-ttu-id="50aee-107">Créez toujours une table de dates distincte dans votre modèle, avec au moins une colonne datetime de type de données Date et avec des valeurs uniques.</span><span class="sxs-lookup"><span data-stu-id="50aee-107">Always create a separate date table in your model with at least one datetime column of Date data type and with unique values.</span></span>  
  
-   <span data-ttu-id="50aee-108">Vérifiez que votre table de dates a une plage de dates continue.</span><span class="sxs-lookup"><span data-stu-id="50aee-108">Make sure your date table has a continuous date range.</span></span>  
  
-   <span data-ttu-id="50aee-109">La colonne datetime dans la table de dates doit avoir une granularité de jour (sans fractions d'un jour).</span><span class="sxs-lookup"><span data-stu-id="50aee-109">The datetime column in the date table should be at day granularity (without fractions of a day).</span></span>  
  
-   <span data-ttu-id="50aee-110">Vous devez spécifier une table de dates et une colonne d'identificateur unique à l'aide de la boîte de dialogue **Marquez la table de dates** .</span><span class="sxs-lookup"><span data-stu-id="50aee-110">You must specify a date table and a unique identifier column by using the **Mark the Date Table** dialog box.</span></span>  
  
-   <span data-ttu-id="50aee-111">Créez des relations entre les tables de faits et les colonnes de type de données Date dans la table de dates.</span><span class="sxs-lookup"><span data-stu-id="50aee-111">Create relationships between fact tables and columns of Date data type in the date table.</span></span>  
  
#### <a name="to-specify-a-date-table-and-unique-identifier"></a><span data-ttu-id="50aee-112">Pour spécifier une table de dates et un identificateur unique</span><span class="sxs-lookup"><span data-stu-id="50aee-112">To specify a date table and unique identifier</span></span>  
  
1.  <span data-ttu-id="50aee-113">Dans le concepteur de modèles, cliquez sur la table de dates.</span><span class="sxs-lookup"><span data-stu-id="50aee-113">In the model designer, click the date table.</span></span>  
  
2.  <span data-ttu-id="50aee-114">Cliquez sur le menu **Table** , cliquez sur **Date**, puis cliquez sur **Marquer en tant que table de dates**</span><span class="sxs-lookup"><span data-stu-id="50aee-114">Click the **Table** menu, then click **Date**, and then click **Mark as Date Table**</span></span>  
  
3.  <span data-ttu-id="50aee-115">Dans la boîte de dialogue **Marquer en tant que table de dates** , dans la zone de liste **Date** , sélectionnez une colonne à utiliser comme identificateur unique.</span><span class="sxs-lookup"><span data-stu-id="50aee-115">In the **Mark as Date Table** dialog box, in the **Date** listbox, select a column to be used as a unique identifier.</span></span> <span data-ttu-id="50aee-116">Cette colonne doit contenir des valeurs uniques et doit avoir le type de données Date.</span><span class="sxs-lookup"><span data-stu-id="50aee-116">This column must contain unique values and should be of Date data type.</span></span> <span data-ttu-id="50aee-117">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="50aee-117">For example:</span></span>  
  
    |<span data-ttu-id="50aee-118">Date</span><span class="sxs-lookup"><span data-stu-id="50aee-118">Date</span></span>|  
    |----------|  
    |<span data-ttu-id="50aee-119">7/1/2010 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="50aee-119">7/1/2010 12:00:00 AM</span></span>|  
    |<span data-ttu-id="50aee-120">7/2/2010 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="50aee-120">7/2/2010 12:00:00 AM</span></span>|  
    |<span data-ttu-id="50aee-121">7/3/2010 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="50aee-121">7/3/2010 12:00:00 AM</span></span>|  
    |<span data-ttu-id="50aee-122">7/4/2010 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="50aee-122">7/4/2010 12:00:00 AM</span></span>|  
    |<span data-ttu-id="50aee-123">7/5/2010 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="50aee-123">7/5/2010 12:00:00 AM</span></span>|  
  
4.  <span data-ttu-id="50aee-124">Si nécessaire, créez les relations entre les tables de faits et la table de dates.</span><span class="sxs-lookup"><span data-stu-id="50aee-124">If necessary, create any relationships between fact tables and the date table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50aee-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="50aee-125">See Also</span></span>  
 <span data-ttu-id="50aee-126">[Calculs &#40;&#41;tabulaire SSAS](calculations-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="50aee-126">[Calculations &#40;SSAS Tabular&#41;](calculations-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="50aee-127">Fonctions Time Intelligence &#40;&#41;DAX</span><span class="sxs-lookup"><span data-stu-id="50aee-127">Time Intelligence Functions &#40;DAX&#41;</span></span>](/dax/time-intelligence-functions-dax)  
  
  
