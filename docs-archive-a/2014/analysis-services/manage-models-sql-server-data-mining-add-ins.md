---
title: Gérer les modèles (SQL Server les compléments d’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, importing
- mining models, deleting
- mining models, managing
- mining models, training
- mining models, processing
- mining models, exporting
ms.assetid: c11380f0-7c24-4668-9cdf-9c53e4aff665
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5f4b5961ec79bb949bf7fa5f53a980f066e81379
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612587"
---
# <a name="manage-models-sql-server-data-mining-add-ins"></a><span data-ttu-id="45653-102">Gérer les modèles (Compléments d'exploration de données SQL Server)</span><span class="sxs-lookup"><span data-stu-id="45653-102">Manage Models (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="45653-103">![Bouton Gérer les modèles, ruban Exploration de données](media/dmc-manage.gif "Bouton Gérer les modèles, ruban Exploration de données")</span><span class="sxs-lookup"><span data-stu-id="45653-103">![Manage Models button, Data Mining ribbon](media/dmc-manage.gif "Manage Models button, Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="45653-104">La boîte de dialogue **gérer les modèles** vous permet d’interagir avec les modèles d’exploration de données et les structures d’exploration de données existants qui sont stockés sur le [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] serveur auquel vous êtes actuellement connecté.</span><span class="sxs-lookup"><span data-stu-id="45653-104">The **Manage Models** dialog box enables you to interact with existing mining models and mining structures that are stored in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server to which you are currently connected.</span></span> <span data-ttu-id="45653-105">Vous pouvez également afficher et gérer les structures et modèles temporaires créés pendant la session active.</span><span class="sxs-lookup"><span data-stu-id="45653-105">You can also view and manage temporary structures and models that have been created during the current session.</span></span> <span data-ttu-id="45653-106">Si vous avez utilisé à la fois les modèles de session et les modèles stockés sur un serveur, les deux sont visibles dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="45653-106">If you have used both session models and models stored on a server, both are visible in the dialog box.</span></span>  
  
## <a name="using-the-manage-models-wizard"></a><span data-ttu-id="45653-107">Utilisation de l'Assistant Gérer les modèles</span><span class="sxs-lookup"><span data-stu-id="45653-107">Using the Manage Models Wizard</span></span>  
 <span data-ttu-id="45653-108">Lorsque vous cliquez sur **gérer les modèles**, la boîte de dialogue gérer les **modèles et les structures d’exploration** de données s’ouvre et fournit un accès aux fonctionnalités suivantes pour gérer les structures et modèles d’exploration de données existants :</span><span class="sxs-lookup"><span data-stu-id="45653-108">When you click **Manage Models**, the **Manage Mining Structures and Models** dialog box opens, providing access to the following functionality for managing existing data mining models and structures:</span></span>  
  
-   <span data-ttu-id="45653-109">Renommer un modèle ou une structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="45653-109">Rename a mining model or structure</span></span>  
  
-   <span data-ttu-id="45653-110">Supprimer un modèle ou une structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="45653-110">Delete a mining model or structure</span></span>  
  
-   <span data-ttu-id="45653-111">Effacer un modèle ou une structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="45653-111">Clear a mining model or structure</span></span>  
  
-   <span data-ttu-id="45653-112">Traiter une structure d'exploration de données à l'aide de données nouvelles ou existantes</span><span class="sxs-lookup"><span data-stu-id="45653-112">Process a mining structure, using either new or existing data</span></span>  
  
-   <span data-ttu-id="45653-113">Exporter ou importer une structure ou un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="45653-113">Export or import a mining model or structure</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45653-114">Cette boîte de dialogue ne vous permet pas de créer des requêtes ou des modèles.</span><span class="sxs-lookup"><span data-stu-id="45653-114">You cannot create queries or models by using this dialog box.</span></span> <span data-ttu-id="45653-115">Pour créer une nouvelle structure d’exploration de données, utilisez l’un des assistants fournis dans le client d’exploration de données pour Excel ou utilisez la **requête d’exploration de données éditeur avancé**.</span><span class="sxs-lookup"><span data-stu-id="45653-115">To create a new mining structure, use one of the wizards provided in the Data Mining Client for Excel, or use the **Data Mining Query Advanced Editor**.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="45653-116">Spécifications</span><span class="sxs-lookup"><span data-stu-id="45653-116">Requirements</span></span>  
 <span data-ttu-id="45653-117">Pour gérer des modèles d'exploration de données, créez tout d'abord une connexion à une instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45653-117">To manage data mining models, you must first create a connection to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="45653-118">La connexion est requise même si vous utilisez des modèles de session stockés dans un fichier temporaire.</span><span class="sxs-lookup"><span data-stu-id="45653-118">A connection is required even if you are working with session models stored in a temporary file.</span></span> <span data-ttu-id="45653-119">Pour plus d’informations sur la création ou la modification d’une connexion, consultez [se connecter à des données sources &#40;client d’exploration de données pour Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="45653-119">For more information about how to create or change a connection, see [Connect to Source Data &#40;Data Mining Client for Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span></span>  
  
 <span data-ttu-id="45653-120">Si l'instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] à laquelle vous vous connectez ne contient aucune structure d'exploration de données ni aucun modèle d'exploration de données, vous pouvez les créer en utilisant les Assistants et les autres outils fournis par ce complément.</span><span class="sxs-lookup"><span data-stu-id="45653-120">If the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you connect to does not contain any existing data mining structures or data mining models, you can create them by using the wizards and other tools provided by this add-in.</span></span> <span data-ttu-id="45653-121">Vous pouvez également créer des modèles à l’aide du **modèle d’exploration de données éditeur avancé**.</span><span class="sxs-lookup"><span data-stu-id="45653-121">You can also create new models by using the **Data Mining Model Advanced Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45653-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="45653-122">See Also</span></span>  
 <span data-ttu-id="45653-123">[Documentation des modèles d’exploration de données &#40;les compléments d’exploration de données pour Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="45653-123">[Documenting Mining Models &#40;Data Mining Add-ins for Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md) </span></span>  
 [<span data-ttu-id="45653-124">Déploiement et mise à l’échelle des modèles d’exploration de données &#40;les compléments d’exploration de données pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="45653-124">Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;</span></span>](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md)   

  
