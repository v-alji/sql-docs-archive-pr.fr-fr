---
title: Gestionnaire de connexions Excel | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- files [Integration Services], connections
- connections [Integration Services], Excel
- Excel [Integration Services]
- connection managers [Integration Services], Excel
ms.assetid: 667419f2-74fb-4b50-b963-9197d1368cda
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7561361c6d4ab7e22282b25367906aa4b75e5bc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604689"
---
# <a name="excel-connection-manager"></a><span data-ttu-id="7b2d6-102">Gestionnaire de connexions Excel</span><span class="sxs-lookup"><span data-stu-id="7b2d6-102">Excel Connection Manager</span></span>
  <span data-ttu-id="7b2d6-103">Un gestionnaire de connexions Excel permet à un package de se connecter à un fichier [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-103">An Excel connection manager enables a package to connect to an existing [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel workbook file.</span></span> <span data-ttu-id="7b2d6-104">La source Excel et la destination Excel qui [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] incluent utilisent le gestionnaire de connexions Excel.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-104">The Excel source and the Excel destination that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] include use the Excel connection manager.</span></span>  
  
 <span data-ttu-id="7b2d6-105">Lorsque vous ajoutez un gestionnaire de connexions Excel à un package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crée un gestionnaire de connexions qui sera converti en connexion Excel au moment de l'exécution, définit les propriétés du gestionnaire de connexions et ajoute le gestionnaire de connexions à la collection `Connections` du package.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-105">When you add an Excel connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that is resolved as an Excel connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="7b2d6-106">La propriété `ConnectionManagerType` du gestionnaire de connexions a pour valeur `EXCEL`.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-106">The `ConnectionManagerType` property of the connection manager is set to `EXCEL`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7b2d6-107">Vous ne pouvez pas vous connecter à un fichier Excel protégé par mot de passe.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-107">You cannot connect to a password-protected Excel file.</span></span>  
  
## <a name="configuration-of-the-excel-connection-manager"></a><span data-ttu-id="7b2d6-108">Configuration du gestionnaire de connexions Excel</span><span class="sxs-lookup"><span data-stu-id="7b2d6-108">Configuration of the Excel Connection Manager</span></span>  
 <span data-ttu-id="7b2d6-109">Vous pouvez configurer le gestionnaire de connexions Excel de plusieurs manières :</span><span class="sxs-lookup"><span data-stu-id="7b2d6-109">You can configure the Excel connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="7b2d6-110">Spécifiez le chemin d'accès du fichier Excel.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-110">Specify the path of the Excel workbook file.</span></span>  
  
-   <span data-ttu-id="7b2d6-111">Spécifiez la version d'Excel utilisée pour créer le fichier.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-111">Specify the version of Excel that was used to create the file.</span></span>  
  
-   <span data-ttu-id="7b2d6-112">Indiquez si la première ligne des données qui ont fait l'objet d'un accès dans les feuilles de calcul ou les plages sélectionnées contient les noms de colonnes.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-112">Indicate whether the first row of accessed data in the selected worksheets or ranges contains column names.</span></span>  
  
 <span data-ttu-id="7b2d6-113">Si le gestionnaire de connexions Excel est utilisé par une source Excel, les noms de colonnes sont inclus avec les données extraites.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-113">If the Excel connection manager is used by an Excel source, the column names are included with the extracted data.</span></span> <span data-ttu-id="7b2d6-114">S'il est utilisé par une destination Excel, les noms de colonnes sont inclus dans les données écrites.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-114">If it is used by an Excel destination, the column names are included in the written data.</span></span>  
  
 <span data-ttu-id="7b2d6-115">Le gestionnaire de connexions Excel utilise le fournisseur [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB pour Jet 4.0 et son pilote de prise en charge Excel ISAM (Indexed Sequential Access Method) pour se connecter aux sources de données Excel, puis y lire et écrire des données.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-115">The Excel connection manager uses the [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider for Jet 4.0 and its supporting Excel ISAM (Indexed Sequential Access Method) driver to connect and read and write data to Excel data sources.</span></span> <span data-ttu-id="7b2d6-116">Pour plus d’informations sur le comportement de ce fournisseur et de ce pilote lorsqu’il est utilisé avec des sources Excel et des destinations Excel, consultez [source](../data-flow/excel-source.md) Excel et [destination](../data-flow/excel-destination.md)Excel.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-116">For more information about the behavior of this provider and driver when used with Excel sources and Excel destinations, see [Excel Source](../data-flow/excel-source.md) and [Excel Destination](../data-flow/excel-destination.md).</span></span>  
  
 <span data-ttu-id="7b2d6-117">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-117">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="7b2d6-118">Pour plus d’informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , consultez [Éditeur du gestionnaire de connexions Excel](../excel-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="7b2d6-118">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Excel Connection Manager Editor](../excel-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="7b2d6-119">Pour plus d’informations sur la configuration d’un gestionnaire de connexions par programmation, consultez <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> et [Ajout de connexions par programme](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="7b2d6-119">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
 <span data-ttu-id="7b2d6-120">Pour plus d’informations sur le bouclage dans un groupe de fichiers Excel, consultez [Effectuer une boucle dans des fichiers et des tables Excel en utilisant un conteneur de boucles Foreach](../control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="7b2d6-120">For information about looping through a group of Excel files, see [Loop through Excel Files and Tables by Using a Foreach Loop Container](../control-flow/foreach-loop-container.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="7b2d6-121">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="7b2d6-121">Related Tasks</span></span>  
  
-   [<span data-ttu-id="7b2d6-122">Effectuer une boucle dans des fichiers et des tables Excel en utilisant un conteneur de boucles Foreach</span><span class="sxs-lookup"><span data-stu-id="7b2d6-122">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](../control-flow/foreach-loop-container.md)  
  
-   [<span data-ttu-id="7b2d6-123">Importer des données à partir d’Excel ou exporter des données vers Excel avec SQL Server Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="7b2d6-123">Import data from Excel or export data to Excel with SQL Server Integration Services (SSIS)</span></span>](../load-data-to-from-excel-with-ssis.md)
  
  
