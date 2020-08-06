---
title: Propriétés générales | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- IdleConnectionTimeout property
- InstanceVisible property
- TempDir property
- AdminTimeout property
- MinIdleSessionTimeout property
- MaxIdleSessionTimeout property
- IdleOrphanSessionTimeout property
- BackupDir property
- CommitTimeout property
- ExternalCommandTimeout property
- Enabled property
- ForceCommitTimeout property
- Port property
- CoordinatorShutdownMode property
- ServerTimeout property
- AllowedBrowsingFolders property
- CoordinatorCancelCount property
- DataDir property
- CoordinatorQueryMaxThreads property
- CoordinatorExecutionMode property
- ExternalConnectionTimeout property
- CollationName property
- EnableFast1033Locale property
- CoordinatorBuildMaxThreads property
- Language property
- StatisticsStoreSize property
- RepositoryConnectionString property
ms.assetid: 88a8117c-396a-469f-a62d-c6f262504021
author: minewiskan
ms.author: owend
ms.openlocfilehash: ca746a1bb57e84cf0f6a8f47622b118c7180eb1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710859"
---
# <a name="general-properties"></a><span data-ttu-id="2e94b-102">Propriétés générales</span><span class="sxs-lookup"><span data-stu-id="2e94b-102">General Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="2e94b-103">prend en charge les propriétés de serveur répertoriées dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="2e94b-103">supports the server properties listed in the following tables.</span></span> <span data-ttu-id="2e94b-104">Cette rubrique décrit les propriétés de serveur qui se trouvent dans le fichier msmdsrv.ini et qui ne font pas l'objet d'une section spécifique, traitant par exemple de la sécurité, du réseau ou de ThreadPool.</span><span class="sxs-lookup"><span data-stu-id="2e94b-104">This topic documents those server properties in the msmdsrv.ini file that are not otherwise included in a specific section, such as Security, Network, or ThreadPool.</span></span> <span data-ttu-id="2e94b-105">Pour plus d'informations sur les autres propriétés de serveur et la façon de les configurer, consultez [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="2e94b-105">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="2e94b-106">**S’applique à :** mode serveur multidimensionnel et tabulaire, sauf indication contraire</span><span class="sxs-lookup"><span data-stu-id="2e94b-106">**Applies to:** Multidimensional and Tabular server mode, unless noted otherwise</span></span>  
  
## <a name="non-specific-category"></a><span data-ttu-id="2e94b-107">Catégorie non spécifique</span><span class="sxs-lookup"><span data-stu-id="2e94b-107">Non-Specific Category</span></span>  
 `AdminTimeout`  
 <span data-ttu-id="2e94b-108">Propriété dont la valeur est un entier 32 bits signé qui définit le délai d'attente de l'administrateur en secondes.</span><span class="sxs-lookup"><span data-stu-id="2e94b-108">A signed 32-bit integer property that defines the administrator timeout in seconds.</span></span> <span data-ttu-id="2e94b-109">Il s'agit d'une propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2e94b-109">This is an advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="2e94b-110">La valeur par défaut de cette propriété, zéro (0), indique l'absence de délai d'attente.</span><span class="sxs-lookup"><span data-stu-id="2e94b-110">The default value for this property is zero (0), which indicates there is no timeout.</span></span>  
  
 `AllowedBrowsingFolders`  
 <span data-ttu-id="2e94b-111">Propriété de type chaîne qui spécifie dans une liste délimitée les dossiers qui peuvent être parcourus en enregistrant, en ouvrant, puis en recherchant les fichiers dans les boîtes de dialogue Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="2e94b-111">A string property that specifies in a delimited list the folders that can be browsed when saving, opening, and finding files in Analysis Services dialog boxes.</span></span> <span data-ttu-id="2e94b-112">Le compte de service Analysis Services doit disposer d'autorisations de lecture et d'écriture sur tous les dossiers que vous ajoutez à la liste.</span><span class="sxs-lookup"><span data-stu-id="2e94b-112">The Analysis Services service account must have read and write permissions to any folders that you add to the list.</span></span>  
  
 `BackupDir`  
 <span data-ttu-id="2e94b-113">Propriété de type chaîne qui identifie le nom du répertoire dans lequel les fichiers de sauvegarde sont stockés par défaut, dans le cas où aucun chemin d’accès n’est spécifié dans le cadre de la commande de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="2e94b-113">A string property that identifies the name of the directory where backup files are stored by default, in the event a path is not specified as part of the Backup command.</span></span>  
  
 `CollationName`  
 <span data-ttu-id="2e94b-114">Propriété de type chaîne qui identifie le classement du serveur.</span><span class="sxs-lookup"><span data-stu-id="2e94b-114">A string property that identifies the server collation.</span></span> <span data-ttu-id="2e94b-115">Pour plus d’informations, consultez [Langues et classements &#40;Analysis Services&#41;](../languages-and-collations-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="2e94b-115">For more information, see [Languages and Collations &#40;Analysis Services&#41;](../languages-and-collations-analysis-services.md).</span></span>  
  
 `CommitTimeout`  
 <span data-ttu-id="2e94b-116">Propriété dont la valeur est un entier qui spécifie le temps (en millisecondes) pendant lequel le serveur attend pour acquérir un verrou d'écriture afin de valider une transaction.</span><span class="sxs-lookup"><span data-stu-id="2e94b-116">An integer property that specifies how long (in milliseconds) the server will wait to acquire a write lock for the purpose of committing a transaction.</span></span> <span data-ttu-id="2e94b-117">Une période d'attente est souvent nécessaire, car le serveur doit attendre la libération d'autres verrous avant de pouvoir accepter un verrou d'écriture qui valide la transaction.</span><span class="sxs-lookup"><span data-stu-id="2e94b-117">A waiting period is often required because the server must wait for other locks to be released before it can take a write lock that commits the transaction.</span></span>  
  
 <span data-ttu-id="2e94b-118">La valeur par défaut de cette propriété, zéro (0), indique que le serveur attend indéfiniment.</span><span class="sxs-lookup"><span data-stu-id="2e94b-118">The default value for this property is zero (0), which indicates that the server will wait indefinitely.</span></span> <span data-ttu-id="2e94b-119">Pour plus d’informations sur les propriétés associées au verrou, consultez le [guide des opérations de SQL Server 2008 R2 Analysis Services](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="2e94b-119">For more information about lock-related properties, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
 `CoordinatorBuildMaxThreads`  
 <span data-ttu-id="2e94b-120">Propriété dont la valeur est un entier 32 bits signé qui spécifie le nombre maximal de threads alloués à la génération des index de partition.</span><span class="sxs-lookup"><span data-stu-id="2e94b-120">A signed 32-bit integer property that defines the maximum number of threads allocated to building partition indexes.</span></span> <span data-ttu-id="2e94b-121">Augmentez cette valeur si vous souhaitez accélérer l'indexation des partitions au prix d'une plus grande consommation de mémoire.</span><span class="sxs-lookup"><span data-stu-id="2e94b-121">Increase this value in order to speed-up partition indexing, at the cost of memory usage.</span></span> <span data-ttu-id="2e94b-122">Pour plus d’informations sur cette propriété, consultez le [guide des opérations de SQL Server 2008 R2 Analysis Services](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="2e94b-122">For more information about this property, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
 `CoordinatorCancelCount`  
 <span data-ttu-id="2e94b-123">Propriété dont la valeur est un entier 32 bits signé qui spécifie la fréquence selon laquelle le serveur doit vérifier si un événement d'annulation s'est produit (en fonction d'un nombre d'itérations interne).</span><span class="sxs-lookup"><span data-stu-id="2e94b-123">A signed 32-bit integer property that defines how frequently the server should check whether a Cancel event occurred (based on internal iteration count).</span></span> <span data-ttu-id="2e94b-124">Diminuez ce nombre si vous souhaitez augmenter la fréquence de ces vérifications au détriment des performances générales.</span><span class="sxs-lookup"><span data-stu-id="2e94b-124">Decrease this number in order to check for Cancel more frequently, at the expense of general performance.</span></span>  
  
 <span data-ttu-id="2e94b-125">`CoordinatorCancelCount` est ignoré en mode serveur tabulaire.</span><span class="sxs-lookup"><span data-stu-id="2e94b-125">`CoordinatorCancelCount` is ignored in tabular server mode.</span></span>  
  
 `CoordinatorExecutionMode`  
 <span data-ttu-id="2e94b-126">Propriété dont la valeur est un entier 32 bits signé qui spécifie le nombre maximal d'opérations parallèles que le serveur essaiera d'effectuer, notamment les opérations de traitement et d'interrogation.</span><span class="sxs-lookup"><span data-stu-id="2e94b-126">A signed 32-bit integer property that defines the maximum number of parallel operations the server will attempt, including processing and querying operations.</span></span> <span data-ttu-id="2e94b-127">Zéro (0) indique que le serveur décidera lui-même, en fonction d'un algorithme interne.</span><span class="sxs-lookup"><span data-stu-id="2e94b-127">Zero (0) indicates that the server will decide, based on an internal algorithm.</span></span> <span data-ttu-id="2e94b-128">Un nombre positif indique le nombre maximal d'opérations au total.</span><span class="sxs-lookup"><span data-stu-id="2e94b-128">A positive number indicates the maximum number of operations in total.</span></span> <span data-ttu-id="2e94b-129">Un nombre négatif (précédé du signe moins) indique le nombre maximal d'opérations par processeur.</span><span class="sxs-lookup"><span data-stu-id="2e94b-129">A negative number, with the sign reversed, indicates the maximum number of operations per processor.</span></span>  
  
 <span data-ttu-id="2e94b-130">`CoordinatorExecutionMode` est ignoré en mode serveur tabulaire.</span><span class="sxs-lookup"><span data-stu-id="2e94b-130">`CoordinatorExecutionMode` is ignored in tabular server mode.</span></span>  
  
 <span data-ttu-id="2e94b-131">La valeur par défaut de cette propriété, -4, indique que le serveur est limité à quatre opérations parallèles par processeur.</span><span class="sxs-lookup"><span data-stu-id="2e94b-131">The default value for this property is -4, which indicates the server is limited to 4 parallel operations per processor.</span></span> <span data-ttu-id="2e94b-132">Pour plus d’informations sur cette propriété, consultez le [guide des opérations de SQL Server 2008 R2 Analysis Services](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="2e94b-132">For more information about this property, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
 `CoordinatorQueryMaxThreads`  
 <span data-ttu-id="2e94b-133">Propriété dont la valeur est un entier 32 bits signé qui spécifie le nombre maximal de threads par segment de partition durant la résolution des requêtes.</span><span class="sxs-lookup"><span data-stu-id="2e94b-133">A signed 32-bit integer property that defines the maximum number of threads per partition segment during query resolution.</span></span> <span data-ttu-id="2e94b-134">Moins il y a d'utilisateurs simultanés, plus cette valeur peut être élevée, au prix d'une plus grande consommation de mémoire.</span><span class="sxs-lookup"><span data-stu-id="2e94b-134">The fewer the number of concurrent users, the higher this value can be, at the cost of memory.</span></span> <span data-ttu-id="2e94b-135">Inversement, il peut s'avérer nécessaire de diminuer cette valeur s'il y a un grand nombre d'utilisateurs simultanés.</span><span class="sxs-lookup"><span data-stu-id="2e94b-135">Conversely, it may need to be lowered if there are a large number of concurrent users.</span></span>  
  
 `CoordinatorShutdownMode`  
 <span data-ttu-id="2e94b-136">Propriété booléenne qui définit le mode d'arrêt du coordinateur.</span><span class="sxs-lookup"><span data-stu-id="2e94b-136">A Boolean property that defines coordinator shutdown mode.</span></span> <span data-ttu-id="2e94b-137">Il s'agit d'une propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2e94b-137">This is an advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataDir`  
 <span data-ttu-id="2e94b-138">Propriété de type chaîne qui spécifie le nom du répertoire où les données sont stockées.</span><span class="sxs-lookup"><span data-stu-id="2e94b-138">A string property that identifies the name of the directory where data is stored.</span></span>  
  
 `DeploymentMode`  
 <span data-ttu-id="2e94b-139">Détermine le contexte opérationnel d'une instance de serveur Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="2e94b-139">Determines the operational context of an Analysis Services server instance.</span></span> <span data-ttu-id="2e94b-140">Cette propriété est appelée « mode serveur » dans les boîtes de dialogue, les messages et la documentation.</span><span class="sxs-lookup"><span data-stu-id="2e94b-140">This property is referred to as 'server mode' in dialog boxes, messages, and documentation.</span></span> <span data-ttu-id="2e94b-141">Cette propriété est configurée par le programme d'installation de SQL Server selon le mode serveur que vous avez sélectionné en installant Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="2e94b-141">This property is configured by SQL Server Setup based on the server mode you selected when installing Analysis Services.</span></span> <span data-ttu-id="2e94b-142">Cette propriété doit être considérée uniquement comme une propriété interne, toujours à l'aide de la valeur spécifiée par le programme d'installation.</span><span class="sxs-lookup"><span data-stu-id="2e94b-142">This property should be considered internal only, always using the value specified by Setup.</span></span>  
  
 <span data-ttu-id="2e94b-143">Les valeurs valides pour cette propriété sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="2e94b-143">Valid values for this property include the following:</span></span>  
  
|<span data-ttu-id="2e94b-144">Valeur</span><span class="sxs-lookup"><span data-stu-id="2e94b-144">Value</span></span>|<span data-ttu-id="2e94b-145">Description</span><span class="sxs-lookup"><span data-stu-id="2e94b-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2e94b-146">0</span><span class="sxs-lookup"><span data-stu-id="2e94b-146">0</span></span>|<span data-ttu-id="2e94b-147">Valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="2e94b-147">This is the default value.</span></span> <span data-ttu-id="2e94b-148">Elle spécifie le mode multidimensionnel, utilisé pour servir les bases de données multidimensionnelles qui utilisent le stockage MOLAP, HOLAP et ROLAP, ainsi que les modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="2e94b-148">It specifies multidimensional mode, used to service multidimensional databases that use MOLAP, HOLAP, and ROLAP storage, as well as data mining models.</span></span>|  
|<span data-ttu-id="2e94b-149">1</span><span class="sxs-lookup"><span data-stu-id="2e94b-149">1</span></span>|<span data-ttu-id="2e94b-150">Spécifie des instances d'Analysis Services installées dans le cadre d'un déploiement PowerPivot pour SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2e94b-150">Specifies Analysis Services instances that were installed as part of a PowerPivot for SharePoint deployment.</span></span> <span data-ttu-id="2e94b-151">Ne modifiez pas la propriété du mode de déploiement de l'instance Analysis Services qui fait partie d'une installation PowerPivot pour SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2e94b-151">Do not change the deployment mode property of Analysis Services instance that is part of a PowerPivot for SharePoint installation.</span></span> <span data-ttu-id="2e94b-152">Les données PowerPivot ne s'exécuteront plus sur le serveur si vous modifiez le mode.</span><span class="sxs-lookup"><span data-stu-id="2e94b-152">PowerPivot data will no longer run on the server if you change the mode.</span></span>|  
|<span data-ttu-id="2e94b-153">2</span><span class="sxs-lookup"><span data-stu-id="2e94b-153">2</span></span>|<span data-ttu-id="2e94b-154">Spécifie le mode tabulaire utilisé pour héberger les bases de données model tabulaires qui utilisent le stockage en mémoire ou le stockage DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="2e94b-154">Specifies Tabular mode used for hosting tabular model databases that use in-memory storage or DirectQuery storage.</span></span>|  
  
 <span data-ttu-id="2e94b-155">Chaque mode est exclusif pour l'autre.</span><span class="sxs-lookup"><span data-stu-id="2e94b-155">Each mode is exclusive of the other.</span></span> <span data-ttu-id="2e94b-156">Un serveur configuré pour le mode tabulaire ne peut pas exécuter des bases de données Analysis Services qui contiennent des cubes et des dimensions.</span><span class="sxs-lookup"><span data-stu-id="2e94b-156">A server that is configured for tabular mode cannot run Analysis Services databases that contain cubes and dimensions.</span></span> <span data-ttu-id="2e94b-157">Si le matériel informatique sous-jacent peut prendre cela en charge, vous pouvez installer plusieurs instances d'Analysis Services sur le même ordinateur et configurer chaque instance pour utiliser un mode de déploiement différent.</span><span class="sxs-lookup"><span data-stu-id="2e94b-157">If the underlying computer hardware can support it, you can install multiple instances of Analysis Services on the same computer and configure each instance to use a different deployment mode.</span></span> <span data-ttu-id="2e94b-158">Souvenez-vous qu'Analysis Services est une application qui consommée beaucoup de ressources.</span><span class="sxs-lookup"><span data-stu-id="2e94b-158">Remember that Analysis Services is a resource intensive application.</span></span> <span data-ttu-id="2e94b-159">Le déploiement de plusieurs instances sur le même système est recommandé uniquement pour les serveurs haut de gamme.</span><span class="sxs-lookup"><span data-stu-id="2e94b-159">Deploying multiple instances on the same system is recommended only for high-end servers.</span></span>  
  
 `EnableFast1033Locale`  
 <span data-ttu-id="2e94b-160">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2e94b-160">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ExternalCommandTimeout`  
 <span data-ttu-id="2e94b-161">Propriété dont la valeur est un entier qui spécifie le délai d'attente en secondes des commandes envoyées aux serveurs externes, notamment les sources de données relationnelles et les serveurs [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] externes.</span><span class="sxs-lookup"><span data-stu-id="2e94b-161">An integer property that defines the timeout, in seconds, for commands issued to external servers, including relational data sources and external [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] servers.</span></span>  
  
 <span data-ttu-id="2e94b-162">La valeur par défaut de cette propriété est 3600 (secondes).</span><span class="sxs-lookup"><span data-stu-id="2e94b-162">The default value for this property is 3600 (seconds).</span></span>  
  
 `ExternalConnectionTimeout`  
 <span data-ttu-id="2e94b-163">Propriété dont la valeur est un entier qui spécifie le délai d’attente en secondes de la création des connexions aux serveurs externes, notamment les sources de données relationnelles et les serveurs [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] externes.</span><span class="sxs-lookup"><span data-stu-id="2e94b-163">An integer property that defines the timeout, in seconds, for creating connections to external servers, including relational data sources and external [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] servers.</span></span> <span data-ttu-id="2e94b-164">Cette propriété est ignorée si un délai de connexion est spécifié dans la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="2e94b-164">This property is ignored if a connection timeout is specified on the connection string.</span></span>  
  
 <span data-ttu-id="2e94b-165">La valeur par défaut de cette propriété est 60 (secondes).</span><span class="sxs-lookup"><span data-stu-id="2e94b-165">The default value for this property is 60 (seconds).</span></span>  
  
 `ForceCommitTimeout`  
 <span data-ttu-id="2e94b-166">Propriété dont la valeur est un entier qui spécifie le temps, en millisecondes, pendant lequel une opération de validation d'écriture doit attendre avant l'annulation d'autres commandes qui ont précédé la commande actuelle, notamment les requêtes en cours.</span><span class="sxs-lookup"><span data-stu-id="2e94b-166">An integer property that specifies how long, in milliseconds, a write commit operation should wait before canceling other commands that preceded the current command, including queries in progress.</span></span> <span data-ttu-id="2e94b-167">Cela permet à la transaction de validation de continuer en annulant les opérations de priorité la plus faible, telles que les requêtes.</span><span class="sxs-lookup"><span data-stu-id="2e94b-167">This allows the commit transaction to proceed by canceling lower priority operations, such as queries.</span></span>  
  
 <span data-ttu-id="2e94b-168">La valeur par défaut de cette propriété, 30 secondes (30 000 millisecondes), indique que l'annulation d'autres commandes ne sera pas forcée tant que la transaction de validation n'a pas attendu 30 secondes.</span><span class="sxs-lookup"><span data-stu-id="2e94b-168">The default value for this property is 30 seconds (30000 milliseconds), which indicates that other commands will not be forced to timeout until the commit transaction has been waiting for 30 seconds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2e94b-169">Les requêtes et les processus annulés par cet événement entraînent l’affichage du message d’erreur suivant : «`Server: The operation has been cancelled`».</span><span class="sxs-lookup"><span data-stu-id="2e94b-169">Queries and processes cancelled by this event will report the following error message: "`Server: The operation has been cancelled`"</span></span>  
  
 <span data-ttu-id="2e94b-170">Pour plus d’informations sur cette propriété, consultez le [guide des opérations de SQL Server 2008 R2 Analysis Services](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="2e94b-170">For more information about this property, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2e94b-171">`ForceCommitTimeout` s'applique aux commandes de traitement de cube et aux opérations d'écriture différée.</span><span class="sxs-lookup"><span data-stu-id="2e94b-171">`ForceCommitTimeout` applies to cube processing commands and to writeback operations.</span></span>  
  
 `IdleConnectionTimeout`  
 <span data-ttu-id="2e94b-172">Propriété dont la valeur est un entier qui spécifie le délai, en secondes, pour les connexions qui sont inactives.</span><span class="sxs-lookup"><span data-stu-id="2e94b-172">An integer property that specifies a timeout, in seconds, for connections that are inactive.</span></span>  
  
 <span data-ttu-id="2e94b-173">La valeur par défaut de cette propriété, zéro (0), indique que le serveur ne ferme pas les connexions inactives.</span><span class="sxs-lookup"><span data-stu-id="2e94b-173">The default value for this property is zero (0), which indicates that idle connections will not be timed out.</span></span>  
  
 `IdleOrphanSessionTimeout`  
 <span data-ttu-id="2e94b-174">Propriété dont la valeur est un entier qui définit le laps de temps, exprimé en secondes, pendant lequel les sessions orphelines sont conservées dans la mémoire du serveur.</span><span class="sxs-lookup"><span data-stu-id="2e94b-174">An integer property that defines how long, in seconds, orphaned sessions will be retained in server memory.</span></span> <span data-ttu-id="2e94b-175">Une session orpheline est une session qui n'a plus de connexion associée.</span><span class="sxs-lookup"><span data-stu-id="2e94b-175">An orphaned session is one that no longer has an associated connection.</span></span> <span data-ttu-id="2e94b-176">La valeur par défaut est 120 secondes.</span><span class="sxs-lookup"><span data-stu-id="2e94b-176">The default is 120 seconds.</span></span>  
  
 `InstanceVisible`  
 <span data-ttu-id="2e94b-177">Propriété booléenne qui indique si l'instance de serveur est visible pour découvrir des demandes d'instance de service SQL Server Browser.</span><span class="sxs-lookup"><span data-stu-id="2e94b-177">A Boolean property that indicates whether the server instance is visible to discover instance requests from SQL Server Browser service.</span></span> <span data-ttu-id="2e94b-178">La valeur par défaut est True.</span><span class="sxs-lookup"><span data-stu-id="2e94b-178">The default is True.</span></span> <span data-ttu-id="2e94b-179">Si vous affectez la valeur False, l'instance n'est pas visible pour SQL Server Browser.</span><span class="sxs-lookup"><span data-stu-id="2e94b-179">If you set it to false, the instance is not visible to SQL Server Browser.</span></span>  
  
 `Language`  
 <span data-ttu-id="2e94b-180">Propriété de type chaîne qui définit la langue, notamment pour les messages d'erreur et la mise en forme des nombres.</span><span class="sxs-lookup"><span data-stu-id="2e94b-180">A string property that defines the language, including error messages and number formatting.</span></span> <span data-ttu-id="2e94b-181">Cette propriété a priorité sur la propriété CollationName.</span><span class="sxs-lookup"><span data-stu-id="2e94b-181">This property overrides the CollationName property.</span></span>  
  
 <span data-ttu-id="2e94b-182">La valeur par défaut de cette propriété est vide, ce qui indique que la langue est définie par la propriété CollationName.</span><span class="sxs-lookup"><span data-stu-id="2e94b-182">The default value for this property is blank, which indicates that the CollationName property defines the language.</span></span>  
  
 `LogDir`  
 <span data-ttu-id="2e94b-183">Propriété de type chaîne qui spécifie le nom du répertoire qui contient les journaux du serveur.</span><span class="sxs-lookup"><span data-stu-id="2e94b-183">A string property that identifies the name of the directory that contains server logs.</span></span> <span data-ttu-id="2e94b-184">Cette propriété s'applique uniquement si vous utilisez des fichiers sur disque pour l'enregistrement, au lieu de tables de base de données (comportement par défaut).</span><span class="sxs-lookup"><span data-stu-id="2e94b-184">This property only applies when disk files are used for logging, as opposed to database tables (the default behavior).</span></span>  
  
 `MaxIdleSessionTimeout`  
 <span data-ttu-id="2e94b-185">Propriété dont la valeur est un entier qui définit le délai d'attente maximal des sessions inactives, exprimé en secondes.</span><span class="sxs-lookup"><span data-stu-id="2e94b-185">An integer property that defines the maximum idle session timeout, in seconds.</span></span> <span data-ttu-id="2e94b-186">La valeur par défaut est zéro (0), ce qui indique que les sessions n’ont jamais dépassé le délai d’attente. Toutefois, les sessions inactives seront quand même supprimées si le serveur est soumis à des contraintes de ressources.</span><span class="sxs-lookup"><span data-stu-id="2e94b-186">The default is zero (0), indicating that sessions are never timed out. However, idle sessions will still be removed if the server is under resource constraints.</span></span>  
  
 `MinIdleSessionTimeout`  
 <span data-ttu-id="2e94b-187">Propriété dont la valeur est un entier qui définit le délai d'attente minimal des sessions inactives, exprimé en secondes.</span><span class="sxs-lookup"><span data-stu-id="2e94b-187">An integer property that defines the minimum time, in seconds, that idle sessions will timeout.</span></span> <span data-ttu-id="2e94b-188">La valeur par défaut est 2700 secondes.</span><span class="sxs-lookup"><span data-stu-id="2e94b-188">The default is 2700 seconds.</span></span> <span data-ttu-id="2e94b-189">Une fois ce délai expiré, le serveur est autorisé à mettre fin à la session inactive, mais il ne le fera que si de la mémoire est requise.</span><span class="sxs-lookup"><span data-stu-id="2e94b-189">After this time expires, the server is permitted to end the idle session, but will only do so as memory is needed.</span></span>  
  
 `Port`  
 <span data-ttu-id="2e94b-190">Propriété dont la valeur est un entier qui définit le numéro de port sur lequel le serveur sera à l'écoute des connexions clientes.</span><span class="sxs-lookup"><span data-stu-id="2e94b-190">An integer property that defines the port number on which server will listen for client connections.</span></span> <span data-ttu-id="2e94b-191">Si cette propriété n'est pas définie, le serveur recherche dynamiquement le premier port inutilisé.</span><span class="sxs-lookup"><span data-stu-id="2e94b-191">If not set, server dynamically finds first unused port.</span></span>  
  
 <span data-ttu-id="2e94b-192">La valeur par défaut de cette propriété, zéro (0), correspond au port 2383.</span><span class="sxs-lookup"><span data-stu-id="2e94b-192">The default value for this property is zero (0), which in turn defaults to port 2383.</span></span> <span data-ttu-id="2e94b-193">Pour plus d'informations sur la configuration du port, consultez [Configure the Windows Firewall to Allow Analysis Services Access](../instances/configure-the-windows-firewall-to-allow-analysis-services-access.md).</span><span class="sxs-lookup"><span data-stu-id="2e94b-193">For more information about port configuration, see [Configure the Windows Firewall to Allow Analysis Services Access](../instances/configure-the-windows-firewall-to-allow-analysis-services-access.md).</span></span>  
  
 `ServerTimeout`  
 <span data-ttu-id="2e94b-194">Entier qui spécifie le délai d'attente des requêtes, en secondes.</span><span class="sxs-lookup"><span data-stu-id="2e94b-194">An integer that defines the timeout, in seconds, for queries.</span></span> <span data-ttu-id="2e94b-195">La valeur par défaut est 3 600 secondes (ou 60 minutes).</span><span class="sxs-lookup"><span data-stu-id="2e94b-195">The default is 3600 seconds (or 60 minutes).</span></span> <span data-ttu-id="2e94b-196">Zéro (0) indique qu'aucune requête n'expire.</span><span class="sxs-lookup"><span data-stu-id="2e94b-196">Zero (0) specifies that no queries will timeout.</span></span>  
  
 `TempDir`  
 <span data-ttu-id="2e94b-197">Propriété de type chaîne qui spécifie l'emplacement de stockage des fichiers temporaires utilisé lors des opérations de traitement, de restauration et autres.</span><span class="sxs-lookup"><span data-stu-id="2e94b-197">A string property that specifies the location for storing temporary files used during processing, restoring, and other operations.</span></span> <span data-ttu-id="2e94b-198">La valeur par défaut de cette propriété est déterminée par l'installation.</span><span class="sxs-lookup"><span data-stu-id="2e94b-198">The default value for this property is determined by setup.</span></span> <span data-ttu-id="2e94b-199">Si elle n'est pas spécifiée, la valeur par défaut est le répertoire Data.</span><span class="sxs-lookup"><span data-stu-id="2e94b-199">If not specified, the default is the Data directory.</span></span>  
  
## <a name="requestprioritization-category"></a><span data-ttu-id="2e94b-200">Catégorie RequestPrioritization</span><span class="sxs-lookup"><span data-stu-id="2e94b-200">RequestPrioritization Category</span></span>  
 `Enabled`  
 <span data-ttu-id="2e94b-201">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2e94b-201">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `StatisticsStoreSize`  
 <span data-ttu-id="2e94b-202">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2e94b-202">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e94b-203">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2e94b-203">See Also</span></span>  
 <span data-ttu-id="2e94b-204">[Configurer les propriétés du serveur dans Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="2e94b-204">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="2e94b-205">Déterminer le mode serveur d'une instance Analysis Services</span><span class="sxs-lookup"><span data-stu-id="2e94b-205">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
