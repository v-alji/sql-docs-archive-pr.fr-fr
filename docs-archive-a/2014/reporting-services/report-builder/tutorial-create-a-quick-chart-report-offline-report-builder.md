---
title: 'Tutoriel : Créer un rapport de graphique rapide en mode hors connexion (Générateur de rapports) | Microsoft Docs'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports, creating
- tutorials, getting started
- creating reports
ms.assetid: 6b1db67a-cf75-494c-b70c-09f1e6a8d414
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 51a9e648550a0108f47e3d93d75267ab0c1c24f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603271"
---
# <a name="tutorial-create-a-quick-chart-report-offline-report-builder"></a><span data-ttu-id="81f29-102">Didacticiel : créer un rapport de graphique rapide en mode hors connexion (Générateur de rapports)</span><span class="sxs-lookup"><span data-stu-id="81f29-102">Tutorial: Create a Quick Chart Report Offline (Report Builder)</span></span>
  <span data-ttu-id="81f29-103">Dans ce didacticiel, vous allez créer un graphique à secteurs à l'aide d'un Assistant, puis le modifier quelque peu afin d'obtenir un petit aperçu des opérations réalisables.</span><span class="sxs-lookup"><span data-stu-id="81f29-103">In this tutorial, you'll create a pie chart by using a wizard, and then you'll modify it a little, just to get an idea of what's possible.</span></span> <span data-ttu-id="81f29-104">Vous pouvez effectuer ce didacticiel de deux façons différentes.</span><span class="sxs-lookup"><span data-stu-id="81f29-104">You can do this tutorial two different ways.</span></span> <span data-ttu-id="81f29-105">Les deux méthodes ont le même résultat : un graphique à secteurs comme celui de l’illustration suivante :</span><span class="sxs-lookup"><span data-stu-id="81f29-105">Both methods have the same outcome-a pie chart like the one in the following illustration:</span></span>

 <span data-ttu-id="81f29-106">![« Mon premier graphique à secteurs » en mode exécution](../media/rs-my1stpierunview.gif "Mon premier graphique à secteurs en mode exécution")</span><span class="sxs-lookup"><span data-stu-id="81f29-106">!["My First Pie Chart" in Run view](../media/rs-my1stpierunview.gif "My First Pie Chart in Run view")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="81f29-107">Prérequis</span><span class="sxs-lookup"><span data-stu-id="81f29-107">Prerequisites</span></span>
 <span data-ttu-id="81f29-108">Que vous utilisiez des données XML ou une requête [!INCLUDE[tsql](../../../includes/tsql-md.md)], vous devez avoir accès au Générateur de rapports [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81f29-108">Whether you use XML data or a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query, you need to have access to [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] Report Builder.</span></span> <span data-ttu-id="81f29-109">Vous pouvez exécuter la version autonome ou la version ClickOnce disponible à partir du Gestionnaire de rapports ou d'un site SharePoint.</span><span class="sxs-lookup"><span data-stu-id="81f29-109">You can run the stand-alone version or the ClickOnce version available from Report Manager or a SharePoint site.</span></span> <span data-ttu-id="81f29-110">Seule la première étape, l'ouverture du Générateur de rapports, est différente pour les versions ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="81f29-110">Only the first step, how to open Report Builder, is different for ClickOnce versions.</span></span> <span data-ttu-id="81f29-111">Pour plus d’informations, consultez [installation, désinstallation et prise en charge de générateur de rapports](../install-uninstall-and-report-builder-support.md).</span><span class="sxs-lookup"><span data-stu-id="81f29-111">For more information, see [Install, Uninstall, and Report Builder Support](../install-uninstall-and-report-builder-support.md).</span></span>

##  <a name="two-ways-to-do-this-tutorial"></a><a name="TwoWays"></a><span data-ttu-id="81f29-112">Deux méthodes pour suivre ce didacticiel</span><span class="sxs-lookup"><span data-stu-id="81f29-112">Two Ways To Do This Tutorial</span></span>

-   [<span data-ttu-id="81f29-113">Créer le graphique à secteurs avec des données XML</span><span class="sxs-lookup"><span data-stu-id="81f29-113">Create the pie chart with XML data</span></span>](#CreatePieChartXML)

-   [<span data-ttu-id="81f29-114">Créer le graphique à secteurs avec une requête Transact-SQL qui contient des données</span><span class="sxs-lookup"><span data-stu-id="81f29-114">Create the pie chart with a Transact-SQL query that contains data</span></span>](#CreatePieQueryData)

### <a name="using-xml-data-for-this-tutorial"></a><span data-ttu-id="81f29-115">Utilisation de données XML pour ce didacticiel</span><span class="sxs-lookup"><span data-stu-id="81f29-115">Using XML data for this tutorial</span></span>
 <span data-ttu-id="81f29-116">Vous pouvez utiliser des données XML que vous copiez à partir de cette rubrique et que vous collez dans l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="81f29-116">You can use XML data that you copy from this topic and paste into the wizard.</span></span> <span data-ttu-id="81f29-117">Vous n'avez pas besoin de vous connecter à un serveur de rapports ou un serveur de rapports en mode intégré SharePoint, et vous n'avez pas besoin d'accéder à une instance de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81f29-117">You don't need to be connected to a report server or a report server in SharePoint integrated mode, and you don't need access to an instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>

 [<span data-ttu-id="81f29-118">Créer le graphique à secteurs avec des données XML</span><span class="sxs-lookup"><span data-stu-id="81f29-118">Create the pie chart with XML data</span></span>](#CreatePieChartXML)

### <a name="using-a-transact-sql-query-that-contains-data-for-this-tutorial"></a><span data-ttu-id="81f29-119">Utilisation d'une requête Transact-SQL qui contient les données de ce didacticiel</span><span class="sxs-lookup"><span data-stu-id="81f29-119">Using a Transact-SQL query that contains data for this tutorial</span></span>
 <span data-ttu-id="81f29-120">Vous pouvez copier une requête comprenant des données incluses à partir de cette rubrique et la coller dans l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="81f29-120">You can copy a query with data included in it from this topic and paste it into the wizard.</span></span> <span data-ttu-id="81f29-121">Vous avez besoin du nom d'une instance de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] et d'informations d'identification suffisantes pour accéder en lecture seule aux bases de données.</span><span class="sxs-lookup"><span data-stu-id="81f29-121">You will need the name of an instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] and credentials sufficient for read-only access to any database.</span></span> <span data-ttu-id="81f29-122">La requête de dataset du didacticiel utilise des données littérales, mais la requête doit être traitée par une instance de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] pour retourner les métadonnées nécessaires à un dataset de rapport.</span><span class="sxs-lookup"><span data-stu-id="81f29-122">The dataset query in the tutorial uses literal data, but the query must be processed by an instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] to return the metadata that is required for a report dataset.</span></span>

 <span data-ttu-id="81f29-123">L'avantage lié à l'utilisation de la requête [!INCLUDE[tsql](../../../includes/tsql-md.md)] vient du fait que tous les autres didacticiels du Générateur de rapports utilisent la même méthode ; par conséquent, lorsque vous effectuerez d'autres didacticiels, vous saurez déjà quoi faire.</span><span class="sxs-lookup"><span data-stu-id="81f29-123">The advantage of using the [!INCLUDE[tsql](../../../includes/tsql-md.md)] query is that all the other Report Builder tutorials use the same method, so when you do the other tutorials, you will already know what to do.</span></span>

 <span data-ttu-id="81f29-124">La requête [!INCLUDE[tsql](../../../includes/tsql-md.md)] requiert quelques conditions préalables supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="81f29-124">The [!INCLUDE[tsql](../../../includes/tsql-md.md)] query does require a few other prerequisites.</span></span> <span data-ttu-id="81f29-125">Pour plus d’informations, voir [Éléments requis pour les didacticiels (Générateur de rapports)](../report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="81f29-125">For more information, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md).</span></span>

 [<span data-ttu-id="81f29-126">Créer le graphique à secteurs avec une requête Transact-SQL qui contient des données</span><span class="sxs-lookup"><span data-stu-id="81f29-126">Create the pie chart with a Transact-SQL query that contains data</span></span>](#CreatePieQueryData)

## <a name="also-in-this-article"></a><span data-ttu-id="81f29-127">Également dans cet article</span><span class="sxs-lookup"><span data-stu-id="81f29-127">Also in This Article</span></span>
 [<span data-ttu-id="81f29-128">Après l’exécution de l’Assistant</span><span class="sxs-lookup"><span data-stu-id="81f29-128">After You Run the Wizard</span></span>](#AfterWizard)

 [<span data-ttu-id="81f29-129">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="81f29-129">What's Next</span></span>](#WhatsNext)

##  <a name="creating-the-pie-chart-with-xml-data"></a><a name="CreatePieChartXML"></a><span data-ttu-id="81f29-130">Création du graphique à secteurs avec des données XML</span><span class="sxs-lookup"><span data-stu-id="81f29-130">Creating the pie chart with XML data</span></span>

#### <a name="to-create-the-pie-chart-with-xml-data"></a><span data-ttu-id="81f29-131">Pour créer le graphique à secteurs avec des données XML</span><span class="sxs-lookup"><span data-stu-id="81f29-131">To create the pie chart with XML data</span></span>

1.  <span data-ttu-id="81f29-132">Cliquez sur **Démarrer**, pointez sur **Programmes**, sur **Générateur de rapports Microsoft SQL Server 2012**, puis cliquez sur **Générateur de rapports version**.</span><span class="sxs-lookup"><span data-stu-id="81f29-132">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>

     <span data-ttu-id="81f29-133">La boîte de dialogue **prise en main** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="81f29-133">The **Getting Started** dialog box appears.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="81f29-134">Si la boîte de dialogue **prise en main** n’apparaît pas, à partir du bouton **Générateur de rapports** , cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="81f29-134">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>

2.  <span data-ttu-id="81f29-135">Dans le volet gauche, assurez-vous que **Rapport** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="81f29-135">In the left pane, verify that **Report** is selected.</span></span>

3.  <span data-ttu-id="81f29-136">Dans le volet droit, cliquez sur **Assistant Graphique**, puis sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="81f29-136">In the right pane, click **Chart Wizard**, and then click **Create**.</span></span>

4.  <span data-ttu-id="81f29-137">Dans la page **Choisir un dataset** , cliquez sur **Créer un dataset**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81f29-137">In the **Choose a dataset** page, click **Create a dataset**, and then click **Next**.</span></span>

5.  <span data-ttu-id="81f29-138">Dans la page **Choisir une connexion à une source de données** , cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="81f29-138">In the **Choose a connection to a data source** page, click **New**.</span></span>

     <span data-ttu-id="81f29-139">La boîte de dialogue **Propriétés de la source de données** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="81f29-139">The **Data Source Properties** dialog box opens.</span></span>

6.  <span data-ttu-id="81f29-140">Vous pouvez attribuer à la source de données le nom de votre choix.</span><span class="sxs-lookup"><span data-stu-id="81f29-140">You can name a data source anything you want.</span></span> <span data-ttu-id="81f29-141">Dans la zone **Nom** , tapez **MonGraphiqueàSecteurs**.</span><span class="sxs-lookup"><span data-stu-id="81f29-141">In the **Name** box, type **MyPieChart**.</span></span>

7.  <span data-ttu-id="81f29-142">Dans la zone **Sélectionner le type de connexion** , cliquez sur **XML.**</span><span class="sxs-lookup"><span data-stu-id="81f29-142">In the **Select connection type** box, click **XML.**</span></span>

8.  <span data-ttu-id="81f29-143">Cliquez sur l’onglet **informations d’identification** , sélectionnez **utiliser l’utilisateur Windows actuel. La délégation Kerberos peut être nécessaire**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="81f29-143">Click the **Credentials** tab, select **Use current Windows user. Kerberos delegation may be required**, and then click **OK**.</span></span>

9. <span data-ttu-id="81f29-144">Dans la page **Choisir une connexion à une source de données** , cliquez sur **MonGraphiqueàSecteurs**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81f29-144">In the **Choose a connection to a data source** page, click **MyPieChart**, and then click **Next**.</span></span>

10. <span data-ttu-id="81f29-145">Copiez le texte suivant et collez-le dans la grande zone au centre de la page **créer une requête** .</span><span class="sxs-lookup"><span data-stu-id="81f29-145">Copy the following text and paste it in the large box in the center of the **Design a query** page.</span></span>

    ```
    <Query>
    <ElementPath>Root /S  {@Sales (Integer)} /C {@FullName} </ElementPath>
    <XmlData>
    <Root>
    <S Sales="150">
      <C FullName="Jae Pak" />
    </S>
    <S Sales="350">
      <C FullName="Jillian  Carson" />
    </S>
    <S Sales="250">
      <C FullName="Linda C Mitchell" />
    </S>
    <S Sales="500">
      <C FullName="Michael Blythe" />
    </S>
    <S Sales="450">
      <C FullName="Ranjit Varkey" />
    </S>
    </Root>
    </XmlData>
    </Query>
    ```

11. <span data-ttu-id="81f29-146">(Facultatif) Cliquez sur le bouton Exécuter (**!**) pour voir les données sur lesquelles votre graphique sera basé.</span><span class="sxs-lookup"><span data-stu-id="81f29-146">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>

12. <span data-ttu-id="81f29-147">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81f29-147">Click **Next**.</span></span>

13. <span data-ttu-id="81f29-148">Dans la page **Choisir un type de graphique** , cliquez sur **Secteurs**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81f29-148">In the **Choose a chart type** page, click **Pie**, and then click **Next**.</span></span>

14. <span data-ttu-id="81f29-149">Dans la page **Organiser les champs du graphique**, double-cliquez sur le champ **Sales** dans la zone **Champs disponibles**.</span><span class="sxs-lookup"><span data-stu-id="81f29-149">In the **Arrange chart fields** page, double-click the **Sales** field in the **Available fields** box.</span></span>

     <span data-ttu-id="81f29-150">Notez que ce champ est déplacé automatiquement vers la zone **Valeurs** , car il s'agit d'une valeur numérique.</span><span class="sxs-lookup"><span data-stu-id="81f29-150">Note that it automatically moves to the **Values** box, because it is a numerical value.</span></span>

15. <span data-ttu-id="81f29-151">Faites glisser le champ **FullName** de la zone **Champs disponibles** vers la zone **Catégories** (ou double-cliquez dessus pour le faire passer dans la zone **Catégories**), puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81f29-151">Drag the **FullName** field from the **Available fields** box to the **Categories** box (or double-click it; it will go to the **Categories** box), and then click **Next**.</span></span>

16. <span data-ttu-id="81f29-152">Dans la page **choisir un style** , **océan** est sélectionné par défaut.</span><span class="sxs-lookup"><span data-stu-id="81f29-152">In the **Choose a style** page, **Ocean** is selected by default.</span></span> <span data-ttu-id="81f29-153">Cliquez sur les autres styles pour voir à quoi ils ressemblent.</span><span class="sxs-lookup"><span data-stu-id="81f29-153">Click the other styles to see what they look like.</span></span>

17. <span data-ttu-id="81f29-154">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="81f29-154">Click **Finish**.</span></span>

     <span data-ttu-id="81f29-155">Votre nouveau graphique à secteurs est maintenant affiché sur l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="81f29-155">You're now looking at your new pie chart report on the design surface.</span></span> <span data-ttu-id="81f29-156">Il ne s'agit que d'une représentation.</span><span class="sxs-lookup"><span data-stu-id="81f29-156">What you see is representational.</span></span> <span data-ttu-id="81f29-157">La légende indique Full Name 1, Full Name 2, etc., plutôt que les noms des agents commerciaux, et la taille des secteurs du graphique est incorrecte.</span><span class="sxs-lookup"><span data-stu-id="81f29-157">The legend reads Full Name 1, Full Name 2, etc., rather than the salespeople's names, and the size of the slices of pie are not accurate.</span></span> <span data-ttu-id="81f29-158">Cela vous donne néanmoins une idée de l'aspect qu'aura votre rapport.</span><span class="sxs-lookup"><span data-stu-id="81f29-158">This is just to give you an idea of what your report will look like.</span></span>

18. <span data-ttu-id="81f29-159">Pour afficher votre graphique à secteurs, cliquez sur **Exécuter** sous l'onglet **Accueil** du ruban.</span><span class="sxs-lookup"><span data-stu-id="81f29-159">To see your actual pie chart, click **Run** on the **Home** tab of the Ribbon.</span></span>

 <span data-ttu-id="81f29-160">![Icône de flèche utilisée avec le lien retour en haut](../../2014-toc/media/uparrow16x16.gif "Icône de flèche utilisée avec le lien Retour en haut") [vers le haut](#TwoWays)</span><span class="sxs-lookup"><span data-stu-id="81f29-160">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Back to Top](#TwoWays)</span></span>

##  <a name="creating-the-pie-chart-with-a-tsql-query"></a><a name="CreatePieQueryData"></a> <span data-ttu-id="81f29-161">Création du graphique à secteurs avec une requête [!INCLUDE[tsql](../../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81f29-161">Creating the pie chart with a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query</span></span>

#### <a name="to-create-the-pie-chart-with-a-tsql-query-that-contains-data"></a><span data-ttu-id="81f29-162">Pour créer le graphique à secteurs avec une requête [!INCLUDE[tsql](../../../includes/tsql-md.md)] qui contient des données</span><span class="sxs-lookup"><span data-stu-id="81f29-162">To create the pie chart with a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query that contains data</span></span>

1.  <span data-ttu-id="81f29-163">Cliquez sur **Démarrer**, pointez sur **Programmes**, sur **Générateur de rapports Microsoft SQL Server 2012**, puis cliquez sur **Générateur de rapports version**.</span><span class="sxs-lookup"><span data-stu-id="81f29-163">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>

2.  <span data-ttu-id="81f29-164">Dans la boîte de dialogue **nouveau rapport ou DataSet** , vérifiez que **rapport** est sélectionné dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="81f29-164">In the **New report or dataset** dialog box, verify that **Report** is selected in the left pane.</span></span>

3.  <span data-ttu-id="81f29-165">Dans le volet droit, cliquez sur **Assistant Graphique**, puis sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="81f29-165">In the right pane, click **Chart Wizard**, and then click **Create**.</span></span>

4.  <span data-ttu-id="81f29-166">Dans la page **Choisir un dataset** , cliquez sur **Créer un dataset**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81f29-166">In the **Choose a dataset** page, click **Create a dataset**, and then click **Next**.</span></span>

5.  <span data-ttu-id="81f29-167">Dans la page **Choisir une connexion à une source de données** , sélectionnez une source de données existante ou naviguez jusqu'au serveur de rapports, sélectionnez une source de données, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81f29-167">In the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source, and then click **Next**.</span></span> <span data-ttu-id="81f29-168">Vous devrez peut-être entrer un nom d'utilisateur et un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="81f29-168">You may need to enter a user name and password.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="81f29-169">La source de données que vous choisissez n'a pas d'importance, tant que vous disposez des autorisations appropriées.</span><span class="sxs-lookup"><span data-stu-id="81f29-169">The data source you choose is unimportant, as long as you have adequate permissions.</span></span> <span data-ttu-id="81f29-170">Vous n'allez pas récupérer de données à partir de la source de données.</span><span class="sxs-lookup"><span data-stu-id="81f29-170">You will not be getting data from the data source.</span></span> <span data-ttu-id="81f29-171">Pour plus d’informations, voir [Éléments requis pour les didacticiels (Générateur de rapports)](../report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="81f29-171">For more information, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md).</span></span>

6.  <span data-ttu-id="81f29-172">Sur la page **créer une requête** , cliquez sur **modifier en tant que texte**.</span><span class="sxs-lookup"><span data-stu-id="81f29-172">On the **Design a Query** page, click **Edit as Text**.</span></span>

7.  <span data-ttu-id="81f29-173">Collez la requête suivante dans le volet de requête :</span><span class="sxs-lookup"><span data-stu-id="81f29-173">Paste the following query into the query pane:</span></span>

    ```
    SELECT 150 AS Sales, 'Jae Pak' AS FullName 
    UNION SELECT 350 AS Sales, 'Jillian Carson' AS FullName 
    UNION SELECT 250 AS Sales, 'Linda C Mitchell' AS FullName 
    UNION SELECT 500 AS Sales, 'Michael Blythe' AS FullName 
    UNION SELECT 450 AS Sales, 'Ranjit Varkey' AS FullName 
    ```

8.  <span data-ttu-id="81f29-174">(Facultatif) Cliquez sur le bouton Exécuter (**!**) pour voir les données sur lesquelles votre graphique sera basé.</span><span class="sxs-lookup"><span data-stu-id="81f29-174">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>

9. <span data-ttu-id="81f29-175">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81f29-175">Click **Next**.</span></span>

10. <span data-ttu-id="81f29-176">Dans la page **Choisir un type de graphique** , cliquez sur **Secteurs**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81f29-176">In the **Choose a chart type** page, click **Pie**, and then click **Next**.</span></span>

11. <span data-ttu-id="81f29-177">Dans la page **Organiser les champs du graphique**, double-cliquez sur le champ **Sales** dans la zone **Champs disponibles**.</span><span class="sxs-lookup"><span data-stu-id="81f29-177">In the **Arrange chart fields** page, double-click the **Sales** field in the **Available fields** box.</span></span>

     <span data-ttu-id="81f29-178">Notez que ce champ est déplacé automatiquement vers la zone **Valeurs** , car il s'agit d'une valeur numérique.</span><span class="sxs-lookup"><span data-stu-id="81f29-178">Note that it automatically moves to the **Values** box, because it's a numerical value.</span></span>

12. <span data-ttu-id="81f29-179">Faites glisser le champ **FullName** de la zone **Champs disponibles** vers la zone **Catégories** (ou double-cliquez dessus pour le faire passer dans la zone **Catégories**), puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81f29-179">Drag the **FullName** field from the **Available fields** box to the **Categories** box (or double-click it; it will go to the **Categories** box), and then click **Next**.</span></span>

13. <span data-ttu-id="81f29-180">Dans la page **Choisir un style** , Océan est sélectionné par défaut.</span><span class="sxs-lookup"><span data-stu-id="81f29-180">In the **Choose a style** page, Ocean is selected by default.</span></span> <span data-ttu-id="81f29-181">Cliquez sur les autres styles pour voir à quoi ils ressemblent.</span><span class="sxs-lookup"><span data-stu-id="81f29-181">Click the other styles to see what they look like.</span></span>

14. <span data-ttu-id="81f29-182">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="81f29-182">Click **Finish**.</span></span>

     <span data-ttu-id="81f29-183">Votre nouveau graphique à secteurs est maintenant affiché sur l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="81f29-183">You're now looking at your new pie chart report on the design surface.</span></span> <span data-ttu-id="81f29-184">Il ne s'agit que d'une représentation.</span><span class="sxs-lookup"><span data-stu-id="81f29-184">What you see is representational.</span></span> <span data-ttu-id="81f29-185">La légende indique Full Name 1, Full Name 2, etc., plutôt que les noms des agents commerciaux, et la taille des secteurs du graphique est incorrecte.</span><span class="sxs-lookup"><span data-stu-id="81f29-185">The legend reads Full Name 1, Full Name 2, etc., rather than the salespeople's names, and the size of the slices of pie are not accurate.</span></span> <span data-ttu-id="81f29-186">Cela vous donne néanmoins une idée de l'aspect qu'aura votre rapport.</span><span class="sxs-lookup"><span data-stu-id="81f29-186">This is just to give you an idea of what your report will look like.</span></span>

15. <span data-ttu-id="81f29-187">Pour afficher votre graphique à secteurs, cliquez sur **Exécuter** sous l'onglet **Accueil** du ruban.</span><span class="sxs-lookup"><span data-stu-id="81f29-187">To see your actual pie chart, click **Run** on the **Home** tab of the Ribbon.</span></span>

 <span data-ttu-id="81f29-188">![Icône de flèche utilisée avec le lien retour en haut](../../2014-toc/media/uparrow16x16.gif "Icône de flèche utilisée avec le lien Retour en haut") [vers le haut](#TwoWays)</span><span class="sxs-lookup"><span data-stu-id="81f29-188">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Back to Top](#TwoWays)</span></span>

##  <a name="after-you-run-the-wizard"></a><a name="AfterWizard"></a><span data-ttu-id="81f29-189">Après l’exécution de l’Assistant</span><span class="sxs-lookup"><span data-stu-id="81f29-189">After You Run the Wizard</span></span>
 <span data-ttu-id="81f29-190">Maintenant que vous avez créé votre rapport de graphique à secteurs, vous pouvez le manipuler.</span><span class="sxs-lookup"><span data-stu-id="81f29-190">Now that you have your pie chart report, you can play with it.</span></span> <span data-ttu-id="81f29-191">Sous l'onglet **Exécuter** du ruban, cliquez sur **Conception**de manière à pouvoir continuer de le modifier.</span><span class="sxs-lookup"><span data-stu-id="81f29-191">On the **Run** tab of the Ribbon, click **Design**, so you can continue modifying it.</span></span>

### <a name="make-the-chart-bigger"></a><span data-ttu-id="81f29-192">Augmenter la taille du graphique</span><span class="sxs-lookup"><span data-stu-id="81f29-192">Make the chart bigger</span></span>
 <span data-ttu-id="81f29-193">Vous pouvez augmenter la taille du graphique à secteurs.</span><span class="sxs-lookup"><span data-stu-id="81f29-193">You may want the pie chart to be bigger.</span></span> <span data-ttu-id="81f29-194">Cliquez sur le graphique (mais pas sur l'un de ses éléments) pour le sélectionner et faites glisser le coin inférieur droit pour le redimensionner.</span><span class="sxs-lookup"><span data-stu-id="81f29-194">Click the chart, but not on any element in the chart, to select it and drag the lower-right corner to resize it.</span></span>

### <a name="add-a-report-title"></a><span data-ttu-id="81f29-195">Ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="81f29-195">Add a report title</span></span>
 <span data-ttu-id="81f29-196">Sélectionnez les mots **Titre du graphique** en haut du graphique, puis tapez un titre, par exemple : **Graphique à secteurs des ventes**.</span><span class="sxs-lookup"><span data-stu-id="81f29-196">Select the words **Chart title** at the top of the chart, and then type a title, such as **Sales Pie Chart**.</span></span>

### <a name="add-percentages"></a><span data-ttu-id="81f29-197">Ajouter des pourcentages</span><span class="sxs-lookup"><span data-stu-id="81f29-197">Add percentages</span></span>

##### <a name="to-display-percentage-values-as-labels-on-a-pie-chart"></a><span data-ttu-id="81f29-198">Pour afficher des valeurs en pourcentage sous forme d'étiquettes sur un graphique à secteurs</span><span class="sxs-lookup"><span data-stu-id="81f29-198">To display percentage values as labels on a pie chart</span></span>

1.  <span data-ttu-id="81f29-199">Cliquez avec le bouton droit sur le graphique à secteurs et sélectionnez **afficher les étiquettes de données**.</span><span class="sxs-lookup"><span data-stu-id="81f29-199">Right-click on the pie chart and select **Show Data Labels**.</span></span> <span data-ttu-id="81f29-200">Les étiquettes de données doivent apparaître dans chaque secteur du graphique.</span><span class="sxs-lookup"><span data-stu-id="81f29-200">The data labels should appear within each slice on the pie chart.</span></span>

2.  <span data-ttu-id="81f29-201">Cliquez avec le bouton droit sur les étiquettes et sélectionnez Propriétés de l’étiquette de la **série**.</span><span class="sxs-lookup"><span data-stu-id="81f29-201">Right-click on the labels and select **Series Label Properties**.</span></span> <span data-ttu-id="81f29-202">La boîte de dialogue **Propriétés de l'étiquette de la série** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="81f29-202">The **Series Label Properties** dialog box appears.</span></span>

3.  <span data-ttu-id="81f29-203">Type `#PERCENT{P0}` de l’option des **données d’étiquette** .</span><span class="sxs-lookup"><span data-stu-id="81f29-203">Type `#PERCENT{P0}` for the **Label data** option.</span></span>

     <span data-ttu-id="81f29-204">`{P0}` indique le pourcentage sans décimales.</span><span class="sxs-lookup"><span data-stu-id="81f29-204">The `{P0}` gives you the percentage without decimal places.</span></span> <span data-ttu-id="81f29-205">Si vous tapez simplement `#PERCENT`, vos chiffres comporteront deux décimales.</span><span class="sxs-lookup"><span data-stu-id="81f29-205">If you type just `#PERCENT`, your numbers will have two decimal places.</span></span> <span data-ttu-id="81f29-206">`#PERCENT` est un mot clé qui effectue un calcul ou une fonction pour vous ; il en existe de nombreux autres.</span><span class="sxs-lookup"><span data-stu-id="81f29-206">`#PERCENT` is a keyword that performs a calculation or function for you; there are many others.</span></span>

 <span data-ttu-id="81f29-207">Pour plus d’informations sur la personnalisation des étiquettes et légendes de graphique, voir [Afficher des valeurs en pourcentage dans un graphique à secteurs (Générateur de rapports et SSRS)](../report-design/display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md) et [Modifier le texte d’un élément de légende (Générateur de rapports et SSRS)](../report-design/chart-legend-change-item-text-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="81f29-207">For more information about customizing chart labels and legends, see [Display Percentage Values on a Pie Chart &#40;Report Builder and SSRS&#41;](../report-design/display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md) and [Change the Text of a Legend Item &#40;Report Builder and SSRS&#41;](../report-design/chart-legend-change-item-text-report-builder.md).</span></span>

 <span data-ttu-id="81f29-208">![Icône de flèche utilisée avec le lien retour en haut](../../2014-toc/media/uparrow16x16.gif "Icône de flèche utilisée avec le lien Retour en haut") [vers le haut](#TwoWays)</span><span class="sxs-lookup"><span data-stu-id="81f29-208">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Back to Top](#TwoWays)</span></span>

##  <a name="whats-next"></a><a name="WhatsNext"></a><span data-ttu-id="81f29-209">Et ensuite ?</span><span class="sxs-lookup"><span data-stu-id="81f29-209">What's Next?</span></span>
 <span data-ttu-id="81f29-210">Maintenant que vous avez créé votre premier rapport dans le Générateur de rapports, vous pouvez effectuer les autres didacticiels et commencer à créer des rapports à partir de vos propres données.</span><span class="sxs-lookup"><span data-stu-id="81f29-210">Now that you have created your first report in Report Builder, you are ready to try the other tutorials and to start creating reports from your own data.</span></span> <span data-ttu-id="81f29-211">Pour exécuter Générateur de rapports, vous devez avoir l’autorisation d’accéder à vos sources de données, telles que des bases de données, avec une *chaîne de connexion*, qui vous permet de vous connecter à la source de données.</span><span class="sxs-lookup"><span data-stu-id="81f29-211">To run Report Builder, you need permission to access your data sources, such as databases, with a *connection string*, which actually connects you to the data source.</span></span> <span data-ttu-id="81f29-212">Votre administrateur système sera en mesure de vous fournir les informations nécessaires.</span><span class="sxs-lookup"><span data-stu-id="81f29-212">Your system administrator will have this information and can set you up.</span></span>

 <span data-ttu-id="81f29-213">Pour utiliser les autres didacticiels, vous avez besoin du nom d'une instance de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] et d'informations d'identification suffisantes pour accéder en lecture seule aux bases de données.</span><span class="sxs-lookup"><span data-stu-id="81f29-213">To work through the other tutorials, you need the name of an instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] and credentials sufficient for read-only access to any database.</span></span> <span data-ttu-id="81f29-214">Là encore, vous pouvez vous adresser à votre administrateur système.</span><span class="sxs-lookup"><span data-stu-id="81f29-214">Your system administrator can also set that up for you.</span></span>

 <span data-ttu-id="81f29-215">Pour finir, afin d'enregistrer vos rapports sur un serveur de rapports ou un site SharePoint intégré à un serveur de rapports, il vous faut posséder l'URL et les autorisations nécessaires.</span><span class="sxs-lookup"><span data-stu-id="81f29-215">Finally, to save your reports to a report server or a SharePoint site that is integrated with a report server, you need the URL and permissions.</span></span> <span data-ttu-id="81f29-216">Vous pouvez créer les rapports que vous créez directement à partir de votre ordinateur, mais les rapports procurent davantage de fonctionnalités lorsqu'ils sont exécutés à partir du serveur de rapports ou d'un site SharePoint.</span><span class="sxs-lookup"><span data-stu-id="81f29-216">You can run any report you create directly from your computer, but reports have more functionality when run from the report server or SharePoint site.</span></span> <span data-ttu-id="81f29-217">Vous devez disposer des autorisations nécessaires pour exécuter vos rapports (ou d'autres rapports) à partir du serveur de rapports ou du site SharePoint sur lequel ils sont publiés.</span><span class="sxs-lookup"><span data-stu-id="81f29-217">You need permissions to run your reports or others from the report server or SharePoint site where they are published.</span></span> <span data-ttu-id="81f29-218">Pour obtenir ces autorisations, contactez votre administrateur système.</span><span class="sxs-lookup"><span data-stu-id="81f29-218">Talk to your system administrator to obtain access.</span></span>

 <span data-ttu-id="81f29-219">Avant de continuer, il peut être utile de lire certains documents relatifs à certains concepts et termes.</span><span class="sxs-lookup"><span data-stu-id="81f29-219">It may help to read about some of the concepts and terms before you get started.</span></span> <span data-ttu-id="81f29-220">Pour plus d’informations, consultez [concepts de création de rapports &#40;générateur de rapports et&#41;SSRS ](../report-design/report-authoring-concepts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="81f29-220">For more information, see [Report Authoring Concepts &#40;Report Builder and SSRS&#41;](../report-design/report-authoring-concepts-report-builder-and-ssrs.md).</span></span> <span data-ttu-id="81f29-221">Il est également conseillé d'accorder un peu de temps à la planification avant de créer votre premier rapport.</span><span class="sxs-lookup"><span data-stu-id="81f29-221">Also, spend some time planning, before you create your first report.</span></span> <span data-ttu-id="81f29-222">Ce temps consacré vous sera utile.</span><span class="sxs-lookup"><span data-stu-id="81f29-222">It will be time well spent.</span></span> <span data-ttu-id="81f29-223">Pour plus d’informations, consultez [planification d’un rapport &#40;Générateur de rapports&#41;](../report-design/planning-a-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="81f29-223">For more information, see [Planning a Report &#40;Report Builder&#41;](../report-design/planning-a-report-report-builder.md).</span></span>

 <span data-ttu-id="81f29-224">![Icône de flèche utilisée avec le lien retour en haut](../../2014-toc/media/uparrow16x16.gif "Icône de flèche utilisée avec le lien Retour en haut") [vers le haut](#TwoWays)</span><span class="sxs-lookup"><span data-stu-id="81f29-224">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Back to Top](#TwoWays)</span></span>

## <a name="see-also"></a><span data-ttu-id="81f29-225">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="81f29-225">See Also</span></span>
 <span data-ttu-id="81f29-226">[Didacticiels &#40;Générateur de rapports&#41;](../report-builder-tutorials.md) [Générateur de rapports dans SQL Server 2014](report-builder-in-sql-server-2016.md)</span><span class="sxs-lookup"><span data-stu-id="81f29-226">[Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md) [Report Builder in SQL Server 2014](report-builder-in-sql-server-2016.md)</span></span>


