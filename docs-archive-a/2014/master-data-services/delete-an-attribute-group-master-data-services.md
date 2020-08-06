---
title: Supprimer un groupe d’attributs (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting attribute groups [Master Data Services]
- attribute groups [Master Data Services], deleting
ms.assetid: f915e89b-629d-4725-aea6-a7f051978244
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 833c5cf327034b25d68af123a1fc134372bd6f10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614140"
---
# <a name="delete-an-attribute-group-master-data-services"></a><span data-ttu-id="55065-102">Supprimer un groupe d'attributs (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="55065-102">Delete an Attribute Group (Master Data Services)</span></span>
  <span data-ttu-id="55065-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], supprimez un groupe d'attributs lorsque vous n'avez plus besoin de l'onglet à afficher dans la zone fonctionnelle **Explorateur** de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55065-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete an attribute group when you no longer need the tab to display in the **Explorer** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
-   <span data-ttu-id="55065-104">**Remarque** Lorsque les groupes d'attributs existent, les attributs qui n'appartiennent pas à un groupe d'attributs ne sont pas affichés dans l' **Explorateur**.</span><span class="sxs-lookup"><span data-stu-id="55065-104">**Note** When attribute groups exist, attributes that do not belong to an attribute group are not displayed in **Explorer**.</span></span> <span data-ttu-id="55065-105">Lorsqu'aucun groupe d'attributs n'existe, tous les attributs sont affichés.</span><span class="sxs-lookup"><span data-stu-id="55065-105">When no attribute groups exist, all attributes are displayed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="55065-106">Prérequis</span><span class="sxs-lookup"><span data-stu-id="55065-106">Prerequisites</span></span>  
 <span data-ttu-id="55065-107">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="55065-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="55065-108">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .</span><span class="sxs-lookup"><span data-stu-id="55065-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="55065-109">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="55065-109">You must be a model administrator.</span></span> <span data-ttu-id="55065-110">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="55065-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-an-attribute-group"></a><span data-ttu-id="55065-111">Pour supprimer un groupe d'attributs</span><span class="sxs-lookup"><span data-stu-id="55065-111">To delete an attribute group</span></span>  
  
1.  <span data-ttu-id="55065-112">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="55065-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="55065-113">Dans la page **vue du modèle** , dans la barre de menus, pointez sur **gérer** , puis cliquez sur groupes d' **attributs**.</span><span class="sxs-lookup"><span data-stu-id="55065-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Attribute Groups**.</span></span>  
  
3.  <span data-ttu-id="55065-114">Dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="55065-114">From the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="55065-115">Dans la liste **Entité** , sélectionnez une entité.</span><span class="sxs-lookup"><span data-stu-id="55065-115">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="55065-116">Cliquez sur le signe plus (+) pour développer **groupes feuille**, groupes **consolidés**ou **groupes de collections**, selon le type de groupe que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="55065-116">Click the plus sign to expand **Leaf Groups**, **Consolidated Groups**, or **Collection Groups**, depending on the type of group you want to delete.</span></span>  
  
6.  <span data-ttu-id="55065-117">Cliquez sur le groupe d'attributs à supprimer.</span><span class="sxs-lookup"><span data-stu-id="55065-117">Click the attribute group you want to delete.</span></span>  
  
7.  <span data-ttu-id="55065-118">Cliquez sur **supprimer le groupe sélectionné**.</span><span class="sxs-lookup"><span data-stu-id="55065-118">Click **Delete selected group**.</span></span>  
  
8.  <span data-ttu-id="55065-119">Dans la boîte de dialogue de confirmation, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="55065-119">In the confirmation dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="55065-120">Dans la boîte de dialogue de confirmation supplémentaire, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="55065-120">In the additional confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55065-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="55065-121">See Also</span></span>  
 <span data-ttu-id="55065-122">[Groupes d’attributs &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="55065-122">[Attribute Groups &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span></span>  
 [<span data-ttu-id="55065-123">Créer un groupe d’attributs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="55065-123">Create an Attribute Group &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-attribute-group-master-data-services.md)  
  
  
