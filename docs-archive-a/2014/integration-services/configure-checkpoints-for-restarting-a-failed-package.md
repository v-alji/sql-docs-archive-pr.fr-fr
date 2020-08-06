---
title: Configurer des points de contrôle pour redémarrer un package ayant échoué | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- checkpoints [Integration Services]
- restarting packages
- starting packages
ms.assetid: 9afffa5a-d803-4653-8afc-386453fc163f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a85354377453e0b24692ab8c2b567cc8998b6b05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705351"
---
# <a name="configure-checkpoints-for-restarting-a-failed-package"></a><span data-ttu-id="972ac-102">Configurer des points de contrôle pour redémarrer un package ayant échoué</span><span class="sxs-lookup"><span data-stu-id="972ac-102">Configure Checkpoints for Restarting a Failed Package</span></span>
  <span data-ttu-id="972ac-103">Vous pouvez configurer les packages [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] de sorte qu'ils redémarrent à partir d'un point d'arrêt au lieu de réexécuter l'ensemble du package. Pour ce faire, vous devez définir les propriétés des points de contrôle.</span><span class="sxs-lookup"><span data-stu-id="972ac-103">You configure [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages to restart from a point of failure, instead of rerunning the entire package, by setting the properties that apply to checkpoints.</span></span>  
  
### <a name="to-configure-a-package-to-restart"></a><span data-ttu-id="972ac-104">Pour configurer le redémarrage d'un package</span><span class="sxs-lookup"><span data-stu-id="972ac-104">To configure a package to restart</span></span>  
  
1.  <span data-ttu-id="972ac-105">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package à configurer.</span><span class="sxs-lookup"><span data-stu-id="972ac-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want to configure.</span></span>  
  
2.  <span data-ttu-id="972ac-106">Dans **l’Explorateur de solutions**, double-cliquez sur le package pour l’ouvrir.</span><span class="sxs-lookup"><span data-stu-id="972ac-106">In **Solution Explorer**, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="972ac-107">Cliquez sur l'onglet **Flux de contrôle** .</span><span class="sxs-lookup"><span data-stu-id="972ac-107">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="972ac-108">Cliquez avec le bouton droit n’importe où dans l’arrière-plan de la surface de dessin du flux de contrôle, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="972ac-108">Right-click anywhere in the background of the control flow design surface, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="972ac-109">Affectez à la propriété SaveCheckpoints la valeur `True` .</span><span class="sxs-lookup"><span data-stu-id="972ac-109">Set the SaveCheckpoints property to `True`.</span></span>  
  
6.  <span data-ttu-id="972ac-110">Tapez le nom du fichier point de contrôle dans la propriété CheckpointFileName.</span><span class="sxs-lookup"><span data-stu-id="972ac-110">Type the name of the checkpoint file in the CheckpointFileName property.</span></span>  
  
7.  <span data-ttu-id="972ac-111">Définissez la propriété CheckpointUsage sur l’une des deux valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="972ac-111">Set the CheckpointUsage property to one of two values:</span></span>  
  
    -   <span data-ttu-id="972ac-112">Sélectionnez `Always` pour toujours redémarrer le package à partir du point d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="972ac-112">Select `Always` to always restart the package from the checkpoint.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="972ac-113">Une erreur se produit si le fichier de point d'arrêt n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="972ac-113">An error occurs if the checkpoint file is not available.</span></span>  
  
    -   <span data-ttu-id="972ac-114">Sélectionnez `IfExists` pour redémarrer le package uniquement si le fichier de point d'arrêt est disponible.</span><span class="sxs-lookup"><span data-stu-id="972ac-114">Select `IfExists` to restart the package only if the checkpoint file is available.</span></span>  
  
8.  <span data-ttu-id="972ac-115">Configurez les tâches et les conteneurs à partir desquels le package peut redémarrer.</span><span class="sxs-lookup"><span data-stu-id="972ac-115">Configure the tasks and containers from which the package can restart.</span></span>  
  
    -   <span data-ttu-id="972ac-116">Cliquez avec le bouton droit sur une tâche ou un conteneur, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="972ac-116">Right-click a task or container and click **Properties**.</span></span>  
  
    -   <span data-ttu-id="972ac-117">Affectez à la propriété FailPackageOnFailure la valeur `True` pour chaque tâche et conteneur sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="972ac-117">Set the FailPackageOnFailure property to `True` for each selected task and container.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="972ac-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="972ac-118">See Also</span></span>  
 [<span data-ttu-id="972ac-119">Redémarrer des packages à l'aide de points de contrôle</span><span class="sxs-lookup"><span data-stu-id="972ac-119">Restart Packages by Using Checkpoints</span></span>](packages/restart-packages-by-using-checkpoints.md)  
  
  
