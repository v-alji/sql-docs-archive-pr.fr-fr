---
title: Définir ou modifier la méthode de connexion par défaut pour DirectQuery | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f10d5678-d678-4251-8cce-4e30cfe15751
author: minewiskan
ms.author: owend
ms.openlocfilehash: 239c80ace0daa3498c8dafd8fea358ce540931d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705512"
---
# <a name="set-or-change-the-preferred-connection-method-for-directquery"></a><span data-ttu-id="18f34-102">Définir ou modifier la méthode de connexion par défaut pour DirectQuery</span><span class="sxs-lookup"><span data-stu-id="18f34-102">Set or Change the Preferred Connection Method for DirectQuery</span></span>
  <span data-ttu-id="18f34-103">Lorsque vous créez un modèle à utiliser en mode DirectQuery, vous devez d'abord configurer l'environnement de conception de façon à ce qu'il prenne en charge l'utilisation de DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="18f34-103">When you create a model for use in DirectQuery mode, you must first configure the design environment to support use of DirectQuery.</span></span> <span data-ttu-id="18f34-104">Pour ce faire, consultez [Enable DirectQuery Design mode &#40;SSAS tabulaire&#41;](tabular-models/enable-directquery-mode-in-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="18f34-104">To do this, see [Enable DirectQuery Design Mode &#40;SSAS Tabular&#41;](tabular-models/enable-directquery-mode-in-ssdt.md).</span></span>  
  
 <span data-ttu-id="18f34-105">Lorsque vous êtes prêt à déployer le modèle, vous devez définir des propriétés supplémentaires pour permettre aux utilisateurs d'accéder à votre modèle à l'aide de l'un des modes DirectQuery :</span><span class="sxs-lookup"><span data-stu-id="18f34-105">When you are ready to deploy the model, you must set some additional properties to enable users to access your model using one of the DirectQuery modes:</span></span>  
  
-   <span data-ttu-id="18f34-106">Vous devez indiquer si les requêtes sur le modèle doivent utiliser les données en mémoire cache ou la source de données relationnelle.</span><span class="sxs-lookup"><span data-stu-id="18f34-106">You must indicate whether queries against the model should use cached data or the relational data source.</span></span> <span data-ttu-id="18f34-107">Vous pouvez utiliser un mode hybride ou DirectQuery uniquement.</span><span class="sxs-lookup"><span data-stu-id="18f34-107">You can use a hybrid mode or DirectQuery only.</span></span>  
  
-   <span data-ttu-id="18f34-108">Si vous utilisez des partitions, vous devez indiquer quelle partition utiliser comme source de données DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="18f34-108">If you are using partitions, you must indicate which partition to use as the DirectQuery data source.</span></span>  
  
-   <span data-ttu-id="18f34-109">Vous devez définir les options d'emprunt d'identité pour les utilisateurs qui accèderont à la source de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="18f34-109">You must set impersonation options for users who will be accessing the SQL Server data source.</span></span>  
  
 <span data-ttu-id="18f34-110">Cette procédure explique comment définir la méthode de connexion par défaut pour un modèle DirectQuery dans le concepteur.</span><span class="sxs-lookup"><span data-stu-id="18f34-110">This procedure describes how to set the preferred connection method for a DirectQuery model in the designer.</span></span> <span data-ttu-id="18f34-111">Elle décrit également comment modifier cette propriété dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] une fois que le modèle a été déployé.</span><span class="sxs-lookup"><span data-stu-id="18f34-111">It also describes how you can change this property in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] after the model has been deployed.</span></span>  
  
### <a name="to-set-the-preferred-connection-method-for-a-directquery-model"></a><span data-ttu-id="18f34-112">Pour définir la méthode de connexion par défaut pour un modèle DirectQuery</span><span class="sxs-lookup"><span data-stu-id="18f34-112">To set the preferred connection method for a DirectQuery model</span></span>  
  
1.  <span data-ttu-id="18f34-113">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le fichier solution pour le modèle DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="18f34-113">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the solution file for the DirectQuery model.</span></span>  
  
2.  <span data-ttu-id="18f34-114">Dans Visual Studio, dans le menu de **Projet** , sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="18f34-114">In Visual Studio, from the **Project** menu, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="18f34-115">Dans le volet **Propriétés** , modifiez la propriété, **DirectQueryMode**, en l'une des valeurs qui prennent en charge l'utilisation de DirectQuery :</span><span class="sxs-lookup"><span data-stu-id="18f34-115">In the **Properties** pane, change the property, **DirectQueryMode**, to one of the values that support DirectQuery usage:</span></span>  
  
    -   <span data-ttu-id="18f34-116">**InMemory avec DirectQuery**: si vous utilisez cette option, le modèle est déployé, mais vous devez traiter le cache avant de pouvoir exécuter des requêtes sur le modèle.</span><span class="sxs-lookup"><span data-stu-id="18f34-116">**InMemory with DirectQuery**: If you use this option, the model is deployed but you must process the cache before you can run queries against the model.</span></span>  
  
    -   <span data-ttu-id="18f34-117">**DirectQuery avec InMemory**: si vous utilisez cette option, le cache est disponible pour une utilisation par les clients s'il a déjà été traité.</span><span class="sxs-lookup"><span data-stu-id="18f34-117">**DirectQuery with InMemory**: If you use this option, the cache will be available for use by clients if it has already been processed.</span></span> <span data-ttu-id="18f34-118">Si vous déployez le modèle avec ce paramètre et ne traitez pas le cache, certains clients doivent obtenir une erreur lors de la tentative de connexion au modèle.</span><span class="sxs-lookup"><span data-stu-id="18f34-118">If you deploy the model with this setting and do not process the cache, some clients must get an error on trying to connect to the model.</span></span>  
  
    -   <span data-ttu-id="18f34-119">**DirectQuery uniquement**: si vous utilisez cette option, les métadonnées sont déployées mais le modèle ne contient pas de données.</span><span class="sxs-lookup"><span data-stu-id="18f34-119">**DirectQuery only**: If you use this option, the metadata is deployed but the model has no data in it.</span></span> <span data-ttu-id="18f34-120">Les clients qui tentent de se connecter à l'aide du mode en mémoire obtiennent une erreur, indiquant que le modèle n'existe pas ou n'a pas été traité.</span><span class="sxs-lookup"><span data-stu-id="18f34-120">Clients that attempt to connect using In-Memory mode will get an error, indicating that the model does not exist or has not been processed.</span></span>  
  
4.  <span data-ttu-id="18f34-121">En cas de erreurs, dans Visual Studio, ouvrez la **Liste d'erreurs** et résolvez tous les problèmes qui empêcheraient le modèle d'être déployé en mode DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="18f34-121">If there are errors, in Visual Studio, open the **Error List** and resolve any problems that would prevent the model from being deployed in DirectQuery mode.</span></span>  
  
### <a name="to-verify-or-change-the-preferred-connection-method-for-a-directquery-model"></a><span data-ttu-id="18f34-122">Pour vérifier ou modifier la méthode de connexion par défaut pour un modèle DirectQuery</span><span class="sxs-lookup"><span data-stu-id="18f34-122">To verify or change the preferred connection method for a DirectQuery model</span></span>  
  
1.  <span data-ttu-id="18f34-123">Dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], connectez -vous à l'instance où vous avez déployé le modèle DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="18f34-123">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], connect to the instance where you deployed the DirectQuery model.</span></span>  
  
2.  <span data-ttu-id="18f34-124">Cliquez avec le bouton droit sur la base de données model et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="18f34-124">Right-click the model database, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="18f34-125">Dans le volet **Propriétés** , modifiez la propriété, **DirectQueryMode**, en l'une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="18f34-125">In the **Properties** pane, change the property, **DirectQueryMode**, to one of these values:</span></span>  
  
    -   <span data-ttu-id="18f34-126">**DirectQuery uniquement**</span><span class="sxs-lookup"><span data-stu-id="18f34-126">**DirectQuery Only**</span></span>  
  
    -   <span data-ttu-id="18f34-127">**InMemory avec DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="18f34-127">**InMemory with DirectQuery**</span></span>  
  
    -   <span data-ttu-id="18f34-128">**DirectQuery avec InMemory**</span><span class="sxs-lookup"><span data-stu-id="18f34-128">**DirectQuery with InMemory**</span></span>  
  
 <span data-ttu-id="18f34-129">Notez que ces propriétés sont les mêmes que les propriétés que vous définissez sur le projet avant son déploiement dans Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="18f34-129">Note that these properties are the same as the properties that you set on the project before deployment in Visual Studio.</span></span> <span data-ttu-id="18f34-130">Vous pouvez modifier le mode de connexion par défaut pour le mode DirectQuery à tout moment, à condition d'avoir configuré le modèle de façon à ce qu'il prenne en charge l'utilisation de DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="18f34-130">You can change the preferred connection mode for DirectQuery mode at any time, provided that you have configured the model to support DirectQuery usage.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18f34-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="18f34-131">See Also</span></span>  
 <span data-ttu-id="18f34-132">[Mode DirectQuery &#40;&#41;tabulaire SSAS](tabular-models/directquery-mode-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="18f34-132">[DirectQuery Mode &#40;SSAS Tabular&#41;](tabular-models/directquery-mode-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="18f34-133">Activer le mode de conception DirectQuery &#40;&#41;SSAS tabulaire</span><span class="sxs-lookup"><span data-stu-id="18f34-133">Enable DirectQuery Design Mode &#40;SSAS Tabular&#41;</span></span>](tabular-models/enable-directquery-mode-in-ssdt.md)  
  
  
