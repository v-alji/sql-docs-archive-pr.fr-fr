---
title: 'Leçon 3 : utilisation de l’utilitaire d’invite de commandes DTA | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], tutorials
ms.assetid: 30f27f4d-8852-4b12-ba62-57f63e496f1d
author: stevestein
ms.author: sstein
ms.openlocfilehash: abbde02cd73e01937e6d0669c10f2db28da8a76e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695000"
---
# <a name="lesson-3-using-the-dta-command-prompt-utility"></a><span data-ttu-id="3f34f-102">Leçon 3 : Utilisation de l'utilitaire de ligne de commande dta</span><span class="sxs-lookup"><span data-stu-id="3f34f-102">Lesson 3: Using the dta Command Prompt Utility</span></span>
  <span data-ttu-id="3f34f-103">L’utilitaire en ligne de commande **dta** offre une fonctionnalité supplémentaire par rapport à celles fournies par l’Assistant Paramétrage du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="3f34f-103">The **dta** command-prompt utility offers functionality in addition to that provided by the Database Engine Tuning Advisor.</span></span>  
  
 <span data-ttu-id="3f34f-104">Vous pouvez utiliser vos outils XML favoris pour créer des fichiers d'entrée pour l'utilitaire en utilisant le schéma XML de l'Assistant Paramétrage du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="3f34f-104">You can use your favorite XML tools to create input files for the utility by using the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="3f34f-105">Ce schéma est installé lorsque vous installez [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et il se trouve dans le dossier : C:\Program Files (x86)\Microsoft SQL Server\110\Tools\Binn\schemas\sqlserver\2004\07\dta\dtaschema.xsd.</span><span class="sxs-lookup"><span data-stu-id="3f34f-105">This schema is installed when you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and can be found at: C:\Program Files (x86)\Microsoft SQL Server\110\Tools\Binn\schemas\sqlserver\2004\07\dta\dtaschema.xsd.</span></span>  
  
 <span data-ttu-id="3f34f-106">Le schéma XML de l'Assistant Paramétrage du moteur de base de données est également disponible en ligne sur ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?linkid=43100&clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="3f34f-106">The Database Engine Tuning Advisor XML schema is also available online at [this Microsoft Web site](https://go.microsoft.com/fwlink/?linkid=43100&clcid=0x409).</span></span>  
  
 <span data-ttu-id="3f34f-107">Ce schéma offre plus de souplesse pour définir les options de paramétrage.</span><span class="sxs-lookup"><span data-stu-id="3f34f-107">The Database Engine Tuning Advisor XML schema provides more flexibility to set tuning options.</span></span> <span data-ttu-id="3f34f-108">Par exemple, il permet d'effectuer des analyses de scénarios.</span><span class="sxs-lookup"><span data-stu-id="3f34f-108">For example, it enables you to perform "what-if" analysis.</span></span> <span data-ttu-id="3f34f-109">Pour réaliser des analyses de scénarios, vous devez spécifier un ensemble de structures de création physiques existantes ou hypothétiques pour la base de données que vous souhaitez paramétrer, puis l'analyser avec l'Assistant Paramétrage du moteur de base de données pour déterminer si cette structure de création physique hypothétique améliorera les performances de traitement des requêtes.</span><span class="sxs-lookup"><span data-stu-id="3f34f-109">"What-if" analysis involves specifying a set of existing and hypothetical physical design structures for the database you want to tune, and then analyzing it with the Database Engine Tuning Advisor to find out whether this hypothetical physical design will improve query processing performance.</span></span> <span data-ttu-id="3f34f-110">Ce type d'analyse offre l'avantage de pouvoir évaluer la nouvelle configuration sans avoir à supporter la charge induite par une mise en œuvre effective.</span><span class="sxs-lookup"><span data-stu-id="3f34f-110">This type of analysis provides the advantage of evaluating the new configuration without incurring the overhead of actually implementing it.</span></span> <span data-ttu-id="3f34f-111">Si votre structure de création physique hypothétique ne permet pas d'obtenir les améliorations souhaitées en matière de performances, il est facile de la modifier et de l'analyser de nouveau jusqu'à ce que vous ayez atteint la configuration qui produit les résultats requis.</span><span class="sxs-lookup"><span data-stu-id="3f34f-111">If your hypothetical physical design does not provide the performance improvements you want, it is easy to change it and analyze it again until you reach the configuration that produces the results you need.</span></span>  
  
 <span data-ttu-id="3f34f-112">De plus, en utilisant le schéma XML de l’Assistant Paramétrage du moteur de base de données et l’utilitaire en ligne de commande **dta** , vous pouvez intégrer la fonctionnalité de l’Assistant Paramétrage du moteur de base de données aux scripts et l’utiliser avec d’autres outils de création de base de données.</span><span class="sxs-lookup"><span data-stu-id="3f34f-112">In addition, using the Database Engine Tuning Advisor XML schema and the **dta** command-prompt utility, you can incorporate Database Engine Tuning Advisor functionality into scripts and use it with other database design tools.</span></span>  
  
 <span data-ttu-id="3f34f-113">Cette leçon ne couvre pas l'utilisation de la fonction d'entrée XML de l'Assistant Paramétrage du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="3f34f-113">Using the XML input functionality of Database Engine Tuning Advisor is beyond the scope of this lesson.</span></span>  
  
 <span data-ttu-id="3f34f-114">Cette leçon présente la syntaxe de base de l’utilitaire de ligne de commande **dta** , explique comment accéder à l’aide et propose des exercices portant sur le paramétrage de charges de travail simples.</span><span class="sxs-lookup"><span data-stu-id="3f34f-114">This lesson provides an introduction to the basic **dta** command-prompt utility syntax, how to access help, and practice for tuning simple workloads.</span></span>  
  
 <span data-ttu-id="3f34f-115">Elle contient les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="3f34f-115">It contains the following topic:</span></span>  
  
-   <span data-ttu-id="3f34f-116">Démarrage de l’utilitaire d’invite de commandes **DTA** et paramétrage d’une charge de travail</span><span class="sxs-lookup"><span data-stu-id="3f34f-116">Starting the **dta** Command Prompt Utility and Tuning a Workload</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="3f34f-117">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="3f34f-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="3f34f-118">Démarrage de l'utilitaire de ligne de commande dta et paramétrage d'une charge de travail</span><span class="sxs-lookup"><span data-stu-id="3f34f-118">Starting the dta Command Prompt Utility and Tuning a Workload</span></span>](lesson-1-1-tuning-a-workload.md)  
  
  
