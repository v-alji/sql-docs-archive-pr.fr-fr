---
title: 'Leçon 2 : nettoyage des données des fournisseurs à l’aide de la base de connaissances fournisseurs | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 215c14de-fc3f-46de-a022-bf69b9ea2a96
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ebc0231cd0f28fcad23656cf22abd8d68eca7dc4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600412"
---
# <a name="lesson-2-cleansing-supplier-data-using-the-suppliers-knowledge-base"></a><span data-ttu-id="b1338-102">Leçon 2 : Nettoyage des données des fournisseurs avec la base de connaissances Fournisseurs</span><span class="sxs-lookup"><span data-stu-id="b1338-102">Lesson 2: Cleansing Supplier Data using the Suppliers Knowledge Base</span></span>
  <span data-ttu-id="b1338-103">Dans cette leçon, vous allez nettoyer les données des fournisseurs dans un fichier Excel à l’aide de la base de connaissances **fournisseurs** que vous avez créée dans la première leçon.</span><span class="sxs-lookup"><span data-stu-id="b1338-103">In this lesson, you cleanse the supplier data in an Excel file by using the **Suppliers** knowledge base you have created in the first lesson.</span></span> <span data-ttu-id="b1338-104">Le nettoyage de données dans DQS comprend un **processus assisté par ordinateur** qui analyse la conformité des données aux connaissances dans une base de connaissances et un **processus interactif** qui vous permet d’examiner et de modifier les résultats du processus assisté par ordinateur.</span><span class="sxs-lookup"><span data-stu-id="b1338-104">Data cleansing in DQS includes a **computer-assisted process** that analyzes how data conforms to the knowledge in a knowledge base, and an **interactive process** that enables you to review and modify results from the computer-assisted process.</span></span> <span data-ttu-id="b1338-105">La fonctionnalité de nettoyage des données identifie les données incorrectes dans votre source de données et les corrige, ou suggère des corrections.</span><span class="sxs-lookup"><span data-stu-id="b1338-105">The data cleansing feature identifies incorrect data in your data source and then corrects or suggests corrections for the incorrect data.</span></span> <span data-ttu-id="b1338-106">Elle normalise et enrichit également les données client en utilisant des valeurs de domaine, des valeurs menantes pour les synonymes, des règles de domaine, des relations à base de termes et des données de référence.</span><span class="sxs-lookup"><span data-stu-id="b1338-106">It also standardizes and enriches customer data by using domain values, leading values for synonyms, domain rules, term-based relations, and reference data.</span></span> <span data-ttu-id="b1338-107">Vous pouvez approuver ou refuser en mode interactif les modifications proposées par le processus assisté par ordinateur.</span><span class="sxs-lookup"><span data-stu-id="b1338-107">You can interactively approve or reject changes proposed by the computer-assisted process.</span></span> <span data-ttu-id="b1338-108">Pour plus d’informations, consultez [nettoyage des données](https://msdn.microsoft.com/library/gg524800.aspx) .</span><span class="sxs-lookup"><span data-stu-id="b1338-108">See [Data Cleansing](https://msdn.microsoft.com/library/gg524800.aspx) for more details.</span></span>  
  
 <span data-ttu-id="b1338-109">Le processus assisté par ordinateur utilise les valeurs de seuil suivantes, que vous pouvez configurer à l'aide de l'option Configuration dans la page principale du Client DQS.</span><span class="sxs-lookup"><span data-stu-id="b1338-109">The computer-assisted process uses the following threshold values that you can configure using the Configuration option on the DQS Client main page.</span></span>  
  
-   <span data-ttu-id="b1338-110">**Score minimal pour les suggestions :** Score minimal ou niveau de confiance qui est utilisé par DQS pour suggérer le remplacement d’une valeur.</span><span class="sxs-lookup"><span data-stu-id="b1338-110">**Min score for suggestions:** The minimum score or confidence level that is used by DQS for suggesting replacement for a value.</span></span>  
  
-   <span data-ttu-id="b1338-111">**Score minimal pour les corrections automatiques :** Score minimal ou niveau de confiance qui est utilisé par DQS pour corriger automatiquement une valeur.</span><span class="sxs-lookup"><span data-stu-id="b1338-111">**Min score for auto corrections:** The minimum score or confidence level that is used by DQS for automatically correcting a value.</span></span>  
  
 <span data-ttu-id="b1338-112">Pour plus d’informations sur la configuration de ces paramètres [, consultez Configurer les valeurs de seuil pour le nettoyage et la correspondance](https://msdn.microsoft.com/library/hh510415.aspx) .</span><span class="sxs-lookup"><span data-stu-id="b1338-112">See [Configure Threshold Values for Cleansing and Matching](https://msdn.microsoft.com/library/hh510415.aspx) for details on how to configure these settings.</span></span>  
  
 <span data-ttu-id="b1338-113">Dans cette leçon, vous allez effectuer les tâches suivantes pour nettoyer les données d'entrée à l'aide de la base de connaissances Fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="b1338-113">In this lesson, you perform the following tasks to cleanse the input data by using the Suppliers knowledge base.</span></span>  
  
1.  <span data-ttu-id="b1338-114">Créer un projet de qualité des données pour le nettoyage, sélectionner la base de connaissances Fournisseurs comme base de connaissances à utiliser pour analyser et nettoyer les données sources dans un fichier Excel, puis sélectionner l'activité de nettoyage.</span><span class="sxs-lookup"><span data-stu-id="b1338-114">Create a Data Quality Project for Cleansing, select the Suppliers knowledge base as the knowledge base to use to analyze and cleanse the source data in an Excel file, and select the Cleansing activity.</span></span>  
  
2.  <span data-ttu-id="b1338-115">Mapper les colonnes Excel que vous souhaitez nettoyer aux domaines/domaines composites DQS appropriés dans la base de connaissances.</span><span class="sxs-lookup"><span data-stu-id="b1338-115">Map the Excel columns that you want to cleanse to appropriate DQS domains/composite domains in the knowledge base.</span></span>  
  
3.  <span data-ttu-id="b1338-116">Exécuter l'activité de nettoyage assistée par ordinateur.</span><span class="sxs-lookup"><span data-stu-id="b1338-116">Run the computer-assisted cleansing activity.</span></span> <span data-ttu-id="b1338-117">Le processus assisté par ordinateur affiche les informations de qualité des données dans le Data Quality Client utilisé pour nettoyer les données de façon interactive.</span><span class="sxs-lookup"><span data-stu-id="b1338-117">The computer-assisted process displays data quality information in the Data Quality Client that you can use to cleanse the data interactively.</span></span>  
  
4.  <span data-ttu-id="b1338-118">Affichez et gérez les résultats de l'activité de nettoyage.</span><span class="sxs-lookup"><span data-stu-id="b1338-118">View and manage the results of the cleansing activity.</span></span> <span data-ttu-id="b1338-119">Vous pouvez examiner les valeurs qui le processus assisté par ordinateur identifie comme correctes, incorrectes mais corrigées, incorrectes avec une modification suggérée, ou non valides.</span><span class="sxs-lookup"><span data-stu-id="b1338-119">You can review the values that the computer-assisted process finds to be correct, incorrect but corrected, incorrect with a suggested change, or invalid.</span></span> <span data-ttu-id="b1338-120">Vous pouvez approuver ou refuser de façon interactive les modifications, ou corriger ou remplacer la suggestion du processus assisté par ordinateur, en utilisant le champ Corriger vers.</span><span class="sxs-lookup"><span data-stu-id="b1338-120">You can interactively approve or reject changes, correcting or overriding the suggestion from the computer-assisted process by using the Correct To field.</span></span>  
  
5.  <span data-ttu-id="b1338-121">Exporter les résultats du nettoyage dans un fichier Excel.</span><span class="sxs-lookup"><span data-stu-id="b1338-121">Export the results from the cleansing process to an Excel file.</span></span>  
  
6.  <span data-ttu-id="b1338-122">Importez les valeurs du projet de nettoyage dans des domaines pour augmenter la connaissance dans la base de connaissances avec de nouvelles règles, valeurs, corrections, etc.</span><span class="sxs-lookup"><span data-stu-id="b1338-122">Import the values from the cleansing project into domains to augment the knowledge in the knowledge base with new rules, values, corrections etc...</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="b1338-123">étape suivante</span><span class="sxs-lookup"><span data-stu-id="b1338-123">Next Step</span></span>  
 [<span data-ttu-id="b1338-124">Tâche 1 : Création d’un projet de qualité des données</span><span class="sxs-lookup"><span data-stu-id="b1338-124">Task 1: Creating a Data Quality Project</span></span>](../../2014/tutorials/task-1-creating-a-data-quality-project.md)  
  
  
