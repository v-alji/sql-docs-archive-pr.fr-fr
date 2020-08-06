---
title: Créer un attribut basé sur un domaine (Complément MDS pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 7b3e30dc-8f41-4a5d-8009-ae5a4426a64b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bda0c7f63ad380aaea5d980d2e729822ec9a3d22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600123"
---
# <a name="create-a-domain-based-attribute-mds-add-in-for-excel"></a><span data-ttu-id="28c4e-102">Créer un attribut basé sur un domaine (complément MDS pour Excel)</span><span class="sxs-lookup"><span data-stu-id="28c4e-102">Create a Domain-based Attribute (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="28c4e-103">Dans le [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], les administrateurs peuvent créer un attribut basé sur un domaine quand ils souhaitent limiter les valeurs d’une colonne à un ensemble de valeurs spécifique.</span><span class="sxs-lookup"><span data-stu-id="28c4e-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], administrators can create a domain-based attribute when they want to constrain the values in a column to a specific set of values.</span></span>  
  
 <span data-ttu-id="28c4e-104">Les valeurs peuvent déjà figurer dans la feuille de calcul ou provenir d'une entité existante.</span><span class="sxs-lookup"><span data-stu-id="28c4e-104">The values can already be in the worksheet or they can come from an existing entity.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="28c4e-105">Si les utilisateurs tapent une valeur dans la colonne contrainte au lieu de la sélectionner dans la liste, des erreurs sont affichées dans la colonne **$InputStatus$** lors de la publication.</span><span class="sxs-lookup"><span data-stu-id="28c4e-105">If users type a value in the constrained column, rather than selecting from the list, errors are displayed in the **$InputStatus$** column when they publish.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="28c4e-106">Prérequis</span><span class="sxs-lookup"><span data-stu-id="28c4e-106">Prerequisites</span></span>  
 <span data-ttu-id="28c4e-107">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="28c4e-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="28c4e-108">Vous devez avoir l'autorisation d'accéder aux zones fonctionnelles **Administration de système** et **Explorateur** .</span><span class="sxs-lookup"><span data-stu-id="28c4e-108">You must have permission to access the **System Administration** and **Explorer** functional areas.</span></span>  
  
-   <span data-ttu-id="28c4e-109">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="28c4e-109">You must be a model administrator.</span></span> <span data-ttu-id="28c4e-110">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="28c4e-110">For more information, see [Administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="28c4e-111">Le modèle et l'entité doivent déjà exister.</span><span class="sxs-lookup"><span data-stu-id="28c4e-111">The model and entity must already exist.</span></span>  
  
### <a name="to-perform-this-procedure"></a><span data-ttu-id="28c4e-112">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="28c4e-112">To perform this procedure:</span></span>  
  
1.  <span data-ttu-id="28c4e-113">Dans Excel, chargez l'entité qui contient la colonne (attribut) que vous souhaitez limiter.</span><span class="sxs-lookup"><span data-stu-id="28c4e-113">In Excel, load the entity that contains the column (attribute) you want to constrain.</span></span> <span data-ttu-id="28c4e-114">Pour plus d’informations, consultez [charger des données à partir de MDS dans Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="28c4e-114">For more information, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
2.  <span data-ttu-id="28c4e-115">Cliquez sur une cellule de la colonne que vous souhaitez limiter.</span><span class="sxs-lookup"><span data-stu-id="28c4e-115">Click any cell in the column you want to constrain.</span></span>  
  
3.  <span data-ttu-id="28c4e-116">Dans le groupe **Modèle de build** , cliquez sur **Propriétés d'attribut**.</span><span class="sxs-lookup"><span data-stu-id="28c4e-116">In the **Build Model** group, click **Attribute Properties**.</span></span>  
  
4.  <span data-ttu-id="28c4e-117">Dans la boîte de dialogue **Propriétés d’attribut** , dans la liste **Type d’attribut** , choisissez **Liste contrainte (basée sur un domaine)**.</span><span class="sxs-lookup"><span data-stu-id="28c4e-117">In the **Attribute Properties** dialog box, in the **Attribute type** list, choose **Constrained list (domain-based)**.</span></span>  
  
5.  <span data-ttu-id="28c4e-118">Dans la liste **Remplir l’attribut avec les valeurs de** :</span><span class="sxs-lookup"><span data-stu-id="28c4e-118">In the **Populate the attribute with values from** list:</span></span>  
  
    -   <span data-ttu-id="28c4e-119">Pour utiliser des valeurs de la feuille de calcul, choisissez **la colonne sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="28c4e-119">To use values from the worksheet, choose **the selected column**.</span></span> <span data-ttu-id="28c4e-120">Une nouvelle entité et une nouvelle table de mise en lots seront créées avec les valeurs de la colonne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="28c4e-120">A new entity and new staging table will be created with the values from the selected column.</span></span>  
  
    -   <span data-ttu-id="28c4e-121">Pour utiliser des valeurs d'une entité existante, choisissez le nom de l'entité.</span><span class="sxs-lookup"><span data-stu-id="28c4e-121">To use values from an existing entity, choose the name of the entity.</span></span>  
  
6.  <span data-ttu-id="28c4e-122">Si vous avez choisi **la colonne sélectionnée** à l’étape précédente, dans la zone **Nouveau nom d’entité** , tapez un nom pour la nouvelle entité.</span><span class="sxs-lookup"><span data-stu-id="28c4e-122">If you chose **the selected column** in the previous step, in the **New entity name** box, type a name for the new entity.</span></span> <span data-ttu-id="28c4e-123">Il peut être identique au nom de la colonne (attribut).</span><span class="sxs-lookup"><span data-stu-id="28c4e-123">This can be the same as the column (attribute) name.</span></span>  
  
7.  <span data-ttu-id="28c4e-124">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="28c4e-124">Click **OK**.</span></span> <span data-ttu-id="28c4e-125">Chaque cellule dans la colonne comporte désormais une liste de valeurs dans laquelle les utilisateurs peuvent faire leur choix.</span><span class="sxs-lookup"><span data-stu-id="28c4e-125">Each cell in the column now has a list of values for users to choose from.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="28c4e-126">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="28c4e-126">Next Steps</span></span>  
  
-   <span data-ttu-id="28c4e-127">Pour ajouter et supprimer des valeurs dans la liste contrainte, chargez l'entité sur laquelle l'attribut est basé.</span><span class="sxs-lookup"><span data-stu-id="28c4e-127">To add and delete values in the constrained list, load the entity that the attribute is based on.</span></span> <span data-ttu-id="28c4e-128">Pour plus d’informations sur le chargement des entités, consultez [charger des données à partir de MDS dans Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="28c4e-128">For more information on loading entities, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28c4e-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="28c4e-129">See Also</span></span>  
 <span data-ttu-id="28c4e-130">[Attributs basés sur un domaine &#40;Master Data Services&#41;](../domain-based-attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="28c4e-130">[Domain-Based Attributes &#40;Master Data Services&#41;](../domain-based-attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="28c4e-131">[Créer une entité &#40;Complément MDS pour Excel&#41;](create-an-entity-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="28c4e-131">[Create an Entity &#40;MDS Add-in for Excel&#41;](create-an-entity-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="28c4e-132">Génération d’un modèle &#40;Complément MDS pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="28c4e-132">Building a Model &#40;MDS Add-in for Excel&#41;</span></span>](building-a-model-mds-add-in-for-excel.md)  
  
  
