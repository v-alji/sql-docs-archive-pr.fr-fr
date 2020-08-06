---
title: Générer automatiquement les valeurs de l’attribut Code (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 19b354ee-2906-4cc7-ba2f-32b4543bddcf
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 6c442f37ffe322985ba55b29b2c4cd539b8a3e05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613002"
---
# <a name="automatically-generate-code-attribute-values-master-data-services"></a><span data-ttu-id="46547-102">Générer automatiquement les valeurs de l'attribut Code (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="46547-102">Automatically Generate Code Attribute Values (Master Data Services)</span></span>
  <span data-ttu-id="46547-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], générez automatiquement les valeurs de l’attribut Code d’une entité quand vous souhaitez qu’un entier soit attribué automatiquement à la valeur Code chaque fois qu’un membre est créé.</span><span class="sxs-lookup"><span data-stu-id="46547-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], automatically generate values for an entity's Code attribute when you want an integer to be automatically assigned to the Code value each time a new member is created.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="46547-104">Prérequis</span><span class="sxs-lookup"><span data-stu-id="46547-104">Prerequisites</span></span>  
 <span data-ttu-id="46547-105">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="46547-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="46547-106">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .</span><span class="sxs-lookup"><span data-stu-id="46547-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="46547-107">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="46547-107">You must be a model administrator.</span></span> <span data-ttu-id="46547-108">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="46547-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="46547-109">L'entité doit exister.</span><span class="sxs-lookup"><span data-stu-id="46547-109">The entity must exist.</span></span> <span data-ttu-id="46547-110">Pour plus d’informations, consultez [créer une entité &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="46547-110">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-automatically-generate-code-values"></a><span data-ttu-id="46547-111">Pour générer automatiquement des valeurs de code</span><span class="sxs-lookup"><span data-stu-id="46547-111">To automatically generate Code values</span></span>  
  
1.  <span data-ttu-id="46547-112">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="46547-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="46547-113">Dans la page **Explorateur de modèles** , dans la barre de menus, pointez sur **gérer** , puis cliquez sur **entités**.</span><span class="sxs-lookup"><span data-stu-id="46547-113">On the **Model Explorer** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="46547-114">Dans la page **Maintenance de l'entité** , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="46547-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="46547-115">Sélectionnez la ligne de l'entité pour laquelle vous voulez générer les codes.</span><span class="sxs-lookup"><span data-stu-id="46547-115">Select the row for the entity that you want to generate codes for.</span></span>  
  
5.  <span data-ttu-id="46547-116">Cliquez sur **Modifier l'entité sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="46547-116">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="46547-117">Activez la case à cocher **Créer automatiquement les valeurs de code** .</span><span class="sxs-lookup"><span data-stu-id="46547-117">Select the **Create Code values automatically** check box.</span></span>  
  
7.  <span data-ttu-id="46547-118">Dans la zone **Démarrer avec** , tapez un nombre pour démarrer l'incrémentation.</span><span class="sxs-lookup"><span data-stu-id="46547-118">In the **Start with** box, type a number to begin incrementing.</span></span> <span data-ttu-id="46547-119">Si les membres existent déjà, le code sera défini en fonction de la valeur existante la plus élevée.</span><span class="sxs-lookup"><span data-stu-id="46547-119">If members already exist, the Code will be set based on the highest existing value.</span></span> <span data-ttu-id="46547-120">Par exemple, si la valeur de code existante la plus élevée est 299, la valeur de code du membre suivant sera 300.</span><span class="sxs-lookup"><span data-stu-id="46547-120">For example, if the highest existing Code value is 299, the next member's Code value will be set to 300.</span></span>  
  
8.  <span data-ttu-id="46547-121">Cliquez sur **enregistrer l’entité**.</span><span class="sxs-lookup"><span data-stu-id="46547-121">Click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46547-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="46547-122">See Also</span></span>  
 <span data-ttu-id="46547-123">[Création automatique de code &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="46547-123">[Automatic Code Creation &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md) </span></span>  
 [<span data-ttu-id="46547-124">Générer automatiquement les valeurs des attributs autres que Code &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="46547-124">Automatically Generate Attribute Values Other Than Code &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/automatically-generate-attribute-values-other-than-code-master-data-services.md)  
  
  
