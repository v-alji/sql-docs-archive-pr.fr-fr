---
title: Dossier d’instantanés | Microsoft Docs
ms.custom: ''
ms.date: 06/30/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replicationutilities.specifysnapshotfolder.f1
ms.assetid: 3eb1b73f-ddb3-4d09-be6e-811c414698e9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 48b490c65662edf65018e98dd1bc3339f6aae6b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614491"
---
# <a name="snapshot-folder"></a><span data-ttu-id="7541d-102">Dossier d'instantanés</span><span class="sxs-lookup"><span data-stu-id="7541d-102">Snapshot Folder</span></span>
  <span data-ttu-id="7541d-103">La page **Dossier d'instantanés** figure dans l'Assistant Configuration de la distribution et l'Assistant Nouvelle publication.</span><span class="sxs-lookup"><span data-stu-id="7541d-103">The **Snapshot Folder** page appears in the Configure Distribution Wizard and in the New Publication Wizard.</span></span> <span data-ttu-id="7541d-104">L'emplacement que vous définissez pour le dossier d'instantanés est utilisé par défaut pour tous les serveurs de publication activés dans cet Assistant (le dossier par défaut des instantanés ne s'applique pas aux serveurs de publication qui sont ensuite activés dans la boîte de dialogue **Propriétés du serveur de distribution** ).</span><span class="sxs-lookup"><span data-stu-id="7541d-104">The location you specify for the snapshot folder will be used as the default for all Publishers enabled in this wizard (the default snapshot folder does not apply to Publishers that are later enabled using the **Distributor Properties** dialog box).</span></span> <span data-ttu-id="7541d-105">Vous pouvez changer ce dossier par défaut pour n'importe quel serveur de publication dans la page **Serveurs de publication** de l'Assistant Configuration de la distribution ou la boîte de dialogue **Propriétés du serveur de distribution** .</span><span class="sxs-lookup"><span data-stu-id="7541d-105">You can override this default for any Publisher on the **Publishers** page of the Configure Distribution Wizard or the **Distributor Properties** dialog box.</span></span>  
  
 <span data-ttu-id="7541d-106">Le dossier d'instantanés correspond à un simple répertoire que vous définissez sous la forme d'un partage ; les agents qui lisent et écrivent dans le dossier doivent disposer des autorisations suffisantes pour pouvoir y accéder.</span><span class="sxs-lookup"><span data-stu-id="7541d-106">The snapshot folder is simply a directory that you have designated as a share; agents that read from and write to this folder must have sufficient permissions to access it.</span></span> <span data-ttu-id="7541d-107">Pour plus d’informations sur une sécurisation appropriée du dossier, consultez [Sécuriser le dossier d’instantanés](security/secure-the-snapshot-folder.md).</span><span class="sxs-lookup"><span data-stu-id="7541d-107">For more information about securing the folder appropriately, see [Secure the Snapshot Folder](security/secure-the-snapshot-folder.md).</span></span> <span data-ttu-id="7541d-108">Avant d'implémenter la réplication, vérifiez que les agents de réplication peuvent se connecter au dossier d'instantanés.</span><span class="sxs-lookup"><span data-stu-id="7541d-108">Prior to implementing replication, test that the replication agents will be able to connect to the snapshot folder.</span></span> <span data-ttu-id="7541d-109">Connectez-vous sous le compte qu'utilisera chaque agent et essayez ensuite d'accéder au dossier d'instantanés.</span><span class="sxs-lookup"><span data-stu-id="7541d-109">Log on under the account that will be used by each agent and then attempt to access the snapshot folder.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7541d-110">Options</span><span class="sxs-lookup"><span data-stu-id="7541d-110">Options</span></span>  
 <span data-ttu-id="7541d-111">**Dossier d'instantanés**</span><span class="sxs-lookup"><span data-stu-id="7541d-111">**Snapshot folder**</span></span>  
 <span data-ttu-id="7541d-112">Entrez le chemin d'accès au dossier où vous souhaitez stocker les fichiers d'instantanés.</span><span class="sxs-lookup"><span data-stu-id="7541d-112">Enter the path for the folder where you want snapshot files stored.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="7541d-113">recommande d'utiliser un partage réseau comme emplacement pour le dossier d'instantanés.</span><span class="sxs-lookup"><span data-stu-id="7541d-113">recommends that you use a network share as a snapshot folder location.</span></span> <span data-ttu-id="7541d-114">Les chemins locaux (ceux qui commencent par une lettre de lecteur, tel que C:\\) ne sont pas accessibles aux agents sur les autres ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="7541d-114">Local paths (those starting with a drive letter, such as C:\\) are not accessible to agents on other computers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7541d-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7541d-115">See Also</span></span>  
 <span data-ttu-id="7541d-116">[Autres emplacements de dossier d’instantanés](alternate-snapshot-folder-locations.md) </span><span class="sxs-lookup"><span data-stu-id="7541d-116">[Alternate Snapshot Folder Locations](alternate-snapshot-folder-locations.md) </span></span>  
 <span data-ttu-id="7541d-117">[Configurer la distribution](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="7541d-117">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="7541d-118">[Configurer la publication et la distribution](configure-publishing-and-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="7541d-118">[Configure Publishing and Distribution](configure-publishing-and-distribution.md) </span></span>  
 <span data-ttu-id="7541d-119">[Afficher et modifier les propriétés d’un serveur de distribution et d’un serveur de publication](view-and-modify-distributor-and-publisher-properties.md) </span><span class="sxs-lookup"><span data-stu-id="7541d-119">[View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md) </span></span>  
 [<span data-ttu-id="7541d-120">Initialiser un abonnement avec un instantané</span><span class="sxs-lookup"><span data-stu-id="7541d-120">Initialize a Subscription with a Snapshot</span></span>](initialize-a-subscription-with-a-snapshot.md)  
  
  
