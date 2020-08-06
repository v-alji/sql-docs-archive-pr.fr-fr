---
title: Analyser dans Excel (onglet navigateur, concepteur de cube) (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.browsecube.datapane.f1
- sql12.asvs.ssms.analyzeinexcel.f1
ms.assetid: 890ed457-137e-44ac-9b2c-83344a1b8fc9
author: minewiskan
ms.author: owend
ms.openlocfilehash: b9fa27ae291d40b7f5637e3968438fcaec1de03d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602636"
---
# <a name="analyze-in-excel-browser-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="3eaa8-102">Analyser dans Excel (onglet Explorateur, Concepteur de cube) (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="3eaa8-102">Analyze in Excel (Browser Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="3eaa8-103">La fonctionnalité**Analyser dans Excel** permet au développeur du cube de vérifier rapidement la façon dont un projet est présenté à l'utilisateur final.</span><span class="sxs-lookup"><span data-stu-id="3eaa8-103">**Analyze in Excel** provides the cube developer with a way to quickly review how a project would look to the end user.</span></span> <span data-ttu-id="3eaa8-104">La fonctionnalité **Analyser dans Excel** ouvre l'application Microsoft Excel, crée une connexion de source de données à la base de données de l'espace de travail, puis ajoute automatiquement un tableau croisé dynamique à la feuille de calcul.</span><span class="sxs-lookup"><span data-stu-id="3eaa8-104">The **Analyze in Excel** feature opens Microsoft Excel, creates a data source connection to the workspace database, and automatically adds a PivotTable to the worksheet.</span></span> <span data-ttu-id="3eaa8-105">Cette fonction remplace le composant Office Web Control qui fournissait un tableau croisé dynamique incorporé dans l'onglet Navigateur dans les versions précédentes.</span><span class="sxs-lookup"><span data-stu-id="3eaa8-105">This feature replaces the Office Web Control that provided an embedded PivotTable in the Browser tab in previous releases.</span></span>  
  
 <span data-ttu-id="3eaa8-106">**Pour afficher les données du cube :**</span><span class="sxs-lookup"><span data-stu-id="3eaa8-106">**To view cube data:**</span></span>  
  
1.  <span data-ttu-id="3eaa8-107">Dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dans l’Explorateur de solutions, double-cliquez sur un cube pour l’ouvrir dans le Concepteur de cube.</span><span class="sxs-lookup"><span data-stu-id="3eaa8-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], in Solution Explorer, double-click a cube to open it in Cube Designer.</span></span>  
  
2.  <span data-ttu-id="3eaa8-108">Cliquez sur l'onglet **Navigateur** .</span><span class="sxs-lookup"><span data-stu-id="3eaa8-108">Click the **Browser** tab.</span></span>  
  
3.  <span data-ttu-id="3eaa8-109">Cliquez sur **Reconnecter** pour valider la connexion.</span><span class="sxs-lookup"><span data-stu-id="3eaa8-109">Click **Reconnect** to validate the connection.</span></span>  
  
4.  <span data-ttu-id="3eaa8-110">Cliquez sur l'icône Excel dans la barre de menus.</span><span class="sxs-lookup"><span data-stu-id="3eaa8-110">Click the Excel icon in the menu bar.</span></span>  
  
5.  <span data-ttu-id="3eaa8-111">Cliquez sur **Activer**lorsque vous êtes invité à activer les connexions de données.</span><span class="sxs-lookup"><span data-stu-id="3eaa8-111">When asked to enable data connections, click **Enable**.</span></span> <span data-ttu-id="3eaa8-112">Excel s'ouvre en utilisant la connexion de données active et ajoute un tableau croisé dynamique à la feuille de calcul afin que vous puissiez commencer à parcourir vos données.</span><span class="sxs-lookup"><span data-stu-id="3eaa8-112">Excel opens using the current data connection, adding a PivotTable to the worksheet so that you can begin browsing your data.</span></span>  
  
 <span data-ttu-id="3eaa8-113">Vous pouvez à présent générer un tableau croisé dynamique de façon interactive en faisant glisser des mesures de la table des faits vers la zone des valeurs, et des attributs de dimension vers les zones Ligne et Colonne.</span><span class="sxs-lookup"><span data-stu-id="3eaa8-113">You can now build a PivotTable interactively by dragging measures from the fact table to the Values area, and dimension attributes to the Row and Column areas.</span></span> <span data-ttu-id="3eaa8-114">Si vous avez des hiérarchies, ajoutez-les aux zones Ligne ou Colonne.</span><span class="sxs-lookup"><span data-stu-id="3eaa8-114">If you have hierarchies, add them to Rows or Column areas.</span></span> <span data-ttu-id="3eaa8-115">Vous pouvez réduire ou développer la hiérarchie pour parcourir les données de faits à des niveaux différents.</span><span class="sxs-lookup"><span data-stu-id="3eaa8-115">You can roll up or drill down the hierarchy to browse fact data at different levels.</span></span>  
  
 <span data-ttu-id="3eaa8-116">Les objets et les données sont affichés dans le contexte du rôle ou de l'utilisateur effectif et de la perspective.</span><span class="sxs-lookup"><span data-stu-id="3eaa8-116">Objects and data are viewed within the context of the effective user or role and perspective.</span></span> <span data-ttu-id="3eaa8-117">Lorsque vous utilisez Excel, les informations d'identification de l'utilisateur actuel, et non celles spécifiées dans la page **Informations d'emprunt d'identité** , sont utilisées pour la connexion à la source de données lorsqu'une requête est exécutée.</span><span class="sxs-lookup"><span data-stu-id="3eaa8-117">When using Excel, the credentials of the current user, not the credentials specified in the **Impersonation Information** page, are used to connect to the data source when a query is executed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3eaa8-118">Pour utiliser la fonctionnalité Analyser dans Excel, Excel doit être installé sur le même ordinateur que [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3eaa8-118">To use the Analyze in Excel feature, Excel must be installed on the same computer as [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="3eaa8-119">Si Excel n'est pas installé sur le même ordinateur, vous pouvez utiliser Excel sur un autre ordinateur et vous connecter au cube comme source de données.</span><span class="sxs-lookup"><span data-stu-id="3eaa8-119">If Excel is not installed on the same computer, you can use Excel on another computer and connect to the cube as a data source.</span></span> <span data-ttu-id="3eaa8-120">Vous pouvez ensuite ajouter manuellement un tableau croisé dynamique à la feuille de calcul.</span><span class="sxs-lookup"><span data-stu-id="3eaa8-120">You can then manually add a PivotTable to the worksheet.</span></span> <span data-ttu-id="3eaa8-121">Les objets de modèle (tables, colonnes, mesures et KPI) sont inclus en tant que champs dans la liste de champs du tableau croisé dynamique.</span><span class="sxs-lookup"><span data-stu-id="3eaa8-121">Model objects (tables, columns, measures, and KPIs) are included as fields in the PivotTable field list.</span></span>  
  
 <span data-ttu-id="3eaa8-122">Pour plus d'informations sur la fonctionnalité **Analyser dans Excel** , consultez ces ressources.</span><span class="sxs-lookup"><span data-stu-id="3eaa8-122">For more information about the **Analyze in Excel** feature, see these resources:</span></span>  
  
 [<span data-ttu-id="3eaa8-123">Analyser dans Excel &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="3eaa8-123">Analyze in Excel &#40;SSAS Tabular&#41;</span></span>](tabular-models/analyze-in-excel-ssas-tabular.md)  
  
 [<span data-ttu-id="3eaa8-124">Analyser un modèle tabulaire dans Excel &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="3eaa8-124">Analyze a Tabular Model in Excel &#40;SSAS Tabular&#41;</span></span>](tabular-models/analyze-a-tabular-model-in-excel-ssas-tabular.md)  
  
 [<span data-ttu-id="3eaa8-125">Parcourir les données et métadonnées de cube</span><span class="sxs-lookup"><span data-stu-id="3eaa8-125">Browse data and metadata in Cube</span></span>](multidimensional-models/browse-data-and-metadata-in-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="3eaa8-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3eaa8-126">See Also</span></span>  
 <span data-ttu-id="3eaa8-127">[Navigateur &#40;concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;](browser-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="3eaa8-127">[Browser &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](browser-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="3eaa8-128">[Barre d’outils &#40;onglet navigateur, concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;](toolbar-browser-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="3eaa8-128">[Toolbar &#40;Browser Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-browser-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="3eaa8-129">[Onglets du navigateur &#40;de métadonnées, concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;](metadata-browser-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="3eaa8-129">[Metadata &#40;Browser Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](metadata-browser-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="3eaa8-130">Requête et filtrage &#40;onglet navigateur, concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="3eaa8-130">Query and Filter &#40;Browser Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](query-filter-browser-cube-designer-analysis-services-multidimensional-data.md)  
  
  
