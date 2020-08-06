---
title: Options (page résultats de la requête et services de dépendance) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.QueryResults.DependencyServicesGeneral
ms.assetid: dd7f6c31-7d7f-4972-854a-1419a2826dca
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 356714ee933fb40eda7038f4088309b6187f3ed8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613131"
---
# <a name="options-query-results-and-dependency-services-page"></a><span data-ttu-id="28723-102">Options (Résultats de la requête et Page Services de dépendance)</span><span class="sxs-lookup"><span data-stu-id="28723-102">Options (Query Results and Dependency Services Page)</span></span>
  <span data-ttu-id="28723-103">Utilisez cette page pour spécifier le serveur auquel se connecter pour les services de dépendance.</span><span class="sxs-lookup"><span data-stu-id="28723-103">Use this page to specify the server to connect for Dependency Services.</span></span> <span data-ttu-id="28723-104">Les services de dépendance vous permettent d'extraire des informations à propos des dépendances entre des objets [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] et [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] stockés sur des serveurs différents.</span><span class="sxs-lookup"><span data-stu-id="28723-104">Dependency Services enables you to extract information about dependencies between [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects stored on different servers.</span></span> <span data-ttu-id="28723-105">Vous pouvez afficher les dépendances d’objets à l’aide de la boîte de dialogue **dépendances d’objets** dans [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="28723-105">You view object dependencies by using the **Object Dependencies** dialog box in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="28723-106">**Que voulez-vous faire ?**</span><span class="sxs-lookup"><span data-stu-id="28723-106">**What do you want to do?**</span></span>  
  
1.  [<span data-ttu-id="28723-107">Ouvrir la boîte de dialogue d'options (Résultats de la requête/page Services de dépendance)</span><span class="sxs-lookup"><span data-stu-id="28723-107">Open the Options (Query Results/Dependency Services Page) Dialog Box</span></span>](#open_dialog)  
  
2.  [<span data-ttu-id="28723-108">Configurer les options</span><span class="sxs-lookup"><span data-stu-id="28723-108">Configure the Options</span></span>](#options)  
  
##  <a name="open-the-options-query-resultsdependency-services-page-dialog-box"></a><a name="open_dialog"></a><span data-ttu-id="28723-109">Ouvrir la boîte de dialogue Options (résultats de la requête/page services de dépendance)</span><span class="sxs-lookup"><span data-stu-id="28723-109">Open the Options (Query Results/Dependency Services Page) Dialog Box</span></span>  
  
1.  <span data-ttu-id="28723-110">Dans [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] , cliquez sur **options** dans le menu **Outils** .</span><span class="sxs-lookup"><span data-stu-id="28723-110">In [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="28723-111">Développez **Résultats de la requête**, puis cliquez sur **Services de dépendance**.</span><span class="sxs-lookup"><span data-stu-id="28723-111">Expand **Query Results**, and then click **Dependency Services**.</span></span>  
  
##  <a name="configure-the-options"></a><a name="options"></a> <span data-ttu-id="28723-112">Configurer les options</span><span class="sxs-lookup"><span data-stu-id="28723-112">Configure the Options</span></span>  
  
### <a name="options"></a><span data-ttu-id="28723-113">Options</span><span class="sxs-lookup"><span data-stu-id="28723-113">Options</span></span>  
 <span data-ttu-id="28723-114">**Serveur de services de dépendance**</span><span class="sxs-lookup"><span data-stu-id="28723-114">**Dependency Services server**</span></span>  
 <span data-ttu-id="28723-115">Spécifiez le serveur sur lequel les services de dépendance sont installés.</span><span class="sxs-lookup"><span data-stu-id="28723-115">Specify the server that Dependency Services is installed on.</span></span>  
  
 <span data-ttu-id="28723-116">**Authentification**</span><span class="sxs-lookup"><span data-stu-id="28723-116">**Authentication**</span></span>  
 <span data-ttu-id="28723-117">Sélectionnez l'authentification Windows pour vous connecter à l'aide d'un compte d'utilisateur Microsoft Windows ou sélectionnez l'authentification SQL Server.</span><span class="sxs-lookup"><span data-stu-id="28723-117">Select Windows Authentication to log on using a Microsoft Windows user account, or select SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="28723-118">Lorsqu'un utilisateur se connecte avec un nom d'accès et un mot de passe spécifiés à partir d'une connexion non autorisée, SQL Server réalise l'authentification en vérifiant si un compte de connexion SQL Server a été défini et si le mot de passe spécifié correspond à celui enregistré précédemment.</span><span class="sxs-lookup"><span data-stu-id="28723-118">When a user connects with a specified login name and password from a non-trusted connection, SQL Server performs the authentication by checking to see if a SQL Server login account has been set up and if the specified password matches the one previously recorded.</span></span> <span data-ttu-id="28723-119">Si SQL Server ne peut pas trouver le compte de connexion, l'authentification échoue et l'utilisateur reçoit un message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="28723-119">If SQL Server cannot find the login account, authentication fails, and the user receives an error message.</span></span>  
  
 <span data-ttu-id="28723-120">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="28723-120">**User name**</span></span>  
 <span data-ttu-id="28723-121">Si vous utilisez l'authentification SQL Server, entrez un nom d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="28723-121">If using SQL Server Authentication, provide a user name.</span></span>  
  
 <span data-ttu-id="28723-122">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="28723-122">**Password**</span></span>  
 <span data-ttu-id="28723-123">Si vous utilisez l'authentification SQL Server, entrez un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="28723-123">If using SQL Server Authentication, provide a password.</span></span>  
  
 <span data-ttu-id="28723-124">**Test**</span><span class="sxs-lookup"><span data-stu-id="28723-124">**Test**</span></span>  
 <span data-ttu-id="28723-125">Cliquez pour vérifier la connexion.</span><span class="sxs-lookup"><span data-stu-id="28723-125">Click to test the connection.</span></span>