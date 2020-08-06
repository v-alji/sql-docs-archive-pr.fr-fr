---
title: 'Étape 4 : Ajout d’une tâche de flux de données au package | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 96af3073-8f11-4444-b934-fe8613a2d084
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4fda1de99e9fcaa683f9063e2feb1b71886a5cd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605583"
---
# <a name="step-4-adding-a-data-flow-task-to-the-package"></a><span data-ttu-id="fc2f1-102">Étape 4 : Ajout d’une tâche de flux de données au package</span><span class="sxs-lookup"><span data-stu-id="fc2f1-102">Step 4: Adding a Data Flow Task to the Package</span></span>
  <span data-ttu-id="fc2f1-103">Après avoir créé des gestionnaires de connexions pour les données sources et de destination, la tâche suivante consiste à ajouter une tâche de flux de données à votre package.</span><span class="sxs-lookup"><span data-stu-id="fc2f1-103">After you have created the connection managers for the source and destination data, the next task is to add a Data Flow task to your package.</span></span> <span data-ttu-id="fc2f1-104">La tâche de flux de données permet d'encapsuler le moteur de flux de données qui déplace les données entre les sources et les destinations et fournit la fonctionnalité grâce à laquelle il est possible de transformer, nettoyer et modifier les données lors de leur déplacement.</span><span class="sxs-lookup"><span data-stu-id="fc2f1-104">The Data Flow task encapsulates the data flow engine that moves data between sources and destinations, and provides the functionality for transforming, cleaning, and modifying data as it is moved.</span></span> <span data-ttu-id="fc2f1-105">La tâche de flux de données est l'endroit où s'effectue la majorité du travail d'un processus d'extraction, de transformation et de chargement (ETL).</span><span class="sxs-lookup"><span data-stu-id="fc2f1-105">The Data Flow task is where most of the work of an extract, transform, and load (ETL) process occurs.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]<span data-ttu-id="fc2f1-106">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]sépare le workflow du Workflow.</span><span class="sxs-lookup"><span data-stu-id="fc2f1-106">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] separates data flow from control flow.</span></span>  
  
### <a name="to-add-a-data-flow-task"></a><span data-ttu-id="fc2f1-107">Pour ajouter une tâche de flux de données</span><span class="sxs-lookup"><span data-stu-id="fc2f1-107">To add a Data Flow task</span></span>  
  
1.  <span data-ttu-id="fc2f1-108">Cliquez sur l'onglet **Flux de contrôle** .</span><span class="sxs-lookup"><span data-stu-id="fc2f1-108">Click the **Control Flow** tab.</span></span>  
  
2.  <span data-ttu-id="fc2f1-109">Dans la **Boîte à outils SSIS**, développez **Favoris**, puis faites glisser une **tâche de flux de données** sur l’aire de conception de l’onglet **Flux de contrôle** .</span><span class="sxs-lookup"><span data-stu-id="fc2f1-109">In the **SSIS Toolbox**, expand **Favorites**, and drag a **Data Flow Task** onto the design surfaceof the **Control Flow** tab.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fc2f1-110">Si la boîte à outils SSIS n’est pas disponible, dans le menu principal, sélectionnez SSIS, puis Boîte à outils SSIS pour afficher cette dernière.</span><span class="sxs-lookup"><span data-stu-id="fc2f1-110">If the SSIS Toolbox isn't available, on the main menu select SSIS then SSIS Toolbox to display the SSIS Toolbox.</span></span>  
  
3.  <span data-ttu-id="fc2f1-111">Sur l’aire de conception du **Workflow de contrôle** , cliquez avec le bouton droit sur la tâche de nouveau projet de **Workflow**, cliquez sur **Renommer**, puis remplacez le nom par `Extract Sample Currency Data` .</span><span class="sxs-lookup"><span data-stu-id="fc2f1-111">On the **Control Flow** design surface, right-click the newly added **Data Flow Task**, click **Rename**, and change the name to `Extract Sample Currency Data`.</span></span>  
  
     <span data-ttu-id="fc2f1-112">Il est préférable d'affecter des noms uniques aux composants que vous ajoutez à une zone de conception.</span><span class="sxs-lookup"><span data-stu-id="fc2f1-112">It is good practice to provide unique names to all components that you add to a design surface.</span></span> <span data-ttu-id="fc2f1-113">Afin d'utiliser et de maintenir les composants plus facilement, il est conseillé de leur affecter des noms décrivant les fonctions qu'ils effectuent.</span><span class="sxs-lookup"><span data-stu-id="fc2f1-113">For ease of use and maintainability, the names should describe the function that each component performs.</span></span> <span data-ttu-id="fc2f1-114">Le respect de ces consignes de nommage permet une auto-documentation de vos packages [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fc2f1-114">Following these naming guidelines allows your [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages to be self-documenting.</span></span> <span data-ttu-id="fc2f1-115">L'autre méthode permettant de documenter vos packages, consiste à utiliser des annotations.</span><span class="sxs-lookup"><span data-stu-id="fc2f1-115">Another way to document your packages is by using annotations.</span></span> <span data-ttu-id="fc2f1-116">Pour plus d’informations sur les annotations, consultez [Utilisation des annotations dans les packages](use-annotations-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="fc2f1-116">For more information about annotations, see [Use Annotations in Packages](use-annotations-in-packages.md).</span></span>  
  
4.  <span data-ttu-id="fc2f1-117">Cliquez avec le bouton droit sur la tâche de workflow, cliquez sur **Propriétés**, et dans la fenêtre Propriétés, vérifiez que la `LocaleID` propriété est définie sur **anglais (États-Unis)**.</span><span class="sxs-lookup"><span data-stu-id="fc2f1-117">Right-click the Data Flow task, click **Properties**, and in the Properties window, verify that the `LocaleID` property is set to **English (United States)**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="fc2f1-118">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="fc2f1-118">Next Task in Lesson</span></span>  
 [<span data-ttu-id="fc2f1-119">Étape 5 : Ajout et configuration de la source de fichier plat</span><span class="sxs-lookup"><span data-stu-id="fc2f1-119">Step 5: Adding and Configuring the Flat File Source</span></span>](lesson-1-5-adding-and-configuring-the-flat-file-source.md)  
  
## <a name="see-also"></a><span data-ttu-id="fc2f1-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fc2f1-120">See Also</span></span>  
 [<span data-ttu-id="fc2f1-121">tâche de flux de données</span><span class="sxs-lookup"><span data-stu-id="fc2f1-121">Data Flow Task</span></span>](control-flow/data-flow-task.md)  
  
  
