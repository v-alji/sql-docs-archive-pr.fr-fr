---
title: Options (éditeur de texte-Transact-SQL-IntelliSense) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.SQL.Advanced
- VS.ToolsOptionsPages.Text_Editor.SQL_Server_Tools.Advanced
dev_langs:
- TSQL
ms.assetid: 1855d916-5bf9-4d94-b0fb-9f9bb05ff950
author: rothja
ms.author: jroth
ms.openlocfilehash: 2d8f9c865516dc5e4c0ddadbdc908a9b4c8ec366
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611947"
---
# <a name="options-text-editor-transact-sql-intellisense"></a><span data-ttu-id="d33b1-102">Options (Text Editor-Transact-SQL-IntelliSense)</span><span class="sxs-lookup"><span data-stu-id="d33b1-102">Options (Text Editor-Transact-SQL-IntelliSense)</span></span>
  <span data-ttu-id="d33b1-103">La boîte de dialogue **Options** vous permet de modifier les paramètres IntelliSense pour l'éditeur de requête du [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d33b1-103">The **Options** dialog box lets you change the IntelliSense settings for the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor.</span></span> <span data-ttu-id="d33b1-104">Pour accéder à ces paramètres, dans le menu **Outils** , cliquez sur **Options**, développez le dossier **Éditeur de texte** , puis le dossier **Transact-SQL** , et cliquez sur **Avancés**.</span><span class="sxs-lookup"><span data-stu-id="d33b1-104">These settings are available when, on the **Tools** menu, you click **Options**, expand the **Text Editor** folder, expand the **Transact-SQL** folder, and then click **Advanced**.</span></span>  
  
## <a name="transact-sql-intellisense-settings"></a><span data-ttu-id="d33b1-105">Paramètres IntelliSense Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d33b1-105">Transact-SQL IntelliSense Settings</span></span>  
 <span data-ttu-id="d33b1-106">Spécifie les options IntelliSense pour l'éditeur de [!INCLUDE[ssDE](../includes/ssde-md.md)] requête du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="d33b1-106">Specifies the IntelliSense options for the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor.</span></span>  
  
### <a name="enable-intellisense"></a><span data-ttu-id="d33b1-107">Activer IntelliSense</span><span class="sxs-lookup"><span data-stu-id="d33b1-107">Enable IntelliSense</span></span>  
 <span data-ttu-id="d33b1-108">Active les fonctionnalités IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="d33b1-108">Enables the IntelliSense features.</span></span> <span data-ttu-id="d33b1-109">Lorsque cette case à cocher n'est pas activée, les options IntelliSense spécifiques ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="d33b1-109">When this box is not selected, the specific IntelliSense options are unavailable.</span></span> <span data-ttu-id="d33b1-110">Par défaut, cette case à cocher est activée.</span><span class="sxs-lookup"><span data-stu-id="d33b1-110">By default, this check box is selected.</span></span>  
  
 <span data-ttu-id="d33b1-111">**Souligner les erreurs**</span><span class="sxs-lookup"><span data-stu-id="d33b1-111">**Underline errors**</span></span>  
 <span data-ttu-id="d33b1-112">Identifie les erreurs syntaxiques et sémantiques dans les instructions [!INCLUDE[tsql](../includes/tsql-md.md)] dans la fenêtre de requête.</span><span class="sxs-lookup"><span data-stu-id="d33b1-112">Identifies syntax and semantic errors in [!INCLUDE[tsql](../includes/tsql-md.md)] statements in the query window.</span></span> <span data-ttu-id="d33b1-113">Les erreurs et les avertissements apparaissent en rouge.</span><span class="sxs-lookup"><span data-stu-id="d33b1-113">All errors and warnings appear in red.</span></span> <span data-ttu-id="d33b1-114">Les erreurs et les avertissements sont uniquement pris en charge pour les instructions [!INCLUDE[tsql](../includes/tsql-md.md)] pour lesquelles IntelliSense a été implémenté.</span><span class="sxs-lookup"><span data-stu-id="d33b1-114">Errors and warnings are supported only for the [!INCLUDE[tsql](../includes/tsql-md.md)] statements for which IntelliSense has been implemented.</span></span> <span data-ttu-id="d33b1-115">Par défaut, cette case à cocher est activée.</span><span class="sxs-lookup"><span data-stu-id="d33b1-115">By default, this check box is selected.</span></span>  
  
 <span data-ttu-id="d33b1-116">**Instructions de plan**</span><span class="sxs-lookup"><span data-stu-id="d33b1-116">**Outline statements**</span></span>  
 <span data-ttu-id="d33b1-117">Active le mode Plan lorsqu'un fichier est ouvert.</span><span class="sxs-lookup"><span data-stu-id="d33b1-117">Enables the outlining feature when a file is opened.</span></span> <span data-ttu-id="d33b1-118">Cela entraîne la création de blocs réductibles de code [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d33b1-118">This creates collapsible blocks of [!INCLUDE[tsql](../includes/tsql-md.md)] code.</span></span> <span data-ttu-id="d33b1-119">Par défaut, cette case à cocher est activée.</span><span class="sxs-lookup"><span data-stu-id="d33b1-119">By default, this check box is selected.</span></span>  
  
 <span data-ttu-id="d33b1-120">**Taille de script maximale**</span><span class="sxs-lookup"><span data-stu-id="d33b1-120">**Maximum script size**</span></span>  
 <span data-ttu-id="d33b1-121">Spécifie la taille à laquelle les fonctionnalités IntelliSense sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="d33b1-121">Specifies the size at which IntelliSense functionality is disabled.</span></span> <span data-ttu-id="d33b1-122">Si un script dépasse la taille spécifiée, un message d'avertissement est émis.</span><span class="sxs-lookup"><span data-stu-id="d33b1-122">If a script exceeds the specified size, a warning message is issued.</span></span> <span data-ttu-id="d33b1-123">Toutes les fonctionnalités IntelliSense, à l'exception du codage en couleurs, sont désactivées pour cette fenêtre d'éditeur.</span><span class="sxs-lookup"><span data-stu-id="d33b1-123">All IntelliSense features, except color coding, are disabled for that editor window.</span></span> <span data-ttu-id="d33b1-124">IntelliSense est réactivé lorsque suffisamment de texte est supprimé pour faire passer la taille du script sous la limite.</span><span class="sxs-lookup"><span data-stu-id="d33b1-124">IntelliSense is reenabled when enough text is deleted to reduce the script size to under the limit.</span></span> <span data-ttu-id="d33b1-125">L'activation d'IntelliSense pour les scripts volumineux peut réduire les performances sur les ordinateurs lents.</span><span class="sxs-lookup"><span data-stu-id="d33b1-125">Enabling IntelliSense for large script sizes can decrease performance on slow computers.</span></span> <span data-ttu-id="d33b1-126">Les tailles autorisées sont 100 Ko, 500 Ko, 1 Mo, 2 Mo et Illimité.</span><span class="sxs-lookup"><span data-stu-id="d33b1-126">The allowed sizes are 100 KB, 500 KB, 1 MB, 2 MB, and Unlimited.</span></span> <span data-ttu-id="d33b1-127">La valeur par défaut est 1 Mo.</span><span class="sxs-lookup"><span data-stu-id="d33b1-127">The default is 1 MB.</span></span>  
  
 <span data-ttu-id="d33b1-128">**Casse des noms de fonctions intégrées**</span><span class="sxs-lookup"><span data-stu-id="d33b1-128">**Casing for built-in function names**</span></span>  
 <span data-ttu-id="d33b1-129">Indique si les noms de fonctions [!INCLUDE[tsql](../includes/tsql-md.md)] intégrées incluses dans les listes de saisie semi-automatique utilisent des lettres majuscules, telles que DATEADD, ou des lettres minuscules, telles que dateadd.</span><span class="sxs-lookup"><span data-stu-id="d33b1-129">Specifies whether the names of built-in [!INCLUDE[tsql](../includes/tsql-md.md)] functions that are included in completion lists use uppercase letters, such as DATEADD; or lowercase letters, such as dateadd.</span></span> <span data-ttu-id="d33b1-130">Sélectionnez l'option qui correspond le mieux aux conventions de codage [!INCLUDE[tsql](../includes/tsql-md.md)] que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="d33b1-130">Select the option that best matches the [!INCLUDE[tsql](../includes/tsql-md.md)] coding conventions that you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d33b1-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d33b1-131">See Also</span></span>  
 [<span data-ttu-id="d33b1-132">Résolution des problèmes d' &#40;IntelliSense SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="d33b1-132">Troubleshooting IntelliSense &#40;SQL Server Management Studio&#41;</span></span>](../relational-databases/scripting/troubleshooting-intellisense.md)  
  
  
