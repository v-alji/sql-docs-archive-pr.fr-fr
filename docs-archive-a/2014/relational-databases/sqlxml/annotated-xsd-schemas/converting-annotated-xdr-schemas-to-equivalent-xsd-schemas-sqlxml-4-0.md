---
title: Conversion de schémas XDR annotés en schémas XSD équivalents (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XDR schemas, converting schemas
- annotated XSD schemas, converting schemas
- XDR to XSD Converter tool [SQLXML]
- XDR schemas [SQLXML], converting
- converting annotated schemas
- mapping schema [SQLXML], conversions
- XSD schemas [SQLXML], converting schemas
ms.assetid: 151c94a8-66d3-4c46-a5ff-a22df456940a
author: rothja
ms.author: jroth
ms.openlocfilehash: c36eb17aacb61a47fad0f389de9a3c216202827d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611682"
---
# <a name="converting-annotated-xdr-schemas-to-equivalent-xsd-schemas-sqlxml-40"></a><span data-ttu-id="7c83b-102">Conversion de schémas XDR annotés en schémas XSD équivalents (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="7c83b-102">Converting Annotated XDR Schemas to Equivalent XSD Schemas (SQLXML 4.0)</span></span>
  <span data-ttu-id="7c83b-103">Le langage XSD (XML Schema Definition) est le successeur du langage de définition de schéma XDR (XML-Data Reduced).</span><span class="sxs-lookup"><span data-stu-id="7c83b-103">The XML Schema Definition (XSD) language is the successor to the XML-Data Reduced (XDR) schema definition language.</span></span> <span data-ttu-id="7c83b-104">Avec l'introduction de la prise en charge du langage XSD dans [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0, les nouveaux schémas annotés sont donc supposés être créés à l'aide de ce langage XSD.</span><span class="sxs-lookup"><span data-stu-id="7c83b-104">With the introduction of XSD support in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0, it is assumed that new annotated schemas are created using XSD.</span></span> <span data-ttu-id="7c83b-105">SQLXML 4.0 inclut un outil de conversion XDR vers XSD conçu pour vous aider à convertir vos schémas XDR annotés en schémas XSD équivalents.</span><span class="sxs-lookup"><span data-stu-id="7c83b-105">SQLXML 4.0 includes an XDR to XSD converter tool that is designed to help you convert your existing annotated XDR schemas to equivalent XSD schemas.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7c83b-106">Utilisez cet outil uniquement lorsque vous souhaitez convertir des schémas XDR annotés en XSD pour une utilisation avec SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="7c83b-106">Use this tool only when you want to convert annotated XDR schemas to XSD for use with SQLXML 4.0.</span></span> <span data-ttu-id="7c83b-107">Il ne s'agit pas d'un outil de conversion XDR vers XSD à usage général.</span><span class="sxs-lookup"><span data-stu-id="7c83b-107">This is not a general purpose XDR to XSD converter tool.</span></span> <span data-ttu-id="7c83b-108">Les schémas XSD convertis peuvent ne pas se comporter de la même façon que les schémas XDR d'origine en cas d'utilisation dans d'autres environnements.</span><span class="sxs-lookup"><span data-stu-id="7c83b-108">The converted XSD schemas may not behave the same as the original XDR schemas when used in other environments.</span></span>  
  
 <span data-ttu-id="7c83b-109">Si le fichier XDR d'entrée spécifie l'encodage dans la déclaration XML, cela devient l'encodage du fichier de sortie XSD généré.</span><span class="sxs-lookup"><span data-stu-id="7c83b-109">If the input XDR file specifies the encoding within the XML declaration, this becomes the encoding of the XSD output file that is generated.</span></span>  
  
 <span data-ttu-id="7c83b-110">L'outil de conversion (Cvtschema.exe) est installé dans le dossier \Program Files\SQLXML 4.0\bin et exécuté à l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="7c83b-110">The converter tool (Cvtschema.exe) is installed in the Program Files\SQLXML 4.0\bin folder and is executed at the command prompt.</span></span>  
  
 <span data-ttu-id="7c83b-111">Voici la syntaxe générale :</span><span class="sxs-lookup"><span data-stu-id="7c83b-111">This is the general syntax:</span></span>  
  
```  
cvtschema XDRFileName, [-y], [-w] [-?]  
```  
  
 <span data-ttu-id="7c83b-112">Où :</span><span class="sxs-lookup"><span data-stu-id="7c83b-112">Where:</span></span>  
  
 <span data-ttu-id="7c83b-113">XDRFileName</span><span class="sxs-lookup"><span data-stu-id="7c83b-113">XDRFileName</span></span>  
 <span data-ttu-id="7c83b-114">Est le nom du fichier XDR qui doit être converti en XSD.</span><span class="sxs-lookup"><span data-stu-id="7c83b-114">Is the name of the XDR file that is to be converted to XSD.</span></span> <span data-ttu-id="7c83b-115">L'outil lit le fichier XDR d'entrée et crée un fichier de sortie XSD dans le répertoire de travail actif.</span><span class="sxs-lookup"><span data-stu-id="7c83b-115">The tool reads the input XDR file and creates an XSD output file in the current working directory.</span></span> <span data-ttu-id="7c83b-116">Si le fichier d'entrée a une extension .xdr ou .xml, le fichier XSD de sortie est créé avec le même nom mais avec une extension .xsd.</span><span class="sxs-lookup"><span data-stu-id="7c83b-116">If the input file has an .xdr or .xml extension, the output XSD file is created with the same name but with an .xsd extension.</span></span> <span data-ttu-id="7c83b-117">Si l'extension du fichier d'entrée n'est ni .xdr ni .xml (ou si elle est manquante), le fichier de sortie est créé avec le même nom et l'extension .xsd est ajoutée au nom de fichier d'entrée.</span><span class="sxs-lookup"><span data-stu-id="7c83b-117">If the input file extension is other than .xml or .xdr (or if the extension is missing), the output file is created with the same name and the .xsd extension is appended to the input file name.</span></span> <span data-ttu-id="7c83b-118">Par exemple, si le nom de fichier XDR d'entrée est SampleFile.abc, le fichier XSD résultant est enregistré en tant que SampleFile.abc.xsd.</span><span class="sxs-lookup"><span data-stu-id="7c83b-118">For example, if the input XDR file name is SampleFile.abc, the resulting XSD is saved as SampleFile.abc.xsd.</span></span>  
  
 <span data-ttu-id="7c83b-119">-y</span><span class="sxs-lookup"><span data-stu-id="7c83b-119">-y</span></span>  
 <span data-ttu-id="7c83b-120">(Facultatif) Remplace le fichier XSD existant par le fichier XSD généré par l'outil de conversion.</span><span class="sxs-lookup"><span data-stu-id="7c83b-120">(Optional) Overwrites the existing XSD file with the XSD file that is generated by the converter tool.</span></span> <span data-ttu-id="7c83b-121">Si l'indicateur n'est pas spécifié, l'outil vous invite à spécifier si vous souhaitez remplacer le fichier XSD existant et vous donne la possibilité de modifier le nom de fichier de sortie.</span><span class="sxs-lookup"><span data-stu-id="7c83b-121">If the flag is not specified, the tool prompts you to specify whether you want to overwrite the existing XSD file and gives you the option to change the output file name.</span></span>  
  
 <span data-ttu-id="7c83b-122">-w</span><span class="sxs-lookup"><span data-stu-id="7c83b-122">-w</span></span>  
 <span data-ttu-id="7c83b-123">(Facultatif) Retourne des avertissements récupérables générés durant le processus de conversion par l'outil.</span><span class="sxs-lookup"><span data-stu-id="7c83b-123">(Optional) Returns nonfatal warnings that are generated in the conversion process by the tool.</span></span> <span data-ttu-id="7c83b-124">Par défaut, l'outil affiche les messages uniquement pour les erreurs irrécupérables.</span><span class="sxs-lookup"><span data-stu-id="7c83b-124">By default, the tool displays messages only for fatal errors.</span></span>  
  
 <span data-ttu-id="7c83b-125">-?</span><span class="sxs-lookup"><span data-stu-id="7c83b-125">-?</span></span>  
 <span data-ttu-id="7c83b-126">Retourne une liste des options que vous pouvez spécifier avec `cvtschema`, accompagnées d'une explication.</span><span class="sxs-lookup"><span data-stu-id="7c83b-126">Returns a list of options that you can specify with `cvtschema`, along with an explanation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c83b-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7c83b-127">See Also</span></span>  
 <span data-ttu-id="7c83b-128">[Mappage de types de données XSD à des types de données XPath &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="7c83b-128">[Mapping XSD Data Types to XPath Data Types &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="7c83b-129">Annotations XSD &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="7c83b-129">XSD Annotations &#40;SQLXML 4.0&#41;</span></span>](../../sqlxml-annotated-xsd-schemas-using/xsd-annotations-sqlxml-4-0.md)  
  
  
