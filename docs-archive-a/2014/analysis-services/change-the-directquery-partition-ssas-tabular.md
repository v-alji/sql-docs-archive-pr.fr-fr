---
title: Modifier la partition DirectQuery (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f9df1e66-dd23-41b4-95eb-af110d10eda4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 43d14785f72d9bfe6406e2b81d3f1b97e9b7cc2e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603157"
---
# <a name="change-the-directquery-partition-ssas-tabular"></a><span data-ttu-id="3aaee-102">Modifier la partition DirectQuery (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="3aaee-102">Change the DirectQuery Partition (SSAS Tabular)</span></span>
  <span data-ttu-id="3aaee-103">Dans la mesure où une seule partition d'une table peut être désignée en tant que partition DirectQuery, par défaut, Analysis Services utilise la première partition qui a été créée dans la table.</span><span class="sxs-lookup"><span data-stu-id="3aaee-103">Because only one partition in a table can be designated as the DirectQuery partition, by default, Analysis Services uses the first partition that was created in the table.</span></span> <span data-ttu-id="3aaee-104">Pendant la création du projet de modèle, vous pouvez modifier la partition DirectQuery à l'aide de la boîte de dialogue Gestionnaire de partitions dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3aaee-104">During model project authoring, you can change the DirectQuery partition by using the Partition Manager dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="3aaee-105">Pour les modèles déployés, vous pouvez modifier la partition DirectQuery à l'aide de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3aaee-105">For deployed models, you can change the DirectQuery partition by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
### <a name="change-the-directquery-partition-for-a-tabular-model-project"></a><span data-ttu-id="3aaee-106">Modifier la partition DirectQuery pour un projet de modèle tabulaire</span><span class="sxs-lookup"><span data-stu-id="3aaee-106">Change the DirectQuery partition for a tabular model project</span></span>  
  
1.  <span data-ttu-id="3aaee-107">Dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dans le générateur de modèles, cliquez sur la table (l'onglet) qui contient la table partitionnée.</span><span class="sxs-lookup"><span data-stu-id="3aaee-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], in the model designer, click on the table (tab) that contains the partitioned table.</span></span>  
  
2.  <span data-ttu-id="3aaee-108">Cliquez sur le menu **Table** , puis sur **Partitions**.</span><span class="sxs-lookup"><span data-stu-id="3aaee-108">Click on the **Table** menu, and then click **Partitions**.</span></span>  
  
3.  <span data-ttu-id="3aaee-109">Dans le **Gestionnaire de partitions**, la partition correspondant à la partition de requête directe active est indiquée par le préfixe **(DirectQuery)** dans le nom de la partition.</span><span class="sxs-lookup"><span data-stu-id="3aaee-109">In **Partition Manager**, the partition that is the current Direct Query partition in indicated by the prefix **(DirectQuery)** on the partition name.</span></span>  
  
     <span data-ttu-id="3aaee-110">Sélectionnez une autre partition dans la liste **Partitions** , puis cliquez sur **Définir comme DirectQuery**.</span><span class="sxs-lookup"><span data-stu-id="3aaee-110">Select a different partition from the **Partitions** list, and then click **Set as DirectQuery**.</span></span> <span data-ttu-id="3aaee-111">Le bouton **Définir comme DirectQuery** n'est pas activé lorsque la partition DirectQuery active est sélectionnée, et n'est pas visible si le modèle n'a pas été activé pour le mode de requête directe.</span><span class="sxs-lookup"><span data-stu-id="3aaee-111">The **Set as DirectQuery** button is not enabled when the current DirectQuery partition is selected, and is not visible if the model has not been enabled for Direct Query mode.</span></span>  
  
4.  <span data-ttu-id="3aaee-112">Si nécessaire, modifiez les options de traitement, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3aaee-112">If necessary, change the processing options, and then click **OK**.</span></span>  
  
### <a name="change-the-directquery-partition-for-a-deployed-tabular-model"></a><span data-ttu-id="3aaee-113">Modifier la partition DirectQuery pour un modèle tabulaire déployé</span><span class="sxs-lookup"><span data-stu-id="3aaee-113">Change the DirectQuery partition for a deployed tabular model</span></span>  
  
1.  <span data-ttu-id="3aaee-114">Dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], ouvrez la base de données model dans l'Explorateur d'objets.</span><span class="sxs-lookup"><span data-stu-id="3aaee-114">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], open the model database in Object Explorer.</span></span>  
  
2.  <span data-ttu-id="3aaee-115">Développez le nœud **Tables** , cliquez avec le bouton droit sur la table partitionnée, puis sélectionnez **Partitions**.</span><span class="sxs-lookup"><span data-stu-id="3aaee-115">Expand the **Tables** node, then right-click the partitioned table, and then select **Partitions**.</span></span>  
  
     <span data-ttu-id="3aaee-116">La partition qui est indiquée pour être utilisée avec le mode DirectQuery a le préfixe (DirectQuery) sur le nom de partition.</span><span class="sxs-lookup"><span data-stu-id="3aaee-116">The partition that is designated for use with DirectQuery mode has the prefix (DirectQuery) on the partition name.</span></span>  
  
3.  <span data-ttu-id="3aaee-117">Pour passer à une autre partition, cliquez sur l'icône de la barre d'outils **Requête directe** pour ouvrir la boîte de dialogue **Définir une partition DirectQuery** .</span><span class="sxs-lookup"><span data-stu-id="3aaee-117">To change to a different partition, click the **Direct Query** toolbar icon to open the **Set DirectQuery Partition** dialog box.</span></span> <span data-ttu-id="3aaee-118">L'icône de la barre d'outils DirectQuery n'est pas disponible sur les modèles qui n'ont pas été activés pour la requête directe.</span><span class="sxs-lookup"><span data-stu-id="3aaee-118">The DirectQuery toolbar icon is not available on models that have not been enabled for Direct Query.</span></span>  
  
4.  <span data-ttu-id="3aaee-119">Choisissez une autre partition dans la liste déroulante **Nom de la partition** , puis modifiez les options de traitement sur la partition, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="3aaee-119">Choose a different partition from the **Partition Name** dropdown list, and then change processing options on the partition if necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aaee-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3aaee-120">See Also</span></span>  
 [<span data-ttu-id="3aaee-121">Partitions &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="3aaee-121">Partitions &#40;SSAS Tabular&#41;</span></span>](tabular-models/partitions-ssas-tabular.md)  
  
  
