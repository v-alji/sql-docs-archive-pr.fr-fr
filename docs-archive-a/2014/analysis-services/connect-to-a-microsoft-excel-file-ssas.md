---
title: Se connecter à un fichier Microsoft Excel (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connexcelfile.f1
ms.assetid: 126f7d6b-d270-40e7-b23e-8d114f87065b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 79bb3d57470be8acbbb990dde71cf21b62b3cb2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602470"
---
# <a name="connect-to-a-microsoft-excel-file-ssas"></a><span data-ttu-id="85af2-102">Connexion à un fichier Microsoft Excel (SSAS)</span><span class="sxs-lookup"><span data-stu-id="85af2-102">Connect to a Microsoft Excel File (SSAS)</span></span>
  <span data-ttu-id="85af2-103">Cette page de l' **Assistant Importation de table** vous permet de vous connecter à un fichier Microsoft Excel stocké sur l'ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="85af2-103">This page of the **Table Import Wizard** enables you to connect to a Microsoft Excel file stored on the local machine.</span></span> <span data-ttu-id="85af2-104">Pour accéder à l'Assistant [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dans le menu **Modèle** , cliquez sur **Importer à partir de la source de données**.</span><span class="sxs-lookup"><span data-stu-id="85af2-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="85af2-105">Pour vous connecter à un fichier Excel, vous devez disposer du fournisseur ACE approprié, installé sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="85af2-105">To connect to a Microsoft Excel file, you must have the appropriate ACE provider installed on your computer.</span></span> <span data-ttu-id="85af2-106">Pour plus d’informations, consultez [Sources de données prises en charge &#40;SSAS Tabulaire&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="85af2-106">For more information, see [Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="85af2-107">Les informations d'identification de l'utilisateur actuel sont utilisées lors de la sélection d'un fichier dans cette page.</span><span class="sxs-lookup"><span data-stu-id="85af2-107">The credentials of the current user are used when selecting a file in this page.</span></span> <span data-ttu-id="85af2-108">Toutefois, l'importation ne réussira pas si l'utilisateur spécifié dans la page Informations d'emprunt d'identité n'a pas de privilèges suffisants pour lire le fichier sélectionné.</span><span class="sxs-lookup"><span data-stu-id="85af2-108">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected file.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="85af2-109">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="85af2-109">UI element list</span></span>  
 <span data-ttu-id="85af2-110">**Nom convivial de la connexion**</span><span class="sxs-lookup"><span data-stu-id="85af2-110">**Friendly connection name**</span></span>  
 <span data-ttu-id="85af2-111">Tapez un nom unique pour cette connexion à la source de données.</span><span class="sxs-lookup"><span data-stu-id="85af2-111">Type a unique name for this data source connection.</span></span> <span data-ttu-id="85af2-112">Ce champ est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="85af2-112">This is a required field.</span></span>  
  
 <span data-ttu-id="85af2-113">**Chemin du fichier Excel**</span><span class="sxs-lookup"><span data-stu-id="85af2-113">**Excel File Path**</span></span>  
 <span data-ttu-id="85af2-114">Spécifiez le chemin d'accès complet du fichier Excel.</span><span class="sxs-lookup"><span data-stu-id="85af2-114">Specify a full path for the Excel file.</span></span>  
  
 <span data-ttu-id="85af2-115">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="85af2-115">**Browse**</span></span>  
 <span data-ttu-id="85af2-116">Accédez à un emplacement dans lequel un fichier Excel est disponible.</span><span class="sxs-lookup"><span data-stu-id="85af2-116">Navigate to a location where an Excel file is available.</span></span>  
  
 <span data-ttu-id="85af2-117">**Avancée**</span><span class="sxs-lookup"><span data-stu-id="85af2-117">**Advanced**</span></span>  
 <span data-ttu-id="85af2-118">Définissez des propriétés de connexion supplémentaires à l’aide de la boîte de dialogue **définir les propriétés avancées** .</span><span class="sxs-lookup"><span data-stu-id="85af2-118">Set additional connection properties by using the **Set Advanced Properties** dialog box..</span></span>  
  
 <span data-ttu-id="85af2-119">**Utiliser la première ligne comme en-têtes de colonnes**</span><span class="sxs-lookup"><span data-stu-id="85af2-119">**Use first row as column headers**</span></span>  
 <span data-ttu-id="85af2-120">Spécifiez s'il convient d'utiliser la première ligne de données comme en-têtes de colonnes de la table de destination.</span><span class="sxs-lookup"><span data-stu-id="85af2-120">Specify whether to use the first data row as the column headers of the destination table.</span></span>  
  
 <span data-ttu-id="85af2-121">**Tester la connexion**</span><span class="sxs-lookup"><span data-stu-id="85af2-121">**Test Connection**</span></span>  
 <span data-ttu-id="85af2-122">Essayez d'établir une connexion à la source de données à l'aide des paramètres actuels.</span><span class="sxs-lookup"><span data-stu-id="85af2-122">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="85af2-123">Un message est affiché pour indiquer si la connexion a abouti.</span><span class="sxs-lookup"><span data-stu-id="85af2-123">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
