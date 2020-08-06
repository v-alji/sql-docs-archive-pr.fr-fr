---
title: Utiliser les relations de valeur dans un domaine composite | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.dm.cdvaluerelations.f1
ms.assetid: 5ee468f0-8538-4620-90e8-63f466c9000e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 135934ec99fed612609e5e1b962f08bb93b98ede
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709947"
---
# <a name="use-value-relations-in-a-composite-domain"></a><span data-ttu-id="367cb-102">Utiliser les relations de valeur dans un domaine composite</span><span class="sxs-lookup"><span data-stu-id="367cb-102">Use Value Relations in a Composite Domain</span></span>
  <span data-ttu-id="367cb-103">Cette rubrique décrit comment afficher les combinaisons de valeurs trouvées pour le domaine composite pendant le processus de découverte des connaissances dans [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="367cb-103">This topic describes how to view value combinations found for the composite domain during the knowledge discovery process in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="367cb-104">Cette page affiche le nombre d'occurrences des combinaisons de valeur.</span><span class="sxs-lookup"><span data-stu-id="367cb-104">This page shows the number of occurrences of the value combinations.</span></span> <span data-ttu-id="367cb-105">La gestion de valeur n'est pas prise en charge pour les domaines composites, vous ne pouvez donc pas exécuter d'opérations sur ces valeurs.</span><span class="sxs-lookup"><span data-stu-id="367cb-105">Value management is not supported for composite domains, so you cannot perform any operations on these values.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="367cb-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="367cb-106">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="367cb-107">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="367cb-107">Prerequisites</span></span>  
 <span data-ttu-id="367cb-108">Pour afficher les relations de valeur, vous devez avoir créé et ouvert un domaine composite.</span><span class="sxs-lookup"><span data-stu-id="367cb-108">To view value relations, you must have created and opened a composite domain.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="367cb-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="367cb-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="367cb-110">Autorisations</span><span class="sxs-lookup"><span data-stu-id="367cb-110">Permissions</span></span>  
 <span data-ttu-id="367cb-111">Vous devez disposer du rôle dqs_kb_editor ou dqs_administrator sur la base de données DQS_MAIN pour afficher les relations de valeur dans un domaine composite.</span><span class="sxs-lookup"><span data-stu-id="367cb-111">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to view value relations in a composite domain.</span></span>  
  
##  <a name="view-value-relations"></a><a name="Use"></a><span data-ttu-id="367cb-112">Afficher les relations de valeur</span><span class="sxs-lookup"><span data-stu-id="367cb-112">View Value Relations</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="367cb-113">[Exécutez l’Application Data Quality client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="367cb-113">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="367cb-114">Dans l'écran d'accueil de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , ouvrez ou créez une base de connaissances.</span><span class="sxs-lookup"><span data-stu-id="367cb-114">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, open or create a knowledge base.</span></span> <span data-ttu-id="367cb-115">Sélectionnez **Gestion de l'arborescence du domaine** comme activité, puis cliquez sur **Ouvrir** ou **Créer**.</span><span class="sxs-lookup"><span data-stu-id="367cb-115">Select **Domain Management** as the activity, and then click **Open** or **Create**.</span></span> <span data-ttu-id="367cb-116">Pour plus d’informations, consultez [Créer une base de connaissances](../../2014/data-quality-services/create-a-knowledge-base.md) ou [Ouvrir une base de connaissances](../../2014/data-quality-services/open-a-knowledge-base.md).</span><span class="sxs-lookup"><span data-stu-id="367cb-116">For more information, see [Create a Knowledge Base](../../2014/data-quality-services/create-a-knowledge-base.md) or [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span></span>  
  
3.  <span data-ttu-id="367cb-117">Dans **Liste des domaines** de la page **Gestion de l'arborescence du domaine** , sélectionnez le domaine composite pour lequel vous souhaitez créer une règle de domaine, ou créez un nouveau domaine composite.</span><span class="sxs-lookup"><span data-stu-id="367cb-117">From the **Domain list** on the **Domain Management** page, select the composite domain that you want to create a domain rule for, or create a new composite domain.</span></span> <span data-ttu-id="367cb-118">Si vous devez créer un domaine, consultez [Create a Composite Domain](../../2014/data-quality-services/create-a-composite-domain.md).</span><span class="sxs-lookup"><span data-stu-id="367cb-118">If you have to create a new domain, see [Create a Composite Domain](../../2014/data-quality-services/create-a-composite-domain.md).</span></span>  
  
4.  <span data-ttu-id="367cb-119">Cliquez sur l'onglet **Relations de valeurs** .</span><span class="sxs-lookup"><span data-stu-id="367cb-119">Click the **Value Relations** tab.</span></span>  
  
5.  <span data-ttu-id="367cb-120">Affichez les fréquences affichées pour chaque combinaison de valeurs.</span><span class="sxs-lookup"><span data-stu-id="367cb-120">View the frequencies displayed for each value combination.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="367cb-121">La table **Valeur** affiche chaque combinaison de valeurs qui existe dans le domaine composite.</span><span class="sxs-lookup"><span data-stu-id="367cb-121">The **Value** table shows each combination of values that exists in the composite domain.</span></span> <span data-ttu-id="367cb-122">Chaque valeur est affichée dans le domaine simple auquel elle s'applique.</span><span class="sxs-lookup"><span data-stu-id="367cb-122">Each value is shown in the single domain that it applies to.</span></span> <span data-ttu-id="367cb-123">Le tri par défaut de la table de relations de valeur se fait sur la fréquence, mais vous pouvez cliquer sur une autre colonne pour trier sur cette colonne.</span><span class="sxs-lookup"><span data-stu-id="367cb-123">The default sorting of the value relations table is by frequency, but you can click on another column to sort by that column.</span></span> <span data-ttu-id="367cb-124">Seules les valeurs ayant une fréquence supérieure ou égale à 20 sont affichées.</span><span class="sxs-lookup"><span data-stu-id="367cb-124">Only those values with a frequency greater than or equal to 20 are displayed.</span></span>  
  
6.  <span data-ttu-id="367cb-125">Vous ne pouvez pas modifier l'une des valeurs de la table.</span><span class="sxs-lookup"><span data-stu-id="367cb-125">You cannot change any of the values in the table.</span></span> <span data-ttu-id="367cb-126">Si vous avez exécuté d'autres opérations, cliquez sur **Terminer** pour terminer l'activité de gestion de domaine.</span><span class="sxs-lookup"><span data-stu-id="367cb-126">If you have performed other operations, click **Finish** to complete the domain management activity.</span></span> <span data-ttu-id="367cb-127">Sinon, cliquez sur **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="367cb-127">Otherwise, click **Cancel**.</span></span>  
  
##  <a name="follow-up-after-viewing-value-relations"></a><a name="FollowUp"></a><span data-ttu-id="367cb-128">Suivi : après l’affichage des relations de valeur</span><span class="sxs-lookup"><span data-stu-id="367cb-128">Follow Up: After Viewing Value Relations</span></span>  
 <span data-ttu-id="367cb-129">Après avoir affiché les relations de valeur, vous pouvez effectuer d'autres tâches de gestion des domaines sur le domaine, effectuer une découverte des connaissances pour ajouter des connaissances au domaine ou ajouter une stratégie de correspondance au domaine.</span><span class="sxs-lookup"><span data-stu-id="367cb-129">After you view value relations, you can perform other domain management tasks on the domain, you can perform knowledge discovery to add knowledge to the domain, or you can add a matching policy to the domain.</span></span> <span data-ttu-id="367cb-130">Pour plus d’informations, consultez [Effectuer une découverte des connaissances](../../2014/data-quality-services/perform-knowledge-discovery.md), [Gestion d’un domaine](../../2014/data-quality-services/managing-a-domain.md) ou [Créer une stratégie de correspondance](../../2014/data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="367cb-130">For more information, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md), [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md), or [Create a Matching Policy](../../2014/data-quality-services/create-a-matching-policy.md).</span></span>  
  
  
