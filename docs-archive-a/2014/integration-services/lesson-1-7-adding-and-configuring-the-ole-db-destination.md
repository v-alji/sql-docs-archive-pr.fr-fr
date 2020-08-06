---
title: 'Étape 7 : Ajout et configuration de la destination OLE DB | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 442c841d-d528-4bf0-8724-7156f909ee50
author: chugugrace
ms.author: chugu
ms.openlocfilehash: da917ccc4ca756c2442e70477976b5a71f7eb56e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605575"
---
# <a name="step-7-adding-and-configuring-the-ole-db-destination"></a><span data-ttu-id="717c6-102">Étape 7 : Ajout et configuration de la destination OLE DB</span><span class="sxs-lookup"><span data-stu-id="717c6-102">Step 7: Adding and Configuring the OLE DB Destination</span></span>
  <span data-ttu-id="717c6-103">Votre package peut maintenant extraire des données à partir de la source de fichier plat pour les transformer dans un format compatible avec la destination.</span><span class="sxs-lookup"><span data-stu-id="717c6-103">Your package now can extract data from the flat file source and transform that data into a format that is compatible with the destination.</span></span> <span data-ttu-id="717c6-104">La tâche suivante consiste à charger les données transformées dans la destination.</span><span class="sxs-lookup"><span data-stu-id="717c6-104">The next task is to actually load the transformed data into the destination.</span></span> <span data-ttu-id="717c6-105">Pour charger les données, vous devez ajouter une destination OLE DB au flux de données.</span><span class="sxs-lookup"><span data-stu-id="717c6-105">To load the data, you must add an OLE DB destination to the data flow.</span></span> <span data-ttu-id="717c6-106">La destination OLE DB peut utiliser une table de base de données, un affichage ou une commande SQL pour charger les données dans plusieurs bases de données compatibles OLE DB.</span><span class="sxs-lookup"><span data-stu-id="717c6-106">The OLE DB destination can use a database table, view, or an SQL command to load data into a variety of OLE DB-compliant databases.</span></span>  
  
 <span data-ttu-id="717c6-107">Au cours de cette procédure, vous allez ajouter et configurer une destination OLE DB pour utiliser le Gestionnaire de connexions OLE DB que vous avez créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="717c6-107">In this procedure, you add and configure an OLE DB destination to use the OLE DB connection manager that you previously created.</span></span>  
  
### <a name="to-add-and-configure-the-sample-ole-db-destination"></a><span data-ttu-id="717c6-108">Pour ajouter et configurer la destination OLE DB fournie en exemple</span><span class="sxs-lookup"><span data-stu-id="717c6-108">To add and configure the sample OLE DB destination</span></span>  
  
1.  <span data-ttu-id="717c6-109">Dans la **boîte à outils SSIS**, développez **autres destinations**, puis faites glisser **OLE DB destination** sur l’aire de conception de l’onglet de **Workflow** . Placez le OLE DB destination directement sous la transformation **Lookup Date Key** .</span><span class="sxs-lookup"><span data-stu-id="717c6-109">In the **SSIS Toolbox**, expand **Other Destinations**, and drag **OLE DB Destination** onto the design surface of the **Data Flow** tab. Place the OLE DB destination directly below the **Lookup Date Key** transformation.</span></span>  
  
2.  <span data-ttu-id="717c6-110">Sélectionnez la transformation **Lookup Date Key** et faites glisser la flèche verte vers la nouvelle **Destination OLE DB** pour connecter les deux composants.</span><span class="sxs-lookup"><span data-stu-id="717c6-110">Click the **Lookup Date Key** transformation and drag the green arrow over to the newly added **OLE DB Destination** to connect the two components together.</span></span>  
  
3.  <span data-ttu-id="717c6-111">Dans la boîte de dialogue **Sélection entrée et sortie** , dans la zone de liste de **Sortie** , cliquez sur **Sortie de recherche avec correspondance**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="717c6-111">In the **Input Output Selection** dialog box, in the **Output** list box, click **Lookup Match Output**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="717c6-112">Sur l’aire de conception **Flux de données** , cliquez sur **Destination OLE DB** dans le composant **Destination OLE DB** que vous venez d’ajouter, puis remplacez le nom par **Sample OLE DB Destination**.</span><span class="sxs-lookup"><span data-stu-id="717c6-112">On the **Data Flow** design surface, click **OLE DB Destination** in the newly added **OLE DB Destination** component, and change the name to **Sample OLE DB Destination**.</span></span>  
  
5.  <span data-ttu-id="717c6-113">Double-cliquez sur **Sample OLE DB Destination**.</span><span class="sxs-lookup"><span data-stu-id="717c6-113">Double-click **Sample OLE DB Destination**.</span></span>  
  
6.  <span data-ttu-id="717c6-114">Dans la boîte de dialogue **Éditeur de destination OLE DB** , vérifiez que **localhost.AdventureWorksDW2012** est sélectionné dans la zone **Gestionnaire de connexions OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="717c6-114">In the **OLE DB Destination Editor** dialog box, ensure that **localhost.AdventureWorksDW2012** is selected in the **OLE DB Connection manager** box.</span></span>  
  
7.  <span data-ttu-id="717c6-115">Dans la zone **Nom de la table ou de la vue** , tapez ou sélectionnez **[dbo].[FactCurrencyRate]**.</span><span class="sxs-lookup"><span data-stu-id="717c6-115">In the **Name of the table or the view** box, type or select **[dbo].[FactCurrencyRate]**.</span></span>  
  
8.  <span data-ttu-id="717c6-116">Cliquez sur le bouton **Nouveau** pour créer une table.</span><span class="sxs-lookup"><span data-stu-id="717c6-116">Click the **New** button to create a new table.</span></span>  <span data-ttu-id="717c6-117">Modifiez le nom de la table dans le script en **NewFactCurrencyRate**.</span><span class="sxs-lookup"><span data-stu-id="717c6-117">Change the name of the table in the script to read **NewFactCurrencyRate**.</span></span>  <span data-ttu-id="717c6-118">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="717c6-118">Click **OK**.</span></span>  
  
9. <span data-ttu-id="717c6-119">Après avoir cliqué sur **OK**, la boîte de dialogue se ferme et **Nom de la table ou de la vue** est automatiquement modifié en **NewFactCurrencyRate**.</span><span class="sxs-lookup"><span data-stu-id="717c6-119">Upon clicking **OK**, the dialog will close and the **Name of the table or the view** will automatically change to **NewFactCurrencyRate**.</span></span>  
  
10. <span data-ttu-id="717c6-120">Cliquez sur **Mappages**.</span><span class="sxs-lookup"><span data-stu-id="717c6-120">Click **Mappings**.</span></span>  
  
11. <span data-ttu-id="717c6-121">Vérifiez que les colonnes d’entrée **AverageRate**, **CurrencyKey**, **EndOfDayRate**et **DateKey** sont correctement mappées aux colonnes de destination.</span><span class="sxs-lookup"><span data-stu-id="717c6-121">Verify that the **AverageRate**, **CurrencyKey**, **EndOfDayRate**, and **DateKey** input columns are mapped correctly to the destination columns.</span></span> <span data-ttu-id="717c6-122">Si des colonnes aux noms identiques sont mappées, le mappage est correct.</span><span class="sxs-lookup"><span data-stu-id="717c6-122">If same-named columns are mapped, the mapping is correct.</span></span>  
  
12. <span data-ttu-id="717c6-123">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="717c6-123">Click **OK**.</span></span>  
  
13. <span data-ttu-id="717c6-124">Cliquez avec le bouton droit sur la **Destination OLE DB exemple** , puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="717c6-124">Right-click the **Sample OLE DB Destination** destination and click **Properties**.</span></span>  
  
14. <span data-ttu-id="717c6-125">Dans la Fenêtre Propriétés, vérifiez que la `LocaleID` propriété est définie sur **anglais (États-Unis)** et que la `DefaultCodePage` propriété a la valeur **1252**.</span><span class="sxs-lookup"><span data-stu-id="717c6-125">In the Properties window, verify that the `LocaleID` property is set to **English (United States)** and the`DefaultCodePage` property is set to **1252**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="717c6-126">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="717c6-126">Next Task in Lesson</span></span>  
 [<span data-ttu-id="717c6-127">Étape 8 : Comment rendre le package de la leçon 1 plus facile à assimiler</span><span class="sxs-lookup"><span data-stu-id="717c6-127">Step 8: Making the Lesson 1 Package Easier to Understand</span></span>](lesson-1-8-making-the-lesson-1-package-easier-to-understand.md)  
  
## <a name="see-also"></a><span data-ttu-id="717c6-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="717c6-128">See Also</span></span>  
 [<span data-ttu-id="717c6-129">Destination OLE DB</span><span class="sxs-lookup"><span data-stu-id="717c6-129">OLE DB Destination</span></span>](data-flow/ole-db-destination.md)  
  
  
