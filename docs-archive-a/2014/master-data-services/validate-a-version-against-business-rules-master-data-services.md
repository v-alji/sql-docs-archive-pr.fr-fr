---
title: Valider une version par rapport aux règles d’entreprise (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- validating versions [Master Data Services]
- validating versions [Master Data Services], about validating versions
- versions [Master Data Services], validating
- business rules [Master Data Services], applying to all members
ms.assetid: 5aee7901-6d05-41d4-8bbb-c6f26791d1df
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 085fa071ca511c9d838c140547419bf87fb857bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604608"
---
# <a name="validate-a-version-against-business-rules-master-data-services"></a><span data-ttu-id="d5a31-102">Valider une version par rapport aux règles d'entreprise (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d5a31-102">Validate a Version against Business Rules (Master Data Services)</span></span>
  <span data-ttu-id="d5a31-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], validez une version pour appliquer des règles d’entreprise à tous les membres dans la version de modèle.</span><span class="sxs-lookup"><span data-stu-id="d5a31-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], validate a version to apply business rules to all members in the model version.</span></span>  
  
 <span data-ttu-id="d5a31-104">Cette procédure explique comment utiliser l’application web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] pour valider les données.</span><span class="sxs-lookup"><span data-stu-id="d5a31-104">This procedure explains how to use the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application to validate data.</span></span> <span data-ttu-id="d5a31-105">Si vous avez l'autorisation dans la base de données MDS, vous pouvez utiliser une procédure stockée à la place.</span><span class="sxs-lookup"><span data-stu-id="d5a31-105">If you have permission in the MDS database, you can use a stored procedure instead.</span></span> <span data-ttu-id="d5a31-106">Pour plus d’informations, consultez [Procédure stockée de validation &#40;Master Data Services&#41;](validation-stored-procedure-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d5a31-106">For more information, see [Validation Stored Procedure &#40;Master Data Services&#41;](validation-stored-procedure-master-data-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d5a31-107">Tous les membres doivent passer la validation avant qu'une version puisse être validée.</span><span class="sxs-lookup"><span data-stu-id="d5a31-107">All members must pass validation before a version can be committed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d5a31-108">Prérequis</span><span class="sxs-lookup"><span data-stu-id="d5a31-108">Prerequisites</span></span>  
 <span data-ttu-id="d5a31-109">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="d5a31-109">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="d5a31-110">Vous devez avoir l’autorisation d’accéder à la zone fonctionnelle **Gestion des versions** .</span><span class="sxs-lookup"><span data-stu-id="d5a31-110">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="d5a31-111">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="d5a31-111">You must be a model administrator.</span></span> <span data-ttu-id="d5a31-112">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d5a31-112">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="d5a31-113">L’état de la version doit être **Ouvert** ou **Verrouillé**.</span><span class="sxs-lookup"><span data-stu-id="d5a31-113">The version's status must be **Open** or **Locked**.</span></span>  
  
-   <span data-ttu-id="d5a31-114">Dans la page **Valider les versions** , les membres doivent exister avec un état autre que **Validation réussie**.</span><span class="sxs-lookup"><span data-stu-id="d5a31-114">On the **Validate Versions** page, members must exist with a status other than **Validation succeeded**.</span></span>  
  
### <a name="to-validate-a-version"></a><span data-ttu-id="d5a31-115">Pour valider une version</span><span class="sxs-lookup"><span data-stu-id="d5a31-115">To validate a version</span></span>  
  
1.  <span data-ttu-id="d5a31-116">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Gestion des versions**.</span><span class="sxs-lookup"><span data-stu-id="d5a31-116">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="d5a31-117">Dans la page **Gérer les versions** , dans la barre de menus, cliquez sur **Valider la version**.</span><span class="sxs-lookup"><span data-stu-id="d5a31-117">On the **Manage Versions** page, from the menu bar, click **Validate Version**.</span></span>  
  
3.  <span data-ttu-id="d5a31-118">Dans la page **Valider les versions** , sélectionnez le modèle et la version à valider.</span><span class="sxs-lookup"><span data-stu-id="d5a31-118">On the **Validate Versions** page, select the model and version you want to validate.</span></span>  
  
4.  <span data-ttu-id="d5a31-119">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="d5a31-119">Click **Validate**.</span></span>  
  
5.  <span data-ttu-id="d5a31-120">Dans la boîte de dialogue de confirmation, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5a31-120">In the confirmation dialog box, click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d5a31-121">Lorsque l'indicateur de progression n'est plus affiché, la validation de la version est terminée.</span><span class="sxs-lookup"><span data-stu-id="d5a31-121">When the progress indicator is no longer displayed, the version has finished validation.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d5a31-122">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="d5a31-122">Next Steps</span></span>  
  
-   [<span data-ttu-id="d5a31-123">Verrouiller une version &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d5a31-123">Lock a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/lock-a-version-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="d5a31-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d5a31-124">See Also</span></span>  
 <span data-ttu-id="d5a31-125">[États de validation &#40;Master Data Services&#41;](../../2014/master-data-services/validation-statuses-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d5a31-125">[Validation Statuses &#40;Master Data Services&#41;](../../2014/master-data-services/validation-statuses-master-data-services.md) </span></span>  
 <span data-ttu-id="d5a31-126">[&#40;de la procédure stockée de validation Master Data Services&#41;](validation-stored-procedure-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d5a31-126">[Validation Stored Procedure &#40;Master Data Services&#41;](validation-stored-procedure-master-data-services.md) </span></span>  
 <span data-ttu-id="d5a31-127">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d5a31-127">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span></span>  
 <span data-ttu-id="d5a31-128">[&#40;des règles d’entreprise Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d5a31-128">[Business Rules &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span></span>  
 [<span data-ttu-id="d5a31-129">Valider des membres spécifiques par rapport aux règles d’entreprise &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d5a31-129">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
  
