---
title: Ajouter un Abonné non-SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.addnonsqlsubscriber.f1
ms.assetid: 21beeaa0-4b9e-48da-be63-1b9ff14e03d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e36d048b11fcc71b27ab0ab2ee815b0284187c4d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610620"
---
# <a name="add-non-sql-server-subscriber"></a><span data-ttu-id="9949b-102">Ajouter un Abonné non-SQL Server</span><span class="sxs-lookup"><span data-stu-id="9949b-102">Add Non-SQL Server Subscriber</span></span>
  <span data-ttu-id="9949b-103">La réplication prend en charge la création d'abonnement par envoi de données (push) à des publications d'instantané et transactionnelles pour les abonnés Oracle et IBM DB2.</span><span class="sxs-lookup"><span data-stu-id="9949b-103">Replication supports creating push subscriptions to snapshot and transactional publications for Oracle and IBM DB2 Subscribers.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9949b-104">Options</span><span class="sxs-lookup"><span data-stu-id="9949b-104">Options</span></span>  
 <span data-ttu-id="9949b-105">**Type d'Abonné à ajouter**</span><span class="sxs-lookup"><span data-stu-id="9949b-105">**Type of Subscriber to add**</span></span>  
 <span data-ttu-id="9949b-106">Sélectionnez un abonné Oracle ou IBM DB2.</span><span class="sxs-lookup"><span data-stu-id="9949b-106">Select an Oracle Subscriber or IBM DB2 Subscriber.</span></span> <span data-ttu-id="9949b-107">Pour plus d’informations sur la prise en charge de ces Abonnés, consultez [Abonnés non-SQL Server](non-sql/non-sql-server-subscribers.md).</span><span class="sxs-lookup"><span data-stu-id="9949b-107">For more information about support for these Subscribers, see [Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md).</span></span>  
  
 <span data-ttu-id="9949b-108">**Nom de la source des données**</span><span class="sxs-lookup"><span data-stu-id="9949b-108">**Data source name**</span></span>  
 <span data-ttu-id="9949b-109">Nom utilisé pour localiser la base de données sur un réseau.</span><span class="sxs-lookup"><span data-stu-id="9949b-109">The name used to locate the database on a network.</span></span> <span data-ttu-id="9949b-110">La réplication produit une chaîne de connexion pour la base de données en utilisant le nom de la source de données, combiné à la connexion, au mot de passe et à toute autre option spécifiée dans la page **Sécurité de l'Agent de distribution** de cet Assistant.</span><span class="sxs-lookup"><span data-stu-id="9949b-110">Replication produces a connection string for the database using the data source name, combined with the login, password, and any connection options you specify in the **Distribution Agent Security** page in this wizard.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9949b-111">Le nom de la source de données et la chaîne de connexion ne sont pas validés par [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tant que l’Agent de distribution n’a pas tenté d’initialiser l’abonnement.</span><span class="sxs-lookup"><span data-stu-id="9949b-111">The data source name and connection string are not validated by [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] until the Distribution Agent attempts to initialize the subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9949b-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9949b-112">See Also</span></span>  
 <span data-ttu-id="9949b-113">[Créer un abonnement pour un abonné non-SQL Server](create-a-subscription-for-a-non-sql-server-subscriber.md) </span><span class="sxs-lookup"><span data-stu-id="9949b-113">[Create a Subscription for a Non-SQL Server Subscriber](create-a-subscription-for-a-non-sql-server-subscriber.md) </span></span>  
 <span data-ttu-id="9949b-114">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span><span class="sxs-lookup"><span data-stu-id="9949b-114">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span></span>  
 [<span data-ttu-id="9949b-115">S'abonner à des publications</span><span class="sxs-lookup"><span data-stu-id="9949b-115">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
