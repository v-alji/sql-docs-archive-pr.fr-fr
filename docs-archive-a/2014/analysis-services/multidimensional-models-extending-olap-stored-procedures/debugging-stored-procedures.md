---
title: Débogage des procédures stockées | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- debugging stored procedures [Analysis Services]
- stored procedures [Analysis Services], debugging
ms.assetid: 34f51b85-02b3-40dd-bf93-375a9e522385
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4f5971fe611f06a413ca48b2bc91237a8c87ee8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700433"
---
# <a name="debugging-stored-procedures"></a><span data-ttu-id="6ea93-102">Débogage des procédures stockées</span><span class="sxs-lookup"><span data-stu-id="6ea93-102">Debugging Stored Procedures</span></span>
  <span data-ttu-id="6ea93-103">Les procédures stockées [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] sont en réalité des bibliothèques CLR ou COM (normalement des DLL) écrites en C# (ou dans tout autre langage CLR ou COM).</span><span class="sxs-lookup"><span data-stu-id="6ea93-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] stored procedures are actually CLR or COM libraries (normally DLLs) that are written in C# (or any other CLR or COM language).</span></span> <span data-ttu-id="6ea93-104">Par conséquent, le débogage d'une procédure stockée n'est pas sans ressembler à celui des autres applications dans l'environnement de débogage de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6ea93-104">Therefore, debugging a stored procedure is much like debugging any other application in the Visual Studio debugging environment.</span></span> <span data-ttu-id="6ea93-105">Pour déboguer les procédures stockées, l'environnement de développement de Visual Studio met à votre disposition ses fonctions de débogage intégrées.</span><span class="sxs-lookup"><span data-stu-id="6ea93-105">You debug stored procedures in the Visual Studio development environment using the integrated debugging functions.</span></span> <span data-ttu-id="6ea93-106">Ces fonctions vous permettent d'arrêter l'exécution aux emplacements des procédures, d'inspecter des valeurs en mémoire et dans le Registre, de modifier des variables, d'observer les échanges de messages et de regarder de près comment votre code fonctionne.</span><span class="sxs-lookup"><span data-stu-id="6ea93-106">These allow you to stop at procedure locations, inspect memory and register values, change variables, observe message traffic and get a close look at how your code works.</span></span>  
  
### <a name="to-debug-a-stored-procedure"></a><span data-ttu-id="6ea93-107">Pour déboguer une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="6ea93-107">To debug a stored procedure</span></span>  
  
1.  <span data-ttu-id="6ea93-108">Ouvrez le projet utilisé pour créer la DLL dans Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6ea93-108">Open the project used to create the DLL in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="6ea93-109">Créez des points d'arrêt dans la méthode ou la fonction correspondant à la procédure à déboguer.</span><span class="sxs-lookup"><span data-stu-id="6ea93-109">Create breakpoints in the method or function corresponding to the procedure you want to debug.</span></span>  
  
3.  <span data-ttu-id="6ea93-110">Utilisez Visual Studio pour créer une version debug d'une DLL de procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="6ea93-110">Use Visual Studio to create a debug build of a stored procedure DLL.</span></span>  
  
4.  <span data-ttu-id="6ea93-111">Déployez la DLL vers le serveur.</span><span class="sxs-lookup"><span data-stu-id="6ea93-111">Deploy the DLL to the server.</span></span> <span data-ttu-id="6ea93-112">Pour plus d’informations sur le déploiement de la DLL sur le serveur, consultez [création de procédures stockées](creating-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="6ea93-112">For more information about deploying the DLL to the server, see [Creating Stored Procedures](creating-stored-procedures.md).</span></span>  
  
5.  <span data-ttu-id="6ea93-113">Vous avez besoin d'une application qui appelle la procédure stockée que vous voulez tester.</span><span class="sxs-lookup"><span data-stu-id="6ea93-113">You need an application that calls the stored procedure that you want to test.</span></span> <span data-ttu-id="6ea93-114">Si vous n'avez pas d'application prête à jouer ce rôle, vous pouvez utiliser l'éditeur de requête MDX dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour créer une requête MDX qui appelle la procédure stockée à tester.</span><span class="sxs-lookup"><span data-stu-id="6ea93-114">If you do not have one ready, you can use the MDX Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to create an MDX query that calls the stored procedure that you want to test.</span></span>  
  
6.  <span data-ttu-id="6ea93-115">Dans Visual Studio, attachez la DLL au processus [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] (Msmdsrv.exe).</span><span class="sxs-lookup"><span data-stu-id="6ea93-115">In Visual Studio, attach to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] process (Msmdsrv.exe).</span></span>  
  
    1.  <span data-ttu-id="6ea93-116">Dans le menu **Déboguer** , choisissez **attacher toProcess**.</span><span class="sxs-lookup"><span data-stu-id="6ea93-116">From the **Debug** menu, choose **Attatch toProcess**.</span></span>  
  
    2.  <span data-ttu-id="6ea93-117">Dans la boîte de dialogue **attacher toProcess** , sélectionnez **afficher les processus de tous les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="6ea93-117">In the **Attatch toProcess** dialog box, select **Show processes from all users**.</span></span>  
  
    3.  <span data-ttu-id="6ea93-118">Dans la liste **processus disponibles** , dans la colonne **traiter** , cliquez sur **Msmdsrv.exe**.</span><span class="sxs-lookup"><span data-stu-id="6ea93-118">In the **Available Processes** list, in the **Process** column, click **Msmdsrv.exe**.</span></span> <span data-ttu-id="6ea93-119">S'il y a plus d'une instance de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] qui s'exécute sur le serveur, vous devez identifier le processus par l'identificateur de l'instance que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="6ea93-119">If there is more than one instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] running on the server, you need to identify the process by the ID of the instance you want to use.</span></span>  
  
    4.  <span data-ttu-id="6ea93-120">Dans la zone de texte **attacher à** , assurez-vous que le type de programme approprié est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="6ea93-120">In the **Attach to** text box, make sure that the appropriate program type is selected.</span></span> <span data-ttu-id="6ea93-121">Pour une DLL CLR, cliquez sur **Sélectionner**, puis sur **Déboguer ces types de codes**, sur **géré**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6ea93-121">For a CLR DLL, click **Select**, then click **Debug these code types**, then click **Managed**, then click **OK**.</span></span> <span data-ttu-id="6ea93-122">Pour une DLL COM, cliquez sur **Sélectionner**, puis sur **Déboguer ces types de codes**, sur **natif**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6ea93-122">For a COM DLL, click **Select**, then click **Debug these code types**, then click **Native**, then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="6ea93-123">Cliquez sur **Attacher**.</span><span class="sxs-lookup"><span data-stu-id="6ea93-123">Click **Attach**.</span></span>  
  
7.  <span data-ttu-id="6ea93-124">Dans [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], appelez le programme ou le script MDX qui appelle la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="6ea93-124">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], invoke the program or MDX script that calls the stored procedure.</span></span> <span data-ttu-id="6ea93-125">Le débogueur s'interrompt lorsqu'il atteint une ligne contenant un point d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="6ea93-125">The debugger breaks when it reaches a line containing a breakpoint.</span></span> <span data-ttu-id="6ea93-126">Vous pouvez évaluer des variables dans la fenêtre Espion, afficher des variables locales et exécuter le code en pas à pas.</span><span class="sxs-lookup"><span data-stu-id="6ea93-126">You can evaluate variables in the watch window, view locals, and step through the code.</span></span>  
  
 <span data-ttu-id="6ea93-127">Si le débogage d'une bibliothèque pose des problèmes, vérifiez que le fichier de base de données du programme (fichier PDB) correspondant a été copié vers l'emplacement du déploiement sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="6ea93-127">If you have problems debugging a library, make sure that the corresponding program database (PDB) file was copied to the deployment location on the server.</span></span> <span data-ttu-id="6ea93-128">Si ce fichier n'a pas été copié durant l'inscription ou le déploiement, vous devez le copier manuellement au même endroit que la DLL.</span><span class="sxs-lookup"><span data-stu-id="6ea93-128">If this file was not copied during registration or deployment, you must copy it manually to the same location as the DLL.</span></span> <span data-ttu-id="6ea93-129">Pour le code natif (DLL COM), le fichier PDB réside dans le sous-répertoire \debug.</span><span class="sxs-lookup"><span data-stu-id="6ea93-129">For native code (COM DLL), the PDB file resides in the \debug subdirectory.</span></span> <span data-ttu-id="6ea93-130">Pour le code managé (DLL CLR), il réside dans le sous-répertoire \WINDEBUG.</span><span class="sxs-lookup"><span data-stu-id="6ea93-130">For managed code (CLR DLL), it resides in the \WINDEBUG subdirectory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ea93-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6ea93-131">See Also</span></span>  
 <span data-ttu-id="6ea93-132">[Gestion des assemblys de modèles multidimensionnels](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="6ea93-132">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="6ea93-133">Définition de procédures stockées</span><span class="sxs-lookup"><span data-stu-id="6ea93-133">Defining Stored Procedures</span></span>](defining-stored-procedures.md)  
  
  
