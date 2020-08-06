---
title: Afficher les numéros de page ou d’autres propriétés de rapport (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c7d95245-4709-4d04-acb4-59bf71e60d97
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: efc3d5d5de11af1fcdfefc52ed12d5057ee12668
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605186"
---
# <a name="display-page-numbers-or-other-report-properties-report-builder-and-ssrs"></a><span data-ttu-id="d39c1-102">Afficher les numéros de page ou d'autres propriétés de rapport (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="d39c1-102">Display Page Numbers or Other Report Properties (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d39c1-103">Vous pouvez facilement ajouter des numéros de page, un titre de rapport, un nom de fichier, et d'autres propriétés de rapport aux en-têtes ou pieds de page de votre rapport.</span><span class="sxs-lookup"><span data-stu-id="d39c1-103">It's easy to add page numbers, a report title, file name, and other report properties to the page headers or footers of your report.</span></span> <span data-ttu-id="d39c1-104">Ces propriétés sont stockées en tant que champs dans le dossier Champs prédéfinis du volet Données du rapport.</span><span class="sxs-lookup"><span data-stu-id="d39c1-104">These properties are stored as fields in the Built-in Fields folder in the Report Data pane:</span></span>  
  
-   <span data-ttu-id="d39c1-105">Durée d’exécution</span><span class="sxs-lookup"><span data-stu-id="d39c1-105">Execution time</span></span>  
  
-   <span data-ttu-id="d39c1-106">Nombre de pages</span><span class="sxs-lookup"><span data-stu-id="d39c1-106">Page number</span></span>  
  
-   <span data-ttu-id="d39c1-107">Dossier Rapport</span><span class="sxs-lookup"><span data-stu-id="d39c1-107">Report folder</span></span>  
  
-   <span data-ttu-id="d39c1-108">Nom du rapport</span><span class="sxs-lookup"><span data-stu-id="d39c1-108">Report name</span></span>  
  
-   <span data-ttu-id="d39c1-109">URL du serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="d39c1-109">Report server URL</span></span>  
  
-   <span data-ttu-id="d39c1-110">Nombre total de pages</span><span class="sxs-lookup"><span data-stu-id="d39c1-110">Total pages</span></span>  
  
-   <span data-ttu-id="d39c1-111">ID d'utilisateur</span><span class="sxs-lookup"><span data-stu-id="d39c1-111">User ID</span></span>  
  
-   <span data-ttu-id="d39c1-112">Langage</span><span class="sxs-lookup"><span data-stu-id="d39c1-112">Language</span></span>  
  
 <span data-ttu-id="d39c1-113">Pour un numéro de page, vous pouvez ajouter le mot « Page » avant le numéro.</span><span class="sxs-lookup"><span data-stu-id="d39c1-113">For a page number, you may want to add the word "Page" before the number.</span></span> <span data-ttu-id="d39c1-114">Vous pouvez également indiquer le nombre total de pages.</span><span class="sxs-lookup"><span data-stu-id="d39c1-114">You may also want to show the total number of pages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d39c1-115">Le fait d'ajouter le nombre total de pages au pied de page peut ralentir les performances lors de l'exécution ou de l'affichage de votre rapport.</span><span class="sxs-lookup"><span data-stu-id="d39c1-115">Adding the total number of pages to the footer may slow performance when you run or preview your report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-page-number-or-other-report-properties"></a><span data-ttu-id="d39c1-116">Pour ajouter un numéro de page ou d'autres propriétés de rapport</span><span class="sxs-lookup"><span data-stu-id="d39c1-116">To add a page number or other report properties</span></span>  
  
1.  <span data-ttu-id="d39c1-117">Dans le volet Données du rapport, développez le dossier Champs prédéfinis.</span><span class="sxs-lookup"><span data-stu-id="d39c1-117">In the Report Data pane, expand the Built-in Fields folder.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d39c1-118">Si le volet des données de rapport n’est pas visible, cochez **Données du rapport**sous l’onglet Affichage.</span><span class="sxs-lookup"><span data-stu-id="d39c1-118">If you don't see the Report Data pane, on the View tab, check **Report Data**.</span></span>  
  
2.  <span data-ttu-id="d39c1-119">Faites glisser le champ **Numéro de page** du volet des données de rapport vers l’en-tête ou le pied de page du rapport.</span><span class="sxs-lookup"><span data-stu-id="d39c1-119">Drag the **Page Number** field from the Report Data pane to the report header or footer.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d39c1-120">Le pied de page est ajouté automatiquement au rapport.</span><span class="sxs-lookup"><span data-stu-id="d39c1-120">The page footer is added to the report automatically.</span></span> <span data-ttu-id="d39c1-121">Pour ajouter un en-tête de page, sous l’onglet **Insérer** , cliquez sur **En-tête**, puis sur **Ajouter un en-tête**.</span><span class="sxs-lookup"><span data-stu-id="d39c1-121">To add a page header, on the **Insert** tab, click **Header**, and then click **Add Header**.</span></span>  
    >   
    >  <span data-ttu-id="d39c1-122">Une zone de texte qui contient l'expression simple [&PageNumber] est ajoutée.</span><span class="sxs-lookup"><span data-stu-id="d39c1-122">A text box that contains the simple expression [&PageNumber] is added.</span></span>  
  
### <a name="to-add-the-word-page-before-the-page-number"></a><span data-ttu-id="d39c1-123">Pour ajouter le mot « Page » avant le numéro de page</span><span class="sxs-lookup"><span data-stu-id="d39c1-123">To add the word "Page" before the page number</span></span>  
  
1.  <span data-ttu-id="d39c1-124">Cliquez avec le bouton droit sur la zone de texte qui contient [&PageNumber] et cliquez sur **Expressions**.</span><span class="sxs-lookup"><span data-stu-id="d39c1-124">Right-click the text box that contains [&PageNumber] and click **Expressions**.</span></span>  
  
     <span data-ttu-id="d39c1-125">La zone de texte **Définir l’expression pour : valeur** contient l’expression =Globals!PageNumber.</span><span class="sxs-lookup"><span data-stu-id="d39c1-125">The **Set Expression for: Value** text box contains the expression =Globals!PageNumber.</span></span>  
  
2.  <span data-ttu-id="d39c1-126">Placez le curseur après le signe =, puis tapez `"Page " &`.</span><span class="sxs-lookup"><span data-stu-id="d39c1-126">Place the cursor after the = sign and type `"Page " &`.</span></span>  
  
     <span data-ttu-id="d39c1-127">L'expression est maintenant ="Page "&Globals!PageNumber</span><span class="sxs-lookup"><span data-stu-id="d39c1-127">The expression is now  ="Page "&Globals!PageNumber</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-add-total-number-of-pages-after-the-page-number"></a><span data-ttu-id="d39c1-128">Pour ajouter le nombre total de pages après le numéro de page</span><span class="sxs-lookup"><span data-stu-id="d39c1-128">To add total number of pages after the page number</span></span>  
  
1.  <span data-ttu-id="d39c1-129">Cliquez avec le bouton droit sur la zone de texte comportant l’expression et cliquez sur **Expressions**.</span><span class="sxs-lookup"><span data-stu-id="d39c1-129">Right click the text box with the expression and click **Expressions**.</span></span>  
  
2.  <span data-ttu-id="d39c1-130">Tapez **&" sur "&** à la fin de l’expression.</span><span class="sxs-lookup"><span data-stu-id="d39c1-130">Type **&" of "&** at the end of the expression.</span></span>  
  
3.  <span data-ttu-id="d39c1-131">Dans le volet Catégorie, développez **Champs prédéfinis** et double-cliquez sur **TotalPages**.</span><span class="sxs-lookup"><span data-stu-id="d39c1-131">In the Category pane, expand **Built-in Fields** and double-click **TotalPages**.</span></span>  
  
     <span data-ttu-id="d39c1-132">L'expression est maintenant ="Page "&Globals!PageNumber &" de "&Globals!TotalPages</span><span class="sxs-lookup"><span data-stu-id="d39c1-132">The expression is now ="Page "&Globals!PageNumber &" of "&Globals!TotalPages</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d39c1-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d39c1-133">See Also</span></span>  
 <span data-ttu-id="d39c1-134">[En-têtes et pieds de page &#40;Générateur de rapports et SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d39c1-134">[Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="d39c1-135">Mettre en forme du texte dans une zone de texte &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d39c1-135">Format Text in a Text Box &#40;Report Builder and SSRS&#41;</span></span>](format-text-in-a-text-box-report-builder-and-ssrs.md)  
  
  
