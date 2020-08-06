---
title: Création de procédures stockées | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- registering assemblies
- database assemblies [Analysis Services]
- server assemblies [Analysis Services]
- stored procedures [Analysis Services], creating
- assemblies [Analysis Services]
ms.assetid: a12ff02f-6d0b-4488-9846-3609fc0d0554
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9a997244a2d54cca8732196107dd21927b5f9e2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700439"
---
# <a name="creating-stored-procedures"></a><span data-ttu-id="33aeb-102">Création de procédures stockées</span><span class="sxs-lookup"><span data-stu-id="33aeb-102">Creating Stored Procedures</span></span>
  <span data-ttu-id="33aeb-103">Toutes les procédures stockées doivent être associées à une classe CLR (Common Language Runtime) ou COM (Component Object Model) pour pouvoir être utilisées.</span><span class="sxs-lookup"><span data-stu-id="33aeb-103">All stored procedures must be associated with a common language runtime (CLR) or Component Object Model (COM) class in order to be used.</span></span> <span data-ttu-id="33aeb-104">La classe doit être installée sur le serveur, généralement sous la forme d’une [!INCLUDE[msCoName](../../includes/msconame-md.md)] bibliothèque de liens dynamiques (dll)® ActiveX, et inscrite en tant qu’assembly sur le serveur ou dans une [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] base de données.</span><span class="sxs-lookup"><span data-stu-id="33aeb-104">The class must be installed on the server - usually in the form of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX® dynamic link library (DLL) - and registered as an assembly on the server or in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="33aeb-105">Les procédures stockées sont enregistrées sur le serveur ou dans une base de données.</span><span class="sxs-lookup"><span data-stu-id="33aeb-105">Stored procedures are registered on a server or on a database.</span></span> <span data-ttu-id="33aeb-106">Les procédures stockées enregistrées sur le serveur peuvent être appelées à partir de n'importe quel contexte de requête.</span><span class="sxs-lookup"><span data-stu-id="33aeb-106">Server stored procedures can be called from any query context.</span></span> <span data-ttu-id="33aeb-107">Les procédures stockées enregistrées dans la base de données sont uniquement accessibles si le contexte de base de données est la base de données dans laquelle la procédure stockée est définie.</span><span class="sxs-lookup"><span data-stu-id="33aeb-107">Database stored procedures can only be accessed if the database context is the database under which the stored procedure is defined.</span></span> <span data-ttu-id="33aeb-108">Si les fonctions d'un assembly appellent les fonctions d'un autre assembly, vous devez enregistrer les deux assemblys dans le même contexte (serveur ou base de données).</span><span class="sxs-lookup"><span data-stu-id="33aeb-108">If functions in one assembly call functions in a different assembly, you must register both assemblies in the same context (server or database).</span></span> <span data-ttu-id="33aeb-109">Pour un serveur ou une [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] base de données déployée sur un serveur, vous pouvez utiliser [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour inscrire un assembly.</span><span class="sxs-lookup"><span data-stu-id="33aeb-109">For a server or a deployed [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database on a server, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to register an assembly.</span></span> <span data-ttu-id="33aeb-110">Pour un projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], vous pouvez utiliser le Concepteur [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] pour enregistrer un assembly dans le projet.</span><span class="sxs-lookup"><span data-stu-id="33aeb-110">For an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, you can use [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Designer to register an assembly in the project.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="33aeb-111">Les assemblys COM peuvent présenter un risque pour la sécurité.</span><span class="sxs-lookup"><span data-stu-id="33aeb-111">COM assemblies might pose a security risk.</span></span> <span data-ttu-id="33aeb-112">En raison de ce risque et d'autres considérations, les assemblys COM ont été déconseillés dans [!INCLUDE[ssASversion10](../../includes/ssasversion10-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33aeb-112">Due to this risk and other considerations, COM assemblies were deprecated in [!INCLUDE[ssASversion10](../../includes/ssasversion10-md.md)].</span></span> <span data-ttu-id="33aeb-113">Les assemblys COM peuvent ne pas être pris en charge dans les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="33aeb-113">COM assemblies might not be supported in future releases.</span></span>  
  
## <a name="registering-a-server-assembly"></a><span data-ttu-id="33aeb-114">Enregistrement d'un assembly de serveur</span><span class="sxs-lookup"><span data-stu-id="33aeb-114">Registering a Server Assembly</span></span>  
 <span data-ttu-id="33aeb-115">Dans l'Explorateur d'objets de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], les assemblys de serveur sont répertoriés dans le dossier Assemblies d'une instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33aeb-115">In Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], server assemblies are listed in the Assemblies folder under an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="33aeb-116">Les assemblys de serveur peuvent contenir à la fois des assemblys .NET (CLR) et des bibliothèques COM.</span><span class="sxs-lookup"><span data-stu-id="33aeb-116">Server assemblies can contain both .NET (CLR) assemblies and COM libraries.</span></span>  
  
### <a name="to-create-a-server-assembly"></a><span data-ttu-id="33aeb-117">Pour créer un assembly de serveur</span><span class="sxs-lookup"><span data-stu-id="33aeb-117">To create a server assembly</span></span>  
  
1.  <span data-ttu-id="33aeb-118">Développez l’instance de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dans l’Explorateur d’objets, cliquez avec le bouton droit sur le dossier **assemblys** , puis cliquez sur **nouvel assembly**.</span><span class="sxs-lookup"><span data-stu-id="33aeb-118">Expand the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in Object Explorer, right-click the **Assemblies** folder, and then click **New Assembly**.</span></span> <span data-ttu-id="33aeb-119">La boîte de dialogue **inscrire un assembly de serveur** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="33aeb-119">This displays the **Register Server Assembly** dialog box.</span></span>  
  
2.  <span data-ttu-id="33aeb-120">Pour **type** , spécifiez le type d’assembly :</span><span class="sxs-lookup"><span data-stu-id="33aeb-120">For **Type** specify the type of assembly:</span></span>  
  
    -   <span data-ttu-id="33aeb-121">Pour une DLL en code managé (CLR), spécifiez Assembly .NET.</span><span class="sxs-lookup"><span data-stu-id="33aeb-121">For a managed code (CLR) DLL, specify .NET Assembly.</span></span>  
  
    -   <span data-ttu-id="33aeb-122">Pour une DLL de code natif (COM), spécifiez la DLL COM.</span><span class="sxs-lookup"><span data-stu-id="33aeb-122">For a native code (COM) DLL, specify COM DLL.</span></span>  
  
3.  <span data-ttu-id="33aeb-123">Pour **nom de fichier**, spécifiez la dll contenant les procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="33aeb-123">For **File name**, specify the DLL containing the stored procedures.</span></span>  
  
4.  <span data-ttu-id="33aeb-124">Pour **nom de l’assembly**, spécifiez un nom pour l’assembly.</span><span class="sxs-lookup"><span data-stu-id="33aeb-124">For **Assembly name**, specify a name for the assembly.</span></span>  
  
5.  <span data-ttu-id="33aeb-125">S’il s’agit d’une version de débogage de la bibliothèque que vous allez utiliser pour déboguer des procédures stockées, activez la case à cocher **inclure les informations de débogage** .</span><span class="sxs-lookup"><span data-stu-id="33aeb-125">If this is a debug build of the library that you are going to use to debug stored procedures, select the **Include debug information** check box.</span></span> <span data-ttu-id="33aeb-126">Pour plus d’informations sur le débogage des procédures stockées, consultez [débogage de procédures stockées](debugging-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="33aeb-126">For more information about debugging stored procedures, see [Debugging Stored Procedures](debugging-stored-procedures.md).</span></span>  
  
6.  <span data-ttu-id="33aeb-127">Vous pouvez cliquer sur **OK** pour inscrire l’assembly immédiatement, ou dans la barre d’outils de la boîte de dialogue, vous pouvez cliquer sur une commande du menu **script** pour générer un script de l’action d’inscription dans une fenêtre de requête, un fichier ou le presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="33aeb-127">You can click **OK** to register the assembly immediately, or on the dialog box toolbar, you can click a command on the **Script** menu to script the registration action to a query window, a file, or the Clipboard.</span></span>  
  
 <span data-ttu-id="33aeb-128">Une fois que vous avez inscrit un assembly de serveur, vous pouvez le configurer en cliquant avec le bouton droit sur l’assembly dans l’Explorateur d’objets, puis en cliquant sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="33aeb-128">After you register a server assembly, you can configure it by right-clicking the assembly in Object Explorer and then clicking **Properties**.</span></span>  
  
## <a name="registering-a-database-assembly-on-the-server"></a><span data-ttu-id="33aeb-129">Enregistrement d'un assembly de base de données sur le serveur</span><span class="sxs-lookup"><span data-stu-id="33aeb-129">Registering a Database Assembly on the Server</span></span>  
 <span data-ttu-id="33aeb-130">Dans l'Explorateur d'objets de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], les assemblys de base de données sont répertoriés dans le dossier Assemblies d'une base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33aeb-130">In Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], database assemblies are listed in the Assemblies folder under an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="33aeb-131">Les assemblys de base de données peuvent contenir à la fois des assemblys .NET (CLR) et des bibliothèques COM.</span><span class="sxs-lookup"><span data-stu-id="33aeb-131">Database assemblies can contain both .NET (CLR) assemblies and COM libraries.</span></span>  
  
### <a name="to-create-a-database-assembly-on-a-server"></a><span data-ttu-id="33aeb-132">Pour créer un assembly de base de données sur un serveur</span><span class="sxs-lookup"><span data-stu-id="33aeb-132">To create a database assembly on a server</span></span>  
  
1.  <span data-ttu-id="33aeb-133">Développez l’instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] de la base de données dans l’Explorateur d’objets, cliquez avec le bouton droit sur le dossier **assemblys** , puis cliquez sur **nouvel assembly**.</span><span class="sxs-lookup"><span data-stu-id="33aeb-133">Expand the instance the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in Object Explorer, right-click the **Assemblies** folder, and then click **New Assembly**.</span></span> <span data-ttu-id="33aeb-134">La boîte **de dialogue inscrire l’assembly de base de données** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="33aeb-134">This displays the **Register Database Assembly** dialog box.</span></span>  
  
2.  <span data-ttu-id="33aeb-135">Pour **type** , spécifiez le type d’assembly :</span><span class="sxs-lookup"><span data-stu-id="33aeb-135">For **Type** specify the type of assembly:</span></span>  
  
    -   <span data-ttu-id="33aeb-136">Pour une DLL en code managé (CLR), spécifiez Assembly .NET.</span><span class="sxs-lookup"><span data-stu-id="33aeb-136">For a managed code (CLR) DLL, specify .NET Assembly.</span></span>  
  
    -   <span data-ttu-id="33aeb-137">Pour une DLL en code natif (COM), spécifiez DLL COM.</span><span class="sxs-lookup"><span data-stu-id="33aeb-137">For a native code (COM) DLL), specify COM DLL.</span></span>  
  
3.  <span data-ttu-id="33aeb-138">Pour **nom de fichier**, spécifiez la dll contenant les procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="33aeb-138">For **File name**, specify the DLL containing the stored procedures.</span></span>  
  
4.  <span data-ttu-id="33aeb-139">Pour **nom de l’assembly**, spécifiez un nom pour l’assembly.</span><span class="sxs-lookup"><span data-stu-id="33aeb-139">For **Assembly name**, specify a name for the assembly.</span></span>  
  
5.  <span data-ttu-id="33aeb-140">S’il s’agit d’une version de débogage de la bibliothèque que vous allez utiliser pour déboguer des procédures stockées, activez la case à cocher **inclure les informations de débogage** .</span><span class="sxs-lookup"><span data-stu-id="33aeb-140">If this is a debug build of the library that you are going to use to debug stored procedures, select the **Include debug information** check box.</span></span> <span data-ttu-id="33aeb-141">Pour plus d’informations sur le débogage des procédures stockées, consultez [débogage de procédures stockées](debugging-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="33aeb-141">For more information about debugging stored procedures, see [Debugging Stored Procedures](debugging-stored-procedures.md).</span></span>  
  
6.  <span data-ttu-id="33aeb-142">Vous pouvez cliquer sur **OK** pour inscrire l’assembly immédiatement, ou dans la barre d’outils de la boîte de dialogue, vous pouvez cliquer sur une commande du menu **script** pour générer un script de l’action d’inscription dans une fenêtre de requête, un fichier ou le presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="33aeb-142">You can click **OK** to register the assembly immediately, or on the dialog box toolbar, you can click a command on the **Script** menu to script the registration action to a query window, a file, or the Clipboard.</span></span>  
  
 <span data-ttu-id="33aeb-143">Une fois que vous avez inscrit un assembly de base de données, vous pouvez le configurer en cliquant avec le bouton droit sur l’assembly dans l’Explorateur d’objets, puis en cliquant sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="33aeb-143">After you register a database assembly, you can configure it by right-clicking the assembly in Object Explorer and then clicking **Properties**.</span></span>  
  
## <a name="registering-a-database-assembly-in-a-project"></a><span data-ttu-id="33aeb-144">Enregistrement d'un assembly de base de données dans un projet</span><span class="sxs-lookup"><span data-stu-id="33aeb-144">Registering a Database Assembly in a Project</span></span>  
 <span data-ttu-id="33aeb-145">Dans l'Explorateur de solutions de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], les assemblys de base de données sont répertoriés dans le dossier Assemblies d'un projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33aeb-145">In Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], database assemblies are listed in the Assemblies folder under an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="33aeb-146">Les assemblys de base de données peuvent contenir à la fois des assemblys .NET (CLR) et des bibliothèques COM.</span><span class="sxs-lookup"><span data-stu-id="33aeb-146">Database assemblies can contain both .NET (CLR) assemblies and COM libraries.</span></span>  
  
### <a name="to-create-a-database-assembly-in-an-analysis-service-project"></a><span data-ttu-id="33aeb-147">Pour créer un assembly de base de données dans un projet Analysis Service</span><span class="sxs-lookup"><span data-stu-id="33aeb-147">To create a database assembly in an Analysis Service project</span></span>  
  
1.  <span data-ttu-id="33aeb-148">Développez l’instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] de la base de données dans l’Explorateur d’objets, cliquez avec le bouton droit sur le dossier **assemblys** , puis cliquez sur **nouvelle référence d’assembly**.</span><span class="sxs-lookup"><span data-stu-id="33aeb-148">Expand the instance the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in Object Explorer, right-click the **Assemblies** folder, and then click **New Assembly Reference**.</span></span> <span data-ttu-id="33aeb-149">La boîte de dialogue **Ajouter une référence** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="33aeb-149">This displays the **Add Reference** dialog box.</span></span> <span data-ttu-id="33aeb-150">L’onglet **.net** de la boîte de dialogue **Ajouter une référence** répertorie les assemblys .net (CLR) existants, tandis que l’onglet **projets** répertorie les projets.</span><span class="sxs-lookup"><span data-stu-id="33aeb-150">The **.NET** tab of the **Add Reference** dialog box lists existing .NET (CLR) assemblies, while the **Projects** tab lists projects.</span></span>  
  
2.  <span data-ttu-id="33aeb-151">Vous pouvez cliquer sur un composant ou un projet existant, puis cliquer sur **Ajouter** pour l’ajouter au [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projet.</span><span class="sxs-lookup"><span data-stu-id="33aeb-151">You can click an existing component or project and then click **Add** to add it to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="33aeb-152">Pour ajouter une référence à une DLL COM, cliquez sur l’onglet **Parcourir** pour rechercher le fichier.</span><span class="sxs-lookup"><span data-stu-id="33aeb-152">To add a reference to a COM DLL, click the **Browse** tab to find the file.</span></span> <span data-ttu-id="33aeb-153">La liste **projets et composants sélectionnés** affiche le nom, le type, la version et l’emplacement de chaque composant que vous ajoutez au projet.</span><span class="sxs-lookup"><span data-stu-id="33aeb-153">The **Selected projects and components** list shows the name, type, version, and location for each component that you are adding to the project.</span></span>  
  
3.  <span data-ttu-id="33aeb-154">Lorsque vous avez terminé de sélectionner les composants à ajouter, cliquez sur **OK** pour les ajouter au [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projet.</span><span class="sxs-lookup"><span data-stu-id="33aeb-154">When you are finished selecting components to add, click **OK** to add them to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span>  
  
## <a name="script-format-for-an-assembly"></a><span data-ttu-id="33aeb-155">Mise en forme du script pour un assembly</span><span class="sxs-lookup"><span data-stu-id="33aeb-155">Script Format For an Assembly</span></span>  
 <span data-ttu-id="33aeb-156">Il est relativement simple d'enregistrer un assembly .NET.</span><span class="sxs-lookup"><span data-stu-id="33aeb-156">Registering a .NET assembly is fairly simple.</span></span> <span data-ttu-id="33aeb-157">Un assembly .NET est ajouté à une base de données au format binaire à l'aide du format suivant :</span><span class="sxs-lookup"><span data-stu-id="33aeb-157">A .NET assembly is added to a database in binary format using the following format:</span></span>  
  
```  
<Create>  
   <ObjectDefinition>  
      <Assembly>  
         <Files>  
            <File>  
               <Name>filename</Name>  
               <Type>filetype</Type>  
               <Data>  
                  <Block>binarydatablock</Block>  
                  <Block>binarydatablock</Block>  
                  ...  
               </Data>  
            </File>  
         </Files>  
         <PermissionSet>PermissionSet</PermissionSet>  
      </Assembly>  
   <ObjectDefinition>  
</Create>  
```  
  
## <a name="see-also"></a><span data-ttu-id="33aeb-158">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="33aeb-158">See Also</span></span>  
 <span data-ttu-id="33aeb-159">[Gestion des assemblys de modèles multidimensionnels](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="33aeb-159">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="33aeb-160">Définition de procédures stockées</span><span class="sxs-lookup"><span data-stu-id="33aeb-160">Defining Stored Procedures</span></span>](defining-stored-procedures.md)  
  
  
