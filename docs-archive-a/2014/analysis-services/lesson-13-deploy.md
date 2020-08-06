---
title: 'Leçon 14 : déployer | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 24863a8a-9017-415a-a97b-fbac76ed0675
author: minewiskan
ms.author: owend
ms.openlocfilehash: c1a55960a0c33a386d978f3c15e489ed7bd861ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600284"
---
# <a name="lesson-14-deploy"></a><span data-ttu-id="b52e9-102">Leçon 14 : Déploiement</span><span class="sxs-lookup"><span data-stu-id="b52e9-102">Lesson 14: Deploy</span></span>
  <span data-ttu-id="b52e9-103">Dans cette leçon, vous allez configurer les propriétés de déploiement ; pour cela, vous allez spécifier une instance de serveur de déploiement d'Analysis Services qui s'exécute en mode tabulaire, ainsi qu'un nom pour le modèle que vous déployez.</span><span class="sxs-lookup"><span data-stu-id="b52e9-103">In this lesson, you will configure deployment properties; specifying a deployment server instance of Analysis Services running in Tabular mode, and a name for the model you deploy.</span></span> <span data-ttu-id="b52e9-104">Vous allez ensuite déployer le modèle sur cette instance.</span><span class="sxs-lookup"><span data-stu-id="b52e9-104">You will then deploy the model to that instance.</span></span> <span data-ttu-id="b52e9-105">Après son déploiement, les utilisateurs peuvent se connecter au modèle en utilisant une application de création de rapports cliente.</span><span class="sxs-lookup"><span data-stu-id="b52e9-105">After it is deployed, users can connect to the model by using a reporting client application.</span></span> <span data-ttu-id="b52e9-106">Pour plus d’informations, consultez [Déploiement d’une solution de modèle tabulaire &#40;SSAS Tabulaire&#41;](tabular-models/tabular-model-solution-deployment-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="b52e9-106">To learn more, see [Tabular Model Solution Deployment &#40;SSAS Tabular&#41;](tabular-models/tabular-model-solution-deployment-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="b52e9-107">Durée estimée pour effectuer cette leçon : **5 minutes**</span><span class="sxs-lookup"><span data-stu-id="b52e9-107">Estimated time to complete this lesson: **5 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b52e9-108">Prérequis</span><span class="sxs-lookup"><span data-stu-id="b52e9-108">Prerequisites</span></span>  
 <span data-ttu-id="b52e9-109">Cette rubrique fait partie d’un didacticiel de modélisation tabulaire, qui doit être suivi dans l’ordre prévu.</span><span class="sxs-lookup"><span data-stu-id="b52e9-109">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="b52e9-110">Avant d’effectuer les tâches de cette leçon, vous devez avoir terminé la leçon précédente : [Leçon 13 : Analyser dans Excel](lesson-12-analyze-in-excel.md).</span><span class="sxs-lookup"><span data-stu-id="b52e9-110">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 13: Analyze in Excel](lesson-12-analyze-in-excel.md).</span></span>  
  
## <a name="deploy-the-model"></a><span data-ttu-id="b52e9-111">Déployer le modèle</span><span class="sxs-lookup"><span data-stu-id="b52e9-111">Deploy the Model</span></span>  
  
#### <a name="to-configure-deployment-properties"></a><span data-ttu-id="b52e9-112">Pour configurer les propriétés de déploiement</span><span class="sxs-lookup"><span data-stu-id="b52e9-112">To configure deployment properties</span></span>  
  
1.  <span data-ttu-id="b52e9-113">Dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dans **l’Explorateur de solutions**, cliquez avec le bouton droit sur le projet **Adventure Works Internet Sales Tabular Model** , puis dans le menu contextuel, cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b52e9-113">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], in **Solution Explorer**, right-click on the **Adventure Works Internet Sales Tabular Model** project, and then in the context menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b52e9-114">Dans la boîte de dialogue **Pages des propriétés de AW Internet Sales Tabular Model** , sous **Serveur de déploiement**, dans la propriété **Serveur** , tapez le nom d’une instance Analysis Services en mode tabulaire.</span><span class="sxs-lookup"><span data-stu-id="b52e9-114">In the **AW Internet Sales Tabular Model Property Pages** dialog box, under **Deployment Server**, in the **Server** property, type the name of an Analysis Services instance running in Tabular mode.</span></span> <span data-ttu-id="b52e9-115">Ce sera l'instance sur laquelle sera déployé votre modèle.</span><span class="sxs-lookup"><span data-stu-id="b52e9-115">This will be the instance your model will be deployed to.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b52e9-116">Vous devez disposer d'autorisations d'administration sur une instance Analysis Services distante afin de déployer dans celle-ci.</span><span class="sxs-lookup"><span data-stu-id="b52e9-116">You must have Administrator permissions on a remote Analysis Services instance in-order to deploy to it.</span></span>  
  
3.  <span data-ttu-id="b52e9-117">Vérifiez que la propriété **mode de requête** est définie sur **in-Memory**.</span><span class="sxs-lookup"><span data-stu-id="b52e9-117">Verify the **Query Mode** property is set to **In-Memory**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b52e9-118">Le modèle créé à l'aide de ce didacticiel n'est pas pris en charge en mode DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="b52e9-118">The model created by using this tutorial is not supported in DirectQuery mode.</span></span>  
  
4.  <span data-ttu-id="b52e9-119">Dans la propriété **Database** , tapez `Adventure Works Internet Sales Model` .</span><span class="sxs-lookup"><span data-stu-id="b52e9-119">In the **Database** property, type `Adventure Works Internet Sales Model`.</span></span>  
  
5.  <span data-ttu-id="b52e9-120">Dans la propriété nom du **cube** , tapez `Adventure Works Internet Sales Model` .</span><span class="sxs-lookup"><span data-stu-id="b52e9-120">In the **Cube** Name property, type `Adventure Works Internet Sales Model`.</span></span>  
  
6.  <span data-ttu-id="b52e9-121">Passez en revue vos sélections, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b52e9-121">Verify your selections and then click **OK**.</span></span>  
  
#### <a name="to-deploy-the-adventure-works-internet-sales-tabular-model"></a><span data-ttu-id="b52e9-122">Pour déployer le modèle tabulaire Internet Sales Adventure Works</span><span class="sxs-lookup"><span data-stu-id="b52e9-122">To deploy the Adventure Works Internet Sales tabular model</span></span>  
  
1.  <span data-ttu-id="b52e9-123">Dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], cliquez sur le menu **Générer** , puis cliquez sur **Déployer AW Internet Sales Tabular Model**.</span><span class="sxs-lookup"><span data-stu-id="b52e9-123">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click the **Build** menu, and then click **Deploy AW Internet Sales Tabular Model**.</span></span>  
  
     <span data-ttu-id="b52e9-124">La boîte de dialogue Déployer apparaît et affiche l'état de déploiement des métadonnées ainsi que de chaque table incluse dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="b52e9-124">The Deploy dialog box appears and displays the deployment status of the metadata as well as each table included in the model.</span></span>  
  
## <a name="conclusion"></a><span data-ttu-id="b52e9-125">Conclusion</span><span class="sxs-lookup"><span data-stu-id="b52e9-125">Conclusion</span></span>  
 <span data-ttu-id="b52e9-126">Félicitations !</span><span class="sxs-lookup"><span data-stu-id="b52e9-126">Congratulations!</span></span> <span data-ttu-id="b52e9-127">Vous avez terminé de créer et déployer votre premier modèle tabulaire Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="b52e9-127">You are finished authoring and deploying your first Analysis Services tabular model.</span></span> <span data-ttu-id="b52e9-128">Ce didacticiel vous a guidés dans les tâches courantes pour créer un modèle tabulaire.</span><span class="sxs-lookup"><span data-stu-id="b52e9-128">This tutorial has helped guide you through completing the most common tasks in creating a tabular model.</span></span> <span data-ttu-id="b52e9-129">Maintenant que votre modèle Internet Sales Adventure Works est déployé, vous pouvez utiliser SQL Server Management Studio pour gérer le modèle, créer des scripts de processus et un plan de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="b52e9-129">Now that your Adventure Works Internet Sales Model is deployed, you can use SQL Server Management Studio to manage the model; create process scripts and a backup plan.</span></span> <span data-ttu-id="b52e9-130">Les utilisateurs peuvent se connecter au modèle à l'aide d'une application cliente de création de rapports telle que Microsoft Excel ou [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b52e9-130">Users can connect to the model using a reporting client application such as Microsoft Excel or [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)].</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="b52e9-131">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b52e9-131">Additional Resources</span></span>  
 <span data-ttu-id="b52e9-132">Pour en savoir plus sur les propriétés de modèle tabulaire qui prennent en charge les rapports [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)], consultez [Propriétés de la génération de rapports Power View &#40;SSAS Tabulaire&#41;](tabular-models/properties-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="b52e9-132">To learn more about tabular model properties that support [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)] reports, see [Power View Reporting Properties &#40;SSAS Tabular&#41;](tabular-models/properties-ssas-tabular.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b52e9-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b52e9-133">See Also</span></span>  
 <span data-ttu-id="b52e9-134">[Mode DirectQuery &#40;&#41;tabulaire SSAS](tabular-models/directquery-mode-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="b52e9-134">[DirectQuery Mode &#40;SSAS Tabular&#41;](tabular-models/directquery-mode-ssas-tabular.md) </span></span>  
 <span data-ttu-id="b52e9-135">[Configurer les propriétés de déploiement et de modélisation des données par défaut &#40;SSAS tabulaire&#41;](tabular-models/configure-default-data-modeling-and-deployment-properties-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="b52e9-135">[Configure Default Data Modeling and Deployment Properties &#40;SSAS Tabular&#41;](tabular-models/configure-default-data-modeling-and-deployment-properties-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="b52e9-136">Bases de données model tabulaires #40;SSAS Tabulaire#41;</span><span class="sxs-lookup"><span data-stu-id="b52e9-136">Tabular Model Databases &#40;SSAS Tabular&#41;</span></span>](tabular-models/tabular-model-databases-ssas-tabular.md)  
  
  
