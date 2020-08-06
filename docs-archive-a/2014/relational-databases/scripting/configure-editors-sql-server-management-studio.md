---
title: Configurer les éditeurs
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: e7c7a8ef-f561-4258-a7b6-c445dba69f87
author: rothja
ms.author: jroth
ms.openlocfilehash: 7e94cdbcd310814081e146e3fd0dbe75260d1240
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701003"
---
# <a name="configure-editors-sql-server-management-studio"></a><span data-ttu-id="64af4-102">Configurer des éditeurs (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="64af4-102">Configure Editors (SQL Server Management Studio)</span></span>
  <span data-ttu-id="64af4-103">Vous pouvez personnaliser le fonctionnement des éditeurs [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] en configurant les options pour chaque éditeur.</span><span class="sxs-lookup"><span data-stu-id="64af4-103">You can customize the operation of the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] editors by configuring the options for each editor.</span></span>  
  
## <a name="settng-editor-options"></a><span data-ttu-id="64af4-104">Définition des options d'éditeur</span><span class="sxs-lookup"><span data-stu-id="64af4-104">Settng Editor Options</span></span>  
 <span data-ttu-id="64af4-105">La plupart des options d’éditeur peuvent être définies dans le menu **Outils**, en sélectionnant **Options...** pour afficher la boîte de dialogue **Options**.</span><span class="sxs-lookup"><span data-stu-id="64af4-105">Most of the editor options are set by using the **Tools** menu and selecting **Options...** to display an **Options** dialog.</span></span> <span data-ttu-id="64af4-106">Dans la boîte de dialogue **Options** , ouvrez le nœud **Éditeur de texte** dans le volet gauche pour définir les options d'édition de code et de texte.</span><span class="sxs-lookup"><span data-stu-id="64af4-106">In the **Options** dialog, open the **Text Editor** node in the left pane to set code and text editing options.</span></span> <span data-ttu-id="64af4-107">Les nœuds sous Éditeur de texte s'appliquent à des éditeurs spécifiques :</span><span class="sxs-lookup"><span data-stu-id="64af4-107">The nodes under Text Editor apply to specific editors:</span></span>  
  
1.  <span data-ttu-id="64af4-108">**Tous les langages** : les options définies à l’aide de ce nœud s’appliquent à tous les éditeurs [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64af4-108">**All Languages** - options set using this node apply to all of the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] editors.</span></span> <span data-ttu-id="64af4-109">Vous pouvez remplacer ces paramètres en utilisant les autres nœuds pour définir différentes options pour un éditeur spécifique.</span><span class="sxs-lookup"><span data-stu-id="64af4-109">You can override these settings by using the other nodes to set different options for a specific editor.</span></span>  
  
2.  <span data-ttu-id="64af4-110">**Texte brut** : les options définies à l’aide de ce nœud s’appliquent aux éditeurs MDX, DMX ainsi qu’aux éditeurs de texte.</span><span class="sxs-lookup"><span data-stu-id="64af4-110">**Plain Text** - options set using this node apply to the MDX, DMX, and text editors.</span></span>  
  
3.  <span data-ttu-id="64af4-111">**Transact-SQL** : les options définies à l’aide de ce nœud s’appliquent à l’éditeur de requête du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="64af4-111">**Transact-SQL** - options set using this node apply to the Database Engine Query Editor.</span></span>  
  
4.  <span data-ttu-id="64af4-112">**XML** : les options définies à l’aide de ce nœud s’appliquent à l’éditeur XML for Analysis.</span><span class="sxs-lookup"><span data-stu-id="64af4-112">**XML** - options set using this node apply to the XML for Analysis editor.</span></span>  
  
 <span data-ttu-id="64af4-113">Ouvrez les nœuds **Exécution de la requête** ou **Résultats de la requête** pour personnaliser l'exécution des requêtes et la façon dont les résultats sont affichés.</span><span class="sxs-lookup"><span data-stu-id="64af4-113">Open the **Query Execution** or **Query Results** nodes to customize the execution of queries and how the results are displayed.</span></span>  
  
## <a name="editor-configuration-tasks"></a><span data-ttu-id="64af4-114">Tâches de configuration d'éditeur</span><span class="sxs-lookup"><span data-stu-id="64af4-114">Editor Configuration Tasks</span></span>  
  
|<span data-ttu-id="64af4-115">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="64af4-115">Task Description</span></span>|<span data-ttu-id="64af4-116">Rubrique</span><span class="sxs-lookup"><span data-stu-id="64af4-116">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="64af4-117">Décrit comment spécifier qu'un éditeur doit être ouvert par un double-clic sur un fichier avec une extension spécifiée dans l'Explorateur Windows.</span><span class="sxs-lookup"><span data-stu-id="64af4-117">Describes how to specify that an editor be opened by double-clicking on a file with a specified extension in Windows Explorer.</span></span>|[<span data-ttu-id="64af4-118">Associer des extensions de fichier à un éditeur de code</span><span class="sxs-lookup"><span data-stu-id="64af4-118">Associate File Extensions to a Code Editor</span></span>](associate-file-extensions-to-a-code-editor.md)|  
|<span data-ttu-id="64af4-119">Décrit comment personnaliser les polices pour rendre le code et le texte plus lisibles.</span><span class="sxs-lookup"><span data-stu-id="64af4-119">Describes how to customize fonts to make code and text more readable.</span></span>|[<span data-ttu-id="64af4-120">Modifier la couleur, la taille et le style de la police</span><span class="sxs-lookup"><span data-stu-id="64af4-120">Change Font Color, Size, and Style</span></span>](change-font-color-size-and-style.md)|  
|<span data-ttu-id="64af4-121">Décrit comment afficher des propriétés.</span><span class="sxs-lookup"><span data-stu-id="64af4-121">Describes how to view properties.</span></span>|[<span data-ttu-id="64af4-122">Utiliser la fenêtre Propriétés dans Management Studio</span><span class="sxs-lookup"><span data-stu-id="64af4-122">Use the Properties Window in Management Studio</span></span>](use-the-properties-window-in-management-studio.md)|  
|<span data-ttu-id="64af4-123">Emplacement des pages d'aide F1 concernant les boîtes de dialogue d'options d'éditeur.</span><span class="sxs-lookup"><span data-stu-id="64af4-123">Location of the F1 help pages for the editor options dialogs.</span></span>|[<span data-ttu-id="64af4-124">Aide (F1) des pages Options de requête</span><span class="sxs-lookup"><span data-stu-id="64af4-124">Query Options Pages F1 Help</span></span>](../../database-engine/query-options-pages-f1-help.md)|  
  
  
