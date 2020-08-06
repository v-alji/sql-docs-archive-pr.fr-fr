---
title: Profilage des données et visionneuse, tâche | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling task [Integration Services], about data profiling
- data profiling
- profiling data
ms.assetid: 756840e3-aa09-45cd-9951-1a17af4b5925
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ae15d1cc75f8db04c36a830e44d07800c5aecf75
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604080"
---
# <a name="data-profiling-task-and-viewer"></a><span data-ttu-id="02713-102">Tâche de profilage des données et visionneuse</span><span class="sxs-lookup"><span data-stu-id="02713-102">Data Profiling Task and Viewer</span></span>
  <span data-ttu-id="02713-103">La tâche de profilage des données fournit des fonctionnalités de profilage de données à l'intérieur du processus d'extraction, de transformation et de chargement de données.</span><span class="sxs-lookup"><span data-stu-id="02713-103">The Data Profiling task provides data profiling functionality inside the process of extracting, transforming, and loading data.</span></span> <span data-ttu-id="02713-104">Grâce à la tâche de profilage des données, vous pouvez bénéficier des avantages suivants :</span><span class="sxs-lookup"><span data-stu-id="02713-104">By using the Data Profiling task, you can achieve the following benefits:</span></span>  
  
-   <span data-ttu-id="02713-105">Analyser les données sources plus efficacement</span><span class="sxs-lookup"><span data-stu-id="02713-105">Analyze the source data more effectively</span></span>  
  
-   <span data-ttu-id="02713-106">Mieux comprendre les données sources</span><span class="sxs-lookup"><span data-stu-id="02713-106">Understand the source data better</span></span>  
  
-   <span data-ttu-id="02713-107">Empêcher les problèmes de qualité des données avant qu'ils ne soient introduits dans l'entrepôt de données</span><span class="sxs-lookup"><span data-stu-id="02713-107">Prevent data quality problems before they are introduced into the data warehouse.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="02713-108">La tâche de profilage des données fonctionne uniquement avec les données stockées dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02713-108">The Data Profiling task works only with data that is stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="02713-109">Elle ne fonctionne pas avec les sources de données tierces ou basées sur des fichiers.</span><span class="sxs-lookup"><span data-stu-id="02713-109">It does not work with third-party or file-based data sources.</span></span>  
  
## <a name="data-profiling-overview"></a><span data-ttu-id="02713-110">Présentation du profilage des données</span><span class="sxs-lookup"><span data-stu-id="02713-110">Data Profiling Overview</span></span>  
 <span data-ttu-id="02713-111">La qualité des données est cruciale dans toute entreprise.</span><span class="sxs-lookup"><span data-stu-id="02713-111">Data quality is important to every business.</span></span> <span data-ttu-id="02713-112">Compte tenu du fait que les systèmes analytiques et décisionnels des entreprises sont fondés sur leurs systèmes transactionnels, la fiabilité des indicateurs de performance clés et des prédictions d'exploration de données dépend entièrement de la validité des données sur lesquelles ils sont basés.</span><span class="sxs-lookup"><span data-stu-id="02713-112">As enterprises build analytical and business intelligence systems on top of their transactional systems, the reliability of key performance indicators and of data mining predictions depends completely on the validity of the data on which they are based.</span></span> <span data-ttu-id="02713-113">Parallèlement à l'importance croissante des données valides dans la prise de décision en entreprise, le processus de validation de ces données est de plus en plus complexe.</span><span class="sxs-lookup"><span data-stu-id="02713-113">But although the importance of valid data for business decision-making is increasing, the challenge of making sure of this data's validity is also increasing.</span></span> <span data-ttu-id="02713-114">Les données affluent constamment dans l'entreprise, en provenance de systèmes et de sources variés et d'un grand nombre d'utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="02713-114">Data is streaming into the enterprise constantly from diverse systems and sources, and a large numbers of users.</span></span>  
  
 <span data-ttu-id="02713-115">Les mesures de la qualité des données peuvent être difficiles à mettre en place car elles sont spécifiques au domaine ou à l'application.</span><span class="sxs-lookup"><span data-stu-id="02713-115">Metrics for data quality can be difficult to define because they are specific to the domain or the application.</span></span> <span data-ttu-id="02713-116">Une approche commune à la définition de la qualité des données est le profilage des données.</span><span class="sxs-lookup"><span data-stu-id="02713-116">One common approach to defining data quality is data profiling.</span></span>  
  
 <span data-ttu-id="02713-117">Un profil de données est une collection de statistiques agrégées sur les données qui peut regrouper, par exemple :</span><span class="sxs-lookup"><span data-stu-id="02713-117">A data profile is a collection of aggregate statistics about data that might include the following:</span></span>  
  
-   <span data-ttu-id="02713-118">le nombre de lignes dans la table Customer ;</span><span class="sxs-lookup"><span data-stu-id="02713-118">The number of rows in the Customer table.</span></span>  
  
-   <span data-ttu-id="02713-119">le nombre de valeurs distinctes dans la colonne State ;</span><span class="sxs-lookup"><span data-stu-id="02713-119">The number of distinct values in the State column.</span></span>  
  
-   <span data-ttu-id="02713-120">le nombre de valeurs Null ou manquantes dans la colonne Zip ;</span><span class="sxs-lookup"><span data-stu-id="02713-120">The number of null or missing values in the Zip column.</span></span>  
  
-   <span data-ttu-id="02713-121">la distribution des valeurs dans la colonne City ;</span><span class="sxs-lookup"><span data-stu-id="02713-121">The distribution of values in the City column.</span></span>  
  
-   <span data-ttu-id="02713-122">la puissance de la dépendance fonctionnelle de la colonne State sur la colonne Zip (en d’autres termes, un État américain doit toujours être le même pour une valeur de code postal donnée).</span><span class="sxs-lookup"><span data-stu-id="02713-122">The strength of the functional dependency of the State column on the Zip column-that is, the state should always be the same for a given zip value.</span></span>  
  
 <span data-ttu-id="02713-123">Les statistiques fournies par un profil de données vous donnent les informations nécessaires pour minimiser de manière efficace les problèmes de qualité qui peuvent résulter de l'utilisation des données sources.</span><span class="sxs-lookup"><span data-stu-id="02713-123">The statistics that a data profile provides gives you the information that you need in order to effectively minimize the quality issues that might occur from using the source data.</span></span>  
  
## <a name="integration-services-and-data-profiling"></a><span data-ttu-id="02713-124">Integration Services et profilage des données</span><span class="sxs-lookup"><span data-stu-id="02713-124">Integration Services and Data Profiling</span></span>  
 <span data-ttu-id="02713-125">Dans [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], le processus de profilage des données comprend les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="02713-125">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], the data profiling process consist of the following steps:</span></span>  
  
 <span data-ttu-id="02713-126">**Étape 1 : Configuration de la tâche de profilage des données**</span><span class="sxs-lookup"><span data-stu-id="02713-126">**Step 1: Setting up the Data Profiling Task**</span></span>  
 <span data-ttu-id="02713-127">La tâche de profilage des données vous permet de configurer les profils à calculer.</span><span class="sxs-lookup"><span data-stu-id="02713-127">The Data Profiling task is a task that you use to configure the profiles that you want to compute.</span></span> <span data-ttu-id="02713-128">Vous exécutez ensuite le package qui contient la tâche de profilage des données pour calculer les profils.</span><span class="sxs-lookup"><span data-stu-id="02713-128">You then run the package that contains the Data Profiling task to compute the profiles.</span></span> <span data-ttu-id="02713-129">La tâche enregistre la sortie du profil au format XML dans un fichier ou une variable de package.</span><span class="sxs-lookup"><span data-stu-id="02713-129">The task saves the profile output in XML format to a file or a package variable.</span></span>  
  
 <span data-ttu-id="02713-130">**Pour plus d'informations :** [Configuration de la tâche de profilage des données](data-profiling-task.md)</span><span class="sxs-lookup"><span data-stu-id="02713-130">**For more information:** [Setup of the Data Profiling Task](data-profiling-task.md)</span></span>  
  
 <span data-ttu-id="02713-131">**Étape 2 : Vérification des profils calculés par la tâche de profilage des données**</span><span class="sxs-lookup"><span data-stu-id="02713-131">**Step 2: Reviewing the Profiles that the Data Profiling Task Computes**</span></span>  
 <span data-ttu-id="02713-132">Pour examiner les profils de données calculés par la tâche de profilage des données, vous envoyez la sortie à un fichier, puis vous utilisez la visionneuse du profil des données.</span><span class="sxs-lookup"><span data-stu-id="02713-132">To view the data profiles that the Data Profiling task computes, you send the output to a file, and then you use the Data Profile Viewer.</span></span> <span data-ttu-id="02713-133">Cette visionneuse est un utilitaire autonome qui affiche la sortie du profil, sous forme d'informations résumées et détaillées, avec en option une fonction d'exploration vers le bas.</span><span class="sxs-lookup"><span data-stu-id="02713-133">This viewer is a stand-alone utility that displays the profile output in both summary and detail format with optional drilldown capability.</span></span>  
  
 <span data-ttu-id="02713-134">**Pour plus d'informations :** [Visionneuse du profil des données](data-profile-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="02713-134">**For more information:** [Data Profile Viewer](data-profile-viewer.md)</span></span>  
  
### <a name="addition-of-conditional-logic-to-the-data-profiling-workflow"></a><span data-ttu-id="02713-135">Ajout de la logique conditionnelle au flux de travail de profilage des données</span><span class="sxs-lookup"><span data-stu-id="02713-135">Addition of Conditional Logic to the Data Profiling Workflow</span></span>  
 <span data-ttu-id="02713-136">La tâche de profilage des données n'inclut pas de fonctionnalités intégrées vous permettant d'utiliser la logique conditionnelle pour connecter cette tâche aux tâches en aval basées sur la sortie du profil.</span><span class="sxs-lookup"><span data-stu-id="02713-136">The Data Profiling task does not have built-in features that allow you to use conditional logic to connect this task to downstream tasks based on the profile output.</span></span> <span data-ttu-id="02713-137">Toutefois, vous pouvez ajouter facilement cette logique, avec un minimum de programmation, dans une tâche de script.</span><span class="sxs-lookup"><span data-stu-id="02713-137">However, you can easily add this logic, with a small amount of programming, in a Script task.</span></span> <span data-ttu-id="02713-138">Par exemple, vous pouvez définir une tâche de script qui effectue une requête XPath sur le fichier de sortie de la tâche de profilage des données.</span><span class="sxs-lookup"><span data-stu-id="02713-138">For example, the Script task could perform an XPath query against the output file of the Data Profiling task.</span></span> <span data-ttu-id="02713-139">La requête peut déterminer si le pourcentage de valeurs NULL dans une colonne particulière dépasse un certain seuil.</span><span class="sxs-lookup"><span data-stu-id="02713-139">The query could determine whether the percentage of null values in a particular column exceeds a certain threshold.</span></span> <span data-ttu-id="02713-140">Si tel est le cas, vous pouvez interrompre le package et résoudre le problème dans les données sources avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="02713-140">If the percentage exceeds the threshold, you could interrupt the package and resolve the problem in the source data before continuing.</span></span> <span data-ttu-id="02713-141">Pour plus d’informations, consultez [Incorporer une tâche de profilage des données dans le flux de travail du package](incorporate-a-data-profiling-task-in-package-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="02713-141">For more information, see [Incorporate a Data Profiling Task in Package Workflow](incorporate-a-data-profiling-task-in-package-workflow.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="02713-142">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="02713-142">Related Content</span></span>  
 [<span data-ttu-id="02713-143">Schéma du profileur de données</span><span class="sxs-lookup"><span data-stu-id="02713-143">Data Profiler Schema</span></span>](https://go.microsoft.com/fwlink/?LinkId=251524)  
  
  
