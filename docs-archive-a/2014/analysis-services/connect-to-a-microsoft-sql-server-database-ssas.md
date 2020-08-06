---
title: Se connecter à une base de données Microsoft SQL Server (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connsqlserverdb.f1
ms.assetid: 6ebfe029-dbba-4f0d-a556-328e79ef629f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 64267cd65836cf8e6c8d8b26a177de595894b601
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602471"
---
# <a name="connect-to-a-microsoft-sql-server-database-ssas"></a><span data-ttu-id="e4576-102">Connexion à une base de données Microsoft SQL Server (SSAS)</span><span class="sxs-lookup"><span data-stu-id="e4576-102">Connect to a Microsoft SQL Server Database (SSAS)</span></span>
  <span data-ttu-id="e4576-103">Cette page de **l’Assistant Importation de table** vous permet de spécifier des paramètres pour vous connecter à une base de données Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e4576-103">This page of the **Table Import Wizard** enables you to specify settings to connect to a Microsoft SQL Server database.</span></span> <span data-ttu-id="e4576-104">Pour accéder à l'Assistant [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dans le menu **Modèle** , cliquez sur **Importer à partir de la source de données**.</span><span class="sxs-lookup"><span data-stu-id="e4576-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="e4576-105">Pour vous connecter à une source de données, vous devez disposer du fournisseur approprié, installé sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="e4576-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e4576-106">Les informations d'identification de l'utilisateur actuel sont utilisées lors de la sélection d'une base de données sur cette page.</span><span class="sxs-lookup"><span data-stu-id="e4576-106">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="e4576-107">Toutefois, l'importation ne réussira pas si l'utilisateur spécifié dans la page Informations d'emprunt d'identité n'a pas de privilèges suffisants pour lire la base de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e4576-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="e4576-108">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="e4576-108">UI element list</span></span>  
 <span data-ttu-id="e4576-109">**Nom convivial de la connexion**</span><span class="sxs-lookup"><span data-stu-id="e4576-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="e4576-110">Tapez un nom unique pour cette connexion à la source de données.</span><span class="sxs-lookup"><span data-stu-id="e4576-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="e4576-111">Ce champ est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="e4576-111">This is a required field.</span></span>  
  
 <span data-ttu-id="e4576-112">**Nom du serveur**</span><span class="sxs-lookup"><span data-stu-id="e4576-112">**Server name**</span></span>  
 <span data-ttu-id="e4576-113">Sélectionnez le nom ou tapez le nom ou l’adresse IP de l’instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] à laquelle vous connecter.</span><span class="sxs-lookup"><span data-stu-id="e4576-113">Select the name, or type the name or IP address, of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance to connect to.</span></span>  
  
 <span data-ttu-id="e4576-114">Vous pouvez utiliser un point (.), (local) ou localhost pour indiquer le serveur local.</span><span class="sxs-lookup"><span data-stu-id="e4576-114">You can use a period (.), (local), or localhost to indicate the local server.</span></span>  
  
 <span data-ttu-id="e4576-115">**Utiliser l'authentification Windows**</span><span class="sxs-lookup"><span data-stu-id="e4576-115">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="e4576-116">Précisez si l’authentification Windows est utilisée pour se connecter à une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4576-116">Specify whether Windows Authentication is used to connect to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="e4576-117">Le mode d’authentification Windows permet à l’utilisateur de se connecter au moyen d’un compte d’utilisateur Windows.</span><span class="sxs-lookup"><span data-stu-id="e4576-117">Windows Authentication mode enables a user to connect by using a Windows user account.</span></span> <span data-ttu-id="e4576-118">Dans la mesure du possible, utilisez l’authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="e4576-118">Whenever possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="e4576-119">Lorsque l'Authentification Windows est utilisée, les informations d'identification de l'utilisateur actuel sont utilisées lors de l'affichage d'un aperçu et le filtrage des données dans la fenêtre Propriétés de la table et dans l'Assistant Importation.</span><span class="sxs-lookup"><span data-stu-id="e4576-119">When Windows Authentication is used, the credentials of the current user are used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="e4576-120">Ces informations d'identification ne sont pas utilisées pour importer ou actualiser des données ; les informations d'identification Windows spécifiées dans la page Informations d'emprunt d'identité sont utilisées à la place.</span><span class="sxs-lookup"><span data-stu-id="e4576-120">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation information page are used instead.</span></span>  
  
 <span data-ttu-id="e4576-121">**Utiliser l’authentification SQL Server**</span><span class="sxs-lookup"><span data-stu-id="e4576-121">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="e4576-122">Précisez si l’authentification SQL Server est utilisée pour se connecter à une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4576-122">Specify whether SQL Server Authentication is used to connect to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="e4576-123">Avec l'authentification SQL Server, SQL Server effectue l'authentification lui-même en vérifiant si un compte de connexion SQL Server a été configuré et si le mot de passe spécifié correspond à celui enregistré précédemment.</span><span class="sxs-lookup"><span data-stu-id="e4576-123">With SQL Server Authentication, SQL Server performs the authentication itself by checking to see if a SQL Server login account has been set up and if the specified password matches the one previously recorded.</span></span>  
  
 <span data-ttu-id="e4576-124">L'Authentification SQL Server est utilisée pour construire la chaîne de connexion pour la source de données.</span><span class="sxs-lookup"><span data-stu-id="e4576-124">SQL Server Authentication is used to construct the connection string for the data source.</span></span> <span data-ttu-id="e4576-125">Ces informations d'identification sont également utilisées lors de l'affichage un aperçu et du filtrage des données dans la fenêtre Propriétés de la table et dans l'Assistant Importation.</span><span class="sxs-lookup"><span data-stu-id="e4576-125">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="e4576-126">Ces informations d'identification ne sont pas utilisées pour importer ou actualiser des données ; les informations d'identification Windows spécifiées dans la page Informations d'emprunt d'identité sont utilisées à la place.</span><span class="sxs-lookup"><span data-stu-id="e4576-126">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="e4576-127">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="e4576-127">**User name**</span></span>  
 <span data-ttu-id="e4576-128">Spécifiez un nom d'utilisateur pour la connexion de base de données.</span><span class="sxs-lookup"><span data-stu-id="e4576-128">Specify a user name for the database connection.</span></span> <span data-ttu-id="e4576-129">Cette option est disponible uniquement si vous avez choisi de vous connecter via l'authentification SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e4576-129">This option is only available if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="e4576-130">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="e4576-130">**Password**</span></span>  
 <span data-ttu-id="e4576-131">Spécifiez un mot de passe pour la connexion de base de données.</span><span class="sxs-lookup"><span data-stu-id="e4576-131">Specify a password for the database connection.</span></span> <span data-ttu-id="e4576-132">Cette option peut être modifiée uniquement si vous avez choisi de vous connecter via l'authentification SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e4576-132">This option is only editable if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="e4576-133">**Enregistrer mon mot de passe**</span><span class="sxs-lookup"><span data-stu-id="e4576-133">**Save my password**</span></span>  
 <span data-ttu-id="e4576-134">Précisez si le mot de passe que vous avez entré dans la zone **Mot de passe** est mémorisé.</span><span class="sxs-lookup"><span data-stu-id="e4576-134">Specify whether the password you have entered in the **Password** box is stored.</span></span> <span data-ttu-id="e4576-135">Cette option est disponible uniquement si vous avez choisi de vous connecter via l'authentification SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e4576-135">This option is only available if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="e4576-136">**Nom de la base de données**</span><span class="sxs-lookup"><span data-stu-id="e4576-136">**Database name**</span></span>  
 <span data-ttu-id="e4576-137">Sélectionnez une base de données dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e4576-137">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="e4576-138">**Avancée**</span><span class="sxs-lookup"><span data-stu-id="e4576-138">**Advanced**</span></span>  
 <span data-ttu-id="e4576-139">Définissez des propriétés de connexion supplémentaires à l’aide de la boîte de dialogue **Définir les propriétés avancées** .</span><span class="sxs-lookup"><span data-stu-id="e4576-139">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="e4576-140">Pour plus d’informations, consultez [Définir les propriétés avancées &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="e4576-140">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="e4576-141">**Tester la connexion**</span><span class="sxs-lookup"><span data-stu-id="e4576-141">**Test Connection**</span></span>  
 <span data-ttu-id="e4576-142">Essayez d'établir une connexion à la source de données à l'aide des paramètres actuels.</span><span class="sxs-lookup"><span data-stu-id="e4576-142">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="e4576-143">Un message s’affiche pour indiquer si la connexion a abouti.</span><span class="sxs-lookup"><span data-stu-id="e4576-143">A message is displayed indicating whether the connection was successful.</span></span>  
  
  
