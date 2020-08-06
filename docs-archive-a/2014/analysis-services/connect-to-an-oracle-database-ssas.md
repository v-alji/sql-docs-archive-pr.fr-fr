---
title: Se connecter à un Oracle Database (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connoracledb.f1
ms.assetid: 9bd177fb-8539-46cd-bf96-189ade52c2a1
author: minewiskan
ms.author: owend
ms.openlocfilehash: b0260983f5060ecba7f618975e805ff63c507d5a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602452"
---
# <a name="connect-to-an-oracle-database-ssas"></a><span data-ttu-id="a9ab6-102">Connexion à une base de données Oracle (SSAS)</span><span class="sxs-lookup"><span data-stu-id="a9ab6-102">Connect to an Oracle Database (SSAS)</span></span>
  <span data-ttu-id="a9ab6-103">Cette page de l' **Assistant Importation de table** vous permet de spécifier des paramètres pour vous connecter à une base de données Oracle.</span><span class="sxs-lookup"><span data-stu-id="a9ab6-103">This page of the **Table Import Wizard** enables you to specify settings to connect to an Oracle database.</span></span> <span data-ttu-id="a9ab6-104">Pour accéder à l'Assistant [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dans le menu **Modèle** , cliquez sur **Importer à partir de la source de données**.</span><span class="sxs-lookup"><span data-stu-id="a9ab6-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="a9ab6-105">Pour vous connecter à une source de données, vous devez disposer du fournisseur approprié, installé sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="a9ab6-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a9ab6-106">Les informations d'identification de l'utilisateur actuel sont utilisées lors de la sélection d'une base de données sur cette page.</span><span class="sxs-lookup"><span data-stu-id="a9ab6-106">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="a9ab6-107">Toutefois, l'importation ne réussira pas si l'utilisateur spécifié dans la page Informations d'emprunt d'identité n'a pas de privilèges suffisants pour lire la base de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a9ab6-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="a9ab6-108">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="a9ab6-108">UI element list</span></span>  
 <span data-ttu-id="a9ab6-109">**Nom convivial de la connexion**</span><span class="sxs-lookup"><span data-stu-id="a9ab6-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="a9ab6-110">Tapez un nom unique pour cette connexion à la source de données.</span><span class="sxs-lookup"><span data-stu-id="a9ab6-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="a9ab6-111">Ce champ est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="a9ab6-111">This is a required field.</span></span>  
  
 <span data-ttu-id="a9ab6-112">**Nom du serveur**</span><span class="sxs-lookup"><span data-stu-id="a9ab6-112">**Server name**</span></span>  
 <span data-ttu-id="a9ab6-113">Tapez ou sélectionnez le nom de l'instance de serveur à laquelle se connecter.</span><span class="sxs-lookup"><span data-stu-id="a9ab6-113">Type or select the name of the server instance to connect to.</span></span>  
  
 <span data-ttu-id="a9ab6-114">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="a9ab6-114">**User name**</span></span>  
 <span data-ttu-id="a9ab6-115">Spécifiez un nom d'utilisateur pour la connexion de base de données.</span><span class="sxs-lookup"><span data-stu-id="a9ab6-115">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="a9ab6-116">Ce nom d'utilisateur est utilisé lors de la construction de la chaîne de connexion pour la source de données.</span><span class="sxs-lookup"><span data-stu-id="a9ab6-116">This user name is used when constructing the connection string for the data source.</span></span> <span data-ttu-id="a9ab6-117">Ces informations d'identification sont également utilisées lors de l'affichage un aperçu et du filtrage des données dans la fenêtre Propriétés de la table et dans l'Assistant Importation.</span><span class="sxs-lookup"><span data-stu-id="a9ab6-117">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="a9ab6-118">Ces informations d'identification ne sont pas utilisées pour importer ou actualiser des données ; les informations d'identification Windows spécifiées dans la page Informations d'emprunt d'identité sont utilisées à la place.</span><span class="sxs-lookup"><span data-stu-id="a9ab6-118">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="a9ab6-119">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="a9ab6-119">**Password**</span></span>  
 <span data-ttu-id="a9ab6-120">Spécifiez un mot de passe pour la connexion de base de données.</span><span class="sxs-lookup"><span data-stu-id="a9ab6-120">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="a9ab6-121">**Enregistrer mon mot de passe**</span><span class="sxs-lookup"><span data-stu-id="a9ab6-121">**Save my password**</span></span>  
 <span data-ttu-id="a9ab6-122">Précisez si le mot de passe que vous avez entré dans la zone **Mot de passe** est mémorisé.</span><span class="sxs-lookup"><span data-stu-id="a9ab6-122">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="a9ab6-123">**Avancée**</span><span class="sxs-lookup"><span data-stu-id="a9ab6-123">**Advanced**</span></span>  
 <span data-ttu-id="a9ab6-124">Définissez des propriétés de connexion supplémentaires à l’aide de la boîte de dialogue **Définir les propriétés avancées** .</span><span class="sxs-lookup"><span data-stu-id="a9ab6-124">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="a9ab6-125">Pour plus d’informations, consultez [Définir les propriétés avancées &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="a9ab6-125">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="a9ab6-126">**Tester la connexion**</span><span class="sxs-lookup"><span data-stu-id="a9ab6-126">**Test Connection**</span></span>  
 <span data-ttu-id="a9ab6-127">Essayez d'établir une connexion à la source de données à l'aide des paramètres actuels.</span><span class="sxs-lookup"><span data-stu-id="a9ab6-127">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="a9ab6-128">Un message est affiché pour indiquer si la connexion a abouti.</span><span class="sxs-lookup"><span data-stu-id="a9ab6-128">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
