---
title: Gérer des connexions dans la liste d’accès à la publication | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- logins [SQL Server replication], publication access list
- publications [SQL Server replication], publication access lists
- publication access list (PAL)
- PAL (publication access list)
- logins [SQL Server replication], managing
ms.assetid: fceb216b-0b18-4e3b-8ae0-13e35920dcbc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b96e6f46403cf3a482f00a3f5155527177920967
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603371"
---
# <a name="manage-logins-in-the-publication-access-list"></a><span data-ttu-id="2308e-102">Gérer des connexions dans la liste d'accès à la publication</span><span class="sxs-lookup"><span data-stu-id="2308e-102">Manage Logins in the Publication Access List</span></span>
  <span data-ttu-id="2308e-103">Cette rubrique explique comment gérer des connexions dans la liste d'accès à la publication dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2308e-103">This topic describes how to manage logins in the Publication Access List in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="2308e-104">L'accès à une publication est contrôlé par la liste d'accès à la publication.</span><span class="sxs-lookup"><span data-stu-id="2308e-104">Access to a publication is controlled by the publication access list (PAL).</span></span> <span data-ttu-id="2308e-105">Les connexions et les groupes peuvent être ajoutés et supprimés de la liste d'accès à la publication.</span><span class="sxs-lookup"><span data-stu-id="2308e-105">Logins and groups can be added and removed from the PAL.</span></span>  
  
 <span data-ttu-id="2308e-106">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="2308e-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2308e-107">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="2308e-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2308e-108">Composants requis</span><span class="sxs-lookup"><span data-stu-id="2308e-108">Prerequisites</span></span>](#Prerequisites)  
  
-   <span data-ttu-id="2308e-109">**Pour gérer les connexions dans la liste d'accès à la publication, à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="2308e-109">**To manage logins in the Publication Access List, using:**</span></span>  
  
     [<span data-ttu-id="2308e-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2308e-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2308e-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2308e-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2308e-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="2308e-112">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="2308e-113">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="2308e-113">Prerequisites</span></span>  
  
-   <span data-ttu-id="2308e-114">Vous devez associer la connexion [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à un utilisateur de base de données dans la base de données de publication avant d'ajouter cette connexion à la liste d'accès à la publication.</span><span class="sxs-lookup"><span data-stu-id="2308e-114">You must associate the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login with a database user in the publication database before you add the login to the PAL.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2308e-115">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2308e-115">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="2308e-116">Vous utilisez la liste d’accès à la publication dans la page **Liste d’accès à la publication** de la boîte de dialogue **Propriétés de la publication - \<Publication>** pour gérer les connexions.</span><span class="sxs-lookup"><span data-stu-id="2308e-116">You use the publication access list (PAL) on the **Publication Access List** page of the **Publication Properties - \<Publication>** dialog box to manage logins.</span></span> <span data-ttu-id="2308e-117">Pour plus d’informations sur la façon d’accéder à cette boîte de dialogue, consultez [Afficher et modifier les propriétés d’une publication](../publish/view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="2308e-117">For more information about how to access this dialog box, see [View and Modify Publication Properties](../publish/view-and-modify-publication-properties.md).</span></span>  
  
#### <a name="to-manage-logins-in-the-pal"></a><span data-ttu-id="2308e-118">Pour gérer des noms de connexion dans la liste d'accès à la publication</span><span class="sxs-lookup"><span data-stu-id="2308e-118">To manage logins in the PAL</span></span>  
  
1.  <span data-ttu-id="2308e-119">Dans la page **Liste d’accès à la publication** de la boîte de dialogue **Propriétés de la publication - \<Publication>** , utilisez les boutons **Ajouter**, **Supprimer** et **Supprimer tout** pour ajouter et supprimer des connexions et des groupes dans la liste d’accès à la publication.</span><span class="sxs-lookup"><span data-stu-id="2308e-119">On the **Publication Access List** page of the **Publication Properties - \<Publication>** dialog box, use the **Add**, **Remove**, and **Remove All** buttons to add and remove logins and groups from the PAL.</span></span> <span data-ttu-id="2308e-120">Ne supprimez pas **distributor_admin** de la liste d'accès à la publication.</span><span class="sxs-lookup"><span data-stu-id="2308e-120">Do not remove **distributor_admin** from the PAL.</span></span> <span data-ttu-id="2308e-121">Ce compte est utilisé par la réplication.</span><span class="sxs-lookup"><span data-stu-id="2308e-121">This account is used by replication.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2308e-122">En cas d'utilisation d'un serveur de distribution distant, les comptes de la liste d'accès à la publication doivent être disponibles à la fois auprès du serveur de publication et auprès du serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="2308e-122">If a remote Distributor is used, accounts in the PAL must be available at both the Publisher and the Distributor.</span></span> <span data-ttu-id="2308e-123">Le compte doit être un compte de domaine ou un compte local défini sur les deux serveurs.</span><span class="sxs-lookup"><span data-stu-id="2308e-123">The account must be either a domain account or a local account that is defined at both servers.</span></span> <span data-ttu-id="2308e-124">Les mots de passe associés aux deux connexions doivent être identiques.</span><span class="sxs-lookup"><span data-stu-id="2308e-124">The passwords that are associated with both logins must be the same.</span></span>  
  
2.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2308e-125">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2308e-125">Using Transact-SQL</span></span>  
  
#### <a name="to-view-groups-and-logins-that-belong-to-the-pal"></a><span data-ttu-id="2308e-126">Pour afficher les groupes et les connexions qui figurent dans la liste d'accès à la publication</span><span class="sxs-lookup"><span data-stu-id="2308e-126">To view groups and logins that belong to the PAL</span></span>  
  
1.  <span data-ttu-id="2308e-127">Exécutez [sp_help_publication_access](/sql/relational-databases/system-stored-procedures/sp-help-publication-access-transact-sql)sur la base de données de publication du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="2308e-127">At the Publisher on the publication database, execute [sp_help_publication_access](/sql/relational-databases/system-stored-procedures/sp-help-publication-access-transact-sql).</span></span> <span data-ttu-id="2308e-128">Pour \*\* \@ publication\*\*, spécifiez le nom de la publication.</span><span class="sxs-lookup"><span data-stu-id="2308e-128">For **\@publication**, specify the publication name.</span></span> <span data-ttu-id="2308e-129">Cela affiche des informations sur les groupes et les connexions qui figurent dans la liste d'accès à la publication.</span><span class="sxs-lookup"><span data-stu-id="2308e-129">This displays information about the groups and logins in the PAL.</span></span>  
  
#### <a name="to-add-groups-and-logins-to-the-pal"></a><span data-ttu-id="2308e-130">Pour ajouter des groupes et des connexions dans la liste d'accès à la publication</span><span class="sxs-lookup"><span data-stu-id="2308e-130">To add groups and logins to the PAL</span></span>  
  
1.  <span data-ttu-id="2308e-131">Exécutez [sp_grant_publication_access](/sql/relational-databases/system-stored-procedures/sp-grant-publication-access-transact-sql)sur la base de données de publication du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="2308e-131">At the Publisher on the publication database, execute [sp_grant_publication_access](/sql/relational-databases/system-stored-procedures/sp-grant-publication-access-transact-sql).</span></span> <span data-ttu-id="2308e-132">Pour \*\* \@ publication**, spécifiez le nom de la publication et, pour la \*\* \@ connexion**, spécifiez le nom de la connexion ou du groupe à ajouter.</span><span class="sxs-lookup"><span data-stu-id="2308e-132">For **\@publication**, specify the publication name; and for **\@login**, specify the name of the login or group that is being added.</span></span>  
  
#### <a name="to-remove-groups-and-logins-from-the-pal"></a><span data-ttu-id="2308e-133">Pour supprimer des groupes et des connexions de la liste d'accès à la publication</span><span class="sxs-lookup"><span data-stu-id="2308e-133">To remove groups and logins from the PAL</span></span>  
  
1.  <span data-ttu-id="2308e-134">Exécutez [sp_revoke_publication_access](/sql/relational-databases/system-stored-procedures/sp-revoke-publication-access-transact-sql)sur la base de données de publication du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="2308e-134">At the Publisher on the publication database, execute [sp_revoke_publication_access](/sql/relational-databases/system-stored-procedures/sp-revoke-publication-access-transact-sql).</span></span> <span data-ttu-id="2308e-135">Pour \*\* \@ publication**, spécifiez le nom de la publication et, pour la \*\* \@ connexion**, spécifiez le nom de la connexion ou du groupe en cours de suppression.</span><span class="sxs-lookup"><span data-stu-id="2308e-135">For **\@publication**, specify the publication name; and for **\@login**, specify the name of the login or group that is being removed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2308e-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2308e-136">See Also</span></span>  
 <span data-ttu-id="2308e-137">[Modèle de sécurité de l’Agent de réplication](replication-agent-security-model.md) </span><span class="sxs-lookup"><span data-stu-id="2308e-137">[Replication Agent Security Model](replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="2308e-138">[Sécuriser une topologie de réplication](view-and-modify-replication-security-settings.md) </span><span class="sxs-lookup"><span data-stu-id="2308e-138">[Secure a Replication Topology](view-and-modify-replication-security-settings.md) </span></span>  
 [<span data-ttu-id="2308e-139">Sécuriser le serveur de publication</span><span class="sxs-lookup"><span data-stu-id="2308e-139">Secure the Publisher</span></span>](secure-the-publisher.md)  
  
  
