---
title: Configurer une sortie d’erreur dans un composant de Data Flow | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- errors [Integration Services], data flow components
- components [Integration Services], data flow
- error outputs [Integration Services]
ms.assetid: 53d7eeea-927d-4b45-8ea9-084e65ad5390
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ebd44383e27daa465576bb056a67f6dacad87b0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708556"
---
# <a name="configure-an-error-output-in-a-data-flow-component"></a><span data-ttu-id="8cff1-102">Configurer une sortie d'erreur dans un composant de flux de données</span><span class="sxs-lookup"><span data-stu-id="8cff1-102">Configure an Error Output in a Data Flow Component</span></span>
  <span data-ttu-id="8cff1-103">De nombreux composants de flux de données prennent en charge les sorties d’erreur, et en fonction du composant, le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] offre différentes manières de configurer une sortie d’erreur.</span><span class="sxs-lookup"><span data-stu-id="8cff1-103">Many data flow components support error outputs, and depending on the component, [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer provides different ways to configure an error output.</span></span> <span data-ttu-id="8cff1-104">En plus de configurer une sortie d'erreur, vous pouvez également configurer les colonnes d'une sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="8cff1-104">In addition to configuring an error output, you can also configure the columns of an error output.</span></span> <span data-ttu-id="8cff1-105">Cela inclut la configuration des colonnes **ErrorCode** et **ErrorColumn** ajoutées par le composant.</span><span class="sxs-lookup"><span data-stu-id="8cff1-105">This includes configuring the **ErrorCode** and **ErrorColumn** columns that are added by the component.</span></span>  
  
## <a name="configuring-an-error-output"></a><span data-ttu-id="8cff1-106">Configuration d'une sortie d'erreur</span><span class="sxs-lookup"><span data-stu-id="8cff1-106">Configuring an Error Output</span></span>  
 <span data-ttu-id="8cff1-107">Pour configurer une sortie d'erreur, vous avez deux options :</span><span class="sxs-lookup"><span data-stu-id="8cff1-107">To configure an error output, you have two options:</span></span>  
  
-   <span data-ttu-id="8cff1-108">Utilisez la boîte de dialogue **Configurer la sortie d’erreur** .</span><span class="sxs-lookup"><span data-stu-id="8cff1-108">Use the **Configure Error Output** dialog box.</span></span> <span data-ttu-id="8cff1-109">Cette boîte de dialogue vous permet de configurer une sortie d'erreur sur n'importe quel composant de flux de données prenant en charge les sorties d'erreur.</span><span class="sxs-lookup"><span data-stu-id="8cff1-109">You can use this dialog box to configure an error output on any data flow component that supports an error output.</span></span>  
  
-   <span data-ttu-id="8cff1-110">Utilisez la boîte de dialogue de l'éditeur pour le composant.</span><span class="sxs-lookup"><span data-stu-id="8cff1-110">Use the editor dialog box for the component.</span></span> <span data-ttu-id="8cff1-111">Certains composants vous permettent de configurer directement des sorties d'erreur dans la boîte de dialogue de l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="8cff1-111">Some components let you configure error outputs directly from their editor dialog box.</span></span> <span data-ttu-id="8cff1-112">Toutefois, vous ne pouvez pas configurer des sorties d’erreur dans la boîte de dialogue de l’éditeur pour la source ADO NET, la transformation d’importation de colonne, la transformation de commande OLE DB ou la destination [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="8cff1-112">However, you cannot configure error outputs from the editor dialog box for the ADO NET source, the Import Column transformation, the OLE DB Command transformation, or the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact destination.</span></span>  
  
 <span data-ttu-id="8cff1-113">Les procédures suivantes décrivent l'utilisation de ces boîtes de dialogue pour configurer des sorties d'erreur.</span><span class="sxs-lookup"><span data-stu-id="8cff1-113">The following procedures describe how to use these dialog boxes to configure error outputs.</span></span>  
  
#### <a name="to-configure-an-error-output-using-the-configure-error-output-dialog-box"></a><span data-ttu-id="8cff1-114">Pour configurer une sortie d'erreur à l'aide de la boîte de dialogue Configurer la sortie d'erreur</span><span class="sxs-lookup"><span data-stu-id="8cff1-114">To configure an error output using the Configure Error Output dialog box</span></span>  
  
1.  <span data-ttu-id="8cff1-115">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="8cff1-115">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="8cff1-116">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="8cff1-116">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="8cff1-117">Dans le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] , cliquez sur l’onglet **Flux de données** .</span><span class="sxs-lookup"><span data-stu-id="8cff1-117">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Data Flow** tab.</span></span>  
  
4.  <span data-ttu-id="8cff1-118">Faites glisser la sortie d'erreur, représentée par la flèche rouge, du composant qui est la source des erreurs vers un autre composant du flux de données.</span><span class="sxs-lookup"><span data-stu-id="8cff1-118">Drag the error output, represented by the red arrow, from the component that is the source of the errors to another component in the data flow.</span></span>  
  
5.  <span data-ttu-id="8cff1-119">Dans la boîte de dialogue **Configurer la sortie d’erreur** , sélectionnez une action dans les colonnes **Erreur** et **Troncation** pour chaque colonne de sortie du composant.</span><span class="sxs-lookup"><span data-stu-id="8cff1-119">In the **Configure Error Output** dialog box, select an action in the **Error** and **Truncation** columns for each column in the component input.</span></span>  
  
6.  <span data-ttu-id="8cff1-120">Pour enregistrer le package mis à jour, dans le menu **Fichier** , cliquez sur **Enregistrer les éléments sélectionnés**.</span><span class="sxs-lookup"><span data-stu-id="8cff1-120">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
#### <a name="to-add-an-error-output-using-the-editor-dialog-box-for-the-component"></a><span data-ttu-id="8cff1-121">Pour ajouter une sortie d'erreur à l'aide de la boîte de dialogue de l'éditeur du composant</span><span class="sxs-lookup"><span data-stu-id="8cff1-121">To add an error output using the editor dialog box for the component</span></span>  
  
1.  <span data-ttu-id="8cff1-122">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="8cff1-122">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="8cff1-123">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="8cff1-123">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="8cff1-124">Dans le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] , cliquez sur l’onglet **Flux de données** .</span><span class="sxs-lookup"><span data-stu-id="8cff1-124">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Data Flow** tab.</span></span>  
  
4.  <span data-ttu-id="8cff1-125">Double-cliquez sur les composants de flux de données pour lesquels vous voulez configurer une sortie d'erreur, et en fonction du composant, procédez de l'une des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="8cff1-125">Double-click the data flow components in which you want to configure an error output and, depending on the component, do one of the following steps:</span></span>  
  
    -   <span data-ttu-id="8cff1-126">Cliquez sur **Configurer la sortie d’erreur**.</span><span class="sxs-lookup"><span data-stu-id="8cff1-126">Click **Configure Error Output**.</span></span>  
  
    -   <span data-ttu-id="8cff1-127">Cliquez sur **Sortie d’erreur**.</span><span class="sxs-lookup"><span data-stu-id="8cff1-127">Click **Error Output**.</span></span>  
  
5.  <span data-ttu-id="8cff1-128">Définissez l’option **Erreur** pour chaque colonne.</span><span class="sxs-lookup"><span data-stu-id="8cff1-128">Set the **Error** option for each column.</span></span>  
  
6.  <span data-ttu-id="8cff1-129">Définissez l’option **Troncation** pour chaque colonne.</span><span class="sxs-lookup"><span data-stu-id="8cff1-129">Set the **Truncation** option for each column.</span></span>  
  
7.  <span data-ttu-id="8cff1-130">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8cff1-130">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="8cff1-131">Pour enregistrer le package mis à jour, dans le menu **Fichier** , cliquez sur **Enregistrer les éléments sélectionnés**.</span><span class="sxs-lookup"><span data-stu-id="8cff1-131">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="configuring-error-output-columns"></a><span data-ttu-id="8cff1-132">Configuration des colonnes de sortie d'erreur</span><span class="sxs-lookup"><span data-stu-id="8cff1-132">Configuring Error Output Columns</span></span>  
 <span data-ttu-id="8cff1-133">Pour configurer les colonnes de sortie d’erreur, vous devez utiliser l’onglet **Propriétés d’entrée et de sortie** dans la boîte de dialogue **Éditeur avancé** .</span><span class="sxs-lookup"><span data-stu-id="8cff1-133">To configure the error output columns, you have to use the **Input and Output Properties** tab of the **Advanced Editor** dialog box.</span></span>  
  
#### <a name="to-configure-error-output-columns"></a><span data-ttu-id="8cff1-134">Pour configurer des colonnes de sortie d'erreur</span><span class="sxs-lookup"><span data-stu-id="8cff1-134">To configure error output columns</span></span>  
  
1.  <span data-ttu-id="8cff1-135">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="8cff1-135">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="8cff1-136">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="8cff1-136">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="8cff1-137">Dans le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] , cliquez sur l’onglet **Flux de données** .</span><span class="sxs-lookup"><span data-stu-id="8cff1-137">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Data Flow** tab.</span></span>  
  
4.  <span data-ttu-id="8cff1-138">Cliquez avec le bouton droit sur le composant dont vous voulez configurer les colonnes de sortie d’erreur et cliquez sur **Afficher l’éditeur avancé**.</span><span class="sxs-lookup"><span data-stu-id="8cff1-138">Right-click the component whose error output columns you want to configure and click **Show Advanced Editor**.</span></span>  
  
5.  <span data-ttu-id="8cff1-139">Cliquez sur l’onglet **Propriétés d’entrée et de sortie** et développez **Sortie d’erreur de \<component name>** , puis **Colonnes de sortie**.</span><span class="sxs-lookup"><span data-stu-id="8cff1-139">Click the **Input and Output Properties** tab and expand **\<component name> Error Output** and then expand **Output Columns**.</span></span>  
  
6.  <span data-ttu-id="8cff1-140">Cliquez sur une colonne et mettez à jour ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="8cff1-140">Click a column and update its properties.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8cff1-141">La liste des colonnes comprend les colonnes de l’entrée du composant, les colonnes **ErrorCode** et **ErrorColumn** ajoutées par des sorties d'erreur précédentes et les colonnes **ErrorCode** et **ErrorColumn** ajoutées par ce composant.</span><span class="sxs-lookup"><span data-stu-id="8cff1-141">The list of columns includes the columns in the component input, the **ErrorCode** and **ErrorColumn** columns added by previous error outputs, and the **ErrorCode** and **ErrorColumn** columns added by this component.</span></span>  
  
7.  <span data-ttu-id="8cff1-142">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8cff1-142">Click **OK.**</span></span>  
  
8.  <span data-ttu-id="8cff1-143">Pour enregistrer le package mis à jour, dans le menu **Fichier** , cliquez sur **Enregistrer les éléments sélectionnés**.</span><span class="sxs-lookup"><span data-stu-id="8cff1-143">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cff1-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8cff1-144">See Also</span></span>  
 [<span data-ttu-id="8cff1-145">Gestion des erreurs dans les données</span><span class="sxs-lookup"><span data-stu-id="8cff1-145">Error Handling in Data</span></span>](data-flow/error-handling-in-data.md)  
  
  
