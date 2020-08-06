---
title: Planifier les stratégies | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 59417a54-55f1-4468-ba41-368aa852c2d4
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 1bce1b9d650606e9485899c34c72ca6b27a72dae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704440"
---
# <a name="schedule-the-policies"></a><span data-ttu-id="a2605-102">Planifier les stratégies</span><span class="sxs-lookup"><span data-stu-id="a2605-102">Schedule the Policies</span></span>
  <span data-ttu-id="a2605-103">Dans cette tâche, vous planifierez les stratégies des meilleures pratiques que vous avez importées dans la tâche précédente.</span><span class="sxs-lookup"><span data-stu-id="a2605-103">In this task, you will schedule the best practices policies that you imported in the previous task.</span></span>  
  
### <a name="to-schedule-the-best-practices-policies"></a><span data-ttu-id="a2605-104">Pour planifier les stratégies des meilleures pratiques</span><span class="sxs-lookup"><span data-stu-id="a2605-104">To schedule the best practices policies</span></span>  
  
1.  <span data-ttu-id="a2605-105">Dans l’Explorateur d’objets, développez **gestion**, gestion de la **stratégie**, **stratégies**, cliquez avec le bouton droit sur une stratégie des meilleures pratiques, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="a2605-105">In Object Explorer, expand **Management**, expand **Policy Management**, expand **Policies**, right-click a best practices policy, and then click **Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a2605-106">En guise d’alternative, pour identifier facilement les stratégies associées aux meilleures pratiques et trier les catégories des meilleures pratiques, développez **gestion**, gestion de la **stratégie**, puis cliquez sur **stratégies**.</span><span class="sxs-lookup"><span data-stu-id="a2605-106">As an alternative, to easily see which policies are associated with best practices and to sort the best practices categories, expand **Management**, expand **Policy Management**, and then click **Policies**.</span></span> <span data-ttu-id="a2605-107">Dans le menu **Affichage** , cliquez sur **Détails de l’Explorateur d’objets**.</span><span class="sxs-lookup"><span data-stu-id="a2605-107">On the **View** menu, click **Object Explorer Details**.</span></span> <span data-ttu-id="a2605-108">Dans le volet Détails de l' **Explorateur d’objets** , cliquez sur l’en-tête **catégorie** pour trier les stratégies par catégorie.</span><span class="sxs-lookup"><span data-stu-id="a2605-108">In the **Object Explorer Details** pane, click the **Category** heading to sort the policies by category.</span></span> <span data-ttu-id="a2605-109">Les stratégies des meilleures pratiques ont le préfixe **Microsoft Best Practices**.</span><span class="sxs-lookup"><span data-stu-id="a2605-109">The best practices policies have the prefix **Microsoft Best Practices**.</span></span> <span data-ttu-id="a2605-110">Cliquez avec le bouton droit sur la stratégie que vous souhaitez configurer, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="a2605-110">Right-click the policy that you want to configure, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="a2605-111">Sur la page **général** de la boîte de dialogue **ouvrir une stratégie** , dans la liste mode d' **évaluation** , cliquez sur **planification**.</span><span class="sxs-lookup"><span data-stu-id="a2605-111">On the **General** page of the **Open Policy** dialog box, in the **Evaluation Mode** list, click **On schedule**.</span></span>  
  
3.  <span data-ttu-id="a2605-112">En regard de la zone **planification** , cliquez sur **choisir** pour spécifier une planification existante ou sur **nouveau** pour créer une planification.</span><span class="sxs-lookup"><span data-stu-id="a2605-112">Next to the **Schedule** box, click **Pick** to specify an existing schedule, or click **New** to create a new schedule.</span></span>  
  
4.  <span data-ttu-id="a2605-113">Une fois que vous avez configuré une planification, vous pouvez activer la case à cocher **activé** vers le haut de la page pour activer la stratégie planifiée.</span><span class="sxs-lookup"><span data-stu-id="a2605-113">After you have configured a schedule, you can select the **Enabled** check box near the top of the page to enable the scheduled policy.</span></span>  
  
5.  <span data-ttu-id="a2605-114">Répétez les étapes 1 à 4 pour chaque stratégie à planifier.</span><span class="sxs-lookup"><span data-stu-id="a2605-114">Repeats steps 1 through 4 for each policy that you want to schedule.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a2605-115">Pour afficher les résultats d'évaluation après l'exécution d'une stratégie planifiée, ouvrez le journal Historique de la stratégie sur l'instance cible.</span><span class="sxs-lookup"><span data-stu-id="a2605-115">To view the evaluation results after a scheduled policy runs, open the Policy History log on the target instance.</span></span> <span data-ttu-id="a2605-116">Pour ouvrir le journal, cliquez avec le bouton droit sur **gestion des stratégies**, puis cliquez sur **afficher l’historique**.</span><span class="sxs-lookup"><span data-stu-id="a2605-116">To open the log, right-click **Policy Management**, and then click **View History**.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="a2605-117">Résumé</span><span class="sxs-lookup"><span data-stu-id="a2605-117">Summary</span></span>  
 <span data-ttu-id="a2605-118">Vous avez configuré l'exécution de stratégies planifiées sur une instance unique de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2605-118">You configured scheduled policies to run on a single instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a2605-119">Si vous souhaitez déployer des stratégies planifiées vers plusieurs instances, passez à la tâche suivante dans ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="a2605-119">If you want to deploy scheduled policies to multiple instances, continue to the next task in this tutorial.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a2605-120">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="a2605-120">Next Steps</span></span>  
 [<span data-ttu-id="a2605-121">Déployer des stratégies planifiées sur plusieurs instances</span><span class="sxs-lookup"><span data-stu-id="a2605-121">Deploy Scheduled Policies to Multiple Instances</span></span>](../../2014/tutorials/deploy-scheduled-policies-to-multiple-instances.md)  
  
  
