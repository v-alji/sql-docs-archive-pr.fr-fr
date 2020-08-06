---
title: Importer les stratégies vers une instance unique | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: bc5bcd87-663f-41d9-bb7b-b3e083cd63df
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 0464bc6f4dcd6326a4b8f222cb4b3128f21561ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707980"
---
# <a name="import-the-policies-to-a-single-instance"></a><span data-ttu-id="b20ab-102">Importer les stratégies vers une instance unique</span><span class="sxs-lookup"><span data-stu-id="b20ab-102">Import the Policies to a Single Instance</span></span>
  <span data-ttu-id="b20ab-103">Dans cette tâche, vous importerez les stratégies des meilleures pratiques que vous souhaitez planifier dans la Gestion basée sur des stratégies sur une instance unique de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b20ab-103">In this task, you will import the best practices policies that you want to schedule into Policy-Based Management on a single instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b20ab-104">Prérequis</span><span class="sxs-lookup"><span data-stu-id="b20ab-104">Prerequisites</span></span>  
 <span data-ttu-id="b20ab-105">Vous devez effectuer cette procédure sur un serveur qui exécute [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="b20ab-105">You must perform this procedure on a server that is running [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] or a later version.</span></span>  
  
### <a name="import-the-best-practices-policies-for-the-database-engine"></a><span data-ttu-id="b20ab-106">Importer les stratégies des meilleures pratiques pour le moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="b20ab-106">Import the best practices policies for the Database Engine</span></span>  
  
1.  <span data-ttu-id="b20ab-107">Démarrez [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , puis connectez-vous au [!INCLUDE[ssDE](../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b20ab-107">Start [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], and then connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b20ab-108">Dans l’Explorateur d’objets, développez **gestion**, puis gestion de la **stratégie**.</span><span class="sxs-lookup"><span data-stu-id="b20ab-108">In Object Explorer, expand **Management**, and then expand **Policy Management**.</span></span>  
  
3.  <span data-ttu-id="b20ab-109">Cliquez avec le bouton droit sur **stratégies**, puis cliquez sur **Importer une stratégie**.</span><span class="sxs-lookup"><span data-stu-id="b20ab-109">Right-click **Policies**, and then click **Import Policy**.</span></span>  
  
4.  <span data-ttu-id="b20ab-110">Dans la boîte de dialogue **Importer** , en regard de la zone **fichiers à importer** , cliquez sur le bouton de sélection (**...**).</span><span class="sxs-lookup"><span data-stu-id="b20ab-110">In the **Import** dialog box, next to the **Files to import** box, click the ellipsis (**...**) button.</span></span>  
  
5.  <span data-ttu-id="b20ab-111">Dans la liste **regarder dans** , accédez au dossier suivant, qui contient les stratégies des meilleures pratiques :</span><span class="sxs-lookup"><span data-stu-id="b20ab-111">In the **Look in** list, browse to the following folder, which contains the best practices policies:</span></span>  
  
     <span data-ttu-id="b20ab-112">**C:\Program Files (x86)\Microsoft SQL Server\110\Tools\Policies\DatabaseEngine\1033**</span><span class="sxs-lookup"><span data-stu-id="b20ab-112">**C:\Program Files (x86)\Microsoft SQL Server\110\Tools\Policies\DatabaseEngine\1033**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b20ab-113">Le chemin d'accès du fichier varie, selon l'emplacement d'installation des fichiers programme [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], si vous exécutez un système d'exploitation 32 bits ou 64 bits, et selon l'identificateur de langue.</span><span class="sxs-lookup"><span data-stu-id="b20ab-113">The file path may vary, depending on where you installed the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] program files, whether you are running a 32-bit or 64-bit operating system, and the language identifier.</span></span>  
  
6.  <span data-ttu-id="b20ab-114">Dans la boîte de dialogue **Sélectionner une stratégie** , sélectionnez un ou plusieurs fichiers de stratégie.</span><span class="sxs-lookup"><span data-stu-id="b20ab-114">In the **Select Policy** dialog box, select one or more policy files.</span></span>  
  
     <span data-ttu-id="b20ab-115">Pour sélectionner des fichiers non adjacents, cliquez sur un fichier, maintenez la touche CTRL enfoncée, puis cliquez sur chaque fichier supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="b20ab-115">To select nonadjacent files, click one file, hold down the CTRL key, and then click each additional file.</span></span> <span data-ttu-id="b20ab-116">Pour sélectionner des fichiers adjacents, cliquez sur le premier fichier dans la séquence, maintenez la touche MAJ enfoncée, puis cliquez sur le dernier fichier.</span><span class="sxs-lookup"><span data-stu-id="b20ab-116">To select adjacent files, click the first file in the sequence, hold down the SHIFT key, and then click the last file.</span></span>  
  
7.  <span data-ttu-id="b20ab-117">Une fois que vous avez fini de sélectionner les fichiers, cliquez sur **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="b20ab-117">When you are finished selecting files, click **Open**.</span></span>  
  
8.  <span data-ttu-id="b20ab-118">Dans la boîte de dialogue **Importer** , assurez-vous que la liste **État** de la stratégie est définie sur **conserver l’état de la stratégie lors de l’importation** (valeur par défaut), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b20ab-118">In the **Import** dialog box, make sure that the **Policy state** list is set to **Preserve policy state on import** (the default), and then click **OK**.</span></span>  
  
     <span data-ttu-id="b20ab-119">Les stratégies sont importées dans le nœud **stratégies** sous gestion de la **stratégie**.</span><span class="sxs-lookup"><span data-stu-id="b20ab-119">The policies are imported into the **Policies** node under **Policy Management**.</span></span> <span data-ttu-id="b20ab-120">Par défaut, les stratégies importées sont définies sur le mode d'évaluation « à la demande ».</span><span class="sxs-lookup"><span data-stu-id="b20ab-120">By default, the imported policies are set to "On demand" evaluation mode.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b20ab-121">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="b20ab-121">Next Steps</span></span>  
 [<span data-ttu-id="b20ab-122">Planifier les stratégies</span><span class="sxs-lookup"><span data-stu-id="b20ab-122">Schedule the Policies</span></span>](../../2014/tutorials/schedule-the-policies.md)  
  
  
