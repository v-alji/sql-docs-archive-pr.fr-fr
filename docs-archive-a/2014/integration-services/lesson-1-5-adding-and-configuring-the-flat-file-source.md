---
title: 'Étape 5 : Ajout et configuration de la source de fichier plat | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5c95ce51-e0fe-4fc5-95eb-2945929f2b13
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 504cfb4bc722627eb8ee70ec1f2c562cef8f1f0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605578"
---
# <a name="step-5-adding-and-configuring-the-flat-file-source"></a><span data-ttu-id="e8aac-102">Étape 5 : Ajout et configuration de la source de fichier plat</span><span class="sxs-lookup"><span data-stu-id="e8aac-102">Step 5: Adding and Configuring the Flat File Source</span></span>
  <span data-ttu-id="e8aac-103">Au cours de cette tâche, vous allez ajouter et configurer une source de fichier plat à votre package.</span><span class="sxs-lookup"><span data-stu-id="e8aac-103">In this task, you will add and configure a Flat File source to your package.</span></span> <span data-ttu-id="e8aac-104">Une source de fichier plat est un composant de flux de données qui utilise des métadonnées définies par un Gestionnaire de connexions de fichiers plats pour spécifier le format et la structure des données à extraire à partir du fichier plat par un processus de transformation.</span><span class="sxs-lookup"><span data-stu-id="e8aac-104">A Flat File source is a data flow component that uses metadata defined by a Flat File connection manager to specify the format and structure of the data to be extracted from the flat file by a transform process.</span></span> <span data-ttu-id="e8aac-105">La source de fichier plat peut être configurée pour extraire les données à partir d'un seul fichier plat en utilisant la définition de format de fichier fournie par le Gestionnaire de connexions de fichiers plats.</span><span class="sxs-lookup"><span data-stu-id="e8aac-105">The Flat File source can be configured to extract data from a single flat file by using the file format definition provided by the Flat File connection manager.</span></span>  
  
 <span data-ttu-id="e8aac-106">Pour ce didacticiel, vous allez configurer la source de fichier plat pour qu’elle utilise le `Sample Flat File Source Data` Gestionnaire de connexions que vous avez créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="e8aac-106">For this tutorial, you will configure the Flat File source to use the `Sample Flat File Source Data` connection manager that you previously created.</span></span>  
  
### <a name="to-add-a-flat-file-source-component"></a><span data-ttu-id="e8aac-107">Pour ajouter un composant source de fichier plat</span><span class="sxs-lookup"><span data-stu-id="e8aac-107">To add a Flat File Source component</span></span>  
  
1.  <span data-ttu-id="e8aac-108">Ouvrez le concepteur de **Workflow** , soit en double-cliquant sur la `Extract Sample Currency Data` tâche de workflow, soit en cliquant sur l’onglet de **Workflow**.</span><span class="sxs-lookup"><span data-stu-id="e8aac-108">Open the **Data Flow** designer, either by double-clicking the `Extract Sample Currency Data` data flow task or by clicking the **Data Flow tab**.</span></span>  
  
2.  <span data-ttu-id="e8aac-109">Dans la **Boîte à outils SSIS**, développez **Autres sources**, puis faites glisser une **source de fichier plat** sur l’aire de conception de l’onglet **Flux de données** .</span><span class="sxs-lookup"><span data-stu-id="e8aac-109">In the **SSIS Toolbox**, expand **OtherSources**, and then drag a **Flat File Source** onto the design surface of the **Data Flow** tab.</span></span>  
  
3.  <span data-ttu-id="e8aac-110">Dans l’aire de conception de **Workflow** , cliquez avec le bouton droit sur la **source de fichier plat**nouvellement ajoutée, cliquez sur **Renommer**, puis remplacez le nom par `Extract Sample Currency Data` .</span><span class="sxs-lookup"><span data-stu-id="e8aac-110">On the **Data Flow** design surface, right-click the newly added **Flat File Source**, click **Rename**, and change the name to `Extract Sample Currency Data`.</span></span>  
  
4.  <span data-ttu-id="e8aac-111">Double-cliquez sur la source de fichier plat pour ouvrir la boîte de dialogue Éditeur de source de fichier plat.</span><span class="sxs-lookup"><span data-stu-id="e8aac-111">Double-click the Flat File source to open the Flat File Source Editor dialog box.</span></span>  
  
5.  <span data-ttu-id="e8aac-112">Dans la zone **Gestionnaire de connexions de fichiers plats** , sélectionnez `Sample Flat File Source Data` .</span><span class="sxs-lookup"><span data-stu-id="e8aac-112">In the **Flat file connection manager** box, select `Sample Flat File Source Data`.</span></span>  
  
6.  <span data-ttu-id="e8aac-113">Sélectionnez **Colonnes** et vérifiez si les noms des colonnes sont corrects.</span><span class="sxs-lookup"><span data-stu-id="e8aac-113">Click **Columns** and verify that the names of the columns are correct.</span></span>  
  
7.  <span data-ttu-id="e8aac-114">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e8aac-114">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="e8aac-115">Cliquez avec le bouton droit sur la source de fichier plat, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="e8aac-115">Right-click the Flat File source and click **Properties**.</span></span>  
  
9. <span data-ttu-id="e8aac-116">Dans la Fenêtre Propriétés, vérifiez que la `LocaleID` propriété est définie sur **anglais (États-Unis)**.</span><span class="sxs-lookup"><span data-stu-id="e8aac-116">In the Properties window, verify that the `LocaleID` property is set to **English (United States)**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="e8aac-117">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="e8aac-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="e8aac-118">Étape 6 : Ajout et configuration des transformations de recherche</span><span class="sxs-lookup"><span data-stu-id="e8aac-118">Step 6: Adding and Configuring the Lookup Transformations</span></span>](lesson-1-6-adding-and-configuring-the-lookup-transformations.md)  
  
## <a name="see-also"></a><span data-ttu-id="e8aac-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e8aac-119">See Also</span></span>  
 <span data-ttu-id="e8aac-120">[Source de fichier plat](data-flow/flat-file-source.md) </span><span class="sxs-lookup"><span data-stu-id="e8aac-120">[Flat File Source](data-flow/flat-file-source.md) </span></span>  
 [<span data-ttu-id="e8aac-121">Éditeur du gestionnaire de connexions de fichiers plats &#40;page Général&#41;</span><span class="sxs-lookup"><span data-stu-id="e8aac-121">Flat File Connection Manager Editor &#40;General Page&#41;</span></span>](general-page-of-integration-services-designers-options.md)  
  
  
