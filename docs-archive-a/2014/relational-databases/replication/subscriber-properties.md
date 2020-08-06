---
title: Propriétés de l’abonné | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.configdistwizard.subscribers.f1
helpviewer_keywords:
- Subscriber Properties dialog box
ms.assetid: 32aa0347-64e4-4aa4-ac57-6bd3e5d52070
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 81ab9cf5f277ccfe1044e5a7083f019db9d843ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708164"
---
# <a name="subscriber-properties"></a><span data-ttu-id="0561c-102">Propriétés de l'abonné</span><span class="sxs-lookup"><span data-stu-id="0561c-102">Subscriber Properties</span></span>
  <span data-ttu-id="0561c-103">La boîte de dialogue **Propriétés de l’Abonné** contient des informations relatives aux versions de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] exécutées par l’Abonné qui sont antérieures à [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0561c-103">The **Subscriber Properties** dialog box contains information relevant to Subscribers running versions of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="0561c-104">Options</span><span class="sxs-lookup"><span data-stu-id="0561c-104">Options</span></span>  
 <span data-ttu-id="0561c-105">**Connexion de l'agent à l'Abonné**</span><span class="sxs-lookup"><span data-stu-id="0561c-105">**Agent Connection to the Subscriber**</span></span>  
 <span data-ttu-id="0561c-106">Contexte dans lequel l'Agent de distribution et l'Agent de fusion se connectent à l'Abonné à partir du serveur de distribution. Ceci ne s'applique qu'aux versions antérieures à [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0561c-106">The context under which the Distribution Agent and Merge Agent connect from the Distributor to the Subscriber This applies only to versions before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="0561c-107">Choisissez l'option **Imiter le compte de processus de l'Agent** afin d'établir des connexions à l'Abonné grâce au contexte du compte de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur le Serveur de distribution, ou bien choisissez **Authentification SQL Server**et saisissez alors une valeur pour chacun des champs **Connexion** et **Mot de passe**.</span><span class="sxs-lookup"><span data-stu-id="0561c-107">Select **Impersonate agent process account** to make connections to the Subscriber using the context of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent account at the Distributor, or specify **SQL Server Authentication**, and then enter a value for **Login** and **Password**.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="0561c-108">recommande de sélectionner plutôt l'option **Imiter le compte de processus de l'Agent**.</span><span class="sxs-lookup"><span data-stu-id="0561c-108">recommends that you select **Impersonate agent process account**.</span></span>  
  
 <span data-ttu-id="0561c-109">Pour [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] et versions ultérieures, les informations de connexion sont spécifiées pour chaque abonnement dans l'Assistant Nouvel abonnement et vous pouvez les modifier dans la boîte de dialogue **Propriétés de l'abonnement** .</span><span class="sxs-lookup"><span data-stu-id="0561c-109">For [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions, connection information is specified for each subscription in the New Subscription Wizard and can be changed in the **Subscription Properties** dialog box.</span></span>  
  
 <span data-ttu-id="0561c-110">**Planifications des agents par défaut**</span><span class="sxs-lookup"><span data-stu-id="0561c-110">**Default Agent Schedules**</span></span>  
 <span data-ttu-id="0561c-111">Planification par défaut utilisée dans l'Assistant Nouvel abonnement pour les Abonnés qui exécutent des versions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] antérieures à [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0561c-111">The default schedule used in the New Subscription Wizard for Subscribers running versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span></span>  
  
 <span data-ttu-id="0561c-112">**Divers**</span><span class="sxs-lookup"><span data-stu-id="0561c-112">**Miscellaneous**</span></span>  
 <span data-ttu-id="0561c-113">Inclut des informations relatives à l'abonné et au type d'abonné.</span><span class="sxs-lookup"><span data-stu-id="0561c-113">Includes information on the Subscriber and Subscriber type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0561c-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0561c-114">See Also</span></span>  
 [<span data-ttu-id="0561c-115">Afficher et modifier les propriétés d’un serveur de distribution ou d’un serveur de publication</span><span class="sxs-lookup"><span data-stu-id="0561c-115">View and Modify Distributor and Publisher Properties</span></span>](view-and-modify-distributor-and-publisher-properties.md)   

 [<span data-ttu-id="0561c-116">S'abonner à des publications</span><span class="sxs-lookup"><span data-stu-id="0561c-116">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
