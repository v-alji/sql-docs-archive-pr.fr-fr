---
title: Créer un projet Visual Basic SMO dans Visual Studio .NET | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic [SMO]
ms.assetid: d7a3892c-0f1c-4c4d-8480-b58dce3720bc
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 844d27ab6aadbc972c6282c79adb13e15d55c322
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709907"
---
# <a name="create-a-visual-basic-smo-project-in-visual-studio-net"></a><span data-ttu-id="84445-102">Créer un projet SMO Visual Basic dans Visual Studio .NET</span><span class="sxs-lookup"><span data-stu-id="84445-102">Create a Visual Basic SMO Project in Visual Studio .NET</span></span>
  <span data-ttu-id="84445-103">Cette section décrit comment élaborer une application de console SMO simple.</span><span class="sxs-lookup"><span data-stu-id="84445-103">This section describes how to build a simple SMO console application.</span></span>  
  
 <span data-ttu-id="84445-104">Cet exemple importe des espaces de noms, qui permettent au programme de référencer des types SMO.</span><span class="sxs-lookup"><span data-stu-id="84445-104">This example imports namespaces, which enables the program to reference SMO types.</span></span> <span data-ttu-id="84445-105">L'importation de l'espace de noms `Agent` est facultative.</span><span class="sxs-lookup"><span data-stu-id="84445-105">The import of the `Agent` namespace is optional.</span></span> <span data-ttu-id="84445-106">Utilisez-le quand vous écrivez un programme qui utilise [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] l’agent.</span><span class="sxs-lookup"><span data-stu-id="84445-106">Use it when you are writing a program that uses [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="84445-107">L'espace de noms `Common` est requis pour établir une connexion sécurisée avec l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84445-107">The `Common` namespace is required to establish a secure connection to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="84445-108">L'espace de noms `SqlClient` est utilisé pour traiter les erreurs d'exception SQL.</span><span class="sxs-lookup"><span data-stu-id="84445-108">The `SqlClient` namespace is used to process SQL exception errors.</span></span>  
  
### <a name="creating-a-visual-basic-smo-project-in-visual-studionet"></a><span data-ttu-id="84445-109">Création d'un projet SMO Visual Basic dans Visual Studio.NET</span><span class="sxs-lookup"><span data-stu-id="84445-109">Creating a Visual Basic SMO project in Visual Studio.NET</span></span>  
  
1.  <span data-ttu-id="84445-110">Démarrez [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] (ou [!INCLUDE[vsprvslong](../../includes/vsprvslong-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="84445-110">Start [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] (or [!INCLUDE[vsprvslong](../../includes/vsprvslong-md.md)]).</span></span>  
  
2.  <span data-ttu-id="84445-111">Dans le menu **Fichier**, cliquez sur **Nouveau projet**.</span><span class="sxs-lookup"><span data-stu-id="84445-111">On the **File** menu, click **NewProject.**</span></span> <span data-ttu-id="84445-112">La boîte de dialogue **Nouveau projet** apparaît.</span><span class="sxs-lookup"><span data-stu-id="84445-112">The **New Project** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="84445-113">Dans la boîte de dialogue **types de projets** , sélectionnez **Visual Basic**, puis sélectionnez **Windows**.</span><span class="sxs-lookup"><span data-stu-id="84445-113">In **Project Types** dialog box, select **Visual Basic**, and then select **Windows**.</span></span> <span data-ttu-id="84445-114">Dans le [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] volet Modèles installés, sélectionnez **application console.**</span><span class="sxs-lookup"><span data-stu-id="84445-114">In the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Installed Templates pane, select **Console Application.**</span></span>  
  
4.  <span data-ttu-id="84445-115">Facultatif Dans le champ **nom** , tapez le nom de la nouvelle application.</span><span class="sxs-lookup"><span data-stu-id="84445-115">(Optional) In the **Name** field, type the name of the new application.</span></span>  
  
5.  <span data-ttu-id="84445-116">Cliquez sur **OK** pour charger le [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] modèle application console.</span><span class="sxs-lookup"><span data-stu-id="84445-116">Click **OK** to load the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] console application template.</span></span>  
  
6.  <span data-ttu-id="84445-117">Dans le menu **Projet**, sélectionnez **Ajouter une référence**.</span><span class="sxs-lookup"><span data-stu-id="84445-117">On the **Project** menu, select **Add Reference**.</span></span> <span data-ttu-id="84445-118">La boîte de dialogue **Ajouter une référence** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="84445-118">The **Add Reference** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="84445-119">Cliquez sur **Parcourir**, recherchez les assemblys Smo dans le dossier C:\Program Files\Microsoft SQL Server\120\SDK\Assemblies, puis sélectionnez les fichiers suivants.</span><span class="sxs-lookup"><span data-stu-id="84445-119">Click **Browse**, locate the SMO assemblies in the C:\Program Files\Microsoft SQL Server\120\SDK\Assemblies folder, and then select the following files.</span></span> <span data-ttu-id="84445-120">Il s'agit des fichiers minimum requis pour générer une application SMO :</span><span class="sxs-lookup"><span data-stu-id="84445-120">These are the minimum files that are required to build an SMO application:</span></span>  
  
     <span data-ttu-id="84445-121">Microsoft.SqlServer.ConnectionInfo.dll</span><span class="sxs-lookup"><span data-stu-id="84445-121">Microsoft.SqlServer.ConnectionInfo.dll</span></span>  
  
     <span data-ttu-id="84445-122">Microsoft.SqlServer.SqlEnum.dll</span><span class="sxs-lookup"><span data-stu-id="84445-122">Microsoft.SqlServer.SqlEnum.dll</span></span>  
  
     <span data-ttu-id="84445-123">Microsoft.SqlServer.Smo.dll</span><span class="sxs-lookup"><span data-stu-id="84445-123">Microsoft.SqlServer.Smo.dll</span></span>  
  
     <span data-ttu-id="84445-124">Microsoft.SqlServer.Management.Sdk.Sfc</span><span class="sxs-lookup"><span data-stu-id="84445-124">Microsoft.SqlServer.Management.Sdk.Sfc</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="84445-125">Utilisez la touche `Ctrl` pour sélectionner plusieurs fichiers.</span><span class="sxs-lookup"><span data-stu-id="84445-125">Use the `Ctrl` key to select more than one file.</span></span>  
  
8.  <span data-ttu-id="84445-126">Ajoutez les autres assemblys SMO qui sont nécessaires.</span><span class="sxs-lookup"><span data-stu-id="84445-126">Add any additional SMO assemblies that are required.</span></span> <span data-ttu-id="84445-127">Par exemple, si vous programmez spécifiquement [!INCLUDE[ssSB](../../includes/sssb-md.md)], ajoutez les assemblys suivants :</span><span class="sxs-lookup"><span data-stu-id="84445-127">For example, if you are specifically programming [!INCLUDE[ssSB](../../includes/sssb-md.md)], add the following assemblies:</span></span>  
  
     <span data-ttu-id="84445-128">Microsoft.SqlServer.ServiceBrokerEmum.dll</span><span class="sxs-lookup"><span data-stu-id="84445-128">Microsoft.SqlServer.ServiceBrokerEmum.dll</span></span>  
  
9. <span data-ttu-id="84445-129">Cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="84445-129">Click **Open**.</span></span>  
  
10. <span data-ttu-id="84445-130">Dans le menu **affichage** , cliquez sur **code**.-ou-sélectionnez la fenêtre Module1. vb pour afficher la fenêtre de code.</span><span class="sxs-lookup"><span data-stu-id="84445-130">On the **View** menu, click **Code**.-Or-Select the Module1.vb window to show the code window.</span></span>  
  
11. <span data-ttu-id="84445-131">Dans le code, avant les déclarations, tapez les instructions **Imports** suivantes pour qualifier les types dans l’espace de noms Smo.</span><span class="sxs-lookup"><span data-stu-id="84445-131">In the code, before any declarations, type the following **Imports** statements to qualify the types in the SMO namespace.</span></span>  
  
    ```  
    Imports Microsoft.SqlServer.Management.Smo  
    Imports Microsoft.SqlServer.Management.Common  
    ```  
  
12. <span data-ttu-id="84445-132">SMO comporte différents espaces de noms sous Microsoft.SqlServer.Management.Smo, par exemple Microsoft.SqlServer.Management.Smo.Agent.</span><span class="sxs-lookup"><span data-stu-id="84445-132">SMO has various namespaces under Microsoft.SqlServer.Management.Smo, such as Microsoft.SqlServer.Management.Smo.Agent.</span></span> <span data-ttu-id="84445-133">Ajoutez ces espaces de noms lorsqu'ils sont requis.</span><span class="sxs-lookup"><span data-stu-id="84445-133">Add these namespaces as they are required.</span></span>  
  
13. <span data-ttu-id="84445-134">Vous pouvez à présent ajouter votre code SMO.</span><span class="sxs-lookup"><span data-stu-id="84445-134">You can now add your SMO code.</span></span>  
  
  
