---
title: Configurer un serveur pour exécuter la stratégie Désactivé par défaut | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 41c3022d-ab13-443e-ac64-ba1d64584f79
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c0842a30b7d0bbcd1b01ee9e98ed1ed9a74f0f35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601417"
---
# <a name="configure-a-server-to-run-the-off-by-default-policy"></a><span data-ttu-id="fd0a7-102">Configurer un serveur pour exécuter la stratégie Désactivé par défaut</span><span class="sxs-lookup"><span data-stu-id="fd0a7-102">Configure a Server to Run the Off By Default Policy</span></span>
  <span data-ttu-id="fd0a7-103">Vous disposez désormais d'une stratégie nommée Désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="fd0a7-103">Now you have a policy named Off By Default.</span></span> <span data-ttu-id="fd0a7-104">Dans cette tâche, vous allez vérifier si votre serveur est conforme aux spécifications de cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="fd0a7-104">In this task, you will check to see whether your server complies with the requirements of this policy.</span></span>  
  
### <a name="to-run-the-off-by-default-policy"></a><span data-ttu-id="fd0a7-105">Pour exécuter la stratégie Désactivé par défaut</span><span class="sxs-lookup"><span data-stu-id="fd0a7-105">To run the Off By Default policy</span></span>  
  
1.  <span data-ttu-id="fd0a7-106">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur votre instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], pointez sur **Stratégies**, puis cliquez sur **Évaluer**.</span><span class="sxs-lookup"><span data-stu-id="fd0a7-106">In Object Explorer, right-click your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], point to **Policies**, and then click **Evaluate**.</span></span>  
  
2.  <span data-ttu-id="fd0a7-107">Dans la boîte de dialogue **Évaluer les stratégies** , vous pouvez sélectionner des stratégies à partir d’une autre instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou d’un fichier.</span><span class="sxs-lookup"><span data-stu-id="fd0a7-107">In the **Evaluate Policies** dialog box you can select policies from another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or from a file.</span></span> <span data-ttu-id="fd0a7-108">Pour cette étape, laissez le paramètre **Source** défini à votre instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd0a7-108">For this step, leave **Source** set to your instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
3.  <span data-ttu-id="fd0a7-109">Dans la section **Stratégies** , sélectionnez la stratégie **Désactivé par défaut** .</span><span class="sxs-lookup"><span data-stu-id="fd0a7-109">In the **Policies** section, select the **Off By Default** policy.</span></span>  
  
4.  <span data-ttu-id="fd0a7-110">Pour voir si le serveur est conforme à la stratégie, cliquez sur **Évaluer**.</span><span class="sxs-lookup"><span data-stu-id="fd0a7-110">To see whether the server is in compliance with the policy, click **Evaluate**.</span></span>  
  
5.  <span data-ttu-id="fd0a7-111">Dans la zone **Résultats** , vous verrez un cercle vert avec une coche si le [!INCLUDE[ssDE](../../includes/ssde-md.md)] est conforme à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="fd0a7-111">In the **Results** area, you will see a green circle with a check mark if the [!INCLUDE[ssDE](../../includes/ssde-md.md)] complies with the policy.</span></span> <span data-ttu-id="fd0a7-112">Vous verrez un cercle rouge avec un X si le [!INCLUDE[ssDE](../../includes/ssde-md.md)] n'est pas conforme à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="fd0a7-112">You will see a red circle with an X if the [!INCLUDE[ssDE](../../includes/ssde-md.md)] does not comply with the policy.</span></span>  
  
6.  <span data-ttu-id="fd0a7-113">Dans la zone **Détails sur les cibles** , des informations supplémentaires apparaîtront dans la colonne **Message** si une erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="fd0a7-113">In the **Target Details** area, you will see additional information in the **Message** column if an error occurs.</span></span> <span data-ttu-id="fd0a7-114">Dans la colonne **Message** , cliquez sur **Afficher** pour voir un rapport contenant les résultats de la vérification de chaque propriété de facette.</span><span class="sxs-lookup"><span data-stu-id="fd0a7-114">In the **Message** column, click **View** to see a report that contains the results of the check for each facet property that was checked.</span></span>  
  
7.  <span data-ttu-id="fd0a7-115">La description de stratégie est affichée en bas de la page et la section **Aide supplémentaire** affiche le lien hypertexte que vous avez configuré pour la stratégie.</span><span class="sxs-lookup"><span data-stu-id="fd0a7-115">The policy description is displayed at the bottom of the page, and the **Additional help** section displays the hyperlink that you have configured for the policy.</span></span> <span data-ttu-id="fd0a7-116">Cliquez sur le lien hypertexte pour ouvrir la page Web que vous avez spécifiée lors de la création de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="fd0a7-116">Click the message hyperlink to open the Web page that you specified when you created the policy.</span></span>  
  
8.  <span data-ttu-id="fd0a7-117">Fermez le navigateur, puis fermez la boîte de dialogue **Vue détaillée des résultats** .</span><span class="sxs-lookup"><span data-stu-id="fd0a7-117">Close the browser, and then close the **Results Detailed View** dialog box.</span></span>  
  
9. <span data-ttu-id="fd0a7-118">Si le serveur n’est pas conforme et que vous souhaitez désactiver la messagerie de base de données, cliquez sur **Appliquer** dans la page **Résultats d’évaluation** .</span><span class="sxs-lookup"><span data-stu-id="fd0a7-118">If the server is out of compliance and you want to disable Database Mail, click **Apply** in the **Evaluation Results** page.</span></span>  
  
10. <span data-ttu-id="fd0a7-119">Fermez les boîtes de dialogue **Vue détaillée des résultats** et **Évaluer les stratégies** .</span><span class="sxs-lookup"><span data-stu-id="fd0a7-119">Close both the **Results Detailed View** and the **Evaluate Policies** dialog boxes.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="fd0a7-120">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="fd0a7-120">Next Lesson</span></span>  
 [<span data-ttu-id="fd0a7-121">Leçon 2 : Créer et appliquer une stratégie de normes d’affectation de noms</span><span class="sxs-lookup"><span data-stu-id="fd0a7-121">Lesson 2: Create and Apply a Naming Standards Policy</span></span>](lesson-2-create-and-apply-a-naming-standards-policy.md)  
  
  
