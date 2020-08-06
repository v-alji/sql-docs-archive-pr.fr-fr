---
title: Créer une règle de domaine | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.kb.createdomain.f1
ms.assetid: 5c4828f5-bd51-4c29-b3de-87b7d2f2d3e5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fad6abd795aa9412bb71d251623d92d3e13b889c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601718"
---
# <a name="create-a-domain"></a><span data-ttu-id="b2b3c-102">Créer un domaine</span><span class="sxs-lookup"><span data-stu-id="b2b3c-102">Create a Domain</span></span>
  <span data-ttu-id="b2b3c-103">Cette rubrique décrit comment créer un domaine dans [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="b2b3c-103">This topic describes how to create a domain in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="b2b3c-104">Les valeurs du domaine sont une représentation sémantique des données d'un champ.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-104">The values in the domain are a semantic representation of the data in a field.</span></span> <span data-ttu-id="b2b3c-105">Pour plus d’informations sur les domaines, consultez [Gestion d’un domaine](../../2014/data-quality-services/managing-a-domain.md).</span><span class="sxs-lookup"><span data-stu-id="b2b3c-105">For more information on domains, see [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md).</span></span>  
  
 <span data-ttu-id="b2b3c-106">Il existe deux méthodes pour créer un domaine :</span><span class="sxs-lookup"><span data-stu-id="b2b3c-106">There are two ways to create a new domain.</span></span> <span data-ttu-id="b2b3c-107">La première se situe pendant l'étape Mapper de l'activité de découverte des connaissances, lorsque vous êtes en cours d'analyse d'un exemple de données pour ajouter des connaissances à une base nouvelle ou existante.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-107">The first is during the Map step of the knowledge discovery activity, when you are in the process of analyzing a data sample to add knowledge to a new or existing knowledge base.</span></span> <span data-ttu-id="b2b3c-108">La deuxième se situe pendant l'activité de gestion de l'arborescence du domaine quand, au lieu de modifier un domaine existant, vous en créez un nouveau.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-108">The second is during the domain management activity, when instead of changing an existing domain, you create a new one.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b2b3c-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="b2b3c-109">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="b2b3c-110">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="b2b3c-110">Prerequisites</span></span>  
 <span data-ttu-id="b2b3c-111">Pour créer un domaine, vous devez avoir créé et ouvert une base de connaissances.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-111">To create a domain, you must have created and opened a knowledge base.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b2b3c-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b2b3c-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b2b3c-113">Autorisations</span><span class="sxs-lookup"><span data-stu-id="b2b3c-113">Permissions</span></span>  
 <span data-ttu-id="b2b3c-114">Vous devez disposer du rôle dqs_kb_editor ou dqs_administrator sur la base de données DQS_MAIN pour créer un domaine.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-114">You must have the dqs_kb_editor role or the dqs_administrator on the DQS_MAIN database to create a domain.</span></span>  
  
##  <a name="create-a-domain-in-the-knowledge-discovery-activity"></a><a name="Discovery"></a> <span data-ttu-id="b2b3c-115">Créer un domaine dans l'activité de découverte des connaissances</span><span class="sxs-lookup"><span data-stu-id="b2b3c-115">Create a Domain in the Knowledge Discovery Activity</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="b2b3c-116">[Exécutez l’Application Data Quality client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="b2b3c-116">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="b2b3c-117">Dans l'écran d'accueil de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , cliquez sur **Ouvrir la base de connaissances** , puis sélectionnez une base de connaissances ou cliquez sur **Nouvelle Base de connaissances** et entrez les propriétés de la base de connaissances.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-117">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open knowledge base** and then select a knowledge base, or click **New knowledge base** and enter properties for the new knowledge base.</span></span>  
  
3.  <span data-ttu-id="b2b3c-118">Sélectionnez **Découverte des connaissances** comme activité, puis cliquez sur **Créer** pour créer la base de connaissances ou sur **Ouvrir** pour ouvrir une base de connaissances existante.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-118">Select **Knowledge Discovery** as the activity, and then click **Create** to create the new knowledge base or **Open** to open an existing knowledge base.</span></span>  
  
4.  <span data-ttu-id="b2b3c-119">Dans la page **Mapper** , spécifiez une connexion à la source de données.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-119">On the **Map** page, specify a connection to the data source.</span></span> <span data-ttu-id="b2b3c-120">Pour plus d'informations, consultez [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="b2b3c-120">For more information, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md).</span></span>  
  
5.  <span data-ttu-id="b2b3c-121">Dans la table **Mappages** , sélectionnez une colonne source dans la liste déroulante de la colonne **Colonne source** d'une ligne vide.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-121">In the **Mappings** table, select a source column from the drop-down list for the **Source Column** column of an empty row.</span></span> <span data-ttu-id="b2b3c-122">Si aucun domaine correspondant n'existe, cliquez sur l'icône **Créer un domaine** .</span><span class="sxs-lookup"><span data-stu-id="b2b3c-122">If no corresponding domain exists, click the **Create a Domain** icon.</span></span>  
  
##  <a name="create-a-domain-in-the-domain-management-activity"></a><a name="DomainManagement"></a><span data-ttu-id="b2b3c-123">Créer un domaine dans l’activité de gestion des domaines</span><span class="sxs-lookup"><span data-stu-id="b2b3c-123">Create a Domain in the Domain Management Activity</span></span>  
  
1.  <span data-ttu-id="b2b3c-124">Dans l'écran d'accueil de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , cliquez sur **Ouvrir la base de connaissances** , puis sélectionnez une base de connaissances ou cliquez sur **Nouvelle Base de connaissances** et entrez les propriétés de la base de connaissances.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-124">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open knowledge base** and then select a knowledge base, or click **New knowledge base** and enter properties for the new knowledge base.</span></span>  
  
2.  <span data-ttu-id="b2b3c-125">Sélectionnez **Gestion de l'arborescence du domaine** comme activité, puis cliquez sur **Créer** pour créer la base de connaissances ou sur **Ouvrir** pour ouvrir une base de connaissances existante.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-125">Select **Domain Management** as the activity, and then click **Create** to create the new knowledge base or **Open** to open an existing knowledge base.</span></span>  
  
3.  <span data-ttu-id="b2b3c-126">Dans la page **Gestion de l'arborescence du domaine** , cliquez sur l'icône **Créer un domaine** au-dessus de la liste des domaines.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-126">On the **Domain Management** page, click the **Create a Domain** icon above the Domain list.</span></span>  
  
##  <a name="set-domain-properties"></a><a name="Properties"></a><span data-ttu-id="b2b3c-127">Définir les propriétés du domaine</span><span class="sxs-lookup"><span data-stu-id="b2b3c-127">Set Domain Properties</span></span>  
  
1.  <span data-ttu-id="b2b3c-128">Dans la boîte de dialogue **Créer un domaine** , entrez un nom qui est unique dans la base de connaissances et une description limitée à 256 caractères.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-128">In the **Create Domain** dialog box, enter a name that is unique to the knowledge base and a description up to 256 characters.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b2b3c-129">Pour plus d'informations sur les propriétés des domaines, consultez [Set Domain Properties](../../2014/data-quality-services/set-domain-properties.md).</span><span class="sxs-lookup"><span data-stu-id="b2b3c-129">For more information about domain properties, see [Set Domain Properties](../../2014/data-quality-services/set-domain-properties.md).</span></span>  
  
2.  <span data-ttu-id="b2b3c-130">Dans la liste **Type de données** , sélectionnez un type de données pour les valeurs dans le domaine.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-130">From the **Data Type** list, select a data type for the values in the domain.</span></span> <span data-ttu-id="b2b3c-131">Le type de données peut être **String** (valeur par défaut), **Date**, **Integer**ou **Decimal**.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-131">The data type can be **String** (the default), **Date**, **Integer**, or **Decimal**.</span></span>  
  
3.  <span data-ttu-id="b2b3c-132">Sélectionnez **Utiliser des valeurs de début** pour spécifier que la valeur de début d'un groupe de synonymes sera sortie au lieu d'une valeur qui lui est synonyme.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-132">Select **Use Leading Values** to specify that the leading value in a group of synonyms will be output instead of a value that is a synonym to it.</span></span> <span data-ttu-id="b2b3c-133">Désélectionnez **Utiliser des valeurs de début** pour spécifier que chaque valeur de synonyme est générée sous sa forme correcte ou corrigée, et n'est pas remplacée par la valeur de début de son groupe.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-133">Deselect **Use Leading Values** to specify that each synonym value is output in its correct or corrected form, and is not replaced by the leading value for its group.</span></span>  
  
4.  <span data-ttu-id="b2b3c-134">Si le type de données est **String**, sélectionnez **Normaliser la chaîne** pour supprimer les caractères spéciaux dans les valeurs de domaine, ce qui peut améliorer la probabilité des correspondances.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-134">If the data type is **String**, select **Normalize String** to remove special characters in the domain values, which may improve the likelihood of matches.</span></span>  
  
5.  <span data-ttu-id="b2b3c-135">Dans la liste déroulante de **Mettre en forme la sortie vers** , sélectionnez la mise en forme qui sera appliqué lors de la sortie des valeurs de données du domaine.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-135">From the **Format Output to** drop-down list, select the formatting that will be applied when the data values in the domain are output.</span></span> <span data-ttu-id="b2b3c-136">La mise en forme est spécifique au type de données sélectionné à l'étape 2, comme indiqué dans la liste suivante :</span><span class="sxs-lookup"><span data-stu-id="b2b3c-136">The formatting is specific to the data type selected in step 2, as shown in the following list:</span></span>  
  
    -   <span data-ttu-id="b2b3c-137">Pour une valeur de chaîne, vous pouvez spécifier que la chaîne soit générée en majuscules, en minuscules, ou avec la première lettre en majuscule.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-137">For a string value, you can specify that the string be output as upper case, lower case, or capitalized.</span></span>  
  
    -   <span data-ttu-id="b2b3c-138">Pour une valeur de date, vous pouvez spécifier le format du jour, du mois et de l'année.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-138">For a date value, you can specify the format of the day, month, and year.</span></span>  
  
    -   <span data-ttu-id="b2b3c-139">Pour une valeur entière, vous pouvez spécifier le type de masque de format à appliquer.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-139">For an integer value, you can specify the type of format mask to be applied.</span></span>  
  
    -   <span data-ttu-id="b2b3c-140">Pour une valeur décimale, vous pouvez spécifier la précision et le type de masque de format à appliquer.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-140">For a decimal value, you can specify the accuracy and the type of format mask to be applied.</span></span>  
  
     <span data-ttu-id="b2b3c-141">Si vous sélectionnez **Aucun** dans la liste déroulante du **Mettre en forme la sortie vers** aucun des formats dans la liste ne sera appliqué.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-141">Selecting **None** in the **Format Output to** drop-down list means none of the formats in the list will be applied.</span></span>  
  
6.  <span data-ttu-id="b2b3c-142">Si le type de données est **String**, dans la liste déroulante **Langue** , sélectionnez la version linguistique du vérificateur d'orthographe que vous souhaitez appliquer si vous activez ce dernier.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-142">If the data type is **String**, in the **Language** drop-down list, select which language version of the speller you want to apply if you enable the speller.</span></span>  
  
7.  <span data-ttu-id="b2b3c-143">Si le type de données est **String**, sélectionnez **Activer le vérificateur d'orthographe** pour exécuter le vérificateur orthographique sur toutes les valeurs de chaîne en remplissant le domaine.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-143">If the data type is **String**, select **Enable Speller** to run the Speller on all string values when populating the domain.</span></span>  
  
8.  <span data-ttu-id="b2b3c-144">Si le type de données est **String**, sélectionnez **Désactiver les algorithmes d'erreur de syntaxe** pour remplir le domaine sans vérifier les valeurs de chaîne pour les erreurs de syntaxe.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-144">If the data type is **String**, select **Disable Syntax Error Algorithms** to populate the domain without checking string values for syntax errors.</span></span>  
  
9. <span data-ttu-id="b2b3c-145">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-145">Click **OK**.</span></span>  
  
10. <span data-ttu-id="b2b3c-146">Cliquez sur **Terminer** pour terminer l'activité de gestion de l'arborescence du domaine, comme décrit dans [End the Domain Management Activity](../../2014/data-quality-services/end-the-domain-management-activity.md).</span><span class="sxs-lookup"><span data-stu-id="b2b3c-146">Click **Finish** to complete the domain management activity, as described in [End the Domain Management Activity](../../2014/data-quality-services/end-the-domain-management-activity.md).</span></span>  
  
##  <a name="follow-up-after-creating-a-domain"></a><a name="FollowUp"></a> <span data-ttu-id="b2b3c-147">Suivi : Après la création d'un domaine</span><span class="sxs-lookup"><span data-stu-id="b2b3c-147">Follow Up: After Creating a Domain</span></span>  
 <span data-ttu-id="b2b3c-148">Après avoir créé un domaine, vous pouvez effectuer d'autres tâches de gestion des domaines sur le domaine, effectuer une découverte des connaissances pour ajouter des connaissances au domaine ou ajouter une stratégie de correspondance au domaine.</span><span class="sxs-lookup"><span data-stu-id="b2b3c-148">After you create a domain, you can perform other domain management tasks on the domain, you can perform knowledge discovery to add knowledge to the domain, or you can add a matching policy to the domain.</span></span> <span data-ttu-id="b2b3c-149">Pour plus d’informations, consultez [Effectuer une découverte des connaissances](../../2014/data-quality-services/perform-knowledge-discovery.md), [Gestion d’un domaine](../../2014/data-quality-services/managing-a-domain.md) ou [Créer une stratégie de correspondance](../../2014/data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="b2b3c-149">For more information, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md), [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md), or [Create a Matching Policy](../../2014/data-quality-services/create-a-matching-policy.md).</span></span>  
  
  
