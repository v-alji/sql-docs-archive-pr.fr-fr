---
title: Appliquer des règles d’entreprise (Complément MDS pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: cd106345-f561-4966-88d3-a69139b2bd78
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: aad5ce6bcebb635fa4659c32654d67406d4ba0dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698394"
---
# <a name="apply-business-rules-mds-add-in-for-excel"></a><span data-ttu-id="0d800-102">Appliquer des règles d'entreprise (Complément MDS pour Excel)</span><span class="sxs-lookup"><span data-stu-id="0d800-102">Apply Business Rules (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="0d800-103">Dans [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] , vous pouvez appliquer des règles d’entreprise quand vous souhaitez valider les données et confirmer leur validité.</span><span class="sxs-lookup"><span data-stu-id="0d800-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] apply business rules when you want to validate data and confirm that it is valid.</span></span> <span data-ttu-id="0d800-104">Vous pouvez corriger des validations et publier à nouveau les données.</span><span class="sxs-lookup"><span data-stu-id="0d800-104">You can correct validations and re-publish the data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0d800-105">La validation des données se produit automatiquement lorsque vous les publiez.</span><span class="sxs-lookup"><span data-stu-id="0d800-105">Data validation occurs automatically when you publish data.</span></span> <span data-ttu-id="0d800-106">Pour plus d’informations, consultez [Procédure stockée de validation &#40;Master Data Services&#41;](../validation-stored-procedure-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0d800-106">For more information, see [Validation Stored Procedure &#40;Master Data Services&#41;](../validation-stored-procedure-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0d800-107">Prérequis</span><span class="sxs-lookup"><span data-stu-id="0d800-107">Prerequisites</span></span>  
 <span data-ttu-id="0d800-108">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="0d800-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="0d800-109">Vous devez avoir accès à la zone fonctionnelle **Explorateur** .</span><span class="sxs-lookup"><span data-stu-id="0d800-109">You must have access to the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="0d800-110">Vous devez disposer d'une feuille de calcul active qui contient des données managées MDS.</span><span class="sxs-lookup"><span data-stu-id="0d800-110">You must have an active worksheet that contains MDS-managed data.</span></span>  
  
### <a name="to-apply-business-rules"></a><span data-ttu-id="0d800-111">Pour appliquer les règles d'entreprise</span><span class="sxs-lookup"><span data-stu-id="0d800-111">To apply business rules</span></span>  
  
1.  <span data-ttu-id="0d800-112">Dans le groupe **Publier et valider** , cliquez sur **Appliquer les règles**.</span><span class="sxs-lookup"><span data-stu-id="0d800-112">In the **Publish and Validate** group, click **Apply Rules**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0d800-113">Le nombre de membres (lignes) qui sont validés en même temps dépend d'un paramètre dans [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d800-113">The number of members (rows) that are validated at one time depends on a setting in [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span> <span data-ttu-id="0d800-114">Pour plus d’informations, consultez [Paramètres de règle d’entreprise](../system-settings-master-data-services.md#BusinessRules).</span><span class="sxs-lookup"><span data-stu-id="0d800-114">For more information, see [Business Rule Settings](../system-settings-master-data-services.md#BusinessRules).</span></span>  
  
2.  <span data-ttu-id="0d800-115">Les données sont validées par rapport aux règles d'entreprise et deux colonnes d'état sont affichées.</span><span class="sxs-lookup"><span data-stu-id="0d800-115">The data is validated against business rules and two status columns are displayed.</span></span> <span data-ttu-id="0d800-116">Si ces colonnes ne sont pas affichées automatiquement, dans le groupe **Publier et valider** , cliquez sur **Afficher l’état** .</span><span class="sxs-lookup"><span data-stu-id="0d800-116">If these columns are not displayed automatically, in the **Publish and Validate** group, click **Show Status** to view them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d800-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0d800-117">See Also</span></span>  
 [<span data-ttu-id="0d800-118">Publication des Complément MDS pour Excel de &#40;de données&#41;</span><span class="sxs-lookup"><span data-stu-id="0d800-118">Publishing Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-importing-data-from-excel-mds-add-in-for-excel.md)  
  
  
