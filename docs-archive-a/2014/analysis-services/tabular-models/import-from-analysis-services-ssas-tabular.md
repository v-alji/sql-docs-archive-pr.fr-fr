---
title: Importer à partir de Analysis Services (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b9a21b23-3a06-4ef8-bc06-9c79cdc54870
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7d6c3d226e46cdb4101bc8db52830046d27b0706
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696187"
---
# <a name="import-from-analysis-services-ssas-tabular"></a><span data-ttu-id="839f7-102">Importer à partir d'Analysis Services (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="839f7-102">Import from Analysis Services (SSAS Tabular)</span></span>
  <span data-ttu-id="839f7-103">Cette rubrique explique comment créer un nouveau projet de modèle tabulaire en important les métadonnées d'un modèle tabulaire existant à l'aide du modèle de projet Importer à partir du serveur dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="839f7-103">This topic describes how to create a new tabular model project by importing the metadata from an existing tabular model by using the Import from Server project template in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="create-a-new-model-by-importing-metadata-from-an-existing-model-in-analysis-services"></a><span data-ttu-id="839f7-104">Créer un modèle en important des métadonnées d'un modèle existant dans Analysis Services</span><span class="sxs-lookup"><span data-stu-id="839f7-104">Create a new model by importing metadata from an existing model in Analysis Services</span></span>  
 <span data-ttu-id="839f7-105">Vous pouvez utiliser le modèle de projet d'importation à partir du serveur pour créer un projet de modèle tabulaire en copiant les métadonnées d'un modèle tabulaire existant sur un serveur Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="839f7-105">You can use the Import from Server project template to create a new tabular model project by copying the metadata from an existing tabular model on an Analysis Services server.</span></span> <span data-ttu-id="839f7-106">Le nouveau projet est créé avec les mêmes connexions à la source de données, tables, relations, mesures, KPI, rôles, hiérarchies, perspectives et partitions que le modèle à partir duquel il a été importé.</span><span class="sxs-lookup"><span data-stu-id="839f7-106">The new project will be created with the same data source connections, tables, relationships, measures, KPIs, roles, hierarchies, perspectives, and partitions as the model it was imported from.</span></span> <span data-ttu-id="839f7-107">Toutefois, les données ne sont pas copiées depuis le modèle existant vers le nouvel espace de travail du modèle.</span><span class="sxs-lookup"><span data-stu-id="839f7-107">The data, however, is not copied from the existing model to the new model workspace.</span></span> <span data-ttu-id="839f7-108">Une fois l'importation terminée et le nouveau projet de modèle créé, vous devez exécuter une commande Traiter tout pour charger les données des sources de données dans la nouvelle base de données model de l'espace de travail du projet.</span><span class="sxs-lookup"><span data-stu-id="839f7-108">Once the import process has completed, and the new model project created, you must run a Process All to load the data from the data sources into the new model project workspace database.</span></span>  
  
#### <a name="to-create-a-new-model-by-importing-metadata-from-an-existing-model"></a><span data-ttu-id="839f7-109">Pour créer un modèle en important des métadonnées à partir d'un modèle existant</span><span class="sxs-lookup"><span data-stu-id="839f7-109">To create a new model by importing metadata from an existing model</span></span>  
  
1.  <span data-ttu-id="839f7-110">Dans le menu [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]Fichier **de** , cliquez sur **Nouveau**, puis sur **Projet**.</span><span class="sxs-lookup"><span data-stu-id="839f7-110">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], on the **File** menu, click **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="839f7-111">Dans la boîte de dialogue **Nouveau projet** , sous **Modèles installés**, cliquez sur **Business Intelligence**puis sur **Importer à partir du serveur**.</span><span class="sxs-lookup"><span data-stu-id="839f7-111">In the **New Project** dialog box, under **Installed Templates**, click **Business Intelligence**, and then click **Import from Server**.</span></span>  
  
3.  <span data-ttu-id="839f7-112">Pour le **Nom**, tapez un nom pour le projet, puis spécifiez un emplacement et le nom de la solution et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="839f7-112">In **Name**, type a name for the project, then specify a location and solution name, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="839f7-113">Dans la boîte de dialogue **Importer à partir d'Analysis Services** , dans la zone **Nom du serveur**tapez le nom du serveur Analysis Services qui contient les métadonnées du modèle que vous souhaitez importer.</span><span class="sxs-lookup"><span data-stu-id="839f7-113">In the **Import from Analysis Services** dialog box, in **Server Name**, specify the name of the Analysis Services server that contains the model metadata you want to import.</span></span>  
  
5.  <span data-ttu-id="839f7-114">Dans **Nom de la base de données**, sélectionnez la base de données du modèle tabulaire qui contient les métadonnées du modèle que vous souhaitez importer, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="839f7-114">In **Database Name**, select the tabular model database that contains the model metadata you want to import, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="839f7-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="839f7-115">See Also</span></span>  
 [<span data-ttu-id="839f7-116">Propriétés de projet &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="839f7-116">Project Properties &#40;SSAS Tabular&#41;</span></span>](properties-ssas-tabular.md)  
  
  
