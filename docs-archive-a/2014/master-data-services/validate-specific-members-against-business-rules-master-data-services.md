---
title: Valider des membres spécifiques par rapport aux règles d’entreprise (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- applying business rules [Master Data Services]
- business rules [Master Data Services], applying to select members
ms.assetid: 2288ef43-5392-47ea-b651-ec25e5692a14
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 18af83146679eb77638dfbc98b31f198dc8e07b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604607"
---
# <a name="validate-specific-members-against-business-rules-master-data-services"></a><span data-ttu-id="cce4a-102">Valider des membres spécifiques par rapport aux règles d'entreprise (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="cce4a-102">Validate Specific Members against Business Rules (Master Data Services)</span></span>
  <span data-ttu-id="cce4a-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], appliquez des règles d'entreprise sélectivement lorsque vous souhaitez mettre à jour ou valider des sous-ensembles de membres par rapport à des règles d'entreprise.</span><span class="sxs-lookup"><span data-stu-id="cce4a-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], apply business rules selectively when you want to update or validate subsets of members against business rules.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cce4a-104">Si vous souhaitez appliquer des règles d’entreprise à tous les membres dans une version d’un modèle, consultez [Valider une version par rapport aux règles d’entreprise &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="cce4a-104">If you want to apply business rules to all members in a version of a model, see [Validate a Version against Business Rules &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cce4a-105">Prérequis</span><span class="sxs-lookup"><span data-stu-id="cce4a-105">Prerequisites</span></span>  
 <span data-ttu-id="cce4a-106">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="cce4a-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="cce4a-107">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Explorateur** .</span><span class="sxs-lookup"><span data-stu-id="cce4a-107">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="cce4a-108">Vous devez au minimum disposer de l'autorisation **Mettre à jour** sur l'objet modèle auquel vous appliquez les règles d'entreprise.</span><span class="sxs-lookup"><span data-stu-id="cce4a-108">You must have a minimum of **Update** permission to the model object you are applying business rules to.</span></span>  
  
### <a name="to-apply-business-rules-selectively"></a><span data-ttu-id="cce4a-109">Pour appliquer des règles d'entreprise sélectivement</span><span class="sxs-lookup"><span data-stu-id="cce4a-109">To apply business rules selectively</span></span>  
  
1.  <span data-ttu-id="cce4a-110">Dans la page d'accueil de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="cce4a-110">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="cce4a-111">Dans la liste **Version** , sélectionnez une version.</span><span class="sxs-lookup"><span data-stu-id="cce4a-111">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="cce4a-112">Cliquez sur **Explorateur**.</span><span class="sxs-lookup"><span data-stu-id="cce4a-112">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="cce4a-113">Dans la barre de menus, pointez sur **Entités** , puis cliquez sur le nom de l'entité qui contient les membres auxquels vous souhaitez appliquer les règles.</span><span class="sxs-lookup"><span data-stu-id="cce4a-113">From the menu bar, point to **Entities** and click the name of the entity that contains members you want to apply rules to.</span></span>  
  
5.  <span data-ttu-id="cce4a-114">Cliquez sur **Appliquer les règles d’entreprise**.</span><span class="sxs-lookup"><span data-stu-id="cce4a-114">Click **Apply business rules**.</span></span> <span data-ttu-id="cce4a-115">Les règles d'entreprise sont appliquées uniquement aux membres affichés dans la grille.</span><span class="sxs-lookup"><span data-stu-id="cce4a-115">Business rules are applied only to the members displayed in the grid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cce4a-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cce4a-116">See Also</span></span>  
 <span data-ttu-id="cce4a-117">[Valider une version par rapport aux règles d’entreprise &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="cce4a-117">[Validate a Version against Business Rules &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md) </span></span>  
 [<span data-ttu-id="cce4a-118">Règles d’entreprise &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="cce4a-118">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  
