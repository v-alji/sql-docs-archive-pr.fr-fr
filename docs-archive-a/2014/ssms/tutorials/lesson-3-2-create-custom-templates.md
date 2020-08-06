---
title: Créer des modèles personnalisés | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- tql
- templates [Transact-SQL], creating
- templates [Transact-SQL]
ms.assetid: 41098e78-b482-410e-bfe8-2ac10769ac4a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 771547b9c47672d2c075b5e7215d78744fe5f18e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702235"
---
# <a name="create-custom-templates"></a><span data-ttu-id="e282c-102">Créer des modèles personnalisés</span><span class="sxs-lookup"><span data-stu-id="e282c-102">Create Custom Templates</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="e282c-103">est fourni avec des modèles pour de nombreuses tâches communes, mais le réel intérêt des modèles réside dans la possibilité de créer un modèle personnalisé pour les scripts complexes qui doivent être créés souvent.</span><span class="sxs-lookup"><span data-stu-id="e282c-103">comes with templates for many common tasks, but the real power of templates lies in the ability to create a custom template for a complex script that you must create frequently.</span></span> <span data-ttu-id="e282c-104">Au cours de cet exercice pratique, vous allez créer un script simple avec quelques paramètres, mais les modèles peuvent être utiles également pour les scripts longs et répétitifs.</span><span class="sxs-lookup"><span data-stu-id="e282c-104">In this practice you will create a simple script with few parameters, but templates are useful for long, repetitive scripts, too.</span></span>  
  
## <a name="using-custom-templates"></a><span data-ttu-id="e282c-105">Utilisation de modèles personnalisés</span><span class="sxs-lookup"><span data-stu-id="e282c-105">Using Custom Templates</span></span>  
  
#### <a name="to-create-a-custom-template"></a><span data-ttu-id="e282c-106">Pour créer un modèle personnalisé</span><span class="sxs-lookup"><span data-stu-id="e282c-106">To create a custom template</span></span>  
  
1.  <span data-ttu-id="e282c-107">Dans l’Explorateur de modèles, développez **Modèles SQL Server**, cliquez avec le bouton droit sur **Procédure stockée**, pointez sur **Nouveau**et cliquez sur **Dossier**.</span><span class="sxs-lookup"><span data-stu-id="e282c-107">In Template Explorer, expand **SQL Server Templates**, right-click **Stored Procedure**, point to **New**, and then click **Folder**.</span></span>  
  
2.  <span data-ttu-id="e282c-108">Tapez **Personnalisé** comme nom de dossier de modèles et appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="e282c-108">Type **Custom** as the name of your new template folder, and then press ENTER.</span></span>  
  
3.  <span data-ttu-id="e282c-109">Cliquez avec le bouton droit sur **Personnalisé**, pointez sur **Nouveau**et cliquez sur **Modèle**.</span><span class="sxs-lookup"><span data-stu-id="e282c-109">Right-click **Custom**, point to **New**, and then click **Template**.</span></span>  
  
4.  <span data-ttu-id="e282c-110">Tapez **ProcBonTravail** comme nom de votre nouveau modèle et appuyez sur **Entrée**.</span><span class="sxs-lookup"><span data-stu-id="e282c-110">Type **WorkOrdersProc** as the name of your new template, and then press **Enter**.</span></span>  
  
5.  <span data-ttu-id="e282c-111">Cliquez avec le bouton droit sur **ProcBonTravail**, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="e282c-111">Right-click **WorkOrdersProc**, and then click **Edit**.</span></span>  
  
6.  <span data-ttu-id="e282c-112">Dans la boîte de dialogue **Se connecter au moteur de base de données** , vérifiez les informations de connexion, puis cliquez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="e282c-112">In the **Connect to Database Engine** dialog box, verify the connection information and then click **Connect**.</span></span>  
  
7.  <span data-ttu-id="e282c-113">Dans l'Éditeur de requête, tapez le script suivant pour créer une procédure stockée qui recherche les bons d'une pièce en particulier, dans le cas présent : blade (la lame en français).</span><span class="sxs-lookup"><span data-stu-id="e282c-113">In Query Editor, type the following script to create a stored procedure that looks up orders for a particular part, in this case the Blade.</span></span> <span data-ttu-id="e282c-114">(Vous pouvez copier et coller le code à partir de la fenêtre du didacticiel.)</span><span class="sxs-lookup"><span data-stu-id="e282c-114">(You can copy and paste the code from the Tutorial window.)</span></span>  
  
    ```  
    USE AdventureWorks20012;  
    GO  
    IF EXISTS (  
    SELECT *   
       FROM INFORMATION_SCHEMA.ROUTINES   
       WHERE SPECIFIC_NAME = 'WorkOrdersForBlade')  
       DROP PROCEDURE dbo.WorkOrdersForBlade;  
    GO  
    CREATE PROCEDURE dbo.WorkOrdersForBlade  
    AS  
    SELECT Name, WorkOrderID   
    FROM Production.WorkOrder AS WO  
    JOIN Production.Product AS Prod  
    ON WO.ProductID = Prod.ProductID  
    WHERE Name = 'Blade';  
    GO  
    ```  
  
8.  <span data-ttu-id="e282c-115">Appuyez sur F5 pour exécuter ce script et créer la procédure **WorkOrdersForBlade** .</span><span class="sxs-lookup"><span data-stu-id="e282c-115">Press F5 to execute this script, creating the **WorkOrdersForBlade** procedure.</span></span>  
  
9. <span data-ttu-id="e282c-116">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur votre serveur et choisissez **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="e282c-116">In Object Explorer, right-click your server, and then click **New Query**.</span></span> <span data-ttu-id="e282c-117">Une nouvelle fenêtre de l'Éditeur de requête s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="e282c-117">A new Query Editor window opens.</span></span>  
  
10. <span data-ttu-id="e282c-118">Dans l’Éditeur de requête, tapez **EXECUTE dbo.WorkOrdersForBlade**et appuyez sur F5 pour exécuter la requête.</span><span class="sxs-lookup"><span data-stu-id="e282c-118">In Query Editor, type **EXECUTE dbo.WorkOrdersForBlade**, and then press F5 to execute the query.</span></span> <span data-ttu-id="e282c-119">Vérifiez si le volet **Résultats** affiche la liste des bons de travaux pour les lames.</span><span class="sxs-lookup"><span data-stu-id="e282c-119">Confirm that the **Results** pane returns a list of work orders for blades.</span></span>  
  
11. <span data-ttu-id="e282c-120">Modifiez le script du modèle (le script de l’étape 7) en remplaçant le nom du produit Blade par le paramètre <strong> *<* product_name</strong>, `nvarchar(50)` , <strong> *>* Name</strong>, à quatre endroits.</span><span class="sxs-lookup"><span data-stu-id="e282c-120">Edit the template script (the script in step 7), replacing the product name Blade with the parameter <strong>*<* product_name</strong>, `nvarchar(50)`, <strong>name*>*</strong>, in four places.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e282c-121">Les paramètres nécessitent trois éléments : le nom du paramètre à remplacer, le type de données du paramètre et une valeur par défaut pour le paramètre.</span><span class="sxs-lookup"><span data-stu-id="e282c-121">Parameters require three elements: the name of the parameter that you want to replace, the data type of the parameter, and a default value for the parameter.</span></span>  
  
12. <span data-ttu-id="e282c-122">Le script doit à présent ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="e282c-122">Now the script should look like:</span></span>  
  
    ```  
    USE AdventureWorks20012;  
    GO  
    IF EXISTS (  
    SELECT *   
       FROM INFORMATION_SCHEMA.ROUTINES   
       WHERE SPECIFIC_NAME = 'WorkOrdersFor<product_name, nvarchar(50), name>')  
       DROP PROCEDURE dbo.WorkOrdersFor<product_name, nvarchar(50), name>;  
    GO  
    CREATE PROCEDURE dbo.WorkOrdersFor<product_name, nvarchar(50), name>  
    AS  
    SELECT Name, WorkOrderID   
    FROM Production.WorkOrder AS WO  
    JOIN Production.Product AS Prod  
    ON WO.ProductID = Prod.ProductID  
    WHERE Name = '<product_name, nvarchar(50), name>';  
    GO  
    ```  
  
13. <span data-ttu-id="e282c-123">Dans le menu **Fichier** , cliquez sur **Save WorkOrdersProc.sql** (Enregistrer ProcBonTravail.sql) pour enregistrer votre modèle.</span><span class="sxs-lookup"><span data-stu-id="e282c-123">On the **File** menu, click **Save WorkOrdersProc.sql** to save your template.</span></span>  
  
#### <a name="to-test-the-custom-template"></a><span data-ttu-id="e282c-124">Pour tester le modèle personnalisé</span><span class="sxs-lookup"><span data-stu-id="e282c-124">To test the custom template</span></span>  
  
1.  <span data-ttu-id="e282c-125">Dans l’Explorateur de modèles, développez **Procédure stockée**puis **Personnalisé**et double-cliquez sur **ProcBonTravail**.</span><span class="sxs-lookup"><span data-stu-id="e282c-125">In Template Explorer, expand **Stored Procedure**, expand **Custom**, and then double-click **WorkOrderProc**.</span></span>  
  
2.  <span data-ttu-id="e282c-126">Dans la boîte de dialogue **Se connecter au moteur de base de données** , fournissez les informations de connexion, puis cliquez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="e282c-126">In the **Connect to Database Engine** dialog box, complete the connection information and then click **Connect**.</span></span> <span data-ttu-id="e282c-127">Une nouvelle fenêtre de l’Éditeur de requête s’affiche avec le modèle **ProcBonTravail** .</span><span class="sxs-lookup"><span data-stu-id="e282c-127">A new Query Editor window opens, containing the contents of the **WorkOrderProc** template.</span></span>  
  
3.  <span data-ttu-id="e282c-128">Dans le menu **Requête** , cliquez sur **Spécifier les valeurs des paramètres du modèle**.</span><span class="sxs-lookup"><span data-stu-id="e282c-128">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span>  
  
4.  <span data-ttu-id="e282c-129">Dans la boîte de dialogue **remplacer les paramètres de modèle** , pour la `product_name` valeur, tapez **freewheel** (en remplaçant le contenu par défaut), puis cliquez sur **OK** pour fermer la boîte de dialogue remplacer les **paramètres de modèle** et modifier le script dans l’éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="e282c-129">In the **Replace Template Parameters** dialog box, for the `product_name` value, type **FreeWheel** (overwriting the default contents), and then click **OK** to close the **Replace Template Parameters** dialog box and modify the script in the Query Editor.</span></span>  
  
5.  <span data-ttu-id="e282c-130">Appuyez sur F5 pour exécuter la requête et créer la procédure.</span><span class="sxs-lookup"><span data-stu-id="e282c-130">Press F5 to execute the query, creating the procedure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="e282c-131">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="e282c-131">Next Task in Lesson</span></span>  
 [<span data-ttu-id="e282c-132">Enregistrer des scripts sous forme de projets ou de solutions</span><span class="sxs-lookup"><span data-stu-id="e282c-132">Save Scripts as Projects or Solutions</span></span>](lesson-3-3-save-scripts-as-projects-or-solutions.md)  
  
  
