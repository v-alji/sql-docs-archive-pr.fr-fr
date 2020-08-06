---
title: Options (éditeur de texte-XML-page mise en forme) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 97373178-d288-4127-af37-d9f5fe1b8607
author: rothja
ms.author: jroth
ms.openlocfilehash: dce36142fe9974c0167fca700c509642e05d89b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701538"
---
# <a name="options-text-editor---xml---formatting-page"></a><span data-ttu-id="3629d-102">Options (Éditeur de texte - XML - Page Mise en forme)</span><span class="sxs-lookup"><span data-stu-id="3629d-102">Options (Text Editor - XML - Formatting Page)</span></span>

<span data-ttu-id="3629d-103">Cette boîte de dialogue vous permet de spécifier les paramètres de mise en forme de l'Éditeur XML.</span><span class="sxs-lookup"><span data-stu-id="3629d-103">This dialog box allows you to specify the formatting settings for the XML Editor.</span></span> <span data-ttu-id="3629d-104">Vous pouvez accéder à la boîte de dialogue **Options** à partir du menu **Outils**.</span><span class="sxs-lookup"><span data-stu-id="3629d-104">You can access the **Options** dialog box from the **Tools** menu.</span></span>  
  
> [!NOTE]  
> <span data-ttu-id="3629d-105">Ces paramètres sont disponibles lorsque vous sélectionnez le dossier **Éditeur de texte**, le dossier **XML**, puis l’option **Mise en forme** de la boîte de dialogue **Options**.</span><span class="sxs-lookup"><span data-stu-id="3629d-105">These settings are available when you select the **Text Editor** folder, the **XML** folder, and then the **Formatting** option from the **Options** dialog box.</span></span>  
  
## <a name="attributes"></a><span data-ttu-id="3629d-106">Attributs</span><span class="sxs-lookup"><span data-stu-id="3629d-106">Attributes</span></span>  
 <span data-ttu-id="3629d-107">**Préserver la mise en forme manuelle des attributs**</span><span class="sxs-lookup"><span data-stu-id="3629d-107">**Preserve manual attribute formatting**</span></span>  
 <span data-ttu-id="3629d-108">Indique qu'il ne faut pas remettre en forme les attributs.</span><span class="sxs-lookup"><span data-stu-id="3629d-108">Do not reformat attributes.</span></span> <span data-ttu-id="3629d-109">Il s'agit de la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="3629d-109">This is the default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3629d-110">Si les attributs se trouvent sur plusieurs lignes, l'éditeur met en retrait chaque ligne d'attributs de façon à correspondre à la mise en retrait de l'élément parent.</span><span class="sxs-lookup"><span data-stu-id="3629d-110">If the attributes are on multiple lines, the editor indents each line of attributes to match the indentation of the parent element.</span></span>  
  
 <span data-ttu-id="3629d-111">\*\*Aligner les attributs chacun sur une ligne séparée \*\*</span><span class="sxs-lookup"><span data-stu-id="3629d-111">**Align attributes each on a separate line**</span></span>  
 <span data-ttu-id="3629d-112">Aligne verticalement le deuxième attribut et les attributs suivants de façon à correspondre à la mise en retrait du premier attribut.</span><span class="sxs-lookup"><span data-stu-id="3629d-112">Align the second and subsequent attributes vertically to match the indentation of the first attribute.</span></span> <span data-ttu-id="3629d-113">Le texte XML suivant montre comment les attributs sont alignés lorsque cette option est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3629d-113">The following XML text is an example of how the attributes would be aligned.</span></span>  
  
```  
<item id = "123-A"  
      name = "hammer"  
      price = "9.95"  
</item>  
```  
  
## <a name="auto-reformat"></a><span data-ttu-id="3629d-114">Remise en forme automatique</span><span class="sxs-lookup"><span data-stu-id="3629d-114">Auto Reformat</span></span>  
 <span data-ttu-id="3629d-115">\*\*En collant le contenu du presse-papiers \*\*</span><span class="sxs-lookup"><span data-stu-id="3629d-115">**On paste from clipboard.**</span></span>  
 <span data-ttu-id="3629d-116">Remet en forme le texte XML collé à partir du Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="3629d-116">Reformat XML text pasted from the clipboard.</span></span>  
  
 <span data-ttu-id="3629d-117">\*\*Après la balise de fin \*\*</span><span class="sxs-lookup"><span data-stu-id="3629d-117">**On completion of end tag**</span></span>  
 <span data-ttu-id="3629d-118">Remet en forme l'élément lorsque la balise de fin est insérée.</span><span class="sxs-lookup"><span data-stu-id="3629d-118">Reformat the element when the end tag is completed.</span></span>  
  
## <a name="mixed-content"></a><span data-ttu-id="3629d-119">Contenu mixte</span><span class="sxs-lookup"><span data-stu-id="3629d-119">Mixed Content</span></span>  
 <span data-ttu-id="3629d-120">\*\*Formater les contenus mixtes par défaut \*\*</span><span class="sxs-lookup"><span data-stu-id="3629d-120">**Format mixed content by default.**</span></span>  
 <span data-ttu-id="3629d-121">Tente de remettre en forme le contenu mixte, sauf lorsque celui-ci se trouve dans une étendue `xml:space="preserve"`.</span><span class="sxs-lookup"><span data-stu-id="3629d-121">Attempt to reformat mixed content, except when the content is found in an `xml:space="preserve"` scope.</span></span> <span data-ttu-id="3629d-122">Il s'agit de la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="3629d-122">This is the default.</span></span>  
  
 <span data-ttu-id="3629d-123">Si un élément contient un mélange de texte et de balises, le contenu est considéré comme mixte.</span><span class="sxs-lookup"><span data-stu-id="3629d-123">If an element contains a mix of text and markup, the contents are considered to be mixed content.</span></span> <span data-ttu-id="3629d-124">Voici un exemple de contenu mixte.</span><span class="sxs-lookup"><span data-stu-id="3629d-124">Following is an example of an element with mixed content.</span></span>  
  
```  
<dir>c:\data\AlphaProject\  
  <file readOnly="false">test1.txt</file>  
  <file readOnly="false">test2.txt</file>  
```  
  
 \</dir>  
  
## <a name="see-also"></a><span data-ttu-id="3629d-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3629d-125">See Also</span></span>  
 [<span data-ttu-id="3629d-126">Éditeur XML &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3629d-126">XML Editor &#40;SQL Server Management Studio&#41;</span></span>](../ssms/sql-server-management-studio-ssms.md)  
