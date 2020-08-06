---
title: Comptes de service (Assistant Configuration de la sécurité de la mise en miroir de bases de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.serviceaccounts.f1
ms.assetid: d58d8f93-7888-4d66-af4d-969ef6a2dbee
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 58e49467a28e816c6592b1ded212b5aea0e6bc55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701771"
---
# <a name="service-accounts-configure-database-mirroring-security-wizard"></a><span data-ttu-id="6edee-102">Comptes de service (Assistant Configuration de la sécurité de la mise en miroir de bases de données)</span><span class="sxs-lookup"><span data-stu-id="6edee-102">Service Accounts (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="6edee-103">Lors de l'utilisation de l'authentification Windows, si les instances de serveur utilisent des comptes différents, spécifiez les comptes de service pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6edee-103">When using Windows Authentication, if the server instances use different accounts, specify the service accounts for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6edee-104">Ces comptes de service doivent tous être des comptes de domaine (dans les mêmes domaines ou des domaines approuvés).</span><span class="sxs-lookup"><span data-stu-id="6edee-104">These service accounts must all be domain accounts (in the same or trusted domains).</span></span>  
  
 <span data-ttu-id="6edee-105">Si toutes les instances de serveur utilisent le même compte de domaine ou une authentification basée sur les certificats, laissez les champs vides.</span><span class="sxs-lookup"><span data-stu-id="6edee-105">If all the server instances use the same domain account or use certificate-based authentication, leave the fields blank.</span></span> <span data-ttu-id="6edee-106">Cliquez simplement sur **Terminer**; l'Assistant configure alors automatiquement les comptes en fonction du compte de l'Assistant actuel.</span><span class="sxs-lookup"><span data-stu-id="6edee-106">Simply click **Finish**, and the wizard automatically configures the accounts based on the account of the current wizard.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6edee-107">Si les points de terminaison de mise en miroir de base de données des instances de serveur sont configurés pour utiliser des certificats, vous devez laisser les champs de compte de service vides.</span><span class="sxs-lookup"><span data-stu-id="6edee-107">If the database mirroring endpoints of the server instances are configured to use certificates, you must leave the service account fields empty.</span></span>  
  
 <span data-ttu-id="6edee-108">**Pour configurer la mise en miroir de bases de données à l'aide de SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="6edee-108">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="6edee-109">Établir une session de mise en miroir de bases de données au moyen de l’authentification Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6edee-109">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="6edee-110">Démarrer l’Assistant Configuration de la sécurité de mise en miroir de bases de données &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6edee-110">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="6edee-111">Options</span><span class="sxs-lookup"><span data-stu-id="6edee-111">Options</span></span>  
 <span data-ttu-id="6edee-112">**Principal**</span><span class="sxs-lookup"><span data-stu-id="6edee-112">**Principal**</span></span>  
 <span data-ttu-id="6edee-113">Permet de spécifier le compte de service de l'instance de serveur principal.</span><span class="sxs-lookup"><span data-stu-id="6edee-113">Specify the service account of the principal server instance.</span></span> <span data-ttu-id="6edee-114">Entrez le nom du domaine en majuscules :</span><span class="sxs-lookup"><span data-stu-id="6edee-114">Enter the domain name in upper case:</span></span>  
  
 <span data-ttu-id="6edee-115">*Nom_domaine* \\ *nom d’utilisateur*</span><span class="sxs-lookup"><span data-stu-id="6edee-115">*DOMAINNAME*\\*username*</span></span>  
  
 <span data-ttu-id="6edee-116">**Miroir**</span><span class="sxs-lookup"><span data-stu-id="6edee-116">**Mirror**</span></span>  
 <span data-ttu-id="6edee-117">Permet de spécifier le compte de service de l'instance de serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="6edee-117">Specify the service account of the mirror server instance.</span></span> <span data-ttu-id="6edee-118">Entrez le nom du domaine en majuscules :</span><span class="sxs-lookup"><span data-stu-id="6edee-118">Enter the domain name in upper case:</span></span>  
  
 <span data-ttu-id="6edee-119">*Nom_domaine* \\ *nom d’utilisateur*</span><span class="sxs-lookup"><span data-stu-id="6edee-119">*DOMAINNAME*\\*username*</span></span>  
  
 <span data-ttu-id="6edee-120">**Foi**</span><span class="sxs-lookup"><span data-stu-id="6edee-120">**Witness**</span></span>  
 <span data-ttu-id="6edee-121">Permet de spécifier le compte de service de l'instance de serveur témoin.</span><span class="sxs-lookup"><span data-stu-id="6edee-121">Specify the service account of the witness server instance.</span></span> <span data-ttu-id="6edee-122">Entrez le nom du domaine en majuscules :</span><span class="sxs-lookup"><span data-stu-id="6edee-122">Enter the domain name in upper case:</span></span>  
  
 <span data-ttu-id="6edee-123">*Nom_domaine* \\ *nom d’utilisateur*</span><span class="sxs-lookup"><span data-stu-id="6edee-123">*DOMAINNAME*\\*username*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6edee-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6edee-124">See Also</span></span>  
 <span data-ttu-id="6edee-125">[Propriétés de la base de données &#40;page Mise en miroir&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="6edee-125">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="6edee-126">[Démarrer le moniteur de mise en miroir de bases de données &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="6edee-126">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="6edee-127">[Mise en miroir de bases de données &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6edee-127">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="6edee-128">Configurer des comptes de connexion pour la mise en miroir de bases de données ou groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6edee-128">Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](set-up-login-accounts-database-mirroring-always-on-availability.md)  
  
  
