---
title: Associer des extensions de fichier à un éditeur de code
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- file extensions [SQL Server]
- associating file extensions [SQL Server]
- Query Editor [SQL Server Management Studio], associating file extensions
ms.assetid: 193630f4-93de-4950-8f36-68702531f925
author: rothja
ms.author: jroth
ms.openlocfilehash: 0e8cfbc89892a99971e985ffd3ff10b99f89fe53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603914"
---
# <a name="associate-file-extensions-to-a-code-editor"></a><span data-ttu-id="bb94e-102">Associer des extensions de fichier à un éditeur de code</span><span class="sxs-lookup"><span data-stu-id="bb94e-102">Associate File Extensions to a Code Editor</span></span>
  <span data-ttu-id="bb94e-103">L'association d'extensions de fichier à un éditeur de code spécifique permet d'ouvrir un fichier avec l'éditeur [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] adapté lorsque vous double-cliquez sur un fichier dans l'Explorateur Windows.</span><span class="sxs-lookup"><span data-stu-id="bb94e-103">Associating file extensions to a specific code editor allows you to open a file with the appropriate [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] code editor when you double-click a file in Windows Explorer.</span></span> <span data-ttu-id="bb94e-104">Les extensions couramment utilisées par [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], par exemple .sql and .mdx,  sont associées lors de l'installation.</span><span class="sxs-lookup"><span data-stu-id="bb94e-104">The extensions commonly used by [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], such as .sql and .mdx, are associated during installation.</span></span> <span data-ttu-id="bb94e-105">Les nouvelles extensions doivent également être associées à [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="bb94e-105">New file extensions must also be associated to [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] in the file system.</span></span> <span data-ttu-id="bb94e-106">Vous pouvez utiliser cette fonctionnalité pour ouvrir des fichiers créés avec d'autres éditeurs. Vous pouvez également ouvrir des fichiers que vous avez renommés (ex. sauvegardes de fichiers .sql renommés avec l'extension .bak).</span><span class="sxs-lookup"><span data-stu-id="bb94e-106">You can use this feature to open files created with other editors, or to open files you have renamed, such as backups of .sql files that were renamed .bak.</span></span>  
  
 <span data-ttu-id="bb94e-107">Cette procédure se déroule en deux étapes.</span><span class="sxs-lookup"><span data-stu-id="bb94e-107">There are two steps in the process.</span></span> <span data-ttu-id="bb94e-108">Associez d'abord l'extension avec [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]et associez-la ensuite à un éditeur de code spécifique.</span><span class="sxs-lookup"><span data-stu-id="bb94e-108">First associate the extension with [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then associate the extension with a specific code editor.</span></span>  
  
### <a name="to-associate-a-new-file-extension-with-sql-server-management-studio"></a><span data-ttu-id="bb94e-109">Pour associer une nouvelle extension à SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bb94e-109">To associate a new file extension with SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="bb94e-110">Dans le menu **Démarrer** , pointez sur **Tous les programmes**, puis sur **Accessoires**. Cliquez ensuite sur **Explorateur Windows**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-110">On the **Start** menu, point to **All Programs**, point to **Accessories**, and then click **Windows Explorer**.</span></span>  
  
2.  <span data-ttu-id="bb94e-111">Dans le menu **Outils** de l’Explorateur Windows, cliquez sur **Options des dossiers**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-111">In Windows Explorer, on the **Tools** menu, click **Folder Options**.</span></span>  
  
3.  <span data-ttu-id="bb94e-112">Dans la boîte de dialogue **Options des dossiers** , cliquez sur l’onglet **Types de fichiers** , puis sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-112">In the **Folder Options** dialog box, on the **File Types** tab, click **New**.</span></span>  
  
4.  <span data-ttu-id="bb94e-113">Dans la zone **Extension du fichier** de la boîte de dialogue **Créer une nouvelle extension** , tapez la nouvelle extension que vous voulez associer. Cliquez ensuite sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-113">In the **Create New Extension** dialog box, in the **File Extension** box, type the new file extension that you want to associate, and then click **OK**.</span></span> <span data-ttu-id="bb94e-114">Ne placez pas un point devant l'extension.</span><span class="sxs-lookup"><span data-stu-id="bb94e-114">Do not start the extension with a period.</span></span>  
  
5.  <span data-ttu-id="bb94e-115">Dans la zone **Types de fichiers enregistrés** , cliquez sur la nouvelle extension, puis sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-115">In the **Registered file** types box, click on your new extension, and then click **Change**.</span></span>  
  
6.  <span data-ttu-id="bb94e-116">Dans la boîte de dialogue **Ouvrir avec**, cliquez sur **SSMS - SQL Server Management Studio**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-116">In the **Open With** dialog box, click **SSMS - SQL Server Management Studio**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="bb94e-117">Cliquez sur **OK** pour fermer la boîte de dialogue **Options des dossiers** , puis fermez l’Explorateur Windows.</span><span class="sxs-lookup"><span data-stu-id="bb94e-117">Click **Close** to close the **Folder Options** dialog box, and then close Windows Explorer.</span></span>  
  
### <a name="to-associate-a-new-file-extension-with-a-code-editor-in-sql-server-management-studio"></a><span data-ttu-id="bb94e-118">Pour associer une nouvelle extension à un éditeur de code dans SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bb94e-118">To associate a new file extension with a code editor in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="bb94e-119">Dans le menu [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]Outils **de** , cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-119">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], from the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="bb94e-120">Dans la boîte de dialogue **Options** , cliquez sur **Éditeur de texte**, puis sur **Extension de fichier**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-120">In the **Options** dialog box, click **Text Editor**, and then click **File Extension**.</span></span>  
  
3.  <span data-ttu-id="bb94e-121">Dans la zone **Extension** , tapez la nouvelle extension de fichier.</span><span class="sxs-lookup"><span data-stu-id="bb94e-121">In the **Extension** box, type your new file extension.</span></span>  
  
4.  <span data-ttu-id="bb94e-122">Dans la zone **Éditeur** , cliquez sur l’éditeur de code que vous voulez utiliser pour ouvrir ce type de fichier. Cliquez sur **Ajouter**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb94e-122">In the **Editor** box, click the code editor that you wish to use to open this file type, click **Add**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb94e-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bb94e-123">See Also</span></span>  
 [<span data-ttu-id="bb94e-124">Utilitaire Ssms</span><span class="sxs-lookup"><span data-stu-id="bb94e-124">Ssms Utility</span></span>](../../ssms/ssms-utility.md)  
  
  
