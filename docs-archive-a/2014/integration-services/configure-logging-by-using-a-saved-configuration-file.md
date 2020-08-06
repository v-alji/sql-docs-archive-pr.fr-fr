---
title: Configurer la journalisation à l’aide d’un fichier de configuration enregistré | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- containers [Integration Services], logs
- logs [Integration Services], containers
ms.assetid: e5fdbbcb-94ca-4912-aa7c-0d89cebbd308
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8eb517462d9e932906f739678fbd46c1004fb84d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611228"
---
# <a name="configure-logging-by-using-a-saved-configuration-file"></a><span data-ttu-id="89e30-102">Configurer la journalisation à l'aide d'un fichier de configuration enregistré</span><span class="sxs-lookup"><span data-stu-id="89e30-102">Configure Logging by Using a Saved Configuration File</span></span>
  <span data-ttu-id="89e30-103">Cette procédure permet de configurer la journalisation de nouveaux conteneurs dans un package en chargeant un fichier de configuration de journalisation déjà enregistré.</span><span class="sxs-lookup"><span data-stu-id="89e30-103">This procedure describes how to configure logging for new containers in a package by loading a previously saved logging configuration file.</span></span>  
  
 <span data-ttu-id="89e30-104">Par défaut, tous les conteneurs d'un package utilisent la même configuration de journalisation que leur conteneur parent.</span><span class="sxs-lookup"><span data-stu-id="89e30-104">By default, all containers in a package use the same logging configuration as their parent container.</span></span> <span data-ttu-id="89e30-105">Par exemple, les tâches d'une boucle Foreach utilisent la même configuration de journalisation que la boucle Foreach.</span><span class="sxs-lookup"><span data-stu-id="89e30-105">For example, the tasks in a Foreach Loop use the same logging configuration as the Foreach Loop.</span></span>  
  
### <a name="to-configure-logging-for-a-container"></a><span data-ttu-id="89e30-106">Pour configurer la journalisation pour un conteneur</span><span class="sxs-lookup"><span data-stu-id="89e30-106">To configure logging for a container</span></span>  
  
1.  <span data-ttu-id="89e30-107">Dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="89e30-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="89e30-108">Dans le menu **SSIS** , cliquez sur **Enregistrement**.</span><span class="sxs-lookup"><span data-stu-id="89e30-108">On the **SSIS** menu, click **Logging**.</span></span>  
  
3.  <span data-ttu-id="89e30-109">Développez l'arborescence du package et sélectionnez le conteneur à configurer.</span><span class="sxs-lookup"><span data-stu-id="89e30-109">Expand the package tree view and select the container to configure.</span></span>  
  
4.  <span data-ttu-id="89e30-110">Sous l’onglet **Fournisseurs et journaux** , sélectionnez les journaux à utiliser pour le conteneur.</span><span class="sxs-lookup"><span data-stu-id="89e30-110">On the **Providers and Logs** tab, select the logs to use for the container.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="89e30-111">Vous ne pouvez créer des journaux qu'au niveau du package.</span><span class="sxs-lookup"><span data-stu-id="89e30-111">You can create logs only at the package level.</span></span> <span data-ttu-id="89e30-112">Pour plus d’informations, consultez [Activer la journalisation des packages dans les outils de données SQL Server](../../2014/integration-services/enable-package-logging-in-sql-server-data-tools.md).</span><span class="sxs-lookup"><span data-stu-id="89e30-112">For more information, see [Enable Package Logging in SQL Server Data Tools](../../2014/integration-services/enable-package-logging-in-sql-server-data-tools.md).</span></span>  
  
5.  <span data-ttu-id="89e30-113">Cliquez sur l’onglet **Détails** , puis sur **Charger**.</span><span class="sxs-lookup"><span data-stu-id="89e30-113">Click the **Details** tab and click **Load**.</span></span>  
  
6.  <span data-ttu-id="89e30-114">Recherchez le fichier de configuration de journalisation que vous voulez utiliser et cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="89e30-114">Locate the logging configuration file you want to use and click **Open**.</span></span>  
  
7.  <span data-ttu-id="89e30-115">Si vous le souhaitez, sélectionnez une entrée de journal différente à consigner en cochant la case correspondante dans la colonne **Événements** .</span><span class="sxs-lookup"><span data-stu-id="89e30-115">Optionally, select a different log entry to log by selecting its check box in the **Events** column.</span></span> <span data-ttu-id="89e30-116">Cliquez sur **Avancé** pour sélectionner le type d’information à consigner pour cette entrée.</span><span class="sxs-lookup"><span data-stu-id="89e30-116">Click **Advanced** to select the type of information to log for this entry.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="89e30-117">Le nouveau conteneur peut inclure des entrées de journal supplémentaires qui ne sont pas disponibles pour le conteneur utilisé à l'origine pour créer la configuration de journalisation.</span><span class="sxs-lookup"><span data-stu-id="89e30-117">The new container may include additional log entries that are not available for the container originally used to create the logging configuration.</span></span> <span data-ttu-id="89e30-118">Ces entrées de journal supplémentaires doivent être sélectionnées manuellement si vous voulez qu'elles soient journalisées.</span><span class="sxs-lookup"><span data-stu-id="89e30-118">These additional log entries must be selected manually if you want them to be logged.</span></span>  
  
8.  <span data-ttu-id="89e30-119">Pour enregistrer la version mise à jour de la configuration de journalisation, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="89e30-119">To save the updated version of the logging configuration, click **Save**.</span></span>  
  
9. <span data-ttu-id="89e30-120">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="89e30-120">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89e30-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="89e30-121">See Also</span></span>  
 [<span data-ttu-id="89e30-122">Journalisation Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="89e30-122">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  
