---
title: Créer un événement défini par l’utilisateur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent alerts, user-defined events
- user-defined events [SQL Server]
- multiple language support [SQL Server], alerts
- languages [SQL Server], alerts
- severity levels [SQL Server]
- global considerations [SQL Server], alerts
- events [SQL Server], user-defined
- SQL Server Agent alerts, multiple-language environments
- alerts [SQL Server], user-defined events
- alerts [SQL Server], multiple-language environments
- custom events [SQL Server Agent]
- international considerations [SQL Server], alerts
ms.assetid: 03d71a35-97fa-4bba-aa9a-23ac9c9cf879
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2323dc4da3d1a8a67dad41ea189877ade25eff0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710104"
---
# <a name="create-a-user-defined-event"></a><span data-ttu-id="83472-102">Créer un événement défini par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="83472-102">Create a User-Defined Event</span></span>
  <span data-ttu-id="83472-103">Vous pouvez créer des événements définis par l'utilisateur si vous voulez surveiller d'autres événements que ceux qui sont prédéfinis par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83472-103">You can create user-defined events if you want to monitor events other than events that are predefined by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="83472-104">Vous pouvez également attribuer un niveau de sévérité à chaque événement défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="83472-104">You can also assign a severity level to each user-defined event.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="83472-105">Quand vous utilisez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], sélectionnez l’option **Enregistrer dans le journal des événements** pour chaque message d’événement défini par l’utilisateur, pour vous assurer que les messages seront journalisés.</span><span class="sxs-lookup"><span data-stu-id="83472-105">When using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the **Write to Windows application event log** option for each user-defined event message, to ensure that the messages are logged.</span></span> <span data-ttu-id="83472-106">Par défaut, les messages définis par l'utilisateur de sévérité inférieure à 19 ne sont pas envoyés au journal des applications [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows lorsqu'ils se produisent.</span><span class="sxs-lookup"><span data-stu-id="83472-106">By default, user-defined messages of severity lower than 19 are not sent to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application log when they occur.</span></span> <span data-ttu-id="83472-107">Par conséquent, les messages définis par l'utilisateur de sévérité inférieure à 19 ne déclenchent pas d'alertes au niveau de l'Agent SQL Server.</span><span class="sxs-lookup"><span data-stu-id="83472-107">User-defined messages of severity lower than 19 therefore do not trigger SQL Server Agent alerts.</span></span>  
  
 <span data-ttu-id="83472-108">Les événements définis par l'utilisateur doivent posséder un numéro de message unique.</span><span class="sxs-lookup"><span data-stu-id="83472-108">User-defined events must have a unique message number.</span></span> <span data-ttu-id="83472-109">Les numéros de message liés à un événement défini par l'utilisateur doivent être supérieurs à 50 000.</span><span class="sxs-lookup"><span data-stu-id="83472-109">Message numbers for a user-defined event must be greater than 50,000.</span></span> <span data-ttu-id="83472-110">Vous pouvez définir des messages pour l'événement dans plusieurs langues.</span><span class="sxs-lookup"><span data-stu-id="83472-110">You can define messages for the event in multiple languages.</span></span> <span data-ttu-id="83472-111">Cependant, un message **En-US** doit exister avant que des messages correspondant à d’autres langues puissent être ajoutés.</span><span class="sxs-lookup"><span data-stu-id="83472-111">However, an **En-US** error message must exist before messages in other languages can be added.</span></span>  
  
 <span data-ttu-id="83472-112">Si vous administrez un environnement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] multilingue, créez des messages définis par l'utilisateur dans chacune des langues prises en charge par le système.</span><span class="sxs-lookup"><span data-stu-id="83472-112">If you administer a multiple-language [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] environment, create user-defined messages in each of the languages that are supported.</span></span> <span data-ttu-id="83472-113">Par exemple, si vous créez un nouveau message d'événement qui sera utilisé aussi bien sur un serveur anglais que sur un serveur allemand, vous devez utiliser le même numéro d'événement et le même niveau de sévérité pour les deux, mais leur affecter un message dans une langue différente.</span><span class="sxs-lookup"><span data-stu-id="83472-113">For example, if you are creating a new event message to be used on both an English and a German server, use the same message number and severity for both, but assign a different language to each.</span></span>  
  
 <span data-ttu-id="83472-114">Les tâches suivantes apportent des informations sur la façon de créer des événements définis par l'utilisateur, ainsi que des alertes qui leur répondent :</span><span class="sxs-lookup"><span data-stu-id="83472-114">The following tasks provide information about how to create user-defined events and alerts that respond to them:</span></span>  
  
 <span data-ttu-id="83472-115">**Pour créer une alerte en fonction d'un numéro de message**</span><span class="sxs-lookup"><span data-stu-id="83472-115">**To create an alert based on a message number**</span></span>  
  
-   [<span data-ttu-id="83472-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="83472-116">SQL Server Management Studio</span></span>](create-an-alert-using-an-error-number.md)  
  
-   [<span data-ttu-id="83472-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="83472-117">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql)  
  
 <span data-ttu-id="83472-118">**Pour créer une alerte en fonction de niveaux de gravité**</span><span class="sxs-lookup"><span data-stu-id="83472-118">**To create an alert based on severity levels**</span></span>  
  
-   [<span data-ttu-id="83472-119">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="83472-119">SQL Server Management Studio</span></span>](create-an-alert-using-severity-level.md)  
  
-   [<span data-ttu-id="83472-120">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="83472-120">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql)  
  
 <span data-ttu-id="83472-121">**Pour définir la réponse à une alerte**</span><span class="sxs-lookup"><span data-stu-id="83472-121">**To define the response to an alert**</span></span>  
  
-   [<span data-ttu-id="83472-122">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="83472-122">SQL Server Management Studio</span></span>](../sql-server-management-studio-ssms.md)  
  
-   [<span data-ttu-id="83472-123">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="83472-123">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql)  
  
 <span data-ttu-id="83472-124">**Pour créer un message d'erreur d'événement défini par l'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="83472-124">**To create a user-defined event error message**</span></span>  
  
-   [<span data-ttu-id="83472-125">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="83472-125">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-addmessage-transact-sql)  
  
 <span data-ttu-id="83472-126">**Pour modifier un message d'erreur d'événement défini par l'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="83472-126">**To modify a user-defined event error message**</span></span>  
  
-   [<span data-ttu-id="83472-127">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="83472-127">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-altermessage-transact-sql)  
  
 <span data-ttu-id="83472-128">**Pour supprimer un message d'erreur d'événement défini par l'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="83472-128">**To delete a user-defined event error message**</span></span>  
  
-   [<span data-ttu-id="83472-129">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="83472-129">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-dropmessage-transact-sql)  
  
 <span data-ttu-id="83472-130">**Pour désactiver ou réactiver une alerte**</span><span class="sxs-lookup"><span data-stu-id="83472-130">**To disable or reactivate an alert**</span></span>  
  
-   [<span data-ttu-id="83472-131">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="83472-131">SQL Server Management Studio</span></span>](disable-or-reactivate-an-alert.md)  
  
-   [<span data-ttu-id="83472-132">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="83472-132">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="83472-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="83472-133">See Also</span></span>  
 [<span data-ttu-id="83472-134">sp_update_alert &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="83472-134">sp_update_alert &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql)  
  
  
