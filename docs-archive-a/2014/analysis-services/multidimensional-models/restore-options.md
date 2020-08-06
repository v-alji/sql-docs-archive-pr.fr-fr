---
title: Options de restauration | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- databases [Analysis Services], restoring
- restoring databases [Analysis Services]
ms.assetid: 75c73802-f321-4671-afc7-54505d62c013
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3fa8da816e656521fb04ae7beb1127786e04e178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710912"
---
# <a name="restore-options"></a><span data-ttu-id="68525-102">Options de restauration</span><span class="sxs-lookup"><span data-stu-id="68525-102">Restore Options</span></span>
  <span data-ttu-id="68525-103">Il existe de nombreuses façons de restaurer vos [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] bases de données, ce qui nécessite que vous disposiez d’autorisations d’administrateur pour l’ordinateur serveur et la [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] base de données.</span><span class="sxs-lookup"><span data-stu-id="68525-103">There are many ways to restore your [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] databases, all of which require that you have administrator permissions for both the server computer and the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="68525-104">Pour restaurer une base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , vous pouvez ouvrir la boîte de dialogue **Restaurer la base de données** dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], sélectionner la configuration des options appropriée, puis exécuter la restauration à partir de cette boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="68525-104">To restore an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, you can open the **Restore Database** dialog box in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the appropriate options configuration and then run the restore from the dialog box.</span></span> <span data-ttu-id="68525-105">Ou bien, vous pouvez créer un script utilisant les paramètres déjà spécifiés dans le fichier ; ce script peut ensuite être enregistré et exécuté aussi souvent que nécessaire.</span><span class="sxs-lookup"><span data-stu-id="68525-105">Or, you can create a script using the settings already specified in the file; the script can then be saved and run as often as needed.</span></span> <span data-ttu-id="68525-106">De cette façon, la restauration est effectuée en utilisant XMLA, comme le décrit la section suivante.</span><span class="sxs-lookup"><span data-stu-id="68525-106">In this way, the restore is completed by using XMLA, as described in the next section.</span></span>  
  
## <a name="restoring-databases-using-xmla"></a><span data-ttu-id="68525-107">Restauration de bases de données à l'aide de XMLA</span><span class="sxs-lookup"><span data-stu-id="68525-107">Restoring Databases Using XMLA</span></span>  
 <span data-ttu-id="68525-108">La commande XMLA Restore permet d'automatiser le processus de restauration en exécutant une restauration basée sur un fichier .abf.</span><span class="sxs-lookup"><span data-stu-id="68525-108">The XMLA Restore command is a way to automate the restore process by running a restore based on an .abf file.</span></span> <span data-ttu-id="68525-109">La commande Restore possède des propriétés qu'il est possible de définir pour spécifier des définitions de sécurité, l'emplacement où stocker les partitions distantes et le déplacement d'objets ROLAP (OLAP relationnel).</span><span class="sxs-lookup"><span data-stu-id="68525-109">The Restore command has a number of properties that can be set to specify security definitions, where remote partitions should be stored, and the relocation of relational OLAP (ROLAP) objects.</span></span> <span data-ttu-id="68525-110">Pour plus d’informations, consultez [Élément Restore &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/restore-element-xmla).</span><span class="sxs-lookup"><span data-stu-id="68525-110">For more information, see [Restore Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/restore-element-xmla).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="68525-111">Pour chaque fichier de sauvegarde, l'utilisateur qui exécute la commande de restauration doit avoir l'autorisation de lire à partir de l'emplacement de sauvegarde spécifié pour chaque fichier.</span><span class="sxs-lookup"><span data-stu-id="68525-111">For each backup file, the user who runs the restore command must have permission to read from the backup location specified for each file.</span></span> <span data-ttu-id="68525-112">Pour restaurer une base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] qui n'est pas installée sur le serveur, l'utilisateur doit également être un membre du rôle serveur pour cette instance d' [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="68525-112">To restore an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database that is not installed on the server, the user must also be a member of the server role for that [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="68525-113">Pour remplacer une base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , l’utilisateur doit avoir l’un des rôles suivants : membre du rôle serveur pour l’instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ou membre d’un rôle de base de données avec les autorisations de contrôle total (Administrateur) sur la base de données à restaurer.</span><span class="sxs-lookup"><span data-stu-id="68525-113">To overwrite an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, the user must have one of the following roles: a member of the server role for the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, or a member of a database role with Full Control (Administrator) permissions on the database to be restored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="68525-114">Après la restauration d'une base de données existante, l'utilisateur qui a restauré la base de données peut perdre l'accès à la base de données restaurée.</span><span class="sxs-lookup"><span data-stu-id="68525-114">After restoring an existing database, the user who restored the database might lose access to the restored database.</span></span> <span data-ttu-id="68525-115">Cette perte d'accès peut se produire si, au moment de la sauvegarde, l'utilisateur n'était pas un membre du rôle de serveur ou un membre du rôle de base de données avec les autorisations de contrôle total (Administrateur).</span><span class="sxs-lookup"><span data-stu-id="68525-115">This loss of access can occur if, at the time that the backup was performed, the user was not a member of the server role or was not a member of the database role with Full Control (Administrator) permissions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68525-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="68525-116">See Also</span></span>  
 <span data-ttu-id="68525-117">[Boîte de dialogue restaurer la base de données &#40;Analysis Services-données multidimensionnelles&#41;](../restore-database-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="68525-117">[Restore Database Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](../restore-database-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="68525-118">[Sauvegarde et restauration de bases de données Analysis Services](backup-and-restore-of-analysis-services-databases.md) </span><span class="sxs-lookup"><span data-stu-id="68525-118">[Backup and Restore of Analysis Services Databases](backup-and-restore-of-analysis-services-databases.md) </span></span>  
 <span data-ttu-id="68525-119">[Élément Restore &#40;&#41;XMLA](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/restore-element-xmla) </span><span class="sxs-lookup"><span data-stu-id="68525-119">[Restore Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/restore-element-xmla) </span></span>  
 [<span data-ttu-id="68525-120">Sauvegarde, restauration et synchronisation de bases de données &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="68525-120">Backing Up, Restoring, and Synchronizing Databases &#40;XMLA&#41;</span></span>](../multidimensional-models-scripting-language-assl-xmla/backing-up-restoring-and-synchronizing-databases-xmla.md)  
  
  