---
title: Vérifier l’état des messages électroniques envoyés avec la messagerie de base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- e-mail [SQL Server], status information
- mail [SQL Server], status information
- Database Mail [SQL Server], message status
- status information [Database Mail]
ms.assetid: eb290f24-b52f-46bc-84eb-595afee6a5f3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1642c456cd64484dede64f8127ff2f979f2242e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614626"
---
# <a name="check-the-status-of-e-mail-messages-sent-with-database-mail"></a><span data-ttu-id="db3df-102">Vérifier l'état des messages électroniques envoyés avec la messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="db3df-102">Check the Status of E-Mail Messages Sent With Database Mail</span></span>
  <span data-ttu-id="db3df-103">Cette rubrique explique comment vérifier l'état du message électronique envoyé à l'aide de la messagerie de base de données dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db3df-103">This topic describes how to check the status of the e-mail message sent using Database Mail  in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="db3df-104">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="db3df-104">**Before you begin:**</span></span>  
  
-   <span data-ttu-id="db3df-105">**Pour afficher l’état de l’e-mail envoyé avec Database Mail, à l’aide de :**  [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="db3df-105">**To view the status of the e-mail sent using Database Mail, using:**  [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="db3df-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="db3df-106">Before You Begin</span></span>  
 <span data-ttu-id="db3df-107">La messagerie de base de données conserve un exemplaire des messages électroniques sortants qu’elle affiche dans les vues **sysmail_allitems**, **sysmail_sentitems**, **sysmail_unsentitems**et **sysmail_faileditems** de la base de données **msdb** .</span><span class="sxs-lookup"><span data-stu-id="db3df-107">Database Mail keeps copies of outgoing e-mail messages and displays them in the **sysmail_allitems**, **sysmail_sentitems**, **sysmail_unsentitems**, **sysmail_faileditems** views of the **msdb** database.</span></span> <span data-ttu-id="db3df-108">Le programme externe de la messagerie de base de données consigne les activités de l’application dans un journal qu’elle affiche par le biais du journal d’événements des applications Windows et la vue **sysmail_event_log** dans la base de données **msdb** .</span><span class="sxs-lookup"><span data-stu-id="db3df-108">The Database Mail external program logs activity and displays the log through the Windows Application Event Log and the **sysmail_event_log** view in the **msdb** database.</span></span> <span data-ttu-id="db3df-109">Pour vérifier l'état d'un message électronique, exécutez une requête sur cette vue.</span><span class="sxs-lookup"><span data-stu-id="db3df-109">To check the status of an e-mail message, run a query against this view.</span></span> <span data-ttu-id="db3df-110">Les messages peuvent présenter quatre états distincts : **sent**(envoyé), **unsent**(non envoyé), **retrying**(nouvel essai) et **failed**(échec).</span><span class="sxs-lookup"><span data-stu-id="db3df-110">E-mail messages have one of four possible statuses: **sent**, **unsent**, **retrying**, and **failed**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="db3df-111">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="db3df-111">Using Transact-SQL</span></span>  
 <span data-ttu-id="db3df-112">**Pour afficher l'état du message électronique envoyé à l'aide de la messagerie de base de données**</span><span class="sxs-lookup"><span data-stu-id="db3df-112">**To view the status of the e-mail sent using Database Mail**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="db3df-113">Pour obtenir un exemple de cette procédure, consultez [Exemple (Transact-SQL)](#TsqlExample)plus loin dans cette section.</span><span class="sxs-lookup"><span data-stu-id="db3df-113">For an example of this procedure, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="db3df-114">Sélectionnez des éléments dans la table **sysmail_allitems** , en spécifiant le ou les messages qui vous intéressent par le biais de l’option **mailitem_id** ou **sent_status**.</span><span class="sxs-lookup"><span data-stu-id="db3df-114">Select from the **sysmail_allitems** table, specifying the messages of interest by **mailitem_id** or **sent_status**.</span></span>  
  
2.  <span data-ttu-id="db3df-115">Pour vérifier l’état retourné par le programme externe pour les messages électroniques, définissez une jointure allant de **sysmail_allitems** à la vue **sysmail_event_log** dans la colonne **mailitem_id** , comme illustré dans la section suivante.</span><span class="sxs-lookup"><span data-stu-id="db3df-115">To check the status returned from the external program for the e-mail messages, join **sysmail_allitems** to **sysmail_event_log** view on the **mailitem_id** column, as shown in the following section.</span></span>  
  
     <span data-ttu-id="db3df-116">Par défaut, le programme externe n'enregistre pas d'informations sur les messages correctement envoyés.</span><span class="sxs-lookup"><span data-stu-id="db3df-116">By default, the external program does not log information about messages that were successfully sent.</span></span> <span data-ttu-id="db3df-117">Si vous voulez activer le journal pour tous les messages, définissez le niveau de journalisation sur le mode commenté par le biais de la page **Configurer les paramètres du système** de l' **Assistant Configuration de la messagerie de base de données**.</span><span class="sxs-lookup"><span data-stu-id="db3df-117">To log all messages, set the logging level to verbose using the **Configure System Parameters** page of the **Database Mail Configuration Wizard.**</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="db3df-118">Exemple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="db3df-118">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="db3df-119">L'exemple suivant regroupe des informations sur tous les messages électroniques envoyés à `danw` que le programme externe n'a pas pu envoyer correctement.</span><span class="sxs-lookup"><span data-stu-id="db3df-119">The following example lists information about any e-mail messages sent to `danw` that the external program could not send successfully.</span></span> <span data-ttu-id="db3df-120">L'instruction renseigne sur l'objet ainsi que sur la date et l'heure auxquelles la tentative d'envoi du message par le programme externe a échoué, elle indique également le message d'erreur provenant du journal de la messagerie de base de données.</span><span class="sxs-lookup"><span data-stu-id="db3df-120">The statement lists the subject, the date and time that the external program failed to send the message, and the error message from the Database Mail log.</span></span>  
  
```  
USE msdb ;  
GO  
  
-- Show the subject, the time that the mail item row was last  
-- modified, and the log information.  
-- Join sysmail_faileditems to sysmail_event_log   
-- on the mailitem_id column.  
-- In the WHERE clause list items where danw was in the recipients,  
-- copy_recipients, or blind_copy_recipients.  
-- These are the items that would have been sent  
-- to danw.  
  
SELECT items.subject,  
    items.last_mod_date  
    ,l.description FROM dbo.sysmail_faileditems as items  
INNER JOIN dbo.sysmail_event_log AS l  
    ON items.mailitem_id = l.mailitem_id  
WHERE items.recipients LIKE '%danw%'    
    OR items.copy_recipients LIKE '%danw%'   
    OR items.blind_copy_recipients LIKE '%danw%'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="db3df-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="db3df-121">See Also</span></span>  
 [<span data-ttu-id="db3df-122">Journal et audits de la messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="db3df-122">Database Mail Log and Audits</span></span>](database-mail-log-and-audits.md)  
  
  
