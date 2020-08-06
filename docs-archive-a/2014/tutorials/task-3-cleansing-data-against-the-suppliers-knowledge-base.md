---
title: 'Tâche 3 : nettoyage des données par rapport à la base de connaissances fournisseurs | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 647c924a-9b91-4294-8d96-e81416e4e90e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 13201a8b904a5fc5232b9fa860710e4e39cce67a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704416"
---
# <a name="task-3-cleansing-data-against-the-suppliers-knowledge-base"></a><span data-ttu-id="bb963-102">Tâche 3 : Nettoyage des données dans la base de connaissances Fournisseurs</span><span class="sxs-lookup"><span data-stu-id="bb963-102">Task 3: Cleansing Data against the Suppliers Knowledge Base</span></span>
  <span data-ttu-id="bb963-103">Dans cette tâche, vous allez exécuter le processus de nettoyage assisté par ordinateur.</span><span class="sxs-lookup"><span data-stu-id="bb963-103">In this task, you run the computer-assisted cleansing process.</span></span> <span data-ttu-id="bb963-104">DQS utilise des algorithmes avancés et des niveaux de confiance basés sur les valeurs de seuil spécifiées pour analyser vos données par rapport à la base de connaissances sélectionnée, puis les nettoyer.</span><span class="sxs-lookup"><span data-stu-id="bb963-104">DQS uses advanced algorithms and confidence levels based on the threshold values specified to analyze the data against the selected knowledge base, and then cleanse it.</span></span> <span data-ttu-id="bb963-105">Pour plus d’informations, consultez [nettoyage des données à l’aide de la connaissance de DQS (interne)](https://msdn.microsoft.com/library/hh213061.aspx) .</span><span class="sxs-lookup"><span data-stu-id="bb963-105">See [Cleansing Data Using DQS (Internal) Knowledge](https://msdn.microsoft.com/library/hh213061.aspx) for more details.</span></span>

1.  <span data-ttu-id="bb963-106">Cliquez sur **Démarrer** pour démarrer le processus de nettoyage assisté par ordinateur.</span><span class="sxs-lookup"><span data-stu-id="bb963-106">Click **Start** to start the computer-assisted cleansing process.</span></span>

     <span data-ttu-id="bb963-107">![Page de nettoyage du processus de nettoyage](../../2014/tutorials/media/et-cleansingdataagainstthesupplierkb-01.jpg "Page de nettoyage du processus de nettoyage")</span><span class="sxs-lookup"><span data-stu-id="bb963-107">![Cleanse Page of the Cleansing Process](../../2014/tutorials/media/et-cleansingdataagainstthesupplierkb-01.jpg "Cleanse Page of the Cleansing Process")</span></span>

2.  <span data-ttu-id="bb963-108">Une fois le processus de nettoyage terminé, examinez les **statistiques** sous l’onglet **Générateur de profils** . Les statistiques sources fournissent le nombre d’enregistrements traités, le nombre d’enregistrements corrects, le nombre d’enregistrements corrects par DQS, le nombre d’enregistrements qui ont des modifications suggérées par DQS et le nombre d’enregistrements non valides.</span><span class="sxs-lookup"><span data-stu-id="bb963-108">When the cleansing process is completed, review **statistics** in the **Profiler** tab. The Source Statistics provide the number of records processed, number of records that are found to be correct, number of records that DQS corrects, number of records that have changes suggested by DQS, and the number of records that are invalid.</span></span> <span data-ttu-id="bb963-109">Dans la zone de liste située à droite, vous pouvez voir les valeurs corrigées, les valeurs suggérées et l'exhaustivité (c'est-à-dire, dans quelle mesure les données sont présentes) et la précision (c'est-à-dire, dans quelle mesure les données peuvent être utilisées à des fins précises) des valeurs de chaque domaine impliqué dans le processus de nettoyage.</span><span class="sxs-lookup"><span data-stu-id="bb963-109">In the list box to the right, you can see the corrected values, suggested values, and the completeness (the extent to which the data is present) and accuracy (the extent to which the data can be used for intended purposes) of values for each domain involved in the cleansing process.</span></span>

     <span data-ttu-id="bb963-110">![Résultats de nettoyage](../../2014/tutorials/media/et-cleansingdataagainstthesupplierkb-02.jpg "Résultats de nettoyage")</span><span class="sxs-lookup"><span data-stu-id="bb963-110">![Cleansing Results](../../2014/tutorials/media/et-cleansingdataagainstthesupplierkb-02.jpg "Cleansing Results")</span></span>

3.  <span data-ttu-id="bb963-111">Cliquez sur **suivant** pour basculer vers la page **gérer et afficher les résultats** .</span><span class="sxs-lookup"><span data-stu-id="bb963-111">Click **Next** to switch to **Manage and View Results** page.</span></span>

## <a name="next-step"></a><span data-ttu-id="bb963-112">étape suivante</span><span class="sxs-lookup"><span data-stu-id="bb963-112">Next Step</span></span>
 [<span data-ttu-id="bb963-113">Tâche 4 : Gestion et affichage des résultats</span><span class="sxs-lookup"><span data-stu-id="bb963-113">Task 4: Manaing and Viewing Results</span></span>](../../2014/tutorials/task-4-manaing-and-viewing-results.md)


