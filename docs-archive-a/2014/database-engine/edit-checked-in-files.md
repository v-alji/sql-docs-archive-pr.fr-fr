---
title: Modifier les fichiers archivés | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- modifying checked-in files
- checking in files
ms.assetid: 560cd19f-ab22-4273-b00c-149993a630e6
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: e2dbe1aad203dfdc83e438d5b7f4ed19c15038c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701627"
---
# <a name="edit-checked-in-files"></a><span data-ttu-id="54b08-102">Modifier des fichiers archivés</span><span class="sxs-lookup"><span data-stu-id="54b08-102">Edit Checked-In Files</span></span>
  <span data-ttu-id="54b08-103">Vous devez généralement extraire les fichiers sous contrôle de code source avant de pouvoir les modifier.</span><span class="sxs-lookup"><span data-stu-id="54b08-103">You typically must check out source-controlled files before you can edit them.</span></span> <span data-ttu-id="54b08-104">Toutefois, vous pouvez configurer [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] de sorte que vous puissiez modifier les fichiers que vous n’avez pas extraits. Dans ce cas, vos modifications sont conservées en mémoire jusqu’à ce que vous enregistriez les fichiers.</span><span class="sxs-lookup"><span data-stu-id="54b08-104">However, you can configure [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] so that you can modify files you have not checked out. When doing so, your changes are held in memory until you save the files.</span></span> <span data-ttu-id="54b08-105">Vous êtes ensuite invité à extraire le fichier à partir du contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="54b08-105">You will then be prompted to check out the file from source control.</span></span>  
  
 <span data-ttu-id="54b08-106">Si vous travaillez en équipe, il n'est pas recommandé d'autoriser la modification des fichiers archivés, sauf si votre fournisseur de contrôle de code source prend en charge l'extraction à la fois de la version locale et de la version serveur.</span><span class="sxs-lookup"><span data-stu-id="54b08-106">If you work on a team, allowing checked-in files to be edited is not recommended unless your source control provider supports both local version and server version checkouts.</span></span> <span data-ttu-id="54b08-107">La plupart des fournisseurs ne prennent pas en charge les extractions de versions locales.</span><span class="sxs-lookup"><span data-stu-id="54b08-107">Most providers do not support local version checkouts.</span></span> <span data-ttu-id="54b08-108">Si votre fournisseur ne prend pas en charge les extractions de versions locales et que vous modifiez un fichier archivé, vous devez fusionner manuellement les versions en mémoire et sur le serveur pour pouvoir archiver le fichier.</span><span class="sxs-lookup"><span data-stu-id="54b08-108">If your provider does not support local version checkouts and you edit a checked-in file, you have to merge the in-memory and server versions manually before the file can be checked in.</span></span> <span data-ttu-id="54b08-109">Les fusions automatiques et assistées par le fournisseur ne sont pas prises en charge dans cette situation.</span><span class="sxs-lookup"><span data-stu-id="54b08-109">Automatic and provider-assisted merges are unsupported in this situation.</span></span>  
  
### <a name="to-edit-checked-in-files"></a><span data-ttu-id="54b08-110">Pour modifier des fichiers archivés</span><span class="sxs-lookup"><span data-stu-id="54b08-110">To edit checked-in files</span></span>  
  
1.  <span data-ttu-id="54b08-111">Dans le menu **Outils** , cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="54b08-111">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="54b08-112">Dans la boîte de dialogue **Options** , développez le dossier **Contrôle de code source**, puis cliquez sur **Environnement**.</span><span class="sxs-lookup"><span data-stu-id="54b08-112">In the **Options** dialog box, expand the **Source Contro**l folder, and then click **Environment**.</span></span>  
  
3.  <span data-ttu-id="54b08-113">Cliquez sur **Permettre la modification des éléments archivés**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="54b08-113">Click **Allow checked-in items to be edited**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54b08-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="54b08-114">See Also</span></span>  
 <span data-ttu-id="54b08-115">[Gérer les archivages](../../2014/database-engine/manage-checkins.md) </span><span class="sxs-lookup"><span data-stu-id="54b08-115">[Manage Checkins](../../2014/database-engine/manage-checkins.md) </span></span>  
 [<span data-ttu-id="54b08-116">Gérer les extractions</span><span class="sxs-lookup"><span data-stu-id="54b08-116">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)  
  
  
