---
title: Bases de données chiffrées avec groupes de disponibilité AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Transparent Data Encryption, AlwaysOn Availability Groups
- TDE, AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 09eb6ebc-3051-4fff-86a5-93524507b1fc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 91e717a896634a7df5a96253c51207831f142cff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601697"
---
# <a name="encrypted-databases-with-alwayson-availability-groups-sql-server"></a><span data-ttu-id="3dde5-102">Bases de données chiffrées avec groupes de disponibilité AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3dde5-102">Encrypted Databases with AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="3dde5-103">Cette rubrique contient des informations sur l'utilisation des bases de données actuellement chiffrées ou récemment déchiffrées avec [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3dde5-103">This topic contains information about the using currently encrypted or recently decrypted databases with [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="3dde5-104">**Dans cette rubrique :**</span><span class="sxs-lookup"><span data-stu-id="3dde5-104">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="3dde5-105">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="3dde5-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
-   [<span data-ttu-id="3dde5-106">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="3dde5-106">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="3dde5-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="3dde5-107">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="3dde5-108">Si une base de données est chiffrée ou même contient une clé de chiffrement de base de données (DEK), vous ne pouvez pas utiliser [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] ou [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] pour ajouter la base de données à un groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="3dde5-108">If a database is encrypted or even contains a Database Encryption Key (DEK), you cannot use the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] or [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] to add the database to an availability group.</span></span> <span data-ttu-id="3dde5-109">Même si une base de données chiffrée a été déchiffrée, ses sauvegardes de fichiers journaux peuvent contenir des données chiffrées.</span><span class="sxs-lookup"><span data-stu-id="3dde5-109">Even if an encrypted database has been decrypted, its log backups might contain encrypted data.</span></span> <span data-ttu-id="3dde5-110">Dans ce cas, la synchronisation complète initiale des données peut échouer sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="3dde5-110">In this case, full initial data synchronization could fail on the database.</span></span> <span data-ttu-id="3dde5-111">En effet, l'opération de journalisation de la restauration peut nécessiter le certificat utilisé par les clés de chiffrement de base de données (DEK), et le certificat peut être indisponible.</span><span class="sxs-lookup"><span data-stu-id="3dde5-111">This is because the restore log operation might require the certificate that was used by the database encryption keys (DEKs), and that certificate might be unavailable.</span></span>  
  
     <span data-ttu-id="3dde5-112">Pour qu'une base de données déchiffrée puisse être ajoutée à un groupe de disponibilité, à l'aide de l'Assistant :</span><span class="sxs-lookup"><span data-stu-id="3dde5-112">To make a decrypted database eligible to add to an availability group using the wizard:</span></span>  
  
    1.  <span data-ttu-id="3dde5-113">Créez une sauvegarde de fichier journal de la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="3dde5-113">Create a log backup of the primary database.</span></span>  
  
    2.  <span data-ttu-id="3dde5-114">Créez une sauvegarde complète de la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="3dde5-114">Create a full database backup of the primary database.</span></span>  
  
    3.  <span data-ttu-id="3dde5-115">Restaurez la sauvegarde de la base de données sur l'instance de serveur qui héberge le réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="3dde5-115">Restore the database backup on the server instance that hosts the secondary replica.</span></span>  
  
    4.  <span data-ttu-id="3dde5-116">Créez une nouvelle sauvegarde du journal de la base de données primaire.</span><span class="sxs-lookup"><span data-stu-id="3dde5-116">Create a new log backup from primary database.</span></span>  
  
    5.  <span data-ttu-id="3dde5-117">Restaurez cette sauvegarde de journal sur la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="3dde5-117">Restore this log backup on the secondary database.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="3dde5-118">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="3dde5-118">Related Tasks</span></span>  
  
-   [<span data-ttu-id="3dde5-119">Préparer manuellement une base de données secondaire pour un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3dde5-119">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="3dde5-120">Utiliser l’Assistant Groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3dde5-120">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="3dde5-121">Utiliser l’Assistant Ajouter une base de données au groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3dde5-121">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="3dde5-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3dde5-122">See Also</span></span>  
 <span data-ttu-id="3dde5-123">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3dde5-123">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="3dde5-124">Chiffrement transparent des données &#40;TDE&#41;</span><span class="sxs-lookup"><span data-stu-id="3dde5-124">Transparent Data Encryption &#40;TDE&#41;</span></span>](../../../relational-databases/security/encryption/transparent-data-encryption.md)  
  
  
