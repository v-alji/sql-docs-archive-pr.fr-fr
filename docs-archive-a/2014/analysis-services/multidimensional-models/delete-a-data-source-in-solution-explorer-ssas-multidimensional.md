---
title: Supprimer une source de données dans Explorateur de solutions (SSAS multidimensionnel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.deleteobjects.f1
helpviewer_keywords:
- data sources [Analysis Services], deleting
- deleting data sources
- removing data sources
ms.assetid: b45441ef-f909-4736-98b9-cc80d0acac99
author: minewiskan
ms.author: owend
ms.openlocfilehash: d6101c8704579894590994d88e0286197148b694
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614208"
---
# <a name="delete-a-data-source-in-solution-explorer-ssas-multidimensional"></a><span data-ttu-id="3527e-102">Supprimer une source de données dans l'Explorateur de solutions (SSAS Multidimensionnel)</span><span class="sxs-lookup"><span data-stu-id="3527e-102">Delete a Data Source in Solution Explorer (SSAS Multidimensional)</span></span>
  <span data-ttu-id="3527e-103">Vous pouvez supprimer un objet de source de données afin de l'effacer définitivement d'un projet de modèle multidimensionnel Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="3527e-103">You can delete a data source object to permanently remove it from an Analysis Services multidimensional model project.</span></span>  
  
 <span data-ttu-id="3527e-104">Dans [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], les sources de données constituent la base sur laquelle les vues de sources de données sont construites et les vues de sources de données servent à leur tour à définir des dimensions, des cubes et des structures d'exploration de données dans un projet ou une base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3527e-104">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], data sources provide the basis on which data source views are constructed, and data source views are in turn used to define dimensions, cubes, and mining structures in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or database.</span></span> <span data-ttu-id="3527e-105">Par conséquent, la suppression d'une source de données peut rendre d'autres objets [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] d'un projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] non valides.</span><span class="sxs-lookup"><span data-stu-id="3527e-105">Therefore, deleting a data source may invalidate other [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="3527e-106">Pensez à toujours vérifier la liste des objets dépendants qui est fournie avant de supprimer l'objet.</span><span class="sxs-lookup"><span data-stu-id="3527e-106">You should always review the list of dependent objects that is provided before deleting the object.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3527e-107">Les sources de données dont dépendent d’autres objets ne peuvent pas être supprimées d’une base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ouverte par [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] en mode en ligne.</span><span class="sxs-lookup"><span data-stu-id="3527e-107">Data sources on which other objects depend cannot be deleted from an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database opened by [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] in online mode.</span></span> <span data-ttu-id="3527e-108">Vous devez supprimer tous les objets de la base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] qui dépendent de cette source de données avant de supprimer la source de données.</span><span class="sxs-lookup"><span data-stu-id="3527e-108">You must delete all objects in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database that depend on that data source before deleting the data source.</span></span> <span data-ttu-id="3527e-109">Pour plus d’informations sur le mode en ligne, consultez [Connexion en mode en ligne à une base de données Analysis Services](connect-in-online-mode-to-an-analysis-services-database.md).</span><span class="sxs-lookup"><span data-stu-id="3527e-109">For more information about online mode, see [Connect in Online Mode to an Analysis Services Database](connect-in-online-mode-to-an-analysis-services-database.md).</span></span>  
  
### <a name="to-delete-a-data-source"></a><span data-ttu-id="3527e-110">Pour supprimer une source de données</span><span class="sxs-lookup"><span data-stu-id="3527e-110">To delete a data source</span></span>  
  
1.  <span data-ttu-id="3527e-111">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le projet ou connectez-vous à la base de données dans laquelle vous souhaitez supprimer une source de données.</span><span class="sxs-lookup"><span data-stu-id="3527e-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database from which you want to delete a data source.</span></span>  
  
2.  <span data-ttu-id="3527e-112">Dans **l’Explorateur de solutions**, développez le dossier **Sources de données** .</span><span class="sxs-lookup"><span data-stu-id="3527e-112">In **Solution Explorer**, expand the **Data Sources** folder.</span></span>  
  
3.  <span data-ttu-id="3527e-113">Cliquez avec le bouton droit sur la source de données, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="3527e-113">Right-click the data source, and then click **Delete**.</span></span> <span data-ttu-id="3527e-114">La boîte de dialogue **Supprimer les objets**  qui s’affiche indique les objets qui seront rendus non valides si vous supprimez la source de données.</span><span class="sxs-lookup"><span data-stu-id="3527e-114">The **Delete Objects**  dialog box appears, showing the objects that will be invalidated if you delete the data source.</span></span> <span data-ttu-id="3527e-115">Examinez soigneusement cette liste avant de cliquer sur **OK** pour supprimer la source de données.</span><span class="sxs-lookup"><span data-stu-id="3527e-115">Review this list carefully before clicking **OK** to delete the data source.</span></span>  
  
4.  <span data-ttu-id="3527e-116">Enregistrez le projet.</span><span class="sxs-lookup"><span data-stu-id="3527e-116">Save the project.</span></span>  
  
     <span data-ttu-id="3527e-117">Après avoir supprimé une source de données dans un projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , vous devez enregistrer le projet modifié. Dans le cas contraire, vous recevrez un message d’erreur la prochaine fois que vous ouvrirez le projet, car le fichier XML sous-jacent de la source de données supprimée sera manquant lorsque le projet tentera de charger la source de données supprimée.</span><span class="sxs-lookup"><span data-stu-id="3527e-117">After deleting a data source from an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, you must save the modified project or you will receive an error the next time you open the project because the underlying XML file for the deleted data source will be missing when the project attempts to load the deleted data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3527e-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3527e-118">See Also</span></span>  
 <span data-ttu-id="3527e-119">[Sources de données dans les modèles multidimensionnels](data-sources-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="3527e-119">[Data Sources in Multidimensional Models](data-sources-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="3527e-120">Sources de données prises en charge &#40;SSAS multidimensionnel&#41;</span><span class="sxs-lookup"><span data-stu-id="3527e-120">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](supported-data-sources-ssas-multidimensional.md)  
  
  
