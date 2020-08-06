---
title: Liste de contrôle de préparation pour l’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0e056c95-ba06-413e-8dc1-4d411a447c3b
author: minewiskan
ms.author: owend
ms.openlocfilehash: e37b1adb6aebe5d5f8fd23f5289f52425f752a6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603155"
---
# <a name="checklist-of-preparation-for-data-mining"></a><span data-ttu-id="3d1e0-102">Liste de vérification : préparation pour l'exploration de données</span><span class="sxs-lookup"><span data-stu-id="3d1e0-102">Checklist of Preparation for Data Mining</span></span>
  <span data-ttu-id="3d1e0-103">Bien que les compléments d'exploration de données facilitent et agrémentent la création de modèles et leur expérimentation, lorsque vous devez obtenir des résultats reproductibles et utilisables, vous devez prévoir suffisamment de temps pour formuler les critères fondamentaux pour l'entreprise, ainsi que pour obtenir et préparer les données.</span><span class="sxs-lookup"><span data-stu-id="3d1e0-103">Although the Data Mining Add-ins make it fairly easy and fun to create and experiment with models, when you need to get repeatable, actionable results, you must allow adequate time for formulating basic business requirements, and for obtaining and preparing data.</span></span> <span data-ttu-id="3d1e0-104">Cette section fournit une liste de vérification pour vous aider à planifier les tâches d'inspection, et décrit les problèmes courants.</span><span class="sxs-lookup"><span data-stu-id="3d1e0-104">This section provides a checklist to help you plan your investigation, and describes common problems.</span></span>  
  
## <a name="checklist-of-data-preparation"></a><span data-ttu-id="3d1e0-105">Liste de vérification de la préparation des données</span><span class="sxs-lookup"><span data-stu-id="3d1e0-105">Checklist of Data Preparation</span></span>  
 <span data-ttu-id="3d1e0-106">**J'ai identifié un résultat bien défini.**</span><span class="sxs-lookup"><span data-stu-id="3d1e0-106">**I have identified a clearly defined output.**</span></span>  
 <span data-ttu-id="3d1e0-107">Disposer d'un plan pour la façon dont vous allez utiliser les résultats.</span><span class="sxs-lookup"><span data-stu-id="3d1e0-107">Have a plan for how you will use the results.</span></span> <span data-ttu-id="3d1e0-108">Les différents types de modèles génèrent des résultats différents.</span><span class="sxs-lookup"><span data-stu-id="3d1e0-108">Different types of models have different outputs.</span></span> <span data-ttu-id="3d1e0-109">Un modèle de série chronologique génère des valeurs d'une série dans le futur, qui sont facilement compréhensible et utilisables.</span><span class="sxs-lookup"><span data-stu-id="3d1e0-109">A time series model generates values for a series in the future, which are easily understood and acted on.</span></span> <span data-ttu-id="3d1e0-110">D'autres modèles génèrent des jeux complexes qui doivent être analysés par des experts techniques pour obtenir la plus grande valeur.</span><span class="sxs-lookup"><span data-stu-id="3d1e0-110">Other models generate complex sets that must be analyzed by subject matter experts to yield the most value.</span></span>  
  
-   <span data-ttu-id="3d1e0-111">Quel résultat voulez-vous ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-111">What output do you want?</span></span>  
  
-   <span data-ttu-id="3d1e0-112">Pouvez-vous définir la sortie en tant que colonne ou valeur unique, ou tout autre résultat utilisable ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-112">Can you define the output as a single column or value, or other actionable result?</span></span>  
  
-   <span data-ttu-id="3d1e0-113">Quels sont les critères pour savoir que le modèle est utile ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-113">What are your criteria for knowing that the model was useful?</span></span>  
  
-   <span data-ttu-id="3d1e0-114">Comment allez-vous utiliser et interpréter ces résultats ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-114">How will you use and interpret those results?</span></span>  
  
-   <span data-ttu-id="3d1e0-115">Pouvez-vous mapper les nouvelles données d'entrée aux résultats attendus ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-115">Can you map new input data to the expected results?</span></span>  
  
 <span data-ttu-id="3d1e0-116">**Je connais la signification, les types de données et la distribution des données d'entrée.**</span><span class="sxs-lookup"><span data-stu-id="3d1e0-116">**I know the meaning, data types, and distribution of the input data.**</span></span>  
 <span data-ttu-id="3d1e0-117">Prenez le temps d'explorer et comprendre vos données source.</span><span class="sxs-lookup"><span data-stu-id="3d1e0-117">Take some time to explore and understand your source data.</span></span> <span data-ttu-id="3d1e0-118">Il est important que les personnes qui examinent le modèle comprennent le type de données d'entrée qui a été utilisé et sachent interpréter les types de données et la variabilité, ainsi que l'équilibre et la qualité.</span><span class="sxs-lookup"><span data-stu-id="3d1e0-118">It is important that people who review the model understand what kind of input data was used and know how to interpret the data types and the variability, as well as the balance and the quality.</span></span>  
  
-   <span data-ttu-id="3d1e0-119">De quel volume de données disposez-vous ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-119">How much data do you have?</span></span> <span data-ttu-id="3d1e0-120">Les données sont-elles suffisantes pour la modélisation ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-120">Is there sufficient data for modeling?</span></span>  
  
     <span data-ttu-id="3d1e0-121">Il n’est pas nécessaire qu’il soit très petit et équilibré.</span><span class="sxs-lookup"><span data-stu-id="3d1e0-121">It need not be a huge amount - smaller and balanced can be better.</span></span>  
  
-   <span data-ttu-id="3d1e0-122">Les données proviennent-elles de plusieurs sources, ou d'une seule source ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-122">Is the data from multiple sources, or a single source?</span></span>  
  
-   <span data-ttu-id="3d1e0-123">Est-ce-que les données sont déjà traitée et nettoyées ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-123">Is the data already processed and clean?</span></span> <span data-ttu-id="3d1e0-124">Des données d'entrée supplémentaires sont-elles disponibles ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-124">Is more input data available?</span></span>  
  
-   <span data-ttu-id="3d1e0-125">Savez-vous comment il a été manipulé avant de le recevoir, comment les données ont peut-être été tronquées, résumées ou converties ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-125">Do you know how it was manipulated before you received it - how data might have been truncated, summarized, or converted?</span></span>  
  
-   <span data-ttu-id="3d1e0-126">Les données d'entrée ont-elles des exemples de résultats qui peuvent être utilisés pour l'apprentissage ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-126">Does the input data have some example results that can be used for training?</span></span>  
  
 <span data-ttu-id="3d1e0-127">**Je comprends le niveau d'intégrité des données dont nous disposons et celui dont nous avons besoin.**</span><span class="sxs-lookup"><span data-stu-id="3d1e0-127">**I understand the level of data integrity we have and the level we need.**</span></span>  
 <span data-ttu-id="3d1e0-128">Des données incorrectes peuvent affecter la qualité du modèle ou empêcher la génération du modèle.</span><span class="sxs-lookup"><span data-stu-id="3d1e0-128">Bad data can affect the quality of the model, or prevent the model from being built at all.</span></span> <span data-ttu-id="3d1e0-129">Vous devez avoir une bonne compréhension de la distribution et de la signification des données, et de la manière dont elles sont parvenues à cet état.</span><span class="sxs-lookup"><span data-stu-id="3d1e0-129">You should have a good understanding of both the distribution and meaning of the data, and how it came to this state.</span></span> <span data-ttu-id="3d1e0-130">Vous devez comprendre s’il est possible ou approprié de simplifier les données en les étiquetant, en tronquant les types de données numériques ou en les résumant.</span><span class="sxs-lookup"><span data-stu-id="3d1e0-130">You'll need to understand if it is possible or appropriate to simplify the data by labeling, truncating numeric data types, or by summarizing.</span></span>  
  
-   <span data-ttu-id="3d1e0-131">Étiquettes de données : sont-elles claires et correctes ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-131">Data labels: are they clear and correct?</span></span>  
  
-   <span data-ttu-id="3d1e0-132">Types de données : sont-ils appropriés et ont-ils été modifiés ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-132">Data types: are they appropriate, and have they been changed?</span></span>  
  
-   <span data-ttu-id="3d1e0-133">Avez-vous trié, nettoyé ou ignoré les données incorrectes ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-133">Have you sorted, cleaned up, or discarded wrong data?</span></span>  
  
     <span data-ttu-id="3d1e0-134">Avez-vous vérifié qu'il n'y a pas de doublons ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-134">Have you verified there are no duplicates?</span></span>  
  
-   <span data-ttu-id="3d1e0-135">Comment allez-vous gérer les valeurs manquantes ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-135">How will you handle missing values?</span></span> <span data-ttu-id="3d1e0-136">Les valeurs manquantes ont-elles une signification ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-136">Do missing values have a meaning?</span></span>  
  
-   <span data-ttu-id="3d1e0-137">Avez-vous vérifié les sources pour déterminer si des erreurs ont été introduites lors du processus d'importation ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-137">Have you verified the sources to see if any errors might have been introduced in the import process?</span></span>  
  
     <span data-ttu-id="3d1e0-138">Où sont stockées les données d'entrée ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-138">Where is the input stored?</span></span> <span data-ttu-id="3d1e0-139">Combien de temps resteront-elles disponibles ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-139">How long does it stay available?</span></span>  
  
     <span data-ttu-id="3d1e0-140">Existe-t-il un dictionnaire des données ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-140">Is there a data dictionary?</span></span> <span data-ttu-id="3d1e0-141">Pouvez-vous en créer un ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-141">Can you create one?</span></span>  
  
-   <span data-ttu-id="3d1e0-142">Si vous avez combiné des jeux de données, avez-vous recherché plusieurs colonnes représentant les mêmes données ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-142">If you combined data sets, did you check for multiple columns representing the same data?</span></span>  
  
 <span data-ttu-id="3d1e0-143">**Je sais où les données sources sont stockées, où elles proviennent et comment elles sont traitées. Le processus peut être répété facilement si nécessaire.**</span><span class="sxs-lookup"><span data-stu-id="3d1e0-143">**I know where source data is stored, where it came from, and how it is processed. The process can be easily repeated if needed.**</span></span>  
 <span data-ttu-id="3d1e0-144">Les jeux de données uniques sont corrects pour les expériences, mais si vous souhaitez déplacer le modèle en production, pensez à l’avance sur la façon dont le processus de nettoyage peut être appliqué aux données opérationnelles.</span><span class="sxs-lookup"><span data-stu-id="3d1e0-144">One-off data sets are fine for experiments, but if you ever want to move the model into production, you'll want to think in advance about how the cleaning process can be applied to operational data.</span></span> <span data-ttu-id="3d1e0-145">En outre, si vous avez des données opérationnelles, vous devez savoir comment elles peuvent avoir été altérées avant de vous y avoir. vous devez savoir comment elles ont été arrondies, ou résumées, certainement.</span><span class="sxs-lookup"><span data-stu-id="3d1e0-145">Also, if you have operational data, you need to know how it might have been altered before you got it-you'll need to know how it was rounded, or summarized, certainly.</span></span>  
  
-   <span data-ttu-id="3d1e0-146">Voulez-vous être en mesure de répéter l'expérience ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-146">Do you want to be able to repeat the experiment?</span></span>  
  
-   <span data-ttu-id="3d1e0-147">Quels outils utiliserez-vous pour préparer les données dans un format qui prend en charge l'analyse de données ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-147">What tools will you use to prepare data in a format that supports data analysis?</span></span> <span data-ttu-id="3d1e0-148">Peut-il être automatisé ou avez-vous besoin de quelqu'un pour la vérification et le nettoyage dans Excel ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-148">Can it be automated or do you need someone to review and clean up in Excel?</span></span>  
  
-   <span data-ttu-id="3d1e0-149">Si les données proviennent d'un autre système, serez-vous en mesure de capturer et suivre les filtres appliqués ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-149">If you are sourcing data from another system, will you be able to capture and track filters that were applied?</span></span>  
  
-   <span data-ttu-id="3d1e0-150">Votre infrastructure de traitement des données peut-elle également appliquer des algorithmes d'apprentissage automatique, réaliser des tests et visualiser les résultats ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-150">Can your data processing framework also apply machine learning algorithms, perform tests, and visualize results?</span></span>  
  
 <span data-ttu-id="3d1e0-151">**Nous nous sommes entendus sur la granularité souhaitée des prédictions et nos données ont été modifiées pour obtenir ces unités.**</span><span class="sxs-lookup"><span data-stu-id="3d1e0-151">**We have agreed on the desired granularity of predictions and our data has been modified to output those units.**</span></span>  
 <span data-ttu-id="3d1e0-152">Décidez de la granularité des résultats que vous recherchez avant de préparer des données. Par exemple, avez-vous besoin des prédictions de ventes chaque jour ou pour chaque trimestre ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-152">Decide on the granularity of the results you want before preparing data, For example, do you want sales predictions by the day, or for each quarter?</span></span> <span data-ttu-id="3d1e0-153">Envisagez éventuellement de configurer différentes structures de données pour les mêmes données de façon à gérer différents niveaux de résumé.</span><span class="sxs-lookup"><span data-stu-id="3d1e0-153">You might consider setting up different data structures for the same data, to handle different levels of summary.</span></span>  
  
-   <span data-ttu-id="3d1e0-154">Quelle est l'unité de mesure ou l'unité de temps actuelle ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-154">What is the current unit of measure or unit of time?</span></span>  
  
     <span data-ttu-id="3d1e0-155">Quelle unité souhaitez-vous utiliser dans les résultats ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-155">What unit do you want to use in the results?</span></span>  
  
-   <span data-ttu-id="3d1e0-156">Est-il possible de définir une unité de base (par exemple, jour/heure/min/instruction call) pour toutes les données d’entrée ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-156">Is it possible to define a basic unit (e.g. day/ hour / min / instruction call) for all input data?</span></span>  
  
     <span data-ttu-id="3d1e0-157">Voulez-vous effectuer le cumul aux unités supérieures ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-157">Do you want to rollup to higher units?</span></span>  
  
-   <span data-ttu-id="3d1e0-158">Est-ce-que les catégories sont étiquetées de façon cohérente ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-158">Are categories labeled consistently?</span></span> <span data-ttu-id="3d1e0-159">Est-il facile d'ajouter ou de supprimer des catégories ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-159">Is it easy to add or remove categories?</span></span>  
  
 <span data-ttu-id="3d1e0-160">**Notre conception expérimentale est renouvelable et reproductible.**</span><span class="sxs-lookup"><span data-stu-id="3d1e0-160">**Our experimental design is repeatable and reproducible.**</span></span>  
 <span data-ttu-id="3d1e0-161">Tenez compte des stratégies pour analyser et valider vos résultats et planifier la capturer d'un instantané des données, pour garantir que vous pouvez tracer les effets sur les données.</span><span class="sxs-lookup"><span data-stu-id="3d1e0-161">Consider strategies for analyzing and validating your results and plan to capture a data snapshot, to make sure you can trace back effects to data.</span></span> <span data-ttu-id="3d1e0-162">Si une valeur de départ aléatoire est utilisée, les résultats peuvent légèrement différer.</span><span class="sxs-lookup"><span data-stu-id="3d1e0-162">If a random seed is used, the results can differ subtly.</span></span> <span data-ttu-id="3d1e0-163">Cela peut rendre la difficile la comparaison et la validation des modèles.</span><span class="sxs-lookup"><span data-stu-id="3d1e0-163">This can make it difficult to compare and validate models.</span></span>  
  
-   <span data-ttu-id="3d1e0-164">Si vous apportez de nombreuses modifications personnalisées aux données, que se passera-t-il la prochaine fois que vous souhaiterez créer le modèle ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-164">If you make a lot of custom changes to the data, what happens the next time you want to build the model?</span></span>  
  
-   <span data-ttu-id="3d1e0-165">Une procédure manuelle ou un processus approuvé que vous devez utiliser pour traiter les données d'entrée et obtenir le résultat souhaité a-t-il déjà été défini ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-165">Has a manual procedure or approved process already been defined that you should use to process input and get the desired outputs?</span></span>  
  
-   <span data-ttu-id="3d1e0-166">Avez-vous décidé d'utiliser une valeur initiale pour le modèle ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-166">Have you decided to use a seed for the model?</span></span>  
  
 <span data-ttu-id="3d1e0-167">**Nous disposons des connaissances dans le domaine pour valider les résultats, ou nous avons accès à des experts techniques qui peuvent nous conseiller.**</span><span class="sxs-lookup"><span data-stu-id="3d1e0-167">**We have the domain knowledge to validate the results, or have access to subject matter experts who can advise.**</span></span>  
 <span data-ttu-id="3d1e0-168">Prenez le temps de valider les variables, le modèle et les résultats.</span><span class="sxs-lookup"><span data-stu-id="3d1e0-168">Take time to validate the variables, the model, and the results.</span></span> <span data-ttu-id="3d1e0-169">Obtenez de l'aide auprès d'experts pour évaluer les interactions et les résultats.</span><span class="sxs-lookup"><span data-stu-id="3d1e0-169">Get the help of experts to assess interactions and results.</span></span> <span data-ttu-id="3d1e0-170">Toutefois, ne laissez pas les hypothèses prioritaires sur les preuves.</span><span class="sxs-lookup"><span data-stu-id="3d1e0-170">However, don't let assumptions overrule evidence.</span></span> <span data-ttu-id="3d1e0-171">Soyez ouvert aux résultats nouveaux et inattendus.</span><span class="sxs-lookup"><span data-stu-id="3d1e0-171">Be open to new and unexpected findings.</span></span>  
  
-   <span data-ttu-id="3d1e0-172">La connaissance de domaine est-elle disponible pour faciliter le filtrage des données et réduire le bruit des données d'entrée ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-172">Is domain knowledge available to help in filtering data and reducing input noise?</span></span>  
  
-   <span data-ttu-id="3d1e0-173">Est-ce-que les experts en matière de domaine aident à comprendre et interpréter les résultats et proposent des améliorations ?</span><span class="sxs-lookup"><span data-stu-id="3d1e0-173">Can domain experts help understand interpret the results and suggest improvements?</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d1e0-174">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3d1e0-174">See Also</span></span>  
 [<span data-ttu-id="3d1e0-175">Choisir les données pour l'exploration de données</span><span class="sxs-lookup"><span data-stu-id="3d1e0-175">Choosing Data for Data Mining</span></span>](choosing-data-for-data-mining.md)  
  
  
