---
title: Réorganiser des colonnes (Complément MDS pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: ac00462e-c0f7-4b8d-86f2-d9eda2598a15
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f0c47a631ffe699936a8d45bcc4e47e0b6f0a985
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698375"
---
# <a name="reorder-columns-mds-add-in-for-excel"></a><span data-ttu-id="26d51-102">Réorganiser des colonnes (Complément MDS pour Excel)</span><span class="sxs-lookup"><span data-stu-id="26d51-102">Reorder Columns (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="26d51-103">Dans [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], vous pouvez réorganiser les colonnes en filtrant la liste avant le chargement.</span><span class="sxs-lookup"><span data-stu-id="26d51-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], you can reorder columns by filtering the list before loading.</span></span>  
  
 <span data-ttu-id="26d51-104">Lorsque vous réorganisez les attributs dans la boîte de dialogue **Filtre** , les données sont chargées dans Excel dans le nouvel ordre.</span><span class="sxs-lookup"><span data-stu-id="26d51-104">When you reorder attributes in the **Filter** dialog box, the data is loaded into Excel with the new order.</span></span> <span data-ttu-id="26d51-105">Toutefois, lors du prochain filtrage des données d'attribut, l'ordre rétabli sera celui de la conception d'origine.</span><span class="sxs-lookup"><span data-stu-id="26d51-105">However, the next time that you filter the attribute data, the order will revert to the order in the original design.</span></span> <span data-ttu-id="26d51-106">Pour modifier définitivement l'ordre, un administrateur doit modifier l'ordre dans la zone **Administration de système** de Master Data Manager.</span><span class="sxs-lookup"><span data-stu-id="26d51-106">To change the order permanently, an administrator should change the order in the **System Administration** area of Master Data Manager.</span></span> <span data-ttu-id="26d51-107">Pour plus d’informations, voir [Change the Order of Attributes](../change-the-order-of-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="26d51-107">For more information, see [Change the Order of Attributes](../change-the-order-of-attributes.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="26d51-108">Prérequis</span><span class="sxs-lookup"><span data-stu-id="26d51-108">Prerequisites</span></span>  
 <span data-ttu-id="26d51-109">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="26d51-109">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="26d51-110">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Explorateur** .</span><span class="sxs-lookup"><span data-stu-id="26d51-110">You must have permission to access the **Explorer** functional area.</span></span>  
  
### <a name="to-reorder-mds-managed-columns"></a><span data-ttu-id="26d51-111">Pour réorganiser les colonnes managées MDS</span><span class="sxs-lookup"><span data-stu-id="26d51-111">To reorder MDS-managed columns</span></span>  
  
1.  <span data-ttu-id="26d51-112">Ouvrez Excel et accédez à l'onglet **Données de référence** , puis connectez-vous à un référentiel MDS.</span><span class="sxs-lookup"><span data-stu-id="26d51-112">Open Excel and on the **Master Data** tab, connect to an MDS repository.</span></span> <span data-ttu-id="26d51-113">Pour plus d’informations, consultez [Se connecter à un référentiel MDS &#40;complément MDS pour Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="26d51-113">For more information, see [Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span></span>  
  
2.  <span data-ttu-id="26d51-114">Dans le volet **Explorateur de données de référence** , sélectionnez un modèle et une version.</span><span class="sxs-lookup"><span data-stu-id="26d51-114">In the **Master Data Explorer** pane, select a model and version.</span></span> <span data-ttu-id="26d51-115">La liste des entités est remplie.</span><span class="sxs-lookup"><span data-stu-id="26d51-115">The list of entities is populated.</span></span>  
  
    -   <span data-ttu-id="26d51-116">Si le volet **Explorateur de données de référence** n'est pas visible, dans le groupe **Se connecter et charger** , cliquez sur **Afficher l'Explorateur**.</span><span class="sxs-lookup"><span data-stu-id="26d51-116">If the **Master Data Explorer** pane is not visible, in the **Connect and Load** group, click **Show Explorer**.</span></span>  
  
    -   <span data-ttu-id="26d51-117">Si le volet **Explorateur de données de référence** est désactivé, cela signifie que la feuille de calcul existante contient déjà des données managées MDS.</span><span class="sxs-lookup"><span data-stu-id="26d51-117">If the **Master Data Explorer** pane is disabled, it is because the existing sheet already contains MDS-managed data.</span></span> <span data-ttu-id="26d51-118">Pour activer le volet, ouvrez une nouvelle feuille de calcul.</span><span class="sxs-lookup"><span data-stu-id="26d51-118">To enable the pane, open a new worksheet.</span></span>  
  
3.  <span data-ttu-id="26d51-119">Dans le volet **Explorateur de données de référence** , cliquez sur une entité.</span><span class="sxs-lookup"><span data-stu-id="26d51-119">In the **Master Data Explorer** pane, click an entity.</span></span>  
  
4.  <span data-ttu-id="26d51-120">Dans le groupe **Se connecter et charger** , cliquez sur **Filtrer**.</span><span class="sxs-lookup"><span data-stu-id="26d51-120">In the **Connect and Load** group, click **Filter**.</span></span>  
  
5.  <span data-ttu-id="26d51-121">Dans la boîte de dialogue **Filtrer** , dans la section **Colonnes** , dans la liste d'attributs, cliquez sur l'attribut à déplacer.</span><span class="sxs-lookup"><span data-stu-id="26d51-121">In the **Filter** dialog box, in the **Columns** section, in the list of attributes, click the attribute you want to move.</span></span>  
  
6.  <span data-ttu-id="26d51-122">À droite de la liste, cliquez sur la flèche **Haut** ou **Bas** pour déplacer l'attribut à gauche et à droite dans la feuille de calcul.</span><span class="sxs-lookup"><span data-stu-id="26d51-122">To the right of the list, click the **Up** or **Down** arrow to move the attribute left and right in the worksheet.</span></span>  
  
7.  <span data-ttu-id="26d51-123">Répétez l'étape 7 pour chaque attribut jusqu'à ce que l'ordre de haut en bas représente l'ordre de gauche à droite que vous souhaitez dans la feuille de calcul.</span><span class="sxs-lookup"><span data-stu-id="26d51-123">Repeat step 7 for each attribute until the top-to-bottom order represents the left-to-right order you want in the worksheet.</span></span>  
  
8.  <span data-ttu-id="26d51-124">Cliquez sur **Charger les données**.</span><span class="sxs-lookup"><span data-stu-id="26d51-124">Click **Load Data**.</span></span> <span data-ttu-id="26d51-125">La feuille est renseignée avec les données managées MDS et les colonnes sont affichées dans l'ordre que vous avez spécifié.</span><span class="sxs-lookup"><span data-stu-id="26d51-125">The sheet is populated with MDS-managed data and the columns are displayed in the order you specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26d51-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="26d51-126">See Also</span></span>  
 [<span data-ttu-id="26d51-127">Chargement de données &#40;Complément MDS pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="26d51-127">Loading Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-exporting-data-to-excel-mds-add-in-for-excel.md)  
  
  
