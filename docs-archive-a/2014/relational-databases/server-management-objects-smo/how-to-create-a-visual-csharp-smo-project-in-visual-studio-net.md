---
title: Créer un projet SMO Visual C# dans Visual Studio .NET | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- Visual C# [SMO]
ms.assetid: 1e7abb16-23a0-4a18-91ad-253261e6bf84
author: stevestein
ms.author: sstein
ms.openlocfilehash: b78820fafd37675332e6703cabbb87e78bde5864
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611719"
---
# <a name="create-a-visual-c-smo-project-in-visual-studio-net"></a><span data-ttu-id="730be-102">Créer un projet SMO Visual C# dans Visual Studio .NET</span><span class="sxs-lookup"><span data-stu-id="730be-102">Create a Visual C# SMO Project in Visual Studio .NET</span></span>
  <span data-ttu-id="730be-103">Cette section décrit comment élaborer une application de console SMO simple.</span><span class="sxs-lookup"><span data-stu-id="730be-103">This section describes how to build a simple SMO console application.</span></span>  
  
 <span data-ttu-id="730be-104">Cet exemple importe des espaces de noms, qui permettent au programme de référencer des types SMO.</span><span class="sxs-lookup"><span data-stu-id="730be-104">This example imports namespaces, which enables the program to reference SMO types.</span></span> <span data-ttu-id="730be-105">L'importation de l'espace de noms `Agent` est facultative.</span><span class="sxs-lookup"><span data-stu-id="730be-105">The import of the `Agent` namespace is optional.</span></span> <span data-ttu-id="730be-106">Utilisez-le quand vous écrivez un programme qui utilise [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] l’agent.</span><span class="sxs-lookup"><span data-stu-id="730be-106">Use it when you are writing a program that uses [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="730be-107">L'espace de noms `Common` est requis pour établir une connexion sécurisée avec l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="730be-107">The `Common` namespace is required to establish a secure connection to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="730be-108">L'espace de noms `SqlClient` est utilisé pour traiter les erreurs d'exception SQL.</span><span class="sxs-lookup"><span data-stu-id="730be-108">The `SqlClient` namespace is used to process SQL exception errors.</span></span>  
  
### <a name="creating-a-visual-c-smo-project-in-visual-studionet"></a><span data-ttu-id="730be-109">Création d'un projet SMO Visual C# dans Visual Studio.NET</span><span class="sxs-lookup"><span data-stu-id="730be-109">Creating a Visual C# SMO project in Visual Studio.NET</span></span>  
  
1.  <span data-ttu-id="730be-110">Démarrez [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] (ou [!INCLUDE[vsprvslong](../../includes/vsprvslong-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="730be-110">Start [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] (or [!INCLUDE[vsprvslong](../../includes/vsprvslong-md.md)]).</span></span>  
  
2.  <span data-ttu-id="730be-111">Dans le menu **Fichier**, cliquez sur **Nouveau projet**.</span><span class="sxs-lookup"><span data-stu-id="730be-111">On the **File** menu, click **NewProject.**</span></span> <span data-ttu-id="730be-112">La boîte de dialogue **Nouveau projet** apparaît.</span><span class="sxs-lookup"><span data-stu-id="730be-112">The **New Project** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="730be-113">Dans la boîte de dialogue **types de projets** , sélectionnez **Visual C#**, puis sélectionnez **Windows**.</span><span class="sxs-lookup"><span data-stu-id="730be-113">In **Project Types** dialog box, select **Visual C#**, and then select **Windows**.</span></span> <span data-ttu-id="730be-114">Dans le [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] volet Modèles installés, sélectionnez **application Windows**.</span><span class="sxs-lookup"><span data-stu-id="730be-114">In the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Installed Templates pane, select **Windows Application**.</span></span>  
  
4.  <span data-ttu-id="730be-115">Facultatif Dans le champ **nom** , tapez le nom de la nouvelle application.</span><span class="sxs-lookup"><span data-stu-id="730be-115">(Optional) In the **Name** field, type the name of the new application</span></span>  
  
5.  <span data-ttu-id="730be-116">Sélectionnez le type d'application Visual C#.</span><span class="sxs-lookup"><span data-stu-id="730be-116">Select the Visual C# application type.</span></span> <span data-ttu-id="730be-117">Pour les exemples qui suivent, sélectionnez **application console**.</span><span class="sxs-lookup"><span data-stu-id="730be-117">For the examples that follow, select **Console Application**.</span></span>  
  
6.  <span data-ttu-id="730be-118">Dans le menu **Projet**, sélectionnez **Ajouter une référence**.</span><span class="sxs-lookup"><span data-stu-id="730be-118">On the **Project** menu, select **Add Reference**.</span></span> <span data-ttu-id="730be-119">La boîte de dialogue **Ajouter une référence** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="730be-119">The **Add Reference** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="730be-120">Cliquez sur **Parcourir**, recherchez les assemblys Smo dans le [!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)] dossier, puis sélectionnez les fichiers suivants.</span><span class="sxs-lookup"><span data-stu-id="730be-120">Click **Browse**, locate the SMO assemblies in the [!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)] folder, and then select the following files.</span></span> <span data-ttu-id="730be-121">Il s'agit des fichiers minimum requis pour générer une application SMO :</span><span class="sxs-lookup"><span data-stu-id="730be-121">These are the minimum files that are required to build an SMO application:</span></span>  
  
     <span data-ttu-id="730be-122">Microsoft.SqlServer.ConnectionInfo.dll</span><span class="sxs-lookup"><span data-stu-id="730be-122">Microsoft.SqlServer.ConnectionInfo.dll</span></span>  
  
     <span data-ttu-id="730be-123">Microsoft.SqlServer.Smo.dll</span><span class="sxs-lookup"><span data-stu-id="730be-123">Microsoft.SqlServer.Smo.dll</span></span>  
  
     <span data-ttu-id="730be-124">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span><span class="sxs-lookup"><span data-stu-id="730be-124">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span></span>  
  
     <span data-ttu-id="730be-125">Microsoft.SqlServer.SqlEnum.dll</span><span class="sxs-lookup"><span data-stu-id="730be-125">Microsoft.SqlServer.SqlEnum.dll</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="730be-126">Utilisez la touche `Ctrl` pour sélectionner plusieurs fichiers.</span><span class="sxs-lookup"><span data-stu-id="730be-126">Use the `Ctrl` key to select more than one file.</span></span>  
  
8.  <span data-ttu-id="730be-127">Ajoutez les autres assemblys SMO qui sont nécessaires.</span><span class="sxs-lookup"><span data-stu-id="730be-127">Add any additional SMO assemblies that are required.</span></span> <span data-ttu-id="730be-128">Par exemple, si vous programmez spécifiquement [!INCLUDE[ssSB](../../includes/sssb-md.md)], ajoutez les assemblys suivants :</span><span class="sxs-lookup"><span data-stu-id="730be-128">For example, if you are specifically programming [!INCLUDE[ssSB](../../includes/sssb-md.md)], add the following assemblies:</span></span>  
  
     <span data-ttu-id="730be-129">Microsoft.SqlServer.ServiceBrokerEmum.dll</span><span class="sxs-lookup"><span data-stu-id="730be-129">Microsoft.SqlServer.ServiceBrokerEmum.dll</span></span>  
  
9. <span data-ttu-id="730be-130">Cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="730be-130">Click **Open**.</span></span>  
  
10. <span data-ttu-id="730be-131">Dans le menu **affichage** , cliquez sur **code**.-ou-sélectionnez le Program1.cs [conception] Windows et double-cliquez sur le Windows Form pour afficher la fenêtre de code.</span><span class="sxs-lookup"><span data-stu-id="730be-131">On the **View** menu, click **Code**.-Or-Select the Program1.cs [Design] Windows and double-click the windows form to show the code window.</span></span>  
  
11. <span data-ttu-id="730be-132">Dans le code, avant l'instruction d'espace de noms, tapez les instructions `using` suivantes pour qualifier les types dans l'espace de noms SMO :</span><span class="sxs-lookup"><span data-stu-id="730be-132">In the code, before the namespace statement, type the following `using` statements to qualify the types in the SMO namespace:</span></span>  
  
    ```  
    using Microsoft.SqlServer.Management.Smo;  
    using Microsoft.SqlServer.Management.Common;  
    ```  
  
12. <span data-ttu-id="730be-133">SMO comporte différents espaces de noms sous Microsoft.SqlServer.Management.Smo, par exemple Microsoft.SqlServer.Management.Smo.Agent.</span><span class="sxs-lookup"><span data-stu-id="730be-133">SMO has various namespaces under Microsoft.SqlServer.Management.Smo, such as Microsoft.SqlServer.Management.Smo.Agent.</span></span> <span data-ttu-id="730be-134">Ajoutez ces espaces de noms lorsqu'ils sont requis.</span><span class="sxs-lookup"><span data-stu-id="730be-134">Add these namespaces as they are required.</span></span>  
  
13. <span data-ttu-id="730be-135">Vous pouvez à présent ajouter votre code SMO.</span><span class="sxs-lookup"><span data-stu-id="730be-135">You can now add your SMO code.</span></span>  
  
  
