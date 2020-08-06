---
title: Ajouter ou remplacer un témoin de mise en miroir de base de données (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- witness [SQL Server], establishing
- database mirroring [SQL Server], witness
ms.assetid: 4b5ecffd-f025-4ab7-b69d-8958c6477127
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5dd14ace23956ceef114f1f032b5d4db5febcec7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603036"
---
# <a name="add-or-replace-a-database-mirroring-witness-sql-server-management-studio"></a><span data-ttu-id="e6bf6-102">Ajouter ou remplacer un témoin de mise en miroir de base de données (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="e6bf6-102">Add or Replace a Database Mirroring Witness (SQL Server Management Studio)</span></span>
  <span data-ttu-id="e6bf6-103">Si les points de terminaison de mise en miroir de base de données utilisent l'authentification Windows, vous pouvez utiliser [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour ajouter ou remplacer un témoin.</span><span class="sxs-lookup"><span data-stu-id="e6bf6-103">If the database mirroring endpoints use Windows Authentication,, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to add or replace a witness.</span></span> <span data-ttu-id="e6bf6-104">Lorsqu'un témoin est ajouté dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , la session passe en mode haute sécurité avec basculement automatique.</span><span class="sxs-lookup"><span data-stu-id="e6bf6-104">Adding a witness in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] also changes the operating mode to high-safety mode with automatic failover.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e6bf6-105">Nous vous recommandons vivement de placer le témoin sur un ordinateur distinct de celui des partenaires.</span><span class="sxs-lookup"><span data-stu-id="e6bf6-105">We strongly recommend that the witness reside on a separate computer from either of the partners.</span></span> <span data-ttu-id="e6bf6-106">Le compte de service utilisé par le témoin doit être dans le même domaine que les comptes de service utilisés par les instances de serveur principal et miroir, ou il doit être situé dans un domaine approuvé.</span><span class="sxs-lookup"><span data-stu-id="e6bf6-106">The service account used by the witness must be in the same domain as the service accounts used by the principal and mirror server instances, or it must be in a trusted domain.</span></span>  
  
### <a name="to-add-or-replace-a-witness"></a><span data-ttu-id="e6bf6-107">Pour ajouter ou remplacer un témoin</span><span class="sxs-lookup"><span data-stu-id="e6bf6-107">To Add or Replace a Witness</span></span>  
  
1.  <span data-ttu-id="e6bf6-108">Après vous être connecté à l'instance du serveur principal, dans l'Explorateur d'objets, cliquez sur le nom du serveur pour développer son arborescence.</span><span class="sxs-lookup"><span data-stu-id="e6bf6-108">After connecting to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="e6bf6-109">Développez **Bases de données**, puis sélectionnez la base de données principale de la session dans laquelle vous ajoutez ou remplacez un témoin.</span><span class="sxs-lookup"><span data-stu-id="e6bf6-109">Expand **Databases**, and select the principal database of the session to which you are adding or replacing a witness.</span></span>  
  
3.  <span data-ttu-id="e6bf6-110">Cliquez avec le bouton droit sur la base de données, sélectionnez **Tâches**, puis cliquez sur **Miroir**.</span><span class="sxs-lookup"><span data-stu-id="e6bf6-110">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="e6bf6-111">La page **Mise en miroir** de la boîte de dialogue **Propriétés de la base de données** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="e6bf6-111">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="e6bf6-112">Cliquez sur **Configurer la sécurité**.</span><span class="sxs-lookup"><span data-stu-id="e6bf6-112">Click **Configure Security**.</span></span>  
  
5.  <span data-ttu-id="e6bf6-113">Si l’écran d’accueil **Configurer l’Assistant Sécurité de mise en miroir de bases de données** s’affiche, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e6bf6-113">If the **Configure Database Mirroring Security Wizard** welcome screen appears, click **Next**.</span></span>  
  
6.  <span data-ttu-id="e6bf6-114">Dans la boîte de dialogue **Inclure un serveur témoin** , cliquez sur **Oui**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e6bf6-114">In the **Include Witness Server** dialog box, click **Yes**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="e6bf6-115">Dans la boîte de dialogue **Choisir les serveurs à configurer** , la case **Instance de serveur témoin** est automatiquement cochée.</span><span class="sxs-lookup"><span data-stu-id="e6bf6-115">In the **Choose Servers to Configure** dialog box, the **Witness server instance** check box is automatically checked.</span></span> <span data-ttu-id="e6bf6-116">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e6bf6-116">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="e6bf6-117">Dans la boîte de dialogue **Instance de serveur principal** , conservez le port et le point de terminaison existants.</span><span class="sxs-lookup"><span data-stu-id="e6bf6-117">On the **Principal Server Instance** dialog box, keep the existing port and endpoint.</span></span> <span data-ttu-id="e6bf6-118">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e6bf6-118">Click **Next**.</span></span>  
  
9. <span data-ttu-id="e6bf6-119">Dans la boîte de dialogue **Instance de serveur témoin** , cliquez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="e6bf6-119">On the **Witness Server Instance** dialog box, click **Connect**.</span></span>  
  
10. <span data-ttu-id="e6bf6-120">Dans la boîte de dialogue **Se connecter au serveur** , indiquez l’instance du serveur témoin dans le champ **Nom du serveur** et utilisez l’authentification Windows (valeur par défaut).</span><span class="sxs-lookup"><span data-stu-id="e6bf6-120">In the **Connect to Server** dialog box, specify the witness server instance in the **Server name** field, and use Windows Authentication (the default).</span></span> <span data-ttu-id="e6bf6-121">Cliquez sur **Connecter**.</span><span class="sxs-lookup"><span data-stu-id="e6bf6-121">Click **Connect**.</span></span>  
  
11. <span data-ttu-id="e6bf6-122">Une fois qu’une connexion a été établie, le port d’écoute et le point de terminaison de mise en miroir de bases de données de l’instance du serveur témoin s’affichent dans la boîte de dialogue **Instance de serveur témoin** .</span><span class="sxs-lookup"><span data-stu-id="e6bf6-122">Once a connection is established, the listener port and database mirroring endpoint of the witness server instance are displayed on the **Witness Server Instance** dialog box.</span></span> <span data-ttu-id="e6bf6-123">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e6bf6-123">Click **Next**.</span></span>  
  
12. <span data-ttu-id="e6bf6-124">La boîte de dialogue **Comptes de service** contient les champs des comptes de service de domaine des instances du serveur témoin, miroir et principal.</span><span class="sxs-lookup"><span data-stu-id="e6bf6-124">The **Service Accounts** dialog box contains fields for the domain service accounts of the principal, mirror, and witness server instances.</span></span>  
  
    -   <span data-ttu-id="e6bf6-125">Si toutes les instances du serveur utilisent le même compte de service, laissez les champs vides.</span><span class="sxs-lookup"><span data-stu-id="e6bf6-125">If the server instances all use the same service account, leave the fields blank.</span></span>  
  
    -   <span data-ttu-id="e6bf6-126">Si l’instance du serveur témoin utilise un compte de service différent de celui des partenaires, entrez le nom du compte dans les champs **Principal**, **Miroir**et **Témoin** :</span><span class="sxs-lookup"><span data-stu-id="e6bf6-126">If the witness server instance uses a different service account from either of the partners, fill in the **Principal**, **Mirror**, and **Witness** fields with the account name:</span></span>  
  
         <span data-ttu-id="e6bf6-127">*NOM_DOMAINE* **\\** *nom_utilisateur*</span><span class="sxs-lookup"><span data-stu-id="e6bf6-127">*DOMAINNAME* **\\** *username*</span></span>  
  
         <span data-ttu-id="e6bf6-128">Le nom de domaine doit être indiqué en majuscules.</span><span class="sxs-lookup"><span data-stu-id="e6bf6-128">The domain name must be in upper case.</span></span>  
  
     <span data-ttu-id="e6bf6-129">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e6bf6-129">Click **Next**.</span></span>  
  
13. <span data-ttu-id="e6bf6-130">Dans l’écran récapitulatif **Terminer l’Assistant** , vérifiez éventuellement la configuration du témoin, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="e6bf6-130">On the **Complete the Wizard** summary screen, optionally, verify the witness configuration, and then click **Finish**.</span></span>  
  
14. <span data-ttu-id="e6bf6-131">Une fois l’Assistant exécuté, la boîte de dialogue **Propriétés de la base de données** s’affiche à nouveau, et l’adresse réseau du serveur du témoin apparaît désormais dans le champ **Témoin** .</span><span class="sxs-lookup"><span data-stu-id="e6bf6-131">On finishing, the wizard returns you to the **Database Properties** dialog box where the server network address of the witness now appears in **Witness** field.</span></span> <span data-ttu-id="e6bf6-132">En outre, l’option **Mode haute sécurité avec basculement automatique (synchrone)** , qui est nécessaire avec un témoin, est automatiquement sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e6bf6-132">Also, **High-safety mode with automatic failover (synchronous)**, which is required with a witness, is automatically selected.</span></span>  
  
     <span data-ttu-id="e6bf6-133">Pour activer le témoin et faire passer la session en mode haute sécurité avec basculement automatique, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6bf6-133">To enable the witness and change the session to high-safety mode with automatic failover, Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6bf6-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e6bf6-134">See Also</span></span>  
 <span data-ttu-id="e6bf6-135">[Témoin de mise en miroir de base de données](database-mirroring-witness.md) </span><span class="sxs-lookup"><span data-stu-id="e6bf6-135">[Database Mirroring Witness](database-mirroring-witness.md) </span></span>  
 <span data-ttu-id="e6bf6-136">[Mise en miroir de bases de données &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e6bf6-136">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="e6bf6-137">[Propriétés de la base de données &#40;page Mise en miroir&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="e6bf6-137">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="e6bf6-138">[Établir une session de mise en miroir de bases de données au moyen de l’authentification Windows &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="e6bf6-138">[Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md) </span></span>  
 [<span data-ttu-id="e6bf6-139">Témoin de mise en miroir de base de données</span><span class="sxs-lookup"><span data-stu-id="e6bf6-139">Database Mirroring Witness</span></span>](database-mirroring-witness.md)  
  
  
