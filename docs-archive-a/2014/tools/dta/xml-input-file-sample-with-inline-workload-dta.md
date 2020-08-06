---
title: Exemple de fichier d’entrée XML avec une charge de travail inline (Assistant Paramétrage de base de données) | Microsoft Docs
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
ms.assetid: 7c04fe1d-6669-44a1-8b73-36d469e9b002
author: stevestein
ms.author: sstein
ms.openlocfilehash: 93b2ab4279378b4cd392d97a9b65f299d0e9c6dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603741"
---
# <a name="xml-input-file-sample-with-inline-workload-dta"></a><span data-ttu-id="b7983-102">Exemple de fichier d'entrée XML avec une charge de travail Inline (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="b7983-102">XML Input File Sample with Inline Workload (DTA)</span></span>
  <span data-ttu-id="b7983-103">Copiez et collez cet exemple de fichier d'entrée XML qui spécifie une charge de travail avec l'élément **EventString** dans votre éditeur XML ou de texte favori.</span><span class="sxs-lookup"><span data-stu-id="b7983-103">Copy and paste this sample of an XML input file that specifies a workload with the **EventString** element into your favorite XML editor or text editor.</span></span> <span data-ttu-id="b7983-104">Vous pouvez utiliser l'élément **EventString** pour spécifier une charge de travail de script [!INCLUDE[tsql](../../includes/tsql-md.md)] dans le fichier d'entrée XML (au lieu d'un fichier de travail distinct).</span><span class="sxs-lookup"><span data-stu-id="b7983-104">You can use the **EventString** element to specify a [!INCLUDE[tsql](../../includes/tsql-md.md)] script workload in the XML input file instead of using a separate workload file.</span></span> <span data-ttu-id="b7983-105">Une fois cet exemple copié dans votre outil d'édition, remplacez les valeurs spécifiées pour les éléments **Server**, **Database**, **Schema**, **Table**, **Workload**, **EventString**et **TuningOptions** par celles dont vous avez besoin pour votre session de paramétrage.</span><span class="sxs-lookup"><span data-stu-id="b7983-105">After copying this sample into your editing tool, replace the values specified for the **Server**, **Database**, **Schema**, **Table**, **Workload**, **EventString**, and **TuningOptions** elements with those for your specific tuning session.</span></span> <span data-ttu-id="b7983-106">Pour plus d’informations sur tous les attributs et éléments enfants que vous pouvez utiliser avec ces éléments, consultez [Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;](xml-input-file-reference-database-engine-tuning-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="b7983-106">For more information about all of the attributes and child elements that you can use with these elements, see the [XML Input File Reference &#40;Database Engine Tuning Advisor&#41;](xml-input-file-reference-database-engine-tuning-advisor.md).</span></span> <span data-ttu-id="b7983-107">L'exemple ci-dessous utilise uniquement un sous-ensemble des options d'attributs et d'éléments enfants disponibles.</span><span class="sxs-lookup"><span data-stu-id="b7983-107">The following sample uses only a subset of available attribute and child element options.</span></span>  
  
## <a name="code"></a><span data-ttu-id="b7983-108">Code</span><span class="sxs-lookup"><span data-stu-id="b7983-108">Code</span></span>  
 [!code-xml[InputFileSamples#InlineWorkloadInputFile](../../snippets/xml/SQL14/dta_xml/inputfilesamples/xml/dta_xml_input_file_samples.xml#inlineworkloadinputfile)]  
  
## <a name="comments"></a><span data-ttu-id="b7983-109">Commentaires</span><span class="sxs-lookup"><span data-stu-id="b7983-109">Comments</span></span>  
 <span data-ttu-id="b7983-110">`USE database_name` peuvent être spécifiées dans la charge de travail inline contenue dans l'élément **EventString** .</span><span class="sxs-lookup"><span data-stu-id="b7983-110">`USE database_name` statements can be specified in the inline workload that is contained in the **EventString** element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7983-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b7983-111">See Also</span></span>  
 <span data-ttu-id="b7983-112">[Démarrer et utiliser l'Assistant Paramétrage du moteur de base de données](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="b7983-112">[Start and Use the Database Engine Tuning Advisor](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md) </span></span>  
 <span data-ttu-id="b7983-113">[Afficher et utiliser la sortie de l'Assistant Paramétrage du moteur de base de données](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="b7983-113">[View and Work with the Output from the Database Engine Tuning Advisor](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md) </span></span>  
 [<span data-ttu-id="b7983-114">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="b7983-114">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
