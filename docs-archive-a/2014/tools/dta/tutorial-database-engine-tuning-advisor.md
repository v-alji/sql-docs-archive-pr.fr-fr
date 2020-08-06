---
title: 'Tutoriel : Assistant Paramétrage du moteur de base de données | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- Database Engine Tuning Advisor [SQL Server], tutorials
- tutorials [Database Engine Tuning Advisor]
ms.assetid: 3b54cbbe-d8c6-424d-92f1-aa58179f4da8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 68e026cb28b875b834f20c906232285ede8e217b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601240"
---
# <a name="tutorial-database-engine-tuning-advisor"></a><span data-ttu-id="e9576-102">Tutoriel : Database Engine Tuning Advisor</span><span class="sxs-lookup"><span data-stu-id="e9576-102">Tutorial: Database Engine Tuning Advisor</span></span>
  <span data-ttu-id="e9576-103">Bienvenue dans le Didacticiel Assistant Paramétrage du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="e9576-103">Welcome to the Database Engine Tuning Advisor tutorial.</span></span> <span data-ttu-id="e9576-104">Cet outil examine la façon dont les requêtes sont traitées dans les bases de données que vous spécifiez, puis il recommande des moyens d'améliorer les performances du traitement des requêtes en modifiant les structures des bases de données telles que les index, les vues indexées et le partitionnement.</span><span class="sxs-lookup"><span data-stu-id="e9576-104">Database Engine Tuning Advisor examines how queries are processed in the databases you specify, and then recommends how you can improve query processing performance by modifying database structures such as indexes, indexed views, and partitioning.</span></span>  
  
 <span data-ttu-id="e9576-105">L’Assistant Paramétrage du moteur de base de données fournit deux interfaces utilisateur : une interface utilisateur graphique (GUI) et l’utilitaire en ligne de commande **dta** .</span><span class="sxs-lookup"><span data-stu-id="e9576-105">Database Engine Tuning Advisor provides two user interfaces: a graphical user interface (GUI) and the **dta** command prompt utility.</span></span> <span data-ttu-id="e9576-106">L’interface utilisateur graphique facilite l’affichage des résultats des sessions de paramétrage, tandis que l’utilitaire en ligne de commande **dta** facilite l’intégration de la fonctionnalité Assistant Paramétrage du moteur de base de données aux scripts pour automatiser le paramétrage.</span><span class="sxs-lookup"><span data-stu-id="e9576-106">The GUI makes it easy to quickly view the results of tuning sessions, and the **dta** utility makes it easy to incorporate Database Engine Tuning Advisor functionality into scripts for automated tuning.</span></span> <span data-ttu-id="e9576-107">De plus, l'Assistant Paramétrage du moteur de base de données peut accepter les entrées XML, ce qui permet de mieux contrôler la procédure de paramétrage.</span><span class="sxs-lookup"><span data-stu-id="e9576-107">In addition, Database Engine Tuning Advisor can take XML input, which offers more control over the tuning process.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="e9576-108">Contenu du didacticiel</span><span class="sxs-lookup"><span data-stu-id="e9576-108">What You Will Learn</span></span>  
 <span data-ttu-id="e9576-109">Dans ce didacticiel, vous allez apprendre à vous déplacer dans l’interface utilisateur graphique de l’Assistant Paramétrage du moteur de base de données et également à effectuer des tâches de base en utilisant à la fois l’interface graphique et l’utilitaire **dta** .</span><span class="sxs-lookup"><span data-stu-id="e9576-109">This tutorial will teach you how to navigate the Database Engine Tuning Advisor GUI, and how to perform some basic tasks with both the GUI and the **dta** utility.</span></span> <span data-ttu-id="e9576-110">Le didacticiel comprend les leçons suivantes :</span><span class="sxs-lookup"><span data-stu-id="e9576-110">It contains the following lessons:</span></span>  
  
 [<span data-ttu-id="e9576-111">Leçon 1 : Navigation de base dans l’Assistant Paramétrage du moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="e9576-111">Lesson 1: Basic Navigation in Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/database-engine-tuning-advisor.md)  
 <span data-ttu-id="e9576-112">Au cours de cette leçon, vous allez vous familiariser avec la nouvelle interface de l'Assistant Paramétrage du moteur de base de données et apprendrez comment définir les options d'affichage et la disposition.</span><span class="sxs-lookup"><span data-stu-id="e9576-112">In this lesson, you will familiarize yourself with the new Database Engine Tuning Advisor GUI and learn how to set display options and layout.</span></span>  
  
 [<span data-ttu-id="e9576-113">Leçon 2 : Utilisation de l'Assistant Paramétrage du moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="e9576-113">Lesson 2: Using Database Engine Tuning Advisor</span></span>](lesson-2-using-database-engine-tuning-advisor.md)  
 <span data-ttu-id="e9576-114">Au cours de cette leçon, vous allez apprendre à effectuer des tâches de paramétrage de base en utilisant l'interface utilisateur de l'Assistant Paramétrage du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="e9576-114">In this lesson, you will learn how to perform basic tuning tasks with the Database Engine Tuning Advisor GUI.</span></span>  
  
 [<span data-ttu-id="e9576-115">Leçon 3 : Utilisation de l’utilitaire de ligne de commande dta</span><span class="sxs-lookup"><span data-stu-id="e9576-115">Lesson 3: Using the dta Command Prompt Utility</span></span>](lesson-3-using-the-dta-command-prompt-utility.md)  
 <span data-ttu-id="e9576-116">Au cours de cette leçon, vous allez apprendre à démarrer l’utilitaire en ligne de commande **dta** et à exécuter des commandes de paramétrage simples.</span><span class="sxs-lookup"><span data-stu-id="e9576-116">In this lesson, you learn how to start the **dta** command prompt utility and how to run some simple tuning commands.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9576-117">Spécifications</span><span class="sxs-lookup"><span data-stu-id="e9576-117">Requirements</span></span>  
 <span data-ttu-id="e9576-118">Ce didacticiel s’adresse aux administrateurs de base de données qui ne connaissent pas l’interface utilisateur de l’Assistant Paramétrage du moteur de base de données ou l’utilitaire en ligne de commande **dta** , mais qui sont des administrateurs de base de données expérimentés et qui maîtrisent les concepts et les structures propres aux bases de données comme les index et les vues indexées.</span><span class="sxs-lookup"><span data-stu-id="e9576-118">This tutorial is intended for database administrators who are not familiar with the Database Engine Tuning Advisor GUI or the **dta** command prompt utility, but who are experienced with database concepts and structures, such as indexes and indexed views.</span></span>  
  
 <span data-ttu-id="e9576-119">Vous devez installer [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] (ou version ultérieure) avec l'exemple de base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9576-119">You must install [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] (or a later version) with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="e9576-120">Pour des raisons de sécurité, les exemples de bases de données ne sont pas installés par défaut.</span><span class="sxs-lookup"><span data-stu-id="e9576-120">To enhance security, the sample databases are not installed by default.</span></span> <span data-ttu-id="e9576-121">Pour installer les exemples de bases de données, consultez [Installation des exemples SQL Server et des exemples de bases de données](http://sqlserversamples.codeplex.com).</span><span class="sxs-lookup"><span data-stu-id="e9576-121">To install the sample databases, see [Installing SQL Server Samples and Sample Databases](http://sqlserversamples.codeplex.com).</span></span>  
  
## <a name="after-you-finish-this-tutorial"></a><span data-ttu-id="e9576-122">Fin du didacticiel</span><span class="sxs-lookup"><span data-stu-id="e9576-122">After You Finish This Tutorial</span></span>  
 <span data-ttu-id="e9576-123">Une fois les leçons du didacticiel terminées, reportez-vous aux rubriques suivantes pour plus d'informations sur l'Assistant Paramétrage du moteur de base de données :</span><span class="sxs-lookup"><span data-stu-id="e9576-123">After you finish the lessons in this tutorial, refer to the following topics for more information about Database Engine Tuning Advisor:</span></span>  
  
-   <span data-ttu-id="e9576-124">[Assistant Paramétrage du moteur de base de données](../../relational-databases/performance/database-engine-tuning-advisor.md) : cette rubrique propose des descriptions de la façon d’effectuer des tâches avec cet outil.</span><span class="sxs-lookup"><span data-stu-id="e9576-124">[Database Engine Tuning Advisor](../../relational-databases/performance/database-engine-tuning-advisor.md) for descriptions of how to perform tasks with this tool.</span></span>  
  
-   <span data-ttu-id="e9576-125">[Utilitaire dta](dta-utility.md) : cette rubrique propose des documents de référence sur l’utilitaire en ligne de commande et le fichier XML facultatif que vous pouvez utiliser pour contrôler le fonctionnement de l’utilitaire.</span><span class="sxs-lookup"><span data-stu-id="e9576-125">[dta Utility](dta-utility.md) for reference material on the command prompt utility and the optional XML file you can use to control the operation of the utility.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="e9576-126">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="e9576-126">Next Lesson</span></span>  
 [<span data-ttu-id="e9576-127">Leçon 1 : Navigation de base dans l’Assistant Paramétrage du moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="e9576-127">Lesson 1: Basic Navigation in Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/database-engine-tuning-advisor.md)  
  
  
