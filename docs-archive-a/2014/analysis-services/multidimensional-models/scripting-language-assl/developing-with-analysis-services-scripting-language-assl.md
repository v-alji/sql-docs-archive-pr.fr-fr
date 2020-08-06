---
title: Développement avec le langage de script Analysis Services (ASSL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Analysis Services Scripting Language
- ASSL
ms.assetid: ce9aca4d-b7ad-451e-bb7f-20c2b0c03f29
author: minewiskan
ms.author: owend
ms.openlocfilehash: fbb64c120e67d5b4ac12e7bd77f0e0c4e5736757
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605805"
---
# <a name="developing-with-analysis-services-scripting-language-assl"></a><span data-ttu-id="ff279-102">Développement avec le langage de script Analysis Services (ASSL)</span><span class="sxs-lookup"><span data-stu-id="ff279-102">Developing with Analysis Services Scripting Language (ASSL)</span></span>
  <span data-ttu-id="ff279-103">Le langage de script ASSL (Analysis Services Scripting Language) est une extension de XMLA qui ajoute un langage de définition d'objets et un langage de commande pour créer et gérer les structures des services Analysis Services directement sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="ff279-103">Analysis Services Scripting Language (ASSL) is an extension to XMLA that adds an object definition language and command language for creating and managing Analysis Services structures directly on the server.</span></span> <span data-ttu-id="ff279-104">Vous pouvez utiliser ASSL dans l'application personnalisée pour communiquer avec Analysis Services sur le protocole XMLA.</span><span class="sxs-lookup"><span data-stu-id="ff279-104">You can use ASSL in custom application to communicate with Analysis Services over the XMLA protocol.</span></span> <span data-ttu-id="ff279-105">ASSL comprend deux parties :</span><span class="sxs-lookup"><span data-stu-id="ff279-105">ASSL is made up of two parts:</span></span>  
  
-   <span data-ttu-id="ff279-106">Un langage de définition de données (DDL), ou un langage de définition d'objets, qui définit et décrit une instance d'[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], ainsi que les bases de données et les objets de base de données que contient l'instance.</span><span class="sxs-lookup"><span data-stu-id="ff279-106">A Data Definition Language (DDL), or object definition language, defines and describes an instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], as well as the databases and database objects that the instance contains.</span></span>  
  
-   <span data-ttu-id="ff279-107">Un langage de commande qui envoie des commandes d'action, telles que `Create`, `Alter` ou `Process`, à une instance d'Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="ff279-107">A command language that sends action commands, such as `Create`, `Alter`, or `Process`, to an instance of Analysis Services.</span></span> <span data-ttu-id="ff279-108">Ce langage de commande est abordé dans la [référence de&#41; XML for Analysis &#40;XMLA](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference).</span><span class="sxs-lookup"><span data-stu-id="ff279-108">This command language is discussed in the [XML for Analysis  &#40;XMLA&#41; Reference](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference).</span></span>  
  
 <span data-ttu-id="ff279-109">Pour afficher l'ASSL qui décrit une solution multidimensionnelle dans [!INCLUDE[ssBIDevStudio](../../../includes/ssbidevstudio-md.md)], vous pouvez utiliser la commande Afficher le code au niveau du projet.</span><span class="sxs-lookup"><span data-stu-id="ff279-109">To view the ASSL that describes a multidimensional solution in [!INCLUDE[ssBIDevStudio](../../../includes/ssbidevstudio-md.md)], you can use the View Code command at the project level.</span></span> <span data-ttu-id="ff279-110">Vous pouvez également créer ou modifier le script ASSL dans [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] à l'aide de l'éditeur de requête XMLA.</span><span class="sxs-lookup"><span data-stu-id="ff279-110">You can also create or edit ASSL script in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] using the XMLA query editor.</span></span> <span data-ttu-id="ff279-111">Les scripts que vous créez peuvent être utilisés pour gérer des objets ou pour exécuter des commandes sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="ff279-111">The scripts you build can be used to manage objects or run commands on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff279-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ff279-112">See Also</span></span>  
 <span data-ttu-id="ff279-113">[Objets ASSL et caractéristiques de l’objet](assl-objects-and-object-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="ff279-113">[ASSL Objects and Object Characteristics](assl-objects-and-object-characteristics.md) </span></span>  
 <span data-ttu-id="ff279-114">[Conventions XML ASSL](assl-xml-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="ff279-114">[ASSL XML Conventions](assl-xml-conventions.md) </span></span>  
 [<span data-ttu-id="ff279-115">Sources de données et liaisons &#40;SSAS Multidimensionnel&#41;</span><span class="sxs-lookup"><span data-stu-id="ff279-115">Data Sources and Bindings &#40;SSAS Multidimensional&#41;</span></span>](../data-sources-and-bindings-ssas-multidimensional.md)  
  
  
