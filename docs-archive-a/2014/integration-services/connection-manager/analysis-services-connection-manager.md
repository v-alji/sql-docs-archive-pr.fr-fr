---
title: Gestionnaire de connexions Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], Analysis Services
- connection managers [Integration Services], Analysis Services
- Analysis Services connection manager
ms.assetid: 9f9cadad-a1d0-4db5-98f5-df5dbbec1be4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b5da84acd131b75ef9ea174986836265934fb44b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605679"
---
# <a name="analysis-services-connection-manager"></a><span data-ttu-id="7ccd5-102">Gestionnaire de connexions Analysis Services</span><span class="sxs-lookup"><span data-stu-id="7ccd5-102">Analysis Services Connection Manager</span></span>
  <span data-ttu-id="7ccd5-103">Un gestionnaire de connexions [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] permet à un package de se connecter à un serveur qui exécute une base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ou à un projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] qui procure un accès à des données de cube et de dimension.</span><span class="sxs-lookup"><span data-stu-id="7ccd5-103">An [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager enables a package to connect to a server that runs an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database or to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project that provides access to cube and dimension data.</span></span> <span data-ttu-id="7ccd5-104">La connexion à un projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] est possible uniquement pendant le développement de packages dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7ccd5-104">You can only connect to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project while developing packages in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="7ccd5-105">Au moment de l'exécution, les packages se connectent au serveur et à la base de données sur lesquels vous avez déployé le projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7ccd5-105">At run time, packages connect to the server and the database to which you deployed the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span>  
  
 <span data-ttu-id="7ccd5-106">Les tâches (telles que la tâche DDL d’exécution [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] et la tâche de traitement [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ) et les destinations (telles que la destination Apprentissage du modèle d’exploration de données) utilisent un gestionnaire de connexions [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7ccd5-106">Both tasks, such as the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Execute DDL task and the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Processing task, and destinations, such as the Data Mining Model Training destination, use an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager.</span></span>  
  
 <span data-ttu-id="7ccd5-107">Pour plus d’informations sur les bases de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], consultez [Bases de données de modèle multidimensionnel &#40;SSAS&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/multidimensional-model-databases-ssas).</span><span class="sxs-lookup"><span data-stu-id="7ccd5-107">For more information about [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] databases, see [Multidimensional Model Databases &#40;SSAS&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/multidimensional-model-databases-ssas).</span></span>  
  
## <a name="configuration-of-the-analysis-services-connection-manager"></a><span data-ttu-id="7ccd5-108">Configuration du gestionnaire de connexions Analysis Services</span><span class="sxs-lookup"><span data-stu-id="7ccd5-108">Configuration of the Analysis Services Connection Manager</span></span>  
 <span data-ttu-id="7ccd5-109">Lorsque vous ajoutez un [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Gestionnaire de connexions à un package, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crée un gestionnaire de connexions qui est résolu en tant que [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connexion au moment de l’exécution, définit les propriétés du gestionnaire de connexions et ajoute le gestionnaire de connexions à la `Connections` collection sur le package.</span><span class="sxs-lookup"><span data-stu-id="7ccd5-109">When you add an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to a package, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that is resolved as an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="7ccd5-110">La propriété `ConnectionManagerType` du gestionnaire de connexions a pour valeur `MSOLAP100`.</span><span class="sxs-lookup"><span data-stu-id="7ccd5-110">The `ConnectionManagerType` property of the connection manager is set to `MSOLAP100`.</span></span>  
  
 <span data-ttu-id="7ccd5-111">Vous pouvez configurer le gestionnaire de connexions [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] comme suit :</span><span class="sxs-lookup"><span data-stu-id="7ccd5-111">You can configure the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="7ccd5-112">Spécifiez une chaîne de connexion configurée de façon à satisfaire les exigences du fournisseur Microsoft OLE pour Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="7ccd5-112">Provide a connection string configured to meet the requirements of the Microsoft OLE Provider for Analysis Services provider.</span></span>  
  
-   <span data-ttu-id="7ccd5-113">Spécifiez l'instance de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ou le projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] auquel se connecter.</span><span class="sxs-lookup"><span data-stu-id="7ccd5-113">Specify the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] or the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project to connect to.</span></span>  
  
-   <span data-ttu-id="7ccd5-114">Si vous vous connectez à une instance de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], spécifiez le mode d'authentification.</span><span class="sxs-lookup"><span data-stu-id="7ccd5-114">If you are connecting to an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], specify the authentication mode.</span></span>  
  
-   <span data-ttu-id="7ccd5-115">Indiquez si la connexion créée à partir du gestionnaire de connexions est conservée au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="7ccd5-115">Indicate whether the connection that is created from the connection manager is retained at run time.</span></span>  
  
 <span data-ttu-id="7ccd5-116">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="7ccd5-116">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="7ccd5-117">Pour plus d’informations sur les propriétés que vous pouvez définir dans le Concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="7ccd5-117">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topic:</span></span>  
  
-   [<span data-ttu-id="7ccd5-118">Référence de l’interface utilisateur de la boîte de dialogue Ajout d’un gestionnaire de connexions Analysis Services</span><span class="sxs-lookup"><span data-stu-id="7ccd5-118">Add Analysis Services Connection Manager Dialog Box UI Reference</span></span>](add-analysis-services-connection-manager-dialog-box-ui-reference.md)  
  
 <span data-ttu-id="7ccd5-119">Pour plus d’informations sur la configuration d’un gestionnaire de connexions par programmation, consultez <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> et [Ajout de connexions par programme](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="7ccd5-119">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
  
