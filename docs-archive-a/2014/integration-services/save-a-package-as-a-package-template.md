---
title: Enregistrer un package en tant que modèle de package | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- reusing packages
- templates [Integration Services]
ms.assetid: efe66cec-3933-4f6e-8d35-fe3d300de66c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 30bddb5a343e7c7aef279bc66c25be30a2cf1a12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698424"
---
# <a name="save-a-package-as-a-package-template"></a><span data-ttu-id="8b56f-102">Enregistrer un package en tant que modèle de package</span><span class="sxs-lookup"><span data-stu-id="8b56f-102">Save a Package as a Package Template</span></span>
  <span data-ttu-id="8b56f-103">Cette rubrique indique comment désigner et utiliser des packages personnalisés comme modèles lorsque que vous créez de nouveaux packages Integration Services dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b56f-103">This topic describes how to designate and use custom packages as templates when you create new Integration Services packages in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="8b56f-104">Par défaut, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] utilise un modèle de package qui crée un package vide lorsque vous ajoutez un nouveau package à un projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8b56f-104">By default, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] uses a package template that creates an empty package when you add a new package to an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="8b56f-105">Vous ne pouvez pas remplacer ce modèle par défaut, mais vous pouvez en ajouter de nouveaux.</span><span class="sxs-lookup"><span data-stu-id="8b56f-105">You cannot replace this default template, but you can add new templates.</span></span>  
  
 <span data-ttu-id="8b56f-106">Vous pouvez désigner plusieurs packages à utiliser comme modèles.</span><span class="sxs-lookup"><span data-stu-id="8b56f-106">You can designate multiple packages to use as templates.</span></span> <span data-ttu-id="8b56f-107">Avant de pouvoir implémenter de nouveaux packages personnalisés comme modèles, vous devez créer les packages.</span><span class="sxs-lookup"><span data-stu-id="8b56f-107">Before you can implement custom packages as templates, you must create the packages.</span></span>  
  
 <span data-ttu-id="8b56f-108">Lorsque vous créez un package en utilisant des packages personnalisés comme modèles, les nouveaux packages portent le même nom et le même GUID que le modèle.</span><span class="sxs-lookup"><span data-stu-id="8b56f-108">When you create package using custom packages as templates, the new packages have the same name and GUID as the template.</span></span> <span data-ttu-id="8b56f-109">Pour différencier les packages, il faut mettre à jour la valeur de la propriété `Name` et générer un nouveau GUID pour la propriété `ID`.</span><span class="sxs-lookup"><span data-stu-id="8b56f-109">To differentiate among packages you should update the value of the `Name` property and generate a new GUID for the `ID` property.</span></span> <span data-ttu-id="8b56f-110">Pour plus d’informations, consultez [Créer des packages dans les outils de données SQL Server](create-packages-in-sql-server-data-tools.md) et [Définir les propriétés d’un package](set-package-properties.md).</span><span class="sxs-lookup"><span data-stu-id="8b56f-110">For more information, see [Create Packages in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) and [Set Package Properties](set-package-properties.md).</span></span>  
  
### <a name="to-designate-a-custom-package-as-a-package-template"></a><span data-ttu-id="8b56f-111">Pour désigner un package personnalisé comme modèle de package</span><span class="sxs-lookup"><span data-stu-id="8b56f-111">To designate a custom package as a package template</span></span>  
  
1.  <span data-ttu-id="8b56f-112">Dans le système de fichiers, localisez le package que vous souhaitez utiliser comme modèle.</span><span class="sxs-lookup"><span data-stu-id="8b56f-112">In the file system, locate the package that you want to use as template.</span></span>  
  
2.  <span data-ttu-id="8b56f-113">Copiez le package dans le dossier DataTransformationItems.</span><span class="sxs-lookup"><span data-stu-id="8b56f-113">Copy the package to the DataTransformationItems folder.</span></span> <span data-ttu-id="8b56f-114">Par défaut ce dossier se trouve dans C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies\ProjectItems\DataTransformationProject.</span><span class="sxs-lookup"><span data-stu-id="8b56f-114">By default this folder is in C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies\ProjectItems\DataTransformationProject.</span></span>  
  
3.  <span data-ttu-id="8b56f-115">Recommencez les étapes 1 et 2 pour chaque package que vous souhaitez utiliser comme modèle.</span><span class="sxs-lookup"><span data-stu-id="8b56f-115">Repeat steps 1 and 2 for each package that you want to use as a template.</span></span>  
  
### <a name="to-use-a-custom-package-as-a-package-template"></a><span data-ttu-id="8b56f-116">Pour utiliser un package personnalisé comme modèle de package</span><span class="sxs-lookup"><span data-stu-id="8b56f-116">To use a custom package as a package template</span></span>  
  
1.  <span data-ttu-id="8b56f-117">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] dans lequel vous souhaitez créer un package.</span><span class="sxs-lookup"><span data-stu-id="8b56f-117">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in which you want to create a package.</span></span>  
  
2.  <span data-ttu-id="8b56f-118">Dans l’Explorateur de solutions, cliquez avec le bouton droit sur le projet, pointez sur **Ajouter**, puis cliquez sur **Nouvel élément**.</span><span class="sxs-lookup"><span data-stu-id="8b56f-118">In Solution Explorer, right-click the project, point to **Add**, and then click **New Item**.</span></span>  
  
3.  <span data-ttu-id="8b56f-119">Dans la boîte de dialogue **Ajouter un nouvel élément - \<project name>** , cliquez sur le package que vous souhaitez utiliser comme modèle.</span><span class="sxs-lookup"><span data-stu-id="8b56f-119">In the **Add New Item -\<project name>** dialog box, click the package that you want to use as a template.</span></span>  
  
     <span data-ttu-id="8b56f-120">La liste de modèles inclut le modèle de package par défaut nommé Nouveau package SSIS.</span><span class="sxs-lookup"><span data-stu-id="8b56f-120">The list of templates includes the default package template named New SSIS Package.</span></span> <span data-ttu-id="8b56f-121">L'icône de package identifie les modèles pouvant être utilisés comme modèles de packages.</span><span class="sxs-lookup"><span data-stu-id="8b56f-121">The package icon identifies templates that can be used as package templates.</span></span>  
  
4.  <span data-ttu-id="8b56f-122">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="8b56f-122">Click **Add**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b56f-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8b56f-123">See Also</span></span>  
 <span data-ttu-id="8b56f-124">[Créer des packages dans SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) </span><span class="sxs-lookup"><span data-stu-id="8b56f-124">[Create Packages in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) </span></span>  
 [<span data-ttu-id="8b56f-125">Packages Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="8b56f-125">Integration Services &#40;SSIS&#41; Packages</span></span>](../../2014/integration-services/integration-services-ssis-packages.md)  
  
  
