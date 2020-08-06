---
title: Publier des données d’Excel dans MDS (Complément MDS pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 89fce454-a816-4b33-a26a-d1b9741d269b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 597a954760816d8938628974998fe8f6daad1af5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612989"
---
# <a name="publish-data-from-excel-to-mds-mds-add-in-for-excel"></a><span data-ttu-id="87501-102">Publier des données d'Excel dans MDS (Complément MDS pour Excel)</span><span class="sxs-lookup"><span data-stu-id="87501-102">Publish Data from Excel to MDS (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="87501-103">Dans [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], vous pouvez publier les données dans le référentiel MDS quand vous avez fini de travailler dans Excel et souhaitez enregistrer vos modifications afin que d’autres utilisateurs puissent y accéder.</span><span class="sxs-lookup"><span data-stu-id="87501-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], publish data to the MDS repository when you are finished working in Excel and want to save your changes so other users have access to them.</span></span>  
  
> [!NOTE]
>  -   <span data-ttu-id="87501-104">Lorsque vous publiez des modifications, les commentaires sur les cellules managées MDS sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="87501-104">When you publish changes, comments on MDS-managed cells are deleted.</span></span>  
> -   <span data-ttu-id="87501-105">Une formule n'est pas prise en charge dans une cellule managée MDS.</span><span class="sxs-lookup"><span data-stu-id="87501-105">A formula is not supported in an MDS-managed cell.</span></span> <span data-ttu-id="87501-106">Une formule dans une cellule managée MDS est traitée comme valeur de texte.</span><span class="sxs-lookup"><span data-stu-id="87501-106">A formula in an MDS-managed cell is handled as a text value.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="87501-107">Prérequis</span><span class="sxs-lookup"><span data-stu-id="87501-107">Prerequisites</span></span>  
 <span data-ttu-id="87501-108">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="87501-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="87501-109">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Explorateur** .</span><span class="sxs-lookup"><span data-stu-id="87501-109">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="87501-110">La feuille de calcul active doit contenir des données managées MDS et vous devez avoir apporté des modifications ou effectué des ajouts à ces données.</span><span class="sxs-lookup"><span data-stu-id="87501-110">The active worksheet must contain MDS-managed data and you must have made changes or additions to the MDS-managed data.</span></span>  
  
-   <span data-ttu-id="87501-111">Si vous ajoutez des membres, vous ne devez pas spécifier de valeur **Code** si les codes de l'entité sont générés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="87501-111">If you are adding members, you do not have to specify a **Code** value if codes for the entity are being automatically generated.</span></span> <span data-ttu-id="87501-112">Pour plus d’informations, consultez [création automatique de Code &#40;Master Data Services&#41;](../automatic-code-creation-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="87501-112">For more information, see [Automatic Code Creation &#40;Master Data Services&#41;](../automatic-code-creation-master-data-services.md).</span></span>  
  
### <a name="to-publish-data-to-the-mds-repository"></a><span data-ttu-id="87501-113">Pour publier des données dans le référentiel MDS</span><span class="sxs-lookup"><span data-stu-id="87501-113">To publish data to the MDS repository</span></span>  
  
1.  <span data-ttu-id="87501-114">Dans le groupe **Publier et valider** , cliquez sur **Publier**.</span><span class="sxs-lookup"><span data-stu-id="87501-114">In the **Publish and Validate** group, click **Publish**.</span></span>  
  
2.  <span data-ttu-id="87501-115">facultatif.</span><span class="sxs-lookup"><span data-stu-id="87501-115">Optional.</span></span> <span data-ttu-id="87501-116">Si la boîte de dialogue **Publier et annoter** s’affiche, choisissez de partager la même annotation (commentaire) pour toutes les mises à jour, ou d’annoter chaque modification individuellement.</span><span class="sxs-lookup"><span data-stu-id="87501-116">If the **Publish and Annotate** dialog box is displayed, choose to share the same annotation (comment) for all updates, or to annotate each change individually.</span></span>  
  
3.  <span data-ttu-id="87501-117">facultatif.</span><span class="sxs-lookup"><span data-stu-id="87501-117">Optional.</span></span> <span data-ttu-id="87501-118">Activez la case à cocher **Ne plus afficher cette boîte de dialogue** .</span><span class="sxs-lookup"><span data-stu-id="87501-118">Select the **Do not show this dialog box again** check box.</span></span> <span data-ttu-id="87501-119">Vous pouvez toujours afficher la boîte de dialogue ultérieurement en choisissant **Paramètres** et en sélectionnant la case à cocher **Afficher la boîte de dialogue Publier et annoter lors de la publication** .</span><span class="sxs-lookup"><span data-stu-id="87501-119">You can always show the dialog box in the future by choosing **Settings** and selecting the **Show Publish and Annotate dialog box when publishing** check box.</span></span>  
  
4.  <span data-ttu-id="87501-120">Cliquez sur **Publier**.</span><span class="sxs-lookup"><span data-stu-id="87501-120">Click **Publish**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="87501-121">Si vous ajoutez de nouveaux membres (lignes) dans votre feuille de calcul et vous n’arrivez pas à les publier correctement sur le référentiel MDS, il est possible que vous n’ayez pas l’autorisation **Mettre à jour** sur tous les attributs dans la feuille de calcul.</span><span class="sxs-lookup"><span data-stu-id="87501-121">If you are adding new members (rows) to your worksheet and you cannot successfully publish them to the MDS repository, you may not have **Update** permission to all of the attributes in the worksheet.</span></span> <span data-ttu-id="87501-122">Sur l'onglet **Révision** , dans le groupe **Modifications** , cliquez sur **Ôter la protection de la feuille** et réessayez de publier à nouveau.</span><span class="sxs-lookup"><span data-stu-id="87501-122">On the **Review** tab, in the **Changes** group, click **Unprotect Sheet** and try to publish again.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="87501-123">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="87501-123">Next Steps</span></span>  
 [<span data-ttu-id="87501-124">Appliquer des règles d’entreprise &#40;Complément MDS pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="87501-124">Apply Business Rules &#40;MDS Add-in for Excel&#41;</span></span>](apply-business-rules-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="87501-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="87501-125">See Also</span></span>  
 <span data-ttu-id="87501-126">[Publication des Complément MDS pour Excel de &#40;de données&#41;](overview-importing-data-from-excel-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="87501-126">[Publishing Data &#40;MDS Add-in for Excel&#41;](overview-importing-data-from-excel-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="87501-127">Validation des données &#40;Complément MDS pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="87501-127">Validating Data &#40;MDS Add-in for Excel&#41;</span></span>](validating-data-mds-add-in-for-excel.md)  
  
  
