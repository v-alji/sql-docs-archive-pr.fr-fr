---
title: Exclure une règle d’entreprise (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], excluding
ms.assetid: bdbc9df0-23f7-40b9-8aba-4445c1482580
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 317964dcbc7b2cbe212c415b3aa4f9f1a0743301
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699947"
---
# <a name="exclude-a-business-rule-master-data-services"></a><span data-ttu-id="0229c-102">Exclure une règle d'entreprise (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0229c-102">Exclude a Business Rule (Master Data Services)</span></span>
  <span data-ttu-id="0229c-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], excluez une règle d'entreprise lorsque vous ne voulez pas supprimer la règle définitivement, mais que vous ne souhaitez pas valider des données par rapport à elle.</span><span class="sxs-lookup"><span data-stu-id="0229c-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], exclude a business rule when you do not want to delete the rule permanently, but you do not want to validate data against it.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0229c-104">Prérequis</span><span class="sxs-lookup"><span data-stu-id="0229c-104">Prerequisites</span></span>  
 <span data-ttu-id="0229c-105">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="0229c-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="0229c-106">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .</span><span class="sxs-lookup"><span data-stu-id="0229c-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="0229c-107">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="0229c-107">You must be a model administrator.</span></span> <span data-ttu-id="0229c-108">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0229c-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-exclude-a-business-rule"></a><span data-ttu-id="0229c-109">Pour exclure une règle d'entreprise</span><span class="sxs-lookup"><span data-stu-id="0229c-109">To exclude a business rule</span></span>  
  
1.  <span data-ttu-id="0229c-110">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="0229c-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="0229c-111">Dans la barre de menus, pointez sur **Gérer** et cliquez sur **Règles d'entreprise**.</span><span class="sxs-lookup"><span data-stu-id="0229c-111">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="0229c-112">Dans la page **Maintenance des règles d’entreprise** , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="0229c-112">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="0229c-113">Dans la liste **Entité** , sélectionnez une entité.</span><span class="sxs-lookup"><span data-stu-id="0229c-113">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="0229c-114">Dans la liste **type de membre** , sélectionnez un type de membre.</span><span class="sxs-lookup"><span data-stu-id="0229c-114">From the **Member Type** list, select a type of member.</span></span>  
  
6.  <span data-ttu-id="0229c-115">Dans la liste **Attribut** , sélectionnez un attribut ou conservez l’option par défaut **Tout**.</span><span class="sxs-lookup"><span data-stu-id="0229c-115">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="0229c-116">Dans la grille, dans la ligne de la règle d’entreprise, activez la case à cocher dans la colonne **exclure** .</span><span class="sxs-lookup"><span data-stu-id="0229c-116">In the grid, in the row for the business rule, select the check box in the **Exclude** column.</span></span> <span data-ttu-id="0229c-117">La valeur dans la colonne **État** est **exclusion en attente**.</span><span class="sxs-lookup"><span data-stu-id="0229c-117">The value in the **Status** column is **Exclusion pending**.</span></span>  
  
8.  <span data-ttu-id="0229c-118">Cliquez sur **Publier les règles d’entreprise**.</span><span class="sxs-lookup"><span data-stu-id="0229c-118">Click **Publish business rules**.</span></span>  
  
9. <span data-ttu-id="0229c-119">Dans la boîte de dialogue de confirmation, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0229c-119">In the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="0229c-120">La valeur de la colonne **État** est **exclue**.</span><span class="sxs-lookup"><span data-stu-id="0229c-120">The value in the **Status** column is **Excluded**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0229c-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0229c-121">See Also</span></span>  
 <span data-ttu-id="0229c-122">[Supprimer une règle d’entreprise &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-business-rule-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="0229c-122">[Delete a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-business-rule-master-data-services.md) </span></span>  
 <span data-ttu-id="0229c-123">[Créer et publier une règle d’entreprise &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="0229c-123">[Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md) </span></span>  
 [<span data-ttu-id="0229c-124">Règles d’entreprise &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0229c-124">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  
