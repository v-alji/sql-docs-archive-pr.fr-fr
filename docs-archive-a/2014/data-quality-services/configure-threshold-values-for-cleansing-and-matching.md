---
title: Configurer les valeurs de seuil pour le nettoyage et la correspondance | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.admin.config.general.f1
helpviewer_keywords:
- cleansing,threshold value
- cleansing threshold values
- matching,threshold value
ms.assetid: d2305409-7115-45a4-8f60-1213c0a47368
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0faf64e96468a3a9aac0de12d3ec3acbb1e1ed85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696083"
---
# <a name="configure-threshold-values-for-cleansing-and-matching"></a><span data-ttu-id="fd2f9-102">Configurer les valeurs de seuil pour le nettoyage et la correspondance</span><span class="sxs-lookup"><span data-stu-id="fd2f9-102">Configure Threshold Values for Cleansing and Matching</span></span>
  <span data-ttu-id="fd2f9-103">Cette rubrique explique comment configurer les valeurs de seuil qui seront utilisées pendant les activités de nettoyage et de correspondance assistées par ordinateur dans [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="fd2f9-103">This topic describes how to configure threshold values that will be used during the computer-assisted cleansing and matching activities in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fd2f9-104">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="fd2f9-104">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fd2f9-105">Sécurité</span><span class="sxs-lookup"><span data-stu-id="fd2f9-105">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fd2f9-106">Autorisations</span><span class="sxs-lookup"><span data-stu-id="fd2f9-106">Permissions</span></span>  
 <span data-ttu-id="fd2f9-107">Vous devez disposer du rôle dqs_administrator sur la base de données DQS_MAIN pour configurer ces valeurs de seuil.</span><span class="sxs-lookup"><span data-stu-id="fd2f9-107">You must have the dqs_administrator role on the DQS_MAIN database to configure these threshold values.</span></span>  
  
##  <a name="configuring-the-threshold-values"></a><a name="Configure"></a> <span data-ttu-id="fd2f9-108">Configuration des valeurs de seuil</span><span class="sxs-lookup"><span data-stu-id="fd2f9-108">Configuring the Threshold Values</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="fd2f9-109">[Exécutez l’Application Data Quality client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="fd2f9-109">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="fd2f9-110">Dans l'écran d'accueil de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , cliquez sur **Configuration**.</span><span class="sxs-lookup"><span data-stu-id="fd2f9-110">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="fd2f9-111">Ensuite, cliquez sur l’onglet **paramètres généraux** . Cet onglet vous permet de spécifier des valeurs de seuil pour les activités de nettoyage et de correspondance.</span><span class="sxs-lookup"><span data-stu-id="fd2f9-111">Next, click the **General Settings** tab. This tab enables you to specify threshold values for cleansing as well as matching activities.</span></span>  
  
4.  <span data-ttu-id="fd2f9-112">Pour spécifier des valeurs de seuil pour l'activité de nettoyage, spécifiez les valeurs appropriées dans les zones suivantes sous la zone **Nettoyage interactif** :</span><span class="sxs-lookup"><span data-stu-id="fd2f9-112">To specify threshold values for the cleansing activity, specify appropriate values in the following boxes under the **Interactive Cleansing** area:</span></span>  
  
    -   <span data-ttu-id="fd2f9-113">**Score minimal pour les suggestions**: score ou niveau de confiance minimal qui sera utilisé par DQS pour suggérer des remplacements d'une valeur pendant le processus de nettoyage assisté par ordinateur.</span><span class="sxs-lookup"><span data-stu-id="fd2f9-113">**Min score for suggestions**: The minimum score or the confidence level that will be used by DQS for suggesting replacements for a value during the computer-assisted cleansing process.</span></span> <span data-ttu-id="fd2f9-114">Entrez une valeur en notation décimale de la valeur de pourcentage correspondante.</span><span class="sxs-lookup"><span data-stu-id="fd2f9-114">Enter a value in the decimal notation of the corresponding percentage value.</span></span> <span data-ttu-id="fd2f9-115">Par exemple, tapez 0,75 pou 75 %.</span><span class="sxs-lookup"><span data-stu-id="fd2f9-115">For example, type 0.75 for 75%.</span></span> <span data-ttu-id="fd2f9-116">Cette valeur doit être inférieure ou égale à la valeur spécifiée dans la zone **Score minimal pour les corrections automatiques** .</span><span class="sxs-lookup"><span data-stu-id="fd2f9-116">This value should be less than or equal to the value specified in the **Min score for auto corrections** box.</span></span> <span data-ttu-id="fd2f9-117">La valeur par défaut est 0,7.</span><span class="sxs-lookup"><span data-stu-id="fd2f9-117">The default value is 0.7.</span></span>  
  
    -   <span data-ttu-id="fd2f9-118">**Score minimal pour les corrections automatiques**: score ou niveau de confiance minimal qui sera utilisé par DQS pour corriger automatiquement une valeur pendant le processus de nettoyage assisté par ordinateur.</span><span class="sxs-lookup"><span data-stu-id="fd2f9-118">**Min score for auto corrections**: The minimum score or the confidence level that will be used by DQS for automatically correcting a value during the computer-assisted cleansing process.</span></span> <span data-ttu-id="fd2f9-119">Entrez une valeur en notation décimale de la valeur de pourcentage correspondante.</span><span class="sxs-lookup"><span data-stu-id="fd2f9-119">Enter a value in the decimal notation of the corresponding percentage value.</span></span> <span data-ttu-id="fd2f9-120">Par exemple, entrez 0,9 pour 90 %.</span><span class="sxs-lookup"><span data-stu-id="fd2f9-120">For example, enter 0.9 for 90%.</span></span> <span data-ttu-id="fd2f9-121">La valeur par défaut est 0,8.</span><span class="sxs-lookup"><span data-stu-id="fd2f9-121">The default value is 0.8.</span></span>  
  
5.  <span data-ttu-id="fd2f9-122">Pour spécifier la valeur de seuil pour l'activité de correspondance, spécifiez une valeur dans la zone **Score d'enregistrement minimal** sous la zone **Correspondance** .</span><span class="sxs-lookup"><span data-stu-id="fd2f9-122">To specify threshold value for the matching activity, specify a value in the **Min record score** box under the **Matching** area.</span></span> <span data-ttu-id="fd2f9-123">Cette valeur représente le score minimal pour qu'un enregistrement soit considéré comme une correspondance d'un autre enregistrement.</span><span class="sxs-lookup"><span data-stu-id="fd2f9-123">This value signifies the minimum score for a record to be considered as a match for another record.</span></span> <span data-ttu-id="fd2f9-124">La valeur par défaut est 80 %.</span><span class="sxs-lookup"><span data-stu-id="fd2f9-124">The default value is 80%.</span></span>  
  
6.  <span data-ttu-id="fd2f9-125">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="fd2f9-125">Click **Close**.</span></span>  
  
  
