---
title: Exclure des fichiers du contrôle de code source | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- excluding files from source control
- source controls [SQL Server Management Studio], file exclusions
ms.assetid: 7dcb6514-db5c-49eb-8b5a-2c766ce39aa7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9fb3c5ccb4fcaad062236eec6d04f995557dc2b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701598"
---
# <a name="exclude-files-from-source-control"></a><span data-ttu-id="d37cf-102">Exclure des fichiers du contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="d37cf-102">Exclude Files from Source Control</span></span>
  <span data-ttu-id="d37cf-103">Si la solution sur laquelle vous travaillez contient des fichiers qui ne nécessitent pas de services de contrôle de code source, vous pouvez utiliser la commande **exclure du contrôle de code source** pour exclure le fichier du contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="d37cf-103">If the solution you are working on contains files that do not require source control services, you can use the **Exclude from Source Control** command to exclude the file from source control.</span></span> <span data-ttu-id="d37cf-104">Lorsque vous effectuez cette opération, le fichier reste dans la base de données de [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, mais il ne fait plus l'objet d'archivage ni d'extraction dans le cadre du projet.</span><span class="sxs-lookup"><span data-stu-id="d37cf-104">When you do this, the file remains in the [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe database, but it is no longer checked in or out with the project.</span></span>  
  
 <span data-ttu-id="d37cf-105">Vous devez utiliser la commande **exclure du contrôle de code source** uniquement sur les fichiers générés.</span><span class="sxs-lookup"><span data-stu-id="d37cf-105">You should use the **Exclude from Source Control** command only on generated files.</span></span> <span data-ttu-id="d37cf-106">Un fichier généré est un fichier qui peut être entièrement recréé par en [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] fonction du contenu d’un autre fichier dans la solution.</span><span class="sxs-lookup"><span data-stu-id="d37cf-106">A generated file is one that can be entirely re-created by [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] based on the contents of another file in the solution.</span></span>  
  
### <a name="to-exclude-a-file-from-source-control"></a><span data-ttu-id="d37cf-107">Pour exclure un fichier du contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="d37cf-107">To exclude a file from source control</span></span>  
  
1.  <span data-ttu-id="d37cf-108">Dans l'Explorateur de solutions, sélectionnez le fichier à exclure.</span><span class="sxs-lookup"><span data-stu-id="d37cf-108">In Solution Explorer, select the file to exclude.</span></span>  
  
2.  <span data-ttu-id="d37cf-109">Dans le menu **fichier** , pointez sur **contrôle de code source**, puis cliquez sur **exclure** *\<file name>* **du contrôle de code source**.</span><span class="sxs-lookup"><span data-stu-id="d37cf-109">On the **File** menu, point to **Source Control**, and then click **Exclude** *\<file name>* **from Source Control**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d37cf-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d37cf-110">See Also</span></span>  
 <span data-ttu-id="d37cf-111">[Notions de base sur le contrôle de code source](../../2014/database-engine/source-control-basics.md) </span><span class="sxs-lookup"><span data-stu-id="d37cf-111">[Source Control Basics](../../2014/database-engine/source-control-basics.md) </span></span>  
 <span data-ttu-id="d37cf-112">[Définir les options de contrôle de code source](../../2014/database-engine/set-source-control-options.md) </span><span class="sxs-lookup"><span data-stu-id="d37cf-112">[Set Source Control Options](../../2014/database-engine/set-source-control-options.md) </span></span>  
 [<span data-ttu-id="d37cf-113">Modifier les connexions du contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="d37cf-113">Change Source Control Connections</span></span>](../../2014/database-engine/change-source-control-connections.md)  
  
  
