---
title: Exécution des options de requête (page général) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.query.general.f1
ms.assetid: 858a0263-2f04-4692-b8bf-63e93c998ead
author: rothja
ms.author: jroth
ms.openlocfilehash: ce3848b51b81f111333ba0e9ac12c96432dd9863
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613123"
---
# <a name="query-options-execution-general-page"></a><span data-ttu-id="669a0-102">Options de requête – Exécution (page Général)</span><span class="sxs-lookup"><span data-stu-id="669a0-102">Query Options Execution (General Page)</span></span>
  <span data-ttu-id="669a0-103">Cette page vous permet de spécifier les options d'exécution des requêtes [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="669a0-103">Use this page to specify the options for running [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="669a0-104">Pour accéder à cette boîte de dialogue, cliquez avec le bouton droit sur le corps d’une fenêtre de l’éditeur de requête, puis cliquez sur **Options de requête**.</span><span class="sxs-lookup"><span data-stu-id="669a0-104">To access this dialog box, right-click the body of a Query Editor window, and then click **Query Options**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="669a0-105">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="669a0-105">UI element list</span></span>  
 <span data-ttu-id="669a0-106">**SET ROWCOUNT**</span><span class="sxs-lookup"><span data-stu-id="669a0-106">**SET ROWCOUNT**</span></span>  
 <span data-ttu-id="669a0-107">La valeur par défaut 0 indique que [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] attend les résultats, tant que tous les résultats ne sont pas reçus.</span><span class="sxs-lookup"><span data-stu-id="669a0-107">The default value of 0 indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will wait for results until all results are received.</span></span> <span data-ttu-id="669a0-108">Spécifiez une valeur supérieure à 0 pour que [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] arrête la requête après avoir obtenu le nombre de lignes spécifié.</span><span class="sxs-lookup"><span data-stu-id="669a0-108">Provide a value greater than 0 if you want [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to halt the query after obtaining the specified number of rows.</span></span> <span data-ttu-id="669a0-109">Pour désactiver cette option, de manière à renvoyer toutes les lignes, spécifiez SET ROWCOUNT 0.</span><span class="sxs-lookup"><span data-stu-id="669a0-109">To turn this option off (so that all rows are returned), specify SET ROWCOUNT 0.</span></span>  
  
 <span data-ttu-id="669a0-110">**SET TEXTSIZE**</span><span class="sxs-lookup"><span data-stu-id="669a0-110">**SET TEXTSIZE**</span></span>  
 <span data-ttu-id="669a0-111">La valeur par défaut de 2 147 483 647 octets indique que [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] fournira un champ de données complet jusqu'à la limite des champs de données `text`, `ntext`, `nvarchar(max)` et `varchar(max)`.</span><span class="sxs-lookup"><span data-stu-id="669a0-111">The default value of 2,147,483,647 bytes indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will provide a complete data field up to the limit of `text`, `ntext`, `nvarchar(max)`, and `varchar(max)` data fields.</span></span> <span data-ttu-id="669a0-112">Cela n'affecte pas le type de données XML.</span><span class="sxs-lookup"><span data-stu-id="669a0-112">It does not affect the XML data type.</span></span> <span data-ttu-id="669a0-113">Spécifiez un nombre inférieur pour limiter les résultats en cas de valeurs importantes.</span><span class="sxs-lookup"><span data-stu-id="669a0-113">Provide a smaller number to limit results in the case of large values.</span></span> <span data-ttu-id="669a0-114">Les colonnes d'une taille supérieure au nombre spécifié sont tronquées.</span><span class="sxs-lookup"><span data-stu-id="669a0-114">Columns greater than the number provided will be truncated.</span></span>  
  
 <span data-ttu-id="669a0-115">**Délai d’exécution**</span><span class="sxs-lookup"><span data-stu-id="669a0-115">**Execution time-out**</span></span>  
 <span data-ttu-id="669a0-116">Spécifie le nombre de secondes à attendre avant d'annuler la requête.</span><span class="sxs-lookup"><span data-stu-id="669a0-116">Indicates the number of seconds to wait before canceling the query.</span></span> <span data-ttu-id="669a0-117">La valeur 0 indique un délai d'attente illimité ou pas de délai.</span><span class="sxs-lookup"><span data-stu-id="669a0-117">A value of 0 indicates an infinite wait, or no time-out.</span></span>  
  
 <span data-ttu-id="669a0-118">**Délimiteur de traitement**</span><span class="sxs-lookup"><span data-stu-id="669a0-118">**Batch separator**</span></span>  
 <span data-ttu-id="669a0-119">Tapez un mot à utiliser pour séparer les instructions Transact-SQL en traitements.</span><span class="sxs-lookup"><span data-stu-id="669a0-119">Type a word that you use to separate Transact-SQL statements into batches.</span></span> <span data-ttu-id="669a0-120">La valeur par défaut est GO.</span><span class="sxs-lookup"><span data-stu-id="669a0-120">The default is GO.</span></span>  
  
 <span data-ttu-id="669a0-121">**Par défaut, ouvrir les nouvelles requêtes en mode SQLCMD**</span><span class="sxs-lookup"><span data-stu-id="669a0-121">**By default, open new queries in SQLCMD Mode**</span></span>  
 <span data-ttu-id="669a0-122">Activez cette case à cocher pour ouvrir les nouvelles requêtes en mode SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="669a0-122">Select this check box to open new queries in SQLCMD mode.</span></span> <span data-ttu-id="669a0-123">Cette case à cocher est visible uniquement lorsque la boîte de dialogue est ouverte via le menu **Outils** .</span><span class="sxs-lookup"><span data-stu-id="669a0-123">This check box is visible only when the dialog box is opened through the **Tools** menu.</span></span>  
  
 <span data-ttu-id="669a0-124">Lorsque vous sélectionnez cette option, prenez en compte les limitations suivantes :</span><span class="sxs-lookup"><span data-stu-id="669a0-124">When you select this option, be aware of the following limitations:</span></span>  
  
-   <span data-ttu-id="669a0-125">IntelliSense dans l’Éditeur de requête du [!INCLUDE[ssDE](../includes/ssde-md.md)] est désactivé.</span><span class="sxs-lookup"><span data-stu-id="669a0-125">IntelliSense in the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor is turned off.</span></span>  
  
-   <span data-ttu-id="669a0-126">L'Éditeur de requête ne s'exécutant pas à partir de la ligne de commande, vous ne pouvez pas passer de paramètres de ligne de commande tels que des variables.</span><span class="sxs-lookup"><span data-stu-id="669a0-126">Because Query Editor does not run from the command line, you cannot pass in command-line parameters such as variables.</span></span>  
  
-   <span data-ttu-id="669a0-127">L'Éditeur de requête étant incapable de répondre aux invites de système d'exploitation, vous devez prendre soin de ne pas exécuter d'instructions interactives.</span><span class="sxs-lookup"><span data-stu-id="669a0-127">Because Query Editor cannot respond to operating-system prompts, you must be careful not to run interactive statements.</span></span>  
  
 <span data-ttu-id="669a0-128">**Rétablir les valeurs par défaut**</span><span class="sxs-lookup"><span data-stu-id="669a0-128">**Reset to Default**</span></span>  
 <span data-ttu-id="669a0-129">Rétablit toutes les valeurs par défaut initiales des options de cette page.</span><span class="sxs-lookup"><span data-stu-id="669a0-129">Resets all values on this page to the original default values.</span></span>  
  
  
