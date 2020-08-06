---
title: Se connecter à Microsoft SQL Server Analysis Services (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connsqlserveras.f1
ms.assetid: 7f3244ee-b690-471c-893d-68e361c2d416
author: minewiskan
ms.author: owend
ms.openlocfilehash: 984979480e3ea54c86c986fa6dd9771aaf879cb1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602448"
---
# <a name="connect-to-microsoft-sql-server-analysis-services-ssas"></a><span data-ttu-id="a903d-102">Connexion à Microsoft SQL Server Analysis Services (SSAS)</span><span class="sxs-lookup"><span data-stu-id="a903d-102">Connect to Microsoft SQL Server Analysis Services (SSAS)</span></span>
  <span data-ttu-id="a903d-103">Cette page de l' **Assistant Importation de table** vous permet de spécifier les paramètres d'importation de données à partir d'un cube Microsoft SQL Server Analysis Services ou d'un classeur PowerPivot hébergé sur SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a903d-103">This page of the **Table Import Wizard** enables you to specify settings to import data from a Microsoft SQL Server Analysis Services cube or a PowerPivot workbook that is hosted on SharePoint.</span></span> <span data-ttu-id="a903d-104">Pour accéder à l'Assistant [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dans le menu **Modèle** , cliquez sur **Importer à partir de la source de données**.</span><span class="sxs-lookup"><span data-stu-id="a903d-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="a903d-105">Pour vous connecter à une source de données, vous devez disposer du fournisseur approprié, installé sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="a903d-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a903d-106">Les informations d'identification de l'utilisateur actuel sont utilisées lors de la sélection d'une base de données sur cette page.</span><span class="sxs-lookup"><span data-stu-id="a903d-106">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="a903d-107">Toutefois, l'importation ne réussira pas si l'utilisateur spécifié dans la page Informations d'emprunt d'identité n'a pas de privilèges suffisants pour lire la base de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a903d-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="a903d-108">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="a903d-108">UI element list</span></span>  
 <span data-ttu-id="a903d-109">**Nom convivial de la connexion**</span><span class="sxs-lookup"><span data-stu-id="a903d-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="a903d-110">Tapez un nom unique pour cette connexion à la source de données.</span><span class="sxs-lookup"><span data-stu-id="a903d-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="a903d-111">Ce champ est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="a903d-111">This is a required field.</span></span>  
  
 <span data-ttu-id="a903d-112">**Nom du serveur ou du fichier**</span><span class="sxs-lookup"><span data-stu-id="a903d-112">**Server or File Name**</span></span>  
 <span data-ttu-id="a903d-113">Entrez l'une des informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a903d-113">Enter one of the following:</span></span>  
  
-   <span data-ttu-id="a903d-114">Tapez le nom ou l'adresse IP du serveur SQL Server Analysis Services auquel vous voulez vous connecter.</span><span class="sxs-lookup"><span data-stu-id="a903d-114">Type the name or IP address of the SQL Server Analysis Services server to connect to.</span></span>  
  
     <span data-ttu-id="a903d-115">Vous pouvez utiliser un point (.), (local) ou localhost pour indiquer le serveur local.</span><span class="sxs-lookup"><span data-stu-id="a903d-115">You can use a period (.), (local), or localhost to indicate the local server.</span></span>  
  
-   <span data-ttu-id="a903d-116">Tapez l'URL d'un classeur PowerPivot publié dans SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a903d-116">Type the URL of a PowerPivot workbook that is published to SharePoint.</span></span>  
  
 <span data-ttu-id="a903d-117">**Utiliser l'authentification Windows**</span><span class="sxs-lookup"><span data-stu-id="a903d-117">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="a903d-118">Spécifiez si l'authentification Windows est utilisée pour se connecter à un serveur SQL Server Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="a903d-118">Specify whether Windows Authentication is used to connect to a SQL Server Analysis Services server.</span></span>  
  
 <span data-ttu-id="a903d-119">Le mode d'authentification Windows permet à l'utilisateur de se connecter au moyen d'un compte d'utilisateur Windows.</span><span class="sxs-lookup"><span data-stu-id="a903d-119">Windows Authentication mode enables a user to connect through a Windows user account.</span></span> <span data-ttu-id="a903d-120">Dans la mesure du possible, utilisez l’authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="a903d-120">Whenever possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="a903d-121">Lorsque l'Authentification Windows est utilisée, les informations d'identification de l'utilisateur actuel sont utilisées lors de l'affichage d'un aperçu et le filtrage des données dans la fenêtre Propriétés de la table et dans l'Assistant Importation.</span><span class="sxs-lookup"><span data-stu-id="a903d-121">When Windows Authentication is used, the credentials of the current user are used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="a903d-122">Ces informations d'identification ne sont pas utilisées pour importer ou actualiser des données ; les informations d'identification Windows spécifiées dans la page Informations d'emprunt d'identité sont utilisées à la place.</span><span class="sxs-lookup"><span data-stu-id="a903d-122">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="a903d-123">**Utiliser l’authentification SQL Server**</span><span class="sxs-lookup"><span data-stu-id="a903d-123">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="a903d-124">Spécifiez si l'authentification SQL Server est utilisée pour se connecter à un serveur SQL Server Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="a903d-124">Specify whether SQL Server Authentication is used to connect to a SQL Server Analysis Services server.</span></span>  
  
 <span data-ttu-id="a903d-125">Avec l'authentification SQL Server, SQL Server effectue l'authentification lui-même en vérifiant si un compte de connexion SQL Server a été configuré et si le mot de passe spécifié correspond à celui enregistré précédemment.</span><span class="sxs-lookup"><span data-stu-id="a903d-125">With SQL Server Authentication, SQL Server performs the authentication itself by checking to see if a SQL Server login account has been set up and if the specified password matches the one previously recorded.</span></span>  
  
 <span data-ttu-id="a903d-126">L'Authentification SQL Server est utilisée pour construire la chaîne de connexion pour la source de données.</span><span class="sxs-lookup"><span data-stu-id="a903d-126">SQL Server Authentication is used to construct the connection string for the data source.</span></span> <span data-ttu-id="a903d-127">Ces informations d'identification sont également utilisées lors de l'affichage un aperçu et du filtrage des données dans la fenêtre Propriétés de la table et dans l'Assistant Importation.</span><span class="sxs-lookup"><span data-stu-id="a903d-127">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="a903d-128">Ces informations d'identification ne sont pas utilisées pour importer ou actualiser des données ; les informations d'identification Windows spécifiées dans la page Informations d'emprunt d'identité sont utilisées à la place.</span><span class="sxs-lookup"><span data-stu-id="a903d-128">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="a903d-129">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="a903d-129">**User name**</span></span>  
 <span data-ttu-id="a903d-130">Spécifiez un nom d'utilisateur pour la connexion de base de données.</span><span class="sxs-lookup"><span data-stu-id="a903d-130">Specify a user name for the database connection.</span></span> <span data-ttu-id="a903d-131">Cette option est uniquement disponible si vous avez choisi la connexion avec l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="a903d-131">This option is only available if you have selected to connect using Windows Authentication.</span></span>  
  
 <span data-ttu-id="a903d-132">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="a903d-132">**Password**</span></span>  
 <span data-ttu-id="a903d-133">Spécifiez un mot de passe pour la connexion de base de données.</span><span class="sxs-lookup"><span data-stu-id="a903d-133">Specify a password for the database connection.</span></span> <span data-ttu-id="a903d-134">Cette option peut être modifiée uniquement si vous avez choisi de vous connecter via l'authentification SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a903d-134">This option is only editable if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="a903d-135">**Enregistrer mon mot de passe**</span><span class="sxs-lookup"><span data-stu-id="a903d-135">**Save my password**</span></span>  
 <span data-ttu-id="a903d-136">Précisez si le mot de passe que vous avez entré dans la zone **Mot de passe** est mémorisé.</span><span class="sxs-lookup"><span data-stu-id="a903d-136">Specify whether the password you have entered in the **Password** box is stored.</span></span> <span data-ttu-id="a903d-137">Cette option est disponible uniquement si vous avez choisi de vous connecter via l'authentification SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a903d-137">This option is only available if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="a903d-138">**Nom de la base de données**</span><span class="sxs-lookup"><span data-stu-id="a903d-138">**Database name**</span></span>  
 <span data-ttu-id="a903d-139">Sélectionnez une base de données dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a903d-139">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="a903d-140">**Avancée**</span><span class="sxs-lookup"><span data-stu-id="a903d-140">**Advanced**</span></span>  
 <span data-ttu-id="a903d-141">Définissez des propriétés de connexion supplémentaires à l’aide de la boîte de dialogue **Définir les propriétés avancées** .</span><span class="sxs-lookup"><span data-stu-id="a903d-141">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="a903d-142">Pour plus d’informations, consultez [Définir les propriétés avancées &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="a903d-142">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="a903d-143">**Tester la connexion**</span><span class="sxs-lookup"><span data-stu-id="a903d-143">**Test Connection**</span></span>  
 <span data-ttu-id="a903d-144">Essayez d'établir une connexion à la source de données à l'aide des paramètres actuels.</span><span class="sxs-lookup"><span data-stu-id="a903d-144">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="a903d-145">Un message est affiché pour indiquer si la connexion a abouti.</span><span class="sxs-lookup"><span data-stu-id="a903d-145">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
