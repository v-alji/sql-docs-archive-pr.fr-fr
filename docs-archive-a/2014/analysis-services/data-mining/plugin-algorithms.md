---
title: Algorithmes de plug-in | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- third-party algorithms [Analysis Services]
- algorithms [data mining], creating
- plugin algorithms [Analysis Services]
ms.assetid: fe364ddc-576e-42fc-9ced-baa399992f92
author: minewiskan
ms.author: owend
ms.openlocfilehash: ebc5e007dcc6de7fb25d59547e21f1e892100570
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703456"
---
# <a name="plugin-algorithms"></a><span data-ttu-id="72891-102">Algorithmes de plug-in</span><span class="sxs-lookup"><span data-stu-id="72891-102">Plugin Algorithms</span></span>
  <span data-ttu-id="72891-103">Outre les algorithmes [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] fournis par, il existe de nombreux autres algorithmes que vous pouvez utiliser pour l’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="72891-103">In addition to the algorithms that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides, there are many other algorithms that you can use for data mining.</span></span> <span data-ttu-id="72891-104">Ainsi, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] fournit un mécanisme d'ajout d'algorithmes créés par des concepteurs tiers.</span><span class="sxs-lookup"><span data-stu-id="72891-104">Accordingly, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides a mechanism for "plugging in" algorithms that are created by third parties.</span></span> <span data-ttu-id="72891-105">Tant que ces algorithmes respectent certaines normes, vous pouvez les utiliser dans [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] de la même manière que vous utilisez les algorithmes [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="72891-105">As long as the algorithms follow certain standards, you can use them within [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] just as you use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] algorithms.</span></span> <span data-ttu-id="72891-106">Les algorithmes de plug-in ont toutes les fonctionnalités des algorithmes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] fournis par.</span><span class="sxs-lookup"><span data-stu-id="72891-106">Plugin algorithms have all the capabilities of algorithms that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides.</span></span>  
  
 <span data-ttu-id="72891-107">Pour obtenir une description complète des interfaces qu’ [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] utilise pour communiquer avec les algorithmes de plug-in, consultez les exemples de création d’un algorithme personnalisé et d’une visionneuse de modèles personnalisés qui sont publiés sur le site web [CodePlex](https://go.microsoft.com/fwlink/?LinkID=87843) .</span><span class="sxs-lookup"><span data-stu-id="72891-107">For a full description of the interfaces that [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] uses to communicate with plugin algorithms, see the samples for creating a custom algorithm and custom model viewer that are published on [CodePlex](https://go.microsoft.com/fwlink/?LinkID=87843) Web site.</span></span>  
  
## <a name="algorithm-requirements"></a><span data-ttu-id="72891-108">Conditions préalables à l'ajout d'algorithmes</span><span class="sxs-lookup"><span data-stu-id="72891-108">Algorithm Requirements</span></span>  
 <span data-ttu-id="72891-109">Pour intégrer un algorithme dans [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], vous devez implémenter les interfaces COM suivantes :</span><span class="sxs-lookup"><span data-stu-id="72891-109">To plug an algorithm into [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you must implement the following COM interfaces:</span></span>  
  
 `IDMAlgorithm`  
 <span data-ttu-id="72891-110">Implémente un algorithme qui produit des modèles et implémente les opérations de prédiction des modèles résultants.</span><span class="sxs-lookup"><span data-stu-id="72891-110">Implements an algorithm that produces models, and implements the prediction operations of the resulting models.</span></span>  
  
 `IDMAlgorithmNavigation`  
 <span data-ttu-id="72891-111">Permet aux navigateurs d'accéder au contenu des modèles.</span><span class="sxs-lookup"><span data-stu-id="72891-111">Enables browsers to access the content of the models.</span></span>  
  
 `IDMPersist`  
 <span data-ttu-id="72891-112">Permet aux modèles dont l’algorithme effectue l’apprentissage d’être enregistrés et chargés par [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72891-112">Enables the models that the algorithm trains to be saved and loaded by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 `IDMAlgorithmMetadata`  
 <span data-ttu-id="72891-113">Décrit les capacités et les paramètres d'entrée de l'algorithme.</span><span class="sxs-lookup"><span data-stu-id="72891-113">Describes the capabilities and input parameters of the algorithm.</span></span>  
  
 `IDMAlgorithmFactory`  
 <span data-ttu-id="72891-114">Crée des instances des objets qui implémentent l'interface de l'algorithme et fournit à [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] l'accès à l'interface des métadonnées de l'algorithme.</span><span class="sxs-lookup"><span data-stu-id="72891-114">Creates instances of the objects that implement the algorithm interface, and provides [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] with access to the algorithm-metadata interface.</span></span>  
  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="72891-115">utilise ces interfaces COM pour communiquer avec les algorithmes de plug-in.</span><span class="sxs-lookup"><span data-stu-id="72891-115">uses these COM interfaces to communicate with plugin algorithms.</span></span> <span data-ttu-id="72891-116">Les algorithmes de plug-in que vous utilisez doivent prendre en charge la spécification [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB pour l’exploration de données, mais ils ne doivent pas nécessairement prendre en charge l’ensemble des options d’exploration de données définies dans la spécification.</span><span class="sxs-lookup"><span data-stu-id="72891-116">Although plugin algorithms that you use must support the [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB for Data Mining specification, they do not have to support all the data mining options in the specification.</span></span> <span data-ttu-id="72891-117">Vous pouvez utiliser l’ensemble de lignes de schéma [MINING_SERVICES](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-services-rowset) pour déterminer les fonctionnalités d’un algorithme.</span><span class="sxs-lookup"><span data-stu-id="72891-117">You can use the [MINING_SERVICES](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-services-rowset) schema rowset to determine the capabilities of an algorithm.</span></span> <span data-ttu-id="72891-118">Cet ensemble de lignes de schéma répertorie les options de prise en charge d'exploration de données pour chaque fournisseur d'algorithme de plug-in.</span><span class="sxs-lookup"><span data-stu-id="72891-118">This schema rowset lists the data mining support options for each plugin algorithm provider.</span></span>  
  
 <span data-ttu-id="72891-119">Vous devez enregistrer les nouveaux algorithmes avant de les utiliser avec [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72891-119">You must register new algorithms before you use them with [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="72891-120">Pour enregistrer un algorithme, ajoutez les informations suivantes dans le fichier .ini de l’instance d’ [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] sur laquelle vous voulez inclure les algorithmes :</span><span class="sxs-lookup"><span data-stu-id="72891-120">To register an algorithm, include the following information in the .ini file of the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] on which you want to include the algorithms:</span></span>  
  
-   <span data-ttu-id="72891-121">Le nom de l'algorithme</span><span class="sxs-lookup"><span data-stu-id="72891-121">The algorithm name</span></span>  
  
-   <span data-ttu-id="72891-122">Le ProgID (information facultative, incluse uniquement pour les algorithmes de plug-in)</span><span class="sxs-lookup"><span data-stu-id="72891-122">ProgID (this is optional and will only be included for plugin algorithms)</span></span>  
  
-   <span data-ttu-id="72891-123">Un indicateur qui signale si l'algorithme est activé ou non</span><span class="sxs-lookup"><span data-stu-id="72891-123">A flag that indicates whether the algorithm is enabled or not</span></span>  
  
 <span data-ttu-id="72891-124">L'exemple de code suivant illustre comment enregistrer un nouvel algorithme :</span><span class="sxs-lookup"><span data-stu-id="72891-124">The following code sample illustrates how to register a new algorithm:</span></span>  
  
 `<ConfigurationSettings>`  
  
 `...`  
  
 `<DataMining>`  
  
 `...`  
  
 `<Algorithms>`  
  
 `...`  
  
 `<Sample_Plugin_Algorithm>`  
  
 `<Enabled>1</Enabled>`  
  
 `<ProgID>Microsoft.DataMining.SamplePlugInAlgorithm.Factory</ProgID>`  
  
 `</Sample_PlugIn_Algorithm>`  
  
 `...`  
  
 `</Algorithms>`  
  
 `...`  
  
 `</DataMining>`  
  
 `...`  
  
 `</ConfigurationSettings>`  
  
## <a name="see-also"></a><span data-ttu-id="72891-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="72891-125">See Also</span></span>  
 <span data-ttu-id="72891-126">[Algorithmes d’exploration de données &#40;Analysis Services d’exploration de données&#41;](data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="72891-126">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="72891-127">Ensemble de lignes DMSCHEMA_MINING_SERVICES</span><span class="sxs-lookup"><span data-stu-id="72891-127">DMSCHEMA_MINING_SERVICES Rowset</span></span>](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-services-rowset)  
  
  
