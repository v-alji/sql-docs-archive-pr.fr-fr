---
title: Ajouter des membres à une collection (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- collections [Master Data Services], adding members
ms.assetid: 1a7155e6-2d4a-4ed1-a72c-edb37fa1a46b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ce2038f3bc90a2f17506b0aadaaf9707fa911896
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614149"
---
# <a name="add-members-to-a-collection-master-data-services"></a><span data-ttu-id="810f5-102">Ajouter des membres à une collection (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="810f5-102">Add Members to a Collection (Master Data Services)</span></span>
  <span data-ttu-id="810f5-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], vous pouvez ajouter les membres feuille et consolidés à une collection.</span><span class="sxs-lookup"><span data-stu-id="810f5-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can add leaf and consolidated members to a collection.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="810f5-104">Prérequis</span><span class="sxs-lookup"><span data-stu-id="810f5-104">Prerequisites</span></span>  
 <span data-ttu-id="810f5-105">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="810f5-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="810f5-106">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Explorateur** .</span><span class="sxs-lookup"><span data-stu-id="810f5-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="810f5-107">Vous devez au minimum disposer de l’autorisation **Mettre à jour** sur l’objet de modèle de collection auquel vous ajoutez des membres.</span><span class="sxs-lookup"><span data-stu-id="810f5-107">You must have a minimum of **Update** permission to the collection model object that you are adding members to.</span></span>  
  
-   <span data-ttu-id="810f5-108">Une collection doit exister.</span><span class="sxs-lookup"><span data-stu-id="810f5-108">A collection must exist.</span></span> <span data-ttu-id="810f5-109">Pour plus d’informations, consultez [Créer une collection &#40;Master Data Services&#41;](create-a-collection-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="810f5-109">For more information, see [Create a Collection &#40;Master Data Services&#41;](create-a-collection-master-data-services.md).</span></span>  
  
### <a name="to-add-members-to-a-collection"></a><span data-ttu-id="810f5-110">Pour ajouter des membres à une collection</span><span class="sxs-lookup"><span data-stu-id="810f5-110">To add members to a collection</span></span>  
  
1.  <span data-ttu-id="810f5-111">Dans la page d'accueil de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="810f5-111">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="810f5-112">Dans la liste **Version** , sélectionnez une version.</span><span class="sxs-lookup"><span data-stu-id="810f5-112">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="810f5-113">Cliquez sur **Explorateur**.</span><span class="sxs-lookup"><span data-stu-id="810f5-113">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="810f5-114">Dans la barre de menus, pointez sur **Collections** , puis cliquez sur *entity_name*.</span><span class="sxs-lookup"><span data-stu-id="810f5-114">From the menu bar, point to **Collections** and click *entity_name*.</span></span>  
  
5.  <span data-ttu-id="810f5-115">Dans la grille, cliquez sur la ligne de la collection à laquelle vous voulez ajouter des membres.</span><span class="sxs-lookup"><span data-stu-id="810f5-115">In the grid, click the row for the collection you want to add members to.</span></span>  
  
6.  <span data-ttu-id="810f5-116">Cliquez sur l’onglet **Membres de collection** .</span><span class="sxs-lookup"><span data-stu-id="810f5-116">Click the **Collection Members** tab.</span></span>  
  
7.  <span data-ttu-id="810f5-117">Cliquez sur **Modifier les membres**.</span><span class="sxs-lookup"><span data-stu-id="810f5-117">Click **Edit Members**.</span></span>  
  
8.  <span data-ttu-id="810f5-118">Pour filtrer la liste des membres disponibles, sélectionnez à partir de la liste à gauche.</span><span class="sxs-lookup"><span data-stu-id="810f5-118">To filter the list of available members, select from the list on the left.</span></span>  
  
9. <span data-ttu-id="810f5-119">Cliquez sur la ligne correspondant au membre que vous souhaitez ajouter, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="810f5-119">Click the row with the member you want to add and click **Add**.</span></span>  
  
10. <span data-ttu-id="810f5-120">Vous pouvez également réorganiser les membres de collection en cliquant sur **Monter** ou **Descendre**.</span><span class="sxs-lookup"><span data-stu-id="810f5-120">Optionally, rearrange collection members by clicking **Up** or **Down**.</span></span>  
  
11. <span data-ttu-id="810f5-121">Si vous le souhaitez, définissez les valeurs de poids en cliquant sur la valeur dans la colonne **Poids** .</span><span class="sxs-lookup"><span data-stu-id="810f5-121">Optionally, set weight values by clicking the value in the **Weight** column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="810f5-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="810f5-122">See Also</span></span>  
 [<span data-ttu-id="810f5-123">Collections &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="810f5-123">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)  
  
  
