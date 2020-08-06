---
title: Documenter et générer des scripts pour une base de données Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- XML for Analysis, scripts
- XMLA, scripts
- scripts [Analysis Services], databases
- documenting databases
- databases [Analysis Services], documenting
- databases [Analysis Services], scripts
ms.assetid: 125044e2-8d36-4733-8743-8bb68ff9aa4e
author: minewiskan
ms.author: owend
ms.openlocfilehash: cfe008b0d6903d7d012eb57d41d6e50240202ec8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613648"
---
# <a name="document-and-script-an-analysis-services-database"></a><span data-ttu-id="d675d-102">Documenter et générer des scripts pour une base de données Analysis Services</span><span class="sxs-lookup"><span data-stu-id="d675d-102">Document and Script an Analysis Services Database</span></span>
  <span data-ttu-id="d675d-103">Après le déploiement d’une base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , vous pouvez utiliser [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour sortir les métadonnées de la base de données ou d’un objet contenu dans la base de données, comme un script XMLA (XML for Analysis).</span><span class="sxs-lookup"><span data-stu-id="d675d-103">After an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database is deployed, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to output the metadata of the database, or of an object contained in the database, as an XML for Analysis (XMLA) script.</span></span> <span data-ttu-id="d675d-104">Vous pouvez sortir ce script dans une nouvelle fenêtre **Éditeur de requête XMLA** , dans un fichier ou dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="d675d-104">You can output this script to a new **XMLA Query Editor** window, to a file, or to the Clipboard.</span></span> <span data-ttu-id="d675d-105">Pour plus d’informations sur XMLA, consultez [Analysis Services Scripting Language &#40;ASSL&#41; Reference](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla).</span><span class="sxs-lookup"><span data-stu-id="d675d-105">For more information about XMLA, see [Analysis Services Scripting Language &#40;ASSL&#41; Reference](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla).</span></span>  
  
 <span data-ttu-id="d675d-106">Le script XMLA généré utilise des éléments ASSL ( [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Scripting Language) pour définir les objets contenus dans le script.</span><span class="sxs-lookup"><span data-stu-id="d675d-106">The generated XMLA script uses [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Scripting Language (ASSL) elements to define the objects contained by the script.</span></span> <span data-ttu-id="d675d-107">Si vous avez généré un script CREATE, le script XMLA obtenu contient une commande XMLA **CREATE** et des éléments ASSL qui peuvent être utilisés pour créer l’intégralité de la structure de la base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] sur une instance.</span><span class="sxs-lookup"><span data-stu-id="d675d-107">If you generated a CREATE script, the resulting XMLA script contains an XMLA **Create** command and ASSL elements that can be used to create the entire [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database structure on an instance.</span></span> <span data-ttu-id="d675d-108">Si vous avez généré un script ALTER, le script XMLA obtenu contient une commande XMLA **ALTER** et des éléments ASSL qui peuvent être utilisés pour restaurer la structure d’une base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] existante dans l’état où la base de données se trouvait au moment de la génération du script.</span><span class="sxs-lookup"><span data-stu-id="d675d-108">If you generated an ALTER script, the resulting XMLA script contains an XMLA **Alter** command and ASSL elements that can be used to restore the structure of an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database to the state of the database at the time the script was created.</span></span>  
  
 <span data-ttu-id="d675d-109">Vous pouvez utiliser le script XMLA généré à partir d'une base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] de nombreuses manières, par exemple :</span><span class="sxs-lookup"><span data-stu-id="d675d-109">You can use the generated XMLA script from an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in many ways, including:</span></span>  
  
-   <span data-ttu-id="d675d-110">pour maintenir un script de sauvegarde qui vous permet de recréer tous les objets et toutes les autorisations de la base de données ;</span><span class="sxs-lookup"><span data-stu-id="d675d-110">To maintain a backup script that allows you to recreate all the database objects and permissions.</span></span>  
  
-   <span data-ttu-id="d675d-111">pour créer ou mettre à jour le code de développement de la base de données ;</span><span class="sxs-lookup"><span data-stu-id="d675d-111">To create or update database development code.</span></span>  
  
-   <span data-ttu-id="d675d-112">pour créer un environnement de test ou de développement à partir d'un schéma existant.</span><span class="sxs-lookup"><span data-stu-id="d675d-112">To create a test or development environment from an existing schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d675d-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d675d-113">See Also</span></span>  
 <span data-ttu-id="d675d-114">[Modifier ou supprimer une base de données Analysis Services](modify-or-delete-an-analysis-services-database.md) </span><span class="sxs-lookup"><span data-stu-id="d675d-114">[Modify or Delete an Analysis Services Database](modify-or-delete-an-analysis-services-database.md) </span></span>  
 <span data-ttu-id="d675d-115">[ALTER Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/alter-element-xmla) </span><span class="sxs-lookup"><span data-stu-id="d675d-115">[Alter Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/alter-element-xmla) </span></span>  
 [<span data-ttu-id="d675d-116">Élément Create &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="d675d-116">Create Element &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla)  
  
  
