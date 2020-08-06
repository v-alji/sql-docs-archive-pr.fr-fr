---
title: Options (exécution de la requête-SQL Server-page général) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.QueryExecution.SqlServer.SqlExecutionGeneral
ms.assetid: 3f8d59bc-3f97-4e5d-8b86-5ac670d20780
author: rothja
ms.author: jroth
ms.openlocfilehash: eaa95293636d02674fb720dcd1b8146279f78e72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613597"
---
# <a name="options-query-execution-sql-server-general-page"></a><span data-ttu-id="28c88-102">Options (exécution de la requête-SQL Server-page général)</span><span class="sxs-lookup"><span data-stu-id="28c88-102">Options (Query Execution-SQL Server-General Page)</span></span>
  <span data-ttu-id="28c88-103">Cette page vous permet de spécifier les options d'exécution des requêtes [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="28c88-103">Use this page to specify the options for running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="28c88-104">Les modifications de ces options sont appliquées uniquement aux nouvelles requêtes [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28c88-104">Changes to these options are only applied to new [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="28c88-105">Pour modifier les options relatives à une requête en cours, cliquez sur **Options de requête** dans le menu **Requête** ou cliquez avec le bouton droit dans une fenêtre Requête de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] et sélectionnez **Options de requête**.</span><span class="sxs-lookup"><span data-stu-id="28c88-105">To change the options for a current query, click **Query Options** on the **Query** menu, or in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Query window right-click and select **Query Options**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="28c88-106">Options</span><span class="sxs-lookup"><span data-stu-id="28c88-106">Options</span></span>  
 <span data-ttu-id="28c88-107">**SET ROWCOUNT**</span><span class="sxs-lookup"><span data-stu-id="28c88-107">**SET ROWCOUNT**</span></span>  
 <span data-ttu-id="28c88-108">La valeur par défaut 0 indique que [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] attend les résultats, tant que tous les résultats ne sont pas reçus.</span><span class="sxs-lookup"><span data-stu-id="28c88-108">The default value of 0 indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will wait for results until all results are received.</span></span> <span data-ttu-id="28c88-109">Spécifiez une valeur supérieure à 0 pour que [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] arrête la requête après avoir obtenu le nombre de lignes spécifié.</span><span class="sxs-lookup"><span data-stu-id="28c88-109">Provide a value greater than 0 if you want [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to halt the query after obtaining the specified number of rows.</span></span> <span data-ttu-id="28c88-110">Pour désactiver cette option, de manière à renvoyer toutes les lignes, spécifiez SET ROWCOUNT 0.</span><span class="sxs-lookup"><span data-stu-id="28c88-110">To turn this option off (so that all rows are returned), specify SET ROWCOUNT 0.</span></span>  
  
 <span data-ttu-id="28c88-111">**SET TEXTSIZE**</span><span class="sxs-lookup"><span data-stu-id="28c88-111">**SET TEXTSIZE**</span></span>  
 <span data-ttu-id="28c88-112">La valeur par défaut de 2 147 483 647 octets indique que [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] fournira des champs de données complets jusqu'à la limite des champs de données `text` et `ntext`.</span><span class="sxs-lookup"><span data-stu-id="28c88-112">The default value of 2,147,483,647 bytes indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will provide complete data fields up to the limit of `text` and `ntext` data fields.</span></span> <span data-ttu-id="28c88-113">Spécifiez un nombre inférieur pour limiter les résultats en cas de valeurs importantes.</span><span class="sxs-lookup"><span data-stu-id="28c88-113">Provide a smaller number to limit results in the case of large values.</span></span> <span data-ttu-id="28c88-114">Les colonnes d'une taille supérieure au nombre spécifié sont tronquées.</span><span class="sxs-lookup"><span data-stu-id="28c88-114">Columns greater than the number provided will be truncated.</span></span>  
  
 <span data-ttu-id="28c88-115">**Délai d’exécution**</span><span class="sxs-lookup"><span data-stu-id="28c88-115">**Execution time-out**</span></span>  
 <span data-ttu-id="28c88-116">Définit la valeur par défaut dans la boîte de dialogue **Nouvelle connexion** .</span><span class="sxs-lookup"><span data-stu-id="28c88-116">Sets the default value in the **New Connection** dialog box.</span></span> <span data-ttu-id="28c88-117">Utilisez cette zone de sélection numérique pour indiquer à [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] le nombre de secondes à patienter avant d’annuler la requête.</span><span class="sxs-lookup"><span data-stu-id="28c88-117">Use this spin box to tell [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] the number of seconds to wait before canceling the query.</span></span> <span data-ttu-id="28c88-118">La valeur 0 indique une attente infinie ou aucun délai d’attente. Cette valeur est 0 sur une nouvelle installation.</span><span class="sxs-lookup"><span data-stu-id="28c88-118">A value of 0 indicates an infinite wait, or no time-out. This value is 0 on a new installation.</span></span>  
  
 <span data-ttu-id="28c88-119">**Délimiteur de traitement**</span><span class="sxs-lookup"><span data-stu-id="28c88-119">**Batch separator**</span></span>  
 <span data-ttu-id="28c88-120">Tapez un mot à utiliser pour séparer les instructions [!INCLUDE[tsql](../includes/tsql-md.md)] en traitements.</span><span class="sxs-lookup"><span data-stu-id="28c88-120">Type a word that you use to separate [!INCLUDE[tsql](../includes/tsql-md.md)] statements into batches.</span></span> <span data-ttu-id="28c88-121">La valeur par défaut est GO.</span><span class="sxs-lookup"><span data-stu-id="28c88-121">The default is GO.</span></span>  
  
 <span data-ttu-id="28c88-122">**Par défaut, ouvrir les nouvelles requêtes en mode SQLCMD**</span><span class="sxs-lookup"><span data-stu-id="28c88-122">**By default, open new queries in SQLCMD Mode**</span></span>  
 <span data-ttu-id="28c88-123">Activez cette case à cocher pour ouvrir les nouvelles requêtes en mode SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="28c88-123">Select this check box to open new queries in SQLCMD mode.</span></span> <span data-ttu-id="28c88-124">Pour plus d’informations sur le mode SQLCMD, consultez [Modifier des scripts SQLCMD à l’aide de l’Éditeur de requête](../relational-databases/scripting/edit-sqlcmd-scripts-with-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="28c88-124">For more information about SQLCMD mode, see [Edit SQLCMD Scripts with Query Editor](../relational-databases/scripting/edit-sqlcmd-scripts-with-query-editor.md).</span></span>  
  
 <span data-ttu-id="28c88-125">Lorsque vous sélectionnez cette option, prenez en compte les limitations suivantes :</span><span class="sxs-lookup"><span data-stu-id="28c88-125">When you select this option, be aware of the following limitations:</span></span>  
  
-   <span data-ttu-id="28c88-126">IntelliSense dans l’Éditeur de requête du [!INCLUDE[ssDE](../includes/ssde-md.md)] est désactivé.</span><span class="sxs-lookup"><span data-stu-id="28c88-126">IntelliSense in the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor is turned off.</span></span>  
  
-   <span data-ttu-id="28c88-127">L'Éditeur de requête ne s'exécutant pas à partir de la ligne de commande, vous ne pouvez pas passer de paramètres de ligne de commande tels que des variables.</span><span class="sxs-lookup"><span data-stu-id="28c88-127">Because Query Editor does not run from the command line, you cannot pass in command-line parameters such as variables.</span></span>  
  
-   <span data-ttu-id="28c88-128">L'Éditeur de requête étant incapable de répondre aux invites de système d'exploitation, vous devez prendre soin de ne pas exécuter d'instructions interactives.</span><span class="sxs-lookup"><span data-stu-id="28c88-128">Because Query Editor cannot respond to operating-system prompts, you must be careful not to run interactive statements.</span></span>  
  
 <span data-ttu-id="28c88-129">**Rétablir les valeurs par défaut**</span><span class="sxs-lookup"><span data-stu-id="28c88-129">**Reset to Default**</span></span>  
 <span data-ttu-id="28c88-130">Cliquez ici pour rétablir les valeurs par défaut d'origine de toutes les valeurs de cette page.</span><span class="sxs-lookup"><span data-stu-id="28c88-130">Click to reset all values on this page to the original default values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28c88-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="28c88-131">See Also</span></span>  
 [<span data-ttu-id="28c88-132">Utilitaire sqlcmd</span><span class="sxs-lookup"><span data-stu-id="28c88-132">sqlcmd Utility</span></span>](../tools/sqlcmd-utility.md)  
  
  
