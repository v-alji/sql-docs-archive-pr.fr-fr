---
title: Créer un cube à l’aide de l’Assistant Cube | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- cubes [Analysis Services], creating
ms.assetid: d46d659c-3a4e-4364-94ac-f5eb6ba0ec25
author: minewiskan
ms.author: owend
ms.openlocfilehash: 441c296c0fd71b2a9c2b8332743da6224839a471
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705640"
---
# <a name="create-a-cube-using-the-cube-wizard"></a><span data-ttu-id="56a27-102">Créer un cube à l'aide de l'Assistant Cube</span><span class="sxs-lookup"><span data-stu-id="56a27-102">Create a Cube Using the Cube Wizard</span></span>
  <span data-ttu-id="56a27-103">Vous pouvez créer un cube en utilisant l’Assistant Cube dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56a27-103">You can create a new cube by using the Cube Wizard in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
### <a name="to-create-a-new-cube"></a><span data-ttu-id="56a27-104">Pour créer un cube</span><span class="sxs-lookup"><span data-stu-id="56a27-104">To create a new cube</span></span>  
  
1.  <span data-ttu-id="56a27-105">Dans **Explorateur de solutions**, cliquez avec le bouton droit sur **cubes**, puis cliquez sur **Nouveau Cube**.</span><span class="sxs-lookup"><span data-stu-id="56a27-105">In **Solution Explorer**, right-click **Cubes**, and then click **New Cube**.</span></span>  
  
2.  <span data-ttu-id="56a27-106">Dans la page **Sélectionner la méthode de création** de l’Assistant Cube, sélectionnez **Utiliser des tables existantes**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="56a27-106">On the **Select Creation Method** page of the Cube Wizard, select **Use existing tables**, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="56a27-107">Parfois, vous devez éventuellement créer un cube sans utiliser de tables existantes.</span><span class="sxs-lookup"><span data-stu-id="56a27-107">You might occasionally have to create a cube without using existing tables.</span></span> <span data-ttu-id="56a27-108">Pour créer un cube vide, sélectionnez **Créer un cube vide**.</span><span class="sxs-lookup"><span data-stu-id="56a27-108">To create an empty cube, select **Create an empty cube**.</span></span> <span data-ttu-id="56a27-109">Pour générer des tables, sélectionnez **Générer des tables dans la source de données**.</span><span class="sxs-lookup"><span data-stu-id="56a27-109">To generate tables, select **Generate tables in the data source**.</span></span>  
  
3.  <span data-ttu-id="56a27-110">Dans la page **Sélectionner les tables de groupes de mesures** , suivez les procédures ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="56a27-110">On the **Select Measure Group Tables** page, do the following procedures:</span></span>  
  
    1.  <span data-ttu-id="56a27-111">Dans la liste **Vue de source de données** , sélectionnez une vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="56a27-111">In the **Data source view** list, select a data source view.</span></span>  
  
    2.  <span data-ttu-id="56a27-112">Dans la liste **Tables de groupes de mesures** , sélectionnez les tables qui à utiliser pour créer des groupes de mesures.</span><span class="sxs-lookup"><span data-stu-id="56a27-112">In the **Measure group tables** list, select the tables that will be used to create measure groups.</span></span>  
  
    3.  <span data-ttu-id="56a27-113">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="56a27-113">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="56a27-114">Dans la page **Sélectionner les mesures** , sélectionnez les mesures à inclure dans le cube, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="56a27-114">On the **Select Measures** page, select the measures that you want to include in the cube, and then click **Next**.</span></span>  
  
     <span data-ttu-id="56a27-115">Vous pouvez éventuellement modifier les noms des mesures et groupes de mesures.</span><span class="sxs-lookup"><span data-stu-id="56a27-115">Optionally, you can change the names of the measures and measure groups.</span></span>  
  
5.  <span data-ttu-id="56a27-116">Dans la page **Sélectionner des dimensions existantes** , sélectionnez les dimensions existantes à inclure dans le cube, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="56a27-116">On the **Select Existing Dimensions** page, select the existing dimensions to include in the cube, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="56a27-117">La page **Sélectionner des dimensions existantes** apparaît si des dimensions existent déjà dans la base de données pour les groupes de mesures sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="56a27-117">The **Select Existing Dimensions** page appears if dimensions already exist in the database for any of the selected measure groups.</span></span>  
  
6.  <span data-ttu-id="56a27-118">Dans la page **Sélectionner de nouvelles dimensions** , sélectionnez les nouvelles dimensions à créer, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="56a27-118">On the **Select New Dimensions** page, select the new dimensions to create, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="56a27-119">La page **Sélectionner de nouvelles dimensions** apparaît si des tables conviennent aux tables de dimension et si elles n’ont pas déjà été utilisées par des dimensions existantes.</span><span class="sxs-lookup"><span data-stu-id="56a27-119">The **Select New Dimensions** page appears if any tables would be good candidates for dimension tables, and the tables have not already been used by existing dimensions.</span></span>  
  
7.  <span data-ttu-id="56a27-120">Dans la page **Sélectionner les clés de dimension manquantes** , sélectionnez une clé pour la dimension, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="56a27-120">On the **Select Missing Dimension Keys** page, select a key for the dimension, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="56a27-121">La page **Sélectionner les clés de dimension manquantes** apparaît si une clé n’est pas définie pour une table de dimension que vous avez spécifiée.</span><span class="sxs-lookup"><span data-stu-id="56a27-121">The **Select Missing Dimension Keys** page appears if any of the dimension tables that you specified do not have a key defined.</span></span>  
  
8.  <span data-ttu-id="56a27-122">Dans la page **Fin de l’Assistant** , entrez le nom du nouveau cube et examinez sa structure.</span><span class="sxs-lookup"><span data-stu-id="56a27-122">On the **Completing the Wizard** page, enter a name for the new cube and review the cube structure.</span></span> <span data-ttu-id="56a27-123">Si vous souhaitez apporter des modifications, cliquez sur **Précédent**; sinon, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="56a27-123">If you want to make changes, click **Back**; otherwise, click **Finish**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="56a27-124">Vous pouvez utiliser le Concepteur de cube une fois l'exécution de l'Assistant Cube terminée pour définir le cube.</span><span class="sxs-lookup"><span data-stu-id="56a27-124">You can use Cube Designer after you complete the Cube Wizard to configure the cube.</span></span> <span data-ttu-id="56a27-125">Vous pouvez également utiliser le Concepteur de dimensions pour ajouter, supprimer et configurer des attributs et des hiérarchies dans les dimensions que vous avez créées.</span><span class="sxs-lookup"><span data-stu-id="56a27-125">You can also use Dimension Designer to add, remove, and configure attributes and hierarchies in the dimensions that you created.</span></span>  
  
  
