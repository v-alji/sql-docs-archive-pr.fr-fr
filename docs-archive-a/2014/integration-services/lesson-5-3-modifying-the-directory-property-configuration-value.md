---
title: 'Étape 3 : Modification de la valeur de configuration de la propriété Directory | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ba2a091f-361c-4331-afe2-53b465164c36
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a71a7a181322d60caca98da4ddf3261cbce99c9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602883"
---
# <a name="step-3-modifying-the-directory-property-configuration-value"></a><span data-ttu-id="54ab1-102">Étape 3 : Modification de la valeur de configuration de la propriété Directory</span><span class="sxs-lookup"><span data-stu-id="54ab1-102">Step 3: Modifying the Directory Property Configuration Value</span></span>
  <span data-ttu-id="54ab1-103">Dans cette tâche, vous modifiez le paramètre de configuration (stocké dans le fichier SSISTutorial.dtsConfig) pour la propriété Value de la variable de niveau package `User::varFolderName`.</span><span class="sxs-lookup"><span data-stu-id="54ab1-103">In this task, you will modify the configuration setting, stored in the SSISTutorial.dtsConfig file, for the Value property of the package-level variable `User::varFolderName`.</span></span> <span data-ttu-id="54ab1-104">Cette variable met à jour la propriété Directory du conteneur de boucles Foreach.</span><span class="sxs-lookup"><span data-stu-id="54ab1-104">The variable updates the Directory property of the Foreach Loop container.</span></span> <span data-ttu-id="54ab1-105">La valeur modifiée pointe vers le `New Sample Data` dossier que vous avez créé lors de la tâche précédente.</span><span class="sxs-lookup"><span data-stu-id="54ab1-105">The modified value will point to the `New Sample Data` folder that you created in the previous task.</span></span> <span data-ttu-id="54ab1-106">Une fois le paramètre de configuration modifié et le package exécuté, la propriété Directory est mise à jour par la variable, en utilisant la valeur récupérée dans le fichier de configuration au lieu de la valeur de la propriété Directory configurée au départ dans le package.</span><span class="sxs-lookup"><span data-stu-id="54ab1-106">After you modify the configuration setting and run the package, the Directory property will be updated by the variable, using the value populated from the configuration file instead of the directory value originally configured in the package.</span></span>  
  
### <a name="to-modify-the-configuration-setting-of-the-directory-property"></a><span data-ttu-id="54ab1-107">Pour modifier le paramétrage de configuration de la propriété Directory</span><span class="sxs-lookup"><span data-stu-id="54ab1-107">To modify the configuration setting of the Directory property</span></span>  
  
1.  <span data-ttu-id="54ab1-108">Dans le Bloc-notes ou dans tout autre éditeur de texte, recherchez et ouvrez le fichier de configuration SSISTutorial.dtsConfig que vous avez créé à l'aide de l'Assistant Configuration de package au cours de la tâche précédente.</span><span class="sxs-lookup"><span data-stu-id="54ab1-108">In Notepad or any other text editor, locate and open the SSISTutorial.dtsConfig configuration file that you created by using the Package Configuration Wizard in the previous task.</span></span>  
  
2.  <span data-ttu-id="54ab1-109">Modifiez la valeur de l’élément **ConfiguredValue** pour qu’elle corresponde au chemin d’accès du `New Sample Data` dossier que vous avez créé lors de la tâche précédente.</span><span class="sxs-lookup"><span data-stu-id="54ab1-109">Change the value of the **ConfiguredValue** element to match the path of the `New Sample Data` folder that you created in the previous task.</span></span> <span data-ttu-id="54ab1-110">N'encadrez pas le chemin d'accès de guillemets.</span><span class="sxs-lookup"><span data-stu-id="54ab1-110">Do not surround the path in quotes.</span></span> <span data-ttu-id="54ab1-111">Si le `New Sample Data` dossier se trouve au niveau racine de votre lecteur (par exemple, C : \\ ), le code XML mis à jour doit ressembler à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="54ab1-111">If the `New Sample Data` folder is at the root level of your drive (for example, C:\\), the updated XML should be similar to the following sample:</span></span>  
  
     `<?xml version="1.0"?><DTSConfiguration><DTSConfigurationHeading><DTSConfigurationFileInfo GeneratedBy="DOMAIN\UserName" GeneratedFromPackageName="Lesson 5" GeneratedFromPackageID="{F4475E73-59E3-478F-8EB2-B10AFA61D3FA}" GeneratedDate="6/10/2012 8:16:50 AM"/></DTSConfigurationHeading><Configuration ConfiguredType="Property" Path="\Package.Variables[User::varFolderName].Properties[Value]" ValueType="String"><ConfiguredValue></ConfiguredValue></Configuration></DTSConfiguration>`  
  
     <span data-ttu-id="54ab1-112">Les informations d’en-tête,, `GeneratedBy` `GeneratedFromPackageID` et **GeneratedDate** sont différentes dans votre fichier, bien sûr.</span><span class="sxs-lookup"><span data-stu-id="54ab1-112">The heading information, `GeneratedBy`, `GeneratedFromPackageID`, and **GeneratedDate** will be different in your file, of course.</span></span> <span data-ttu-id="54ab1-113">L'élément à noter est l'élément `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="54ab1-113">The element to note is the `Configuration` element.</span></span> <span data-ttu-id="54ab1-114">La propriété `Value` de la variable `User::varFolderName` contient maintenant C:\New Sample Data.</span><span class="sxs-lookup"><span data-stu-id="54ab1-114">The `Value` property of the variable, `User::varFolderName`, now contains C:\New Sample Data.</span></span>  
  
3.  <span data-ttu-id="54ab1-115">Enregistrez les modifications, puis fermez l'éditeur de texte.</span><span class="sxs-lookup"><span data-stu-id="54ab1-115">Save the change, and then close the text editor.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="54ab1-116">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="54ab1-116">Next Task in Lesson</span></span>  
 [<span data-ttu-id="54ab1-117">Étape 4 : Test du package du tutoriel de la leçon 5</span><span class="sxs-lookup"><span data-stu-id="54ab1-117">Step 4: Testing the Lesson 5 Tutorial Package</span></span>](../integration-services/lesson-5-4-testing-the-lesson-5-tutorial-package.md)  
  
  
