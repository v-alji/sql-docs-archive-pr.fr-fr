---
title: Modifier ou supprimer une base de données Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- databases [Analysis Services], modifying
- removing databases
- deleting databases
- dropping databases
- databases [Analysis Services], deleting
- modifying databases
ms.assetid: e48e3988-c091-4379-aabc-4da62f709a7e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6182e91bd95754fe639e8a48548b5cab1835bdc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707944"
---
# <a name="modify-or-delete-an-analysis-services-database"></a><span data-ttu-id="6d4a1-102">Modifier ou supprimer une base de données Analysis Services</span><span class="sxs-lookup"><span data-stu-id="6d4a1-102">Modify or Delete an Analysis Services Database</span></span>
  <span data-ttu-id="6d4a1-103">Vous pouvez modifier le nom et la description d’une base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] avant son déploiement dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] et après son déploiement dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d4a1-103">You can change the name and description of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database before deployment in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and after deployment in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="6d4a1-104">Vous pouvez également régler des paramètres supplémentaires sur une base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , en fonction de l'environnement.</span><span class="sxs-lookup"><span data-stu-id="6d4a1-104">You can also adjust additional settings on an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, depending on the environment.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6d4a1-105">Vous ne pouvez pas modifier les propriétés de base de données à l'aide de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] en mode en ligne.</span><span class="sxs-lookup"><span data-stu-id="6d4a1-105">You cannot change database properties using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] in online mode.</span></span>  
  
## <a name="modifying-databases-using-sql-server-management-studio"></a><span data-ttu-id="6d4a1-106">Modification des bases de données à l'aide de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6d4a1-106">Modifying Databases Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="6d4a1-107">Une fois qu'une base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] a été déployée, vous pouvez utiliser [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour modifier le mode d'emprunt d'identité utilisé par [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] lors de la connexion à des sources de données incluses dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="6d4a1-107">Once an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database is deployed, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to change the impersonation mode used by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] when connecting to data sources contained by the database.</span></span> <span data-ttu-id="6d4a1-108">Le mode d'emprunt d'identité vous permet de spécifier le contexte de sécurité utilisé par [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] lors d'une tentative de connexion à une source de données pour des tâches de traitement, de navigation ou d'extraction.</span><span class="sxs-lookup"><span data-stu-id="6d4a1-108">The impersonation mode allows you to specify the security context used by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] when attempting to connect to a data source for processing, browsing, or drillthrough purposes.</span></span>  
  
## <a name="modifying-databases-using-sql-server-data-tools"></a><span data-ttu-id="6d4a1-109">Modification des bases de données à l'aide des outils de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="6d4a1-109">Modifying Databases Using SQL Server Data Tools</span></span>  
 <span data-ttu-id="6d4a1-110">Vous pouvez utiliser [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] en mode projet pour modifier les traductions de la légende et de la description d’un projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] utilisé pour définir une base de données.</span><span class="sxs-lookup"><span data-stu-id="6d4a1-110">You can use [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] in project mode to modify the translations for the caption and description of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project used to define a database.</span></span> <span data-ttu-id="6d4a1-111">Pour plus d’informations sur l’utilisation des traductions dans une [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] base de données, consultez [scénarios de globalisation pour Analysis Services données multidimensionnelles](../globalization-scenarios-for-analysis-services-multiidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="6d4a1-111">For more information about using translations in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, see [Globalization scenarios for Analysis Services Multiidimensional](../globalization-scenarios-for-analysis-services-multiidimensional.md).</span></span>  
  
 <span data-ttu-id="6d4a1-112">Vous pouvez également définir les alias et les fonctions d'agrégation associés aux types de comptes utilisés par les attributs de compte dans les dimensions incluses dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="6d4a1-112">You can also set the aliases and aggregation functions associated with account types used by account attributes in dimensions contained by the database.</span></span> <span data-ttu-id="6d4a1-113">Les alias vous permettent de sélectionner la terminologie d'entreprise utilisée par votre organisation pour les types de comptes dans un plan comptable.</span><span class="sxs-lookup"><span data-stu-id="6d4a1-113">Aliases allow you to select the business-specific terminology used by your organization for the account types in a chart of accounts.</span></span> <span data-ttu-id="6d4a1-114">Les types de comptes sont utilisés par les membres d'un attribut de compte pour indiquer comment agréger les mesures sur chaque membre en utilisant les fonctions d'agrégation spécifiées pour chaque type de compte inclus dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="6d4a1-114">The account types are used by members of an account attribute to indicate how to aggregate measures over each member by using the aggregation functions specified for each account type contained in the database.</span></span> <span data-ttu-id="6d4a1-115">Pour plus d’informations sur les attributs de compte, consultez [Attributs et hiérarchies d’attributs](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="6d4a1-115">For more information about account attributes, see [Attributes and Attribute Hierarchies](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md).</span></span>  
  
## <a name="deleting-databases"></a><span data-ttu-id="6d4a1-116">suppression de bases de données</span><span class="sxs-lookup"><span data-stu-id="6d4a1-116">Deleting Databases</span></span>  
 <span data-ttu-id="6d4a1-117">La suppression d'une base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] existante entraîne la suppression de la base de données et de tous les cubes, dimensions et modèles d'exploration de données inclus dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="6d4a1-117">Deleting an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database deletes the database and all cubes, dimensions, and mining models in the database.</span></span> <span data-ttu-id="6d4a1-118">Vous pouvez supprimer uniquement une base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] existante dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d4a1-118">You can only delete an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-delete-an-analysis-services-database"></a><span data-ttu-id="6d4a1-119">Pour supprimer une base de données Analysis Services</span><span class="sxs-lookup"><span data-stu-id="6d4a1-119">To delete an Analysis Services database</span></span>  
  
1.  <span data-ttu-id="6d4a1-120">Connectez-vous à une instance d’ [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6d4a1-120">Connect to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span>  
  
2.  <span data-ttu-id="6d4a1-121">Dans **l’Explorateur d’objets**, développez le nœud de l’instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connectée et vérifiez que l’objet à supprimer est visible.</span><span class="sxs-lookup"><span data-stu-id="6d4a1-121">In **Object Explorer**, expand the node for the connected [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and ensure that the object to be deleted is visible.</span></span>  
  
3.  <span data-ttu-id="6d4a1-122">Cliquez avec le bouton droit sur l’objet à supprimer et sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="6d4a1-122">Right-click the object to be deleted and select **Delete**.</span></span>  
  
4.  <span data-ttu-id="6d4a1-123">Dans la boîte de dialogue **Supprimer l'objet** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6d4a1-123">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d4a1-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6d4a1-124">See Also</span></span>  
 [<span data-ttu-id="6d4a1-125">Documenter et générer des scripts pour une base de données Analysis Services</span><span class="sxs-lookup"><span data-stu-id="6d4a1-125">Document and Script an Analysis Services Database</span></span>](document-and-script-an-analysis-services-database.md)  
  
  
