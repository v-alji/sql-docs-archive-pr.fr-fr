---
title: Caractères non valides et règles d’échappement | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, invalid characters
- FOR XML clause, escape rules
ms.assetid: f2e9b997-f400-4963-b225-59d46c6b93e8
author: rothja
ms.author: jroth
ms.openlocfilehash: 8624a31dea4e97e05da6d86c3c0c518b9c4d0aba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709020"
---
# <a name="invalid-characters-and-escape-rules"></a><span data-ttu-id="017a3-102">Caractères non valides et règles d'échappement</span><span class="sxs-lookup"><span data-stu-id="017a3-102">Invalid Characters and Escape Rules</span></span>
  <span data-ttu-id="017a3-103">Cette rubrique décrit comment les caractères XML non valides sont contrôlés par la clause FOR XML, et répertorie les règles d'échappement pour les caractères qui ne sont pas valides dans les noms XML.</span><span class="sxs-lookup"><span data-stu-id="017a3-103">This topic describes how invalid XML characters are handled by the FOR XML clause, and lists the escape rules for characters that are invalid in XML names.</span></span>  
  
## <a name="for-xml-and-invalid-characters"></a><span data-ttu-id="017a3-104">FOR XML et les caractères non valides</span><span class="sxs-lookup"><span data-stu-id="017a3-104">For XML and Invalid Characters</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="017a3-105">convertit en entités les caractères XML non valides quand ils sont retournés dans des requêtes FOR XML qui n’utilisent pas la directive TYPE.</span><span class="sxs-lookup"><span data-stu-id="017a3-105">entitizes invalid XML characters when they are returned within FOR XML queries that do not use the TYPE directive.</span></span>  
  
 <span data-ttu-id="017a3-106">Bien que les analyseurs XML 1.0 génèrent des erreurs d'analyse, que ces caractères soient ou non codés sous forme d'entité, le codage d'entité est plus en conformité avec XML 1.1.</span><span class="sxs-lookup"><span data-stu-id="017a3-106">Although XML 1.0 conformant parsers raise parse errors regardless of whether these characters are entitized or not, the entitized form is better aligned with XML 1.1.</span></span> <span data-ttu-id="017a3-107">Le codage d'entité est aussi en meilleure adéquation avec les futures versions de la norme XML.</span><span class="sxs-lookup"><span data-stu-id="017a3-107">The entitized form is also potentially better aligned with future versions of the XML standard.</span></span> <span data-ttu-id="017a3-108">De plus, il facilite le débogage puisque le point de code du caractère incorrect est visible.</span><span class="sxs-lookup"><span data-stu-id="017a3-108">Additionally, it makes debugging simpler, because the code point of the invalid character becomes visible.</span></span>  
  
 <span data-ttu-id="017a3-109">Pour les utilisateurs d'outils XML, il n'existe aucun moyen de contourner le problème puisque l'analyseur XML échouera quoi qu'il arrive au point où se présentent les caractères non valides dans le flux de données.</span><span class="sxs-lookup"><span data-stu-id="017a3-109">For users of XML tools, no workaround is required, because the XML parser will fail either way at the point where the invalid characters occur in the data stream.</span></span> <span data-ttu-id="017a3-110">Si vous utilisez des outils non XML, cette modification risque de vous imposer la mise à jour de votre logique de programmation afin de rechercher ces caractères sous la forme de leurs codes d'entité.</span><span class="sxs-lookup"><span data-stu-id="017a3-110">If you use non-XML tools, this change can require you to update your programming logic to search for these characters as entitized values.</span></span>  
  
 <span data-ttu-id="017a3-111">Les caractères d'espace suivants sont codés différemment dans les requêtes FOR XML afin de les garder présents tout au long des va-et-vient :</span><span class="sxs-lookup"><span data-stu-id="017a3-111">The following white space characters are entitized differently in FOR XML queries to preserve their presence through round-tripping:</span></span>  
  
-   <span data-ttu-id="017a3-112">Dans le contenu d’élément et d’attribut : **hex(0D)** (retour chariot)</span><span class="sxs-lookup"><span data-stu-id="017a3-112">In element content and attributes: **hex(0D)** (carriage return)</span></span>  
  
-   <span data-ttu-id="017a3-113">Dans le contenu d’attribut : **hex(09)** (tabulation), **hex(0A)** (saut de ligne)</span><span class="sxs-lookup"><span data-stu-id="017a3-113">In attribute content: **hex(09)** (tab), **hex(0A)** (line feed)</span></span>  
  
 <span data-ttu-id="017a3-114">Ces caractères sont conservés dans la sortie et ne seront pas normalisés par un analyseur.</span><span class="sxs-lookup"><span data-stu-id="017a3-114">These characters are preserved in output, and a parser will not normalize them.</span></span>  
  
## <a name="escape-rules"></a><span data-ttu-id="017a3-115">Règles d'échappement</span><span class="sxs-lookup"><span data-stu-id="017a3-115">Escape Rules</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="017a3-116">Les noms contenant des caractères non valides pour les noms XML (comme les espaces) sont convertis en noms XML de telle façon que les caractères non valides soient convertis en codages d’entités numériques placés dans une séquence d’échappement.</span><span class="sxs-lookup"><span data-stu-id="017a3-116">names that contain characters that are invalid in XML names, such as spaces, are translated into XML names in a way in which the invalid characters are translated into escaped numeric entity encoding.</span></span>  
  
 <span data-ttu-id="017a3-117">Seuls deux caractères non alphabétiques sont autorisés au début d'un nom XML : les deux-points (:) et le trait de soulignement (_).</span><span class="sxs-lookup"><span data-stu-id="017a3-117">There are only two non-alphabetic characters that can occur within an XML name: the colon (:) and the underscore (_).</span></span> <span data-ttu-id="017a3-118">Dans la mesure où les deux-points (:) sont déjà réservés aux espaces de noms, le trait de soulignement (_) est utilisé comme caractère d'échappement.</span><span class="sxs-lookup"><span data-stu-id="017a3-118">Because the colon is already reserved for namespaces, the underscore is chosen as the escape character.</span></span> <span data-ttu-id="017a3-119">Les règles d'échappement utilisées pour l'encodage sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="017a3-119">Following are the escape rules that are used for encoding:</span></span>  
  
-   <span data-ttu-id="017a3-120">Tout caractère UCS-2 qui n’est pas un caractère valide pour un nom XML (selon la spécification XML 1.0), est placé dans une séquence d’échappement sous la forme _xHHHH\_.</span><span class="sxs-lookup"><span data-stu-id="017a3-120">Any UCS-2 character that is not a valid XML name character, according to the XML 1.0 specification, is escaped as _xHHHH\_.</span></span> <span data-ttu-id="017a3-121">La chaîne HHHH désigne le code hexadécimal UCS-2 à quatre chiffres du caractère dans l'ordre du bit le plus significatif en premier.</span><span class="sxs-lookup"><span data-stu-id="017a3-121">The HHHH stands for the four-digit hexadecimal UCS-2 code for the character in the most significant bit-first order.</span></span> <span data-ttu-id="017a3-122">Par exemple, le nom de la table **Order Details** est encodé sous la forme Order_x0020_Details.</span><span class="sxs-lookup"><span data-stu-id="017a3-122">For example, the table name **Order Details** is encoded as Order_x0020_Details.</span></span>  
  
-   <span data-ttu-id="017a3-123">Les caractères qui n’entrent pas dans le domaine UCS-2 (les ajouts UCS-4 correspondant à la plage comprise entre U+00010000 et U+0010FFFF) sont encodés sous la forme _xHHHHHHHH\_,</span><span class="sxs-lookup"><span data-stu-id="017a3-123">Characters that do not fit into the UCS-2 realm (the UCS-4 additions of the range U+00010000 to U+0010FFFF) are encoded as _xHHHHHHHH\_.</span></span> <span data-ttu-id="017a3-124">où HHHHHHHH représente l'encodage UCS-4 hexadécimal à huit chiffres du caractère, en cas d'utilisation du mode de compatibilité ascendante avec SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="017a3-124">The HHHHHHHH stands for the eight-digit hexadecimal UCS-4 encoding of the character, if under SQL Server 2000 backward compatibility mode.</span></span> <span data-ttu-id="017a3-125">Dans tous les autres cas, les caractères sont encodés sous la forme _xHHHHHH\_de façon à respecter la norme ISO.</span><span class="sxs-lookup"><span data-stu-id="017a3-125">Otherwise, the characters are encoded as_xHHHHHH\_, in order to align with the ISO standard.</span></span>  
  
-   <span data-ttu-id="017a3-126">Le caractère de soulignement n'a pas besoin d'être placé dans une séquence d'échappement, sauf s'il est suivi du caractère x.</span><span class="sxs-lookup"><span data-stu-id="017a3-126">The underscore character does not have to be escaped unless it is followed by the character x.</span></span> <span data-ttu-id="017a3-127">Par exemple, le nom de la table **Order_Details** n’est pas encodé.</span><span class="sxs-lookup"><span data-stu-id="017a3-127">For example, the table name **Order_Details** is not encoded.</span></span>  
  
-   <span data-ttu-id="017a3-128">Dans les identificateurs, les deux-points (:) ne sont pas placés dans une séquence d'échappement pour que les noms d'élément ou d'attribut des espaces de noms puissent être générés par la requête FOR XML.</span><span class="sxs-lookup"><span data-stu-id="017a3-128">The colon in identifiers is not escaped As a result, the namespace element and attribute names can be generated by the FOR XML query.</span></span> <span data-ttu-id="017a3-129">Par exemple, la requête suivante génère un attribut d'espace de noms comportant deux-points (:) dans le nom :</span><span class="sxs-lookup"><span data-stu-id="017a3-129">For example, the following query generates a namespace attribute that has a colon in the name:</span></span>  
  
    ```  
    SELECT 'namespace-urn' as 'xmlns:namespace',   
     1 as 'namespace:a'   
    FOR XML RAW  
    ```  
  
     <span data-ttu-id="017a3-130">La requête produit le résultat suivant :</span><span class="sxs-lookup"><span data-stu-id="017a3-130">The query produces this result:</span></span>  
  
    ```  
    <row xmlns:namespace="namespace-urn" namespace:a="1"/>  
    ```  
  
     <span data-ttu-id="017a3-131">Notez qu'il est quand même préférable d'utiliser WITH XMLNAMESPACES pour ajouter des espaces de noms XML.</span><span class="sxs-lookup"><span data-stu-id="017a3-131">Note that WITH XMLNAMESPACES is the recommended way to add XML namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="017a3-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="017a3-132">See Also</span></span>  
 [<span data-ttu-id="017a3-133">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="017a3-133">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
