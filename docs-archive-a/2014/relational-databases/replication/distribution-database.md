---
title: Base de données de distribution | Microsoft Docs
ms.custom: ''
ms.date: 06/30/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.configuredistributionwizard.distributiondatabase.f1
ms.assetid: 5b42a083-7a11-41d8-9e3f-320c7c907237
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d98a80be52ae77cbdaf1581a5b3397f9d11af4fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601372"
---
# <a name="distribution-database"></a><span data-ttu-id="455de-102">Base de données de distribution</span><span class="sxs-lookup"><span data-stu-id="455de-102">Distribution Database</span></span>
  <span data-ttu-id="455de-103">La base de données de distribution stocke les métadonnées et les données d'historique pour tous les types de réplications, et les transactions pour la réplication transactionnelle.</span><span class="sxs-lookup"><span data-stu-id="455de-103">The distribution database stores metadata and history data for all types of replication, and transactions for transactional replication.</span></span>  
  
 <span data-ttu-id="455de-104">Dans de nombreux cas, une seule base de données de distribution est suffisante.</span><span class="sxs-lookup"><span data-stu-id="455de-104">In many cases, a single distribution database is sufficient.</span></span> <span data-ttu-id="455de-105">Toutefois, si plusieurs serveurs de publication utilisent un seul serveur de distribution, créez une base de distribution pour chaque serveur de publication</span><span class="sxs-lookup"><span data-stu-id="455de-105">However, if multiple Publishers use a single Distributor, consider creating a distribution database for each Publisher.</span></span> <span data-ttu-id="455de-106">Ainsi, vous vous assurerez que les données transitant entre chaque base de données de distribution seront bien séparées.</span><span class="sxs-lookup"><span data-stu-id="455de-106">Doing so ensures that the data flowing through each distribution database is distinct.</span></span> <span data-ttu-id="455de-107">Vous pouvez définir une base de données de distribution pour le serveur de distribution en utilisant l'Assistant Configuration de la distribution.</span><span class="sxs-lookup"><span data-stu-id="455de-107">You can specify one distribution database for the Distributor using the Configure Distribution Wizard.</span></span> <span data-ttu-id="455de-108">Si nécessaire, définissez des bases de données de distribution supplémentaires dans la boîte de dialogue **Propriétés du serveur de distribution** .</span><span class="sxs-lookup"><span data-stu-id="455de-108">If necessary, specify additional distribution databases in the **Distributor Properties** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="455de-109">Options</span><span class="sxs-lookup"><span data-stu-id="455de-109">Options</span></span>  
 <span data-ttu-id="455de-110">**Nom de la base de données de distribution**</span><span class="sxs-lookup"><span data-stu-id="455de-110">**Distribution database name**</span></span>  
 <span data-ttu-id="455de-111">Entrez le nom de la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="455de-111">Enter a name for the distribution database.</span></span> <span data-ttu-id="455de-112">Le nom par défaut de la base de données de distribution est « distribution ».</span><span class="sxs-lookup"><span data-stu-id="455de-112">The default name for the distribution database is 'distribution'.</span></span> <span data-ttu-id="455de-113">Si vous définissez un nom, celui-ci peut contenir jusqu’à 128 caractères. Il doit être unique dans une instance de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et être conforme aux règles des identificateurs.</span><span class="sxs-lookup"><span data-stu-id="455de-113">If you specify a name, the name can be a maximum of 128 characters, must be unique within an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and must conform to the rules for identifiers.</span></span> <span data-ttu-id="455de-114">Pour plus d'informations, consultez [Database Identifiers](../databases/database-identifiers.md).</span><span class="sxs-lookup"><span data-stu-id="455de-114">For more information, see [Database Identifiers](../databases/database-identifiers.md).</span></span>  
  
 <span data-ttu-id="455de-115">**Dossier du fichier de la base de données de distribution** et **Dossier du fichier-journal de la base de données de distribution**</span><span class="sxs-lookup"><span data-stu-id="455de-115">**Folder for the distribution database file** and **Folder for the distribution database log file**</span></span>  
 <span data-ttu-id="455de-116">Entrez le chemin d'accès aux fichiers journaux et de base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="455de-116">Enter the path for the distribution database and log files.</span></span> <span data-ttu-id="455de-117">Les chemins d'accès doivent faire référence à des disques locaux situés sur le serveur de distribution et commencer par une lettre de lecteur local suivie des deux-points (par exemple, C:).</span><span class="sxs-lookup"><span data-stu-id="455de-117">Paths must refer to disks that are local to the Distributor and begin with a local drive letter and colon (for example, C:).</span></span> <span data-ttu-id="455de-118">Les lettres d'unités mappées et les chemins d'accès réseau ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="455de-118">Mapped drive letters and network paths are not valid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="455de-119">Vous pouvez réduire le délai d'écriture des transactions et améliorer les performances de la réplication en plaçant le journal de la base de données de distribution sur un disque différent de celui de la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="455de-119">You can decrease the time it takes to write transactions and improve the performance of replication by placing the distribution database log on a separate disk drive from the distribution database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="455de-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="455de-120">See Also</span></span>  
 <span data-ttu-id="455de-121">[Configurer la distribution](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="455de-121">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="455de-122">[Configurer la publication et la distribution](configure-publishing-and-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="455de-122">[Configure Publishing and Distribution](configure-publishing-and-distribution.md) </span></span>  
 [<span data-ttu-id="455de-123">Afficher et modifier les propriétés d’un serveur de distribution ou d’un serveur de publication</span><span class="sxs-lookup"><span data-stu-id="455de-123">View and Modify Distributor and Publisher Properties</span></span>](view-and-modify-distributor-and-publisher-properties.md)  
  
  
