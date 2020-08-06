---
title: Ajouter une destination à l’aide de l’Assistant destination | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 747a0de0-3c2f-4d31-a692-7111fc0911d8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cd36828a7bab7fb33b86765f9f064b6406a17a9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602269"
---
# <a name="add-a-destination-using-destination-assistant"></a><span data-ttu-id="2128d-102">Ajouter une destination à l'aide de l'Assistant Destination</span><span class="sxs-lookup"><span data-stu-id="2128d-102">Add a Destination using Destination Assistant</span></span>
  <span data-ttu-id="2128d-103">Cette rubrique indique les étapes à suivre pour ajouter une nouvelle destination via l’Assistant Destination. En outre, elle recense les options disponibles dans la boîte de dialogue **Ajouter une nouvelle destination** , qui s’affiche quand vous effectuez un glisser-déplacer de l’Assistant Destination vers le concepteur SSIS.</span><span class="sxs-lookup"><span data-stu-id="2128d-103">This topic provides steps to add a new destination using the Destination Assistant and also lists the options that are available on the **Add New Destination** dialog, which you will see when you drag-drop the Destination Assistant to the SSIS Designer.</span></span>  
  
### <a name="to-use-destination-assistant-to-add-a-destination"></a><span data-ttu-id="2128d-104">Pour utiliser l'Assistant Destination afin d'ajouter une destination</span><span class="sxs-lookup"><span data-stu-id="2128d-104">To use Destination Assistant to add a destination</span></span>  
  
1.  <span data-ttu-id="2128d-105">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] auquel vous voulez ajouter un composant destination.</span><span class="sxs-lookup"><span data-stu-id="2128d-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that you want to add a destination component to.</span></span>  
  
2.  <span data-ttu-id="2128d-106">Faites glisser le composant **Assistant Destination** de la boîte à outils SSIS vers l'onglet **Flux de données** . Vous devez voir s'afficher la boîte de dialogue **Ajouter une nouvelle destination** .</span><span class="sxs-lookup"><span data-stu-id="2128d-106">Drag the **Destination Assistant** component from the SSIS Toolbox to the **Data Flow** tab. You should see the **Add New Destination** dialog box.</span></span> <span data-ttu-id="2128d-107">La section suivante fournit des détails sur les options disponibles dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="2128d-107">The next section provides you details about the options available in the dialog box.</span></span>  
  
3.  <span data-ttu-id="2128d-108">Sélectionnez le type de la destination dans la liste **Types** .</span><span class="sxs-lookup"><span data-stu-id="2128d-108">Select the type of the destination in the **Types** list.</span></span>  
  
4.  <span data-ttu-id="2128d-109">Sélectionnez un gestionnaire de connexions existant dans la liste **Gestionnaires de connexions** ou sélectionnez **\<New>** pour en créer un.</span><span class="sxs-lookup"><span data-stu-id="2128d-109">Select an existing connection manager in the **Connection Managers** list or select **\<New>** to create a new connection manager.</span></span>  
  
5.  <span data-ttu-id="2128d-110">Si vous sélectionnez un gestionnaire de connexions existant, cliquez sur **OK** pour fermer la boîte de dialogue **Ajouter une nouvelle destination** .</span><span class="sxs-lookup"><span data-stu-id="2128d-110">If you select an existing connection manager, click **OK** to close the **Add New Destination** dialog box.</span></span> <span data-ttu-id="2128d-111">Vous devez constater que la destination et les gestionnaires de connexions ont été ajoutés au flux de données.</span><span class="sxs-lookup"><span data-stu-id="2128d-111">You should see the destination and connection managers added to the data flow.</span></span>  
  
6.  <span data-ttu-id="2128d-112">Si vous cliquez sur **\<New>** pour créer un gestionnaire de connexions, vous devez voir s’afficher une boîte de dialogue **Gestionnaire de connexions**, qui vous permet de spécifier les paramètres de la connexion.</span><span class="sxs-lookup"><span data-stu-id="2128d-112">If you click **\<New>** to create a new connection manager, you should see a **Connection Manager** dialog box, which lets you specify parameters for the connection.</span></span> <span data-ttu-id="2128d-113">Une fois que vous avez fini de créer le gestionnaire de connexions, vous constatez que la destination et le gestionnaire de connexions figurent dans le concepteur SSIS.</span><span class="sxs-lookup"><span data-stu-id="2128d-113">After you are done with creating the new connection manager, you will see the destination and the connection manager in SSIS Designer.</span></span>  
  
  
