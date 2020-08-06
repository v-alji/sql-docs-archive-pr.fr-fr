---
title: Supprimer un attribut (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], deleting
- deleting attributes [Master Data Services]
ms.assetid: ec3e66f7-0e35-43d7-a80d-64899948ebfe
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 96db56dac9356b1131e722fc7f6b779c93305bb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695779"
---
# <a name="delete-an-attribute-master-data-services"></a><span data-ttu-id="5b750-102">Supprimer un attribut (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="5b750-102">Delete an Attribute (Master Data Services)</span></span>
  <span data-ttu-id="5b750-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], supprimez un attribut lorsque vous souhaitez supprimer définitivement l’attribut et toutes les valeurs d’attribut associées.</span><span class="sxs-lookup"><span data-stu-id="5b750-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete an attribute when you want to permanently delete the attribute and all associated attribute values.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5b750-104">Prérequis</span><span class="sxs-lookup"><span data-stu-id="5b750-104">Prerequisites</span></span>  
 <span data-ttu-id="5b750-105">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="5b750-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="5b750-106">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .</span><span class="sxs-lookup"><span data-stu-id="5b750-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="5b750-107">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="5b750-107">You must be a model administrator.</span></span> <span data-ttu-id="5b750-108">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5b750-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-an-attribute"></a><span data-ttu-id="5b750-109">Pour supprimer un attribut</span><span class="sxs-lookup"><span data-stu-id="5b750-109">To delete an attribute</span></span>  
  
1.  <span data-ttu-id="5b750-110">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="5b750-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="5b750-111">Dans la page **Vue du modèle** , dans la barre de menus, pointez sur **Gérer** , puis cliquez sur **Entités**.</span><span class="sxs-lookup"><span data-stu-id="5b750-111">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="5b750-112">Dans la page **Maintenance de l'entité** , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="5b750-112">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="5b750-113">Sélectionnez la ligne de l'entité qui contient l'attribut à supprimer.</span><span class="sxs-lookup"><span data-stu-id="5b750-113">Select the row for the entity that contains the attribute you want to delete.</span></span>  
  
5.  <span data-ttu-id="5b750-114">Cliquez sur **Modifier l'entité sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="5b750-114">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="5b750-115">Dans la page **modifier l’entité** , cliquez sur l’attribut que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="5b750-115">On the **Edit Entity** page, click the attribute you want to delete.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5b750-116">Vous ne pouvez pas supprimer les attributs Name ni Code.</span><span class="sxs-lookup"><span data-stu-id="5b750-116">You cannot delete the Name or Code attributes.</span></span>  
  
7.  <span data-ttu-id="5b750-117">Cliquez sur **Supprimer l’attribut sélectionné**.</span><span class="sxs-lookup"><span data-stu-id="5b750-117">Click **Delete selected attribute**.</span></span>  
  
8.  <span data-ttu-id="5b750-118">Dans la boîte de dialogue de confirmation, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5b750-118">In the confirmation dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="5b750-119">Dans la boîte de dialogue de confirmation supplémentaire, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5b750-119">In the additional confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b750-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5b750-120">See Also</span></span>  
 <span data-ttu-id="5b750-121">[Attributs &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5b750-121">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="5b750-122">[Attributs basés sur un domaine &#40;Master Data Services&#41;](../../2014/master-data-services/domain-based-attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5b750-122">[Domain-Based Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/domain-based-attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="5b750-123">[Créez un attribut de texte &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5b750-123">[Create a Text Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="5b750-124">Créer un attribut basé sur un domaine &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5b750-124">Create a Domain-Based Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md)  
  
  
