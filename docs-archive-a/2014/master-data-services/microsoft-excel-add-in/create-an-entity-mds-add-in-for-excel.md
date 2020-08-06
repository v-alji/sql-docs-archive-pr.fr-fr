---
title: Créer une entité (Complément MDS pour Excel)| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: d354abb3-88fe-4b40-a374-f6256b84ffae
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 87ad67f7347da87c67afc11590df6775af4cf3d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600121"
---
# <a name="create-an-entity-mds-add-in-for-excel"></a><span data-ttu-id="6644d-102">Créer une entité (Complément MDS pour Excel)</span><span class="sxs-lookup"><span data-stu-id="6644d-102">Create an Entity (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="6644d-103">Dans [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], les administrateurs peuvent créer des entités pour stocker des données.</span><span class="sxs-lookup"><span data-stu-id="6644d-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], administrators can create new entities to store data.</span></span> <span data-ttu-id="6644d-104">Lorsque vous créez une entité, vous devez charger au moins un échantillonnage des données que vous souhaitez stocker.</span><span class="sxs-lookup"><span data-stu-id="6644d-104">When you create an entity you should load at least a sampling of the data you want to store.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6644d-105">Prérequis</span><span class="sxs-lookup"><span data-stu-id="6644d-105">Prerequisites</span></span>  
 <span data-ttu-id="6644d-106">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="6644d-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="6644d-107">Vous devez avoir l'autorisation d'accéder aux zones fonctionnelles **Administration de système** et **Explorateur** .</span><span class="sxs-lookup"><span data-stu-id="6644d-107">You must have permission to access the **System Administration** and **Explorer** functional areas.</span></span>  
  
-   <span data-ttu-id="6644d-108">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="6644d-108">You must be a model administrator.</span></span> <span data-ttu-id="6644d-109">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6644d-109">For more information, see [Administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="6644d-110">Vous devez disposer d'un modèle existant dans lequel créer l'entité.</span><span class="sxs-lookup"><span data-stu-id="6644d-110">You must have an existing model to create the entity in.</span></span> <span data-ttu-id="6644d-111">Pour plus d’informations, consultez [Créer un modèle &#40;Master Data Services&#41;](../create-a-model-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6644d-111">For more information, see [Create a Model &#40;Master Data Services&#41;](../create-a-model-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="6644d-112">Assurez-vous que vos données répondent aux exigences suivantes :</span><span class="sxs-lookup"><span data-stu-id="6644d-112">Ensure that your data meets the following requirements:</span></span>  
  
    -   <span data-ttu-id="6644d-113">Les données doivent avoir une ligne d'en-tête.</span><span class="sxs-lookup"><span data-stu-id="6644d-113">The data should have a header row.</span></span>  
  
    -   <span data-ttu-id="6644d-114">Il est utile de disposer de colonnes **Nom** et **Code** .</span><span class="sxs-lookup"><span data-stu-id="6644d-114">It is helpful to have **Name** and **Code** columns.</span></span> <span data-ttu-id="6644d-115">**Code** est un identificateur unique pour chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="6644d-115">**Code** is a unique identifier for each row.</span></span>  
  
    -   <span data-ttu-id="6644d-116">Vous devez avoir au moins une ligne de données autre que l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="6644d-116">You should have at least one row of data other than the header.</span></span> <span data-ttu-id="6644d-117">Toutes les colonnes n'ont pas besoin de valeurs, mais les données doivent être représentatives des données qui figureront dans l'entité.</span><span class="sxs-lookup"><span data-stu-id="6644d-117">All columns do not need values, but the data should be representative of the data that will be in the entity.</span></span>  
  
    -   <span data-ttu-id="6644d-118">Si vous avez une colonne qui contient un identificateur unique (connu dans MDS en tant que **Code**), assurez-vous que les valeurs sont uniques.</span><span class="sxs-lookup"><span data-stu-id="6644d-118">If you have a column that contains a unique identifier (known in MDS as **Code**), ensure that the values are unique.</span></span> <span data-ttu-id="6644d-119">Si aucune colonne ne contient d'identificateurs, vous pouvez les générer automatiquement lorsque vous créez l'entité.</span><span class="sxs-lookup"><span data-stu-id="6644d-119">If no column contains identifiers, you can have them generated automatically when you create the entity.</span></span>  
  
    -   <span data-ttu-id="6644d-120">Assurez-vous qu'aucune cellule ne contient de formules.</span><span class="sxs-lookup"><span data-stu-id="6644d-120">Ensure that no cells contain formulas.</span></span>  
  
    -   <span data-ttu-id="6644d-121">Assurez vous qu'aucune cellule ne contient de valeurs horaires.</span><span class="sxs-lookup"><span data-stu-id="6644d-121">Ensure that no cells contain time values.</span></span> <span data-ttu-id="6644d-122">Les valeurs de date peuvent être enregistrées dans MDS, mais pas les valeurs horaires.</span><span class="sxs-lookup"><span data-stu-id="6644d-122">Date values can be saved in MDS but time values cannot.</span></span>  
  
### <a name="to-create-an-entity-and-load-data"></a><span data-ttu-id="6644d-123">Pour créer une entité et charger des données</span><span class="sxs-lookup"><span data-stu-id="6644d-123">To create an entity and load data</span></span>  
  
1.  <span data-ttu-id="6644d-124">Ouvrez ou créez une feuille de calcul Excel contenant les données que vous souhaitez charger.</span><span class="sxs-lookup"><span data-stu-id="6644d-124">Open or create an Excel worksheet that contains data you want to load.</span></span>  
  
2.  <span data-ttu-id="6644d-125">Sélectionnez les cellules que vous souhaitez charger dans la nouvelle entité.</span><span class="sxs-lookup"><span data-stu-id="6644d-125">Select the cells you want to load into the new entity.</span></span>  
  
3.  <span data-ttu-id="6644d-126">Sous l’onglet **Données de référence** , dans le groupe **Modèle de build** , cliquez sur **Créer une entité**.</span><span class="sxs-lookup"><span data-stu-id="6644d-126">On the **Master Data** tab, in the **Build Model** group, click **Create Entity**.</span></span>  
  
4.  <span data-ttu-id="6644d-127">Si vous êtes invité à vous connecter à un référentiel MDS, faites-le.</span><span class="sxs-lookup"><span data-stu-id="6644d-127">If you are prompted to connect to an MDS repository, connect.</span></span>  
  
5.  <span data-ttu-id="6644d-128">Dans la boîte de dialogue **Créer une entité** , conservez la plage par défaut ou modifiez-la pour l’appliquer aux données que vous souhaitez charger.</span><span class="sxs-lookup"><span data-stu-id="6644d-128">In the **Create Entity** dialog box, leave the default range or change it to apply to the data you want to load.</span></span>  
  
6.  <span data-ttu-id="6644d-129">Ne décochez pas la case **Mes données comportent des en-têtes** .</span><span class="sxs-lookup"><span data-stu-id="6644d-129">Do not clear the **My data has headers** check box.</span></span>  
  
7.  <span data-ttu-id="6644d-130">Dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="6644d-130">From the **Model** list, select a model.</span></span>  
  
8.  <span data-ttu-id="6644d-131">Dans la liste **Version** , sélectionnez une version.</span><span class="sxs-lookup"><span data-stu-id="6644d-131">From the **Version** list, select a version.</span></span>  
  
9. <span data-ttu-id="6644d-132">Dans la zone **Nouveau nom d’entité** , entrez un nom pour l’entité.</span><span class="sxs-lookup"><span data-stu-id="6644d-132">In the **New entity name** box, type a name for the entity.</span></span>  
  
10. <span data-ttu-id="6644d-133">Dans la liste **Code** , sélectionnez la colonne qui contient les identificateurs uniques ou générez les codes automatiquement.</span><span class="sxs-lookup"><span data-stu-id="6644d-133">From the **Code** list, select the column that contains unique identifiers or have codes generated automatically.</span></span>  
  
11. <span data-ttu-id="6644d-134">facultatif.</span><span class="sxs-lookup"><span data-stu-id="6644d-134">Optional.</span></span> <span data-ttu-id="6644d-135">Dans la liste **Nom** , sélectionnez une colonne qui contient le nom de chaque membre.</span><span class="sxs-lookup"><span data-stu-id="6644d-135">From the **Name** list, select a column that contains names for each member.</span></span>  
  
12. <span data-ttu-id="6644d-136">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6644d-136">Click **OK**.</span></span> <span data-ttu-id="6644d-137">Lorsque l'entité a été correctement créée, une nouvelle ligne d'en-tête est affichée, les cellules sont mises en surbrillance et le nom de la feuille est mis à jour pour correspondre au nom de l'entité.</span><span class="sxs-lookup"><span data-stu-id="6644d-137">When the entity has been created successfully, a new header row is displayed, the cells are highlighted, and the sheet name is updated to match the entity name.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6644d-138">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="6644d-138">Next Steps</span></span>  
  
-   <span data-ttu-id="6644d-139">Pour afficher les erreurs qui se sont produites, dans le groupe **Publier et valider** , cliquez sur **Afficher l’état**.</span><span class="sxs-lookup"><span data-stu-id="6644d-139">To view errors that occurred, in the **Publish and Validate** group, click **Show Status**.</span></span> <span data-ttu-id="6644d-140">Les colonnes ValidationStatus et InputStatus sont affichées.</span><span class="sxs-lookup"><span data-stu-id="6644d-140">ValidationStatus and InputStatus columns are displayed.</span></span> <span data-ttu-id="6644d-141">Pour plus d’informations, consultez [Validation des données &#40;Complément MDS pour Excel&#41;](validating-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="6644d-141">For more information, see [Validating Data &#40;MDS Add-in for Excel&#41;](validating-data-mds-add-in-for-excel.md).</span></span>  
  
-   <span data-ttu-id="6644d-142">Vérifiez que les attributs ont été créés avec le type de données escompté.</span><span class="sxs-lookup"><span data-stu-id="6644d-142">Confirm that the attributes were created as the data type you expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6644d-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6644d-143">See Also</span></span>  
 [<span data-ttu-id="6644d-144">Créer un attribut basé sur un domaine &#40;complément MDS pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="6644d-144">Create a Domain-based Attribute &#40;MDS Add-in for Excel&#41;</span></span>](create-a-domain-based-attribute-mds-add-in-for-excel.md)  
  
  
