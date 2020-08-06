---
title: Gestionnaire de connexions OData | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3caa4372-aff3-4c0f-9ecd-97870948b8d0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 46eedaa008b284661fd1d364d2e2bc87c373a9f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611221"
---
# <a name="odata-connection-manager"></a><span data-ttu-id="f70bb-102">Gestionnaire de connexions OData</span><span class="sxs-lookup"><span data-stu-id="f70bb-102">OData Connection Manager</span></span>
  <span data-ttu-id="f70bb-103">Un gestionnaire de connexions OData permet à un package de se connecter à une source OData.</span><span class="sxs-lookup"><span data-stu-id="f70bb-103">An OData connection manager enables a package to connect to an OData source.</span></span> <span data-ttu-id="f70bb-104">Un composant source OData se connecte à une source OData à l'aide d'un gestionnaire de connexions OData et consomme les données du service.</span><span class="sxs-lookup"><span data-stu-id="f70bb-104">An OData Source component connects to an OData source using an OData connection manager and consumes data from the service.</span></span> <span data-ttu-id="f70bb-105">Consultez la [OData Source](../data-flow/odata-source.md)section qui traite des informations détaillées et des instructions d'installation de ces composants.</span><span class="sxs-lookup"><span data-stu-id="f70bb-105">See [OData Source](../data-flow/odata-source.md)section for detailed information including the installation instructions for these components.</span></span>  
  
## <a name="adding-connection-manager-to-an-ssis-package"></a><span data-ttu-id="f70bb-106">Ajout d'un gestionnaire de connexions à un package SSIS</span><span class="sxs-lookup"><span data-stu-id="f70bb-106">Adding Connection Manager to an SSIS Package</span></span>  
 <span data-ttu-id="f70bb-107">Vous pouvez ajouter un nouveau gestionnaire de connexions OData à un package SSIS de trois manières :</span><span class="sxs-lookup"><span data-stu-id="f70bb-107">You can add a new OData Connection Manager to an SSIS package in three ways:</span></span>  
  
-   <span data-ttu-id="f70bb-108">Cliquez sur le bouton **Nouveau...** dans **Éditeur de source OData**.</span><span class="sxs-lookup"><span data-stu-id="f70bb-108">Click the **New...** button in the **OData Source Editor**</span></span>  
  
-   <span data-ttu-id="f70bb-109">Cliquez avec le bouton droit sur le dossier **Gestionnaires de connexions** dans l' **Explorateur de solutions** et cliquez sur **Nouveau gestionnaire de connexions**.</span><span class="sxs-lookup"><span data-stu-id="f70bb-109">Right-click **Connection Managers** folder in the **Solution Explorer** and click **New Connection Manager**.</span></span> <span data-ttu-id="f70bb-110">Sélectionnez **ODATA** pour **Type du gestionnaire de connexions**.</span><span class="sxs-lookup"><span data-stu-id="f70bb-110">Select **ODATA** for **Connection manager type**.</span></span>  
  
-   <span data-ttu-id="f70bb-111">Cliquez avec le bouton droit dans le volet **gestionnaires de connexions** au bas du concepteur de packages, puis sélectionnez **nouvelle connexion...**. Sélectionnez **ODATA** pour le **type de gestionnaire de connexions**.</span><span class="sxs-lookup"><span data-stu-id="f70bb-111">Right-click in the **Connection Managers** pane at the bottom of the package designer, and select **New Connection...**. Select **ODATA** for **Connection manager type**.</span></span>  
  
## <a name="connection-manager-authentication"></a><span data-ttu-id="f70bb-112">Authentification du gestionnaire de connexions</span><span class="sxs-lookup"><span data-stu-id="f70bb-112">Connection Manager Authentication</span></span>  
 <span data-ttu-id="f70bb-113">Le Gestionnaire de connexions OData prend en charge deux modes d'authentification.</span><span class="sxs-lookup"><span data-stu-id="f70bb-113">The OData Connection Manager supports two modes of authentication.</span></span>  
  
-   <span data-ttu-id="f70bb-114">Authentification Windows</span><span class="sxs-lookup"><span data-stu-id="f70bb-114">Windows Authentication</span></span>  
  
-   <span data-ttu-id="f70bb-115">Authentification de base (nom d'utilisateur/mot de passe)</span><span class="sxs-lookup"><span data-stu-id="f70bb-115">Basic Authentication (username/password)</span></span>  
  
 <span data-ttu-id="f70bb-116">Pour un accès anonyme, sélectionnez l'option Authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="f70bb-116">For anonymous access, select the Windows Authentication option</span></span>  
  
### <a name="specifying-and-securing-credentials"></a><span data-ttu-id="f70bb-117">Spécification des informations d'identification</span><span class="sxs-lookup"><span data-stu-id="f70bb-117">Specifying and Securing Credentials</span></span>  
 <span data-ttu-id="f70bb-118">Si votre service OData requiert l'authentification de base, spécifiez un nom d'utilisateur et un mot de passe dans [OData Connection Manager Editor](../odata-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="f70bb-118">If your OData service requires basic authentication, you can specify a username and password in the [OData Connection Manager Editor](../odata-connection-manager-editor.md).</span></span> <span data-ttu-id="f70bb-119">Les valeurs que vous entrez dans l'éditeur sont conservées dans le package.</span><span class="sxs-lookup"><span data-stu-id="f70bb-119">The values you enter in the editor are persisted in the package.</span></span> <span data-ttu-id="f70bb-120">La valeur du mot de passe est chiffrée selon le niveau de protection du package.</span><span class="sxs-lookup"><span data-stu-id="f70bb-120">The password value is encrypted according to the package protection level.</span></span>  
  
 <span data-ttu-id="f70bb-121">Il y a plusieurs manières d'extérioriser/paramétrer les valeurs de nom d'utilisateur et de mot de passe.</span><span class="sxs-lookup"><span data-stu-id="f70bb-121">There are multiple ways to externalize/parameterize the username and password values.</span></span> <span data-ttu-id="f70bb-122">Les deux principales façons de procéder dans [!INCLUDE[ssISversion11](../../includes/ssisversion11-md.md)] sont en utilisant les paramètres, ou en définissant les propriétés du gestionnaire de connexions directement lorsque vous exécutez le package en utilisant SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="f70bb-122">The two primary ways of doing this in [!INCLUDE[ssISversion11](../../includes/ssisversion11-md.md)] are by using parameters, or by setting the connection manager properties directly when you run the package using SQL Server Management Studio.</span></span>  
  
## <a name="odata-connection-manager-properties"></a><span data-ttu-id="f70bb-123">Propriétés du gestionnaire de connexions OData</span><span class="sxs-lookup"><span data-stu-id="f70bb-123">OData Connection Manager Properties</span></span>  
 <span data-ttu-id="f70bb-124">Le tableau suivant répertorie certaines propriétés du gestionnaire de connexions OData que vous pouvez modifier.</span><span class="sxs-lookup"><span data-stu-id="f70bb-124">The following list describes some of the OData Connection Manager properties that you may want to change.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f70bb-125">Propriété</span><span class="sxs-lookup"><span data-stu-id="f70bb-125">Property</span></span>|<span data-ttu-id="f70bb-126">Description</span><span class="sxs-lookup"><span data-stu-id="f70bb-126">Description</span></span>|  
|<span data-ttu-id="f70bb-127">Url</span><span class="sxs-lookup"><span data-stu-id="f70bb-127">Url</span></span>|<span data-ttu-id="f70bb-128">URL vers le document de service.</span><span class="sxs-lookup"><span data-stu-id="f70bb-128">URL to the service document.</span></span>|  
|<span data-ttu-id="f70bb-129">UserName</span><span class="sxs-lookup"><span data-stu-id="f70bb-129">UserName</span></span>|<span data-ttu-id="f70bb-130">Nom d'utilisateur à utiliser pour l'authentification de base.</span><span class="sxs-lookup"><span data-stu-id="f70bb-130">Username to use for Basic Authentication.</span></span>|  
|<span data-ttu-id="f70bb-131">Mot de passe</span><span class="sxs-lookup"><span data-stu-id="f70bb-131">Password</span></span>|<span data-ttu-id="f70bb-132">Mot de passe à utiliser pour l'authentification de base.</span><span class="sxs-lookup"><span data-stu-id="f70bb-132">Password to use for Basic Authentication.</span></span>|  
|<span data-ttu-id="f70bb-133">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="f70bb-133">ConnectionString</span></span>|<span data-ttu-id="f70bb-134">Reflète d'autres propriétés du gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="f70bb-134">Reflects other properties of the connection manager.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f70bb-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f70bb-135">See Also</span></span>  
 [<span data-ttu-id="f70bb-136">Éditeur du gestionnaire de connexions OData</span><span class="sxs-lookup"><span data-stu-id="f70bb-136">OData Connection Manager Editor</span></span>](../odata-connection-manager-editor.md)  
  
  
