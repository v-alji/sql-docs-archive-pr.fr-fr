---
title: Définition des options et de la disposition des outils | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], tutorials
ms.assetid: 43e97ce0-97bc-4a27-9485-5bbeb7190b85
author: stevestein
ms.author: sstein
ms.openlocfilehash: 96d853a85b8ee4d451c55d7ea59af3755887be22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703619"
---
# <a name="setting-tool-options-and-layout"></a><span data-ttu-id="091a7-102">Définition des options du menu Outils et de la disposition</span><span class="sxs-lookup"><span data-stu-id="091a7-102">Setting Tool Options and Layout</span></span>
  <span data-ttu-id="091a7-103">Vous pouvez définir les options qui permettent de configurer ce que l'interface de l'Assistant Paramétrage du moteur de base de données affiche au démarrage, les polices qu'elle utilise et également configurer d'autres fonctionnalités pour faciliter l'utilisation de l'outil.</span><span class="sxs-lookup"><span data-stu-id="091a7-103">You can set options that configure what the Database Engine Tuning Advisor graphical user interface (GUI) displays on startup, the font it uses, and other tool functionality to best support how you use it.</span></span> <span data-ttu-id="091a7-104">Les exercices pratiques de cette page vous aideront à vous familiariser avec les options qu'il est possible de définir et avec la façon de procéder.</span><span class="sxs-lookup"><span data-stu-id="091a7-104">The practices on this page familiarize you with the options you can set, and how to set them.</span></span>  
  
### <a name="set-the-tool-options"></a><span data-ttu-id="091a7-105">Définition des options de l'outil</span><span class="sxs-lookup"><span data-stu-id="091a7-105">Set the tool options</span></span>  
  
1.  <span data-ttu-id="091a7-106">Démarrez l'Assistant Paramétrage du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="091a7-106">Start the Database Engine Tuning Advisor.</span></span> <span data-ttu-id="091a7-107">Dans le menu Windows **Démarrer** , pointez sur **Tous les programmes**, sur [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)]et sur **Outils de performances**, puis cliquez sur **Assistant Paramétrage du moteur de base de données**.</span><span class="sxs-lookup"><span data-stu-id="091a7-107">On the Windows **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Performance Tools**, and click **Database Engine Tuning Advisor**.</span></span>  
  
2.  <span data-ttu-id="091a7-108">Dans le menu **Outils** , cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="091a7-108">On the **Tools** menu, click **Options**.</span></span>  
  
3.  <span data-ttu-id="091a7-109">Dans la boîte de dialogue **Options** , passez en revue les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="091a7-109">In the **Options** dialog box, view the following options:</span></span>  
  
    -   <span data-ttu-id="091a7-110">Développez la liste **Au démarrage** pour voir ce que l'Assistant Paramétrage du moteur de base de données affiche au démarrage.</span><span class="sxs-lookup"><span data-stu-id="091a7-110">Expand the **On startup** list to view what Database Engine Tuning Advisor can display when it is started.</span></span> <span data-ttu-id="091a7-111">Par défaut, **Afficher une nouvelle session** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="091a7-111">By default, **Show a new session** is selected.</span></span>  
  
    -   <span data-ttu-id="091a7-112">Cliquez sur **modifier la police** pour voir les polices que vous pouvez choisir pour les listes de bases de données et de tables sous l’onglet **général** . Les polices que vous choisissez pour cette option sont également utilisées dans Assistant Paramétrage du moteur de base de données des grilles et des rapports de recommandation une fois que vous avez effectué le paramétrage.</span><span class="sxs-lookup"><span data-stu-id="091a7-112">Click **Change Font** to see what fonts you can choose for the lists of databases and tables on the **General** tab. The fonts you choose for this option also are used in Database Engine Tuning Advisor recommendation grids and reports after you have performed tuning.</span></span> <span data-ttu-id="091a7-113">Par défaut, l'Assistant Paramétrage du moteur de base de données utilise les polices système.</span><span class="sxs-lookup"><span data-stu-id="091a7-113">By default, Database Engine Tuning Advisor uses system fonts.</span></span>  
  
    -   <span data-ttu-id="091a7-114">Vous pouvez affecter à l'option **Nombre d'éléments dans les listes des derniers fichiers utilisés** une valeur comprise entre **1** et **10**.</span><span class="sxs-lookup"><span data-stu-id="091a7-114">The **Number of items in most recently used lists** can be set between **1** and **10**.</span></span> <span data-ttu-id="091a7-115">Cela permet de définir le nombre maximal d'éléments qui s'affichent dans les listes lorsque vous cliquez sur **Sessions récentes** ou sur **Fichiers récents** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="091a7-115">This sets the maximum number of items in the lists displayed by clicking **Recent Sessions** or **Recent Files** on the **File** menu.</span></span> <span data-ttu-id="091a7-116">Par défaut, la valeur affectée à cette option est **4**.</span><span class="sxs-lookup"><span data-stu-id="091a7-116">By default, this option is set to **4**.</span></span>  
  
    -   <span data-ttu-id="091a7-117">Lorsque l'option **Mémoriser mes dernières options de paramétrage** est activée, l'Assistant Paramétrage du moteur de base de données utilise par défaut les options de paramétrage que vous avez spécifiées au cours de la dernière session de paramétrage pour la session de paramétrage suivante.</span><span class="sxs-lookup"><span data-stu-id="091a7-117">When **Remember my last tuning options** is checked, by default Database Engine Tuning Advisor uses the tuning options you specified for your last tuning session for the next tuning session.</span></span> <span data-ttu-id="091a7-118">Désactivez cette case à cocher pour utiliser les valeurs par défaut des options de paramétrage de l'Assistant Paramétrage du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="091a7-118">Clear this check box to use Database Engine Tuning Advisor tuning option defaults.</span></span> <span data-ttu-id="091a7-119">Cette option est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="091a7-119">By default, this option is selected.</span></span>  
  
    -   <span data-ttu-id="091a7-120">Par défaut, l'option **Demander avant de supprimer définitivement les sessions** est activée pour éviter la suppression accidentelle des sessions de paramétrage.</span><span class="sxs-lookup"><span data-stu-id="091a7-120">By default, **Ask before permanently deleting sessions** is checked to avoid accidentally deleting tuning sessions.</span></span>  
  
    -   <span data-ttu-id="091a7-121">Par défaut, l'option **Demander avant d'arrêter l'analyse de la session** est activée pour éviter d'arrêter accidentellement une session de paramétrage avant que l'Assistant Paramétrage du moteur de base de données n'ait terminé d'analyser une charge de travail.</span><span class="sxs-lookup"><span data-stu-id="091a7-121">By default, **Ask before stopping session analysis** is checked to avoid accidentally stopping a tuning session before Database Engine Tuning Advisor has finished analyzing a workload.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="091a7-122">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="091a7-122">Next Lesson</span></span>  
 [<span data-ttu-id="091a7-123">Leçon 2 : Utilisation de l'Assistant Paramétrage du moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="091a7-123">Lesson 2: Using Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/database-engine-tuning-advisor.md)  
  
  
