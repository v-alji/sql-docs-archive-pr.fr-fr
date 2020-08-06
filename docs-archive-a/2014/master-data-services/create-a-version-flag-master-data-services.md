---
title: Créer un indicateur de version (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating version flags [Master Data Services]
- version flags [Master Data Services], creating
- versions [Master Data Services], creating flags
ms.assetid: 3067e1e3-05b7-4f11-9206-c612ef4e7e42
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f04c93f8315ccd5b53e07db169783da53afe0156
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611843"
---
# <a name="create-a-version-flag-master-data-services"></a><span data-ttu-id="54c17-102">Créer un indicateur de version (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="54c17-102">Create a Version Flag (Master Data Services)</span></span>
  <span data-ttu-id="54c17-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], créez un indicateur de version à affecter à une version.</span><span class="sxs-lookup"><span data-stu-id="54c17-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a version flag to assign to a version.</span></span> <span data-ttu-id="54c17-104">L’indicateur peut spécifier la version que les utilisateurs ou les systèmes d’abonnement doivent utiliser.</span><span class="sxs-lookup"><span data-stu-id="54c17-104">The flag can indicate the version that users or subscribing systems should use.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="54c17-105">Prérequis</span><span class="sxs-lookup"><span data-stu-id="54c17-105">Prerequisites</span></span>  
 <span data-ttu-id="54c17-106">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="54c17-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="54c17-107">Vous devez avoir l’autorisation d’accéder à la zone fonctionnelle **Gestion des versions** .</span><span class="sxs-lookup"><span data-stu-id="54c17-107">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="54c17-108">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="54c17-108">You must be a model administrator.</span></span> <span data-ttu-id="54c17-109">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="54c17-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-version-flag"></a><span data-ttu-id="54c17-110">Pour créer un indicateur de version</span><span class="sxs-lookup"><span data-stu-id="54c17-110">To create a version flag</span></span>  
  
1.  <span data-ttu-id="54c17-111">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Gestion des versions**.</span><span class="sxs-lookup"><span data-stu-id="54c17-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="54c17-112">Dans la page **Gérer les versions** , dans la barre de menus, pointez sur **Gérer** , puis cliquez sur **Indicateurs**.</span><span class="sxs-lookup"><span data-stu-id="54c17-112">On the **Manage Versions** page, from the menu bar, point to **Manage** and then click **Flags**.</span></span>  
  
3.  <span data-ttu-id="54c17-113">Dans la page **Gérer les indicateurs de version** , dans le champ **Modèle** , sélectionnez le modèle pour lequel vous souhaitez créer un indicateur.</span><span class="sxs-lookup"><span data-stu-id="54c17-113">On the **Manage Version Flags** page, from the **Model** field, select the model for which you want to create a flag.</span></span>  
  
4.  <span data-ttu-id="54c17-114">Cliquez sur **Add**.</span><span class="sxs-lookup"><span data-stu-id="54c17-114">Click **Add**.</span></span>  
  
5.  <span data-ttu-id="54c17-115">Renseignez la zone **Nom** .</span><span class="sxs-lookup"><span data-stu-id="54c17-115">In the **Name** box, type a name.</span></span>  
  
6.  <span data-ttu-id="54c17-116">Dans la zone **Description**, tapez une description.</span><span class="sxs-lookup"><span data-stu-id="54c17-116">In the **Description** box, type a description.</span></span>  
  
7.  <span data-ttu-id="54c17-117">Dans le champ **Versions activées uniquement** , sélectionnez **True** pour spécifier que l’indicateur ne peut être affecté qu’aux versions présentant l’état **Activé** .</span><span class="sxs-lookup"><span data-stu-id="54c17-117">In the **Committed Versions Only** field, select **True** to indicate that the flag can be assigned to versions with a status of **Committed** only.</span></span> <span data-ttu-id="54c17-118">Sélectionnez **False** pour indiquer que l’indicateur peut être affecté aux versions présentant n’importe quel état.</span><span class="sxs-lookup"><span data-stu-id="54c17-118">Select **False** to indicate that the flag can be assigned to versions with any status.</span></span>  
  
8.  <span data-ttu-id="54c17-119">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="54c17-119">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="54c17-120">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="54c17-120">Next Steps</span></span>  
  
-   [<span data-ttu-id="54c17-121">Affecter un indicateur à une version &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="54c17-121">Assign a Flag to a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-a-flag-to-a-version-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="54c17-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="54c17-122">See Also</span></span>  
 <span data-ttu-id="54c17-123">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="54c17-123">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span></span>  
 [<span data-ttu-id="54c17-124">Modifier le nom d’un indicateur de version &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="54c17-124">Change a Version Flag Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-a-version-flag-name-master-data-services.md)  
  
  
