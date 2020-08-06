---
title: Gérer des fichiers avec encodage | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- files [SQL Server Management Studio]
- encoding [SQL Server Management Studio]
- files [SQL Server Management Studio], encoding
ms.assetid: 919544c9-59f0-4cc6-bb2a-f1ad671eb74b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9b0aaa123001fed3f6ad42ea9d642e4007e2640f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614949"
---
# <a name="manage-files-with-encoding"></a><span data-ttu-id="00887-102">Gérer des fichiers avec encodage</span><span class="sxs-lookup"><span data-stu-id="00887-102">Manage Files with Encoding</span></span>
  <span data-ttu-id="00887-103">Pour faciliter l'affichage de votre code dans un langage particulier ou sur une plateforme spécifique, vous pouvez associer un encodage de caractères déterminé à un fichier.</span><span class="sxs-lookup"><span data-stu-id="00887-103">To facilitate the display of your code in a particular language and on a particular platform, you can associate a particular character encoding with a file.</span></span>  
  
## <a name="opening-files"></a><span data-ttu-id="00887-104">Ouverture de fichiers</span><span class="sxs-lookup"><span data-stu-id="00887-104">Opening Files</span></span>  
 <span data-ttu-id="00887-105">Vous pouvez choisir l'éditeur que vous souhaitez utiliser pour modifier le fichier.</span><span class="sxs-lookup"><span data-stu-id="00887-105">You can choose the editor you want to use to edit the file.</span></span>  
  
#### <a name="to-open-a-file-with-a-specific-editor"></a><span data-ttu-id="00887-106">Pour ouvrir un fichier avec un éditeur spécifique</span><span class="sxs-lookup"><span data-stu-id="00887-106">To open a file with a specific editor</span></span>  
  
1.  <span data-ttu-id="00887-107">Dans le menu **Fichier** , pointez sur **Ouvrir**, puis cliquez sur **Fichier**.</span><span class="sxs-lookup"><span data-stu-id="00887-107">On the **File** menu, point to **Open**, and then click **File**.</span></span>  
  
2.  <span data-ttu-id="00887-108">Dans la boîte de dialogue **Ouvrir un fichier** , sélectionnez le nom du fichier.</span><span class="sxs-lookup"><span data-stu-id="00887-108">In the **Open File** dialog box, select the file name.</span></span>  
  
3.  <span data-ttu-id="00887-109">Cliquez sur la flèche en regard du bouton **Ouvrir** , puis sur**Ouvrir avec** dans le menu qui s’affiche.</span><span class="sxs-lookup"><span data-stu-id="00887-109">Click the arrow next to the **Open** button, and then click**Open With** from the menu that appears.</span></span>  
  
4.  <span data-ttu-id="00887-110">Dans la liste **Sélectionnez le programme à ouvrir** , sélectionnez un éditeur, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="00887-110">In the **Select a program to open** list, select an editor, and then click **Open**.</span></span> <span data-ttu-id="00887-111">Pour ouvrir le fichier à l'aide d'un encodage particulier, sélectionnez un éditeur prenant en charge l'encodage, tel que l'Éditeur de requête SQL avec encodage ou l'Éditeur XML avec encodage.</span><span class="sxs-lookup"><span data-stu-id="00887-111">To open the file with a particular encoding, select an editor with encoding support, such as SQL Query Editor with Encoding or XML Editor with Encoding.</span></span>  
  
## <a name="saving-files"></a><span data-ttu-id="00887-112">Enregistrement de fichiers</span><span class="sxs-lookup"><span data-stu-id="00887-112">Saving Files</span></span>  
 <span data-ttu-id="00887-113">Vous pouvez également enregistrer votre code avec un encodage Unicode ou une autre page de codes pour prendre en charge plusieurs langues, par exemple Europe de l'Ouest ou Europe de l'Est.</span><span class="sxs-lookup"><span data-stu-id="00887-113">You can also save your code with a Unicode encoding or a different code page to support various languages, such as Western European or Eastern European.</span></span> <span data-ttu-id="00887-114">Vous pouvez associer un encodage de caractères particulier à un fichier pour faciliter l'affichage de votre code dans cette langue, ainsi qu'un type de fin de ligne pour prendre en charge un système d'exploitation déterminé.</span><span class="sxs-lookup"><span data-stu-id="00887-114">You can associate a particular character encoding with a file to facilitate the display of your code in that language, as well as a line-ending type to support a particular operating system.</span></span> <span data-ttu-id="00887-115">De plus, certains caractères, lorsqu'ils sont utilisés dans des noms de fichiers, ne peuvent pas être enregistrés autrement qu'avec un encodage Unicode.</span><span class="sxs-lookup"><span data-stu-id="00887-115">Also, some characters, when used in file names, cannot be saved unless they are saved with Unicode encoding.</span></span>  
  
#### <a name="to-save-a-file-with-a-different-encoding-or-line-ending-type"></a><span data-ttu-id="00887-116">Pour enregistrer un fichier avec un encodage ou un type de fin de ligne différent</span><span class="sxs-lookup"><span data-stu-id="00887-116">To save a file with a different encoding or line ending type</span></span>  
  
1.  <span data-ttu-id="00887-117">Dans le menu **Fichier** , cliquez sur **Enregistrer \<filename> sous**.</span><span class="sxs-lookup"><span data-stu-id="00887-117">On the **File** menu, click **Save \<filename> As**.</span></span>  
  
2.  <span data-ttu-id="00887-118">Dans la boîte de dialogue **Enregistrer le fichier sous** , développez le bouton **Enregistrer** , puis cliquez sur **Enregistrer avec l’encodage**.</span><span class="sxs-lookup"><span data-stu-id="00887-118">In the **Save File As** dialog, expand the **Save** button, and then click **Save with Encoding**.</span></span>  
  
3.  <span data-ttu-id="00887-119">Dans la boîte de dialogue **Options d’enregistrement avancées** , sélectionnez l’encodage de votre choix dans la liste **Encodage** .</span><span class="sxs-lookup"><span data-stu-id="00887-119">In the **Advanced Save Options** dialog box, select the encoding you want from the **Encoding** list.</span></span>  
  
4.  <span data-ttu-id="00887-120">Dans la liste **Fins de ligne**, sélectionnez le type de fin de ligne souhaité.</span><span class="sxs-lookup"><span data-stu-id="00887-120">From the **Line Endings**list, select the type of line ending you want.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="00887-121">Si vous enregistrez votre fichier avec un encodage Unicode, il doit être archivé dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] comme un fichier binaire, car cette application ne prend pas en charge la fusion, la comparaison et l'affichage des différences entre les fichiers enregistrés au format Unicode.</span><span class="sxs-lookup"><span data-stu-id="00887-121">If you save your file your file with Unicode encoding, the file should be checked into [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual SourceSafe as a binary file because Visual SourceSafe does not support merging, comparing, and showing differences between files that are saved as Unicode.</span></span>  
  
 <span data-ttu-id="00887-122">Si vous utilisez Visual SourceSafe pour stocker des fichiers ANSI, UTF-8 ou Unicode, gardez à l'esprit les limites suivantes relatives à chacun de ces formats :</span><span class="sxs-lookup"><span data-stu-id="00887-122">If you are using Visual SourceSafe to store files with ANSI, UTF8, or Unicode, be aware of the following limitations for each:</span></span>  
  
-   <span data-ttu-id="00887-123">Les fichiers ANSI acceptent uniquement les caractères qui sont pris en charge dans la page de codes en cours, ce qui limite l'usage international.</span><span class="sxs-lookup"><span data-stu-id="00887-123">ANSI files allow only characters that are supported in the current code page, which limits international use.</span></span>  
  
-   <span data-ttu-id="00887-124">Les fichiers Unicode ne peuvent pas utiliser les fonctionnalités d'extraction en mode partagé, de contrôle des différences ou de fusion, car ils sont traités en tant que fichiers binaires.</span><span class="sxs-lookup"><span data-stu-id="00887-124">Unicode files cannot use shared checkout, difference checking, or merging functionality because they are handled as binary files.</span></span> <span data-ttu-id="00887-125">Vous pouvez utiliser ce format dans les fichiers internationaux.</span><span class="sxs-lookup"><span data-stu-id="00887-125">You can use this format in international files.</span></span>  
  
-   <span data-ttu-id="00887-126">Les fichiers UTF8 ne fonctionnent pas de façon fiable avec Visual SourceSafe, car les modifications doivent être apportées pendant l'archivage, l'extraction, le contrôle des différences et la fusion, ce qui provoque des problèmes pour les éditeurs de fichier UTF8.</span><span class="sxs-lookup"><span data-stu-id="00887-126">UTF8 files do not work safely with Visual SourceSafe because changes that cause problems for UTF8 file editors are made during check in, check out, difference checking, and merging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00887-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="00887-127">See Also</span></span>  
 <span data-ttu-id="00887-128">[Fichiers qui gèrent des solutions et des projets](files-that-manage-solutions-and-projects.md) </span><span class="sxs-lookup"><span data-stu-id="00887-128">[Files That Manage Solutions and Projects](files-that-manage-solutions-and-projects.md) </span></span>  
 [<span data-ttu-id="00887-129">Associer des extensions de fichier à un éditeur de code</span><span class="sxs-lookup"><span data-stu-id="00887-129">Associate File Extensions to a Code Editor</span></span>](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md)  
  
  
