---
title: Modifier les connexions du contrôle de code source | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server Management Studio], source controls
- source controls [SQL Server Management Studio], connections
ms.assetid: 538e3beb-f99c-4095-bd65-6413e872d26e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 077a09cdca0c0aff777184f04467ca39592690aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611323"
---
# <a name="change-source-control-connections"></a><span data-ttu-id="6174b-102">Modifier les connexions du contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="6174b-102">Change Source Control Connections</span></span>
  <span data-ttu-id="6174b-103">La première fois que vous ouvrez ou ajoutez une solution au contrôle de code source, le fournisseur de contrôle de code source crée une association entre le dossier racine du répertoire de la solution locale et le dossier de serveur correspondant.</span><span class="sxs-lookup"><span data-stu-id="6174b-103">The first time you add or open a solution from source control, your source control provider creates an association between the root folder of the local solution directory and its corresponding server folder.</span></span>  
  
 <span data-ttu-id="6174b-104">Le dossier racine (appelé également racine unique) réside sur le client.</span><span class="sxs-lookup"><span data-stu-id="6174b-104">The root folder (also called unified root) resides on the client.</span></span> <span data-ttu-id="6174b-105">Il s'agit du dossier dans lequel se trouvent tous les fichiers référencés par une solution ou un projet.</span><span class="sxs-lookup"><span data-stu-id="6174b-105">It is the folder beneath which all the files referenced by a solution or project can be found.</span></span> <span data-ttu-id="6174b-106">Pour trouver la dernière version d'une solution, son historique et ses informations d'état, recherchez le dossier de serveur qui réside sur le serveur du contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="6174b-106">To find the latest version of a solution, its history, and its status information, locate the server folder, which resides on the source control server.</span></span> <span data-ttu-id="6174b-107">Dans [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, les dossiers de serveur sont appelés projets.</span><span class="sxs-lookup"><span data-stu-id="6174b-107">In [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, server folders are called projects.</span></span>  
  
 <span data-ttu-id="6174b-108">Dans de nombreux cas, vous devez détacher ou déconnecter une solution de son dossier de serveur.</span><span class="sxs-lookup"><span data-stu-id="6174b-108">In many situations, you need to unbind or disconnect a solution from its server folder.</span></span> <span data-ttu-id="6174b-109">Par exemple, si l'ordinateur sur lequel votre fournisseur de contrôle de code source réside n'est pas disponible, vous pouvez alors vous connecter à un ordinateur de réserve, reconnecter votre solution à un dossier de serveur sauvegardé et reprendre le travail normalement.</span><span class="sxs-lookup"><span data-stu-id="6174b-109">For example, if the computer on which your source control provider resides is unavailable, you can connect to a backup computer, rebind your solution to a backed-up server folder, and resume working normally.</span></span> <span data-ttu-id="6174b-110">En cas de dédoublement d'un projet de contrôle de code source, vous pouvez également être amené à vous connecter au dossier de serveur dans lequel la nouvelle version de projet réside.</span><span class="sxs-lookup"><span data-stu-id="6174b-110">Also, if a source control project is forked, you may have to bind your solution to the server folder where the new project version resides.</span></span>  
  
 <span data-ttu-id="6174b-111">Utilisez l'interface utilisateur du fournisseur de contrôle de code source pour modifier le dossier de serveur auquel une solution est liée.</span><span class="sxs-lookup"><span data-stu-id="6174b-111">Use the user interface of the source control provider to change the server folder that a solution is bound to.</span></span> <span data-ttu-id="6174b-112">Vous pouvez ouvrir l'interface utilisateur du contrôle de code source à partir de l'environnement [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6174b-112">You can open the source control user interface from within the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] environment.</span></span>  
  
#### <a name="to-open-the-source-control-user-interface-from-the-studio-environment"></a><span data-ttu-id="6174b-113">Pour ouvrir l'interface utilisateur du contrôle de code source à partir de l'environnement Studio</span><span class="sxs-lookup"><span data-stu-id="6174b-113">To open the source control user interface from the Studio environment</span></span>  
  
1.  <span data-ttu-id="6174b-114">Dans le menu **fichier** , pointez sur **contrôle de code source**, puis cliquez sur **Démarrer Microsoft Visual SourceSafe**.</span><span class="sxs-lookup"><span data-stu-id="6174b-114">On the **File** menu, point to **Source Control**, and then click **Launch Microsoft Visual SourceSafe**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6174b-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6174b-115">See Also</span></span>  
 <span data-ttu-id="6174b-116">[Notions de base sur le contrôle de code source](../../2014/database-engine/source-control-basics.md) </span><span class="sxs-lookup"><span data-stu-id="6174b-116">[Source Control Basics](../../2014/database-engine/source-control-basics.md) </span></span>  
 <span data-ttu-id="6174b-117">[Définir les options de contrôle de code source](../../2014/database-engine/set-source-control-options.md) </span><span class="sxs-lookup"><span data-stu-id="6174b-117">[Set Source Control Options](../../2014/database-engine/set-source-control-options.md) </span></span>  
 [<span data-ttu-id="6174b-118">Exclure des fichiers du contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="6174b-118">Exclude Files from Source Control</span></span>](../../2014/database-engine/exclude-files-from-source-control.md)  
  
  
