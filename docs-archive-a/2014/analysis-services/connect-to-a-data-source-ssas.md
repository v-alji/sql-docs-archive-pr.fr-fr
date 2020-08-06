---
title: Se connecter à une source de données (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.conndatasource.f1
ms.assetid: 1e2b17e9-092b-4af1-8a58-c52b8fe10ff1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4fe7f7d5b31118369b8ce2a855b955e44f661dbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602478"
---
# <a name="connect-to-a-data-source-ssas"></a><span data-ttu-id="4b084-102">Connexion à une source de données (SSAS)</span><span class="sxs-lookup"><span data-stu-id="4b084-102">Connect to a Data Source (SSAS)</span></span>
  <span data-ttu-id="4b084-103">Cette page de l' **Assistant Importation de table** vous permet de créer une connexion à diverses sources de données, telles que des bases de données relationnelles, des flux de données et des fichiers.</span><span class="sxs-lookup"><span data-stu-id="4b084-103">This page of the **Table Import Wizard** enables you to create a new data source connection to a variety of data sources, such as relational databases, data feeds, and files.</span></span> <span data-ttu-id="4b084-104">Pour accéder à l'Assistant [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dans le menu **Modèle** , cliquez sur **Importer à partir de la source de données**.</span><span class="sxs-lookup"><span data-stu-id="4b084-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="4b084-105">Pour vous connecter à une source de données, vous devez disposer du fournisseur approprié, installé sur votre machine.</span><span class="sxs-lookup"><span data-stu-id="4b084-105">To connect to a data source, you must have the appropriate provider installed on your machine.</span></span> <span data-ttu-id="4b084-106">Le fournisseur approprié doit également être installé sur le serveur de base de données d'espace de travail.</span><span class="sxs-lookup"><span data-stu-id="4b084-106">You must also have the appropriate provider installed on the workspace database server.</span></span> <span data-ttu-id="4b084-107">Pour les serveurs 32 bits (x86), les fournisseurs 32 bits doivent être installés.</span><span class="sxs-lookup"><span data-stu-id="4b084-107">For 32-bit (x86) servers, 32-bit providers must be installed.</span></span> <span data-ttu-id="4b084-108">Pour les serveurs 64 bits (x64), les fournisseurs 64 bits doivent être installés.</span><span class="sxs-lookup"><span data-stu-id="4b084-108">For 64-bit (x64) servers, 64-bit providers must be installed.</span></span>  
  
 [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] <span data-ttu-id="4b084-109">s'exécute toujours dans un processus 32 bits, indépendamment de l'architecture.</span><span class="sxs-lookup"><span data-stu-id="4b084-109">always runs in a 32-bit process, regardless of architecture.</span></span> <span data-ttu-id="4b084-110">Lorsque vous exécutez [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] sur un ordinateur 64 bits, vous devez veiller aux points suivants lors de l'installation des fournisseurs de données :</span><span class="sxs-lookup"><span data-stu-id="4b084-110">When running [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] on a 64-bit machine, you should be aware of the following when installing data providers:</span></span>  
  
-   <span data-ttu-id="4b084-111">Pour les fournisseurs qui prennent en charge l'installation côte à côte des fournisseurs 32 bits et 64 bits, vous devez installer les deux fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="4b084-111">For providers that support side-by-side installation of 32-bit and 64-bit providers, you should install both providers.</span></span>  
  
-   <span data-ttu-id="4b084-112">Pour le fournisseur ACE, vous devez installer la version 64 bits du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="4b084-112">For the ACE provider, you must install the 64-bit version of the provider.</span></span> <span data-ttu-id="4b084-113">Étant donné qu'Office installe automatiquement le fournisseur ACE, vous ne devez pas exécuter la version 32 bits de Microsoft Office sur un ordinateur 64 bits qui héberge le serveur de base de données d'espace de travail.</span><span class="sxs-lookup"><span data-stu-id="4b084-113">Because Office automatically installs the ACE provider, you should not run a 32-bit version of Microsoft Office on a 64-bit machine hosting the workspace database server.</span></span>  
  
     <span data-ttu-id="4b084-114">Le fournisseur ACE est utilisé pour importer à partir de fichiers texte, Excel et Access.</span><span class="sxs-lookup"><span data-stu-id="4b084-114">The ACE provider is used to import from Text, Excel, and Access files.</span></span> <span data-ttu-id="4b084-115">Si la prise en charge de ces sources de données n'est pas nécessaire, vous pouvez exécuter une version 32 bits de Microsoft Office sur un ordinateur qui exécute un serveur de base de données d'espace de travail 64 bits.</span><span class="sxs-lookup"><span data-stu-id="4b084-115">If support for these data sources is not needed, you can then run a 32-bit version of Microsoft Office on a machine running a 64-bit workspace database server.</span></span>  
  
-   <span data-ttu-id="4b084-116">Pour les autres fournisseurs qui ne prennent pas en charge l'installation côte à côte des fournisseurs 32 bits et 64 bits, vous devez installer le fournisseur 32 bits.</span><span class="sxs-lookup"><span data-stu-id="4b084-116">For other providers that do not support side-by-side installation of 32-bit and 64-bit providers, you must install the 32-bit provider.</span></span> <span data-ttu-id="4b084-117">Si seuls les ordinateurs 64 bits sont disponibles, vous devez utiliser un ordinateur distant avec un fournisseur 64 bits installé comme serveur de base de données d'espace de travail.</span><span class="sxs-lookup"><span data-stu-id="4b084-117">If only 64-bit machines are available, you must use a remote machine with a 64-bit provider installed as the workspace database server.</span></span>  
  
  
