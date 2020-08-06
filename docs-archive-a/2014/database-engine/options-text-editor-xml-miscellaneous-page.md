---
title: Options (éditeur de texte-XML-page divers) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 1a9509f0-c663-4b31-b396-7f5dc4371651
author: rothja
ms.author: jroth
ms.openlocfilehash: d937368d30122442ccbc40372a6b8e1cabc141e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694688"
---
# <a name="options-text-editor---xml---miscellaneous-page"></a><span data-ttu-id="2ff8d-102">Options (Éditeur de texte - XML - Page Divers)</span><span class="sxs-lookup"><span data-stu-id="2ff8d-102">Options (Text Editor - XML - Miscellaneous Page)</span></span>

<span data-ttu-id="2ff8d-103">La boîte de dialogue **Options** vous permet de modifier les paramètres de saisie automatique et de schémas de l’Éditeur XML.</span><span class="sxs-lookup"><span data-stu-id="2ff8d-103">The **Options** dialog box lets you change the autocompletion and schema settings for the XML Editor.</span></span> <span data-ttu-id="2ff8d-104">Pour accéder à ces paramètres, dans le menu **Outils** , cliquez sur **Options**, développez le dossier **Éditeur de texte** , cliquez sur **XML** , puis sur **Divers** .</span><span class="sxs-lookup"><span data-stu-id="2ff8d-104">These settings are available when, on the **Tools** menu, you click **Options**, expand the **Text Editor** folder, click **XML** and then click **Miscellaneous** .</span></span>  
  
## <a name="auto-insert"></a><span data-ttu-id="2ff8d-105">Insertion automatique</span><span class="sxs-lookup"><span data-stu-id="2ff8d-105">Auto Insert</span></span>  
 <span data-ttu-id="2ff8d-106">**Balises de fermeture**</span><span class="sxs-lookup"><span data-stu-id="2ff8d-106">**Close tags**</span></span>  
 <span data-ttu-id="2ff8d-107">L'Éditeur de texte ajoute des balises de fin lors de la création d'éléments XML.</span><span class="sxs-lookup"><span data-stu-id="2ff8d-107">The Text Editor adds close tags when authoring XML elements.</span></span> <span data-ttu-id="2ff8d-108">Si la balise de début d'un élément est sélectionnée, l'Éditeur insère la balise de fin correspondante avec un préfixe d'espace de noms équivalent.</span><span class="sxs-lookup"><span data-stu-id="2ff8d-108">If an element start tag is selected, the editor inserts the matching close tag, including a matching namespace prefix.</span></span> <span data-ttu-id="2ff8d-109">Cette case à cocher est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="2ff8d-109">This check box is selected by default.</span></span>  
  
 <span data-ttu-id="2ff8d-110">**Guillemets d'attribut**</span><span class="sxs-lookup"><span data-stu-id="2ff8d-110">**Attribute quotes**</span></span>  
 <span data-ttu-id="2ff8d-111">Lors de la création d’attributs XML, l’Éditeur insère les caractères `="``"` et place le signe insertion (**^)** à l’intérieur des guillemets.</span><span class="sxs-lookup"><span data-stu-id="2ff8d-111">When authoring XML attributes, the editor inserts the `="``"` characters and positions the caret (**^)** inside the quotation marks.</span></span> <span data-ttu-id="2ff8d-112">Cette case à cocher est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="2ff8d-112">This check box is selected by default.</span></span>  
  
 <span data-ttu-id="2ff8d-113">**Déclarations d'espace de noms**</span><span class="sxs-lookup"><span data-stu-id="2ff8d-113">**Namespace declarations**</span></span>  
 <span data-ttu-id="2ff8d-114">L'Éditeur insère automatiquement les déclarations d'espace de noms là où elles sont requises.</span><span class="sxs-lookup"><span data-stu-id="2ff8d-114">The editor automatically inserts namespace declarations wherever they are needed.</span></span> <span data-ttu-id="2ff8d-115">Cette case à cocher est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="2ff8d-115">This check box is selected by default.</span></span>  
  
 <span data-ttu-id="2ff8d-116">**Autre balisage (Commentaires, CDATA)**</span><span class="sxs-lookup"><span data-stu-id="2ff8d-116">**Other markup (Comments, CDATA)**</span></span>  
 <span data-ttu-id="2ff8d-117">Les éléments CDATA, DOCTYPE, les commentaires, les instructions de traitement et autre balisage sont entrés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="2ff8d-117">Comments, CDATA, DOCTYPE, processing instructions, and other markup is autocompleted.</span></span> <span data-ttu-id="2ff8d-118">Cette case à cocher est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="2ff8d-118">This check box is selected by default.</span></span>  
  
## <a name="network"></a><span data-ttu-id="2ff8d-119">Réseau</span><span class="sxs-lookup"><span data-stu-id="2ff8d-119">Network</span></span>  
 <span data-ttu-id="2ff8d-120">**Télécharger automatiquement les DTD et les schémas**</span><span class="sxs-lookup"><span data-stu-id="2ff8d-120">**Automatically download DTDs and schemas**</span></span>  
 <span data-ttu-id="2ff8d-121">Les schémas et les définitions de type de document (DTD) sont automatiquement téléchargés à partir d'emplacements HTTP.</span><span class="sxs-lookup"><span data-stu-id="2ff8d-121">Schemas and document type definitions (DTDs) are automatically downloaded from HTTP locations.</span></span> <span data-ttu-id="2ff8d-122">Cette fonctionnalité utilise System.Net avec détection de serveur de proxy automatique.</span><span class="sxs-lookup"><span data-stu-id="2ff8d-122">This feature uses System.Net with autoproxy server detection enabled.</span></span> <span data-ttu-id="2ff8d-123">Cette case à cocher est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="2ff8d-123">This check box is selected by default.</span></span>  
  
## <a name="outlining"></a><span data-ttu-id="2ff8d-124">mode Plan</span><span class="sxs-lookup"><span data-stu-id="2ff8d-124">Outlining</span></span>  
 <span data-ttu-id="2ff8d-125">**Passer en mode Plan à l'ouverture des fichiers**</span><span class="sxs-lookup"><span data-stu-id="2ff8d-125">**Enter outlining mode when files open**</span></span>  
 <span data-ttu-id="2ff8d-126">Active la fonctionnalité mode Plan lorsqu'un fichier est ouvert.</span><span class="sxs-lookup"><span data-stu-id="2ff8d-126">Turns on the outlining feature when a file is opened.</span></span> <span data-ttu-id="2ff8d-127">Cette case à cocher est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="2ff8d-127">This check box is selected by default.</span></span>  
  
## <a name="caching"></a><span data-ttu-id="2ff8d-128">Mise en cache</span><span class="sxs-lookup"><span data-stu-id="2ff8d-128">Caching</span></span>  
 <span data-ttu-id="2ff8d-129">**Schémas**</span><span class="sxs-lookup"><span data-stu-id="2ff8d-129">**Schemas**</span></span>  
 <span data-ttu-id="2ff8d-130">Indique l'emplacement du cache des schémas.</span><span class="sxs-lookup"><span data-stu-id="2ff8d-130">Specifies the location of the schema cache.</span></span> <span data-ttu-id="2ff8d-131">Le bouton Parcourir (...) ouvre l'emplacement actuel du cache des schémas dans une nouvelle fenêtre.</span><span class="sxs-lookup"><span data-stu-id="2ff8d-131">The Browse button (...) opens the current schema cache location in a new window.</span></span> <span data-ttu-id="2ff8d-132">L’emplacement par défaut est *\<Management Studio install directory>* \Xml\Schemas.</span><span class="sxs-lookup"><span data-stu-id="2ff8d-132">The default location is *\<Management Studio install directory>* \Xml\Schemas.</span></span>  
