---
title: Créer un nouvel InfoObject | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3587a633-1c0b-4d63-a22a-6b2b93923c3a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 022f2d1e3fe10ae037ea379a02a18845b3a36107
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613568"
---
# <a name="create-new-infoobject"></a><span data-ttu-id="8045a-102">Créer un nouvel InfoObject</span><span class="sxs-lookup"><span data-stu-id="8045a-102">Create New InfoObject</span></span>
  <span data-ttu-id="8045a-103">Utilisez la boîte de dialogue **Créer un nouvel InfoObject** pour créer un InfoObject dans le système SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="8045a-103">Use the **Create New InfoObject** dialog box to create a new InfoObject in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="8045a-104">Vous pouvez ouvrir la boîte de dialogue **Créer un nouvel InfoObject** à partir de la page **Gestionnaire de connexions** de **l’Éditeur de destination SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="8045a-104">You can open the **Create InfoObject** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="8045a-105">Pour en savoir plus sur la destination SAP BW, consultez [Destination SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="8045a-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8045a-106">La documentation de Microsoft Connector 1.1 pour SAP BW suppose que vous êtes familiarisé avec l'environnement SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="8045a-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="8045a-107">Pour plus d'informations sur SAP Netweaver BW, ou sur la configuration des objets et des processus SAP Netweaver BW objets, consultez la documentation SAP.</span><span class="sxs-lookup"><span data-stu-id="8045a-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="8045a-108">**Pour ouvrir la boîte de dialogue Créer un nouvel InfoObject**</span><span class="sxs-lookup"><span data-stu-id="8045a-108">**To open the Create New InfoObject dialog box**</span></span>  
  
1.  <span data-ttu-id="8045a-109">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui contient la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="8045a-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="8045a-110">Sous l’onglet **Flux de données** , double-cliquez sur la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="8045a-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="8045a-111">Dans l' **Éditeur de destination SAP BW**, cliquez sur **Gestionnaire de connexions** pour ouvrir la page **Gestionnaire de connexions** de l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="8045a-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="8045a-112">Dans la page **Gestionnaire de connexions** , dans la zone de groupe **Créer des objets SAP BW** , procédez de l’une des façons suivantes pour créer un InfoObject :</span><span class="sxs-lookup"><span data-stu-id="8045a-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, do one of the following steps to create an InfoObject:</span></span>  
  
    1.  <span data-ttu-id="8045a-113">Pour créer un InfoObject directement, sélectionnez **InfoObject**, puis cliquez sur **Créer** pour ouvrir la boîte de dialogue **Créer un nouvel InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="8045a-113">To create an InfoObject directly, select **InfoObject**, and then click **Create** to open the **Create New InfoObject** dialog box.</span></span>  
  
    2.  <span data-ttu-id="8045a-114">Pour créer un InfoObject lors de la création d’un InfoCube, sélectionnez **InfoCube**, puis cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="8045a-114">To create an InfoObject while creating an InfoCube, select **InfoCube**, and then click **Create**.</span></span> <span data-ttu-id="8045a-115">Dans la boîte de dialogue **Créer un InfoCube pour les données de transaction** , dans la colonne **IObject** pour l’une des lignes de la liste, sélectionnez **Créer** pour ouvrir la boîte de dialogue **Créer un nouvel InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="8045a-115">In the **Create InfoCube for Transaction Data** dialog box, in the **IObject** column for one of the rows in the list, select **Create** to open the **Create New InfoObject** dialog box.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="8045a-116">Chaque ligne de la table représente une colonne dans le flux de données du package.</span><span class="sxs-lookup"><span data-stu-id="8045a-116">Each row in the table represents a column in the data flow of the package.</span></span>  
  
    3.  <span data-ttu-id="8045a-117">Pour créer un InfoObject lors de la création d’un InfoSouce pour les données transactionnelles, sélectionnez **InfoSource**, puis cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="8045a-117">To create an InfoObject while creating an InfoSouce for transactional data, select **InfoSource**, and then click **Create**.</span></span> <span data-ttu-id="8045a-118">Dans la boîte de dialogue **Créer un InfoSource** , sélectionnez **Données de transaction**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8045a-118">In the **Create InfoSource** dialog box, select **Transaction Data**, and then click **OK**.</span></span> <span data-ttu-id="8045a-119">Dans la boîte de dialogue **Créer un InfoSource pour les données de transaction** , dans la colonne **IObject** pour l’une des lignes de la liste, sélectionnez **Créer** pour ouvrir la boîte de dialogue **Créer un nouvel InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="8045a-119">In the **Create InfoSource for Transaction Data** dialog box, in the **IObject** column for one of the rows in the list, select **Create** to open the **Create New InfoObject** dialog box.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="8045a-120">Chaque ligne de la table représente une colonne dans le flux de données du package.</span><span class="sxs-lookup"><span data-stu-id="8045a-120">Each row in the table represents a column in the data flow of the package.</span></span>  
  
    4.  <span data-ttu-id="8045a-121">Pour créer un InfoObject lors de la création d’un InfoSource pour les données maîtres, sélectionnez **InfoSource**, puis cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="8045a-121">To create an InfoObject while creating an InfoSource for master data, select **InfoSource**, and then click **Create**.</span></span> <span data-ttu-id="8045a-122">Dans la boîte de dialogue **Créer un InfoSource** , sélectionnez **Données maîtres**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8045a-122">In the **Create InfoSource** dialog box, select **Master Data**, and then click **OK**.</span></span> <span data-ttu-id="8045a-123">Dans la boîte de dialogue **Créer un InfoSource pour les données maîtres** , cliquez sur **Nouveau** pour ouvrir la boîte de dialogue **Créer un nouvel InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="8045a-123">In the **Create InfoSource for Master Data** dialog box, click **New** to open the **Create New InfoObject** dialog box.</span></span>  
  
 <span data-ttu-id="8045a-124">Vous pouvez également ouvrir la boîte de dialogue **Créer un nouvel InfoObject** en cliquant sur **Nouveau** dans la section **Attributs** de la boîte de dialogue **Créer un nouvel InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="8045a-124">You can also open the **Create New InfoObject** dialog box by clicking **New** in the **Attributes** section of the **Create New InfoObject** dialog box.</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="8045a-125">Options générales</span><span class="sxs-lookup"><span data-stu-id="8045a-125">General Options</span></span>  
 <span data-ttu-id="8045a-126">**Caractéristique**</span><span class="sxs-lookup"><span data-stu-id="8045a-126">**Characteristic**</span></span>  
 <span data-ttu-id="8045a-127">Créez un InfoObject qui représente des données de dimension.</span><span class="sxs-lookup"><span data-stu-id="8045a-127">Create an InfoObject that represents dimension data.</span></span>  
  
 <span data-ttu-id="8045a-128">**Chiffre clé**</span><span class="sxs-lookup"><span data-stu-id="8045a-128">**Key figure**</span></span>  
 <span data-ttu-id="8045a-129">Créez un InfoObject qui représente des données de faits.</span><span class="sxs-lookup"><span data-stu-id="8045a-129">Create an InfoObject that represents fact data.</span></span>  
  
 <span data-ttu-id="8045a-130">**Nom de l'InfoObject**</span><span class="sxs-lookup"><span data-stu-id="8045a-130">**InfoObject name**</span></span>  
 <span data-ttu-id="8045a-131">Entrez le nom de l'InfoObject.</span><span class="sxs-lookup"><span data-stu-id="8045a-131">Enter a name for the InfoObject.</span></span>  
  
 <span data-ttu-id="8045a-132">**Brève description**</span><span class="sxs-lookup"><span data-stu-id="8045a-132">**Short description**</span></span>  
 <span data-ttu-id="8045a-133">Entrez une brève description pour l'InfoObject.</span><span class="sxs-lookup"><span data-stu-id="8045a-133">Enter a short description for the InfoObject.</span></span>  
  
 <span data-ttu-id="8045a-134">**Description longue**</span><span class="sxs-lookup"><span data-stu-id="8045a-134">**Long description**</span></span>  
 <span data-ttu-id="8045a-135">Entrez une longue description pour l'InfoObject.</span><span class="sxs-lookup"><span data-stu-id="8045a-135">Enter a long description for the InfoObject.</span></span>  
  
 <span data-ttu-id="8045a-136">**Comporte des données maîtres**</span><span class="sxs-lookup"><span data-stu-id="8045a-136">**Has master data**</span></span>  
 <span data-ttu-id="8045a-137">Indique que l'InfoObject contient des données maîtres sous la forme d'attributs, de textes ou de hiérarchies.</span><span class="sxs-lookup"><span data-stu-id="8045a-137">Indicate that the InfoObject contains master data in the form of attributes, texts, or hierarchies.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8045a-138">Sélectionnez cette option si l’InfoObject représente des données dimensionnelles et que vous avez sélectionné l’option **Caractéristique** .</span><span class="sxs-lookup"><span data-stu-id="8045a-138">Select this option if the InfoObject represents dimensional data and you have selected the **Characteristic** option.</span></span>  
  
 <span data-ttu-id="8045a-139">**Autoriser les minuscules**</span><span class="sxs-lookup"><span data-stu-id="8045a-139">**Allow lower-case characters**</span></span>  
 <span data-ttu-id="8045a-140">Autorisez les minuscules dans les données de l'InfoObject.</span><span class="sxs-lookup"><span data-stu-id="8045a-140">Allow lower-case characters in the InfoObject data.</span></span>  
  
 <span data-ttu-id="8045a-141">**Enregistrer et activer**</span><span class="sxs-lookup"><span data-stu-id="8045a-141">**Save & Activate**</span></span>  
 <span data-ttu-id="8045a-142">Enregistrez et activez le nouvel InfoObject.</span><span class="sxs-lookup"><span data-stu-id="8045a-142">Save and active the new InfoObject.</span></span>  
  
## <a name="data-type-options"></a><span data-ttu-id="8045a-143">Options de type de données</span><span class="sxs-lookup"><span data-stu-id="8045a-143">Data Type Options</span></span>  
 <span data-ttu-id="8045a-144">**CHAR - Chaîne de caractères**</span><span class="sxs-lookup"><span data-stu-id="8045a-144">**CHAR - Character String**</span></span>  
 <span data-ttu-id="8045a-145">Indique que l'InfoObject contient des données caractères.</span><span class="sxs-lookup"><span data-stu-id="8045a-145">Indicates that the InfoObject contains character data.</span></span>  
  
 <span data-ttu-id="8045a-146">**NUMC - Chaîne numérique**</span><span class="sxs-lookup"><span data-stu-id="8045a-146">**NUMC - Numeric String**</span></span>  
 <span data-ttu-id="8045a-147">Indique que l'InfoObject contient des données numériques.</span><span class="sxs-lookup"><span data-stu-id="8045a-147">Indicates that the InfoObject contains numeric data.</span></span>  
  
 <span data-ttu-id="8045a-148">**DATS - Date (AAAMMJJ)**</span><span class="sxs-lookup"><span data-stu-id="8045a-148">**DATS - Date (YYYYMMDD)**</span></span>  
 <span data-ttu-id="8045a-149">Indique que l'InfoObject contient des données de date.</span><span class="sxs-lookup"><span data-stu-id="8045a-149">Indicates that the InfoObject contains date data.</span></span>  
  
 <span data-ttu-id="8045a-150">**TIMS - Heure (HHMMSS)**</span><span class="sxs-lookup"><span data-stu-id="8045a-150">**TIMS - Time (HHMMSS)**</span></span>  
 <span data-ttu-id="8045a-151">Indique que l'InfoObject contient des données d'heure.</span><span class="sxs-lookup"><span data-stu-id="8045a-151">Indicates that the InfoObject contains time data.</span></span>  
  
 <span data-ttu-id="8045a-152">**Longueur**</span><span class="sxs-lookup"><span data-stu-id="8045a-152">**Length**</span></span>  
 <span data-ttu-id="8045a-153">Entrez la longueur des données.</span><span class="sxs-lookup"><span data-stu-id="8045a-153">Enter the length of the data.</span></span>  
  
## <a name="text-options"></a><span data-ttu-id="8045a-154">Options de texte</span><span class="sxs-lookup"><span data-stu-id="8045a-154">Text Options</span></span>  
 <span data-ttu-id="8045a-155">**Avec textes**</span><span class="sxs-lookup"><span data-stu-id="8045a-155">**With Texts**</span></span>  
 <span data-ttu-id="8045a-156">Indique que l'InfoObject contient des textes.</span><span class="sxs-lookup"><span data-stu-id="8045a-156">Indicate that the InfoObject contains texts.</span></span>  
  
 <span data-ttu-id="8045a-157">**Texte court**</span><span class="sxs-lookup"><span data-stu-id="8045a-157">**Short Text**</span></span>  
 <span data-ttu-id="8045a-158">Indique que l'InfoObject contient des textes courts.</span><span class="sxs-lookup"><span data-stu-id="8045a-158">Indicates that the InfoObject contains short texts.</span></span>  
  
 <span data-ttu-id="8045a-159">**Texte moyen**</span><span class="sxs-lookup"><span data-stu-id="8045a-159">**Medium Text**</span></span>  
 <span data-ttu-id="8045a-160">Indique que l'InfoObject contient des textes moyens.</span><span class="sxs-lookup"><span data-stu-id="8045a-160">Indicates that the InfoObject contains medium texts.</span></span>  
  
 <span data-ttu-id="8045a-161">**Texte long**</span><span class="sxs-lookup"><span data-stu-id="8045a-161">**Long Text**</span></span>  
 <span data-ttu-id="8045a-162">Indique que l'InfoObject contient des textes longs.</span><span class="sxs-lookup"><span data-stu-id="8045a-162">Indicates that the InfoObject contains long texts.</span></span>  
  
 <span data-ttu-id="8045a-163">**Texte dépendant de la langue**</span><span class="sxs-lookup"><span data-stu-id="8045a-163">**Text Language-Dependent**</span></span>  
 <span data-ttu-id="8045a-164">Indique que les textes sont dépendants de la langue.</span><span class="sxs-lookup"><span data-stu-id="8045a-164">Indicates that the texts are language-dependent.</span></span>  
  
 <span data-ttu-id="8045a-165">**Texte dépendant de l'heure**</span><span class="sxs-lookup"><span data-stu-id="8045a-165">**Text Time-Dependent**</span></span>  
 <span data-ttu-id="8045a-166">Indique que les textes sont dépendants de l'heure.</span><span class="sxs-lookup"><span data-stu-id="8045a-166">Indicates that the texts are time-dependent.</span></span>  
  
## <a name="attributes-section"></a><span data-ttu-id="8045a-167">Section Attributs</span><span class="sxs-lookup"><span data-stu-id="8045a-167">Attributes Section</span></span>  
 <span data-ttu-id="8045a-168">La section **Attributs** se compose d’une liste d’attributs pour l’InfoObject et des options qui vous permettent d’ajouter et de supprimer des attributs dans la liste.</span><span class="sxs-lookup"><span data-stu-id="8045a-168">The **Attributes** section consists of a list of attributes for the InfoObject, and the options that let you add and remove attributes from the list.</span></span>  
  
### <a name="attributes-list"></a><span data-ttu-id="8045a-169">Liste des attributs</span><span class="sxs-lookup"><span data-stu-id="8045a-169">Attributes List</span></span>  
 <span data-ttu-id="8045a-170">La liste **Attributs** affiche les attributs de l’InfoObject en cours de création.</span><span class="sxs-lookup"><span data-stu-id="8045a-170">The **Attributes** list displays the attributes of the InfoObject that you are creating.</span></span> <span data-ttu-id="8045a-171">La liste **Attributs** comporte les en-têtes de colonnes suivants :</span><span class="sxs-lookup"><span data-stu-id="8045a-171">The **Attributes** list has the following column headings:</span></span>  
  
 <span data-ttu-id="8045a-172">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="8045a-172">**InfoObject**</span></span>  
 <span data-ttu-id="8045a-173">Affichez le nom de l'InfoObject.</span><span class="sxs-lookup"><span data-stu-id="8045a-173">View the name of the InfoObject.</span></span>  
  
 <span data-ttu-id="8045a-174">**Description**</span><span class="sxs-lookup"><span data-stu-id="8045a-174">**Description**</span></span>  
 <span data-ttu-id="8045a-175">Affichez la description de l'InfoObject.</span><span class="sxs-lookup"><span data-stu-id="8045a-175">View the description of the InfoObject.</span></span>  
  
 <span data-ttu-id="8045a-176">**Type d'InfoObject**</span><span class="sxs-lookup"><span data-stu-id="8045a-176">**InfoObject Type**</span></span>  
 <span data-ttu-id="8045a-177">Affichez le type de l'InfoObject.</span><span class="sxs-lookup"><span data-stu-id="8045a-177">View the type of the InfoObject.</span></span> <span data-ttu-id="8045a-178">Le tableau suivant répertorie les valeurs possibles pour le type.</span><span class="sxs-lookup"><span data-stu-id="8045a-178">The following table lists the possible values for the type.</span></span>  
  
|<span data-ttu-id="8045a-179">Valeur</span><span class="sxs-lookup"><span data-stu-id="8045a-179">Value</span></span>|<span data-ttu-id="8045a-180">Description</span><span class="sxs-lookup"><span data-stu-id="8045a-180">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8045a-181">CHA</span><span class="sxs-lookup"><span data-stu-id="8045a-181">CHA</span></span>|<span data-ttu-id="8045a-182">Caractéristiques</span><span class="sxs-lookup"><span data-stu-id="8045a-182">Characteristics</span></span>|  
|<span data-ttu-id="8045a-183">KYF</span><span class="sxs-lookup"><span data-stu-id="8045a-183">KYF</span></span>|<span data-ttu-id="8045a-184">Chiffres clés</span><span class="sxs-lookup"><span data-stu-id="8045a-184">Key figures</span></span>|  
|<span data-ttu-id="8045a-185">UNI</span><span class="sxs-lookup"><span data-stu-id="8045a-185">UNI</span></span>|<span data-ttu-id="8045a-186">Units</span><span class="sxs-lookup"><span data-stu-id="8045a-186">Units</span></span>|  
|<span data-ttu-id="8045a-187">TIM</span><span class="sxs-lookup"><span data-stu-id="8045a-187">TIM</span></span>|<span data-ttu-id="8045a-188">Caractéristiques de temps</span><span class="sxs-lookup"><span data-stu-id="8045a-188">Time characteristics</span></span>|  
  
### <a name="attributes-options"></a><span data-ttu-id="8045a-189">Options des attributs</span><span class="sxs-lookup"><span data-stu-id="8045a-189">Attributes Options</span></span>  
 <span data-ttu-id="8045a-190">Utilisez les options suivantes pour ajouter et supprimer des attributs pour l'InfoObject en cours de création :</span><span class="sxs-lookup"><span data-stu-id="8045a-190">Use the following options to add and remove attributes for the InfoObject that you are creating:</span></span>  
  
 <span data-ttu-id="8045a-191">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="8045a-191">**Add**</span></span>  
 <span data-ttu-id="8045a-192">Ajoutez un InfoObject existant comme attribut.</span><span class="sxs-lookup"><span data-stu-id="8045a-192">Add an existing InfoObject as an attribute.</span></span>  
  
 <span data-ttu-id="8045a-193">Pour ajouter un InfoObject existant, cliquez sur Ajouter, puis utilisez la boîte de dialogue **Rechercher un InfoObject** pour trouver l’InfoObject.</span><span class="sxs-lookup"><span data-stu-id="8045a-193">To add an existing InfoObject, click Add, and then use the **Look Up InfoObject** dialog box to find the InfoObject.</span></span> <span data-ttu-id="8045a-194">Pour plus d’informations sur cette boîte de dialogue, consultez [Rechercher un InfoObject](look-up-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="8045a-194">For more information about this dialog box, see [Look Up InfoObject](look-up-infoobject.md).</span></span>  
  
 <span data-ttu-id="8045a-195">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="8045a-195">**New**</span></span>  
 <span data-ttu-id="8045a-196">Ajoutez un nouvel InfoObject comme attribut.</span><span class="sxs-lookup"><span data-stu-id="8045a-196">Add a new InfoObject as an attribute.</span></span>  
  
 <span data-ttu-id="8045a-197">Pour créer et ajouter un nouvel InfoObject, cliquez sur Nouveau, puis utilisez une nouvelle instance de la boîte de dialogue **Créer un nouvel InfoObject** pour créer l’InfoObject.</span><span class="sxs-lookup"><span data-stu-id="8045a-197">To create and add a new InfoObject, click New, and then use a new instance of the **Create New InfoObject** dialog box to create the new InfoObject.</span></span>  
  
 <span data-ttu-id="8045a-198">**Remove**</span><span class="sxs-lookup"><span data-stu-id="8045a-198">**Remove**</span></span>  
 <span data-ttu-id="8045a-199">Supprimez l’InfoObject sélectionné de la liste **Attributs** .</span><span class="sxs-lookup"><span data-stu-id="8045a-199">Remove the selected InfoObject from the **Attributes** list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8045a-200">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8045a-200">See Also</span></span>  
 <span data-ttu-id="8045a-201">[Créer un InfoCube pour les données de transaction](create-infocube-for-transaction-data.md) </span><span class="sxs-lookup"><span data-stu-id="8045a-201">[Create InfoCube for Transaction Data](create-infocube-for-transaction-data.md) </span></span>  
 <span data-ttu-id="8045a-202">[Créer un InfoSource](create-infosource.md) </span><span class="sxs-lookup"><span data-stu-id="8045a-202">[Create InfoSource](create-infosource.md) </span></span>  
 <span data-ttu-id="8045a-203">[Créer un InfoSource pour les données de transaction](create-infosource-for-transaction-data.md) </span><span class="sxs-lookup"><span data-stu-id="8045a-203">[Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md) </span></span>  
 <span data-ttu-id="8045a-204">[Créer un InfoSource pour les données maîtres](create-infosource-for-master-data.md) </span><span class="sxs-lookup"><span data-stu-id="8045a-204">[Create InfoSource for Master Data](create-infosource-for-master-data.md) </span></span>  
 [<span data-ttu-id="8045a-205">Aide (F1) sur Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="8045a-205">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
