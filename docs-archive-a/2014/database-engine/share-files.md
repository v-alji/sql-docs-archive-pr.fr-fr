---
title: Partager des fichiers | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- sharing files
- file sharing [SQL Server]
- version control services [SQL Server], file sharing
ms.assetid: 645f5c0a-e949-4e87-8988-85e4d6128464
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 79909fcdb09e349798edfe285475f8a898c3bf04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708580"
---
# <a name="share-files"></a><span data-ttu-id="d38c6-102">Partager des fichiers</span><span class="sxs-lookup"><span data-stu-id="d38c6-102">Share Files</span></span>
  <span data-ttu-id="d38c6-103">Vous pouvez utiliser [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] pour partager des éléments avec des projets du contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="d38c6-103">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to share items across source control projects.</span></span> <span data-ttu-id="d38c6-104">Lorsque vous partagez un élément, toute modification apportée à cet élément est réfléchie sur chaque projet avec lequel l'élément est partagé.</span><span class="sxs-lookup"><span data-stu-id="d38c6-104">When you share an item, any changes to the item are reflected in every project to which the item is shared.</span></span>  
  
 <span data-ttu-id="d38c6-105">Le partage d'éléments présente les avantages suivants aux utilisateurs du contrôle de code source :</span><span class="sxs-lookup"><span data-stu-id="d38c6-105">Item sharing provides the following advantages to source control users:</span></span>  
  
-   <span data-ttu-id="d38c6-106">Chaque projet qui utilise un élément partagé n'est pas tenu de stocker une copie distincte de cet élément, ce qui permet d'économiser de l'espace disque à la fois sur le serveur et sur le client du contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="d38c6-106">Makes it unnecessary for each project that uses the shared item to store a separate copy of the item, conserving disk space on both the source control client and server.</span></span> <span data-ttu-id="d38c6-107">Le fournisseur de contrôle de code source stocke l'élément partagé à un emplacement centralisé et chaque projet avec lequel il est partagé stocke un pointeur désignant cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="d38c6-107">The source control provider stores the shared item in one central location, and every project to which it is shared stores a pointer to that location.</span></span>  
  
-   <span data-ttu-id="d38c6-108">Les risques d'incompatibilité entre les versions sont écartés.</span><span class="sxs-lookup"><span data-stu-id="d38c6-108">Avoids version incompatibilities.</span></span> <span data-ttu-id="d38c6-109">Comme chaque projet avec lequel l'élément est partagé utilise la même version de cet élément, tout conflit survenant lors de la modification indépendante de chaque copie d'un élément dans plusieurs projets est évité.</span><span class="sxs-lookup"><span data-stu-id="d38c6-109">Because every project to which the item is shared uses the same version of the item, you avoid the conflicts that arise when each copy of an item is changing independently within multiple projects.</span></span>  
  
### <a name="to-share-an-item"></a><span data-ttu-id="d38c6-110">Pour partager un élément</span><span class="sxs-lookup"><span data-stu-id="d38c6-110">To share an item</span></span>  
  
1.  <span data-ttu-id="d38c6-111">Dans l'Explorateur de solutions, sélectionnez le dossier ou le projet dans lequel vous souhaitez placer les fichiers partagés.</span><span class="sxs-lookup"><span data-stu-id="d38c6-111">In Solution Explorer, select either the folder or project in which you want to place the shared files.</span></span>  
  
2.  <span data-ttu-id="d38c6-112">Dans le menu **fichier** , pointez sur **contrôle de code source**, puis cliquez sur **partager**.</span><span class="sxs-lookup"><span data-stu-id="d38c6-112">On the **File** menu, point to **Source Control**, and then click **Share**.</span></span>  
  
3.  <span data-ttu-id="d38c6-113">Dans la boîte de dialogue **partager avec** , recherchez dans la liste des répertoires l’élément que vous souhaitez partager, puis cliquez sur cet élément.</span><span class="sxs-lookup"><span data-stu-id="d38c6-113">In the **Share with** dialog box, browse the directory list for the item you want to share, and click that item.</span></span>  
  
4.  <span data-ttu-id="d38c6-114">Cliquez sur **Partager**.</span><span class="sxs-lookup"><span data-stu-id="d38c6-114">Click **Share**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d38c6-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d38c6-115">See Also</span></span>  
 [<span data-ttu-id="d38c6-116">Présentation du contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="d38c6-116">Source Control Basics</span></span>](../../2014/database-engine/source-control-basics.md)  
  
  
