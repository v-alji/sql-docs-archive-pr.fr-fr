---
title: Exemple de fichier d’entrée XML avec une configuration spécifiée par l’utilisateur (Assistant Paramétrage de base de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- sample applications [DTA]
ms.assetid: b29c9716-e5c3-4003-9efb-3ade2197b630
author: stevestein
ms.author: sstein
ms.openlocfilehash: 121972518aa114e16cc81517d52a9d9656b067c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612042"
---
# <a name="xml-input-file-sample-with-user-specified-configuration-dta"></a><span data-ttu-id="0beba-102">Exemple de fichier d'entrée XML avec une configuration spécifiée par l'utilisateur (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="0beba-102">XML Input File Sample with User-specified Configuration (DTA)</span></span>
  <span data-ttu-id="0beba-103">Copiez et collez cet exemple de fichier d’entrée XML qui spécifie une configuration spécifiée par l’utilisateur avec l’élément **Configuration** dans votre éditeur XML ou de texte favori.</span><span class="sxs-lookup"><span data-stu-id="0beba-103">Copy and paste this sample of an XML input file that specifies a user-specified configuration with the **Configuration** element into your favorite XML editor or text editor.</span></span> <span data-ttu-id="0beba-104">Vous pouvez ainsi effectuer une évaluation de simulation.</span><span class="sxs-lookup"><span data-stu-id="0beba-104">This enables you to perform "what-if" analysis.</span></span> <span data-ttu-id="0beba-105">Une évaluation de simulation implique l’utilisation de l’élément **Configuration** pour spécifier un ensemble de structures PDS hypothétiques pour la base de données que vous souhaitez paramétrer.</span><span class="sxs-lookup"><span data-stu-id="0beba-105">"What-if" analysis involves using the **Configuration** element to specify a set of hypothetical physical design structures for the database you want to tune.</span></span> <span data-ttu-id="0beba-106">Vous pouvez ensuite utiliser l'Assistant Paramétrage du moteur de base de données pour analyser les effets de l'exécution d'une charge de travail dans cette configuration hypothétique en vue de déterminer si elle améliore les performances du traitement des requêtes.</span><span class="sxs-lookup"><span data-stu-id="0beba-106">Then you use Database Engine Tuning Advisor to analyze the effects of running a workload against this hypothetical configuration to find out whether it improves query processing performance.</span></span> <span data-ttu-id="0beba-107">Ce type d'analyse offre l'avantage de pouvoir évaluer la nouvelle configuration sans avoir à supporter la charge induite par une mise en œuvre effective.</span><span class="sxs-lookup"><span data-stu-id="0beba-107">This type of analysis provides the advantage of evaluating the new configuration without incurring the overhead of actually implementing it.</span></span> <span data-ttu-id="0beba-108">Si votre configuration hypothétique ne permet pas d'améliorer suffisamment les performances, vous pouvez facilement la modifier et l'analyser de nouveau jusqu'à obtention des résultats escomptés.</span><span class="sxs-lookup"><span data-stu-id="0beba-108">If your hypothetical configuration does not provide the performance improvements you want, it is easy to change it and analyze it again until you reach the configuration that produces the results you need.</span></span>  
  
 <span data-ttu-id="0beba-109">Une fois cet exemple copié dans votre outil d'édition, remplacez les valeurs spécifiées pour les éléments **Server**, **Database**, **Schema**, **Table**, **Workload**, **TuningOptions**et **Configuration** par celles dont vous avez besoin pour votre session de paramétrage.</span><span class="sxs-lookup"><span data-stu-id="0beba-109">After copying this sample into your editing tool, replace the values specified for the **Server**, **Database**, **Schema**, **Table**, **Workload**, **TuningOptions**, and **Configuration** elements with those for your specific tuning session.</span></span> <span data-ttu-id="0beba-110">Pour plus d’informations sur tous les attributs et éléments enfants que vous pouvez utiliser avec ces éléments, consultez [Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;](xml-input-file-reference-database-engine-tuning-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="0beba-110">For more information about all of the attributes and child elements that you can use with these elements, see the [XML Input File Reference &#40;Database Engine Tuning Advisor&#41;](xml-input-file-reference-database-engine-tuning-advisor.md).</span></span> <span data-ttu-id="0beba-111">L'exemple ci-dessous utilise uniquement un sous-ensemble des options d'attributs et d'éléments enfants disponibles.</span><span class="sxs-lookup"><span data-stu-id="0beba-111">The following sample uses only a subset of available attribute and child element options.</span></span>  
  
## <a name="code"></a><span data-ttu-id="0beba-112">Code</span><span class="sxs-lookup"><span data-stu-id="0beba-112">Code</span></span>  
 [!code-xml[InputFileSamples#UserSpecifiedConfigInputFile](../../snippets/xml/SQL14/dta_xml/inputfilesamples/xml/dta_xml_input_file_samples.xml#userspecifiedconfiginputfile)]  
  
## <a name="comments"></a><span data-ttu-id="0beba-113">Commentaires</span><span class="sxs-lookup"><span data-stu-id="0beba-113">Comments</span></span>  
  
-   <span data-ttu-id="0beba-114">La suppression de structures PDS n’est pas prise en charge si vous spécifiez le mode **Absolute** pour l’élément **Configuration** (`Configuration SpecificationMode="Absolute"`).</span><span class="sxs-lookup"><span data-stu-id="0beba-114">Dropping physical design structures is not supported if you specify the **Absolute** mode for the **Configuration** element (`Configuration SpecificationMode="Absolute"`).</span></span>  
  
-   <span data-ttu-id="0beba-115">Vous ne pouvez pas créer et supprimer la même structure PDS dans les deux modes (**Relative** ou **Absolute**) de l’élément **Configuration** .</span><span class="sxs-lookup"><span data-stu-id="0beba-115">You cannot create and drop the same physical design structure in either mode (**Relative** or **Absolute**) of the **Configuration** element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0beba-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0beba-116">See Also</span></span>  
 <span data-ttu-id="0beba-117">[Démarrer et utiliser l'Assistant Paramétrage du moteur de base de données](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="0beba-117">[Start and Use the Database Engine Tuning Advisor](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md) </span></span>  
 <span data-ttu-id="0beba-118">[Afficher et utiliser la sortie de l'Assistant Paramétrage du moteur de base de données](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="0beba-118">[View and Work with the Output from the Database Engine Tuning Advisor](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md) </span></span>  
 [<span data-ttu-id="0beba-119">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="0beba-119">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
