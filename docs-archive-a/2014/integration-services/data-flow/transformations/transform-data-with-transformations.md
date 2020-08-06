---
title: Transformer des données avec des transformations | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data flow [Integration Services], transformations
- transformations [Integration Services], about transformations
- transforming data [Integration Services]
ms.assetid: e1340b6f-ef75-4b14-af6f-823586eff0ed
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 952d8ea4eeea2dd8010a17a2b3deba41447b6231
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614186"
---
# <a name="transform-data-with-transformations"></a><span data-ttu-id="62c1f-102">Transformer des données avec des transformations</span><span class="sxs-lookup"><span data-stu-id="62c1f-102">Transform Data with Transformations</span></span>
  [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="62c1f-103">inclut trois types de composants de flux de données : les sources, les transformations et les destinations.</span><span class="sxs-lookup"><span data-stu-id="62c1f-103">includes three types of data flow components: sources, transformations, and destinations.</span></span>  
  
 <span data-ttu-id="62c1f-104">Le schéma suivant illustre un flux de données simple qui possède une source, deux transformations et une destination.</span><span class="sxs-lookup"><span data-stu-id="62c1f-104">The following diagram shows a simple data flow that has a source, two transformations, and a destination.</span></span>  
  
 <span data-ttu-id="62c1f-105">![Data flow](../../media/mw-dts-08.gif "Flux de données") (Flux de données)</span><span class="sxs-lookup"><span data-stu-id="62c1f-105">![Data flow](../../media/mw-dts-08.gif "Data flow")</span></span>  
  
 [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="62c1f-106">Les transformations procurent la fonctionnalité suivante :</span><span class="sxs-lookup"><span data-stu-id="62c1f-106">transformations provide the following functionality:</span></span>  
  
-   <span data-ttu-id="62c1f-107">Fractionnement, copie et fusion d'ensembles de lignes et opérations de recherche.</span><span class="sxs-lookup"><span data-stu-id="62c1f-107">Splitting, copying, and merging rowsets and performing lookup operations.</span></span>  
  
-   <span data-ttu-id="62c1f-108">Mise à jour de valeurs de colonnes et création de colonnes en appliquant des transformations telles que la modification de minuscules en majuscules.</span><span class="sxs-lookup"><span data-stu-id="62c1f-108">Updating column values and creating new columns by applying transformations such as changing lowercase to uppercase.</span></span>  
  
-   <span data-ttu-id="62c1f-109">Exécution d'opérations Business Intelligence telles que le nettoyage de données, l'exploration de texte et l'exécution de requêtes de prédictions d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="62c1f-109">Performing business intelligence operations such as cleaning data, mining text, or running data mining prediction queries.</span></span>  
  
-   <span data-ttu-id="62c1f-110">Création d'ensembles de lignes constitués de valeurs agrégées ou triées, d'échantillons de données ou de données croisées dynamiques et non croisées dynamiques.</span><span class="sxs-lookup"><span data-stu-id="62c1f-110">Creating new rowsets that consist of aggregate or sorted values, sample data, or pivoted and unpivoted data.</span></span>  
  
-   <span data-ttu-id="62c1f-111">Exécution de tâches telles que l'exportation et l'importation de données, l'apport d'informations d'audit et l'utilisation de dimensions à variation lente.</span><span class="sxs-lookup"><span data-stu-id="62c1f-111">Performing tasks such as exporting and importing data, providing audit information, and working with slowly changing dimensions.</span></span>  
  
 <span data-ttu-id="62c1f-112">Pour plus d’informations, consultez [Transformations Integration Services](integration-services-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="62c1f-112">For more information, see [Integration Services Transformations](integration-services-transformations.md).</span></span>  
  
 <span data-ttu-id="62c1f-113">Vous pouvez également écrire des transformations personnalisées.</span><span class="sxs-lookup"><span data-stu-id="62c1f-113">You can also write custom transformations.</span></span> <span data-ttu-id="62c1f-114">Pour plus d’informations, consultez [Développement d’un composant de flux de données personnalisé](../../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) et [Développement de types spécifiques de composants de flux de données](../../extending-packages-custom-objects-data-flow-types/developing-specific-types-of-data-flow-components.md).</span><span class="sxs-lookup"><span data-stu-id="62c1f-114">For more information, see [Developing a Custom Data Flow Component](../../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) and [Developing Specific Types of Data Flow Components](../../extending-packages-custom-objects-data-flow-types/developing-specific-types-of-data-flow-components.md).</span></span>  
  
 <span data-ttu-id="62c1f-115">Après avoir ajouté la transformation au concepteur de flux de données, mais avant de configurer la transformation, vous devez connecter la transformation au flux de données en connectant la sortie d'une autre transformation ou source du flux de données à l'entrée de cette transformation.</span><span class="sxs-lookup"><span data-stu-id="62c1f-115">After you add the transformation to the data flow designer, but before you configure the transformation, you connect the transformation to the data flow by connecting the output of another transformation or source in the data flow to the input of this transformation.</span></span> <span data-ttu-id="62c1f-116">Le connecteur entre ces deux composants de flux de données porte le nom de chemin d'accès.</span><span class="sxs-lookup"><span data-stu-id="62c1f-116">The connector between two data flow components is called a path.</span></span> <span data-ttu-id="62c1f-117">Pour plus d’informations sur la connexion des composants et l’utilisation des chemins d’accès, consultez [Connecter des composants avec des chemins d’accès](../../connect-components-with-paths.md).</span><span class="sxs-lookup"><span data-stu-id="62c1f-117">For more information about connecting components and working with paths, see [Connect Components with Paths](../../connect-components-with-paths.md).</span></span>  
  
### <a name="to-add-a-transformation-to-a-data-flow"></a><span data-ttu-id="62c1f-118">Pour ajouter une transformation à un flux de données</span><span class="sxs-lookup"><span data-stu-id="62c1f-118">To add a transformation to a data flow</span></span>  
  
-   [<span data-ttu-id="62c1f-119">Ajouter ou supprimer un composant dans un flux de données</span><span class="sxs-lookup"><span data-stu-id="62c1f-119">Add or Delete a Component in a Data Flow</span></span>](../add-or-delete-a-component-in-a-data-flow.md)  
  
### <a name="to-connect-a-transformation-to-a-data-flow"></a><span data-ttu-id="62c1f-120">Pour connecter une transformation à un flux de données</span><span class="sxs-lookup"><span data-stu-id="62c1f-120">To connect a transformation to a data flow</span></span>  
  
-   [<span data-ttu-id="62c1f-121">Connecter des composants dans un flux de données</span><span class="sxs-lookup"><span data-stu-id="62c1f-121">Connect Components in a Data Flow</span></span>](../connect-components-in-a-data-flow.md)  
  
### <a name="to-set-the-properties-of-a-transformation"></a><span data-ttu-id="62c1f-122">Pour définir les propriétés d'une transformation</span><span class="sxs-lookup"><span data-stu-id="62c1f-122">To set the properties of a transformation</span></span>  
  
-   [<span data-ttu-id="62c1f-123">Définir les propriétés d’un composant de flux de données</span><span class="sxs-lookup"><span data-stu-id="62c1f-123">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
## <a name="see-also"></a><span data-ttu-id="62c1f-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="62c1f-124">See Also</span></span>  
 <span data-ttu-id="62c1f-125">[Tâche de flux de données](../../control-flow/data-flow-task.md) </span><span class="sxs-lookup"><span data-stu-id="62c1f-125">[Data Flow Task](../../control-flow/data-flow-task.md) </span></span>  
 <span data-ttu-id="62c1f-126">[Flux de données](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="62c1f-126">[Data Flow](../data-flow.md) </span></span>  
 <span data-ttu-id="62c1f-127">[Connecter des composants avec des chemins](../../connect-components-with-paths.md) </span><span class="sxs-lookup"><span data-stu-id="62c1f-127">[Connect Components with Paths](../../connect-components-with-paths.md) </span></span>  
 <span data-ttu-id="62c1f-128">[Gestion des erreurs dans les données](../error-handling-in-data.md) </span><span class="sxs-lookup"><span data-stu-id="62c1f-128">[Error Handling in Data](../error-handling-in-data.md) </span></span>  
 [<span data-ttu-id="62c1f-129">Flux de données</span><span class="sxs-lookup"><span data-stu-id="62c1f-129">Data Flow</span></span>](../data-flow.md)  
  
  
