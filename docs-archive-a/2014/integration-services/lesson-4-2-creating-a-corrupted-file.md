---
title: 'Étape 2 : Création d’un fichier endommagé | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: cd0b18dc-66c3-4d88-86ef-8e40cb660fae
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0dd5fbe942774192881489e9ea430672f9da5083
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604625"
---
# <a name="step-2-creating-a-corrupted-file"></a><span data-ttu-id="4e0ef-102">Étape 2 : Création d’un fichier corrompu</span><span class="sxs-lookup"><span data-stu-id="4e0ef-102">Step 2: Creating a Corrupted File</span></span>
  <span data-ttu-id="4e0ef-103">Afin de démontrer l'utilisation des fonctions de configuration et de gestion des erreurs de transformation, vous allez devoir créer un exemple de fichier plat qui, lors de son traitement, entraîne l'échec d'un composant.</span><span class="sxs-lookup"><span data-stu-id="4e0ef-103">In order to demonstrate the configuration and handling of transformation errors, you will have to create a sample flat file that when processed causes a component to fail.</span></span>  
  
 <span data-ttu-id="4e0ef-104">Au cours de cette tâche, vous allez créer une copie d'un fichier plat existant.</span><span class="sxs-lookup"><span data-stu-id="4e0ef-104">In this task, you will create a copy of an existing sample flat file.</span></span> <span data-ttu-id="4e0ef-105">Vous ouvrirez ensuite ce fichier dans le Bloc-notes et modifierez la colonne **CurrencyID** pour vous assurer qu'aucune correspondance ne peut être établie au cours de la recherche de transformations.</span><span class="sxs-lookup"><span data-stu-id="4e0ef-105">You will then open the file in Notepad and edit the **CurrencyID** column to ensure that it will fail to produce a match during the transformations lookup.</span></span> <span data-ttu-id="4e0ef-106">Lors du traitement du nouveau fichier, l'échec de la recherche provoquera à son tour l'échec de la transformation Lookup Currency Key et, par conséquent, celui du reste du package.</span><span class="sxs-lookup"><span data-stu-id="4e0ef-106">When the new file is processed, the lookup failure will cause the Currency Key Lookup transformation to fail and therefore fail the rest of the package.</span></span> <span data-ttu-id="4e0ef-107">Une fois le fichier exemple corrompu créé, vous exécuterez le package pour examiner son échec.</span><span class="sxs-lookup"><span data-stu-id="4e0ef-107">After you have created the corrupted sample file, you will run the package to view the package failure.</span></span>  
  
### <a name="to-create-a-corrupted-sample-flat-file"></a><span data-ttu-id="4e0ef-108">Pour créer un fichier plat exemple corrompu</span><span class="sxs-lookup"><span data-stu-id="4e0ef-108">To create a corrupted sample flat file</span></span>  
  
1.  <span data-ttu-id="4e0ef-109">Dans le Bloc-notes ou un autre éditeur de texte, ouvrez le fichier Currency_VEB.txt.</span><span class="sxs-lookup"><span data-stu-id="4e0ef-109">In Notepad or any other text editor, open the Currency_VEB.txt file.</span></span>  
  
     <span data-ttu-id="4e0ef-110">Les exemples de données sont inclus dans les packages de leçons SSIS.</span><span class="sxs-lookup"><span data-stu-id="4e0ef-110">The sample data is included with the SSIS Lesson packages.</span></span> <span data-ttu-id="4e0ef-111">Pour télécharger ces exemples de données et les packages de leçons, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="4e0ef-111">To download the sample data and the lesson packages, do the following.</span></span>  
  
    1.  <span data-ttu-id="4e0ef-112">Accédez à [Integration Services exemples de produits](https://go.microsoft.com/fwlink/?LinkID=267527).</span><span class="sxs-lookup"><span data-stu-id="4e0ef-112">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkID=267527).</span></span>  
  
    2.  <span data-ttu-id="4e0ef-113">Cliquez sur l’onglet **téléchargements** .</span><span class="sxs-lookup"><span data-stu-id="4e0ef-113">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="4e0ef-114">Cliquez sur le fichier SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="4e0ef-114">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
2.  <span data-ttu-id="4e0ef-115">Utilisez la fonctionnalité Rechercher et remplacer de l’éditeur de texte pour rechercher toutes les instances de `VEB` et les remplacer par `BAD` .</span><span class="sxs-lookup"><span data-stu-id="4e0ef-115">Use the text editor's find and replace feature to find all instances of `VEB` and replace them with `BAD`.</span></span>  
  
3.  <span data-ttu-id="4e0ef-116">Dans le même dossier que les autres exemples de fichiers de données, enregistrez le fichier modifié sous `Currency_BAD.txt` .</span><span class="sxs-lookup"><span data-stu-id="4e0ef-116">In the same folder as the other sample data files, save the modified file as `Currency_BAD.txt`.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="4e0ef-117">Assurez-vous que `Currency_BAD.txt` est enregistré dans le même dossier que les autres exemples de fichiers de données.</span><span class="sxs-lookup"><span data-stu-id="4e0ef-117">Make sure that `Currency_BAD.txt` is saved the same folder as the other sample data files.</span></span>  
  
4.  <span data-ttu-id="4e0ef-118">Fermez l'éditeur de texte.</span><span class="sxs-lookup"><span data-stu-id="4e0ef-118">Close your text editor.</span></span>  
  
### <a name="to-verify-that-an-error-will-occur-during-run-time"></a><span data-ttu-id="4e0ef-119">Pour vérifier si une erreur se produit au moment de l'exécution</span><span class="sxs-lookup"><span data-stu-id="4e0ef-119">To verify that an error will occur during run time</span></span>  
  
1.  <span data-ttu-id="4e0ef-120">Dans le menu **Déboguer**, cliquez sur **Démarrer le débogage**.</span><span class="sxs-lookup"><span data-stu-id="4e0ef-120">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
     <span data-ttu-id="4e0ef-121">À la troisième itération du flux de données, la transformation Lookup Currency Key tente de traiter le fichier Currency_BAD.txt et la transformation échoue.</span><span class="sxs-lookup"><span data-stu-id="4e0ef-121">On the third iteration of the data flow, the Lookup Currency Key transformation tries to process the Currency_BAD.txt file, and the transformation will fail.</span></span> <span data-ttu-id="4e0ef-122">L'échec de la transformation entraîne l'échec de tout le package.</span><span class="sxs-lookup"><span data-stu-id="4e0ef-122">The failure of the transformation will cause the whole package to fail.</span></span>  
  
2.  <span data-ttu-id="4e0ef-123">Dans le menu **Déboguer**, cliquez sur **Arrêter le débogage**.</span><span class="sxs-lookup"><span data-stu-id="4e0ef-123">On the **Debug** menu, click **Stop Debugging**.</span></span>  
  
3.  <span data-ttu-id="4e0ef-124">Dans la zone de conception, cliquez sur l'onglet **Résultats d'exécution** .</span><span class="sxs-lookup"><span data-stu-id="4e0ef-124">On the design surface, click the **Execution Results** tab.</span></span>  
  
4.  <span data-ttu-id="4e0ef-125">Parcourez le journal et vérifiez si les erreurs non gérées suivantes se sont produites :</span><span class="sxs-lookup"><span data-stu-id="4e0ef-125">Browse through the log and verify that the following unhandled error occurred:</span></span>  
  
     `[Lookup Currency Key[27]] Error: Row yielded no match during lookup.`  
  
    > [!NOTE]  
    >  <span data-ttu-id="4e0ef-126">Le nombre 27 désigne l'ID du composant.</span><span class="sxs-lookup"><span data-stu-id="4e0ef-126">The number 27 is the ID of the component.</span></span> <span data-ttu-id="4e0ef-127">Cette valeur est attribuée lors de la création du flux de données ; la valeur définie dans votre package peut être différente.</span><span class="sxs-lookup"><span data-stu-id="4e0ef-127">This value is assigned when you build the data flow, and the value in your package may be different.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4e0ef-128">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="4e0ef-128">Next Steps</span></span>  
 [<span data-ttu-id="4e0ef-129">Étape 3 : Ajout de redirection de flux d’erreurs</span><span class="sxs-lookup"><span data-stu-id="4e0ef-129">Step 3: Adding Error Flow Redirection</span></span>](lesson-4-3-adding-error-flow-redirection.md)  
  
  
