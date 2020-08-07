---
title: Réparer une installation de Distributed Replay | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 6fcd8ca8-1ceb-457d-9545-096c74e274d7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 57f5b2bde308e48dbf14b52a8b159b30f6a98bc8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612098"
---
# <a name="repair-a-distributed-replay-installation"></a><span data-ttu-id="40d8e-102">Réparer une installation de Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="40d8e-102">Repair a Distributed Replay Installation</span></span>
  <span data-ttu-id="40d8e-103">La réparation d'un composant Distributed Replay (contrôleur ou client) effectuera les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="40d8e-103">Repairing a Distributed Replay component (controller or client) will do the following:</span></span>  
  
1.  <span data-ttu-id="40d8e-104">Installation de tous les fichiers associés sur le disque et remplacement de tous les fichiers existants.</span><span class="sxs-lookup"><span data-stu-id="40d8e-104">Install all associated files on disk again, and replace any existing files.</span></span>  
  
2.  <span data-ttu-id="40d8e-105">recréation du compte de service Windows si le compte de service correspondant a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="40d8e-105">Recreate the Windows service account if the corresponding service account was removed.</span></span>  
  
 <span data-ttu-id="40d8e-106">Vous ne pouvez pas utiliser l'opération de Réparation pour ajouter ou supprimer des composants.</span><span class="sxs-lookup"><span data-stu-id="40d8e-106">You cannot use the Repair operation to add or remove components.</span></span> <span data-ttu-id="40d8e-107">Pour ajouter ou supprimer des composants, activez ou désactivez le composant correspondant dans l'arborescence des fonctionnalités sur la page **Sélection de fonctionnalités** dans le programme d'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="40d8e-107">To add or remove components, check or uncheck the corresponding component in the Feature tree on the **Feature Selection** page in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup.</span></span>  
  
### <a name="to-repair-a-failed-installation-of-distributed-replay"></a><span data-ttu-id="40d8e-108">Pour réparer une installation défaillante de Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="40d8e-108">To repair a failed installation of Distributed Replay</span></span>  
  
1.  <span data-ttu-id="40d8e-109">Depuis le menu **Démarrer** , cliquez sur **Panneau de configuration**, puis double-cliquez sur **Ajouter ou supprimer des programmes**.</span><span class="sxs-lookup"><span data-stu-id="40d8e-109">From the **Start** menu, click **Control Panel**, and then double-click **Add or Remove Programs**.</span></span>  
  
2.  <span data-ttu-id="40d8e-110">Sélectionnez [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] dans la fenêtre **Désinstaller ou modifier un programme** , puis dans la boîte de dialogue [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , cliquez sur **Réparation**.</span><span class="sxs-lookup"><span data-stu-id="40d8e-110">Select [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in the **Uninstall or change a program** window, and then in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] dialog box, click **Repair**.</span></span>  
  
3.  <span data-ttu-id="40d8e-111">Suivez les étapes de l'Assistant [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , et sur la page **Sélection de fonctionnalités** , sélectionnez les composants de Distributed Replay que vous souhaitez réparer, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="40d8e-111">Follow the steps in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] wizard, and on the **Select Features** page, select the Distributed Replay components you want to repair, and then click **Next.**.</span></span>  
  
4.  <span data-ttu-id="40d8e-112">Complétez l'Assistant Installation de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] pour réparer les fonctionnalités Distributed Replay sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="40d8e-112">Complete the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Installation Wizard to repair the selected Distributed Replay features.</span></span>  
  
  
