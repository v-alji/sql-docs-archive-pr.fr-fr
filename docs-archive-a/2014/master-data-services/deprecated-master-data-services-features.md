---
title: Fonctionnalités de Master Data Services dépréciées dans SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: d8506bda-66dd-45a4-bfc9-3a10fa665acc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ce532e9f407ec475f7e59c0d79659265a9e0bf3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695768"
---
# <a name="deprecated-master-data-services-features-in-sql-server-2014"></a><span data-ttu-id="6aba0-102">Fonctionnalités Master Data Services déconseillées dans SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="6aba0-102">Deprecated Master Data Services Features in SQL Server 2014</span></span>
  <span data-ttu-id="6aba0-103">Cette rubrique décrit les fonctionnalités [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] déconseillées qui sont toujours disponibles dans [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6aba0-103">This topic describes the deprecated [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] features that are still available in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="6aba0-104">Il est prévu que ces fonctionnalités soient supprimées dans une prochaine version de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6aba0-104">These features are scheduled to be removed in a future release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6aba0-105">Les fonctions déconseillées ne doivent pas être utilisées dans de nouvelles applications.</span><span class="sxs-lookup"><span data-stu-id="6aba0-105">Deprecated features should not be used in new applications.</span></span>  
  
## <a name="staging-process"></a><span data-ttu-id="6aba0-106">Processus de site</span><span class="sxs-lookup"><span data-stu-id="6aba0-106">Staging Process</span></span>  
 <span data-ttu-id="6aba0-107">Le processus de site utilisé dans [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] n'est plus disponible dans l'application Web de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] ; toutefois il l'est encore dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6aba0-107">The staging process that was used in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] is no longer available in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application; however it is still available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="6aba0-108">Les erreurs du processus de site de [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] ne sont plus affichées dans l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6aba0-108">Staging errors from the [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] staging process are no longer displayed in the UI.</span></span> <span data-ttu-id="6aba0-109">Les codes d’erreur qui sont remplis pendant le processus de site sont toujours disponibles dans les tables de mise en lots et se trouvent ici : [https://msdn.microsoft.com/library/ff487022.aspx](https://msdn.microsoft.com/library/ff487022.aspx) .</span><span class="sxs-lookup"><span data-stu-id="6aba0-109">Error codes that are populated during the staging process are still available in the staging tables, and can be found here: [https://msdn.microsoft.com/library/ff487022.aspx](https://msdn.microsoft.com/library/ff487022.aspx).</span></span>  
  
 <span data-ttu-id="6aba0-110">Les tables de mise en lots (tblStgMember, tblStgMemberAttribute et tblStgRelationship) sont toujours disponibles dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="6aba0-110">The staging tables (tblStgMember, tblStgMemberAttribute, and tblStgRelationship) are still available in the database.</span></span> <span data-ttu-id="6aba0-111">La procédure stockée utilisée pour initialiser le processus de site (mdm.udpStagingSweep) est encore disponible dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="6aba0-111">The stored procedure used to initiate the staging process (mdm.udpStagingSweep) is still available in the database.</span></span>  
  
 <span data-ttu-id="6aba0-112">Les méthodes de service Web qui appellent le processus de site sont toujours disponibles.</span><span class="sxs-lookup"><span data-stu-id="6aba0-112">The web service methods that call the staging process are still available.</span></span>  
  
 <span data-ttu-id="6aba0-113">L'intervalle de mise en lots défini dans [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] s'applique au processus de site dans [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] et [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6aba0-113">The staging interval set in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] applies to the staging process in both [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] and [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="6aba0-114">Un nouveau processus de site plus performant a été implémenté dans [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6aba0-114">A new, higher performance staging process has been implemented in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="6aba0-115">Pour plus d’informations, consultez [Importation de données &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6aba0-115">For more information, see [Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md).</span></span>  
  
## <a name="metadata"></a><span data-ttu-id="6aba0-116">Métadonnées</span><span class="sxs-lookup"><span data-stu-id="6aba0-116">Metadata</span></span>  
 <span data-ttu-id="6aba0-117">Bien que le modèle de métadonnées soit toujours affiché dans l'application Web de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], il ne doit pas être utilisé.</span><span class="sxs-lookup"><span data-stu-id="6aba0-117">Though the Metadata model is still displayed in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application, it should not be used.</span></span> <span data-ttu-id="6aba0-118">Elle sera supprimée dans une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="6aba0-118">It will be removed in a future release.</span></span> <span data-ttu-id="6aba0-119">Les utilisateurs ne peuvent plus afficher les métadonnées dans la zone fonctionnelle **Explorateur** et vous ne pouvez plus créer de versions du modèle de métadonnées.</span><span class="sxs-lookup"><span data-stu-id="6aba0-119">Users can also no longer view metadata in the **Explorer** functional area, and you can no longer create versions of the Metadata model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aba0-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6aba0-120">See Also</span></span>  
 [<span data-ttu-id="6aba0-121">Fonctionnalités Master Data Services supprimées dans SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="6aba0-121">Discontinued Master Data Services Features in SQL Server 2014</span></span>](discontinued-master-data-services-features.md)  
  
  
