---
title: Ajouter du code HTML dans un rapport (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 30bd631a-f774-48e7-a13a-b6c2eb54d9bb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 605c84843d62fb664a8a665a3fc3b024f8f87186
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706215"
---
# <a name="add-html-into-a-report-report-builder-and-ssrs"></a><span data-ttu-id="edc22-102">Ajouter du code HTML à un rapport (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="edc22-102">Add HTML into a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="edc22-103">À l'aide d'un espace réservé, vous pouvez importer des éléments HTML depuis un champ dans votre dataset pour les utiliser dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="edc22-103">Using a placeholder, you can import HTML from a field in your dataset for use in the report.</span></span> <span data-ttu-id="edc22-104">Par défaut, un espace réservé contient du texte brut. Par conséquent vous devrez modifier le type de balisage de l'espace réservé en HTML.</span><span class="sxs-lookup"><span data-stu-id="edc22-104">By default, a placeholder represents plain text, so you will need to change the placeholder mark-up type to HTML.</span></span> <span data-ttu-id="edc22-105">Pour plus d’informations, consultez [Importation de données HTML dans un rapport &#40;Générateur de rapports et SSRS&#41;](importing-html-into-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="edc22-105">For more information, see [Importing HTML into a Report &#40;Report Builder and SSRS&#41;](importing-html-into-a-report-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-html-from-a-field-in-your-dataset-into-a-text-box"></a><span data-ttu-id="edc22-106">Pour ajouter des éléments HTML d'un champ de votre dataset dans une zone de texte</span><span class="sxs-lookup"><span data-stu-id="edc22-106">To add HTML from a field in your dataset into a text box</span></span>  
  
1.  <span data-ttu-id="edc22-107">Sous l’onglet **Insérer** , cliquez sur **Liste**.</span><span class="sxs-lookup"><span data-stu-id="edc22-107">On the **Insert** tab, click **List**.</span></span> <span data-ttu-id="edc22-108">Cliquez sur l'aire de conception, puis faites glisser la souris pour créer une zone de la taille voulue.</span><span class="sxs-lookup"><span data-stu-id="edc22-108">Click the design surface, and then drag to create a box that is the size you want.</span></span>  
  
     <span data-ttu-id="edc22-109">La boîte de dialogue **Propriétés du dataset** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="edc22-109">The **Dataset Properties** dialog box opens.</span></span> <span data-ttu-id="edc22-110">Vous pouvez utiliser un dataset partagé ou un dataset incorporé dans votre rapport.</span><span class="sxs-lookup"><span data-stu-id="edc22-110">You can use a shared dataset or a dataset embedded in your report.</span></span> <span data-ttu-id="edc22-111">Pour plus d’informations, cliquez sur [Boîte de dialogue Propriétés du dataset, Requête &#40;Générateur de rapports&#41;](../report-data/dataset-properties-dialog-box-query-report-builder.md) ou [Boîte de dialogue Propriétés du dataset, Requête](../dataset-properties-dialog-box-query.md).</span><span class="sxs-lookup"><span data-stu-id="edc22-111">For more information, click [Dataset Properties Dialog Box, Query &#40;Report Builder&#41;](../report-data/dataset-properties-dialog-box-query-report-builder.md) or [Dataset Properties Dialog Box, Query](../dataset-properties-dialog-box-query.md).</span></span>  
  
2.  <span data-ttu-id="edc22-112">Sous l'onglet **Insérer** , cliquez sur **Zone de texte**.</span><span class="sxs-lookup"><span data-stu-id="edc22-112">On the **Insert** tab, click **Text Box**.</span></span> <span data-ttu-id="edc22-113">Cliquez dans la liste, puis faites glisser la souris pour créer une zone de la taille voulue.</span><span class="sxs-lookup"><span data-stu-id="edc22-113">Click in the list, and then drag to create a box that is the size you want.</span></span>  
  
3.  <span data-ttu-id="edc22-114">Faites glisser un champ HTML de votre dataset dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="edc22-114">Drag an HTML field from your dataset into the text box.</span></span> <span data-ttu-id="edc22-115">Un espace réservé est créé pour votre champ.</span><span class="sxs-lookup"><span data-stu-id="edc22-115">A placeholder is created for your field.</span></span>  
  
4.  <span data-ttu-id="edc22-116">Cliquez avec le bouton droit sur l’espace réservé, puis cliquez sur **Propriétés de l’espace réservé**.</span><span class="sxs-lookup"><span data-stu-id="edc22-116">Right-click the placeholder, and then click **Placeholder Properties**.</span></span>  
  
5.  <span data-ttu-id="edc22-117">Sous l’onglet **Général** , vérifiez que la zone **Valeur** contient une expression qui évalue le champ que vous avez déposé à l’étape 3.</span><span class="sxs-lookup"><span data-stu-id="edc22-117">On the **General** tab, verify that the **Value** box contains an expression that evaluates to the field you dropped in step 3.</span></span>  
  
6.  <span data-ttu-id="edc22-118">Cliquez sur **HTML - Interpréter les balises HTML comme des styles**.</span><span class="sxs-lookup"><span data-stu-id="edc22-118">Click **HTML - Interpret HTML tags as styles**.</span></span> <span data-ttu-id="edc22-119">Cette opération permet d'évaluer le champ en tant que texte HTML.</span><span class="sxs-lookup"><span data-stu-id="edc22-119">This causes the field to be evaluated as HTML.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="edc22-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="edc22-120">See Also</span></span>  
 <span data-ttu-id="edc22-121">[Mise en forme des nombres et des dates &#40;Générateur de rapports et SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="edc22-121">[Formatting Numbers and Dates &#40;Report Builder and SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="edc22-122">[Mise en forme des lignes, des couleurs et des images &#40;Générateur de rapports et SSRS&#41;](images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="edc22-122">[Formatting Lines, Colors, and Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="edc22-123">Boîte de dialogue Propriétés de l’espace réservé, Général &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="edc22-123">Placeholder Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../placeholder-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
