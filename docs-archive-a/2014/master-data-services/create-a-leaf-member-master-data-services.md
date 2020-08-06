---
title: Créer un membre feuille (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- leaf members [Master Data Services], creating
- creating leaf members [Master Data Services]
- members [Master Data Services], creating leaf members
ms.assetid: 0499d3b3-d508-4d43-a740-19cf53ade9f1
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fe0245dd30019e1cb9112754bd8b8eeafed93aa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600128"
---
# <a name="create-a-leaf-member-master-data-services"></a><span data-ttu-id="fa3f4-102">Créer un membre feuille (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="fa3f4-102">Create a Leaf Member (Master Data Services)</span></span>
  <span data-ttu-id="fa3f4-103">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , créez un membre feuille lorsque vous souhaitez ajouter des données de référence à votre système et que vous n’utilisez pas de tables de mise en lots ou [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] de pour importer des données.</span><span class="sxs-lookup"><span data-stu-id="fa3f4-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], create a leaf member when you want to add master data to your system and are not using staging tables or the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] to import data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fa3f4-104">Prérequis</span><span class="sxs-lookup"><span data-stu-id="fa3f4-104">Prerequisites</span></span>  
 <span data-ttu-id="fa3f4-105">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="fa3f4-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="fa3f4-106">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Explorateur** .</span><span class="sxs-lookup"><span data-stu-id="fa3f4-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="fa3f4-107">Vous devez disposer au minimum de l’autorisation **mettre à jour** sur l’objet modèle feuille pour l’entité à laquelle vous ajoutez un membre.</span><span class="sxs-lookup"><span data-stu-id="fa3f4-107">You must have a minimum of **Update** permission to the leaf model object for the entity you are adding a member to.</span></span>  
  
### <a name="to-create-a-leaf-member"></a><span data-ttu-id="fa3f4-108">Pour créer un membre feuille</span><span class="sxs-lookup"><span data-stu-id="fa3f4-108">To create a leaf member</span></span>  
  
1.  <span data-ttu-id="fa3f4-109">Dans la page d'accueil de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="fa3f4-109">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="fa3f4-110">Si vous êtes un utilisateur, sélectionnez une version ouverte dans la liste **Version** .</span><span class="sxs-lookup"><span data-stu-id="fa3f4-110">If you are a user, select an open version from the **Version** list.</span></span> <span data-ttu-id="fa3f4-111">Si vous êtes un administrateur, sélectionnez une version avec l'état ouvert ou verrouillé dans la liste **Version** .</span><span class="sxs-lookup"><span data-stu-id="fa3f4-111">If you are an administrator, select a version with open or locked status from the **Version** list.</span></span>  
  
3.  <span data-ttu-id="fa3f4-112">Cliquez sur **Explorateur**.</span><span class="sxs-lookup"><span data-stu-id="fa3f4-112">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="fa3f4-113">Dans la barre de menus, pointez sur **Entités** , puis cliquez sur le nom de l'entité à laquelle vous souhaitez ajouter un membre.</span><span class="sxs-lookup"><span data-stu-id="fa3f4-113">From the menu bar, point to **Entities** and click the name of the entity you want to add a member to.</span></span>  
  
5.  <span data-ttu-id="fa3f4-114">Cliquez sur **Ajouter un membre**.</span><span class="sxs-lookup"><span data-stu-id="fa3f4-114">Click **Add member**.</span></span>  
  
6.  <span data-ttu-id="fa3f4-115">Dans le volet **Détails** , renseignez les champs.</span><span class="sxs-lookup"><span data-stu-id="fa3f4-115">In the **Details** pane, complete the fields.</span></span>  
  
7.  <span data-ttu-id="fa3f4-116">facultatif.</span><span class="sxs-lookup"><span data-stu-id="fa3f4-116">Optional.</span></span> <span data-ttu-id="fa3f4-117">Dans la zone **Annotations** , tapez un commentaire pour expliquer l'ajout du membre.</span><span class="sxs-lookup"><span data-stu-id="fa3f4-117">In the **Annotations** box, type a comment about why the member was added.</span></span> <span data-ttu-id="fa3f4-118">Tous les utilisateurs ayant accès au membre peuvent afficher l'annotation.</span><span class="sxs-lookup"><span data-stu-id="fa3f4-118">All users who have access to the member can view the annotation.</span></span>  
  
8.  <span data-ttu-id="fa3f4-119">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fa3f4-119">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa3f4-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fa3f4-120">See Also</span></span>  
 <span data-ttu-id="fa3f4-121">[Charger ou mettre à jour des membres dans Master Data Services à l’aide du processus de site](add-update-and-delete-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="fa3f4-121">[Load or Update Members in Master Data Services by Using the Staging Process](add-update-and-delete-data-master-data-services.md) </span></span>  
 <span data-ttu-id="fa3f4-122">[Créer un membre consolidé &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-consolidated-member-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="fa3f4-122">[Create a Consolidated Member &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-consolidated-member-master-data-services.md) </span></span>  
 [<span data-ttu-id="fa3f4-123">Membres &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="fa3f4-123">Members &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/members-master-data-services.md)  
  
  
