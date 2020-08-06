---
title: Générer un script pour une session d’événements étendus | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 80f9fdde-1f13-4292-a4fc-55da826be3b4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 11adc60ae7c7e0f8b8012d06f56c83874d3708ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604120"
---
# <a name="script-an-extended-event-session"></a><span data-ttu-id="d51e4-102">Générer un script de session d'événements étendus</span><span class="sxs-lookup"><span data-stu-id="d51e4-102">Script an Extended Event Session</span></span>
  <span data-ttu-id="d51e4-103">Cette rubrique explique comment générer un script de session d'événements.</span><span class="sxs-lookup"><span data-stu-id="d51e4-103">This topic describes how to script an event session.</span></span> <span data-ttu-id="d51e4-104">Vous pouvez exporter, modifier ou supprimer la session d'événements ou supprimer et créer la session d'événements dans les emplacements suivants :</span><span class="sxs-lookup"><span data-stu-id="d51e4-104">You can export, alter, or drop the event session, or drop and create the event session to the following:</span></span>  
  
-   <span data-ttu-id="d51e4-105">**Nouvelle fenêtre d’éditeur de requête**</span><span class="sxs-lookup"><span data-stu-id="d51e4-105">**New Query Editor Window**</span></span>  
  
-   <span data-ttu-id="d51e4-106">**Fichier**</span><span class="sxs-lookup"><span data-stu-id="d51e4-106">**File**</span></span>  
  
-   <span data-ttu-id="d51e4-107">**Presse-papiers**</span><span class="sxs-lookup"><span data-stu-id="d51e4-107">**Clipboard**</span></span>  
  
-   <span data-ttu-id="d51e4-108">**Travail de l'Agent**</span><span class="sxs-lookup"><span data-stu-id="d51e4-108">**Agent Job**</span></span>  
  
### <a name="to-script-an-existing-event-session"></a><span data-ttu-id="d51e4-109">Pour générer un script de session d'événements existante</span><span class="sxs-lookup"><span data-stu-id="d51e4-109">To script an existing event session</span></span>  
  
1.  <span data-ttu-id="d51e4-110">Dans l'Explorateur d'objets, développez le nœud **Gestion** , puis **Événements étendus**.</span><span class="sxs-lookup"><span data-stu-id="d51e4-110">In Object Explorer, expand the **Management** node, and then expand **Extended Events**.</span></span>  
  
2.  <span data-ttu-id="d51e4-111">Cliquez avec le bouton droit sur la session dont vous voulez générer le script, pointez sur **Générer un script de la session en tant que**, pointez sur **CREATE to**, puis sélectionnez où vous souhaitez écrire la session.</span><span class="sxs-lookup"><span data-stu-id="d51e4-111">Right-click the session you want to script, point to **Script Session as**, point to **CREATE to**, and then select where you want to script the session.</span></span>  
  
### <a name="to-script-a-new-event-session"></a><span data-ttu-id="d51e4-112">Pour générer un script de nouvelle session d'événements</span><span class="sxs-lookup"><span data-stu-id="d51e4-112">To script a new event session</span></span>  
  
1.  <span data-ttu-id="d51e4-113">Dans l'Explorateur d'objets, développez le nœud **Gestion** , puis **Événements étendus**.</span><span class="sxs-lookup"><span data-stu-id="d51e4-113">In Object Explorer, expand the **Management** node, and then expand **Extended Events**.</span></span>  
  
2.  <span data-ttu-id="d51e4-114">Cliquez avec le bouton droit sur **Sessions**, puis cliquez sur **Nouvelle session**.</span><span class="sxs-lookup"><span data-stu-id="d51e4-114">Right-click **Sessions**, and then click **New Session**.</span></span>  
  
3.  <span data-ttu-id="d51e4-115">Dans l'interface utilisateur **Nouvelle session** , créez la session d'événements, puis sélectionnez où vous souhaitez écrire la session d'événements dans la liste déroulante **Script** .</span><span class="sxs-lookup"><span data-stu-id="d51e4-115">In the **New Session** UI, create the event session, and then select where you want to script the event session from the **Script** drop-down list.</span></span>  
  
### <a name="to-script-a-modified-event-session"></a><span data-ttu-id="d51e4-116">Pour générer un script de session d'événements modifiée</span><span class="sxs-lookup"><span data-stu-id="d51e4-116">To script a modified event session</span></span>  
  
1.  <span data-ttu-id="d51e4-117">Dans l'Explorateur d'objets, développez le nœud **Gestion** , puis **Événements étendus**.</span><span class="sxs-lookup"><span data-stu-id="d51e4-117">In Object Explorer, expand the **Management** node, and then expand **Extended Events**.</span></span>  
  
2.  <span data-ttu-id="d51e4-118">Cliquez avec le bouton droit sur la session à modifier, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="d51e4-118">Right-click the session you want to modify, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="d51e4-119">Dans la boîte de dialogue **Propriétés de la session** , modifiez la session d'événements, puis sélectionnez où vous souhaitez écrire la session modifiée dans la liste déroulante **Script** .</span><span class="sxs-lookup"><span data-stu-id="d51e4-119">In the **Session Properties** dialog box, modify the event session, and then select where you want to script the modified session from the **Script** drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d51e4-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d51e4-120">See Also</span></span>  
 [<span data-ttu-id="d51e4-121">Événements étendus</span><span class="sxs-lookup"><span data-stu-id="d51e4-121">Extended Events</span></span>](../relational-databases/extended-events/extended-events.md)  
  
  
