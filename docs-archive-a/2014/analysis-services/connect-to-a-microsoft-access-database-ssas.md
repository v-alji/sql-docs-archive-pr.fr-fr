---
title: Se connecter à une base de données Microsoft Access (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connaccessdb.f1
ms.assetid: 9fa81839-dd8b-41d3-915e-c774a707ed53
author: minewiskan
ms.author: owend
ms.openlocfilehash: fbb180a754b6bc276d588997117eb84fd1a5a873
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602472"
---
# <a name="connect-to-a-microsoft-access-database-ssas"></a><span data-ttu-id="11992-102">Connexion à une base de données Microsoft Access (SSAS)</span><span class="sxs-lookup"><span data-stu-id="11992-102">Connect to a Microsoft Access Database (SSAS)</span></span>
  <span data-ttu-id="11992-103">Cette page de **l’Assistant Importation de table** vous permet de spécifier des paramètres pour vous connecter à une base de données Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="11992-103">This page of the **Table Import Wizard** enables you to specify settings to connect to a Microsoft Access database.</span></span> <span data-ttu-id="11992-104">Pour accéder à l'Assistant [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dans le menu **Modèle** , cliquez sur **Importer à partir de la source de données**.</span><span class="sxs-lookup"><span data-stu-id="11992-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="11992-105">Pour vous connecter à une base de données Microsoft Access, vous devez disposer du fournisseur ACE approprié, installé sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="11992-105">To connect to a Microsoft Access database, you must have the appropriate ACE provider installed on your computer.</span></span> <span data-ttu-id="11992-106">Pour plus d’informations, consultez [Sources de données prises en charge &#40;SSAS Tabulaire&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="11992-106">For more information, see [Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="11992-107">Les informations d'identification de l'utilisateur actuel sont utilisées lors de la sélection d'un fichier dans cette page.</span><span class="sxs-lookup"><span data-stu-id="11992-107">The credentials of the current user are used when selecting a file in this page.</span></span> <span data-ttu-id="11992-108">Toutefois, l'importation ne réussira pas si l'utilisateur spécifié dans la page Informations d'emprunt d'identité n'a pas de privilèges suffisants pour lire le fichier sélectionné.</span><span class="sxs-lookup"><span data-stu-id="11992-108">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected file.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="11992-109">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="11992-109">UI element list</span></span>  
 <span data-ttu-id="11992-110">**Nom convivial de la connexion**</span><span class="sxs-lookup"><span data-stu-id="11992-110">**Friendly connection name**</span></span>  
 <span data-ttu-id="11992-111">Tapez un nom unique pour cette connexion à la source de données.</span><span class="sxs-lookup"><span data-stu-id="11992-111">Type a unique name for this data source connection.</span></span> <span data-ttu-id="11992-112">Ce champ est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="11992-112">This is a required field.</span></span>  
  
 <span data-ttu-id="11992-113">**Nom de la base de données**</span><span class="sxs-lookup"><span data-stu-id="11992-113">**Database name**</span></span>  
 <span data-ttu-id="11992-114">Spécifiez le chemin d'accès complet à un fichier de base de données Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="11992-114">Specify the full path for a Microsoft Access database file.</span></span>  
  
 <span data-ttu-id="11992-115">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="11992-115">**Browse**</span></span>  
 <span data-ttu-id="11992-116">Accédez à un emplacement dans lequel un fichier de base de données Microsoft Access est disponible.</span><span class="sxs-lookup"><span data-stu-id="11992-116">Navigate to a location where a Microsoft Access database file is available.</span></span>  
  
 <span data-ttu-id="11992-117">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="11992-117">**User name**</span></span>  
 <span data-ttu-id="11992-118">Spécifiez un nom d'utilisateur pour la connexion de base de données.</span><span class="sxs-lookup"><span data-stu-id="11992-118">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="11992-119">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="11992-119">**Password**</span></span>  
 <span data-ttu-id="11992-120">Spécifiez un mot de passe pour la connexion de base de données.</span><span class="sxs-lookup"><span data-stu-id="11992-120">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="11992-121">**Enregistrer mon mot de passe**</span><span class="sxs-lookup"><span data-stu-id="11992-121">**Save my password**</span></span>  
 <span data-ttu-id="11992-122">Précisez si le mot de passe que vous avez entré dans la zone **Mot de passe** est mémorisé.</span><span class="sxs-lookup"><span data-stu-id="11992-122">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="11992-123">**Avancée**</span><span class="sxs-lookup"><span data-stu-id="11992-123">**Advanced**</span></span>  
 <span data-ttu-id="11992-124">Définissez des propriétés de connexion supplémentaires à l’aide de la boîte de dialogue **Définir les propriétés avancées** .</span><span class="sxs-lookup"><span data-stu-id="11992-124">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span>  
  
 <span data-ttu-id="11992-125">**Tester la connexion**</span><span class="sxs-lookup"><span data-stu-id="11992-125">**Test Connection**</span></span>  
 <span data-ttu-id="11992-126">Essayez d'établir une connexion à la source de données à l'aide des paramètres actuels.</span><span class="sxs-lookup"><span data-stu-id="11992-126">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="11992-127">Un message est affiché pour indiquer si la connexion a abouti.</span><span class="sxs-lookup"><span data-stu-id="11992-127">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
