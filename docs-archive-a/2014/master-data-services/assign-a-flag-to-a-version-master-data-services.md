---
title: Affecter un indicateur à une version (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- version flags [Master Data Services], assigning flags
- versions [Master Data Services], assigning flags
ms.assetid: 6629ec7e-32e7-4a1e-8b31-eb43c5923766
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 2de0d0d8d8ea96814e13b9123fe4fcd4782d6bef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614146"
---
# <a name="assign-a-flag-to-a-version-master-data-services"></a><span data-ttu-id="1262c-102">Affecter un indicateur à une version (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="1262c-102">Assign a Flag to a Version (Master Data Services)</span></span>
  <span data-ttu-id="1262c-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], affectez un indicateur à une version pour indiquer la version que les utilisateurs ou les systèmes d'abonnement doivent utiliser.</span><span class="sxs-lookup"><span data-stu-id="1262c-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], assign a flag to a version to indicate the version that users or subscribing systems should use.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1262c-104">Les indicateurs de version ne peuvent être affectés qu'à une seule version à la fois.</span><span class="sxs-lookup"><span data-stu-id="1262c-104">Version flags can be assigned to only one version at a time.</span></span> <span data-ttu-id="1262c-105">Si vous affectez un indicateur qui est déjà affecté à une autre version, l'indicateur est déplacé vers la version que vous avez sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1262c-105">If you assign a flag that is already assigned to another version, the flag is moved to the version you selected.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1262c-106">Prérequis</span><span class="sxs-lookup"><span data-stu-id="1262c-106">Prerequisites</span></span>  
 <span data-ttu-id="1262c-107">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="1262c-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="1262c-108">Vous devez avoir l’autorisation d’accéder à la zone fonctionnelle **Gestion des versions** .</span><span class="sxs-lookup"><span data-stu-id="1262c-108">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="1262c-109">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="1262c-109">You must be a model administrator.</span></span> <span data-ttu-id="1262c-110">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="1262c-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="1262c-111">Vous devez créer un indicateur de version avant de l'affecter.</span><span class="sxs-lookup"><span data-stu-id="1262c-111">You must have created a version flag to assign.</span></span> <span data-ttu-id="1262c-112">Pour plus d’informations, consultez [Créer un indicateur de version &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-version-flag-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="1262c-112">For more information, see [Create a Version Flag &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-version-flag-master-data-services.md).</span></span>  
  
### <a name="to-assign-a-flag-to-a-version"></a><span data-ttu-id="1262c-113">Pour affecter un indicateur à une version</span><span class="sxs-lookup"><span data-stu-id="1262c-113">To assign a flag to a version</span></span>  
  
1.  <span data-ttu-id="1262c-114">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Gestion des versions**.</span><span class="sxs-lookup"><span data-stu-id="1262c-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="1262c-115">Dans la page **Gérer les versions** , dans la ligne correspondant à la version à laquelle vous souhaitez affecter un indicateur, double-cliquez sur la cellule dans la colonne **Indicateur** .</span><span class="sxs-lookup"><span data-stu-id="1262c-115">On the **Manage Versions** page, in the row for the version to which you want to assign a flag, double-click the cell in the **Flag** column.</span></span>  
  
3.  <span data-ttu-id="1262c-116">Dans la liste, sélectionnez l'indicateur à affecter.</span><span class="sxs-lookup"><span data-stu-id="1262c-116">From the list, select the flag you want to assign.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1262c-117">Si l’indicateur n’est pas disponible, il se peut qu’il soit uniquement disponible pour les versions dont l’état est **Activé** .</span><span class="sxs-lookup"><span data-stu-id="1262c-117">If the flag you want is not available, the flag might be available for **Committed** versions only.</span></span> <span data-ttu-id="1262c-118">Pour le vérifier, allez à la page **Gérer les indicateurs de version** et recherchez l’indicateur dans le champ **Versions activées uniquement** .</span><span class="sxs-lookup"><span data-stu-id="1262c-118">To confirm, go to the **Manage Version Flags** page and view the **Committed Versions Only** field for the flag.</span></span>  
  
4.  <span data-ttu-id="1262c-119">Appuyez sur ENTRÉE pour enregistrer la modification.</span><span class="sxs-lookup"><span data-stu-id="1262c-119">Press ENTER to save the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1262c-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1262c-120">See Also</span></span>  
 <span data-ttu-id="1262c-121">[Créer un indicateur de version &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-version-flag-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="1262c-121">[Create a Version Flag &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-version-flag-master-data-services.md) </span></span>  
 [<span data-ttu-id="1262c-122">Versions &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1262c-122">Versions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/versions-master-data-services.md)  
  
  
