---
title: Afficher les erreurs qui se produisent pendant le processus de site (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- staging process [Master Data Services], viewing errors
ms.assetid: 6d2bff84-624b-47fc-a4a5-d9ea01d13412
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3b39d039b29090f3021c764126ebb782ce25cbfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699876"
---
# <a name="view-errors-that-occur-during-the-staging-process-master-data-services"></a><span data-ttu-id="968f7-102">Afficher les erreurs qui se produisent pendant le processus de site (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="968f7-102">View Errors that Occur During the Staging Process (Master Data Services)</span></span>
  <span data-ttu-id="968f7-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], vous pouvez consulter les erreurs qui se produisent pendant le processus de site.</span><span class="sxs-lookup"><span data-stu-id="968f7-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can view errors that occur during the staging process.</span></span> <span data-ttu-id="968f7-104">La base de données [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] comporte deux vues pour afficher les erreurs :</span><span class="sxs-lookup"><span data-stu-id="968f7-104">In the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database, there are two views that show errors:</span></span>  
  
-   <span data-ttu-id="968f7-105">stg.viw_name_MemberErrorDetails pour les mises à jour de membre feuille ou consolidé.</span><span class="sxs-lookup"><span data-stu-id="968f7-105">stg.viw_name_MemberErrorDetails for leaf or consolidated member updates.</span></span>  
  
-   <span data-ttu-id="968f7-106">stg.viw_name_RelationshipErrorDetails pour les mises à jour de relation de hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="968f7-106">stg.viw_name_RelationshipErrorDetails for hierarchy relationship updates.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="968f7-107">Prérequis</span><span class="sxs-lookup"><span data-stu-id="968f7-107">Prerequisites</span></span>  
 <span data-ttu-id="968f7-108">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="968f7-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="968f7-109">Dans la base de données [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] , vous devez disposer des autorisations SELECT sur la vue stg.viw_name_MemberErrorDetails ou stg.viw_name_RelationshipErrorDetails.</span><span class="sxs-lookup"><span data-stu-id="968f7-109">In the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database, you must have SELECT permissions to either the stg.viw_name_MemberErrorDetails or stg.viw_name_RelationshipErrorDetails view.</span></span>  
  
-   <span data-ttu-id="968f7-110">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="968f7-110">You must be a model administrator.</span></span> <span data-ttu-id="968f7-111">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="968f7-111">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-view-staging-errors"></a><span data-ttu-id="968f7-112">Pour afficher des erreurs de mise en lots</span><span class="sxs-lookup"><span data-stu-id="968f7-112">To view staging errors</span></span>  
  
1.  <span data-ttu-id="968f7-113">Ouvrez [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] et connectez-vous à l’instance [!INCLUDE[ssDE](../includes/ssde-md.md)] pour votre base de données [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="968f7-113">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] instance for your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="968f7-114">Ouvrez une nouvelle requête.</span><span class="sxs-lookup"><span data-stu-id="968f7-114">Open a new query.</span></span>  
  
3.  <span data-ttu-id="968f7-115">Tapez le texte suivant, en remplaçant « name » par le nom de votre table de mise en lots, par exemple, viw_Product_MemberErrorDetails.</span><span class="sxs-lookup"><span data-stu-id="968f7-115">Type the following text, replacing name with the name of your staging table, for example, viw_Product_MemberErrorDetails.</span></span>  
  
     `SELECT * FROM stg.viw_name_MemberErrorDetails`  
  
4.  <span data-ttu-id="968f7-116">Exécutez la requête.</span><span class="sxs-lookup"><span data-stu-id="968f7-116">Excecute the query.</span></span> <span data-ttu-id="968f7-117">Les détails des erreurs sont affichés dans le champ **ErrorDescription** .</span><span class="sxs-lookup"><span data-stu-id="968f7-117">Error details are displayed in the **ErrorDescription** field.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="968f7-118">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="968f7-118">Next Steps</span></span>  
 <span data-ttu-id="968f7-119">Pour plus d’informations sur les messages d’erreur, consultez [Erreurs du processus de mise en lots &#40;Master Data Services&#41;](../../2014/master-data-services/staging-process-errors-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="968f7-119">For more details on error messages, see [Staging Process Errors &#40;Master Data Services&#41;](../../2014/master-data-services/staging-process-errors-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="968f7-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="968f7-120">See Also</span></span>  
 <span data-ttu-id="968f7-121">[&#40;d’importation de données Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="968f7-121">[Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md) </span></span>  
 [<span data-ttu-id="968f7-122">Résolution des problèmes liés au processus de site (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="968f7-122">Troubleshooting the Staging Process (Master Data Services)</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/troubleshooting-the-staging-process-master-data-services.aspx)  
  
  
