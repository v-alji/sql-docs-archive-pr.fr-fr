---
title: Ajouter un sous-rapport et des paramètres (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10093"
- sql12.rtp.rptdesigner.subreportproperties.general.f1
ms.assetid: 94f960f8-a629-4f1e-8277-c3b8f0680d98
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3aeede343763ea5fc8fbdfde179208f98fa1a2ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600540"
---
# <a name="add-a-subreport-and-parameters-report-builder-and-ssrs"></a><span data-ttu-id="d8e53-102">Ajouter un sous-rapport et des paramètres (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="d8e53-102">Add a Subreport and Parameters (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d8e53-103">Ajoutez des sous-rapports à un rapport pour créer un rapport principal servant de conteneur à plusieurs rapports connexes.</span><span class="sxs-lookup"><span data-stu-id="d8e53-103">Add subreports to a report when you want to create a main report that is a container for multiple related reports.</span></span> <span data-ttu-id="d8e53-104">Un sous-rapport est une référence à un autre rapport.</span><span class="sxs-lookup"><span data-stu-id="d8e53-104">A subreport is a reference to another report.</span></span> <span data-ttu-id="d8e53-105">Pour connecter les rapports par des valeurs de données (par exemple, pour que plusieurs rapports indiquent des données pour le même client), vous devez désigner un rapport paramétrable (par exemple, un rapport qui affiche les renseignements concernant un client spécifique) en tant que sous-rapport.</span><span class="sxs-lookup"><span data-stu-id="d8e53-105">To relate the reports through data values (for example, to have multiple reports show data for the same customer), you must design a parameterized report (for example, a report that shows the details for a specific customer) as the subreport.</span></span> <span data-ttu-id="d8e53-106">Lorsque vous ajoutez un sous-rapport au rapport principal, vous pouvez spécifier des paramètres à passer au sous-rapport.</span><span class="sxs-lookup"><span data-stu-id="d8e53-106">When you add a subreport to the main report, you can specify parameters to pass to the subreport.</span></span>  
  
 <span data-ttu-id="d8e53-107">Vous pouvez aussi ajouter des sous-rapports aux lignes ou colonnes dynamiques d'une table ou d'une matrice.</span><span class="sxs-lookup"><span data-stu-id="d8e53-107">You can also add subreports to dynamic rows or columns in a table or matrix.</span></span> <span data-ttu-id="d8e53-108">Lorsque le rapport principal est traité, le sous-rapport est traité pour chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="d8e53-108">When the main report is processed, the subreport is processed for each row.</span></span> <span data-ttu-id="d8e53-109">Dans ce cas, demandez-vous si vous pouvez obtenir le résultat escompté en utilisant des régions de données classiques ou imbriquées.</span><span class="sxs-lookup"><span data-stu-id="d8e53-109">In this case, consider whether you can achieve the desired effect by using data regions or nested data regions.</span></span>  
  
 <span data-ttu-id="d8e53-110">Pour ajouter un sous-rapport à un rapport, vous devez d'abord créer le rapport qui sert de sous-rapport.</span><span class="sxs-lookup"><span data-stu-id="d8e53-110">To add a subreport to a report, you must first create the report that will act as the subreport.</span></span> <span data-ttu-id="d8e53-111">Pour plus d’informations sur la création du sous-rapport, consultez [Sous-rapports &#40;Générateur de rapports et SSRS&#41;](subreports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d8e53-111">For more information on creating the subreport, see [Subreports &#40;Report Builder and SSRS&#41;](subreports-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-subreport"></a><span data-ttu-id="d8e53-112">Pour ajouter un sous-rapport</span><span class="sxs-lookup"><span data-stu-id="d8e53-112">To add a subreport</span></span>  
  
1.  <span data-ttu-id="d8e53-113">Sous l’onglet **Insérer** , cliquez sur **Sous-rapport**.</span><span class="sxs-lookup"><span data-stu-id="d8e53-113">On the **Insert** tab, click **Subreport**.</span></span>  
  
2.  <span data-ttu-id="d8e53-114">Sur l'aire de conception, cliquez à un endroit quelconque du rapport et faites glisser la souris pour créer une zone de la taille voulue pour le sous-rapport.</span><span class="sxs-lookup"><span data-stu-id="d8e53-114">On the design surface, click a location on the report and then drag a box to the desired size of the subreport.</span></span> <span data-ttu-id="d8e53-115">Une autre solution consiste à cliquer sur l'aire de conception pour créer un sous-rapport de taille par défaut.</span><span class="sxs-lookup"><span data-stu-id="d8e53-115">Alternatively, click the design surface to create a subreport of default size.</span></span>  
  
3.  <span data-ttu-id="d8e53-116">Cliquez avec le bouton droit sur le sous-rapport, puis cliquez sur **Propriétés du sous-rapport**.</span><span class="sxs-lookup"><span data-stu-id="d8e53-116">Right-click the subreport, and then click **Subreport Properties**.</span></span>  
  
4.  <span data-ttu-id="d8e53-117">Dans la boîte de dialogue **Propriétés du sous-rapport** , tapez un nom dans la zone de texte **Nom** ou acceptez le nom par défaut.</span><span class="sxs-lookup"><span data-stu-id="d8e53-117">In the **Subreport Properties** dialog box, type a name in the **Name** text box or accept the default.</span></span> <span data-ttu-id="d8e53-118">Ce nom doit être unique dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="d8e53-118">The name must be unique within the report.</span></span> <span data-ttu-id="d8e53-119">Par défaut, un nom général, tel que Subreport1 ou Subreport2, est assigné.</span><span class="sxs-lookup"><span data-stu-id="d8e53-119">By default, a general name such as Subreport1 or Subreport2 is assigned.</span></span>  
  
5.  <span data-ttu-id="d8e53-120">Dans la zone **Utiliser ce rapport comme sous-rapport** , cliquez sur **Parcourir**ou tapez le nom du rapport.</span><span class="sxs-lookup"><span data-stu-id="d8e53-120">In the **Use this report as a subreport** box, click **Browse**, or type the name of the report.</span></span> <span data-ttu-id="d8e53-121">Il est préférable de cliquer sur **Parcourir** , car le chemin du sous-rapport est spécifié automatiquement.</span><span class="sxs-lookup"><span data-stu-id="d8e53-121">Clicking **Browse** is preferred because the path to the subreport will be specified automatically.</span></span> <span data-ttu-id="d8e53-122">Vous pouvez spécifier le rapport de plusieurs manières.</span><span class="sxs-lookup"><span data-stu-id="d8e53-122">You can specify the report in the several ways.</span></span> <span data-ttu-id="d8e53-123">Pour plus d’informations, consultez [Spécification de chemins d’accès à des éléments externes &#40;Générateur de rapports et SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d8e53-123">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
6.  <span data-ttu-id="d8e53-124">(Facultatif) Cliquez sur **Oui** pour **Omettre la bordure sur le saut de page** et ainsi empêcher l’affichage d’une bordure au milieu du sous-rapport si ce dernier prend plusieurs pages.</span><span class="sxs-lookup"><span data-stu-id="d8e53-124">(Optional) Click **Yes** for **Omit border on page break** to prevent a border from being rendered in the middle of the subreport if the subreport spans more than one page.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-specify-parameters-to-pass-to-a-subreport"></a><span data-ttu-id="d8e53-125">Pour spécifier les paramètres à passer à un sous-rapport</span><span class="sxs-lookup"><span data-stu-id="d8e53-125">To specify parameters to pass to a subreport</span></span>  
  
1.  <span data-ttu-id="d8e53-126">En mode Conception, cliquez avec le bouton droit sur le sous-rapport, puis cliquez sur **Propriétés du sous-rapport**.</span><span class="sxs-lookup"><span data-stu-id="d8e53-126">In Design view, right-click the subreport and then click **Subreport Properties**.</span></span>  
  
2.  <span data-ttu-id="d8e53-127">Dans la boîte de dialogue **Propriétés du sous-rapport** , cliquez sur **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="d8e53-127">In the **Subreport Properties** dialog box, click **Parameters**.</span></span>  
  
3.  <span data-ttu-id="d8e53-128">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="d8e53-128">Click **Add**.</span></span> <span data-ttu-id="d8e53-129">Une nouvelle ligne est ajoutée à la grille des paramètres.</span><span class="sxs-lookup"><span data-stu-id="d8e53-129">A new row is added to the parameter grid.</span></span>  
  
4.  <span data-ttu-id="d8e53-130">Dans la zone **Nom** , tapez le nom d’un paramètre du sous-rapport ou choisissez-le dans la zone de liste.</span><span class="sxs-lookup"><span data-stu-id="d8e53-130">In the **Name** text box, type the name of a parameter in the subreport or choose it from the list box.</span></span> <span data-ttu-id="d8e53-131">Ce nom doit correspondre au nom d'un paramètre de rapport, pas d'un paramètre de requête, dans le sous-rapport.</span><span class="sxs-lookup"><span data-stu-id="d8e53-131">This name must match a report parameter, not a query parameter, in the subreport.</span></span>  
  
5.  <span data-ttu-id="d8e53-132">Dans la zone de liste **Valeur** , tapez ou sélectionnez une valeur à passer au sous-rapport.</span><span class="sxs-lookup"><span data-stu-id="d8e53-132">In the **Value** list box, type or select a value to pass to the subreport.</span></span> <span data-ttu-id="d8e53-133">Cette valeur peut être du texte statique ou une expression qui fait référence à un champ ou un autre objet situé dans le rapport principal.</span><span class="sxs-lookup"><span data-stu-id="d8e53-133">This value can be static text or an expression that references a field or other object in the main report.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d8e53-134">Dans le Générateur de rapports, s’il manque un paramètre dans la liste **Paramètres** et qu’une valeur par défaut est définie pour le sous-rapport, celui-ci est traité correctement.</span><span class="sxs-lookup"><span data-stu-id="d8e53-134">In Report Builder, if a parameter is missing from the **Parameters** list and the subreport has a default value defined, the subreport will be processed correctly.</span></span>  
    >   
    >  <span data-ttu-id="d8e53-135">Dans le Générateur de rapports, tous les paramètres nécessaires au sous-rapport doivent figurer dans la liste **Paramètres** .</span><span class="sxs-lookup"><span data-stu-id="d8e53-135">In Report Designer, all parameters that are required by the subreport must be included in the **Parameters** list.</span></span> <span data-ttu-id="d8e53-136">S'il manque un paramètre obligatoire, le sous-rapport ne s'affiche pas correctement dans le rapport principal.</span><span class="sxs-lookup"><span data-stu-id="d8e53-136">If a required parameter is missing, the subreport is not displayed correctly in the main report.</span></span>  
  
6.  <span data-ttu-id="d8e53-137">Répétez les étapes 3 et 5 pour spécifier un nom et une valeur pour chaque paramètre de sous-rapport.</span><span class="sxs-lookup"><span data-stu-id="d8e53-137">Repeat steps 3-5 to specify a name and value for each subreport parameter.</span></span>  
  
7.  <span data-ttu-id="d8e53-138">Pour supprimer un paramètre du sous-rapport, cliquez sur le paramètre dans la grille de paramètres, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="d8e53-138">To delete a subreport parameter, click the parameter in the parameter grid, and then click **Delete**.</span></span>  
  
8.  <span data-ttu-id="d8e53-139">Pour modifier l'ordre d'un paramètre de sous-rapport, cliquez sur le paramètre, puis cliquez sur le bouton Haut ou Bas.</span><span class="sxs-lookup"><span data-stu-id="d8e53-139">To change the order of a subreport parameter, click the parameter, and then click the up button or the down button.</span></span>  
  
     <span data-ttu-id="d8e53-140">La modification de l'ordre d'un paramètre n'a aucun effet sur le traitement du sous-rapport.</span><span class="sxs-lookup"><span data-stu-id="d8e53-140">Changing the order of a subreport parameter does not affect the processing of the subreport.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8e53-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d8e53-141">See Also</span></span>  
 <span data-ttu-id="d8e53-142">[Sous-rapports &#40;Générateur de rapports et SSRS&#41;](subreports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d8e53-142">[Subreports &#40;Report Builder and SSRS&#41;](subreports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="d8e53-143">Comportements de rendu &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d8e53-143">Rendering Behaviors &#40;Report Builder  and SSRS&#41;</span></span>](rendering-behaviors-report-builder-and-ssrs.md)  
  
  
