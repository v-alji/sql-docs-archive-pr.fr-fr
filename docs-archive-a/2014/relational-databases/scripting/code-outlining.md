---
title: Mise en relief du code
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Query Editor [SQL Server Management Studio], outlining code
- Query Editor [SQL Server Management Studio], hiding code
ms.assetid: 556c7dfe-7bc8-4cab-a36f-2b753a05d3f1
author: rothja
ms.author: jroth
ms.openlocfilehash: 0a142ca8fbdcdfcfbfd1b71de06c0b0fd4c5339c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603906"
---
# <a name="code-outlining"></a><span data-ttu-id="c7a16-102">Mise en relief du code</span><span class="sxs-lookup"><span data-stu-id="c7a16-102">Code Outlining</span></span>
  <span data-ttu-id="c7a16-103">Vous pouvez utiliser la fonctionnalité mode Plan dans les éditeurs de requête [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] pour masquer le code de manière sélective lorsque vous modifiez des requêtes.</span><span class="sxs-lookup"><span data-stu-id="c7a16-103">You can use the outlining feature in the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] query editors to selectively hide code when you edit queries.</span></span> <span data-ttu-id="c7a16-104">Cela permet d'afficher plus facilement le code sur lequel vous travaillez, surtout dans les fichiers de requête volumineux.</span><span class="sxs-lookup"><span data-stu-id="c7a16-104">This enables you to more easily view the code you are working on, especially in large query files.</span></span>

## <a name="outlining-overview"></a><span data-ttu-id="c7a16-105">Vue d'ensemble du mode Plan</span><span class="sxs-lookup"><span data-stu-id="c7a16-105">Outlining Overview</span></span>
 <span data-ttu-id="c7a16-106">Par défaut, tout le code est visible lorsque vous ouvrez une fenêtre de l'éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="c7a16-106">By default, all code is visible when you open a query editor window.</span></span> <span data-ttu-id="c7a16-107">Les régions du code peuvent être réduites pour être masquées.</span><span class="sxs-lookup"><span data-stu-id="c7a16-107">Regions of the code can be collapsed to hide it from view.</span></span> <span data-ttu-id="c7a16-108">Une ligne verticale sur le contour gauche de la fenêtre d'éditeur utilise un carré avec un signe moins (-) pour identifier le début de chaque région de code pouvant être réduite.</span><span class="sxs-lookup"><span data-stu-id="c7a16-108">A vertical line on the left edge of the editor window uses a square with a minus sign (-) to identify the start of each collapsible code region.</span></span> <span data-ttu-id="c7a16-109">Lorsque vous cliquez sur un signe moins, le texte de la région de code est remplacé par une zone qui contient trois points (…), et le signe moins se transforme en signe plus (+).</span><span class="sxs-lookup"><span data-stu-id="c7a16-109">When you click a minus sign, the text of the code region is replaced with a box that contains three periods (...), and the minus sign changes to a plus sign (+).</span></span> <span data-ttu-id="c7a16-110">Lorsque vous cliquez sur un signe plus, le code réduit apparaît et le signe plus se transforme en signe moins.</span><span class="sxs-lookup"><span data-stu-id="c7a16-110">When you click a plus sign, the collapsed code appears and the plus sign changes to a minus sign.</span></span> <span data-ttu-id="c7a16-111">Lorsque vous déplacez le pointeur sur une zone comportant trois points, une info-bulle apparaît qui affiche le code dans la section réduite.</span><span class="sxs-lookup"><span data-stu-id="c7a16-111">When you move the pointer over a box that has three periods, a tooltip appears that shows the code in the collapsed section.</span></span>

## <a name="system-outline-regions"></a><span data-ttu-id="c7a16-112">Régions du mode Plan système</span><span class="sxs-lookup"><span data-stu-id="c7a16-112">System Outline Regions</span></span>
 <span data-ttu-id="c7a16-113">Chaque éditeur [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] génère un ensemble de régions en mode Plan par défaut, définies par le système.</span><span class="sxs-lookup"><span data-stu-id="c7a16-113">Each [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] editor generates a set of default, system-defined outline regions.</span></span>

 <span data-ttu-id="c7a16-114">Les éditeurs de code MDX et DMX créent des régions en mode Plan pour chaque instruction multiligne.</span><span class="sxs-lookup"><span data-stu-id="c7a16-114">The MDX and DMX code editors create outline regions for each multiline statement.</span></span> <span data-ttu-id="c7a16-115">C'est le seul niveau de mode Plan que ces éditeurs prennent en charge.</span><span class="sxs-lookup"><span data-stu-id="c7a16-115">This is the only level of outlining that these editors support.</span></span>

### <a name="analysis-services-xmla-query-editor-regions"></a><span data-ttu-id="c7a16-116">Régions de l'éditeur de requête XMLA Analysis Services</span><span class="sxs-lookup"><span data-stu-id="c7a16-116">Analysis Services XMLA Query Editor Regions</span></span>
 <span data-ttu-id="c7a16-117">L'éditeur de requête XMLA [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] génère une région en mode Plan pour chaque attribut XML multiligne.</span><span class="sxs-lookup"><span data-stu-id="c7a16-117">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] XMLA Query Editor generates an outline region for each multiline XML attribute.</span></span> <span data-ttu-id="c7a16-118">L'éditeur imbrique les régions en mode Plan pour les balises imbriquées.</span><span class="sxs-lookup"><span data-stu-id="c7a16-118">The editor nests the outline regions for nested tags.</span></span> <span data-ttu-id="c7a16-119">Par exemple, l'éditeur XMLA crée trois régions en mode Plan pour le document suivant.</span><span class="sxs-lookup"><span data-stu-id="c7a16-119">For example, the XMLA Editor creates three outline regions for the following document.</span></span>

 <span data-ttu-id="c7a16-120">![Code XML montrant le plan](../../database-engine/media/editoutlinexmlfull.gif "Code XML montrant le plan")</span><span class="sxs-lookup"><span data-stu-id="c7a16-120">![XML code showing outlining](../../database-engine/media/editoutlinexmlfull.gif "XML code showing outlining")</span></span>

 <span data-ttu-id="c7a16-121">Lorsque vous cliquez sur le signe moins sur la \<InnerTag> ligne, seul le InnerTag est réduit, comme le montre l’illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="c7a16-121">When you click the minus sign on the \<InnerTag> line, just the InnerTag is collapsed, as shown in the following illustration.</span></span>

 <span data-ttu-id="c7a16-122">![Code XML avec nœud interne masqué](../../database-engine/media/editoutlinexmlinnercol.gif "Code XML avec nœud interne masqué")</span><span class="sxs-lookup"><span data-stu-id="c7a16-122">![XML code with inner node hidden](../../database-engine/media/editoutlinexmlinnercol.gif "XML code with inner node hidden")</span></span>

 <span data-ttu-id="c7a16-123">Lorsque vous déplacez le pointeur sur la zone qui contient les trois points (…), le code de la région réduite apparaît dans une info-bulle, comme affiché dans l’illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="c7a16-123">When you move the pointer over the box that has the three periods (...), the code in the collapsed region appears in a tooltip, as shown in the following illustration.</span></span>

 <span data-ttu-id="c7a16-124">![Code XML avec info-bulle montrant le code masqué](../../database-engine/media/editoutlinexmlmouse.gif "Code XML avec info-bulle montrant le code masqué")</span><span class="sxs-lookup"><span data-stu-id="c7a16-124">![XML code with tooltip showing hidden code](../../database-engine/media/editoutlinexmlmouse.gif "XML code with tooltip showing hidden code")</span></span>

 <span data-ttu-id="c7a16-125">Lorsque vous cliquez sur le signe moins sur la \<MiddleTag> ligne, les MiddleTag et InnerTag sont réduits, comme le montre l’illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="c7a16-125">When you click the minus sign on the \<MiddleTag> line, both the MiddleTag and InnerTag are collapsed, as shown in the following illustration.</span></span>

 <span data-ttu-id="c7a16-126">![Code XML avec balises internes et intermédiaires masquées](../../database-engine/media/editoutlinexmlmiddlecol.gif "Code XML avec balises internes et intermédiaires masquées")</span><span class="sxs-lookup"><span data-stu-id="c7a16-126">![XML code with inner and middle tags hidden](../../database-engine/media/editoutlinexmlmiddlecol.gif "XML code with inner and middle tags hidden")</span></span>

 <span data-ttu-id="c7a16-127">Lorsque vous cliquez sur le signe moins sur la \<OuterTag> ligne, les trois lignes sont réduites, comme le montre l’illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="c7a16-127">When you click the minus sign on the \<OuterTag> line, all three lines are collapsed, as shown in the following illustration.</span></span>

 <span data-ttu-id="c7a16-128">![Code XML montrant les trois balises masquées](../../database-engine/media/editoutlinexmloutercol.gif "Code XML montrant les trois balises masquées")</span><span class="sxs-lookup"><span data-stu-id="c7a16-128">![XML code showing all three tags hidden](../../database-engine/media/editoutlinexmloutercol.gif "XML code showing all three tags hidden")</span></span>

### <a name="database-engine-query-editor-regions"></a><span data-ttu-id="c7a16-129">Régions de l'éditeur de requête du moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="c7a16-129">Database Engine Query Editor Regions</span></span>
 <span data-ttu-id="c7a16-130">L’éditeur de requête du [!INCLUDE[ssDE](../../../includes/ssde-md.md)] génère des régions en mode Plan pour chaque élément de la hiérarchie suivante :</span><span class="sxs-lookup"><span data-stu-id="c7a16-130">The [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Query Editor generates outline regions for each element in the following hierarchy:</span></span>

1.  <span data-ttu-id="c7a16-131">Lots.</span><span class="sxs-lookup"><span data-stu-id="c7a16-131">Batches.</span></span> <span data-ttu-id="c7a16-132">Le premier lot est le code compris entre le début du fichier et la première commande GO ou la fin du fichier lorsqu'il n'existe pas de commandes GO.</span><span class="sxs-lookup"><span data-stu-id="c7a16-132">The first batch is the code from the start of the file to either the first GO command or the end of the file when there are no GO commands.</span></span> <span data-ttu-id="c7a16-133">Après la première commande GO, il existe un lot entre chaque commande GO et la commande GO suivante ou la fin du fichier.</span><span class="sxs-lookup"><span data-stu-id="c7a16-133">After the first GO, there is one batch from each GO command to either the next GO command or the end of the file.</span></span>

2.  <span data-ttu-id="c7a16-134">Blocs délimités par les mots clés suivants :</span><span class="sxs-lookup"><span data-stu-id="c7a16-134">Blocks delimited by the following keywords:</span></span>

    -   <span data-ttu-id="c7a16-135">BEGIN - END</span><span class="sxs-lookup"><span data-stu-id="c7a16-135">BEGIN - END</span></span>

    -   <span data-ttu-id="c7a16-136">BEGIN TRY - END TRY</span><span class="sxs-lookup"><span data-stu-id="c7a16-136">BEGIN TRY - END TRY</span></span>

    -   <span data-ttu-id="c7a16-137">BEGIN CATCH - END CATCH</span><span class="sxs-lookup"><span data-stu-id="c7a16-137">BEGIN CATCH - END CATCH</span></span>

3.  <span data-ttu-id="c7a16-138">Instructions multilignes.</span><span class="sxs-lookup"><span data-stu-id="c7a16-138">Multiline statements.</span></span>

 <span data-ttu-id="c7a16-139">Par exemple, l’éditeur de requête du [!INCLUDE[ssDE](../../../includes/ssde-md.md)] crée trois régions en mode Plan pour la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="c7a16-139">For example, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Query Editor creates three outline regions for the following query:</span></span>

```
CREATE PROCEDURE Sales.SampleProc --Outline region 1
AS
BEGIN --Outline region 2 
  SELECT GETDATE() AS TimeOfQuery;
  SELECT * --Outline region 3
  FROM sys.transmission_queue;
  SELECT @@VERSION;
END;
GO
```

 <span data-ttu-id="c7a16-140">Vous pouvez cliquer sur le signe moins de la ligne `SELECT *` pour réduire juste cette instruction `SELECT` .</span><span class="sxs-lookup"><span data-stu-id="c7a16-140">You can click the minus sign on the `SELECT *` line to collapse just that `SELECT` statement.</span></span> <span data-ttu-id="c7a16-141">Pour réduire tout le bloc `BEGIN - END` , cliquez sur le signe moins de la ligne `BEGIN` .</span><span class="sxs-lookup"><span data-stu-id="c7a16-141">To collapse the whole `BEGIN - END` block, click the minus sign on the `BEGIN` line.</span></span> <span data-ttu-id="c7a16-142">Pour réduire tout le lot à la commande `GO` , cliquez sur le signe moins de la ligne `CREATE PROCEDURE` .</span><span class="sxs-lookup"><span data-stu-id="c7a16-142">To collapse the whole batch to the `GO` command, click the minus sign on the `CREATE PROCEDURE` line.</span></span> <span data-ttu-id="c7a16-143">Vous ne pouvez pas réduire les lignes `SELECT GETDATE()` ou `SELECT @@VERSION` individuellement parce qu'il s'agit d'instructions à une seule ligne et qu'elles n'obtiennent pas de régions en mode Plan.</span><span class="sxs-lookup"><span data-stu-id="c7a16-143">You cannot collapse the `SELECT GETDATE()` or `SELECT @@VERSION` lines individually because they are single line statements and do not get outlining regions.</span></span>


