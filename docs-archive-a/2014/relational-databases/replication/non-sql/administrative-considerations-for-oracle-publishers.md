---
title: Considérations sur l’administration des serveurs de publication Oracle | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Oracle publishing [SQL Server replication], administrative considerations
- administering replication, Oracle publishing
ms.assetid: cfd81fb5-419b-4a1b-97c4-be7c9d4ee289
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3104b507987a4a236d39dd0ae1f8e3c29358c730
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612234"
---
# <a name="administrative-considerations-for-oracle-publishers"></a><span data-ttu-id="8e5da-102">Considérations sur l'administration des serveurs de publication Oracle</span><span class="sxs-lookup"><span data-stu-id="8e5da-102">Administrative Considerations for Oracle Publishers</span></span>
  <span data-ttu-id="8e5da-103">Quand un serveur de publication Oracle est configuré et que les mécanismes de suivi des modifications de la réplication sont en place, les administrateurs du système de base de données Oracle peuvent continuer à utiliser les utilitaires de base de données standard d'Oracle et à effectuer des tâches courantes d'administration du système.</span><span class="sxs-lookup"><span data-stu-id="8e5da-103">After an Oracle Publisher is configured and the replication change tracking mechanisms are in place, administrators of the Oracle database system can still use standard Oracle database utilities and perform typical system administration tasks.</span></span> <span data-ttu-id="8e5da-104">Cependant, il faut être attentif aux effets que peuvent avoir certaines tâches d'administration sur les données publiées.</span><span class="sxs-lookup"><span data-stu-id="8e5da-104">However, you should be aware of the effects on the published data of performing certain administrative tasks.</span></span>  
  
 <span data-ttu-id="8e5da-105">À l'exception de la suppression ou de la modification d'une colonne qui est publiée pour réplication, ou de la suppression ou de la modification de n'importe quel objet de réplication, ces considérations ne s'appliquent pas aux publications d'instantané.</span><span class="sxs-lookup"><span data-stu-id="8e5da-105">With the exception of dropping or modifying a column that is published for replication, or dropping or modifying any replication objects, these considerations do not apply to snapshot publications.</span></span>  
  
## <a name="importing-and-loading-data"></a><span data-ttu-id="8e5da-106">Importation et chargement de données</span><span class="sxs-lookup"><span data-stu-id="8e5da-106">Importing and loading data</span></span>  
 <span data-ttu-id="8e5da-107">Les déclencheurs sont utilisés dans le suivi des modifications pour les publications transactionnelles sur Oracle.</span><span class="sxs-lookup"><span data-stu-id="8e5da-107">Triggers are used in change tracking for transactional publications on Oracle.</span></span> <span data-ttu-id="8e5da-108">Les modifications apportées aux tables publiées peuvent être répliquées vers les Abonnés seulement si les déclencheurs de réplication s'exécutent quand une mise à jour, une insertion ou une suppression se produit.</span><span class="sxs-lookup"><span data-stu-id="8e5da-108">Changes to published tables can be replicated to Subscribers only if the replication triggers fire when an update, insert, or delete occurs.</span></span> <span data-ttu-id="8e5da-109">Les utilitaires Oracle Import et SQL\*Loader d'Oracle ont tous deux des options qui affectent l'activation des déclencheurs quand des lignes sont insérées dans des tables répliquées avec ces utilitaires.</span><span class="sxs-lookup"><span data-stu-id="8e5da-109">The Oracle utilities Oracle Import and SQL\*Loader both have options that affect whether triggers will fire when rows are inserted into replicated tables with these utilities.</span></span>  
  
### <a name="oracle-import"></a><span data-ttu-id="8e5da-110">Oracle Import</span><span class="sxs-lookup"><span data-stu-id="8e5da-110">Oracle Import</span></span>  
 <span data-ttu-id="8e5da-111">Avec Oracle Import, vous pouvez définir la valeur de l'option **ignore** à 'y' ou à 'n' (la valeur par défaut est 'n').</span><span class="sxs-lookup"><span data-stu-id="8e5da-111">With Oracle Import, you can set the option **ignore** to 'y' or 'n' (the default is 'n').</span></span> <span data-ttu-id="8e5da-112">Si **ignore** est définie à 'n', la table est supprimée et recréée lors de l'importation.</span><span class="sxs-lookup"><span data-stu-id="8e5da-112">If **ignore** is set to 'n', the table is dropped and re-created during import.</span></span> <span data-ttu-id="8e5da-113">Cela supprime les déclencheurs de réplication et désactive la réplication.</span><span class="sxs-lookup"><span data-stu-id="8e5da-113">This removes replication triggers and disables replication.</span></span> <span data-ttu-id="8e5da-114">Si **ignore** est définie à 'y', l'importation va tenter de charger les lignes dans la table existante, ce qui active les déclencheurs de réplication.</span><span class="sxs-lookup"><span data-stu-id="8e5da-114">If **ignore** is set to 'y', import will attempt to load the rows into the existing table, which fires the replication triggers.</span></span> <span data-ttu-id="8e5da-115">Par conséquent, vérifiez que **ignore** est défini à 'y' lors de l'importation dans une table répliquée avec l'outil Import.</span><span class="sxs-lookup"><span data-stu-id="8e5da-115">Therefore, ensure **ignore** is set to 'y' when importing into a replicated table with the Import tool.</span></span>  
  
### <a name="sqlloader"></a><span data-ttu-id="8e5da-116">SQL\*Loader</span><span class="sxs-lookup"><span data-stu-id="8e5da-116">SQL\*Loader</span></span>  
 <span data-ttu-id="8e5da-117">Avec SQL\*Loader, vous pouvez définir la valeur de l’option **direct** à ’True’ ou à ’False’ (la valeur par défaut est ’False’).</span><span class="sxs-lookup"><span data-stu-id="8e5da-117">With SQL\*Loader, you can set the option **direct** to 'true' or 'false' (the default is 'false').</span></span> <span data-ttu-id="8e5da-118">Si **direct** est définie à 'False', les lignes sont insérées à l'aide d'instructions INSERT conventionnelles, qui activent les déclencheurs de réplication.</span><span class="sxs-lookup"><span data-stu-id="8e5da-118">If **direct** is set to 'false', rows are inserted using conventional INSERT statements, which fire replication triggers.</span></span> <span data-ttu-id="8e5da-119">Si **direct** est définie à 'True', la charge est optimisée et les déclencheurs ne sont pas activés.</span><span class="sxs-lookup"><span data-stu-id="8e5da-119">If **direct** is set to 'true', the load is optimized, and triggers are not fired.</span></span> <span data-ttu-id="8e5da-120">Par conséquent, vérifiez que **direct** est définie à 'False' lors du chargement dans une table répliquée avec l'outil SQL\*Loader.</span><span class="sxs-lookup"><span data-stu-id="8e5da-120">Therefore, ensure **direct** is set to 'false' when loading into a replicated table with the SQL\*Loader tool.</span></span>  
  
## <a name="making-changes-to-published-objects"></a><span data-ttu-id="8e5da-121">Modifications d'objets publiés</span><span class="sxs-lookup"><span data-stu-id="8e5da-121">Making changes to published objects</span></span>  
 <span data-ttu-id="8e5da-122">Les actions suivantes ne requièrent pas de considérations particulières :</span><span class="sxs-lookup"><span data-stu-id="8e5da-122">The following actions require no special considerations:</span></span>  
  
-   <span data-ttu-id="8e5da-123">Reconstruction d'index sur des tables publiées.</span><span class="sxs-lookup"><span data-stu-id="8e5da-123">Rebuilding indexes on published tables.</span></span>  
  
-   <span data-ttu-id="8e5da-124">Ajout de déclencheurs de l'utilisateur à une table publiée.</span><span class="sxs-lookup"><span data-stu-id="8e5da-124">Adding user triggers to a published table.</span></span>  
  
 <span data-ttu-id="8e5da-125">L'action suivante nécessite l'arrêt de toutes les activités sur les tables publiées :</span><span class="sxs-lookup"><span data-stu-id="8e5da-125">The following action requires you to stop all activity on the published tables:</span></span>  
  
-   <span data-ttu-id="8e5da-126">Déplacement d'une table publiée.</span><span class="sxs-lookup"><span data-stu-id="8e5da-126">Moving a published table.</span></span>  
  
 <span data-ttu-id="8e5da-127">Les actions suivantes nécessitent la suppression de la publication, la réalisation de l'opération, puis la recréation de la publication :</span><span class="sxs-lookup"><span data-stu-id="8e5da-127">The following actions require you to drop the publication, perform the operation, and then recreate the publication:</span></span>  
  
-   <span data-ttu-id="8e5da-128">Troncation d'une table publiée.</span><span class="sxs-lookup"><span data-stu-id="8e5da-128">Truncating a published table.</span></span>  
  
-   <span data-ttu-id="8e5da-129">Renommage d'une table publiée.</span><span class="sxs-lookup"><span data-stu-id="8e5da-129">Renaming a published table.</span></span>  
  
-   <span data-ttu-id="8e5da-130">Ajout d'une colonne à une table publiée.</span><span class="sxs-lookup"><span data-stu-id="8e5da-130">Adding a column to a published table.</span></span>  
  
-   <span data-ttu-id="8e5da-131">Ajout ou modification d'une colonne qui est publiée pour réplication.</span><span class="sxs-lookup"><span data-stu-id="8e5da-131">Dropping or modifying a column that is published for replication.</span></span>  
  
-   <span data-ttu-id="8e5da-132">Réalisation d'opérations sans journalisation.</span><span class="sxs-lookup"><span data-stu-id="8e5da-132">Performing non-logged operations.</span></span>  
  
## <a name="dropping-or-modifying-replication-objects"></a><span data-ttu-id="8e5da-133">Suppression ou modification d'objets de réplication</span><span class="sxs-lookup"><span data-stu-id="8e5da-133">Dropping or modifying replication objects</span></span>  
 <span data-ttu-id="8e5da-134">Vous devez supprimer et reconfigurer le serveur de publication si vous supprimez ou si vous modifiez des tables, des déclencheurs, des séquences ou des procédures stockées de suivi au niveau d'un serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="8e5da-134">You must drop and reconfigure the Publisher if you drop or modify any Publisher level tracking tables, triggers, sequences, or stored procedures.</span></span> <span data-ttu-id="8e5da-135">Pour obtenir une liste partielle de ces objets, consultez [Objets créés sur le serveur de publication Oracle](objects-created-on-the-oracle-publisher.md).</span><span class="sxs-lookup"><span data-stu-id="8e5da-135">For a partial list of these objects, see [Objects Created on the Oracle Publisher](objects-created-on-the-oracle-publisher.md).</span></span>  
  
 <span data-ttu-id="8e5da-136">Pour des informations sur la suppression et la reconfiguration du serveur de publication, consultez la section « Des modifications sont effectuées et nécessitent la reconfiguration du serveur de publication » dans la rubrique [Troubleshooting Oracle Publishers](troubleshooting-oracle-publishers.md).</span><span class="sxs-lookup"><span data-stu-id="8e5da-136">For information about dropping and reconfiguring the Publisher, see the section "Changes are made that require reconfiguration of the Publisher" in the topic [Troubleshooting Oracle Publishers](troubleshooting-oracle-publishers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e5da-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8e5da-137">See Also</span></span>  
 <span data-ttu-id="8e5da-138">[Configurer un serveur de publication Oracle](configure-an-oracle-publisher.md) </span><span class="sxs-lookup"><span data-stu-id="8e5da-138">[Configure an Oracle Publisher](configure-an-oracle-publisher.md) </span></span>  
 <span data-ttu-id="8e5da-139">[Problèmes et limitations de conception des serveurs de publication Oracle](design-considerations-and-limitations-for-oracle-publishers.md) </span><span class="sxs-lookup"><span data-stu-id="8e5da-139">[Design Considerations and Limitations for Oracle Publishers](design-considerations-and-limitations-for-oracle-publishers.md) </span></span>  
 [<span data-ttu-id="8e5da-140">Vue d’ensemble de la publication Oracle</span><span class="sxs-lookup"><span data-stu-id="8e5da-140">Oracle Publishing Overview</span></span>](oracle-publishing-overview.md)  
  
  
