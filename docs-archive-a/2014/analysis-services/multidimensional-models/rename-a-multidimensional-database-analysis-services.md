---
title: Renommer une base de données multidimensionnelle (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- renaming databases
ms.assetid: 15fdaec7-f3e4-44d9-9b78-1a1d78c484e0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3974e7671aff5d1cba22b10563bbc85a129a1dff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611359"
---
# <a name="rename-a-multidimensional-database-analysis-services"></a><span data-ttu-id="25386-102">Renommer une base de données multidimensionnelle (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="25386-102">Rename a Multidimensional Database (Analysis Services)</span></span>
  <span data-ttu-id="25386-103">La façon dont vous modifiez le nom d’une [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] base de données dépend de la façon dont vous vous connectez à la [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] base de données.</span><span class="sxs-lookup"><span data-stu-id="25386-103">The manner in which you change the name of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database depends upon how you connect to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="25386-104">Pour modifier le nom d'une base de données existante, vous devez vous connecter à l'aide du mode en ligne.</span><span class="sxs-lookup"><span data-stu-id="25386-104">To change the name of an existing database, you must connect in online mode.</span></span> <span data-ttu-id="25386-105">Pour modifier le nom de la base de données dans laquelle des objets d'un projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] seront instanciés, vous devez vous connecter à l'aide du mode projet.</span><span class="sxs-lookup"><span data-stu-id="25386-105">To change the name of the database into which objects in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project will be instantiated, you must connect in project mode.</span></span>  
  
### <a name="to-change-the-database-name-in-online-mode"></a><span data-ttu-id="25386-106">Pour modifier le nom de la base de données en mode en ligne</span><span class="sxs-lookup"><span data-stu-id="25386-106">To change the database name in online mode</span></span>  
  
1.  <span data-ttu-id="25386-107">Connectez-vous directement à la base de données [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]à l'aide de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25386-107">Using [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], connect directly to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="25386-108">Dans l’Explorateur de solutions, cliquez avec le bouton droit sur la base de données, puis cliquez sur **Modifier la base de données**.</span><span class="sxs-lookup"><span data-stu-id="25386-108">In Solution Explorer, right-click the database and then click **Edit Database**.</span></span>  
  
3.  <span data-ttu-id="25386-109">Dans la zone de texte **Nom de la base de données** , modifiez le nom de la base de données.</span><span class="sxs-lookup"><span data-stu-id="25386-109">In the **Database name** text box, change the database name.</span></span>  
  
4.  <span data-ttu-id="25386-110">Dans la barre d'outils, cliquez sur **Enregistrer** ou sur **Enregistrer tout** , ou, dans le menu **Fichier** , cliquez sur **Enregistrer les éléments sélectionnés** ou sur **Enregistrer tout** , ou, fermez le **Concepteur de bases de données** , puis cliquez sur **Enregistrer** à l'invite.</span><span class="sxs-lookup"><span data-stu-id="25386-110">Click **Save** or **Save All** on the toolbar, click **Save Selected Items** or **Save All** on the **File** menu, or close the **Database Designer** and then click **Save** when prompted.</span></span>  
  
     <span data-ttu-id="25386-111">Le nom de la base de données est mis à jour dans l'instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] et l'objet base de données est actualisé dans l'Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="25386-111">The database name is updated in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and the database object in Solution Explorer is refreshed.</span></span>  
  
### <a name="to-change-the-database-name-in-project-mode"></a><span data-ttu-id="25386-112">Pour modifier le nom de la base de données en mode projet</span><span class="sxs-lookup"><span data-stu-id="25386-112">To change the database name in project mode</span></span>  
  
1.  <span data-ttu-id="25386-113">Ouvrez le projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25386-113">Open the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="25386-114">Dans l’Explorateur de solutions, cliquez avec le bouton droit sur le projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="25386-114">In Solution Explorer, right-click the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="25386-115">Dans la boîte de dialogue **Pages de propriétés** sous **Propriétés de configuration** , sélectionnez **Déploiement** .</span><span class="sxs-lookup"><span data-stu-id="25386-115">In the **Property Pages** dialog box, click **Deployment** in the **Configuration Properties** section.</span></span>  
  
4.  <span data-ttu-id="25386-116">Affectez à la propriété **Database** le nom de la nouvelle base de données.</span><span class="sxs-lookup"><span data-stu-id="25386-116">Change the **Database** property to the new database name.</span></span>  
  
     <span data-ttu-id="25386-117">La prochaine fois que le projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] sera déployé, le déploiement s'effectuera dans cette nouvelle base de données.</span><span class="sxs-lookup"><span data-stu-id="25386-117">The next time the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project is deployed, it will be deployed to this new database name.</span></span> <span data-ttu-id="25386-118">Si cette base de données existe déjà, elle sera remplacée.</span><span class="sxs-lookup"><span data-stu-id="25386-118">If this database already exists, it will be overwritten.</span></span>  
  
### <a name="to-change-the-database-name-using-sql-server-management-studio"></a><span data-ttu-id="25386-119">Pour modifier le nom de la base de données à l'aide de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="25386-119">To change the database name using SQL Server Management Studio</span></span>  
  
-   <span data-ttu-id="25386-120">Cliquez avec le bouton droit sur la base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , puis modifiez la propriété Name.</span><span class="sxs-lookup"><span data-stu-id="25386-120">Right-click the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database and edit the Name property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25386-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="25386-121">See Also</span></span>  
 <span data-ttu-id="25386-122">[Configurer les propriétés du serveur dans Analysis Services](../server-properties/server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="25386-122">[Configure Server Properties in Analysis Services](../server-properties/server-properties-in-analysis-services.md) </span></span>  
 <span data-ttu-id="25386-123">[Définir les propriétés d’une base de données multidimensionnelle &#40;Analysis Services&#41;](set-multidimensional-database-properties-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="25386-123">[Set Multidimensional Database Properties &#40;Analysis Services&#41;](set-multidimensional-database-properties-analysis-services.md) </span></span>  
 <span data-ttu-id="25386-124">[Configurez Analysis Services propriétés du projet &#40;SSDT&#41;](configure-analysis-services-project-properties-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="25386-124">[Configure Analysis Services Project Properties &#40;SSDT&#41;](configure-analysis-services-project-properties-ssdt.md) </span></span>  
 [<span data-ttu-id="25386-125">Déployer des projets Analysis Services &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="25386-125">Deploy Analysis Services Projects &#40;SSDT&#41;</span></span>](deploy-analysis-services-projects-ssdt.md)  
  
  
