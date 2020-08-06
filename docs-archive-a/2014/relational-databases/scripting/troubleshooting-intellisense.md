---
title: Résolution des problèmes liés à IntelliSense
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- unavailable options [IntelliSense]
- IntelliSense [SQL Server], troubleshooting
- IntelliSense [SQL Server], unavailable options
- troubleshooting [IntelliSense]
ms.assetid: 4b72ffc6-aea2-4e11-ab36-fa2de4d7bcc5
author: rothja
ms.author: jroth
ms.openlocfilehash: 087baf616fc215c480ae78621623cbe1ed512b57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702643"
---
# <a name="troubleshooting-intellisense-sql-server-management-studio"></a><span data-ttu-id="2e401-102">Résolution des problèmes liés à IntelliSense (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="2e401-102">Troubleshooting IntelliSense (SQL Server Management Studio)</span></span>
  <span data-ttu-id="2e401-103">Dans certains cas, les options IntelliSense ne fonctionneront peut-être pas comme vous l'attendez. Ces cas sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="2e401-103">There are certain cases when the IntelliSense options might not work as you expect.</span></span>  
  
## <a name="conditions-that-affect-intellisense"></a><span data-ttu-id="2e401-104">Conditions qui affectent IntelliSense</span><span class="sxs-lookup"><span data-stu-id="2e401-104">Conditions That Affect IntelliSense</span></span>  
 <span data-ttu-id="2e401-105">Les conditions suivantes peuvent affecter le comportement d'IntelliSense :</span><span class="sxs-lookup"><span data-stu-id="2e401-105">The following conditions might affect the behavior of IntelliSense:</span></span>  
  
-   <span data-ttu-id="2e401-106">Il y a une erreur de codage au-dessus du curseur.</span><span class="sxs-lookup"><span data-stu-id="2e401-106">There is a code error above the cursor.</span></span>  
  
     <span data-ttu-id="2e401-107">S'il existe une instruction incomplète ou une autre erreur de codage au-dessus du point d'insertion, IntelliSense ne peut pas analyser les éléments de code et par conséquent ne peut pas fonctionner.</span><span class="sxs-lookup"><span data-stu-id="2e401-107">If there is an incomplete statement or other coding error above the location of the insertion point, IntelliSense may be unable to parse the code elements, and therefore will not work.</span></span> <span data-ttu-id="2e401-108">Pour réactiver IntelliSense, mettez en commentaire le code concerné.</span><span class="sxs-lookup"><span data-stu-id="2e401-108">You can comment out the applicable code to enable IntelliSense again.</span></span>  
  
-   <span data-ttu-id="2e401-109">Le point d'insertion est à l'intérieur d'un commentaire de code.</span><span class="sxs-lookup"><span data-stu-id="2e401-109">The insertion point is inside a code comment.</span></span>  
  
     <span data-ttu-id="2e401-110">Les options IntelliSense ne sont pas disponibles si le point d'insertion se trouve dans un commentaire de votre fichier source.</span><span class="sxs-lookup"><span data-stu-id="2e401-110">IntelliSense options are not available when the insertion point is within a comment in your source file.</span></span>  
  
-   <span data-ttu-id="2e401-111">Le point d'insertion est à l'intérieur d'un littéral de chaîne.</span><span class="sxs-lookup"><span data-stu-id="2e401-111">The insertion point is inside a string literal.</span></span>  
  
     <span data-ttu-id="2e401-112">Les options IntelliSense ne sont pas disponibles si le point d'insertion se trouve à l'intérieur des guillemets entourant un littéral de chaîne, comme dans l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="2e401-112">IntelliSense options are not available when the insertion point is inside the quotation marks around a string literal, for example:</span></span>  
  
     `WHERE FirstName LIKE 'Patri%|'`  
  
-   <span data-ttu-id="2e401-113">Les options automatiques ne sont pas activées.</span><span class="sxs-lookup"><span data-stu-id="2e401-113">The automatic options are turned off.</span></span>  
  
     <span data-ttu-id="2e401-114">La plupart des fonctionnalités IntelliSense fonctionnent automatiquement par défaut. Vous pouvez toutefois désactiver n'importe quelle fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="2e401-114">Many IntelliSense features work automatically by default, but you can disable any feature.</span></span>  
  
     <span data-ttu-id="2e401-115">Même si l'option qui permet de compléter automatiquement les instructions est désactivée, vous pouvez utiliser une fonctionnalité IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="2e401-115">Even when automatic statement completion is disabled, you can use an IntelliSense feature.</span></span> <span data-ttu-id="2e401-116">Pour plus d’informations, consultez [Configurer IntelliSense &#40;SQL Server Management Studio&#41;](configure-intellisense-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="2e401-116">For more information, see [Configure IntelliSense &#40;SQL Server Management Studio&#41;](configure-intellisense-sql-server-management-studio.md).</span></span>  
  
## <a name="database-engine-query-intellisense"></a><span data-ttu-id="2e401-117">Requête de moteur de base de données IntelliSense</span><span class="sxs-lookup"><span data-stu-id="2e401-117">Database Engine Query IntelliSense</span></span>  
 <span data-ttu-id="2e401-118">Les problèmes suivants s’appliquent à l’éditeur de requête du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="2e401-118">The following issues apply to the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] Query Editor:</span></span>  
  
-   <span data-ttu-id="2e401-119">La fonctionnalité IntelliSense de l’éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] ne prend pas en charge tous les éléments de la syntaxe [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2e401-119">The IntelliSense functionality of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor does not support all [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax elements.</span></span> <span data-ttu-id="2e401-120">L'aide sur les paramètres ne prend pas en charge les paramètres dans certains objets, tels que les procédures stockées étendues.</span><span class="sxs-lookup"><span data-stu-id="2e401-120">Parameter help does not support the parameters in some objects, such as extended stored procedures.</span></span> <span data-ttu-id="2e401-121">Pour plus d’informations, consultez [Syntaxe Transact-SQL prise en charge par IntelliSense](transact-sql-syntax-supported-by-intellisense.md).</span><span class="sxs-lookup"><span data-stu-id="2e401-121">For more information, see [Transact-SQL Syntax Supported by IntelliSense](transact-sql-syntax-supported-by-intellisense.md).</span></span>  
  
-   <span data-ttu-id="2e401-122">IntelliSense n’est disponible que si l’éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] est connecté à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] de [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="2e401-122">IntelliSense is only available when the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor is connected to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] from [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or later.</span></span> <span data-ttu-id="2e401-123">IntelliSense n’est pas disponible quand l’éditeur de requête est connecté à des versions antérieures du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e401-123">IntelliSense is not available when the Query Editor is connected to earlier versions of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="2e401-124">IntelliSense est désactivé dans l’éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] quand le mode SQLCMD est activé.</span><span class="sxs-lookup"><span data-stu-id="2e401-124">IntelliSense is turned off in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor when the SQLCMD mode is set on.</span></span>  
  
-   <span data-ttu-id="2e401-125">Les fonctionnalités IntelliSense ne couvrent pas les objets de base de données créés par une autre connexion après que votre fenêtre d'éditeur s'est connectée à la base de données.</span><span class="sxs-lookup"><span data-stu-id="2e401-125">IntelliSense functionality does not cover database objects created by another connection after your editor window connected to the database.</span></span> <span data-ttu-id="2e401-126">Si des objets sont absents dans les fonctionnalités IntelliSense telles que les listes de saisie semi-automatique, vous pouvez choisir l'un de ces trois mécanismes pour actualiser le cache d'objets pour votre fenêtre d'éditeur :</span><span class="sxs-lookup"><span data-stu-id="2e401-126">If objects are missing from IntelliSense features such as completion lists, you can choose one of these three mechanisms to refresh the cache of objects for your editor window:</span></span>  
  
    -   <span data-ttu-id="2e401-127">Sélectionnez le menu **Edition** , sélectionnez **IntelliSense**, puis **Actualiser le cache local**.</span><span class="sxs-lookup"><span data-stu-id="2e401-127">Select the **Edit** menu, select **IntelliSense**, then select **Refresh Local Cache**.</span></span>  
  
    -   <span data-ttu-id="2e401-128">Utilisez le raccourci clavier CTRL+MAJ+R.</span><span class="sxs-lookup"><span data-stu-id="2e401-128">Use the CTRL+Shift+R keyboard shortcut.</span></span>  
  
    -   <span data-ttu-id="2e401-129">Déconnectez la fenêtre d’éditeur de l’instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] , puis reconnectez-la.</span><span class="sxs-lookup"><span data-stu-id="2e401-129">Disconnect your editor window from the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and reconnect.</span></span>  
  
-   <span data-ttu-id="2e401-130">Les listes de saisie semi-automatique n'incluent pas les objets de base de données pour lesquels vous n'avez pas d'autorisations.</span><span class="sxs-lookup"><span data-stu-id="2e401-130">Completion lists do not include database objects for which you do not have permissions.</span></span> <span data-ttu-id="2e401-131">IntelliSense signale les références aux objets pour lesquels vous disposez d'autorisations.</span><span class="sxs-lookup"><span data-stu-id="2e401-131">IntelliSense flags references to objects for which you do have permissions.</span></span> <span data-ttu-id="2e401-132">Par exemple, si vous ouvrez un script écrit par un autre utilisateur, toute référence à un objet pour lequel cette personne dispose d'autorisations, contrairement à vous, est signalée comme incorrecte.</span><span class="sxs-lookup"><span data-stu-id="2e401-132">For example, if you open a script that is written by someone else, any references to objects for which that person has permissions and you do not are flagged as incorrect.</span></span>  
  
-   <span data-ttu-id="2e401-133">Les listes de saisie semi-automatique peuvent cesser de fonctionner si vous perdez la connexion à l’instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e401-133">Completion lists might stop working if you lose the connection to the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="2e401-134">Rétablissez la connexion à l'instance.</span><span class="sxs-lookup"><span data-stu-id="2e401-134">Reconnect to the instance.</span></span>  
  
  
