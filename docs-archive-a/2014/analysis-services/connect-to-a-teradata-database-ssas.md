---
title: Se connecter à une base de données Teradata (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connterradb.f1
ms.assetid: 875ad4a3-a2b3-4b68-8c1c-6507e9f25b4d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 047eed5f8625059750a67c51735c7c0d61d17853
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602460"
---
# <a name="connect-to-a-teradata-database-ssas"></a><span data-ttu-id="ed632-102">Connexion à une base de données Teradata (SSAS)</span><span class="sxs-lookup"><span data-stu-id="ed632-102">Connect to a Teradata Database (SSAS)</span></span>
  <span data-ttu-id="ed632-103">Cette page de **l’Assistant Importation de table** vous permet de spécifier des paramètres pour vous connecter à une base de données Teradata.</span><span class="sxs-lookup"><span data-stu-id="ed632-103">This page of the **Table Import Wizard** enables you to specify settings to connect to a Teradata database.</span></span> <span data-ttu-id="ed632-104">Pour accéder à l'Assistant [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dans le menu **Modèle** , cliquez sur **Importer à partir de la source de données**.</span><span class="sxs-lookup"><span data-stu-id="ed632-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="ed632-105">Pour vous connecter à une source de données, vous devez disposer du fournisseur approprié, installé sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="ed632-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ed632-106">Les informations d'identification de l'utilisateur actuel sont utilisées lors de la sélection d'une base de données sur cette page.</span><span class="sxs-lookup"><span data-stu-id="ed632-106">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="ed632-107">Toutefois, l'importation ne réussira pas si l'utilisateur spécifié dans la page Informations d'emprunt d'identité n'a pas de privilèges suffisants pour lire la base de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ed632-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="ed632-108">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="ed632-108">UI element list</span></span>  
 <span data-ttu-id="ed632-109">**Nom convivial de la connexion**</span><span class="sxs-lookup"><span data-stu-id="ed632-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="ed632-110">Tapez un nom unique pour cette connexion à la source de données.</span><span class="sxs-lookup"><span data-stu-id="ed632-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="ed632-111">Ce champ est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="ed632-111">This is a required field.</span></span>  
  
 <span data-ttu-id="ed632-112">**Nom du serveur**</span><span class="sxs-lookup"><span data-stu-id="ed632-112">**Server name**</span></span>  
 <span data-ttu-id="ed632-113">Tapez ou sélectionnez le nom de l'instance de serveur à laquelle se connecter.</span><span class="sxs-lookup"><span data-stu-id="ed632-113">Type or select the name of the server instance to connect to.</span></span>  
  
 <span data-ttu-id="ed632-114">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="ed632-114">**User name**</span></span>  
 <span data-ttu-id="ed632-115">Spécifiez un nom d'utilisateur pour la connexion de base de données.</span><span class="sxs-lookup"><span data-stu-id="ed632-115">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="ed632-116">Ce nom d'utilisateur est utilisé lors de la construction de la chaîne de connexion pour la source de données.</span><span class="sxs-lookup"><span data-stu-id="ed632-116">This user name is used when constructing the connection string for the data source.</span></span> <span data-ttu-id="ed632-117">Ces informations d'identification sont également utilisées lors de l'affichage un aperçu et du filtrage des données dans la fenêtre Propriétés de la table et dans l'Assistant Importation.</span><span class="sxs-lookup"><span data-stu-id="ed632-117">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="ed632-118">Ces informations d'identification ne sont pas utilisées pour importer ou actualiser des données ; les informations d'identification Windows spécifiées dans la page Informations d'emprunt d'identité sont utilisées à la place.</span><span class="sxs-lookup"><span data-stu-id="ed632-118">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation information page are used instead.</span></span>  
  
 <span data-ttu-id="ed632-119">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="ed632-119">**Password**</span></span>  
 <span data-ttu-id="ed632-120">Spécifiez un mot de passe pour la connexion de base de données.</span><span class="sxs-lookup"><span data-stu-id="ed632-120">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="ed632-121">**Enregistrer mon mot de passe**</span><span class="sxs-lookup"><span data-stu-id="ed632-121">**Save my password**</span></span>  
 <span data-ttu-id="ed632-122">Spécifiez si le mot de passe que vous avez entré dans la zone **Mot de passe** doit être mémorisé.</span><span class="sxs-lookup"><span data-stu-id="ed632-122">Specify whether the password you have entered in the **Password** box should be stored.</span></span>  
  
 <span data-ttu-id="ed632-123">**Avancée**</span><span class="sxs-lookup"><span data-stu-id="ed632-123">**Advanced**</span></span>  
 <span data-ttu-id="ed632-124">Définissez des propriétés de connexion supplémentaires à l’aide de la boîte de dialogue **Définir les propriétés avancées** .</span><span class="sxs-lookup"><span data-stu-id="ed632-124">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="ed632-125">Pour plus d’informations, consultez [Définir les propriétés avancées &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="ed632-125">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="ed632-126">**Tester la connexion**</span><span class="sxs-lookup"><span data-stu-id="ed632-126">**Test Connection**</span></span>  
 <span data-ttu-id="ed632-127">Essayez d'établir une connexion à la source de données à l'aide des paramètres actuels.</span><span class="sxs-lookup"><span data-stu-id="ed632-127">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="ed632-128">Un message est affiché pour indiquer si la connexion a abouti.</span><span class="sxs-lookup"><span data-stu-id="ed632-128">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
