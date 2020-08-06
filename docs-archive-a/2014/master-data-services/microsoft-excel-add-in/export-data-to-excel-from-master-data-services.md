---
title: Charger des données à partir de MDS dans Excel | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: dd29389b-928c-4e50-995c-c6af27f97805
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 35672807d5bb108e9386f892aea1847d45ebeb33
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699893"
---
# <a name="load-data-from-mds-into-excel"></a><span data-ttu-id="32856-102">Charger des données MDS dans Excel</span><span class="sxs-lookup"><span data-stu-id="32856-102">Load Data from MDS into Excel</span></span>
  <span data-ttu-id="32856-103">Dans [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] , vous devez charger les données à partir du référentiel MDS afin de les utiliser.</span><span class="sxs-lookup"><span data-stu-id="32856-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], you must load data from the MDS repository in order to work with it.</span></span>  
  
 <span data-ttu-id="32856-104">Si vous souhaitez filtrer le DataSet avant le chargement, consultez [Filtrer les données avant de charger &#40;Complément MDS pour Excel&#41;](filter-data-before-exporting-mds-add-in-for-excel.md) à la place.</span><span class="sxs-lookup"><span data-stu-id="32856-104">If you want to filter the dataset before loading, see [Filter Data before Loading &#40;MDS Add-in for Excel&#41;](filter-data-before-exporting-mds-add-in-for-excel.md) instead.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="32856-105">Prérequis</span><span class="sxs-lookup"><span data-stu-id="32856-105">Prerequisites</span></span>  
 <span data-ttu-id="32856-106">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="32856-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="32856-107">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Explorateur** .</span><span class="sxs-lookup"><span data-stu-id="32856-107">You must have permission to access the **Explorer** functional area.</span></span>  
  
### <a name="to-load-data-from-mds-into-excel"></a><span data-ttu-id="32856-108">Pour charger des données MDS dans Excel</span><span class="sxs-lookup"><span data-stu-id="32856-108">To load data from MDS into Excel</span></span>  
  
1.  <span data-ttu-id="32856-109">Ouvrez Excel et accédez à l'onglet **Données de référence** , puis connectez-vous à un référentiel MDS.</span><span class="sxs-lookup"><span data-stu-id="32856-109">Open Excel and on the **Master Data** tab, connect to an MDS repository.</span></span> <span data-ttu-id="32856-110">Pour plus d’informations, consultez [Se connecter à un référentiel MDS &#40;complément MDS pour Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="32856-110">For more information, see [Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span></span>  
  
2.  <span data-ttu-id="32856-111">Dans le volet **Explorateur de données de référence** , sélectionnez un modèle et une version.</span><span class="sxs-lookup"><span data-stu-id="32856-111">In the **Master Data Explorer** pane, select a model and version.</span></span> <span data-ttu-id="32856-112">La liste des entités est remplie.</span><span class="sxs-lookup"><span data-stu-id="32856-112">The list of entities is populated.</span></span>  
  
    -   <span data-ttu-id="32856-113">Si le volet **Explorateur de données de référence** n'est pas visible, dans le groupe **Se connecter et charger** , cliquez sur **Afficher l'Explorateur**.</span><span class="sxs-lookup"><span data-stu-id="32856-113">If the **Master Data Explorer** pane is not visible, in the **Connect and Load** group, click **Show Explorer**.</span></span>  
  
    -   <span data-ttu-id="32856-114">Si le volet **Explorateur de données de référence** est désactivé, cela signifie que la feuille de calcul existante contient déjà des données managées MDS.</span><span class="sxs-lookup"><span data-stu-id="32856-114">If the **Master Data Explorer** pane is disabled, it is because the existing sheet already contains MDS-managed data.</span></span> <span data-ttu-id="32856-115">Pour activer le volet, ouvrez une nouvelle feuille de calcul.</span><span class="sxs-lookup"><span data-stu-id="32856-115">To enable the pane, open a new worksheet.</span></span>  
  
3.  <span data-ttu-id="32856-116">Dans le volet **Explorateur de données de référence** , dans la liste des entités, double-cliquez sur l’entité à charger.</span><span class="sxs-lookup"><span data-stu-id="32856-116">In the **Master Data Explorer** pane, in the list of entities, double-click the entity you want to load.</span></span>  
  
    > [!NOTE]  
    >  -   <span data-ttu-id="32856-117">Seul le premier million de membres est chargé dans Excel.</span><span class="sxs-lookup"><span data-stu-id="32856-117">Only the first one million members are loaded into Excel.</span></span> <span data-ttu-id="32856-118">Pour filtrer la liste avant le chargement, dans le ruban, dans le groupe **Se connecter et charger** , cliquez sur **Filtre**.</span><span class="sxs-lookup"><span data-stu-id="32856-118">To filter the list before loading, on the ribbon in the **Connect and Load** group, click **Filter**.</span></span>  
    > -   <span data-ttu-id="32856-119">Dans les colonnes qui représentent des listes contraintes (attributs basés sur un domaine), seules les 25 000 premières valeurs sont chargées.</span><span class="sxs-lookup"><span data-stu-id="32856-119">In columns that are constrained lists (domain-based attributes), only the first 25,000 values are loaded.</span></span> <span data-ttu-id="32856-120">Vous pouvez modifier ce nombre dans la propriété MaximumDbaEntitySize du fichier excelusersettings.config situé sur l'ordinateur sur lequel Excel est installé.</span><span class="sxs-lookup"><span data-stu-id="32856-120">You can change this number in the MaximumDbaEntitySize property in the excelusersettings.config file located on the computer that Excel is installed on.</span></span> <span data-ttu-id="32856-121">Ce fichier se trouve dans C:\Users \\<utilisateur \> \AppData\Local\Microsoft\Microsoft SQL Server\120\MasterDataServices \\ .</span><span class="sxs-lookup"><span data-stu-id="32856-121">This file is located in C:\Users\\<user\>\AppData\Local\Microsoft\Microsoft SQL Server\120\MasterDataServices\\.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="32856-122">Quand vous chargez des données de texte délimitées à l’aide du complément pour Microsoft Excel avec Excel 32 bits et que les paramètres des propriétés **Nombre de cellules à charger** et **Nombre de cellules à publier** ont une valeur maximale de 1000, une erreur de mémoire insuffisante se produit.</span><span class="sxs-lookup"><span data-stu-id="32856-122">When you load text-delimited data using the Add-in for Microsoft Excel with 32-bit Excel, and the settings for the **Cell Count to Load** and **Cell Count to Publish** properties are both set to the maximum of 1000, an out-of-memory error will occur.</span></span> <span data-ttu-id="32856-123">Vous devez utiliser Excel 64 bits pour utiliser les paramètres maximaux de **Nombre de cellules à charger** et **Nombre de cellules à publier**.</span><span class="sxs-lookup"><span data-stu-id="32856-123">You have to use 64-bit Excel to use the maximum settings for **Cell Count to Load** and **Cell Count to Publish**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="32856-124">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="32856-124">Next Steps</span></span>  
 [<span data-ttu-id="32856-125">Publier des données d’Excel dans MDS &#40;Complément MDS pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="32856-125">Publish Data from Excel to MDS &#40;MDS Add-in for Excel&#41;</span></span>](import-data-from-excel-to-master-data-services-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="32856-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="32856-126">See Also</span></span>  
 <span data-ttu-id="32856-127">[Chargement de données &#40;Complément MDS pour Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="32856-127">[Loading Data &#40;MDS Add-in for Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span></span>  
 <span data-ttu-id="32856-128">[Boîte de dialogue Filtrer &#40;Complément MDS pour Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="32856-128">[Filter Dialog Box &#40;MDS Add-in for Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="32856-129">Publication des Complément MDS pour Excel de &#40;de données&#41;</span><span class="sxs-lookup"><span data-stu-id="32856-129">Publishing Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-importing-data-from-excel-mds-add-in-for-excel.md)  
  
  
