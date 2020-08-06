---
title: Supprimer un modèle d’exploration de données d’une structure d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], mining models
- deleting mining models
- removing mining models
- mining models [Analysis Services], deleting
ms.assetid: 9ab1506b-856e-4762-a663-5adf15ac71e3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 72c79dcdccf6225b8e75144f8b090dcab7506c10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613223"
---
# <a name="delete-a-mining-model-from-a-mining-structure"></a><span data-ttu-id="db8ca-102">supprimer un modèle d'exploration de données d'une structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="db8ca-102">Delete a Mining Model from a Mining Structure</span></span>
  <span data-ttu-id="db8ca-103">Vous pouvez supprimer les modèles d’exploration de données en utilisant le Concepteur d’exploration de données, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]ou des instructions DMX.</span><span class="sxs-lookup"><span data-stu-id="db8ca-103">You can delete mining models by using Data Mining Designer, by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], or by using DMX statements.</span></span>  
  
### <a name="delete-a-mining-model-using-sql-server-data-tools"></a><span data-ttu-id="db8ca-104">Supprimer un modèle d'exploration de données à l'aide de des outils de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="db8ca-104">Delete a mining model using SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="db8ca-105">Sélectionnez l’onglet **Modèles d’exploration de données** dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db8ca-105">Select the **Mining Models** tab in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="db8ca-106">Cliquez avec le bouton droit sur le modèle à supprimer, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="db8ca-106">Right-click the model that you want to delete, and select **Delete**.</span></span>  
  
     <span data-ttu-id="db8ca-107">La boîte de dialogue **Supprimer les objets** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="db8ca-107">The **Delete Objects** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="db8ca-108">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="db8ca-108">Click **OK**.</span></span>  
  
### <a name="delete-a-mining-model-using-sql-server-management-studio"></a><span data-ttu-id="db8ca-109">Supprimer un modèle d'exploration de données à l'aide de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="db8ca-109">Delete a mining model using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="db8ca-110">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], ouvrez la base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] qui contient le modèle.</span><span class="sxs-lookup"><span data-stu-id="db8ca-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database that contains the model.</span></span>  
  
2.  <span data-ttu-id="db8ca-111">Développez **Structures d’exploration de données**, puis développez **Modèles d’exploration de données**.</span><span class="sxs-lookup"><span data-stu-id="db8ca-111">Expand **Mining Structures**, and then expand **Mining Models**.</span></span>  
  
3.  <span data-ttu-id="db8ca-112">Cliquez avec le bouton droit sur le modèle à supprimer, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="db8ca-112">Right-click the model you want to delete, and select **Delete**.</span></span>  
  
     <span data-ttu-id="db8ca-113">La suppression du modèle ne supprime pas les données d'apprentissage, seuls les métadonnées et les schémas créés lorsque vous avez formé le modèle sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="db8ca-113">Deleting the model does not delete the training data, only the metadata and any patterns created when you trained the model.</span></span>  
  
### <a name="delete-a-mining-model-using-dmx"></a><span data-ttu-id="db8ca-114">Supprimer un modèle d'exploration de données à l'aide de DMX</span><span class="sxs-lookup"><span data-stu-id="db8ca-114">Delete a mining model using DMX</span></span>  
  
-   [<span data-ttu-id="db8ca-115">DROP MINING MODEL &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="db8ca-115">DROP MINING MODEL &#40;DMX&#41;</span></span>](/sql/dmx/drop-mining-model-dmx)  
  
## <a name="see-also"></a><span data-ttu-id="db8ca-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="db8ca-116">See Also</span></span>  
 [<span data-ttu-id="db8ca-117">Tâches du modèle d'exploration de données et procédures</span><span class="sxs-lookup"><span data-stu-id="db8ca-117">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
