---
title: "Étape 3 : Ajout de redirection de flux d'erreurs | Microsoft Docs"
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5683a45d-9e73-4cd5-83ca-fae8b26b488c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ceaea310cba05a940f310c01b52d5f912a53bea8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604626"
---
# <a name="step-3-adding-error-flow-redirection"></a><span data-ttu-id="15607-102">Étape 3 : Ajout de redirection de flux d’erreurs</span><span class="sxs-lookup"><span data-stu-id="15607-102">Step 3: Adding Error Flow Redirection</span></span>
  <span data-ttu-id="15607-103">Comme nous l'avons démontré au cours de la tâche précédente, la transformation Lookup Currency Key ne peut pas générer de correspondance lorsqu'elle tente de traiter le fichier plat exemple endommagé qui a généré une erreur.</span><span class="sxs-lookup"><span data-stu-id="15607-103">As demonstrated in the previous task, the Lookup Currency Key transformation cannot generate a match when the transformation tries to process the corrupted sample flat file, which produced an error.</span></span> <span data-ttu-id="15607-104">Du fait que la transformation utilise les paramètres par défaut pour l'affichage en sortie des erreurs, toute erreur qui survient entraîne un échec de la transformation.</span><span class="sxs-lookup"><span data-stu-id="15607-104">Because the transformation uses the default settings for error output, any error causes the transformation to fail.</span></span> <span data-ttu-id="15607-105">Si la transformation échoue, le reste du package échoue également.</span><span class="sxs-lookup"><span data-stu-id="15607-105">When the transformation fails, the rest of the package also fails.</span></span>  
  
 <span data-ttu-id="15607-106">Pour éviter tout échec de la transformation, vous pouvez configurer le composant afin qu'il réachemine la ligne qui a échoué vers un autre chemin de traitement à l'aide de la sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="15607-106">Instead of permitting the transformation to fail, you can configure the component to redirect the failed row to another processing path by using the error output.</span></span> <span data-ttu-id="15607-107">L'utilisation d'un chemin de traitement des erreurs distinct vous permet d'accomplir un certain nombre de choses.</span><span class="sxs-lookup"><span data-stu-id="15607-107">Use of a separate error processing path lets you do a number of things.</span></span> <span data-ttu-id="15607-108">Par exemple, vous pouvez essayer de nettoyer les données puis de retraiter la ligne qui a échoué.</span><span class="sxs-lookup"><span data-stu-id="15607-108">For instance, you might try to clean the data and then reprocess the failed row.</span></span> <span data-ttu-id="15607-109">Ou vous pouvez enregistrer la ligne qui a échoué avec d'autres informations d'erreur, pour la vérifier et la retraiter ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="15607-109">Or, you might save the failed row along with additional error information for later verification and reprocessing.</span></span>  
  
 <span data-ttu-id="15607-110">Au cours de cette tâche, vous allez configurer la transformation Lookup Currency Key afin qu'elle réachemine toutes les lignes échouant lors de la sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="15607-110">In this task, you will configure the Lookup Currency Key transformation to redirect any rows that fail to the error output.</span></span> <span data-ttu-id="15607-111">Dans la branche d'erreur du flux de données, ces lignes sont enregistrées dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="15607-111">In the error branch of the data flow, these rows will be written to a file.</span></span>  
  
 <span data-ttu-id="15607-112">Par défaut, les deux colonnes supplémentaires d’une [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sortie d’erreur, **ErrorCode** et **ErrorColumn**, contiennent uniquement des codes numériques qui représentent un numéro d’erreur et l’ID de la colonne dans laquelle l’erreur s’est produite.</span><span class="sxs-lookup"><span data-stu-id="15607-112">By default the two extra columns in an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] error output, **ErrorCode** and **ErrorColumn**, contain only numeric codes that represent an error number, and the ID of the column in which the error occurred.</span></span> <span data-ttu-id="15607-113">L'usage de ces valeurs numériques peut être limité sans la description d'erreur correspondante.</span><span class="sxs-lookup"><span data-stu-id="15607-113">These numeric values may be of limited use without the corresponding error description.</span></span>  
  
 <span data-ttu-id="15607-114">Pour améliorer l'utilité de la sortie d'erreur, vous allez utiliser un composant Script pour accéder à l'API [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] et obtenir une description de l'erreur avant que le package n'enregistre les lignes ayant échoué dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="15607-114">To enhance the usefulness of the error output, before the package writes the failed rows to the file, you will use a Script component to access the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] API and get a description of the error.</span></span>  
  
### <a name="to-configure-an-error-output"></a><span data-ttu-id="15607-115">Pour configurer un affichage des erreurs</span><span class="sxs-lookup"><span data-stu-id="15607-115">To configure an error output</span></span>  
  
1.  <span data-ttu-id="15607-116">Dans la **boîte à outils SSIS**, développez **commun**, puis faites glisser **composant script** sur l’aire de conception de l’onglet de **Workflow** . Placez le **script** à droite de la transformation **Lookup Currency Key** .</span><span class="sxs-lookup"><span data-stu-id="15607-116">In the **SSIS Toolbox**, expand **Common**, and then drag **Script Component** onto the design surface of the **Data Flow** tab. Place **Script** to the right of the **Lookup Currency Key** transformation.</span></span>  
  
2.  <span data-ttu-id="15607-117">Dans la boîte de dialogue **Sélectionner le type de composant de script** , cliquez sur **Transformation**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="15607-117">In the **Select Script Component Type** dialog box, click **Transformation**, and click **OK**.</span></span>  
  
3.  <span data-ttu-id="15607-118">Cliquez sur la transformation **Lookup Currency Key** et faites glisser la flèche rouge vers la transformation **Script** que vous venez d'ajouter pour connecter les deux composants.</span><span class="sxs-lookup"><span data-stu-id="15607-118">Click the **Lookup Currency Key** transformation and then drag the red arrow onto the newly added **Script** transformation to connect the two components.</span></span>  
  
     <span data-ttu-id="15607-119">La flèche rouge représente la sortie d'erreur de la transformation **Lookup Currency Key** .</span><span class="sxs-lookup"><span data-stu-id="15607-119">The red arrow represents the error output of the **Lookup Currency Key** transformation.</span></span> <span data-ttu-id="15607-120">En utilisant la flèche rouge pour connecter la transformation avec le composant Script, vous pouvez rediriger toutes les erreurs de traitement vers le composant Script, lequel traite ensuite les erreurs et les transmet au composant de destination.</span><span class="sxs-lookup"><span data-stu-id="15607-120">By using the red arrow to connect the transformation to the Script component, you can redirect any processing errors to the Script component, which then processes the errors and sends them to the destination.</span></span>  
  
4.  <span data-ttu-id="15607-121">Dans la colonne **Erreur** de la boîte de dialogue **Configurer la sortie d'erreur** , sélectionnez **Réacheminer la ligne**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="15607-121">In the **Configure Error Output** dialog box, in the **Error** column, select **Redirect row**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="15607-122">Sur l’aire de conception **Flux de données** , cliquez sur **Composant Script** dans le **Composant Script**que vous venez d’ajouter, puis remplacez le nom par **Get Error Description**.</span><span class="sxs-lookup"><span data-stu-id="15607-122">On the **Data Flow** design surface, click **Script Component** in the newly added **ScriptComponent**, and change the name to **Get Error Description**.</span></span>  
  
6.  <span data-ttu-id="15607-123">Double-cliquez sur la transformation **Get Error Description** .</span><span class="sxs-lookup"><span data-stu-id="15607-123">Double-click the **Get Error Description** transformation.</span></span>  
  
7.  <span data-ttu-id="15607-124">Dans la boîte de dialogue **Éditeur de transformation de script** , dans la page **Colonnes d'entrée** , sélectionnez la colonne **ErrorCode** .</span><span class="sxs-lookup"><span data-stu-id="15607-124">In the **Script Transformation Editor** dialog box, on the **Input Columns** page, select the **ErrorCode** column.</span></span>  
  
8.  <span data-ttu-id="15607-125">Dans la page **Entrées et sorties** , développez **Sortie 0**, cliquez sur **Colonnes de sortie**, puis sur **Ajouter une colonne**.</span><span class="sxs-lookup"><span data-stu-id="15607-125">On the **Inputs and Outputs** page, expand **Output 0**, click **Output Columns**, and then click **Add Column**.</span></span>  
  
9. <span data-ttu-id="15607-126">Dans la `Name` propriété, tapez **ErrorDescription** et affectez `DataType` à la propriété la valeur **chaîne Unicode [DT_WSTR]**.</span><span class="sxs-lookup"><span data-stu-id="15607-126">In the `Name` property, type **ErrorDescription** and set the `DataType` property to **Unicode string [DT_WSTR]**.</span></span>  
  
10. <span data-ttu-id="15607-127">Dans la page **script** , vérifiez que la `LocaleID` propriété est définie sur **anglais (États-Unis.**</span><span class="sxs-lookup"><span data-stu-id="15607-127">On the **Script** page, verify that the `LocaleID` property is set to **English (United States.**</span></span>  
  
11. <span data-ttu-id="15607-128">Cliquez sur **Modifier le script** pour ouvrir [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span><span class="sxs-lookup"><span data-stu-id="15607-128">Click **Edit Script** to open [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span> <span data-ttu-id="15607-129">Dans la méthode `Input0_ProcessInputRow`, tapez ou collez le code suivant.</span><span class="sxs-lookup"><span data-stu-id="15607-129">In the `Input0_ProcessInputRow` method, type or paste the following code.</span></span>  
  
     <span data-ttu-id="15607-130">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="15607-130">[Visual Basic]</span></span>  
  
    ```  
    Row.ErrorDescription =   
      Me.ComponentMetaData.GetErrorDescription(Row.ErrorCode)  
    ```  
  
     <span data-ttu-id="15607-131">[Visual C#]</span><span class="sxs-lookup"><span data-stu-id="15607-131">[Visual C#]</span></span>  
  
    ```  
    Row.ErrorDescription = this.ComponentMetaData.GetErrorDescription(Row.ErrorCode);  
    ```  
  
     <span data-ttu-id="15607-132">La sous-routine terminée doit se présenter comme le code ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="15607-132">The completed subroutine will look like the following code.</span></span>  
  
     <span data-ttu-id="15607-133">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="15607-133">[Visual Basic]</span></span>  
  
    ```  
    Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
      Row.ErrorDescription =   
        Me.ComponentMetaData.GetErrorDescription(Row.ErrorCode)  
  
    End Sub  
    ```  
  
     <span data-ttu-id="15607-134">[Visual C#]</span><span class="sxs-lookup"><span data-stu-id="15607-134">[Visual C#]</span></span>  
  
    ```  
    public override void Input0_ProcessInputRow(Input0Buffer Row)  
        {  
  
            Row.ErrorDescription = this.ComponentMetaData.GetErrorDescription(Row.ErrorCode);  
  
        }  
    ```  
  
12. <span data-ttu-id="15607-135">Dans le menu **Générer** , cliquez sur **Générer la solution** pour créer le script et enregistrer vos modifications, puis fermez VSTA.</span><span class="sxs-lookup"><span data-stu-id="15607-135">On the **Build** menu, click **Build Solution** to build the script and save your changes, and then close VSTA.</span></span>  
  
13. <span data-ttu-id="15607-136">Cliquez sur **OK** pour fermer la boîte de dialogue **Éditeur de transformation de script** .</span><span class="sxs-lookup"><span data-stu-id="15607-136">Click **OK** to close the **Script Transformation Editor** dialog box.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="15607-137">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="15607-137">Next Steps</span></span>  
 <span data-ttu-id="15607-138">[Étape 4 : ajout d’une destination de fichier plat] (lesson-4-4-adding-a-flat-file-destination.md</span><span class="sxs-lookup"><span data-stu-id="15607-138">[Step 4: Adding a Flat File Destination](lesson-4-4-adding-a-flat-file-destination.md</span></span>  
  
  
