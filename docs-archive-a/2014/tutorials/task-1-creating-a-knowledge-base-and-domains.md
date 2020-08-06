---
title: 'Tâche 1 : création d’une base de connaissances et de domaines | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 7d74a60b-8933-4038-bcbb-4e9dcc4f70e9
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ce1b22e3d677e831a1d518dacc1267ad0e6be236
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699059"
---
# <a name="task-1-creating-a-knowledge-base-and-domains"></a><span data-ttu-id="99f1a-102">Tâche 1 : Création d’une base de connaissances et de domaines</span><span class="sxs-lookup"><span data-stu-id="99f1a-102">Task 1: Creating a Knowledge Base and Domains</span></span>
  <span data-ttu-id="99f1a-103">Au cours de cette tâche, vous allez créer la base de connaissances **fournisseurs** et créer des domaines qui sont utilisés pour nettoyer les données et les données correspondantes pour supprimer les doublons.</span><span class="sxs-lookup"><span data-stu-id="99f1a-103">In this task, you create the **Suppliers** knowledge base and create domains that is used for cleansing data and matching data to remove duplicates.</span></span>  
  
1.  <span data-ttu-id="99f1a-104">Lancez **Data Quality client**.</span><span class="sxs-lookup"><span data-stu-id="99f1a-104">Launch **Data Quality Client**.</span></span> <span data-ttu-id="99f1a-105">Cliquez sur **Démarrer**, pointez sur **tous les programmes**, cliquez sur **Microsoft SQL Server 2012**, sur **Data Quality Services**, puis sur **Data Quality client**.</span><span class="sxs-lookup"><span data-stu-id="99f1a-105">Click **Start**, point to **All Programs**, click **Microsoft SQL Server 2012**, click **Data Quality Services**, and then click **Data Quality Client**.</span></span>  
  
2.  <span data-ttu-id="99f1a-106">Dans la boîte de dialogue **se connecter au serveur** , sélectionnez l’instance de serveur de base de données sur laquelle le DQS est installé, puis cliquez sur **se connecter**.</span><span class="sxs-lookup"><span data-stu-id="99f1a-106">In the **Connect to Server** dialog box, select the database server instance on which the DQS is installed, and click **Connect**.</span></span>  
  
     <span data-ttu-id="99f1a-107">![Boîte de dialogue se connecter au serveur](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-01.jpg "Boîte de dialogue Connexion au serveur")</span><span class="sxs-lookup"><span data-stu-id="99f1a-107">![Connect to Server Dialog Box](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-01.jpg "Connect to Server Dialog Box")</span></span>  
  
3.  <span data-ttu-id="99f1a-108">Dans la page d’espace de Data Quality Client, dans le volet gestion de la **base de connaissances** , cliquez sur **nouvelle base de connaissances**.</span><span class="sxs-lookup"><span data-stu-id="99f1a-108">In the Data Quality Client home page, in the **Knowledge Base Management** pane, click **New Knowledge Base**.</span></span>  
  
     <span data-ttu-id="99f1a-109">![Gestion des bases de connaissances - Nouvelle base de connaissances](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-02.jpg "Gestion des bases de connaissances - Nouvelle base de connaissances")</span><span class="sxs-lookup"><span data-stu-id="99f1a-109">![Knowledge Base Management - New KB](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-02.jpg "Knowledge Base Management - New KB")</span></span>  
  
4.  <span data-ttu-id="99f1a-110">Entrez **Suppliers** pour le **nom** de la base de connaissances.</span><span class="sxs-lookup"><span data-stu-id="99f1a-110">Enter **Suppliers** for **Name** of the knowledge base.</span></span>  
  
     <span data-ttu-id="99f1a-111">![Nouvelle base de connaissances - Gestion du domaine](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-03.jpg "Nouvelle base de connaissances - Gestion du domaine")</span><span class="sxs-lookup"><span data-stu-id="99f1a-111">![New Knowledge Base - Domain Management](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-03.jpg "New Knowledge Base - Domain Management")</span></span>  
  
5.  <span data-ttu-id="99f1a-112">Vérifiez que l’option **créer une base de connaissances à partir de** est définie sur **aucun** , car vous créez la base de connaissances **fournisseurs** à partir de zéro.</span><span class="sxs-lookup"><span data-stu-id="99f1a-112">Confirm that **Create Knowledge Base from** field is set to **None** since you are creating the **Suppliers** knowledge base from scratch.</span></span>  
  
6.  <span data-ttu-id="99f1a-113">Vérifiez que **gestion de domaine** est sélectionné pour l' **activité** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="99f1a-113">Confirm that **Domain Management** is selected for the **Activity** and click **Next**.</span></span> <span data-ttu-id="99f1a-114">L'activité de Gestion de l'arborescence du domaine vous permet de créer et gérer des domaines dans la base de connaissances.</span><span class="sxs-lookup"><span data-stu-id="99f1a-114">The Domain Management activity lets you create and manage domains in the knowledge base.</span></span>  
  
7.  <span data-ttu-id="99f1a-115">Dans la fenêtre **gestion des domaines** , cliquez sur le bouton **créer un domaine** de la barre d’outils pour créer un domaine.</span><span class="sxs-lookup"><span data-stu-id="99f1a-115">In the **Domain Management** window, click **Create a domain** toolbar button to create a domain.</span></span>  
  
     <span data-ttu-id="99f1a-116">![Bouton de la barre d'outils Créer un domaine](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-04.jpg "Bouton de la barre d'outils Créer un domaine")</span><span class="sxs-lookup"><span data-stu-id="99f1a-116">![Create Domain Toolbar Button](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-04.jpg "Create Domain Toolbar Button")</span></span>  
  
8.  <span data-ttu-id="99f1a-117">Dans la boîte de dialogue **créer un domaine** , tapez **ID du fournisseur** pour le **nom de domaine**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="99f1a-117">In the **Create Domain** dialog box, type **Supplier ID** for the **Domain Name**, and click **OK**.</span></span>  
  
     <span data-ttu-id="99f1a-118">![Boîte de dialogue Créer une table](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-05.jpg "Boîte de dialogue Créer une table")</span><span class="sxs-lookup"><span data-stu-id="99f1a-118">![Create Domain Dialog Box](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-05.jpg "Create Domain Dialog Box")</span></span>  
  
9. <span data-ttu-id="99f1a-119">Répétez l'étape précédente pour créer les domaines suivants avec les paramètres par défaut.</span><span class="sxs-lookup"><span data-stu-id="99f1a-119">Repeat previous step to create the following domains with all the default settings.</span></span> <span data-ttu-id="99f1a-120">Pour simplifier le didacticiel, vous définissez le **type de données** de tous les domaines en tant que **chaîne**.</span><span class="sxs-lookup"><span data-stu-id="99f1a-120">To keep the tutorial simple, you set the **Data Type** of all the domains as **String**.</span></span> <span data-ttu-id="99f1a-121">Les autres types de données autorisés sont : entier, décimal, et date.</span><span class="sxs-lookup"><span data-stu-id="99f1a-121">The other allowed data types are: Integer, Decimal, and Date.</span></span> <span data-ttu-id="99f1a-122">Lorsque l’option **utiliser des valeurs de début** est sélectionnée (valeur par défaut), tous les synonymes sont remplacés par la valeur de début du groupe de synonymes dans la sortie.</span><span class="sxs-lookup"><span data-stu-id="99f1a-122">When the **Use Leading Values** option is selected (default), all synonyms are replaced with the leading value of the synonym group in the output.</span></span> <span data-ttu-id="99f1a-123">La définition de l’option **normaliser la chaîne** (valeur par défaut) supprime tous les caractères spéciaux dans les valeurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="99f1a-123">Setting **Normalize String** option (default) removes any special characters in the domain values.</span></span> <span data-ttu-id="99f1a-124">L’option **mettre en forme la sortie vers** vous permet de sélectionner la mise en forme qui est appliquée lorsque les valeurs de données dans le domaine sont générées.</span><span class="sxs-lookup"><span data-stu-id="99f1a-124">The **Format Output to** option lets you select the formatting that is applied when the data values in the domain are output.</span></span> <span data-ttu-id="99f1a-125">Sélectionnez **activer le vérificateur d’orthographe** (par défaut) pour exécuter le vérificateur d’orthographe sur toutes les valeurs de chaîne lors du remplissage du domaine.</span><span class="sxs-lookup"><span data-stu-id="99f1a-125">Select **Enable Speller** (default) to run Speller on all string values when populating the domain.</span></span> <span data-ttu-id="99f1a-126">Le paramètre de **langue** spécifie la version linguistique du **vérificateur d’orthographe** que vous souhaitez appliquer.</span><span class="sxs-lookup"><span data-stu-id="99f1a-126">The **Language** setting specifies which language version of the **Speller** you want to apply.</span></span> <span data-ttu-id="99f1a-127">Sélectionnez **Désactiver les algorithmes d’erreur de syntaxe** pour remplir le domaine sans vérifier les valeurs de chaîne pour les erreurs de syntaxe.</span><span class="sxs-lookup"><span data-stu-id="99f1a-127">Select **Disable Syntax Error Algorithms** to populate the domain without checking string values for syntax errors.</span></span> <span data-ttu-id="99f1a-128">Pour plus d’informations, consultez la rubrique [créer un domaine](https://msdn.microsoft.com/library/hh510401.aspx) dans MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="99f1a-128">See [Create a Domain](https://msdn.microsoft.com/library/hh510401.aspx) topic in the MSDN library for more details.</span></span>  
  
    -   <span data-ttu-id="99f1a-129">Nom du fournisseur</span><span class="sxs-lookup"><span data-stu-id="99f1a-129">Supplier Name</span></span>  
  
    -   <span data-ttu-id="99f1a-130">E-mail du contact</span><span class="sxs-lookup"><span data-stu-id="99f1a-130">Contact Email</span></span>  
  
    -   <span data-ttu-id="99f1a-131">Adresse</span><span class="sxs-lookup"><span data-stu-id="99f1a-131">Address Line</span></span>  
  
    -   <span data-ttu-id="99f1a-132">City</span><span class="sxs-lookup"><span data-stu-id="99f1a-132">City</span></span>  
  
    -   <span data-ttu-id="99f1a-133">State</span><span class="sxs-lookup"><span data-stu-id="99f1a-133">State</span></span>  
  
    -   <span data-ttu-id="99f1a-134">Pays ou région</span><span class="sxs-lookup"><span data-stu-id="99f1a-134">Country</span></span>  
  
    -   <span data-ttu-id="99f1a-135">Zip</span><span class="sxs-lookup"><span data-stu-id="99f1a-135">Zip</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="99f1a-136">étape suivante</span><span class="sxs-lookup"><span data-stu-id="99f1a-136">Next Step</span></span>  
 [<span data-ttu-id="99f1a-137">Tâche 2 : Ajout de valeurs de domaine manuellement</span><span class="sxs-lookup"><span data-stu-id="99f1a-137">Task 2: Adding Domain Values Manually</span></span>](../../2014/tutorials/task-2-adding-domain-values-manually.md)  
  
  
