---
title: Modifier une session d’événements étendus | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
ms.assetid: 114ec05b-7eca-4c87-b276-25e37b84be39
author: rothja
ms.author: jroth
ms.openlocfilehash: 14be41e48262bc7ebc8aeeaf55185f5e35d0c72e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600023"
---
# <a name="alter-an-extended-events-session"></a><span data-ttu-id="0bfdc-102">Modifier une session d'événements étendus</span><span class="sxs-lookup"><span data-stu-id="0bfdc-102">Alter an Extended Events Session</span></span>
  <span data-ttu-id="0bfdc-103">Après avoir créé une session d'événements étendus, vous pouvez la modifier en fonction de vos besoins à l'aide de l' **Assistant Événements étendus SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="0bfdc-103">After you create an Extended Events session, you can alter it according to your needs using the **SQL Server Extended Events Wizard**.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="0bfdc-104">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="0bfdc-104">Before you Begin</span></span>  
 <span data-ttu-id="0bfdc-105">Vous ne pouvez pas modifier une cible pour les sessions actives et inactives, et vous ne pouvez pas modifier les configurations avancées de propriétés pour une session active.</span><span class="sxs-lookup"><span data-stu-id="0bfdc-105">You cannot alter a target for active and inactive sessions, and you cannot change the advanced properties configurations for an active session.</span></span>  
  
 <span data-ttu-id="0bfdc-106">Vous pouvez apporter les modifications suivantes aux sessions d'événements actives et inactives :</span><span class="sxs-lookup"><span data-stu-id="0bfdc-106">You can make the following alterations to both active and inactive event sessions:</span></span>  
  
-   <span data-ttu-id="0bfdc-107">Ajouter ou supprimer des événements de la session, puis modifier les configurations des événements, telles que les champs d'événement, les filtres et les actions.</span><span class="sxs-lookup"><span data-stu-id="0bfdc-107">Add or remove events from the session, and alter the event configurations such as event fields, filters and actions.</span></span>  
  
-   <span data-ttu-id="0bfdc-108">Ajouter ou supprimer une cible de la session d'événements.</span><span class="sxs-lookup"><span data-stu-id="0bfdc-108">Add or remove a target from the event session.</span></span>  
  
-   <span data-ttu-id="0bfdc-109">Activer l'option **Démarrer la session d'événements au démarrage du serveur** .</span><span class="sxs-lookup"><span data-stu-id="0bfdc-109">Enable the **Start the event session on server startup** option.</span></span>  
  
 <span data-ttu-id="0bfdc-110">Vous pouvez apporter les modifications supplémentaires suivantes à une session d'événements inactive :</span><span class="sxs-lookup"><span data-stu-id="0bfdc-110">You can make the following additional alterations to an inactive event session:</span></span>  
  
-   <span data-ttu-id="0bfdc-111">Activer l'option **Suivre la relation entre les événements** .</span><span class="sxs-lookup"><span data-stu-id="0bfdc-111">Enable the **Track the relationship between events** option.</span></span>  
  
-   <span data-ttu-id="0bfdc-112">Modifier la configuration de propriétés avancée.</span><span class="sxs-lookup"><span data-stu-id="0bfdc-112">Change the advanced properties configuration.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0bfdc-113">L’ **Assistant Événements étendus SQL Server** ne prend pas en charge la modification de la session d’événements.</span><span class="sxs-lookup"><span data-stu-id="0bfdc-113">The **SQL Server Extended Events Wizard** does not support event session modification.</span></span>  
  
## <a name="how-to-alter-an-extended-events-session-using-the-sql-server-extended-events-wizard"></a><span data-ttu-id="0bfdc-114">Comment modifier une session d'événements étendus à l'aide de l'Assistant Événements étendus SQL Server</span><span class="sxs-lookup"><span data-stu-id="0bfdc-114">How to alter an Extended Events session using the SQL Server Extended Events Wizard</span></span>  
  
-   <span data-ttu-id="0bfdc-115">Dans l'Explorateur d'objets, développez **Gestion**, **Événements étendus**, puis **Sessions**.</span><span class="sxs-lookup"><span data-stu-id="0bfdc-115">In Object Explorer, expand **Management**, expand **Extended Events**, and then expand **Sessions**.</span></span>  
  
-   <span data-ttu-id="0bfdc-116">Cliquez avec le bouton droit sur la session à modifier, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="0bfdc-116">Right-click the session you want to alter, and then click **Properties**.</span></span>  
  
-   <span data-ttu-id="0bfdc-117">Dans la boîte de dialogue **Propriétés** , apportez les modifications appropriées, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0bfdc-117">In the **Properties** dialog box, make the appropriate changes, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bfdc-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0bfdc-118">See Also</span></span>  
 <span data-ttu-id="0bfdc-119">[ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0bfdc-119">[ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql) </span></span>  
 [<span data-ttu-id="0bfdc-120">Créer une session d'événements étendus à l'aide de l'éditeur de requête</span><span class="sxs-lookup"><span data-stu-id="0bfdc-120">Create an Extended Events Session Using Query Editor</span></span>](../../database-engine/create-an-extended-events-session-using-query-editor.md)  
  
  
